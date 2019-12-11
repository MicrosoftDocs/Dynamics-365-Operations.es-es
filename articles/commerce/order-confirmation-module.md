---
title: Módulo de confirmación de pedido
description: En este tema se tratan los módulos de confirmación de pedidos y se describe cómo crearlos en Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: e339ce02bb646d0d9a68c22b24fde9b72071de6f
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "2698335"
---
# <a name="order-confirmation-module"></a><span data-ttu-id="2c9fb-103">Módulo de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="2c9fb-103">Order confirmation module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="2c9fb-104">En este tema se tratan los módulos de confirmación de pedidos y se describe cómo crearlos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-104">This topic covers order confirmation modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="2c9fb-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="2c9fb-105">Overview</span></span>

<span data-ttu-id="2c9fb-106">Un módulo de la confirmación de pedido se usa para mostrar un mensaje de confirmación en una página de confirmación de pedido después de realizar un pedido.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-106">An order confirmation module is used to show a confirmation message on an order confirmation page after an order is placed.</span></span> <span data-ttu-id="2c9fb-107">El módulo de confirmación de pedido muestra el número de confirmación de pedido y la dirección de correo electrónico del cliente que se proporcionó durante la finalización de la compra.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-107">The order confirmation module shows the order confirmation number and the customer email address that was provided during checkout.</span></span>

<span data-ttu-id="2c9fb-108">Cuando se realiza un pedido durante la finalización de la compra, la dirección de correo electrónico del cliente y el número de confirmación del pedido se pasan a la página de confirmación de pedido como cadena de consulta en la dirección URL de la página.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-108">When an order is placed during checkout, the order confirmation number and customer email address are passed to the order confirmation page as a query string in the page's URL.</span></span> <span data-ttu-id="2c9fb-109">El módulo de confirmación de pedido recibe esta información y genera el estado del pedido en la página de confirmación de pedido.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-109">The order confirmation module receives this information and renders the order status on the order confirmation page.</span></span> <span data-ttu-id="2c9fb-110">El módulo de confirmación de pedido requiere este contexto de página para proporcionar el estado del pedido.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-110">The order confirmation module requires this page context to provide the status of the order.</span></span>

## <a name="order-confirmation-module-properties"></a><span data-ttu-id="2c9fb-111">Propiedades del módulo de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="2c9fb-111">Order confirmation module properties</span></span>

| <span data-ttu-id="2c9fb-112">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="2c9fb-112">Property name</span></span> | <span data-ttu-id="2c9fb-113">Valores</span><span class="sxs-lookup"><span data-stu-id="2c9fb-113">Values</span></span> | <span data-ttu-id="2c9fb-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="2c9fb-114">Description</span></span> |
|---------------|--------|-------------|
| <span data-ttu-id="2c9fb-115">Título</span><span class="sxs-lookup"><span data-stu-id="2c9fb-115">Heading</span></span>       | <span data-ttu-id="2c9fb-116">Etiqueta de encabezado y texto de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**)</span><span class="sxs-lookup"><span data-stu-id="2c9fb-116">Heading text and heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="2c9fb-117">El módulo de confirmación de pedido puede tener un encabezado.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-117">The order confirmation module can have a heading.</span></span> <span data-ttu-id="2c9fb-118">De forma predeterminada, la etiqueta de encabezado **H2** se usa para el encabezado.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-118">By default, the **H2** heading tag is used for the heading.</span></span> <span data-ttu-id="2c9fb-119">Sin embargo, la etiqueta se puede cambiar para satisfacer los requisitos de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-119">However, the tag can be changed to meet accessibility requirements.</span></span> |

## <a name="modules-that-can-be-used-in-an-order-confirmation-page-module"></a><span data-ttu-id="2c9fb-120">Módulos que se pueden usar en un módulo de página de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="2c9fb-120">Modules that can be used in an order confirmation page module</span></span> 

- <span data-ttu-id="2c9fb-121">**Recomendaciones**: el módulo de recomendaciones se puede colocar en la página de confirmación de pedido para sugerir otros productos al cliente.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-121">**Recommendations** – The recommendations module can be put on the order confirmation page to suggest other products to the customer.</span></span>
- <span data-ttu-id="2c9fb-122">**Marketing**: el módulo de marketing puede agregar contenido de marketing a la página de confirmación de pedido.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-122">**Marketing** – The marketing module can add marketing content to the order confirmation page.</span></span>

## <a name="create-an-order-confirmation-page-module"></a><span data-ttu-id="2c9fb-123">Crear un módulo de página de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="2c9fb-123">Create an order confirmation page module</span></span>

1. <span data-ttu-id="2c9fb-124">Cree una plantilla de página con el nombre **plantilla de confirmación de pedido**.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-124">Create a page template that is named **order confirmation template**.</span></span>
1. <span data-ttu-id="2c9fb-125">En la franja **Principal** de la página predeterminada, agregue un módulo de confirmación de pedido.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-125">In the **Main** slot of the default page, add an order confirmation module.</span></span>
1. <span data-ttu-id="2c9fb-126">En el módulo de confirmación de pedido, agregue un módulo de recomendaciones.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-126">In the order confirmation module, add a recommendations module.</span></span>
1. <span data-ttu-id="2c9fb-127">Guarde la plantilla y obtenga una vista previa de ella.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-127">Save and preview the template.</span></span> <span data-ttu-id="2c9fb-128">No se debe representar el módulo de confirmación de pedido porque requiere el contexto del número de confirmación de pedido.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-128">The order confirmation module should not be rendered, because it requires the context of the order confirmation number.</span></span>
1. <span data-ttu-id="2c9fb-129">Proteja la plantilla y publíquela.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-129">Check in the template, and publish it.</span></span>
1. <span data-ttu-id="2c9fb-130">Use la plantilla de confirmación de pedido que acaba de crear para crear una página con el nombre **página de confirmación de pedido**.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-130">Use the order confirmation template that you just created to create a page that is named **order confirmation page**.</span></span>
1. <span data-ttu-id="2c9fb-131">Agregue la página predeterminada al esquema de página.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-131">Add the default page to the page outline.</span></span>
1. <span data-ttu-id="2c9fb-132">En la franja **Encabezado**, agregue un fragmento de encabezado.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-132">In the **Header** slot, add a header fragment.</span></span>
1. <span data-ttu-id="2c9fb-133">En la franja **Pie de página**, agregue un fragmento de pie de página.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-133">In the **Footer** slot, add a footer fragment.</span></span>
1. <span data-ttu-id="2c9fb-134">En la franja **Principal**, agregue un módulo de confirmación de pedido.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-134">In the **Main** slot, add an order confirmation module.</span></span>
1. <span data-ttu-id="2c9fb-135">En el panel de propiedades del módulo de confirmación de pedido, agregue el encabezado **Confirmación de pedido**.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-135">In the property pane of the order confirmation module, add the heading **Order confirmation**.</span></span>
1. <span data-ttu-id="2c9fb-136">Debajo del módulo de confirmación de pedido, agregue un módulo de recomendaciones y configúrelo para que use la configuración **Nuevos** y **Más vendidos**.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-136">Below the order confirmation module, add a recommendations module, and configure it so that it uses the **New** and **Best Selling** settings.</span></span>
1. <span data-ttu-id="2c9fb-137">Guarde la página y obtenga una vista previa de ella, protéjala y publíquela.</span><span class="sxs-lookup"><span data-stu-id="2c9fb-137">Save and preview the page, check it in, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2c9fb-138">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2c9fb-138">Additional resources</span></span>

[<span data-ttu-id="2c9fb-139">Visión general de kit de inicio</span><span class="sxs-lookup"><span data-stu-id="2c9fb-139">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="2c9fb-140">Módulo Contenedor</span><span class="sxs-lookup"><span data-stu-id="2c9fb-140">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="2c9fb-141">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="2c9fb-141">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="2c9fb-142">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="2c9fb-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="2c9fb-143">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="2c9fb-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="2c9fb-144">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="2c9fb-144">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="2c9fb-145">Módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="2c9fb-145">Footer module</span></span>](author-footer-module.md)
