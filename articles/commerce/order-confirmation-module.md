---
title: Módulo Detalles del pedido
description: En este tema se tratan los módulos de detalles de pedidos y se describe cómo usarlos en Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: cb09a0b6ce1e48707f96021e9fad0006d9c1c55c
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3026026"
---
# <a name="order-details-module"></a><span data-ttu-id="40078-103">Módulo Detalles del pedido</span><span class="sxs-lookup"><span data-stu-id="40078-103">Order details module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="40078-104">En este tema se tratan los módulos de detalles de pedidos y se describe cómo usarlos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="40078-104">This topic covers order details modules and describes how to use them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="40078-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="40078-105">Overview</span></span>

<span data-ttu-id="40078-106">El módulo Detalles del pedido se usa para mostrar los detalles de confirmación de pedido después de que se haya realizado un pedido.</span><span class="sxs-lookup"><span data-stu-id="40078-106">The order details module is used to show order confirmation details after an order has been placed.</span></span> <span data-ttu-id="40078-107">Muestra el id. de confirmación del pedido, la información de contacto del pedido y otros detalles del pedido, como los artículos que se compraron, la información de pago y el método de envío.</span><span class="sxs-lookup"><span data-stu-id="40078-107">It shows the order confirmation ID, order contact information, and other order details, such as the items that were purchased, payment information, and the shipping method.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="40078-108">Propiedades del módulo de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="40078-108">Order confirmation module properties</span></span>

| <span data-ttu-id="40078-109">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="40078-109">Property name</span></span>  | <span data-ttu-id="40078-110">Valores</span><span class="sxs-lookup"><span data-stu-id="40078-110">Values</span></span> | <span data-ttu-id="40078-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="40078-111">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="40078-112">Título</span><span class="sxs-lookup"><span data-stu-id="40078-112">Heading</span></span>        | <span data-ttu-id="40078-113">Etiqueta de encabezado y texto de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**)</span><span class="sxs-lookup"><span data-stu-id="40078-113">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="40078-114">El módulo de confirmación de pedido puede tener un encabezado.</span><span class="sxs-lookup"><span data-stu-id="40078-114">The order confirmation module can have a heading.</span></span> <span data-ttu-id="40078-115">De forma predeterminada, la etiqueta de encabezado **H2** se usa para el encabezado.</span><span class="sxs-lookup"><span data-stu-id="40078-115">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="40078-116">Sin embargo, la etiqueta se puede cambiar para satisfacer los requisitos de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="40078-116">However, the tag can be changed to meet accessibility requirements.</span></span> |
| <span data-ttu-id="40078-117">Número de contacto</span><span class="sxs-lookup"><span data-stu-id="40078-117">Contact number</span></span> | <span data-ttu-id="40078-118">Text</span><span class="sxs-lookup"><span data-stu-id="40078-118">Text</span></span> | <span data-ttu-id="40078-119">Se puede proporcionar un número de contacto para preguntas relacionadas con pedidos.</span><span class="sxs-lookup"><span data-stu-id="40078-119">A contact number can be provided for order-related questions.</span></span> |

## <a name="modules-that-can-be-used-on-an-order-details-page"></a><span data-ttu-id="40078-120">Módulos que se pueden usar en una página de detalles del pedido</span><span class="sxs-lookup"><span data-stu-id="40078-120">Modules that can be used on an order details page</span></span>

<span data-ttu-id="40078-121">Al crear una página de detalles del pedido, puede agregar otros módulos relevantes además del módulo de detalles del pedido.</span><span class="sxs-lookup"><span data-stu-id="40078-121">When you create an order details page, you can add other relevant modules in addition to the order details module.</span></span> <span data-ttu-id="40078-122">A continuación, encontrará algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="40078-122">Here are some examples:</span></span>

- <span data-ttu-id="40078-123">**Módulo Recomendaciones**: el módulo de recomendaciones se puede agregar a la página de detalles del pedido para sugerir otros productos al cliente.</span><span class="sxs-lookup"><span data-stu-id="40078-123">**Recommendations module** – The recommendations module can be added to the order details page to suggest other products to the customer.</span></span>
- <span data-ttu-id="40078-124">**Módulos de marketing**: se puede agregar cualquier módulo de marketing a la página de detalles del pedido para mostrar el contenido de marketing.</span><span class="sxs-lookup"><span data-stu-id="40078-124">**Marketing modules** – Any marketing module can be added to the order details page to show marketing content.</span></span>

## <a name="create-an-order-details-page-module"></a><span data-ttu-id="40078-125">Crear un módulo de página de detalles del pedido</span><span class="sxs-lookup"><span data-stu-id="40078-125">Create an order details page module</span></span>

1. <span data-ttu-id="40078-126">Cree una plantilla de página con el nombre **Plantilla de detalles del pedido**.</span><span class="sxs-lookup"><span data-stu-id="40078-126">Create a page template that is named **Order details template**.</span></span>
1. <span data-ttu-id="40078-127">En la franja **Principal** de la página predeterminada, agregue un módulo de detalles de pedido.</span><span class="sxs-lookup"><span data-stu-id="40078-127">In the **Main** slot of the default page, add an order details module.</span></span>
1. <span data-ttu-id="40078-128">En el módulo de detalles del pedido, agregue un módulo de recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="40078-128">In the order details module, add a recommendations module.</span></span>
1. <span data-ttu-id="40078-129">Guarde la plantilla y obtenga una vista previa de ella.</span><span class="sxs-lookup"><span data-stu-id="40078-129">Save and preview the template.</span></span> <span data-ttu-id="40078-130">No se representará el módulo de detalles del pedido porque requiere el contexto del número de confirmación de pedido.</span><span class="sxs-lookup"><span data-stu-id="40078-130">The order details module won't be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="40078-131">Termine de editar la plantilla y publíquela.</span><span class="sxs-lookup"><span data-stu-id="40078-131">Finish editing the template, and publish it.</span></span>
1. <span data-ttu-id="40078-132">Use la plantilla de detalles del pedido que acaba de crear para crear una página con el nombre **página de detalles de pedido**.</span><span class="sxs-lookup"><span data-stu-id="40078-132">Use the order details template that you just created to create a page that is named **order details page**.</span></span>
1. <span data-ttu-id="40078-133">Agregue la página predeterminada al esquema de página.</span><span class="sxs-lookup"><span data-stu-id="40078-133">Add the default page to the page outline.</span></span>
1. <span data-ttu-id="40078-134">En la franja **Encabezado**, agregue un fragmento de encabezado.</span><span class="sxs-lookup"><span data-stu-id="40078-134">In the **Header** slot, add a header fragment.</span></span>
1. <span data-ttu-id="40078-135">En la franja **Pie de página**, agregue un fragmento de pie de página.</span><span class="sxs-lookup"><span data-stu-id="40078-135">In the **Footer** slot, add a footer fragment.</span></span>
1. <span data-ttu-id="40078-136">En la franja **Principal**, agregue un módulo de detalles de pedido.</span><span class="sxs-lookup"><span data-stu-id="40078-136">In the **Main** slot, add an order details module.</span></span>
1. <span data-ttu-id="40078-137">En el panel de propiedades para el módulo de detalles de pedido, agregue el encabezado **Detalles de pedido**.</span><span class="sxs-lookup"><span data-stu-id="40078-137">In the property pane for the order details module, add the heading **Order details**.</span></span>
1. <span data-ttu-id="40078-138">Debajo del módulo de detalles de pedido, agregue un módulo de recomendaciones y configúrelo para que use la configuración **Nuevos** y **Más vendidos**.</span><span class="sxs-lookup"><span data-stu-id="40078-138">Below the order details module, add a recommendations module, and configure it so that it uses the **New** and **Best Selling** settings.</span></span>
1. <span data-ttu-id="40078-139">Guarde la página y obtenga una vista previa de ella.</span><span class="sxs-lookup"><span data-stu-id="40078-139">Save and preview the page.</span></span>
1. <span data-ttu-id="40078-140">Termine de editar la página y publíquela.</span><span class="sxs-lookup"><span data-stu-id="40078-140">Finish editing the page, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="40078-141">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="40078-141">Additional resources</span></span>

[<span data-ttu-id="40078-142">Visión general de kit de inicio</span><span class="sxs-lookup"><span data-stu-id="40078-142">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="40078-143">Módulo Contenedor</span><span class="sxs-lookup"><span data-stu-id="40078-143">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="40078-144">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="40078-144">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="40078-145">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="40078-145">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="40078-146">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="40078-146">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="40078-147">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="40078-147">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="40078-148">Módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="40078-148">Footer module</span></span>](author-footer-module.md)
