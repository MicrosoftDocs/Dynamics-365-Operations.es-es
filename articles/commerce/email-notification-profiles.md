---
title: Configurar un perfil de notificación por correo electrónico
description: Este tema describe cómo crear un perfil de notificación por correo electrónico en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 9378fb200a239433f2023bb90f72840dace1c0eb
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5000833"
---
# <a name="set-up-an-email-notification-profile"></a>Configurar un perfil de notificación por correo electrónico


[!include [banner](includes/banner.md)]

Este tema describe cómo crear un perfil de notificación por correo electrónico en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Antes de crear canales, querrá configurar un perfil para asegurarse de que se puedan enviar notificaciones por correo electrónico para varios eventos, como la creación de pedidos, el estado de envío del pedido y el incumplimiento del pago.

Para obtener más información sobre cómo configurar el correo electrónico, consulte [Configurar y enviar correo electrónico](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).

## <a name="create-an-email-notification-profile"></a>Crear un perfil de notificación por correo electrónico

Para crear un perfil de notificación por correo electrónico, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de sede central \> Perfil de notificación por correo electrónico de Commerce**.
1. En el panel de acciones, haga clic en **Nuevo**.
1. En el campo **Perfil de notificación por correo electrónico**, ingrese un nombre para identificar el perfil.
1. En el campo **Descripción**, escriba una descripción pertinente.
1. Establezca el conmutador **Activo** en **Sí**.

### <a name="create-an-email-template"></a>Crear una plantilla de correo electrónico

Antes de que se pueda crear una notificación por correo electrónico, debe crear una plantilla de correo electrónico de la organización que contenga la información de correo electrónico del remitente y la plantilla de correo electrónico.

Para crear una plantilla de correo electrónico, siga estos pasos:

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de sede central \> Parámetros \> Plantillas de correo electrónico de organización**.
1. En el panel de acciones, seleccione **Nueva**.
1. En el campo **Identificación de correo**, introduzca un id. para ayudar a identificar esta plantilla.
1. En el campo **Nombre del remitente**, introduzca el nombre del remitente.
1. En el campo **Descripción de correo electrónico**, escriba una descripción comprensible.
1. A continuación, en el campo **Correo electrónico del remitente**, escriba la dirección de correo electrónico del remitente.
1. En la sección **General**, complete cualquier información opcional necesaria (como la prioridad de correo electrónico).
1. Amplíe la sección **Contenido del mensaje de correo electrónico** y seleccione **Nuevo** para crear el contenido de la plantilla. Para cada elemento de contenido, seleccione el idioma y proporcione el asunto del correo electrónico. Si el correo electrónico va a tener un cuerpo, asegúrese de que la casilla **Tiene cuerpo** está marcada.
1. En el panel de acciones, seleccione **Mensaje de correo electrónico** para proporcionar una plantilla de cuerpo de correo electrónico.

La siguiente imagen muestra algunos ejemplos de configuración de plantillas de correo electrónico.

![Configuración de plantilla de correo electrónico](media/email-template.png)

### <a name="create-an-email-event"></a>Crear un evento de correo electrónico

Para crear un evento de correo electrónico, siga estos pasos:

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de sede central \> Perfil de notificación por correo electrónico de Commerce**.
1. En la lista, busque y seleccione el registro deseado. 
1. Seleccione la plantilla de correo electrónico en la lista desplegable **Id. de correo**.
1. Seleccione el **tipo de notificación de correo electrónico** apropiado en la lista desplegable.
1. Active la casilla **Activo**.
1. En el panel de acciones, seleccione **Guardar**.

La siguiente imagen muestra algunos ejemplos de configuración de notificaciones de eventos.

![Configuración de notificación de evento](media/email-notification-profile.png)

### <a name="next-steps"></a>Pasos siguientes

Antes de poder enviar correos, debe configurar su servicio de correo saliente y configurar un trabajo por lotes. Para obtener más información, consulte [Configurar y enviar correo electrónico](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).


## <a name="additional-resources"></a>Recursos adicionales

[Configurar y enviar correo electrónico](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[Visión general de canales](channels-overview.md)

[Requisitos previos de configuración de canales](channels-prerequisites.md)

[Visión general de las organizaciones y las jerarquías organizativas](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
