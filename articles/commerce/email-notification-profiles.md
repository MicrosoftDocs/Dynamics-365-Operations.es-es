---
title: Configurar perfil de notificación por correo electrónico
description: Este artículo describe cómo crear un perfil de notificación por correo electrónico en Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: db6c46d471e3b54982132df3e4819236833cf4a8
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9292145"
---
# <a name="set-up-an-email-notification-profile"></a>Configurar perfil de notificación por correo electrónico

[!include [banner](includes/banner.md)]

Este artículo describe cómo crear un perfil de notificación por correo electrónico en Microsoft Dynamics 365 Commerce.

Cuando crea canales, puede configurar un perfil de notificación por correo electrónico. El perfil de notificación por correo electrónico define los eventos de una transacción de ventas (como eventos de pedido creado, pedido empaquetado y pedido facturado) para los cuales enviará notificaciones a sus clientes. 

Para obtener más información sobre cómo configurar el correo electrónico, consulte [Configurar y enviar correo electrónico](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).



## <a name="create-an-email-template"></a>Crear una plantilla de correo electrónico

Antes de que se pueda habilitar un tipo de notificación por correo electrónico, debe crear una plantilla de correo electrónico de la organización en la sede de Commerce para cada tipo de notificación que desee admitir. Esta plantilla define el asunto del correo electrónico, el remitente, el idioma predeterminado y el cuerpo del correo electrónico para cada idioma admitido.

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

Para obtener más información sobre cómo crear plantillas de correo electrónico, consulte [Crear plantillas de correo electrónico para eventos transaccionales](email-templates-transactions.md). 

## <a name="create-an-email-notification-profile"></a>Crear un perfil de notificación por correo electrónico

Para crear un perfil de notificación por correo electrónico en la sede central, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de sede central \> Perfil de notificación por correo electrónico de Commerce**.
1. En el panel Acciones, seleccione **Nueva**.
1. En el campo **Perfil de notificación por correo electrónico**, ingrese un nombre para identificar el perfil.
1. En el campo **Descripción**, escriba una descripción pertinente.
1. Establezca el conmutador **Activo** en **Sí**.

## <a name="add-a-notification-type"></a>Añadir un tipo de notificación

Para crear un evento de correo electrónico, siga estos pasos:

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de sede central \> Perfil de notificación por correo electrónico de Commerce**.
1. Bajo **Configuración de notificaciones de correo electrónico minorista**, seleccione **Nuevo**.
1. Seleccione el **tipo de notificación de correo electrónico** apropiado en la lista desplegable.
1. Seleccione la plantilla de correo electrónico que creó arriba de la lista desplegable **Identificación de correo**.
1. Active la casilla **Activo**.
1. En el panel de acciones, seleccione **Guardar**.

La siguiente imagen muestra algunos ejemplos de configuración de notificaciones de eventos.

![Configuración de notificación de evento.](media/email-notification-profile.png)


## <a name="schedule-a-recurring-email-notification-process-job"></a>Programar un trabajo de proceso de notificación por correo electrónico recurrente

Para enviar notificaciones por correo electrónico, debe ejecutar el trabajo **Procesar notificación por correo electrónico de pedido comercial**.

Para configurar un trabajo por lotes en la sede central para enviar correos electrónicos transaccionales, siga estos pasos.

1. Vaya a **Retail y Commerce \> TI de Retail y Commerce \> Correo electrónico y notificaciones \> Enviar notificación por correo electrónico**.
1. En el cuadro de diálogo **Procesar notificación por correo electrónico de pedido comercial**, seleccione **Periodicidad**.
1. En el cuadro de diálogo **Definir periodicidad**, seleccione **Sin fecha final**.
1. En **Patrón de periodicidad**, seleccione **Minutos** y luego establezca el campo **Recuento** a **1**. Esta configuración garantizará que las notificaciones por correo electrónico se procesen lo más rápido posible.
1. Seleccione **Aceptar** para volver al cuadro de diálogo **Procesar notificación por correo electrónico de pedido comercial**.
1. Seleccione **Aceptar** para completar la configuración del trabajo.

## <a name="next-steps"></a>Pasos siguientes

Antes de poder enviar correos electrónicos, debe configurar su servicio de correo saliente. Para obtener más información, consulte [Configurar y enviar correo electrónico](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="additional-resources"></a>Recursos adicionales

[Configurar y enviar correo electrónico](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[Visión general de canales](channels-overview.md)

[Requisitos previos de configuración de canales](channels-prerequisites.md)

[Visión general de las organizaciones y las jerarquías organizativas](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
