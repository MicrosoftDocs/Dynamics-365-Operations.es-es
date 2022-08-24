---
title: Solucionar problemas durante la configuración inicial
description: Este artículo proporciona información que puede ayudarlo a solucionar los problemas que pueden ocurrir durante la configuración inicial de la integración de escritura doble.
author: RamaKrishnamoorthy
ms.date: 08/10/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: d33fc6f4895b53f16cc6957a3a2fc6b1abe90a2f
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9289526"
---
# <a name="troubleshoot-issues-during-initial-setup"></a>Solucionar problemas durante la configuración inicial

[!include [banner](../../includes/banner.md)]

Este artículo proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de finanzas y operaciones y Dataverse. Proporciona información específica que puede ayudarlo a solucionar los problemas que pueden ocurrir durante la configuración inicial de la integración de escritura doble.

> [!IMPORTANT]
> Algunos de los problemas que aborda este artículo pueden requerir la característica de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos. La sección para cada problema explica si se requiere una característica o credenciales específicas.

## <a name="you-cant-link-a-finance-and-operations-app-to-dataverse"></a>No puede vincular una aplicación de finanzas y operaciones a Dataverse

**Rol requerido para configurar doble escritura**: Administrador del sistema en aplicaciones de finanzas y operaciones y Dataverse.

Los errores en la página **Enlace de configuración a Dataverse** generalmente se deben a problemas de configuración o permisos incompletos. Asegúrese de que toda la compración de estado aprueba en la página **Enlace de configuración a Dataverse**, como se muestra en la siguiente ilustración. No puede vincular la escritura doble a menos que se apruebe toda la comprobación de estado.

![Comprobación de estado exitosa.](media/health_check.png)

Debe tener credenciales de administrador de inquilinos de Azure AD para vincular los entornos de finanzas y operaciones y Dataverse. Después de vincular los entornos, los usuarios pueden iniciar sesión utilizando sus credenciales de cuenta y actualizar un mapa de tabla existente.

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a>Encuentre el límite en el número de tablas jurídicas o empresas que pueden vincularse para doble escritura

Es posible que reciba el siguiente mensaje de error cuando intenta habilitar mapas:

*Error de doble escritura - Error de registro del complemento: [(No se puede obtener el mapa de particiones para el proyecto DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Error Excede el número máximo de particiones permitidas para asignar DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)], Se han producido uno o más errores.*

El límite actual cuando vincula los entornos es de aproximadamente 40 tablas legales. Este error ocurre si intenta habilitar mapas, y más de 40 tablas legales están vinculadas entre los entornos.

## <a name="connection-set-failed-while-linking-environment"></a>Error del conjunto de conexión al vincular el entorno

Al vincular el entorno de doble escritura, se produce un error de la acción con el siguiente mensaje:

*Error al guardar el conjunto de conexiones: ya se ha agregado un elemento con la misma clave.*

La doble escritura no admite varias entidades jurídicas o empresas con el mismo nombre. Por ejemplo, recibirá este mensaje de error si tiene dos empresas con el nombre "DAT" en Dataverse.

Para desbloquear el cliente, quite los registros duplicados de la tabla **cdm_company** en Dataverse. Además, si la tabla **cdm_company** tiene registros con nombre en blanco, quite o corrija esos registros.

## <a name="error-when-opening-the-dual-write-page-in-finance-and-operations-apps"></a>Error al abrir la página de doble escritura en las aplicaciones de finanzas y operaciones

Es posible que reciba el siguiente mensaje de error cuando intente vincular un entorno de Dataverse para doble escritura:

*El código de estado de respuesta no indica éxito: 404 (no encontrado).*

Este error ocurre cuando el paso de consentimiento de la aplicación no se ha completado. Puede validar si se ha proporcionado el consentimiento iniciando sesión en `portal.azure.com` con la cuenta de administrador del inquilino y comprobar si la aplicación de terceros con id. `33976c19-1db5-4c02-810e-c243db79efde` figura en la lista de aplicaciones empresariales de AAD. De lo contrario, vuelva a ejecutar el paso de consentimiento como se describe en la siguiente sección.

### <a name="providing-app-consent"></a>Proporcionar el consentimiento de la aplicación

+ Abra la siguiente dirección URL utilizando sus credenciales de administrador.

    `https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent`

+ Seleccione **Aceptar** para proporcionar el consentimiento. Está dando su consentimiento para instalar la aplicación (con `id=33976c19-1db5-4c02-810e-c243db79efde`) en su inquilino.
+ Esta aplicación es necesaria para que Dataverse se comunique con aplicaciones de finanzas y operaciones.

    ![Solucione problemas de la configuración de sincronización inicial.](media/Initial-sync-setup-troubleshooting-1.png)

> [!NOTE]
> Si esto no funciona, abra la dirección URL en el modo privado de Microsoft Edge o el modo incógnito de Chrome.

## <a name="finance-and-operations-environment-is-not-discoverable"></a>El entorno de finanzas y operaciones no se puede descubrir

Podría recibir el siguiente mensaje de error:

*El entorno de aplicaciones de finanzas y operaciones \*\*\*.cloudax.dynamics.com no es detectable.*

Hay dos cosas que pueden hacer que un problema del entorno no sea detectable:

+ El usuario utilizado para iniciar sesión no está en el mismo inquilino que la instancia de finanzas y operaciones.
+ Están alojadas en Microsoft algunas instancias de finanzas y operaciones heredadas que tenían un problema de detección. Para solucionar este problema, actualice la instancia de finanzas y operaciones. El entorno pasará a ser detectable con cualquier actualización.

## <a name="403-forbidden-error-while-connections-are-being-created"></a>Error 403 (Prohibido) mientras se crean conexiones

Como parte del proceso de vinculación de doble escritura, dos conexiones de Power Apps (también conocido como conexiones *apihub*) se crean en nombre del usuario en el entorno de Dataverse vinculado. Si el cliente no tiene una licencia para el entorno de Power Apps, la creación de las conexiones ApiHub falla y se muestra un error 403 (Prohibido). A continuación se muestra un ejemplo del mensaje de error:

> MSJ=\[No se pudo configurar el entorno de doble escritura. Detalles del error: El código de estado de respuesta no indica éxito: 403 (Prohibido). - El código de estado de respuesta no indica éxito: 403 (Prohibido).\] STACKTRACE=\[   en Microsoft.Dynamics.Integrator.ProjectManagementService.DualWrite.DualWriteConnectionSetProcessor.\<CreateDualWriteConnectionSetAsync\>d\_\_29.MoveNext() en X:\\bt\\1158727\\repo\\src\\ProjectManagementService\\DualWrite\\DualWriteConnectionSetProcessor.cs:line 297 --- Fin de traza de pila de la ubicación anterior donde se inició la excepción --- en System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw() en System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task) en Microsoft.Dynamics.Integrator.ProjectManagementService.Controllers.DualWriteEnvironmentManagementController.\<SetupDualWriteEnvironmentAsync\>d\_\_34.MoveNext() in X:\\bt\\1158727\\repo\\src\\ProjectManagementService\\Controllers\\DualWriteEnvironmentManagementController.cs:line 265\]

Este error ocurre debido a la falta de una licencia de Power Apps. Asigne una licencia apropiada (por ejemplo, Power Apps Plan de prueba 2) al usuario, de modo que el usuario tenga permiso para crear las conexiones. Para verificar la licencia, el cliente puede ir al sitio [Mi cuenta](https://portal.office.com/account/?ref=MeControl#subscriptions) para ver las licencias que están actualmente asignadas al usuario.

Para obtener más información acerca de la licencia de Power Apps, consulte los siguientes artículos:

- [Asignar licencias a usuarios](/microsoft-365/admin/manage/assign-licenses-to-users?view=o365-worldwide)
- [Comprar Power Apps para su organización](/power-platform/admin/signup-for-powerapps-admin)

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]

