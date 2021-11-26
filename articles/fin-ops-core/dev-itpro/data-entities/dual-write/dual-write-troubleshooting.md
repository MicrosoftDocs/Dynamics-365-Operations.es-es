---
title: Solución de problemas generales
description: Este tema proporciona información general para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Dataverse.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: bcedb9f6e8fb15210512ed6a376d4329759593e4
ms.sourcegitcommit: 9acfb9ddba9582751f53501b82a7e9e60702a613
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2021
ms.locfileid: "7781183"
---
# <a name="general-troubleshooting"></a>Solución de problemas generales

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tema proporciona información general para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Dataverse.

> [!IMPORTANT]
> Algunos de los problemas que aborda este tema pueden requerir la función de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos. La sección para cada problema explica si se requiere una característica o credenciales específicas.

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

**Rol requerido para ver los errores:** Administrador del sistema

Los errores de doble escritura que se originan en Dataverse puede aparecer en la aplicación Finance and Operations. Para habilitar el registro detallado de errores, siga estos pasos:

1. Para todas las configuraciones de proyecto en la aplicación de Finance and Operations hay un indicador **IsDebugMode** en la tabla **DualWriteProjectConfiguration**.
2. Abra la tabla **DualWriteProjectConfiguration** mediante el complemento de Excel. Para usar el complemento, habilite el modo de diseño en el complemento de Excel de Finance and Operations y agregue **DualWriteProjectConfiguration** a la hoja. Para obtener más información, consulte [Usar Excel para ver y actualizar datos de entidades](../../office-integration/use-excel-add-in.md).
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

## <a name="how-to-enable-and-save-network-trace-so-that-traces-can-be-attached-to-support-tickets"></a>Cómo habilitar y guardar el seguimiento de la red para poder adjuntar trazas a los vales de soporte

Para solucionar algunos problemas, el equipo de soporte técnico puede tener que revisar trazas de red. Para crear una traza de red, siga estos pasos:

### <a name="chrome"></a>Chrome

1. En la pestaña abierta, presione **F12** o elija **Herramientas de desarrollo** para abrir las herramientas de desarrollo.
2. Abra la pestaña **Red** y escriba **integ** en el cuadro de texto del filtro.
3. Ejecute el escenario y observe las solicitudes que se registran.
4. Haga clic con el botón secundario en las entradas y seleccione **Guardar todo como un HAR con contenido**.

### <a name="microsoft-edge"></a>Microsoft Edge

1. En la pestaña abierta, presione **F12** o elija **Herramientas de desarrollo** para abrir las herramientas de desarrollo.
2. Abra la pestaña **Red**.
3. Ejecute el escenario.
4. Seleccione **Guardar** para exportar los resultados como HAR.

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
