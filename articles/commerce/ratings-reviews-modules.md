---
title: Módulos de clasificaciones y opiniones
description: Este tema cubre los módulos de calificaciones y revisiones utilizados en las páginas de detalles del producto en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-10-31
ms.dyn365.ops.version: Release 10.0.6
ms.openlocfilehash: b17e986c2e30134c334cd547a85a1dd682172a0e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979812"
---
# <a name="ratings-and-reviews-modules"></a><span data-ttu-id="a333a-103">Módulos de clasificaciones y opiniones</span><span class="sxs-lookup"><span data-stu-id="a333a-103">Ratings and reviews modules</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a333a-104">Este tema cubre los módulos de calificaciones y revisiones utilizados en las páginas de detalles (PDP) del producto en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a333a-104">This topic covers ratings and reviews modules used on product details pages (PDPs) in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a333a-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="a333a-105">Overview</span></span>

<span data-ttu-id="a333a-106">Las clasificaciones y opiniones en sitios web de comercio electrónico ayudan a los clientes a obtener información acerca de los productos antes de tomar una decisión de compra, y también son un mecanismo para obtener opiniones de los clientes acerca de esos productos.</span><span class="sxs-lookup"><span data-stu-id="a333a-106">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision, and are also a mechanism for collecting customer feedback about products.</span></span> 

<span data-ttu-id="a333a-107">Las clasificaciones se muestran en las páginas de lista de productos, páginas de lista de categorías, páginas de resultados de la búsqueda y otras páginas del sitio.</span><span class="sxs-lookup"><span data-stu-id="a333a-107">Ratings are shown on product list pages, category list pages, search results pages, and other site pages.</span></span> 

<span data-ttu-id="a333a-108">Las histogramas de clasificaciones y revisiones de productos se muestran en las PDP.</span><span class="sxs-lookup"><span data-stu-id="a333a-108">Ratings histograms and product reviews are shown on PDPs.</span></span> <span data-ttu-id="a333a-109">Un botón **Escribir una opinión** permite a los clientes enviar clasificaciones y opiniones para un producto.</span><span class="sxs-lookup"><span data-stu-id="a333a-109">A **Write a review** button lets customers submit ratings and reviews for a product.</span></span> <span data-ttu-id="a333a-110">Estas características de PDP están controladas por los módulos de calificaciones y revisión.</span><span class="sxs-lookup"><span data-stu-id="a333a-110">These PDP features are controlled by ratings and review modules.</span></span>

## <a name="ratings-and-reviews-modules-on-pdps"></a><span data-ttu-id="a333a-111">Módulos de clasificaciones y opiniones en PDP</span><span class="sxs-lookup"><span data-stu-id="a333a-111">Ratings and reviews modules on PDPs</span></span> 

<span data-ttu-id="a333a-112">Tres módulos muestran el resumen de clasificaciones y opiniones en PDP:</span><span class="sxs-lookup"><span data-stu-id="a333a-112">Three modules show the ratings and reviews summary on PDPs:</span></span>
- <span data-ttu-id="a333a-113">Módulo Escribir opinión</span><span class="sxs-lookup"><span data-stu-id="a333a-113">Write review module</span></span>
- <span data-ttu-id="a333a-114">Módulo de lista de opiniones de productos</span><span class="sxs-lookup"><span data-stu-id="a333a-114">Product reviews list module</span></span>
- <span data-ttu-id="a333a-115">Módulo de histograma de clasificaciones</span><span class="sxs-lookup"><span data-stu-id="a333a-115">Ratings histogram module</span></span>
 
<span data-ttu-id="a333a-116">La ilustración siguiente muestra el aspecto de los módulos de clasificaciones y opiniones en un PDP.</span><span class="sxs-lookup"><span data-stu-id="a333a-116">The following illustration shows what the ratings and reviews modules look like on a PDP.</span></span>

![Módulos de clasificaciones y opiniones en un PDP](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> <span data-ttu-id="a333a-118">Para obtener información acerca de cómo optimizar diseños y plantillas PDP de modo que pueda compartir las configuraciones para los módulos de clasificaciones y opiniones entre varios PDP en su sitio de comercio electrónico, consulte [Visión general de plantillas y diseños](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a333a-118">For information about how to optimize PDP templates and layouts so that you can share the configurations for ratings and reviews modules among multiple PDPs on your e-Commerce site, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

<span data-ttu-id="a333a-119">La siguiente ilustración muestra cómo el cuadro de diálogo **Agregar módulo** presenta módulos de calificaciones y opiniones en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a333a-119">The following illustration shows how the **Add module** dialog box presents ratings and reviews modules in Dynamics 365 Commerce.</span></span>
<span data-ttu-id="a333a-120">![Cuadro de diálogo Agregar módulo](media/rnr-eCommerce-pdp-adding-rnr-modules.png)</span><span class="sxs-lookup"><span data-stu-id="a333a-120">![Add module dialog box](media/rnr-eCommerce-pdp-adding-rnr-modules.png)</span></span>

### <a name="write-review-module"></a><span data-ttu-id="a333a-121">Módulo Escribir opinión</span><span class="sxs-lookup"><span data-stu-id="a333a-121">Write review module</span></span>

<span data-ttu-id="a333a-122">El módulo Escribir opinión incluye un botón **Escribir una opinión** que permite a los usuarios iniciar sesión, asigne una clasificación y escribir una opinión de un producto.</span><span class="sxs-lookup"><span data-stu-id="a333a-122">The write review module includes a **Write a review** button that lets users sign in, assign a rating, and write a review of a product.</span></span> <span data-ttu-id="a333a-123">Este módulo también permite a los usuarios editar una clasificación u opinión que han enviado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a333a-123">This module also lets users edit a rating or review that they previously submitted.</span></span> <span data-ttu-id="a333a-124">Este módulo aparece normalmente encima de los módulos de lista de opiniones de productos e histograma de clasificaciones en un PDP.</span><span class="sxs-lookup"><span data-stu-id="a333a-124">This module typically appears above the ratings histogram and product reviews list modules on a PDP.</span></span>
<span data-ttu-id="a333a-125">La ilustración siguiente muestra el cuadro de diálogo **Escribir una opinión** que aparece cuando un cliente selecciona **Escribir una opinión**.</span><span class="sxs-lookup"><span data-stu-id="a333a-125">The following illustration shows the **Write a review** dialog box that appears when a customer selects **Write a review**.</span></span> <span data-ttu-id="a333a-126">El cliente puede usar este cuadro de diálogo para enviar una clasificación y una revisión.</span><span class="sxs-lookup"><span data-stu-id="a333a-126">The customer can use this dialog box to submit a rating and a review.</span></span>
<span data-ttu-id="a333a-127">![Escribir un cuadro de diálogo de opinión](media/rnr-eCommerce-write-review-module.png) En la tabla siguiente se muestra la propiedad del módulo de escribir una opinión que tiene que configurarse en la herramienta de creación.</span><span class="sxs-lookup"><span data-stu-id="a333a-127">![Write a review dialog box](media/rnr-eCommerce-write-review-module.png) The following table shows the write review module property that needs to be configured in the authoring tool.</span></span>
| <span data-ttu-id="a333a-128">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="a333a-128">Property name</span></span> | <span data-ttu-id="a333a-129">Valor</span><span class="sxs-lookup"><span data-stu-id="a333a-129">Value</span></span>        | <span data-ttu-id="a333a-130">Descripción de la propiedad</span><span class="sxs-lookup"><span data-stu-id="a333a-130">Property description</span></span>                 |
|---------------|--------------|--------------------------------------|
| <span data-ttu-id="a333a-131">Nombre</span><span class="sxs-lookup"><span data-stu-id="a333a-131">Name</span></span>          | <span data-ttu-id="a333a-132">Escribir opinión</span><span class="sxs-lookup"><span data-stu-id="a333a-132">Write review</span></span> | <span data-ttu-id="a333a-133">El nombre del módulo de escribir opinión.</span><span class="sxs-lookup"><span data-stu-id="a333a-133">The name of the write review module.</span></span> |

### <a name="ratings-histogram-module"></a><span data-ttu-id="a333a-134">Módulo de histograma de clasificaciones</span><span class="sxs-lookup"><span data-stu-id="a333a-134">Ratings histogram module</span></span>

<span data-ttu-id="a333a-135">El módulo del histograma de clasificaciones muestra un histograma de clasificaciones.</span><span class="sxs-lookup"><span data-stu-id="a333a-135">The ratings histogram module shows a ratings histogram.</span></span> <span data-ttu-id="a333a-136">Este módulo normalmente aparece entre el módulo de escribir opinión y el módulo de lista de opiniones de productos en un PDP.</span><span class="sxs-lookup"><span data-stu-id="a333a-136">This module typically appears between the write review module and the product reviews list module on a PDP.</span></span>
<span data-ttu-id="a333a-137">El módulo del histograma de calificaciones no requiere ninguna configuración.</span><span class="sxs-lookup"><span data-stu-id="a333a-137">The ratings histogram module requires no configuration.</span></span> <span data-ttu-id="a333a-138">Solo tiene que agregar el módulo en la plantilla PDP.</span><span class="sxs-lookup"><span data-stu-id="a333a-138">You just have to add the module in the PDP template.</span></span> <span data-ttu-id="a333a-139">En las siguientes ilustraciones se muestran el aspecto de una plantilla PDP en Dynamics 365 Commerce cuando se configuran los módulos de clasificaciones y opiniones para su visualización en PDP.</span><span class="sxs-lookup"><span data-stu-id="a333a-139">The following illustrations shows what a PDP template looks like in Dynamics 365 Commerce when ratings and reviews modules are configured for display on PDPs.</span></span>
<span data-ttu-id="a333a-140">![Plantilla PDP cuando se configuran las clasificaciones y las opiniones para su visualización en PDP](media/rnr-eCommerce-pdp-reviews-modules.png)</span><span class="sxs-lookup"><span data-stu-id="a333a-140">![PDP template when ratings and reviews are configured for display on PDPs](media/rnr-eCommerce-pdp-reviews-modules.png)</span></span>

### <a name="product-reviews-list-module"></a><span data-ttu-id="a333a-141">Módulo de lista de opiniones de productos</span><span class="sxs-lookup"><span data-stu-id="a333a-141">Product reviews list module</span></span>

<span data-ttu-id="a333a-142">El módulo de lista de opiniones de productos muestra una lista de opiniones de productos junto con las opciones de ordenación, filtrado y paginación.</span><span class="sxs-lookup"><span data-stu-id="a333a-142">The product reviews list module shows a list of product reviews together with sort, filter, and pagination options.</span></span> <span data-ttu-id="a333a-143">Este módulo aparece normalmente después del módulo del histograma de clasificaciones en un PDP.</span><span class="sxs-lookup"><span data-stu-id="a333a-143">This module typically appears after the ratings histogram module on a PDP.</span></span>
<span data-ttu-id="a333a-144">En la tabla siguiente se muestra las propiedades del módulo de lista de opiniones de productos que se tienen que configurar en la herramienta de creación.</span><span class="sxs-lookup"><span data-stu-id="a333a-144">The following table shows the product reviews list module properties that need to be configured in the authoring tool.</span></span>

| <span data-ttu-id="a333a-145">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="a333a-145">Property name</span></span>              | <span data-ttu-id="a333a-146">Valor</span><span class="sxs-lookup"><span data-stu-id="a333a-146">Value</span></span> | <span data-ttu-id="a333a-147">Descripción de la propiedad</span><span class="sxs-lookup"><span data-stu-id="a333a-147">Property description</span></span> |
|----------------------------|-------| ---------------------|
| <span data-ttu-id="a333a-148">Opiniones que se muestran en cada página</span><span class="sxs-lookup"><span data-stu-id="a333a-148">Reviews shown on each page</span></span> | <span data-ttu-id="a333a-149">10</span><span class="sxs-lookup"><span data-stu-id="a333a-149">10</span></span>    | <span data-ttu-id="a333a-150">El número de opiniones que se deben mostrar al mismo tiempo en un PDP.</span><span class="sxs-lookup"><span data-stu-id="a333a-150">The number of reviews that should be shown at a time on a PDP.</span></span> <span data-ttu-id="a333a-151">Se incluyen los botones **Siguiente** y **Anterior**, de modo que los usuarios puedan moverse por las páginas de opiniones.</span><span class="sxs-lookup"><span data-stu-id="a333a-151">**Next** and **Previous** buttons are included, so that users can move through the pages of reviews.</span></span> |

#### <a name="ratings-histogram--summary-view"></a><span data-ttu-id="a333a-152">Histograma de clasificaciones: vista de resumen</span><span class="sxs-lookup"><span data-stu-id="a333a-152">Ratings histogram – Summary view</span></span>

<span data-ttu-id="a333a-153">El módulo de lista de opiniones de productos incluye una franja donde puede agregar un módulo de histograma de clasificaciones.</span><span class="sxs-lookup"><span data-stu-id="a333a-153">The product reviews list module includes a slot where you can add a ratings histogram module.</span></span> <span data-ttu-id="a333a-154">La ilustración siguiente muestra cómo puede agregar un módulo de histograma de clasificaciones en el módulo de la lista de opiniones de productos en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a333a-154">The following illustration shows how you can add a ratings histogram module in the product reviews list module in Dynamics 365 Commerce.</span></span>

![Adición de un módulo de histograma de clasificaciones en un módulo de lista de opiniones de productos](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="additional-resources"></a><span data-ttu-id="a333a-156">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a333a-156">Additional resources</span></span>

[<span data-ttu-id="a333a-157">Visión general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="a333a-157">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="a333a-158">Módulo de contenedor</span><span class="sxs-lookup"><span data-stu-id="a333a-158">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="a333a-159">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="a333a-159">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="a333a-160">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="a333a-160">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="a333a-161">Módulo de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="a333a-161">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="a333a-162">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="a333a-162">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="a333a-163">Módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="a333a-163">Footer module</span></span>](author-footer-module.md)
