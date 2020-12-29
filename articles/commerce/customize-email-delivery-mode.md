---
title: Personalizar correos electrónicos transaccionales por modo de entrega
description: Este tema describe cómo configurar plantillas de correo electrónico personalizadas para tipos de notificación y modos de entrega específicos en Microsoft Dynamics 365 Commerce.
author: stuharg
manager: annbe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Commerce, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: faf5fba70bf9297727464e6046806696ab725001
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594996"
---
# <a name="customize-transactional-emails-by-mode-of-delivery"></a><span data-ttu-id="49e5f-103">Personalizar correos electrónicos transaccionales por modo de entrega</span><span class="sxs-lookup"><span data-stu-id="49e5f-103">Customize transactional emails by mode of delivery</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="49e5f-104">Este tema describe cómo configurar plantillas de correo electrónico personalizadas para tipos de notificación y modos de entrega específicos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="49e5f-104">This topic describes how to set up custom email templates for specific notification types and modes of delivery in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="49e5f-105">Los correos electrónicos transaccionales ahora se pueden personalizar para una combinación de un tipo de notificación (por ejemplo, **Pedido creado**, **Pedido empaquetado** o **Pedido facturado**) y un modo de entrega (por ejemplo, durante la noche, recogida en la tienda o recogida en puntos de entrega).</span><span class="sxs-lookup"><span data-stu-id="49e5f-105">Transactional emails can now be customized for a combination of a notification type (for example, **Order created**, **Order packed**, or **Order invoiced**) and a mode of delivery (for example, overnight, in-store pickup, or curbside pickup).</span></span> <span data-ttu-id="49e5f-106">Los correos electrónicos transaccionales personalizados permiten a los minoristas proporcionar a sus clientes experiencias de cumplimiento que se adaptan al modo de entrega del pedido.</span><span class="sxs-lookup"><span data-stu-id="49e5f-106">Custom transactional emails let retailers provide their customers order with fulfillment experiences that are tailored to the order's mode of delivery.</span></span> <span data-ttu-id="49e5f-107">Por ejemplo, el evento "pedido empaquetado" se puede personalizar para que proporcione instrucciones de recolección en un punto de entrega para los clientes que eligen esa opción.</span><span class="sxs-lookup"><span data-stu-id="49e5f-107">For example, the "order packed" event can be customized so that it provides curbside pickup instructions for customers who choose curbside pickup.</span></span> <span data-ttu-id="49e5f-108">Alternativamente, puede proporcionar el transportista de envío y la información de entrega para los clientes que eligen que se envíe su pedido.</span><span class="sxs-lookup"><span data-stu-id="49e5f-108">Alternatively, it can provide shipping carrier and delivery information for customers who choose to have their order shipped.</span></span>

> [!NOTE]
> <span data-ttu-id="49e5f-109">Para utilizar la funcionalidad de correos electrónicos transaccionales personalizados, primero debe activar la característica **Personalizar correos electrónicos transaccionales por modo de entrega** yendo a **Espacios de trabajo \> Administración de características** en la sede central de Commerce.</span><span class="sxs-lookup"><span data-stu-id="49e5f-109">To use the functionality for customized transactional emails, you first must turn on the **Customize transactional email templates by mode of delivery** feature by going to **Workspaces \> Feature management** in Commerce headquarters.</span></span>

<span data-ttu-id="49e5f-110">Los correos electrónicos se pueden personalizar por modo de entrega para los siguientes tipos de notificación:</span><span class="sxs-lookup"><span data-stu-id="49e5f-110">Emails can be customized by mode of delivery for the following notification types:</span></span>

- <span data-ttu-id="49e5f-111">**Cancelación de pedido**: este tipo de notificación por correo electrónico es nueva.</span><span class="sxs-lookup"><span data-stu-id="49e5f-111">**Order cancellation** – This email notification type is new.</span></span>
- <span data-ttu-id="49e5f-112">**Pedido creado**</span><span class="sxs-lookup"><span data-stu-id="49e5f-112">**Order created**</span></span>
- <span data-ttu-id="49e5f-113">**Pedido confirmado**</span><span class="sxs-lookup"><span data-stu-id="49e5f-113">**Order confirmed**</span></span>
- <span data-ttu-id="49e5f-114">**Pedido facturado**: este tipo de notificación por correo electrónico es nueva.</span><span class="sxs-lookup"><span data-stu-id="49e5f-114">**Order invoiced** – This email notification type is new.</span></span> <span data-ttu-id="49e5f-115">Se puede utilizar en lugar del tipo de notificación **Pedido enviado** que enviará una notificación para cualquier evento de factura que tenga un modo de entrega enviado (no un modo de recogida, envío o envío electrónico).</span><span class="sxs-lookup"><span data-stu-id="49e5f-115">It can be used instead of the **Order shipped** notification type that will send a notification for any invoice event that has a shipped mode of delivery (not a pickup, carry out, or electronic mode of delivery).</span></span>
- <span data-ttu-id="49e5f-116">**Pedido recogido**</span><span class="sxs-lookup"><span data-stu-id="49e5f-116">**Order picked**</span></span>
- <span data-ttu-id="49e5f-117">**Pedido empaquetado**</span><span class="sxs-lookup"><span data-stu-id="49e5f-117">**Order packed**</span></span>
- <span data-ttu-id="49e5f-118">**Pedido listo para recoger**: este tipo de notificación se puede personalizar por modo de entrega solo si la característica **Compatibilidad para múltiples modos de entrega de recogida** está activada.</span><span class="sxs-lookup"><span data-stu-id="49e5f-118">**Order ready for pickup** – This notification type can be customized by mode of delivery only if the **Support for multiple pickup delivery modes** feature is turned on.</span></span> <span data-ttu-id="49e5f-119">En ese caso, este tipo de notificación es funcionalmente equivalente al tipo de notificación **Pedido empaquetado**.</span><span class="sxs-lookup"><span data-stu-id="49e5f-119">In that case, this notification type is functionally equivalent to the **Order packed** notification type.</span></span>
- <span data-ttu-id="49e5f-120">**Pago fallido**</span><span class="sxs-lookup"><span data-stu-id="49e5f-120">**Payment failed**</span></span>
- <span data-ttu-id="49e5f-121">**Pedido de sustitución creado**</span><span class="sxs-lookup"><span data-stu-id="49e5f-121">**Replacement order created**</span></span>

## <a name="configure-email-templates-for-specific-modes-of-delivery"></a><span data-ttu-id="49e5f-122">Configurar plantillas de correo electrónico para modos de entrega específicos</span><span class="sxs-lookup"><span data-stu-id="49e5f-122">Configure email templates for specific modes of delivery</span></span>

<span data-ttu-id="49e5f-123">Para este procedimiento, se supone que ya ha creado sus nuevas plantillas de correo electrónico personalizadas y las ha agregado a la página **Plantillas de correo electrónico de organización**.</span><span class="sxs-lookup"><span data-stu-id="49e5f-123">For this procedure, the assumption is that you've already created your new, custom email templates and added them to the **Organization email templates** page.</span></span> <span data-ttu-id="49e5f-124">Para obtener información sobre cómo crear y cargar plantillas de correo electrónico, consulte [Crear plantillas de correo electrónico para eventos transaccionales](email-templates-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="49e5f-124">For information about how to create and upload email templates, see [Create email templates for transactional events](email-templates-transactions.md).</span></span>

<span data-ttu-id="49e5f-125">Para configurar plantillas de correo electrónico para modos específicos de entrega en la sede central de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="49e5f-125">To configure email templates for specific modes of delivery in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="49e5f-126">Vaya a **Perfil de notificación por correo electrónico de Commerce**.</span><span class="sxs-lookup"><span data-stu-id="49e5f-126">Go to **Commerce email notification profile**.</span></span>
1. <span data-ttu-id="49e5f-127">En **Configuración de notificación de evento comercial**, seleccione un tipo de notificación existente.</span><span class="sxs-lookup"><span data-stu-id="49e5f-127">Under **Retail event notification settings**, select an existing notification type.</span></span>
1. <span data-ttu-id="49e5f-128">Mientras el tipo de notificación aún está seleccionado, seleccione **Configurar modos de entrega**.</span><span class="sxs-lookup"><span data-stu-id="49e5f-128">While the notification type is still selected, select **Configure modes of delivery**.</span></span>
1. <span data-ttu-id="49e5f-129">En el cuadro de diálogo **Modos de entrega**, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="49e5f-129">In the **Modes of delivery** dialog box, select **New**.</span></span>
1. <span data-ttu-id="49e5f-130">En la nueva fila, en el campo **Modo de entrega**, seleccione un modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="49e5f-130">In the new row, in the **Mode of delivery** field, select a mode of delivery.</span></span>
1. <span data-ttu-id="49e5f-131">En el campo **Identificación de correo**, seleccione la plantilla de correo electrónico para asignar al modo de entrega.</span><span class="sxs-lookup"><span data-stu-id="49e5f-131">In the **Email ID** field, select the email template to map to the mode of delivery.</span></span>
1. <span data-ttu-id="49e5f-132">Active la casilla **Activo**.</span><span class="sxs-lookup"><span data-stu-id="49e5f-132">Select the **Active** check box.</span></span>
1. <span data-ttu-id="49e5f-133">Repita los pasos 4 a 7 para agregar más modos de entrega.</span><span class="sxs-lookup"><span data-stu-id="49e5f-133">Repeat steps 4 through 7 to add more modes of delivery.</span></span>
1. <span data-ttu-id="49e5f-134">Cuando haya terminado, haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="49e5f-134">When you've finished, select **OK**.</span></span>

> [!NOTE]
> - <span data-ttu-id="49e5f-135">Cuando hay más de un modo de entrega en las líneas de un pedido de cliente, se utilizará la plantilla predeterminada.</span><span class="sxs-lookup"><span data-stu-id="49e5f-135">When more than one mode of delivery is present across lines in a sales order, the default template will be used.</span></span> <span data-ttu-id="49e5f-136">La plantilla predeterminada es la plantilla que se asigna al tipo de notificación en la página **Perfil de notificación por correo electrónico de Commerce** página.</span><span class="sxs-lookup"><span data-stu-id="49e5f-136">The default template is the template that is mapped to the notification type on the **Commerce email notification profile** page.</span></span>
> - <span data-ttu-id="49e5f-137">Si un pedido de venta tiene un modo de entrega que no se ha configurado para una plantilla de correo electrónico personalizada, se utilizará la plantilla de correo electrónico predeterminada.</span><span class="sxs-lookup"><span data-stu-id="49e5f-137">If a sales order has a mode of delivery that hasn't been configured for a custom email template, the default email template will be used.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="49e5f-138">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="49e5f-138">Additional resources</span></span>

[<span data-ttu-id="49e5f-139">Crear pedidos de centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="49e5f-139">Create call center orders</span></span>](tasks/create-call-center-orders.md)

[<span data-ttu-id="49e5f-140">Cambiar el modo de entrega en PDV</span><span class="sxs-lookup"><span data-stu-id="49e5f-140">Change mode of delivery in POS</span></span>](pos-change-delivery-mode.md)
