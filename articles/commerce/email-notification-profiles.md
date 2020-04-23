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
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: c0ab56c15a37313d0a88b1174d5bcf51d391dcec
ms.sourcegitcommit: 17ffdcbf4b1801bd6ee9c9ddc18622d5d04b8a98
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2020
ms.locfileid: "3180204"
---
# <a name="set-up-an-email-notification-profile"></a><span data-ttu-id="2bd0a-103">Configurar un perfil de notificación por correo electrónico</span><span class="sxs-lookup"><span data-stu-id="2bd0a-103">Set up an email notification profile</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="2bd0a-104">Este tema describe cómo crear un perfil de notificación por correo electrónico en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-104">This topic describes how to create an email notification profile in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="2bd0a-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="2bd0a-105">Overview</span></span>

<span data-ttu-id="2bd0a-106">Antes de crear canales, querrá configurar un perfil para asegurarse de que se puedan enviar notificaciones por correo electrónico para varios eventos, como la creación de pedidos, el estado de envío del pedido y el incumplimiento del pago.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-106">Before creating channels, you'll want to set up a profile to ensure that email notifications can be sent out for various events, such as order creation, order shipping status, and payment failure.</span></span>

<span data-ttu-id="2bd0a-107">Para obtener más información sobre cómo configurar el correo electrónico, consulte [Configurar y enviar correo electrónico](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="2bd0a-107">For additional email configuration information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="create-an-email-notification-profile"></a><span data-ttu-id="2bd0a-108">Crear un perfil de notificación por correo electrónico</span><span class="sxs-lookup"><span data-stu-id="2bd0a-108">Create an email notification profile</span></span>

<span data-ttu-id="2bd0a-109">Para crear un perfil de notificación por correo electrónico, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-109">To create an email notification profile, follow these steps.</span></span>

1. <span data-ttu-id="2bd0a-110">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de sede central \> Perfil de notificación por correo electrónico de Commerce**.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-110">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="2bd0a-111">En el panel de acciones, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-111">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="2bd0a-112">En el campo **Perfil de notificación por correo electrónico**, ingrese un nombre para identificar el perfil.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-112">In the **Email notification profile** field, enter a name to identify the profile.</span></span>
1. <span data-ttu-id="2bd0a-113">En el campo **Descripción**, escriba una descripción pertinente.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-113">In the **Description** field, enter a relevant description.</span></span>
1. <span data-ttu-id="2bd0a-114">Establezca el conmutador **Activo** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-114">Set the **Active** switch to **Yes**.</span></span>

### <a name="create-an-email-template"></a><span data-ttu-id="2bd0a-115">Crear una plantilla de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="2bd0a-115">Create an email template</span></span>

<span data-ttu-id="2bd0a-116">Antes de que se pueda crear una notificación por correo electrónico, debe crear una plantilla de correo electrónico de la organización que contenga la información de correo electrónico del remitente y la plantilla de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-116">Before an email notification can be created, you must create an organization email template which contains the senders email information and the email template.</span></span>

<span data-ttu-id="2bd0a-117">Para crear una plantilla de correo electrónico, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2bd0a-117">To create an email template, follow these steps.</span></span>

1. <span data-ttu-id="2bd0a-118">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de sede central \> Parámetros \> Plantillas de correo electrónico de organización**.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-118">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="2bd0a-119">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-119">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="2bd0a-120">En el campo **Identificación de correo**, introduzca un id. para ayudar a identificar esta plantilla.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-120">In the **Email ID** field, enter an ID to help identify this template.</span></span>
1. <span data-ttu-id="2bd0a-121">En el campo **Nombre del remitente**, introduzca el nombre del remitente.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-121">In the **Sends name** field, enter the senders name.</span></span>
1. <span data-ttu-id="2bd0a-122">En el campo **Descripción de correo electrónico**, escriba una descripción comprensible.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-122">In the **Email Description**, enter a meaningful description.</span></span>
1. <span data-ttu-id="2bd0a-123">A continuación, en el campo **Correo electrónico del remitente**, escriba la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-123">In the **Sender email**, enter the senders email address.</span></span>
1. <span data-ttu-id="2bd0a-124">En la sección **General**, complete cualquier información opcional necesaria (como la prioridad de correo electrónico).</span><span class="sxs-lookup"><span data-stu-id="2bd0a-124">In the **General** section, fill out any optional information needed (such as the email priority).</span></span>
1. <span data-ttu-id="2bd0a-125">Amplíe la sección **Contenido del mensaje de correo electrónico** y seleccione **Nuevo** para crear el contenido de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-125">Expand the **Email message content** section and select **New** to create the template content.</span></span> <span data-ttu-id="2bd0a-126">Para cada elemento de contenido, seleccione el idioma y proporcione el asunto del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-126">For each content item, select the language and provide the email subject line.</span></span> <span data-ttu-id="2bd0a-127">Si el correo electrónico va a tener un cuerpo, asegúrese de que la casilla **Tiene cuerpo** está marcada.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-127">If the email will have a body, ensure that the **Has body** box is checked.</span></span>
1. <span data-ttu-id="2bd0a-128">En el panel de acciones, seleccione **Mensaje de correo electrónico** para proporcionar una plantilla de cuerpo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-128">On the action pane, select **Email message** to provide an email body template.</span></span>

<span data-ttu-id="2bd0a-129">La siguiente imagen muestra algunos ejemplos de configuración de plantillas de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-129">The following image shows some example email template settings.</span></span>

![Configuración de plantilla de correo electrónico](media/email-template.png)

### <a name="create-an-email-event"></a><span data-ttu-id="2bd0a-131">Crear un evento de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="2bd0a-131">Create an email event</span></span>

<span data-ttu-id="2bd0a-132">Para crear un evento de correo electrónico, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="2bd0a-132">To create an email event, follow these steps.</span></span>

1. <span data-ttu-id="2bd0a-133">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de sede central \> Perfil de notificación por correo electrónico de Commerce**.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-133">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="2bd0a-134">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-134">In the list, find and select the desired record.</span></span> 
1. <span data-ttu-id="2bd0a-135">Seleccione la plantilla de correo electrónico en la lista desplegable **Id. de correo**.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-135">Select the email template from the **Email ID** drop-down list.</span></span>
1. <span data-ttu-id="2bd0a-136">Seleccione el **tipo de notificación de correo electrónico** apropiado en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-136">Select the appropriate **Email notification type** from the drop-down list.</span></span>
1. <span data-ttu-id="2bd0a-137">Active la casilla **Activo**.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-137">Select the **Active** check box.</span></span>
1. <span data-ttu-id="2bd0a-138">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-138">On the action pane, select **Save**.</span></span>

<span data-ttu-id="2bd0a-139">La siguiente imagen muestra algunos ejemplos de configuración de notificaciones de eventos.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-139">The following image shows some example event notification settings.</span></span>

![Configuración de notificación de evento](media/email-notification-profile.png)

### <a name="next-steps"></a><span data-ttu-id="2bd0a-141">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="2bd0a-141">Next steps</span></span>

<span data-ttu-id="2bd0a-142">Antes de poder enviar correos, debe configurar su servicio de correo saliente y configurar un trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="2bd0a-142">Before you can send mails, you must configure your outgoing mail service and set up a batch job.</span></span> <span data-ttu-id="2bd0a-143">Para obtener más información, consulte [Configurar y enviar correo electrónico](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="2bd0a-143">For more information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>


## <a name="additional-resources"></a><span data-ttu-id="2bd0a-144">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2bd0a-144">Additional resources</span></span>

[<span data-ttu-id="2bd0a-145">Configurar y enviar correo electrónico</span><span class="sxs-lookup"><span data-stu-id="2bd0a-145">Configure and send email</span></span>](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="2bd0a-146">Visión general de canales</span><span class="sxs-lookup"><span data-stu-id="2bd0a-146">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="2bd0a-147">Requisitos previos de configuración de canales</span><span class="sxs-lookup"><span data-stu-id="2bd0a-147">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="2bd0a-148">Visión general de las organizaciones y las jerarquías organizativas</span><span class="sxs-lookup"><span data-stu-id="2bd0a-148">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
