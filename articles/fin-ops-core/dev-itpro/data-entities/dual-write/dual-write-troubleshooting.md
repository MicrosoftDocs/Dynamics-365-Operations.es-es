---
title: Solución de problemas generales
description: Este tema proporciona información general para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: b4de461d26fc6d5c39c1ac0c49201f265f562f5a
ms.sourcegitcommit: f65bde9ab0bf4c12a3250e7c9b2abb1555cd7931
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/13/2021
ms.locfileid: "6542500"
---
# <a name="general-troubleshooting"></a>Solución de problemas generales

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Este tema proporciona información general para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Dataverse.

> [!IMPORTANT]
> Algunos de los problemas que aborda este tema pueden requerir la función de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos. La sección para cada problema explica si se requiere una función o credenciales específicas.

## <a name="when-you-try-to-install-the-dual-write-package-by-using-the-package-deployer-tool-no-available-solutions-are-shown"></a>Cuando intenta instalar el paquete de escritura doble utilizando la herramienta Package Deployer, no se muestran soluciones disponibles

Algunas versiones de la herramienta Package Deployer son incompatibles con el paquete de solución de doble escritura. Para instalar con éxito el paquete, asegúrese de usar la [versión 9.1.0.20](https://www.nuget.org/packages/Microsoft.CrmSdk.XrmTooling.PackageDeployment.Wpf/9.1.0.20) o posterior de la herramienta Package Deployer.

Después de instalar la herramienta Package Deployer, instale el paquete de la solución siguiendo estos pasos.

1. Descargue el archivo del paquete de solución más reciente de Yammer.com. Después de descargar el archivo zip del paquete, haga clic con el botón derecho y seleccione **Propiedades**. Selecciona la casilla **Desbloquear** y luego elija **Aplicar**. Si no ve la casilla de verificación **Desbloquear**, el archivo zip ya está desbloqueado y puede omitir este paso.

    ![Cuadro de diálogo Propiedades.](media/unblock_option.png)

2. Extraiga el archivo zip del paquete y copie todos los archivos en la carpeta **Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438**.

    ![Contenido de la carpeta Dynamics365FinanceAndOperationsCommon.PackageDeployer.2.0.438.](media/extract_package.png)

3. Pegue todos los archivos copiados en la carpeta **Herramientas** de la herramienta Package Deployer. 
4. Ejecute **PackageDeployer.exe** para seleccionar el entorno Dataverse e instalar las soluciones.

    ![Contenido de la carpeta Herramientas.](media/paste_copied_files.png)

## <a name="enable-and-view-the-plug-in-trace-log-in-dataverse-to-view-error-details"></a><a id="enable-view-trace"></a>Habilite y vea el inicio de sesión de seguimiento del complemento Dataverse para ver detalles del error

**Rol requerido para activar el registro de seguimiento y ver los errores:** Administrador del sistema

Para activar el registro de seguimiento, siga estos pasos.

1. Inicie sesión en la aplicación Customer Engagement, abra la página **Configuración**, y luego, en **Sistema**, seleccione **Administración**.
2. En la página **Administración** , seleccione **Configuración del sistema**.
3. En la pestaña **Personalización**, en la columna **Complemento y seguimiento de actividad de flujo de trabajo personalizado**, seleccione **Todo** para habilitar el registro de seguimiento del complemento. Si desea registrar registros de rastreo solo cuando se producen excepciones, puede seleccionar **Excepción** en su lugar.


Para ver el registro de seguimiento, siga estos pasos.

1. Inicie sesión en la aplicación Customer Engagement, abra la página **Configuración**, y luego, en **Personalización**, seleccione **Registro de seguimiento de complemento**.
2. Encuentre los registros de seguimiento donde la columna **Escribir nombre** se establece en **Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PreCommmitPlugin**.
3. Haga doble clic en un elemento para ver el registro completo y luego, en la ficha desplegable **Ejecución**, revise el texto **Bloque de mensajes**.

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a>Habilite el modo de depuración para solucionar problemas de sincronización en vivo en aplicaciones Finance and Operations

**Rol requerido para ver los errores**: los errores de doble escritura del administrador del sistema que se originan en Dataverse pueden aparecer en la aplicación de Finance and Operations. En algunos casos, el texto completo del mensaje de error no está disponible porque el mensaje es demasiado largo o contiene información de identificación personal (PII). Puede activar el registro detallado de errores siguiendo estos pasos.

1. Todas las configuraciones del proyecto en las aplicaciones Finance and Operations tienen una propiedad **IsDebugMode** en la tabla **DualWriteProjectConfiguration**. Abra la tabla **DualWriteProjectConfiguration** usando el complemento de Excel.

    > [!TIP]
    > Una manera fácil de abrir la tabla es activar el modo **Diseño** en el complemento de Excel y luego agregar **DualWriteProjectConfigurationEntity** a la hoja de trabajo. Para más información consulte [Abrir los datos de tabla en Excel y actualizarlos mediante el complemento de Excel](../../office-integration/use-excel-add-in.md).

2. Estableza la propiedad **IsDebugMode** a **Sí** para el proyecto.
3. Ejecute el escenario que genera errores.
4. Los registros detallados están disponibles en la tabla DualWriteErrorLog. Para buscar datos en el navegador de tablas, use la siguiente URL (reemplace **XXX** según sea apropiado):

    `https://XXXaos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a>Verifique los errores de sincronización en la máquina virtual para la aplicación Finance and Operations

**Rol requerido para ver los errores**: Administrador del sistema

1. Inicie sesión en Microsoft Dynamics LifeCycle Services (LCS).
2. Abra el proyecto LCS que seleccionó para realizar la prueba de escritura dual.
3. Seleccione el mosaico **Entornos hospedados en la nube**.
4. Use Escritorio remoto para iniciar sesión en la máquina virtual (VM) para la aplicación Finance and Operations. Use la cuenta local que se muestra en LCS.
5. Abra el visor de eventos.
6. Seleccione **Registros de aplicaciones y servicios \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operacional**.
7. Revise la lista de errores recientes.

## <a name="unlink-and-link-another-dataverse-environment-from-a-finance-and-operations-app"></a>Desvincular y vincular a otro entorno de Dataverse de una aplicación Finance and Operations

**Rol requerido para desvincular el entorno**: Administrador del sistema para cualquier aplicación de Finance and Operations o Dataverse.

1. Iniciar sesión en la aplicación Finance and Operations.
2. Vaya a **Espacios de trabajo \> Gestión de datos** y seleccione el mosaico **Doble escritura**.
3. Seleccione todas las asignaciones en funcionamiento y seleccione **Detener**.
4. Seleccione **Desvincular entorno**.
5. Seleccione **Sí** para confirmar la operación.

Ahora puede vincular un nuevo entorno.

## <a name="unable-to-view-the-sales-order-line-information-form"></a>No se puede ver el formulario de información de línea para el pedido de ventas 

Cuando crea un pedido de ventas en Dynamics 365 Sales, al hacer clic en **+ Agregar productos** podría redirigírsele al formulario de línea de pedido de Dynamics 365 Project Operations. No hay forma desde ese formulario de ver el formulario de **Información** de la línea de pedido de ventas. La opción para **Información** no aparece en el menú desplegable bajo **Nueva línea de pedido**. Esto sucede porque Project Operations se ha instalado en su entorno.

Para volver a habilitar la opción de formulario **Información**, siga estos pasos:
1. Navegue hasta la tabla **Línea de pedido**.
2. Busque el formulario **Información** bajo el nodo de formularios. 
3. Seleccione el formulario **Información** y haga clic en **Habilitar roles de seguridad**. 
4. Cambie la configuración de seguridad a **Mostrar para todos**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]