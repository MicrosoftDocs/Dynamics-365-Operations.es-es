---
title: Crear una aplicación de exportación de datos periódica
description: En este artículo se describe cómo crear una aplicación lógica de Microsoft Azure que exporta datos de Microsoft Dynamics 365 Human Resources según una programación periódica.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9c840dbf4f717da3359640ee5c8231ccd129ebb2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875840"
---
# <a name="create-a-recurring-data-export-app"></a>Crear una aplicación de exportación de datos periódica


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

En este artículo se describe cómo crear una aplicación lógica de Microsoft Azure que exporta datos de Microsoft Dynamics 365 Human Resources según una programación periódica. El tutorial aprovecha la interfaz de programación de aplicaciones (API) REST del paquete DMF de Human Resources para exportar los datos. Después de exportar los datos, la aplicación lógica guarda el paquete de datos exportados en la carpeta de Microsoft OneDrive for Business.

## <a name="business-scenario"></a>Escenario empresarial

En un escenario empresarial típico para integraciones de Microsoft Dynamics 365, los datos deben exportarse a un sistema descendente según una programación periódica. Este tutorial muestra cómo exportar todos los registros de trabajo de Microsoft Dynamics 365 Human Resources y guardar la lista de trabajadores en una carpeta de OneDrive for Business.

> [!TIP]
> Los datos específicos que se exportan en este tutorial y el destino de los datos exportados son solo ejemplos. Puede cambiarlos fácilmente para satisfacer sus necesidades comerciales.

## <a name="technologies-used"></a>Tecnologías utilizadas

Este tutorial utiliza las siguientes tecnologías:

- **[Dynamics 365 Human Resources](https://dynamics.microsoft.com/talent/overview/)**- El origen de datos maestros para los trabajadores que se exportarán.
- **[Azure Logic Apps](https://azure.microsoft.com/services/logic-apps/)** - La tecnología que proporciona la orquestación y la programación de la exportación periódica.

    - **[Conectores](/azure/connectors/apis-list)** - La tecnología que se utiliza para conectar la aplicación lógica con los puntos de conexión requeridos.

        - Conector [HTTP con Azure AD](/connectors/webcontents/)
        - Conector [OneDrive for Business](/azure/connectors/connectors-create-api-onedriveforbusiness)

- **[API REST de paquetes DMF](../fin-ops-core/dev-itpro/data-entities/data-management-api.md)** - La tecnología que se utiliza para activar la exportación y controlar su progreso.
- **[OneDrive for Business](https://onedrive.live.com/about/business/)** - El destino de los trabajadores exportados.

## <a name="prerequisites"></a>Requisitos previos

Antes de comenzar el ejercicio en este tutorial, debe tener los siguientes elementos:

- Un entorno de Human Resources que tiene permisos de nivel de administrador en el entorno.
- Una [suscripción a Azure](https://azure.microsoft.com/free/) para hospedar la aplicación lógica

## <a name="the-exercise"></a>El ejercicio

Al final de este ejercicio, tendrá una aplicación lógica conectada a su entorno de Human Resources y su cuenta de OneDrive for Business. La aplicación lógica exportará un paquete de datos de Human Resources, esperará a que se complete la exportación, descargará el paquete de datos exportado y guardará el paquete de datos en la carpeta de OneDrive for Business que especificó.

La aplicación lógica completada se parecerá a la siguiente ilustración.

![Visión general de las aplicaciones lógicas.](media/integration-logic-app-overview.png)

### <a name="step-1-create-a-data-export-project-in-human-resources"></a>Paso 1: crear un proyecto de exportación de datos en Human Resources

En Human Resources, cree un proyecto de exportación de datos que exporte trabajadores. Asigne al proyecto el nombre **Exportar trabajadores** y asegúrese de que la opción **Generar paquete de datos** está establecida en **Sí**. Agregue una sola entidad (**Trabajador**) al proyecto y seleccione el formato para exportar. (En este tutorial se usa el formato de Microsoft Excel).

![Exportar el proyecto de datos de trabajadores.](media/integration-logic-app-export-workers-project.png)

> [!IMPORTANT]
> Recuerde el nombre del proyecto de exportación de datos. Lo necesitará cuando cree la aplicación lógica en el siguiente paso.

### <a name="step-2-create-the-logic-app"></a>Paso 2: crear la aplicación lógica

La mayor parte del ejercicio implica la creación de la aplicación lógica.

1. En Azure Portal, cree una aplicación lógica.

    ![Página de creación de aplicaciones lógicas.](media/integration-logic-app-creation-1.png)

2. En Logic Apps Designer, comience con una aplicación lógica en blanco.
3. Agregue un [desencadenador de programación periódica](/azure/connectors/connectors-native-recurrence) para ejecutar la aplicación lógica cada 24 horas (o de acuerdo con un horario de su elección).

    ![Cuadro de diálogo Periodicidad.](media/integration-logic-app-recurrence-step.png)

4. Llame a la API REST DMF [ExportToPackage](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#exporttopackage) para programar la exportación del paquete de datos.

    1. Utilice la acción **Invocar una solicitud HTTP** desde el conector HTTP con Azure AD.

        - **URL de recurso base:** la URL del entorno de Human Resources (no incluya información de ruta/espacio de nombres).
        - **URI de recurso de Azure AD**: `http://hr.talent.dynamics.com`

        > [!NOTE]
        > El servicio Human Resources aún no proporciona un conector que exponga todas las API que componen la API REST de paquetes DMF, como **ExportToPackage**. En su lugar, debe llamar a las API utilizando solicitudes HTTPS sin procesar a través del conector HTTP con Azure AD. Este conector usa Azure Active Directory (Azure AD) para la autenticación y autorización en Human Resources.

        ![Conector HTTP con Azure AD.](media/integration-logic-app-http-aad-connector-step.png)

    2. Inicie sesión en el entorno de Human Resources a través del conector HTTP con Azure AD.
    3. Configure una solicitud HTTP **POST** para llamar a la API REST DMF **ExportToPackage**.

        - **Método:** POST
        - **URL de la solicitud:** https://\<hostname\>/espacios de nombres/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.ExportToPackage
        - **Cuerpo de la solicitud:**

            ```JSON
            {
                "definitionGroupId":"Export Workers",
                "packageName":"talent_package.zip",
                "executionId":"",
                "reExecute":false,
                "legalEntityId":"USMF"
            }
            ```

        ![Invocar una acción de solicitud HTTP.](media/integration-logic-app-export-to-package-step.png)

    > [!TIP]
    > Es posible que desee cambiar el nombre de cada paso para que sea más significativo que el nombre predeterminado, **Invocar una solicitud HTTP**. Por ejemplo, puede cambiar el nombre de este paso **ExportToPackage**.

5. [Inicializar una variable](/azure/logic-apps/logic-apps-create-variables-store-values#initialize-variable) para almacenar el estado de ejecución de la solicitud **ExportToPackage**.

    ![Acción Inicializar variable.](media/integration-logic-app-initialize-variable-step.png)

6. Espere hasta que el estado de ejecución de la exportación de datos sea **Correcto**.

    1. Agregar un [bucle Until](/azure/logic-apps/logic-apps-control-flow-loops#until-loop) que se repite hasta que el valor de la variable **ExecutionStatus** sea **Correcto**.
    2. Agregue una acción **Retrasar** que espere cinco segundos antes de sondear el estado de ejecución actual de la exportación.

        ![Contenedor de bucle Until.](media/integration-logic-app-until-loop-step.png)

        > [!NOTE]
        > Establezca el recuento límite en **15** para esperar un máximo de 75 segundos (15 iteraciones × 5 segundos) a que se complete la exportación. Si su exportación lleva más tiempo, ajuste el recuento de límites según corresponda.        

    3. Agregue una acción **Invocar solicitud HTTP** para llamar a la API REST DMF [GetExecutionSummaryStatus](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus) y establezca la variable **ExecutionStatus** en el resultado de la respuesta **GetExecutionSummaryStatus**.

        > Este ejemplo no realiza la comprobación de errores. La API **GetExecutionSummaryStatus** puede devolver estados terminales no exitosos (es decir, estados distintos de **Correcto**). Para obtener más información, consulte la [documentación de la API](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexecutionsummarystatus).

        - **Método:** POST
        - **Url de la solicitud:** https://\<hostname\>/espacios de nombres/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExecutionSummaryStatus
        - **Cuerpo de la solicitud:** body('Invocar\_una\_solicitud\_HTTP')?['valor']

            > [!NOTE]
            > Puede que tenga que introducir el valor de **Cuerpo de la solicitud** en la vista de código o en el editor de funciones del diseñador.

        ![Acción Invocar una solicitud HTTP 2.](media/integration-logic-app-get-execution-status-step.png)

        ![Acción Establecer variable.](media/integration-logic-app-set-variable-step.png)

        > [!IMPORTANT]
        > El valor para la acción **Establecer variable** (**body('Invocar\_una\_solicitud\_HTTP\_2')?['valor']**) diferirá del valor del cuerpo de **Invocar una solicitud HTTP 2**, aunque el diseñador mostrará los valores de la misma manera.

7. Obtenga la URL de descarga del paquete exportado.

    - Agregue una acción **Invocar solicitud HTTP** para llamar a la API REST DMF [GetExportedPackageUrl](../fin-ops-core/dev-itpro/data-entities/data-management-api.md#getexportedpackageurl).

        - **Método:** POST
        - **URL de la solicitud:** https://\<hostname\>/namespaces/\<namespace\_guid\>/data/DataManagementDefinitionGroups/Microsoft.Dynamics.DataEntities.GetExportedPackageUrl
        - **Cuerpo de la solicitud:** {"executionId": body('GetExportedPackageURL')?['valor']}

        ![Acción GetExportedPackageURL.](media/integration-logic-app-get-exported-package-step.png)

8. Descargue el paquete exportado.

    - Agregue una solicitud HTTP **GET** (una [acción del conector HTTP](/azure/connectors/connectors-native-http) incorporada) para descargar el paquete desde la URL que se devolvió en el paso anterior.

        - **Método:** GET
        - **URI:** body('Invocar\_una\_solicitud\_HTTP\_3').valor

            > [!NOTE]
            > Puede que tenga que introducir el valor de **URI** en la vista de código o en el editor de funciones del diseñador.

        ![Acción HTTP GET.](media/integration-logic-app-download-file-step.png)

        > [!NOTE]
        > Esta solicitud no requiere ninguna autenticación adicional, porque la URL que devuelve la API **GetExportedPackageUrl** incluye un token de firmas de acceso compartido que otorga acceso para descargar el archivo.

9. Guarde el paquete descargado utilizando el conector de [OneDrive for Business](/azure/connectors/connectors-create-api-onedriveforbusiness).

    - Agregue una acción [Crear archivo](/connectors/onedriveforbusinessconnector/#create-file) en OneDrive for Business.
    - Conéctese a su cuenta de OneDrive for Business según sea necesario.

        - **Ruta de la carpeta:** una carpeta de su elección
        - **Nombre del archivo:** worker\_package.zip
        - **Contenido del archivo**: el cuerpo del paso anterior (contenido dinámico)

        ![Acción Crear archivo.](media/integration-logic-app-create-file-step.png)

### <a name="step-3-test-the-logic-app"></a>Paso 3: probar la aplicación lógica

Para probar la aplicación lógica, seleccione el botón **Ejecutar** en el diseñador. Verá que los pasos de la aplicación lógica comienzan a ejecutarse. Después de 30 a 40 segundos, la aplicación lógica debería terminar de ejecutarse y la carpeta de OneDrive for Business debe incluir un nuevo archivo de paquete que contenga los trabajadores exportados.

Si se informa una falla para cualquier paso, seleccione el paso fallido en el diseñador y examine los campos **Entradas** y **Salidas** para ello. Depure y ajuste el paso según sea necesario para corregir los errores.

La siguiente ilustración muestra cómo se ve el Logic Apps Designer cuando todos los pasos de la aplicación lógica se ejecutan correctamente.

![Ejecución exitosa de la aplicación lógica.](media/integration-logic-app-successful-run.png)

## <a name="summary"></a>Resumen

En este tutorial, aprendió a usar una aplicación lógica para exportar datos de Human Resources y guardar los datos exportados en una carpeta de OneDrive for Business. Puede modificar los pasos de este tutorial según sea necesario para satisfacer las necesidades de su negocio.




[!INCLUDE[footer-include](../includes/footer-banner.md)]
