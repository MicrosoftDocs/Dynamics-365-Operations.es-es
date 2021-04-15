---
title: Solucionar problemas durante la configuración inicial
description: Este tema proporciona información que puede ayudarlo a solucionar los problemas que pueden ocurrir durante la configuración inicial de la integración de escritura doble.
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
ms.openlocfilehash: 9ffb1378eccf175fbb9bd84228f91ba606125a63
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753999"
---
# <a name="troubleshoot-issues-during-initial-setup"></a>Solucionar problemas durante la configuración inicial

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Dataverse. Proporciona información específica que puede ayudarlo a solucionar los problemas que pueden ocurrir durante la configuración inicial de la integración de escritura doble.

> [!IMPORTANT]
> Algunos de los problemas que aborda este tema pueden requerir la función de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos. La sección para cada problema explica si se requiere una función o credenciales específicas.

## <a name="you-cant-link-a-finance-and-operations-app-to-dataverse"></a>No puede vincular una aplicación Finance and Operations a Dataverse

**Rol requerido para configurar doble escritura**: Administrador del sistema en aplicaciones de Finance and Operations y Dataverse.

Los errores en la página **Enlace de configuración a Dataverse** generalmente se deben a problemas de configuración o permisos incompletos. Asegúrese de que toda la compración de estado aprueba en la página **Enlace de configuración a Dataverse**, como se muestra en la siguiente ilustración. No puede vincular la escritura doble a menos que se apruebe toda la comprobación de estado.

![Comprobación de estado exitosa](media/health_check.png)

Debe tener credenciales de administrador de inquilinos de Azure AD para vincular los entornos Finance and Operations y Dataverse. Después de vincular los entornos, los usuarios pueden iniciar sesión utilizando sus credenciales de cuenta y actualizar un mapa de tabla existente.

## <a name="error-when-you-open-the-link-to-dataverse-page"></a>Error al abrir el enlace a la página Dataverse

**Credenciales requeridas para arreglar el problema:** Administrador de inquilinos Azure AD

Es posible que reciba el siguiente mensaje de error cuando abra la página **Vincular a Dataverse** en una aplicación Finance and Operations:

*El código de estado de respuesta no indica éxito: 404 (no encontrado).*

Este error ocurre cuando el paso de consentimiento no se ha completado. Para validar si se ha completado el paso de consentimiento, inicie sesión en portal.Azure.com utilizando la cuenta de administrador del inquilino de Azure AD, y vea si la aplicación de terceros que tiene la ID **33976c19-1db5-4c02-810e-c243db79efde** aparece en la lista de **Aplicaciones empresariales** de Azure AD. Si no es así, debe proporcionar el consentimiento de la aplicación.

Para proporcionar el consentimiento de la aplicación, siga estos pasos.

1. Abra la siguiente URL utilizando sus credenciales de administrador. Se le debe solicitar su consentimiento.

    <https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent>

2. Seleccione **Aceptar** para indicar que está dando su consentimiento para instalar la aplicación que tiene la ID **33976c19-1db5-4c02-810e-c243db79efde** en su inquilino.

    > [!TIP]
    > Esta aplicación es necesaria para vincular Dataverse y aplicaciones Finance and Operations. Si tiene problemas con este paso, abra su navegador en modo incógnito (en Google Chrome) o en modo InPrivate (en Microsoft Edge).

## <a name="verify-that-company-data-and-dual-write-teams-are-set-up-correctly-during-linking"></a>Verifique que los datos de la empresa y los equipos de doble escritura estén configurados correctamente durante el enlace

Para garantizar que la escritura doble funcione correctamente, las empresas que seleccione durante la configuración se crean en el entorno Dataverse. Por defecto, estas empresas son de solo lectura, y la propiedad **IsDualWriteEnable** se establece en **Verdadero**. Además, se crean el propietario y el equipo de la unidad de negocios propietaria predeterminada e incluyen el nombre de la empresa. Antes de habilitar los mapas, verifique que se haya especificado el propietario del equipo predeterminado. Para encontrar la tabla **Empresas (MDL\_Empresa)**, siga estos pasos.

1. En la aplicación basada en modelos en Dynamics 365, seleccione el filtro en la esquina superior derecha.
2. En la lista desplegable , seleccione **Compañía**.
3. Seleccione **Ejecutar** para ver los resultados.
4. Seleccione la compañía que estaba vinculada cuando configuró la escritura doble.
5. Verifique que la columna **Equipo propietario predeterminado** tiene un valor. En la siguiente ilustración, la columna **Equipo propietario predeterminado** se establece en **USMF de doble escritura**.

    ![Verificación del equipo propietario predeterminado](media/default_owning_team.png)

## <a name="find-the-limit-on-the-number-of-legal-tables-or-companies-that-can-be-linked-for-dual-write"></a>Encuentre el límite en el número de tablas jurídicas o empresas que pueden vincularse para doble escritura

Es posible que reciba el siguiente mensaje de error cuando intenta habilitar mapas:

*Error de escritura doble - Error en el registro del complemento: \[(No se puede obtener el mapa de partición para el proyecto DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Error Excede las particiones máximas permitidas para asignar DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\], Ocurrieron uno o más errores.*

El límite actual cuando vincula los entornos es de aproximadamente 40 tablas legales. Este error ocurre si intenta habilitar mapas, y más de 40 tablas legales están vinculadas entre los entornos.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]