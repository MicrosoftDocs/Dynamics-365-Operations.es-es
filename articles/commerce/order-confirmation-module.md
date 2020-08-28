---
title: Módulo Detalles del pedido
description: En este tema se tratan los módulos de detalles de pedidos y se describe cómo usarlos en Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 06/18/2020
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
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 5876b953a3b3d960c106acf37731fde13b93f8e7
ms.sourcegitcommit: ae0843763a8b6b232bb71db326fab28605ac6c53
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2020
ms.locfileid: "3661181"
---
# <a name="order-details-module"></a><span data-ttu-id="533da-103">Módulo Detalles del pedido</span><span class="sxs-lookup"><span data-stu-id="533da-103">Order details module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="533da-104">En este tema se tratan los módulos de detalles de pedidos y se describe cómo usarlos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="533da-104">This topic covers order details modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="533da-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="533da-105">Overview</span></span>

<span data-ttu-id="533da-106">El módulo Detalles del pedido se usa para mostrar los detalles de confirmación de pedido después de que se haya realizado un pedido.</span><span class="sxs-lookup"><span data-stu-id="533da-106">The order details module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="533da-107">Muestra el id. de confirmación del pedido, la información de contacto del pedido y otros detalles del pedido, como los artículos que se compraron, la información de pago y el método de envío.</span><span class="sxs-lookup"><span data-stu-id="533da-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, and the shipping method.</span></span>

## <a name="order-details-module-properties"></a><span data-ttu-id="533da-108">Propiedades del módulo de detalles de pedido</span><span class="sxs-lookup"><span data-stu-id="533da-108">Order details module properties</span></span>

| <span data-ttu-id="533da-109">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="533da-109">Property name</span></span>  | <span data-ttu-id="533da-110">Valores</span><span class="sxs-lookup"><span data-stu-id="533da-110">Values</span></span> | <span data-ttu-id="533da-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="533da-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="533da-112">Cabecera</span><span class="sxs-lookup"><span data-stu-id="533da-112">Heading</span></span>        | <span data-ttu-id="533da-113">Etiqueta de encabezado y texto de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**)</span><span class="sxs-lookup"><span data-stu-id="533da-113">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="533da-114">El módulo de detalles de pedido puede tener un encabezado.</span><span class="sxs-lookup"><span data-stu-id="533da-114">The order details module can have a heading.</span></span> <span data-ttu-id="533da-115">De forma predeterminada, la etiqueta de encabezado **H2** se usa para el encabezado.</span><span class="sxs-lookup"><span data-stu-id="533da-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="533da-116">Sin embargo, la etiqueta se puede cambiar para satisfacer los requisitos de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="533da-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="533da-117">Número de contacto</span><span class="sxs-lookup"><span data-stu-id="533da-117">Contact number</span></span> | <span data-ttu-id="533da-118">Text</span><span class="sxs-lookup"><span data-stu-id="533da-118">Text</span></span> | <span data-ttu-id="533da-119">Se puede proporcionar un número de contacto para preguntas relacionadas con pedidos.</span><span class="sxs-lookup"><span data-stu-id="533da-119">A contact number can be provided for order-related questions.</span></span> |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a><span data-ttu-id="533da-120">Módulos que se pueden usar en una página de detalles del pedido</span><span class="sxs-lookup"><span data-stu-id="533da-120">Modules that can be used on an order details page</span></span>

<span data-ttu-id="533da-121">Al crear una página de detalles del pedido, puede agregar otros módulos relevantes además del módulo de detalles del pedido.</span><span class="sxs-lookup"><span data-stu-id="533da-121">When you create an order details page, you can add other relevant modules in addition to the order details module.</span></span> <span data-ttu-id="533da-122">A continuación, encontrará algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="533da-122">Here are some examples:</span></span>

- <span data-ttu-id="533da-123">**Módulo Recomendaciones**: el módulo de recomendaciones se puede agregar a la página de detalles del pedido para sugerir otros productos al cliente.</span><span class="sxs-lookup"><span data-stu-id="533da-123">**Recommendations module** – The recommendations module can be added to the order details page to suggest other products to the customer.</span></span>
- <span data-ttu-id="533da-124">**Módulos de marketing**: se puede agregar cualquier módulo de marketing a la página de detalles del pedido para mostrar el contenido de marketing.</span><span class="sxs-lookup"><span data-stu-id="533da-124">**Marketing modules** – Any marketing module can be added to the order details page to show marketing content.</span></span>

## <a name="add-an-order-details-module-to-a-page"></a><span data-ttu-id="533da-125">Agregar un módulo detalles de pedido a una página</span><span class="sxs-lookup"><span data-stu-id="533da-125">Add an order details module to a page</span></span>

<span data-ttu-id="533da-126">Para agregar un módulo de detalles de pedido a una página nueva y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="533da-126">To add an order details module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="533da-127">Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="533da-127">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="533da-128">En el cuadro de diálogo **Nueva plantilla**, en de **Nombre de la plantilla**, especifique el nombre **Plantilla de detalles pedio** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="533da-128">In the **New Template** dialog box, under **Template name**, enter the name **Order details template**, and then select **OK**.</span></span>
1. <span data-ttu-id="533da-129">En el espacio **Cuerpo**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="533da-129">In the **Body** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="533da-130">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Página predeterminada** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="533da-130">In the **Add Module** dialog box, select the **Default page** module, and then select **OK**.</span></span>
1. <span data-ttu-id="533da-131">En el espacio **Principal** del módulo **Página predeterminada**, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="533da-131">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="533da-132">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Detalles del pedido** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="533da-132">In the **Add Module** dialog box, select the **Order details** module, and then select **OK**.</span></span>
1. <span data-ttu-id="533da-133">Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="533da-133">Select **Save**, and then select **Preview** to preview the template.</span></span> <span data-ttu-id="533da-134">No se representará el módulo de detalles del pedido porque requiere el contexto del número de confirmación de pedido.</span><span class="sxs-lookup"><span data-stu-id="533da-134">The order details module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="533da-135">Seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="533da-135">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="533da-136">Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.</span><span class="sxs-lookup"><span data-stu-id="533da-136">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="533da-137">En el cuadro de diálogo **Elegir una plantilla**, seleccione la plantilla **Plantilla de detalles del pedido**.</span><span class="sxs-lookup"><span data-stu-id="533da-137">In the **Choose a template** dialog box, select **Order details template**.</span></span> <span data-ttu-id="533da-138">En **Nombre de página**, introduzca **Página de detalles de pedido** y después seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="533da-138">Under **Page name**, enter **Order details page**, and then select **OK**.</span></span>
1. <span data-ttu-id="533da-139">En el espacio **Principal** del módulo **Página predeterminada**, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="533da-139">In the **Main** slot of the **Default Page** module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="533da-140">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Detalles del pedido** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="533da-140">In the **Add Module** dialog box, select the **Order details** module, and then select **OK**.</span></span>
1. <span data-ttu-id="533da-141">En el panel de propiedades del módulo de detalles del pedido, seleccione **Encabezado** al lado del símbolo de lápiz.</span><span class="sxs-lookup"><span data-stu-id="533da-141">In the properties pane for the order details module, select **Heading** next to the pencil symbol.</span></span>
1. <span data-ttu-id="533da-142">En el campo **Texto de encabezado** del cuadro de diálogo **Encabezado**, especifique el texto de encabezado **Detalles del pedido** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="533da-142">In the **Heading Text** field of the **Heading** dialog box, enter the heading text **Order details**, and then select **OK**.</span></span>
1. <span data-ttu-id="533da-143">Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.</span><span class="sxs-lookup"><span data-stu-id="533da-143">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="533da-144">Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="533da-144">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="533da-145">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="533da-145">Additional resources</span></span>

[<span data-ttu-id="533da-146">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="533da-146">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="533da-147">Módulo de icono de carro</span><span class="sxs-lookup"><span data-stu-id="533da-147">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="533da-148">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="533da-148">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="533da-149">Módulo de pago</span><span class="sxs-lookup"><span data-stu-id="533da-149">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="533da-150">Módulo de dirección de envío</span><span class="sxs-lookup"><span data-stu-id="533da-150">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="533da-151">Módulo de opciones de entrega</span><span class="sxs-lookup"><span data-stu-id="533da-151">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="533da-152">Módulo de tarjeta de regalo</span><span class="sxs-lookup"><span data-stu-id="533da-152">Gift card module</span></span>](add-giftcard.md)
