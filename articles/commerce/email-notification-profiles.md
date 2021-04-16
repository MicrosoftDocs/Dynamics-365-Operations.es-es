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
ms.openlocfilehash: 7504b2b36f6869f90de196bf32c09e7bdd51e7b5
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792666"
---
# <a name="set-up-an-email-notification-profile"></a><span data-ttu-id="87e5a-103">Configurar perfil de notificación por correo electrónico</span><span class="sxs-lookup"><span data-stu-id="87e5a-103">Set up an email notification profile</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="87e5a-104">Este tema describe cómo crear un perfil de notificación por correo electrónico en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="87e5a-104">This topic describes how to create an email notification profile in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="87e5a-105">Cuando crea canales, puede configurar un perfil de notificación por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="87e5a-105">When you create channels, you can set up an email notification profile.</span></span> <span data-ttu-id="87e5a-106">De esa manera, se pueden enviar correos electrónicos a los clientes para varios eventos transaccionales, como creación de pedidos, estado de envío de pedidos y fallos de pago.</span><span class="sxs-lookup"><span data-stu-id="87e5a-106">In that way, emails can be sent to customers for various transactional events, such as order creation, order shipping status, and payment failure.</span></span>

<span data-ttu-id="87e5a-107">Para obtener más información sobre cómo configurar el correo electrónico, consulte [Configurar y enviar correo electrónico](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="87e5a-107">For additional email configuration information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>

## <a name="create-an-email-notification-profile"></a><span data-ttu-id="87e5a-108">Crear un perfil de notificación por correo electrónico</span><span class="sxs-lookup"><span data-stu-id="87e5a-108">Create an email notification profile</span></span>

<span data-ttu-id="87e5a-109">Para crear un perfil de notificación por correo electrónico, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="87e5a-109">To create an email notification profile, follow these steps.</span></span>

1. <span data-ttu-id="87e5a-110">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de sede central \> Perfil de notificación por correo electrónico de Commerce**.</span><span class="sxs-lookup"><span data-stu-id="87e5a-110">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="87e5a-111">En el panel de acciones, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="87e5a-111">On the action pane, click **New**.</span></span>
1. <span data-ttu-id="87e5a-112">En el campo **Perfil de notificación por correo electrónico**, ingrese un nombre para identificar el perfil.</span><span class="sxs-lookup"><span data-stu-id="87e5a-112">In the **Email notification profile** field, enter a name to identify the profile.</span></span>
1. <span data-ttu-id="87e5a-113">En el campo **Descripción**, escriba una descripción pertinente.</span><span class="sxs-lookup"><span data-stu-id="87e5a-113">In the **Description** field, enter a relevant description.</span></span>
1. <span data-ttu-id="87e5a-114">Establezca el conmutador **Activo** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="87e5a-114">Set the **Active** switch to **Yes**.</span></span>

### <a name="create-an-email-template"></a><span data-ttu-id="87e5a-115">Crear una plantilla de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="87e5a-115">Create an email template</span></span>

<span data-ttu-id="87e5a-116">Antes de que se pueda habilitar un tipo de notificación por correo electrónico, debe crear una plantilla de correo electrónico de la organización en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="87e5a-116">Before an email notification type can be enabled, you must create an organization email template in Commerce headquarters.</span></span> <span data-ttu-id="87e5a-117">Esta plantilla define el asunto del correo electrónico, el remitente, el idioma predeterminado y el cuerpo del correo electrónico para cada idioma que desea admitir.</span><span class="sxs-lookup"><span data-stu-id="87e5a-117">This template defines the email subject, sender, default language, and email body for each language that you want to support.</span></span>

<span data-ttu-id="87e5a-118">Para crear una plantilla de correo electrónico, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="87e5a-118">To create an email template, follow these steps.</span></span>

1. <span data-ttu-id="87e5a-119">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de sede central \> Parámetros \> Plantillas de correo electrónico de organización**.</span><span class="sxs-lookup"><span data-stu-id="87e5a-119">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Parameters \> Organization email templates**.</span></span>
1. <span data-ttu-id="87e5a-120">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="87e5a-120">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="87e5a-121">En el campo **Identificación de correo**, introduzca un id. para ayudar a identificar esta plantilla.</span><span class="sxs-lookup"><span data-stu-id="87e5a-121">In the **Email ID** field, enter an ID to help identify this template.</span></span>
1. <span data-ttu-id="87e5a-122">En el campo **Nombre del remitente**, introduzca el nombre del remitente.</span><span class="sxs-lookup"><span data-stu-id="87e5a-122">In the **Sends name** field, enter the senders name.</span></span>
1. <span data-ttu-id="87e5a-123">En el campo **Descripción de correo electrónico**, escriba una descripción comprensible.</span><span class="sxs-lookup"><span data-stu-id="87e5a-123">In the **Email Description**, enter a meaningful description.</span></span>
1. <span data-ttu-id="87e5a-124">A continuación, en el campo **Correo electrónico del remitente**, escriba la dirección de correo electrónico del remitente.</span><span class="sxs-lookup"><span data-stu-id="87e5a-124">In the **Sender email**, enter the senders email address.</span></span>
1. <span data-ttu-id="87e5a-125">En la sección **General**, seleccione un idioma predeterminado para la plantilla de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="87e5a-125">In the **General** section, select a default language for the email template.</span></span> <span data-ttu-id="87e5a-126">El idioma predeterminado se utilizará cuando no exista una plantilla localizada para el idioma especificado.</span><span class="sxs-lookup"><span data-stu-id="87e5a-126">The default language will be used when no localized template exists for the specified language.</span></span>
1. <span data-ttu-id="87e5a-127">Amplíe la sección **Contenido del mensaje de correo electrónico** y seleccione **Nuevo** para crear el contenido de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="87e5a-127">Expand the **Email message content** section and select **New** to create the template content.</span></span> <span data-ttu-id="87e5a-128">Para cada elemento de contenido, seleccione el idioma y proporcione el asunto del correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="87e5a-128">For each content item, select the language and provide the email subject line.</span></span> <span data-ttu-id="87e5a-129">Si el correo electrónico va a tener un cuerpo, asegúrese de que la casilla **Tiene cuerpo** está marcada.</span><span class="sxs-lookup"><span data-stu-id="87e5a-129">If the email will have a body, ensure that the **Has body** box is checked.</span></span>
1. <span data-ttu-id="87e5a-130">En el panel de acciones, seleccione **Mensaje de correo electrónico** para proporcionar una plantilla de cuerpo de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="87e5a-130">On the action pane, select **Email message** to provide an email body template.</span></span>

<span data-ttu-id="87e5a-131">La siguiente imagen muestra algunos ejemplos de configuración de plantillas de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="87e5a-131">The following image shows some example email template settings.</span></span>

![Configuración de plantilla de correo electrónico](media/email-template.png)

### <a name="create-an-email-event"></a><span data-ttu-id="87e5a-133">Crear un evento de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="87e5a-133">Create an email event</span></span>

<span data-ttu-id="87e5a-134">Para crear un evento de correo electrónico, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="87e5a-134">To create an email event, follow these steps.</span></span>

1. <span data-ttu-id="87e5a-135">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de sede central \> Perfil de notificación por correo electrónico de Commerce**.</span><span class="sxs-lookup"><span data-stu-id="87e5a-135">In the navigation pane, go to **Modules \> Retail and commerce \> Headquarters setup \> Commerce email notification profile**.</span></span>
1. <span data-ttu-id="87e5a-136">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="87e5a-136">In the list, find and select the desired record.</span></span> 
1. <span data-ttu-id="87e5a-137">Seleccione la plantilla de correo electrónico en la lista desplegable **Id. de correo**.</span><span class="sxs-lookup"><span data-stu-id="87e5a-137">Select the email template from the **Email ID** drop-down list.</span></span>
1. <span data-ttu-id="87e5a-138">Seleccione el **tipo de notificación de correo electrónico** apropiado en la lista desplegable.</span><span class="sxs-lookup"><span data-stu-id="87e5a-138">Select the appropriate **Email notification type** from the drop-down list.</span></span>
1. <span data-ttu-id="87e5a-139">Active la casilla **Activo**.</span><span class="sxs-lookup"><span data-stu-id="87e5a-139">Select the **Active** check box.</span></span>
1. <span data-ttu-id="87e5a-140">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="87e5a-140">On the action pane, select **Save**.</span></span>

<span data-ttu-id="87e5a-141">La siguiente imagen muestra algunos ejemplos de configuración de notificaciones de eventos.</span><span class="sxs-lookup"><span data-stu-id="87e5a-141">The following image shows some example event notification settings.</span></span>

![Configuración de notificación de evento](media/email-notification-profile.png)

### <a name="next-steps"></a><span data-ttu-id="87e5a-143">Pasos siguientes</span><span class="sxs-lookup"><span data-stu-id="87e5a-143">Next steps</span></span>

<span data-ttu-id="87e5a-144">Antes de poder enviar correos, debe configurar su servicio de correo saliente y configurar un trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="87e5a-144">Before you can send mails, you must configure your outgoing mail service and set up a batch job.</span></span> <span data-ttu-id="87e5a-145">Para obtener más información, consulte [Configurar y enviar correo electrónico](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="87e5a-145">For more information, see [Configure and send email](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json).</span></span>


## <a name="additional-resources"></a><span data-ttu-id="87e5a-146">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="87e5a-146">Additional resources</span></span>

[<span data-ttu-id="87e5a-147">Configurar y enviar correo electrónico</span><span class="sxs-lookup"><span data-stu-id="87e5a-147">Configure and send email</span></span>](../fin-ops-core/fin-ops/organization-administration/configure-email.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="87e5a-148">Visión general de canales</span><span class="sxs-lookup"><span data-stu-id="87e5a-148">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="87e5a-149">Requisitos previos de configuración de canales</span><span class="sxs-lookup"><span data-stu-id="87e5a-149">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="87e5a-150">Visión general de las organizaciones y las jerarquías organizativas</span><span class="sxs-lookup"><span data-stu-id="87e5a-150">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
