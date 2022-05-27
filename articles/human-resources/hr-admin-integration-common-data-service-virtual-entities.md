---
title: Configurar tablas virtuales de Dataverse
description: En este tema se muestra cómo configurar, generar, actualizar tablas virtuales existentes y analizar tablas generadas y disponibles para Dynamics 365 Human Resources.
author: twheeloc
ms.date: 08/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: d7f4d3770c754d2a7974d17fc7c40462ac8fc642
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8691425"
---
# <a name="configure-dataverse-virtual-tables"></a>Configurar tablas virtuales de Dataverse


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Dynamics 365 Human Resources es una fuente de datos virtual en Microsoft Dataverse. Proporciona operaciones completas de creación, lectura, actualización y eliminación (CRUD) de Dataverse y Microsoft Power Platform. Los datos de las tablas virtuales no se almacenan en Dataverse, sino en la base de datos de la aplicación.

Para habilitar las operaciones CRUD en entidades de Human Resources desde Dataverse, debe hacer que las entidades estén disponibles como tablas virtuales en Dataverse. Esto le permite realizar operaciones CRUD desde Dataverse y Microsoft Power Platform en datos que se encuentran en Human Resources. Las operaciones también respaldan las validaciones de la lógica empresarial completa de Human Resources para garantizar la integridad de los datos al escribir datos en las entidades.

> [!NOTE]
> Las entidades de Human Resources se corresponden con tablas de Dataverse. Para obtener más información sobre Dataverse (antes denominado Common Data Service) y actualizaciones de terminología, consulte [¿Qué es Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)

## <a name="available-virtual-tables-for-human-resources"></a>Tablas virtuales disponibles para Human Resources

Todas las entidades de Protocolo de datos abiertos (OData) de Human Resources están disponibles como tablas virtuales en Dataverse. También están disponibles en Power Platform. Ahora puede crear aplicaciones y experiencias con datos directamente de Human Resources con capacidad CRUD completa, sin copiar ni sincronizar datos en Dataverse. Puede usar los portales de Power Apps para construir sitios web externos que habiliten escenarios de colaboración para procesos comerciales en Human Resources.

Puede ver la lista de tablas virtuales habilitadas en el entorno y comenzar a trabajar con las tablas en [Power Apps](https://make.powerapps.com), en la solución **Tablas virtuales de Dynamics 365 HR**.

![Tablas virtuales de Dynamics 365 HR en Power Apps.](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a>Tablas virtuales versus tablas nativas

Las tablas virtuales de Human Resources no son lo mismo que las tablas de Dataverse nativas creadas para Human Resources. 

Las tablas nativas para Human Resources se generan por separado y se mantienen en la solución HCM Common en Dataverse. Con tablas nativas, los datos se almacenan en Dataverse y esto requiere la sincronización con la base de datos de la aplicación Human Resources.

> [!NOTE]
> Para obtener una lista de las tablas de Dataverse nativas para Human Resources, vea [Tablas de Dataverse](./hr-developer-entities.md).

## <a name="setup"></a>Configurar

Siga estos pasos de configuración para habilitar tablas virtuales en su entorno.

### <a name="enable-virtual-tables-in-human-resources"></a>Habilitar tablas virtuales en Human Resources

Primero, debe habilitar las tablas virtuales en el espacio de trabajo **Administración de características**.

1. En Human Resources, seleccione **Administración del sistema**.

2. Seleccione la ventana **Gestión de funciones**.

3. Seleccione **Compatibilidad con tablas virtuales para HR en Dataverse** y, a continuación, seleccione **Habilitar**.

Para obtener más información sobre cómo habilitar y deshabilitar características, consulte [Administrar características](hr-admin-manage-features.md).

### <a name="register-the-app-in-microsoft-azure"></a>Registrar la aplicación en Microsoft Azure

Debe registrar su instancia de Human Resources en Azure Portal para que la plataforma de identidad de Microsoft pueda proporcionar servicios de autenticación y autorización para la aplicación y los usuarios. Para obtener más información sobre cómo registrar aplicaciones en Azure, consulte [Inicio rápido: registre una aplicación con la plataforma de identidad de Microsoft](/azure/active-directory/develop/quickstart-register-app).

1. Abra el [portal de Microsoft Azure](https://portal.azure.com).

2. En la lista de servicios de Azure, seleccione **Registros de aplicación**.

3. Seleccione **Nuevo registro**.

4. En el campo **Nombre**, especifique un nombre descriptivo para la aplicación. Por ejemplo, **Tablas virtuales de Dynamics 365 Human Resources**.

5. En el campo **Redirigir URI**, ingrese la URL del espacio de nombres de su instancia de Human Resources.

6. Seleccione **Registrar**.

7. Cuando se completa el registro, Azure Portal muestra el panel **Visión de conjunto** del registro de la aplicación, que incluye su **ID de aplicación (cliente)**. Tome nota del **ID de aplicación (cliente)** en este momento. Debe introducir esta información al [Configurar el origen de datos de la tabla virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).

8. En el panel de navegación izquierdo, seleccione **Certificados y secretos**.

9. En la sección **Secretos del cliente** de la página, seleccione **Nuevo secreto de cliente**.

10. Proporcione una descripción, seleccione una duración y seleccione **Añadir**.

11. Registre el valor del secreto de la propiedad de la tabla **Valor**. Debe introducir esta información al [Configurar el origen de datos de la tabla virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).

    > [!IMPORTANT]
    > Asegúrese de tomar nota del valor del secreto en este momento. El secreto nunca se vuelve a mostrar después de salir de esta página.

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a>Instalar la aplicación Dynamics 365 HR Virtual Tabla

Instale la aplicación Dynamics 365 HR Virtual Tabla en su entorno de Power Apps para implementar el paquete de solución de tabla virtual para Dataverse.

1. En Human Resources, abra la página **Integración de Microsoft Dataverse**.

2. Seleccione la pestaña **Tablas virtuales**.

3. Seleccione **Instalar aplicación de tablas virtuales**.

### <a name="configure-the-virtual-table-data-source"></a>Configurar el origen de datos de la tabla virtual

El siguiente paso es configurar el origen de datos de la tabla virtual en el entorno de Power Apps.

1. Abra el [centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).

2. En la lista **Entornos**, seleccione el entorno de Power Apps asociado a su instancia de Human Resources.

3. Seleccione la **URL del entorno** la sección **Detalles** de la página.

4. En el **Centro de estado de la solución**, selecciona el icono **Búsqueda avanzada** en la parte superior derecha de la página de la aplicación.

5. En la página **Búsqueda avanzada**, en la lista desplegable **Buscar**, seleccione **Configuraciones de fuentes de datos virtuales de Finance and Operations**.

   > [!NOTE]
   > La instalación de la aplicación de tablas virtuales desde el paso de configuración anterior puede tardar unos minutos. Si las **Configuraciones de datos de origen virtuales de Finance and Operations** no están disponibles en la lista, espere un minuto y actualice la lista.

6. Seleccione **Resultados**.

7. Seleccione el registro **Fuente de datos de recursos humanos de Microsoft**.

8. Introduzca la información requerida para la configuración del origen de datos:

   - **URL de destino**: la URL del espacio de nombres de Human Resources. El formato de la URL de destino es:
     
     https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/

     Por ejemplo:
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     >Asegúrese de incluir el carácter "**/**" al final de la URL para evitar recibir un error.

     >[!NOTE]
     >La dirección URL de destino determina el entorno de Human Resources al que apuntarán las tablas virtuales para obtener datos. Si crea un entorno de espacio aislado creando una copia de su entorno de producción, actualice este valor a la URL del espacio de nombres de su nuevo entorno de espacio aislado. Esto garantiza que las tablas virtuales se conecten a los datos del entorno de espacio aislado en lugar de seguir apuntando al entorno de producción.

   - **ID de inquilino**: el ID de inquilino de Azure Active Directory (Azure AD).

   - **ID de la aplicación de AAD**: id. de aplicación (cliente) creado para la aplicación registrada en el portal de Microsoft Azure. Recibió esta información anteriormente durante el paso [Registrar la aplicación en Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).

   - **Secreto de aplicación de AAD**: secreto de aplicación creado para la aplicación registrada en el portal de Microsoft Azure. Recibió esta información anteriormente durante el paso [Registrar la aplicación en Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).

   ![Fuente de datos de HR de Microsoft.](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. Seleccione **Guardar y cerrar**.

### <a name="grant-app-permissions-in-human-resources"></a>Conceder permisos de aplicación en Human Resources

Otorgar permisos para los las dos aplicaciones de Azure AD en Human Resources:

- La aplicación creada para su inquilino en el portal de Microsoft Azure
- La aplicación Dynamics 365 HR Virtual Tabla instalada en el entorno de Power Apps 

1. En Human Resources, abra la página **Aplicaciones de Azure Active Directory**.

2. Seleccione **Nuevo** para crear un nuevo registro de aplicación.

    - En el campo **Id. de cliente**, ingrese el ID de cliente de la aplicación que registró en el portal de Microsoft Azure.
    - En el campo **Nombre**, ingrese el nombre de la aplicación que registró en el portal de Microsoft Azure.
    - En el campo **ID de usuario**, seleccione el ID de un usuario con permisos de administrador en Human Resources y el entorno de Power Apps.

3. Seleccione **Nuevo** para crear un segundo registro de aplicación:

    - **Id. de cliente**: f9be0c49-aa22-4ec6-911a-c5da515226ff
    - **Nombre**: Dynamics 365 HR Virtual Table
    - En el campo **ID de usuario**, seleccione el ID de un usuario con permisos de administrador en Human Resources y el entorno de Power Apps.

## <a name="generate-virtual-tables"></a>Generar tablas virtuales

Cuando se haya completado la configuración, puede seleccionar las tablas virtuales que desea generar y habilitar en su instancia de Dataverse.

1. En Human Resources, abra la página **Integración de Microsoft Dataverse**.

2. Seleccione la pestaña **Tablas virtuales**.

> [!NOTE]
> El botón de alternancia **Habilitar tablas virtuales** se establecerá en **Sí** automáticamente cuando se haya completado toda la configuración necesaria. Si el botón de alternancia está configurado en **No**, revise los pasos de las secciones anteriores de este documento para asegurarse de completar toda la configuración los requisitos previos.

3. Seleccione la tabla (o tablas) que desea generar en Dataverse.

4. Seleccione **Generar/actualizar**.

![Integración de Dataverse.](./media/hr-admin-integration-dataverse-integration.png)

## <a name="check-table-generation-status"></a>Comprobar el estado de generación de tablas

Las tablas virtuales se generan en Dataverse mediante un proceso asincrónico en segundo plano. Actualizaciones de la visualización del proceso en el centro de actividades. Los detalles del proceso, incluidos los registros de errores, aparecen en la página **Automatizaciones de procesos**.

1. En Recursos humanos, abra la página **Automatizaciones de procesos**.

2. Seleccione la pestaña **Procesos en segundo plano**.

3. Seleccione **Proceso en segundo plano de operación asincrónica de sondeo de tabla virtual**.

4. Seleccione **Ver los resultados más recientes**.

El panel deslizante muestra los resultados de ejecución más recientes del proceso. Puede ver el registro del proceso, que incluye los errores devueltos por Dataverse.

## <a name="see-also"></a>Consulte también

[¿Qué es Dataverse?](/powerapps/maker/common-data-service/data-platform-intro)<br>
[Tablas en Dataverse](/powerapps/maker/common-data-service/entity-overview)<br>
[Visión general de las relaciones entre tablas](/powerapps/maker/common-data-service/relationships-overview)<br>
[Crear y editar tablas virtuales que contienen datos de un origen de datos externo](/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[¿Que son los portales de Power Apps?](/powerapps/maker/portals/overview)<br>
[Descripción general de la creación de aplicaciones en Power Apps](/powerapps/maker/)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
