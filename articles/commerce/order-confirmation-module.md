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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 407fc2724d4b589ef5f611974f9358e879dba7ed
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257156"
---
# <a name="order-confirmation-module"></a><span data-ttu-id="b0a7b-103">Módulo de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="b0a7b-103">Order confirmation module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b0a7b-104">En este tema se tratan los módulos de confirmación de pedidos y se describe cómo usarlos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-104">This topic covers order confirmation modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="b0a7b-105">El módulo para la confirmación del pedido se usa para mostrar los detalles de confirmación de pedido después de que se haya realizado un pedido.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-105">The order confirmation module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="b0a7b-106">Muestra el id. de confirmación del pedido, la información de contacto del pedido y otros detalles del pedido, como los artículos que se compraron, la información de pago, las opciones de recogida y el método de envío.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-106">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, pickup options, and the shipping method.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="b0a7b-107">Propiedades del módulo de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="b0a7b-107">Order confirmation module properties</span></span>

| <span data-ttu-id="b0a7b-108">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="b0a7b-108">Property name</span></span>  | <span data-ttu-id="b0a7b-109">Valores</span><span class="sxs-lookup"><span data-stu-id="b0a7b-109">Values</span></span> | <span data-ttu-id="b0a7b-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="b0a7b-110">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="b0a7b-111">Título</span><span class="sxs-lookup"><span data-stu-id="b0a7b-111">Heading</span></span>        | <span data-ttu-id="b0a7b-112">Etiqueta de encabezado y texto de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**)</span><span class="sxs-lookup"><span data-stu-id="b0a7b-112">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="b0a7b-113">El módulo de confirmación de pedido puede tener un encabezado.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-113">The order confirmation module can have a heading.</span></span> <span data-ttu-id="b0a7b-114">De forma predeterminada, la etiqueta de encabezado **H2** se usa para el encabezado.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-114">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="b0a7b-115">Sin embargo, la etiqueta se puede cambiar para satisfacer los requisitos de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-115">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="b0a7b-116">Número de contacto</span><span class="sxs-lookup"><span data-stu-id="b0a7b-116">Contact number</span></span> | <span data-ttu-id="b0a7b-117">Text</span><span class="sxs-lookup"><span data-stu-id="b0a7b-117">Text</span></span> | <span data-ttu-id="b0a7b-118">Se puede proporcionar un número de contacto para preguntas relacionadas con pedidos.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-118">A contact number can be provided for order-related questions.</span></span> |
| <span data-ttu-id="b0a7b-119">Mostrar información sobre el horario de recogida</span><span class="sxs-lookup"><span data-stu-id="b0a7b-119">Show pickup timeslot information</span></span> | <span data-ttu-id="b0a7b-120">Verdadero o falso</span><span class="sxs-lookup"><span data-stu-id="b0a7b-120">True or False</span></span> | <span data-ttu-id="b0a7b-121">Esta propiedad está disponible en Dynamics 365 Commerce 10.0.15 y versiones posteriores.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-121">This property is available in Dynamics 365 Commerce 10.0.15 and higher.</span></span> <span data-ttu-id="b0a7b-122">Cuando se establece en True, muestra la información del intervalo de tiempo de recogida si se proporciona para un artículo de recogida</span><span class="sxs-lookup"><span data-stu-id="b0a7b-122">When true, it displays the pickup timeslot information if provided for a pickup item</span></span>|

## <a name="modules-that-can-be-used-on-an-order-confirmation-page"></a><span data-ttu-id="b0a7b-123">Módulos que se pueden usar en una página de confirmación del pedido</span><span class="sxs-lookup"><span data-stu-id="b0a7b-123">Modules that can be used on an order confirmation page</span></span>

<span data-ttu-id="b0a7b-124">Al crear una página de confirmación del pedido, puede agregar otros módulos relevantes además del módulo de confirmación del pedido.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-124">When you create an order confirmation page, you can add other relevant modules in addition to the order confirmation module.</span></span> <span data-ttu-id="b0a7b-125">A continuación, encontrará algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="b0a7b-125">Here are some examples:</span></span>

- <span data-ttu-id="b0a7b-126">**Módulo Recomendaciones**: el módulo de recomendaciones se puede agregar a la página de confirmación del pedido para sugerir otros productos al cliente.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-126">**Recommendations module** – The recommendations module can be added to the order confirmation page to suggest other products to the customer.</span></span>
- <span data-ttu-id="b0a7b-127">**Módulos de marketing**: se puede agregar cualquier módulo de marketing a la página de confirmación del pedido para mostrar el contenido de marketing.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-127">**Marketing modules** – Any marketing module can be added to the order confirmation page to show marketing content.</span></span>

## <a name="add-an-order-confirmation-module-to-a-page"></a><span data-ttu-id="b0a7b-128">Agregar un módulo de confirmación del pedido a una página</span><span class="sxs-lookup"><span data-stu-id="b0a7b-128">Add an order confirmation module to a page</span></span>

<span data-ttu-id="b0a7b-129">Para agregar un módulo de confirmación del pedido a una página nueva y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-129">To add an order confirmation module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="b0a7b-130">Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-130">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="b0a7b-131">En el cuadro de diálogo **Nueva plantilla**, en de **Nombre de la plantilla**, especifique el nombre **Plantilla de confirmación del pedio** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-131">In the **New Template** dialog box, under **Template name**, enter the name **Order confirmation template**, and then select **OK**.</span></span>
1. <span data-ttu-id="b0a7b-132">En el espacio **Cuerpo**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-132">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b0a7b-133">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Página predeterminada** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-133">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b0a7b-134">En el espacio **Principal** del módulo **Página predeterminada**, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-134">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b0a7b-135">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Confirmación del pedido** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-135">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b0a7b-136">Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-136">Select **Save**, and then select **Preview** to preview the template.</span></span> <span data-ttu-id="b0a7b-137">No se representará el módulo de confirmación de pedido porque requiere el contexto del número de confirmación de pedido.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-137">The order confirmation module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="b0a7b-138">Seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-138">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="b0a7b-139">Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-139">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="b0a7b-140">En el cuadro de diálogo **Elegir una plantilla**, seleccione la plantilla **Plantilla de confirmación del pedido**.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-140">In the **Choose a template** dialog box, select **Order confirmation template**.</span></span> <span data-ttu-id="b0a7b-141">En **Nombre de página**, introduzca **Página de confirmación del pedido** y después seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-141">Under **Page name**, enter **Order confirmation page**, and then select **OK**.</span></span>
1. <span data-ttu-id="b0a7b-142">En el espacio **Principal** del módulo **Página predeterminada**, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-142">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="b0a7b-143">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Confirmación del pedido** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-143">In the **Add Module** dialog box, select the **Order confirmation** module, and then select **OK**.</span></span>
1. <span data-ttu-id="b0a7b-144">En el panel de propiedades del módulo de confirmación del pedido, seleccione **Encabezado** al lado del símbolo de lápiz.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-144">In the properties pane for the order confirmation module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="b0a7b-145">En el campo **Texto de encabezado** del cuadro de diálogo **Encabezado**, especifique el texto de encabezado **Confirmación del pedido** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-145">In the **Heading Text** field of the **Heading** dialog box, enter the heading text **Order confirmation**, and then select **OK**.</span></span>
1. <span data-ttu-id="b0a7b-146">Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-146">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="b0a7b-147">Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="b0a7b-147">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b0a7b-148">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b0a7b-148">Additional resources</span></span>

[<span data-ttu-id="b0a7b-149">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="b0a7b-149">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="b0a7b-150">Módulo de icono de carro</span><span class="sxs-lookup"><span data-stu-id="b0a7b-150">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="b0a7b-151">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="b0a7b-151">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="b0a7b-152">Módulo de pago</span><span class="sxs-lookup"><span data-stu-id="b0a7b-152">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="b0a7b-153">Módulo de dirección de envío</span><span class="sxs-lookup"><span data-stu-id="b0a7b-153">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="b0a7b-154">Módulo de opciones de entrega</span><span class="sxs-lookup"><span data-stu-id="b0a7b-154">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="b0a7b-155">Módulo de información de recogida</span><span class="sxs-lookup"><span data-stu-id="b0a7b-155">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="b0a7b-156">Módulo de tarjeta de regalo</span><span class="sxs-lookup"><span data-stu-id="b0a7b-156">Gift card module</span></span>](add-giftcard.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]