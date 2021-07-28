---
title: Configurar un perfil de notificación por correo electrónico
description: Este tema describe cómo crear un perfil de notificación por correo electrónico en Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 03/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: ac58ea4f1dfd8208c1c2f78e36d82d1375475413
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6349529"
---
# <a name="set-up-an-email-notification-profile"></a>Configurar perfil de notificación por correo electrónico

[!include [banner](includes/banner.md)]

Este tema describe cómo crear un perfil de notificación por correo electrónico en Microsoft Dynamics 365 Commerce.

Cuando crea canales, puede configurar un perfil de notificación por correo electrónico. De esa manera, se pueden enviar correos electrónicos a los clientes para varios eventos transaccionales, como creación de pedidos, estado de envío de pedidos y fallos de pago.

Para obtener más información sobre cómo configurar el correo electrónico, consulte [Configurar y enviar correo electrónico](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="create-an-email-notification-profile"></a>Crear un perfil de notificación por correo electrónico

Para crear un perfil de notificación por correo electrónico, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de sede central \> Perfil de notificación por correo electrónico de Commerce**.
1. En el panel de acciones, haga clic en **Nuevo**.
1. En el campo **Perfil de notificación por correo electrónico**, ingrese un nombre para identificar el perfil.
1. En el campo **Descripción**, escriba una descripción pertinente.
1. Establezca el conmutador **Activo** en **Sí**.

### <a name="create-an-email-template"></a>Crear una plantilla de correo electrónico

Antes de que se pueda habilitar un tipo de notificación por correo electrónico, debe crear una plantilla de correo electrónico de la organización en la sede de Commerce. Esta plantilla define el asunto del correo electrónico, el remitente, el idioma predeterminado y el cuerpo del correo electrónico para cada idioma que desea admitir.

Para crear una plantilla de correo electrónico, siga estos pasos:

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de sede central \> Parámetros \> Plantillas de correo electrónico de organización**.
1. En el panel de acciones, seleccione **Nueva**.
1. En el campo **Identificación de correo**, introduzca un id. para ayudar a identificar esta plantilla.
1. En el campo **Nombre del remitente**, introduzca el nombre del remitente.
1. En el campo **Descripción de correo electrónico**, escriba una descripción comprensible.
1. A continuación, en el campo **Correo electrónico del remitente**, escriba la dirección de correo electrónico del remitente.
1. En la sección **General**, seleccione un idioma predeterminado para la plantilla de correo electrónico. El idioma predeterminado se utilizará cuando no exista una plantilla localizada para el idioma especificado.
1. Amplíe la sección **Contenido del mensaje de correo electrónico** y seleccione **Nuevo** para crear el contenido de la plantilla. Para cada elemento de contenido, seleccione el idioma y proporcione el asunto del correo electrónico. Si el correo electrónico va a tener un cuerpo, asegúrese de que la casilla **Tiene cuerpo** está marcada.
1. En el panel de acciones, seleccione **Mensaje de correo electrónico** para proporcionar una plantilla de cuerpo de correo electrónico.

La siguiente imagen muestra algunos ejemplos de configuración de plantillas de correo electrónico.

![Configuración de plantilla de correo electrónico.](media/email-template.png)

### <a name="create-an-email-event"></a>Crear un evento de correo electrónico

Para crear un evento de correo electrónico, siga estos pasos:

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de sede central \> Perfil de notificación por correo electrónico de Commerce**.
1. En la lista, busque y seleccione el registro deseado. 
1. Seleccione la plantilla de correo electrónico en la lista desplegable **Id. de correo**.
1. Seleccione el **tipo de notificación de correo electrónico** apropiado en la lista desplegable.
1. Active la casilla **Activo**.
1. En el panel de acciones, seleccione **Guardar**.

La siguiente imagen muestra algunos ejemplos de configuración de notificaciones de eventos.

![Configuración de notificación de evento.](media/email-notification-profile.png)

### <a name="next-steps"></a>Pasos siguientes

Antes de poder enviar correos, debe configurar su servicio de correo saliente y configurar un trabajo por lotes. Para obtener más información, consulte [Configurar y enviar correo electrónico](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).


## <a name="additional-resources"></a>Recursos adicionales

[Configurar y enviar correo electrónico](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[Visión general de canales](channels-overview.md)

[Requisitos previos de configuración de canales](channels-prerequisites.md)

[Visión general de las organizaciones y las jerarquías organizativas](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
