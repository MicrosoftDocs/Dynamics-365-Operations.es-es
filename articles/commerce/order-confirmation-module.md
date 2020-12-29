---
title: Módulo de confirmación de pedido
description: En este tema se tratan los módulos de confirmación de pedidos y se describe cómo usarlos en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: bf33ebf9c0c5136f40fcd7e1012988d186c4169b
ms.sourcegitcommit: 12d271bb26c7490e7525d9b4bbf125cdc39fef43
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/07/2020
ms.locfileid: "4415698"
---
# <a name="order-confirmation-module"></a><span data-ttu-id="aded7-103">Módulo de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="aded7-103">Order confirmation module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="aded7-104">En este tema se tratan los módulos de confirmación de pedidos y se describe cómo usarlos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="aded7-104">This topic covers order confirmation modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="aded7-105">Información general</span><span class="sxs-lookup"><span data-stu-id="aded7-105">Overview</span></span>

<span data-ttu-id="aded7-106">El módulo para la confirmación del pedido se usa para mostrar los detalles de confirmación de pedido después de que se haya realizado un pedido.</span><span class="sxs-lookup"><span data-stu-id="aded7-106">The order confirmation module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="aded7-107">Muestra el id. de confirmación del pedido, la información de contacto del pedido y otros detalles del pedido, como los artículos que se compraron, la información de pago, las opciones de recogida y el método de envío.</span><span class="sxs-lookup"><span data-stu-id="aded7-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, pickup options, and the shipping method.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="aded7-108">Propiedades del módulo de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="aded7-108">Order confirmation module properties</span></span>

| <span data-ttu-id="aded7-109">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="aded7-109">Property name</span></span>  | <span data-ttu-id="aded7-110">Valores</span><span class="sxs-lookup"><span data-stu-id="aded7-110">Values</span></span> | <span data-ttu-id="aded7-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="aded7-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="aded7-112">Título</span><span class="sxs-lookup"><span data-stu-id="aded7-112">Heading</span></span>        | <span data-ttu-id="aded7-113">Etiqueta de encabezado y texto de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**)</span><span class="sxs-lookup"><span data-stu-id="aded7-113">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="aded7-114">El módulo de confirmación de pedido puede tener un encabezado.</span><span class="sxs-lookup"><span data-stu-id="aded7-114">The order confirmation module can have a heading.</span></span> <span data-ttu-id="aded7-115">De forma predeterminada, la etiqueta de encabezado **H2** se usa para el encabezado.</span><span class="sxs-lookup"><span data-stu-id="aded7-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="aded7-116">Sin embargo, la etiqueta se puede cambiar para satisfacer los requisitos de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="aded7-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="aded7-117">Número de contacto</span><span class="sxs-lookup"><span data-stu-id="aded7-117">Contact number</span></span> | <span data-ttu-id="aded7-118">Text</span><span class="sxs-lookup"><span data-stu-id="aded7-118">Text</span></span> | <span data-ttu-id="aded7-119">Se puede proporcionar un número de contacto para preguntas relacionadas con pedidos.</span><span class="sxs-lookup"><span data-stu-id="aded7-119">A contact number can be provided for order-related questions.</span></span> |
| <span data-ttu-id="aded7-120">Mostrar información sobre el horario de recogida</span><span class="sxs-lookup"><span data-stu-id="aded7-120">Show pickup timeslot information</span></span> | <span data-ttu-id="aded7-121">Verdadero o falso</span><span class="sxs-lookup"><span data-stu-id="aded7-121">True or False</span></span> | <span data-ttu-id="aded7-122">Esta propiedad está disponible en Dynamics 365 Commerce 10.0.15 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="aded7-122">This property is available in Dynamics 365 Commerce 10.0.15 and higher.</span></span> <span data-ttu-id="aded7-123">Cuando se establece en True, muestra la información del intervalo de tiempo de recogida si se proporciona para un artículo de recogida</span><span class="sxs-lookup"><span data-stu-id="aded7-123">When true, it displays the pickup timeslot information if provided for a pickup item</span></span>|

## <a name="modules-that-can-be-used-on-an-order-confirmation-page"></a><span data-ttu-id="aded7-124">Módulos que se pueden usar en una página de confirmación del pedido</span><span class="sxs-lookup"><span data-stu-id="aded7-124">Modules that can be used on an order confirmation page</span></span>

<span data-ttu-id="aded7-125">Al crear una página de confirmación del pedido, puede agregar otros módulos relevantes además del módulo de confirmación del pedido.</span><span class="sxs-lookup"><span data-stu-id="aded7-125">When you create an order confirmation page, you can add other relevant modules in addition to the order confirmation module.</span></span> <span data-ttu-id="aded7-126">A continuación, encontrará algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="aded7-126">Here are some examples:</span></span>

- <span data-ttu-id="aded7-127">**Módulo Recomendaciones**: el módulo de recomendaciones se puede agregar a la página de confirmación del pedido para sugerir otros productos al cliente.</span><span class="sxs-lookup"><span data-stu-id="aded7-127">**Recommendations module** – The recommendations module can be added to the order confirmation page to suggest other products to the customer.</span></span>
- <span data-ttu-id="aded7-128">**Módulos de marketing**: se puede agregar cualquier módulo de marketing a la página de confirmación del pedido para mostrar el contenido de marketing.</span><span class="sxs-lookup"><span data-stu-id="aded7-128">**Marketing modules** – Any marketing module can be added to the order confirmation page to show marketing content.</span></span>

## <a name="add-an-order-confirmation-module-to-a-page"></a><span data-ttu-id="aded7-129">Agregar un módulo de confirmación del pedido a una página</span><span class="sxs-lookup"><span data-stu-id="aded7-129">Add an order confirmation module to a page</span></span>

<span data-ttu-id="aded7-130">Para agregar un módulo de confirmación del pedido a una página nueva y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="aded7-130">To add an order confirmation module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="aded7-131">Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="aded7-131">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="aded7-132">En el cuadro de diálogo **Nueva plantilla**, en de **Nombre de la plantilla**, especifique el nombre **Plantilla de confirmación del pedio** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aded7-132">In the **New Template** dialog box, under **Template name**, enter the name **Order confirmation template**, and then select **OK**.</span></span>
1. <span data-ttu-id="aded7-133">En el espacio **Cuerpo**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="aded7-133">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="aded7-134">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Página predeterminada** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aded7-134">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="aded7-135">En el espacio **Principal** del módulo **Página predeterminada**, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="aded7-135">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="aded7-136">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Confirmación del pedido** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aded7-136">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="aded7-137">Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="aded7-137">Select **Save**, and then select **Preview** to preview the template.</span></span> <span data-ttu-id="aded7-138">No se representará el módulo de confirmación de pedido porque requiere el contexto del número de confirmación de pedido.</span><span class="sxs-lookup"><span data-stu-id="aded7-138">The order confirmation module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="aded7-139">Seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="aded7-139">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="aded7-140">Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.</span><span class="sxs-lookup"><span data-stu-id="aded7-140">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="aded7-141">En el cuadro de diálogo **Elegir una plantilla**, seleccione la plantilla **Plantilla de confirmación del pedido**.</span><span class="sxs-lookup"><span data-stu-id="aded7-141">In the **Choose a template** dialog box, select **Order confirmation template**.</span></span> <span data-ttu-id="aded7-142">En **Nombre de página**, introduzca **Página de confirmación del pedido** y después seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aded7-142">Under **Page name**, enter **Order confirmation page**, and then select **OK**.</span></span>
1. <span data-ttu-id="aded7-143">En el espacio **Principal** del módulo **Página predeterminada**, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="aded7-143">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="aded7-144">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Confirmación del pedido** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aded7-144">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="aded7-145">En el panel de propiedades del módulo de confirmación del pedido, seleccione **Encabezado** al lado del símbolo de lápiz.</span><span class="sxs-lookup"><span data-stu-id="aded7-145">In the properties pane for the order confirmation module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="aded7-146">En el campo **Texto de encabezado** del cuadro de diálogo **Encabezado**, especifique el texto de encabezado **Confirmación del pedido** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="aded7-146">In the **Heading Text** field of the **Heading** dialog box, enter the heading text **Order confirmation**, and then select **OK**.</span></span>
1. <span data-ttu-id="aded7-147">Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.</span><span class="sxs-lookup"><span data-stu-id="aded7-147">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="aded7-148">Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="aded7-148">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="aded7-149">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="aded7-149">Additional resources</span></span>

[<span data-ttu-id="aded7-150">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="aded7-150">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="aded7-151">Módulo de icono de carro</span><span class="sxs-lookup"><span data-stu-id="aded7-151">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="aded7-152">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="aded7-152">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="aded7-153">Módulo de pago</span><span class="sxs-lookup"><span data-stu-id="aded7-153">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="aded7-154">Módulo de dirección de envío</span><span class="sxs-lookup"><span data-stu-id="aded7-154">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="aded7-155">Módulo de opciones de entrega</span><span class="sxs-lookup"><span data-stu-id="aded7-155">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="aded7-156">Módulo de información de recogida</span><span class="sxs-lookup"><span data-stu-id="aded7-156">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="aded7-157">Módulo de tarjeta de regalo</span><span class="sxs-lookup"><span data-stu-id="aded7-157">Gift card module</span></span>](add-giftcard.md)
