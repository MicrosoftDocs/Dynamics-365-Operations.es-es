---
title: Configurar un perfil de notificación por correo electrónico
description: Este tema describe cómo crear un perfil de notificación por correo electrónico en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: feb28b9c801786f63282c4189d3eeb6d53ed07e1
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3003151"
---
# <a name="set-up-an-email-notification-profile"></a>Configurar un perfil de notificación por correo electrónico


[!include [banner](includes/banner.md)]

Este tema describe cómo crear un perfil de notificación por correo electrónico en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Antes de crear canales, querrá configurar un perfil para asegurarse de que se puedan enviar notificaciones por correo electrónico para varios eventos, como la creación de pedidos, el estado de envío del pedido y el incumplimiento del pago.

Para obtener más información sobre cómo configurar el correo electrónico, consulte [Configurar y enviar correo electrónico](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-email).

## <a name="create-an-email-notification-profile"></a>Crear un perfil de notificación por correo electrónico

Para crear un perfil de notificación por correo electrónico, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de sede central \> Perfil de notificación por correo electrónico de Retail**.
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

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de sede central \> Perfil de notificación por correo electrónico de Retail**.
1. En la lista, busque y seleccione el registro deseado. 
1. Seleccione la plantilla de correo electrónico en la lista desplegable **Id. de correo**.
1. Seleccione el **tipo de notificación de correo electrónico** apropiado en la lista desplegable.
1. Active la casilla **Activo**.
1. En el panel de acciones, seleccione **Guardar**.

La siguiente imagen muestra algunos ejemplos de configuración de notificaciones de eventos comerciales.

![Configuración de notificación de evento comercial](media/email-notification-profile.png)

## <a name="additional-resources"></a>Recursos adicionales

[Configurar y enviar correo electrónico](https://docs.microsoft.com/en-us/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-email)

[Resumen de canales](channels-overview.md)

[Requisitos previos de configuración de canales](channels-prerequisites.md)

[Visión general de las organizaciones y las jerarquías organizativas](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
