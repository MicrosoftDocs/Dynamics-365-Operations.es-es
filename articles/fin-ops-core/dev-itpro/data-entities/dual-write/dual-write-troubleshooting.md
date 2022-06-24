---
title: Solución de problemas generales
description: Este artículo proporciona información general para solución de problemas de integración de escritura doble entre las aplicaciones de finanzas y operaciones y Dataverse.
author: RamaKrishnamoorthy
ms.date: 04/18/2022
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 620f6f999859eff0ccd8aeb1cff12ddd56fa9926
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8853666"
---
# <a name="general-troubleshooting"></a>Solución de problemas generales

[!include [banner](../../includes/banner.md)]



Este artículo proporciona información general para solución de problemas de integración de escritura doble entre las aplicaciones de finanzas y operaciones y Dataverse.

> [!IMPORTANT]
> Algunos de los problemas que aborda este artículo pueden requerir la característica de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos. La sección para cada problema explica si se requiere una característica o credenciales específicas.

## <a name="enable-and-view-the-plug-in-trace-log-in-dataverse-to-view-error-details"></a><a id="enable-view-trace"></a>Habilite y vea el inicio de sesión de seguimiento del complemento Dataverse para ver detalles del error

Los registros de seguimiento pueden ser útiles para solucionar problemas de sincronización en vivo de doble escritura entre Finance + Operations y Dataverse. Los registros pueden proporcionar detalles específicos a los equipos que brindan soporte técnico y de ingeniería para Dynamics 365. Este artículo cubre cómo habilitar los registros de seguimiento y cómo verlos. Los registros de seguimiento se administran en la página Configuración de Dynamics 365 y requieren privilegios de nivel de administrador para cambiarlos y verlos. 

**Rol requerido para activar el registro de seguimiento y ver los errores:** Administrador del sistema

### <a name="turn-on-the-trace-log"></a>Activar el registro de seguimiento
Para activar el registro de seguimiento, siga estos pasos.

1.  En la barra de navegación superior, inicie sesión en Dynamics 365 y luego seleccione **Configuración**. En la página Sistemas, haga clic en **Administración**.
2.  En la página Administración , haga clic en **Configuración del sistema**.
3.  Seleccione la pestaña **Personalización** y el complemento, y luego, en la sección Seguimiento de actividad de flujo de trabajo personalizado, cambie el desplegable a **Todo**. Esto rastreará todas las actividades y proporciona un conjunto completo de datos para los equipos que deben revisar los posibles problemas.

> [!NOTE]
> Configurar el menú desplegable en **Excepción** solo proporcionará información de seguimiento cuando se produzcan excepciones (errores).

Una vez habilitados, los registros de seguimiento del complemento se seguirán recopilando hasta que se desactiven manualmente regresando a esta ubicación y seleccionando **Desactivado**.

### <a name="view-the-trace-log"></a>Ver el archivo de seguimiento
Para ver el registro de seguimiento, siga estos pasos.

1. En la página Configuración de Dynamics 365, seleccione **Configuración** en la barra de navegación superior. 
2. Seleccione **Registro de seguimiento de complementos** en la sección **Personalizaciones** de la página.
3. Puede encontrar entradas en la lista de registros de seguimiento, en función del nombre del tipo y/o el nombre del mensaje.
4. Abra la entrada deseada para ver el registro completo. El bloque de mensajes en la sección Ejecución proporcionará información disponible para el complemento. Si está disponible, también se proporcionarán los detalles de la excepción. 

Puede copiar el contenido de los registros de seguimiento y pegarlos en otra aplicación, como el Bloc de notas, u otras herramientas para ver registros o archivos de texto, para ver todo el contenido más fácilmente. 

## <a name="enable-debug-mode-to-troubleshoot-live-synchronization-issues-in-finance-and-operations-apps"></a>Habilite el modo de depuración para solucionar problemas de sincronización en vivo en aplicaciones Finance and Operations

**Rol requerido para ver los errores:** Administrador del sistema

Los errores de doble escritura que se originan en Dataverse puede aparecer en la aplicación de Finanzas y operaciones. Para habilitar el registro detallado de errores, siga estos pasos:

1. Para todas las configuraciones del proyecto en las aplicaciones de Finanzas y operaciones tienen una propiedad **IsDebugMode** en la tabla **DualWriteProjectConfiguration**.
2. Abra la tabla **DualWriteProjectConfiguration** mediante el complemento de Excel. Para usar el complemento, habilite el modo de diseño en el complemento de Excel de Finanzas y operaciones, y agregue **DualWriteProjectConfiguration** a la hoja. Para obtener más información, consulte [Usar Excel para ver y actualizar datos de entidades](../../office-integration/use-excel-add-in.md).
3. Establezca **IsDebugMode** en **Sí** para el proyecto.
4. Ejecute el escenario que genera errores.
5. Los registros detallados se almacenan en la tabla **DualWriteErrorLog**.
6. Para buscar datos en el explorador de tablas, use el siguiente vínculo: `https://999aos.cloudax.dynamics.com/?mi=SysTableBrowser&tableName=DualWriteErrorLog`, reemplazando `999` según sea necesario.
7. Actualice de nuevo después de [KB 4595434](https://fix.lcs.dynamics.com/Issue/Details?kb=4595434&bugId=527820&dbType=3&qc=98e5dc124ac125c57ad633d885ac612aea3ddb8f4abf9d71ab3aa354f2e06cbe), que está disponible para las actualizaciones de plataforma 37 y posteriores. Si tiene esta solución instalada, el modo de depuración capturará más registros.  

## <a name="check-synchronization-errors-on-the-virtual-machine-for-the-finance-and-operations-app"></a>Verifique los errores de sincronización en la máquina virtual para la aplicación Finance and Operations

**Rol requerido para ver los errores**: Administrador del sistema

1. Inicie sesión en Microsoft Dynamics LifeCycle Services (LCS).
2. Abra el proyecto LCS que seleccionó para realizar la prueba de escritura dual.
3. Seleccione el mosaico **Entornos hospedados en la nube**.
4. Use Escritorio remoto para iniciar sesión en la máquina virtual (VM) para la aplicación Finance and Operations. Use la cuenta local que se muestra en LCS.
5. Abra el visor de eventos.
6. Seleccione **Registros de aplicaciones y servicios \> Microsoft \> Dynamics \> AX-DualWriteSync \> Operacional**.
7. Revise la lista de errores recientes.

## <a name="dual-write-ui-landing-page-showing-blank"></a>La página de inicio de la interfaz de usuario de doble escritura se muestra en blanco
Al abrir la página de doble escritura en los navegadores Microsoft Edge o Google Chrome, la página de inicio no se carga y se ve una página en blanco, o un error como "Algo salió mal".
En Devtools, aparece un error en los registros de la consola:

>bundle.eed39124e62c58ef34d2.js:37 DOMException: Failed to read the 'sessionStorage' property from 'Window': Access is denied for this document. at t.storeInSessionStorage (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:16:136860 ) at new t (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:69:20103 ) at ci (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:44115 ) at Eo (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:58728 ) at jo (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:65191 ) at Nr (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:84692 ) at Or (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:85076 ) at Ss (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:91750 ) at vs (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:91130 ) at hs (https://dataintegrator.trafficmanager.net/bundle.eed39124e62c58ef34d2.js:37:90151 )

La interfaz de usuario utiliza el 'almacenamiento de sesión' del navegador para almacenar algunos valores de propiedad para cargar la página de inicio. Para que esto funcione, las cookies de terceros deben estar permitidas en el navegador del sitio. El error indica que la interfaz de usuario no puede acceder al almacenamiento de la sesión. Puede haber dos escenarios en los que se encuentre este problema:

1.  Está abriendo la interfaz de usuario en modo de incógnito de Edge/Chrome y las cookies de terceros en modo de incógnito están bloqueadas.
2.  Ha bloqueado las cookies de terceros por completo en Edge/Chrome.

### <a name="mitigation"></a>Mitigación
Las cookies de terceros deben estar permitidas en la configuración del navegador.

### <a name="google-chrome-browser"></a>Navegador Google Chrome
1.ª opción:
1.  Vaya a la configuración introduciendo chrome://settings/ en la barra de direcciones y luego navegue hasta Privacidad y seguridad -> Cookies y otros datos del sitio.
2.  Seleccione 'Permitir todas las cookies'. Si no desea hacer esto, vaya a la segunda opción.

2.ª opción:
1.  Vaya a la configuración introduciendo chrome://settings/ en la barra de direcciones y luego navegue hasta Privacidad y seguridad -> Cookies y otros datos del sitio.
2.  Si está seleccionado 'Bloquear cookies de terceros en modo incógnito' o 'Bloquear cookies de terceros', vaya a 'Sitios que siempre pueden usar cookies' y haga clic en **Agregar**. 
3.  Agregue el nombre del sitio de las aplicaciones de Finance + Operations: https://<your_FinOp_instance>.cloudax.dynamics.com. Asegúrese de seleccionar la casilla "Todas las cookies, solo en este sitio". 

### <a name="microsoft-edge-browser"></a>Navegador Microsoft Edge
1.  Vaya a Configuración -> Permisos del sitio -> Cookies y datos del sitio.
2.  Desactive 'Bloquear cookies de terceros'.  

## <a name="unlink-and-link-another-dataverse-environment-from-a-finance-and-operations-app"></a>Desvincular y vincular otro entorno Dataverse de una aplicación de Finanzas y operaciones

**Rol requerido para desvincular el entorno**: Administrador del sistema para cualquier aplicación de Finanzas y operaciones o Dataverse.

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

## <a name="how-to-ensure-data-integration-is-using-the-most-current-finance-and-operations-schema"></a>Cómo garantizar que la integración de datos utilice el esquema de finanzas y operaciones más actual

Es posible que enfrente problemas de datos en su integración de datos si no se utiliza el esquema más actualizado. Los siguientes pasos lo ayudarán a actualizar la lista de entidades en las aplicaciones de finanzas y operaciones y las entidades en el integrador de datos.

### <a name="refresh-entity-list-in-finance-and-operations-environment"></a>Actualizar la lista de entidades en el entorno de finanzas y operaciones
1.  Inicie sesión en su entorno de finanzas y operaciones.
2.  Seleccione **Gestión de datos**.
3.  Dentro de gestión de datos, seleccione **Parámetros de marco**.
4.  En la página **Parámetros del marco de importación / exportación de datos**, seleccione la pestaña **Configuración de la entidad** y seleccione **Actualizar lista de entidades**. Esto puede tardar más de 30 minutos en actualizarse, según la cantidad de entidades involucradas.
5.  Vaya a **Gestión de datos** y seleccione **Entidades de datos** para validar que se enumeran las entidades esperadas. Si las entidades esperadas no aparecen en la lista, valide que las entidades aparezcan en su entorno de finanzas y operaciones y restaure las entidades que faltan, según sea necesario.

#### <a name="if-the-refresh-fails-to-resolve-the-issue-delete-and-re-add-the-entities"></a>Si la actualización no resuelve el problema, elimine y vuelva a agregar las entidades

> [!NOTE]
> Es posible que deba detener cualquier grupo de procesamiento que esté utilizando activamente las entidades antes de la eliminación.

1.  Seleccione **Gestión de datos** en su entorno de finanzas y operaciones y seleccione **Entidades de datos**.
2.  Busque las entidades que tengan problemas y anote la entidad de destino, la tabla de puesta en escena, el nombre de la entidad y otros parámetros. Eliminar la entidad o entidades de la lista.
3.  Seleccione **Nuevo** y vuelva a agregar la entidad o entidades utilizando los datos del paso 2. 

#### <a name="refresh-entities-in-data-integrator"></a>Actualizar entidades en el integrador de datos
Inicie sesión en el centro de administración Power Platform y seleccione **Integración de datos**. Abra el proyecto donde se producen los problemas y seleccione **Actualizar entidades**.

## <a name="how-to-enable-and-save-network-trace-so-that-traces-can-be-attached-to-support-tickets"></a>Cómo habilitar y guardar el seguimiento de la red para poder adjuntar trazas a los vales de soporte

Para solucionar algunos problemas, el equipo de soporte técnico puede tener que revisar trazas de red. Para crear una traza de red, siga estos pasos:

### <a name="google-chrome-browser"></a>Navegador Google Chrome

1. En la pestaña abierta, presione **F12** o elija **Herramientas de desarrollo** para abrir las herramientas de desarrollo.
2. Abra la pestaña **Red** y escriba **integ** en el cuadro de texto del filtro.
3. Ejecute el escenario y observe las solicitudes que se registran.
4. Haga clic con el botón secundario en las entradas y seleccione **Guardar todo como un HAR con contenido**.

### <a name="microsoft-edge-browser"></a>Navegador Microsoft Edge

1. En la pestaña abierta, presione **F12** o elija **Herramientas de desarrollo** para abrir las herramientas de desarrollo.
2. Abra la pestaña **Red**.
3. Ejecute el escenario.
4. Seleccione **Guardar** para exportar los resultados como HAR.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
