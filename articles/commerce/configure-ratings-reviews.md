---
title: Configurar clasificaciones y revisiones
description: Este tema describe cómo configurar el sitio de comercio electrónico para mostrar clasificaciones y opiniones de clientes en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 0612b32e7751b32ad851f627a53bce2ac491870f
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770490"
---
# <a name="configure-ratings-and-reviews"></a><span data-ttu-id="bca7e-103">Configurar clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="bca7e-103">Configure ratings and reviews</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="bca7e-104">Este tema describe cómo configurar el sitio de comercio electrónico para mostrar clasificaciones y opiniones de clientes en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bca7e-104">This topic describes how to configure your e-Commerce site to show customer ratings and reviews in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="bca7e-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="bca7e-105">Overview</span></span>

<span data-ttu-id="bca7e-106">Las clasificaciones y opiniones en sitios web de comercio electrónico ayudan a los clientes a obtener información acerca de los productos antes de tomar una decisión de compra, al mostrarles qué piensan otros clientes acerca de esos productos.</span><span class="sxs-lookup"><span data-stu-id="bca7e-106">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision, by showing them what other customers think about those products.</span></span> <span data-ttu-id="bca7e-107">Para los sitios web de comercio electrónicos, las clasificaciones y opiniones son también un mecanismo para obtener los comentarios de los clientes acerca de los productos.</span><span class="sxs-lookup"><span data-stu-id="bca7e-107">For e-Commerce websites, ratings and reviews are also a mechanism for collecting customer feedback about products.</span></span> 

<span data-ttu-id="bca7e-108">Las clasificaciones se muestran en las páginas de lista de productos, páginas de lista de categorías, páginas de resultados de la búsqueda y otras páginas del sitio.</span><span class="sxs-lookup"><span data-stu-id="bca7e-108">Ratings are shown on product list pages, category list pages, search results pages, and other site pages.</span></span> <span data-ttu-id="bca7e-109">Las histogramas de clasificaciones y revisiones de productos se muestran en las páginas de detalles de producto (PDP).</span><span class="sxs-lookup"><span data-stu-id="bca7e-109">Ratings histograms and product reviews are shown on product details pages (PDPs).</span></span> <span data-ttu-id="bca7e-110">Un botón **Escribir una opinión** permite a los clientes enviar clasificaciones y opiniones para un producto.</span><span class="sxs-lookup"><span data-stu-id="bca7e-110">A **Write a review** button lets customers submit ratings and reviews for a product.</span></span>

## <a name="ratings-and-reviews-modules-on-pdps"></a><span data-ttu-id="bca7e-111">Módulos de clasificaciones y opiniones en PDP</span><span class="sxs-lookup"><span data-stu-id="bca7e-111">Ratings and reviews modules on PDPs</span></span> 

<span data-ttu-id="bca7e-112">Tres módulos muestran el resumen de clasificaciones y opiniones en PDP:</span><span class="sxs-lookup"><span data-stu-id="bca7e-112">Three modules show the ratings and reviews summary on PDPs:</span></span>

- <span data-ttu-id="bca7e-113">Módulo Escribir opinión</span><span class="sxs-lookup"><span data-stu-id="bca7e-113">Write review module</span></span>
- <span data-ttu-id="bca7e-114">Módulo de lista de opiniones de productos</span><span class="sxs-lookup"><span data-stu-id="bca7e-114">Product reviews list module</span></span>
- <span data-ttu-id="bca7e-115">Módulo de histograma de clasificaciones</span><span class="sxs-lookup"><span data-stu-id="bca7e-115">Ratings histogram module</span></span>
 
<span data-ttu-id="bca7e-116">La ilustración siguiente muestra el aspecto de los módulos de clasificaciones y opiniones en un PDP.</span><span class="sxs-lookup"><span data-stu-id="bca7e-116">The following illustration shows what the ratings and reviews modules look like on a PDP.</span></span>

![Módulos de clasificaciones y opiniones en un PDP](media/rnr-eCommerce-pdp-reviews-modules_design.png)

> [!TIP] 
> <span data-ttu-id="bca7e-118">Para obtener información acerca de cómo optimizar diseños y plantillas PDP de modo que pueda compartir las configuraciones para los módulos de clasificaciones y opiniones entre varios PDP en su sitio de comercio electrónico, consulte [Visión general de plantillas y diseños](templates-layouts-overview.md).</span><span class="sxs-lookup"><span data-stu-id="bca7e-118">For information about how to optimize PDP templates and layouts so that you can share the configurations for ratings and reviews modules among multiple PDPs on your e-Commerce site, see [Templates and layouts overview](templates-layouts-overview.md).</span></span>

<span data-ttu-id="bca7e-119">La siguiente ilustración muestra cómo el cuadro de diálogo **Agregar módulo** presenta módulos de calificaciones y opiniones en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bca7e-119">The following illustration shows how the **Add module** dialog box presents ratings and reviews modules in Dynamics 365 Commerce.</span></span>

![Cuadro de diálogo Agregar módulo](media/rnr-eCommerce-pdp-adding-rnr-modules.png)

### <a name="write-review-module"></a><span data-ttu-id="bca7e-121">Módulo Escribir opinión</span><span class="sxs-lookup"><span data-stu-id="bca7e-121">Write review module</span></span>

<span data-ttu-id="bca7e-122">El módulo Escribir opinión incluye un botón **Escribir una opinión** que permite a los usuarios iniciar sesión, asigne una clasificación y escribir una opinión de un producto.</span><span class="sxs-lookup"><span data-stu-id="bca7e-122">The write review module includes a **Write a review** button that lets users sign in, assign a rating, and write a review of a product.</span></span> <span data-ttu-id="bca7e-123">Este módulo también permite a los usuarios editar una clasificación u opinión que han enviado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="bca7e-123">This module also lets users edit a rating or review that they previously submitted.</span></span> <span data-ttu-id="bca7e-124">Este módulo aparece normalmente encima de los módulos de lista de opiniones de productos e histograma de clasificaciones en un PDP.</span><span class="sxs-lookup"><span data-stu-id="bca7e-124">This module typically appears above the ratings histogram and product reviews list modules on a PDP.</span></span>

<span data-ttu-id="bca7e-125">La ilustración siguiente muestra el cuadro de diálogo **Escribir una opinión** que aparece cuando un cliente selecciona **Escribir una opinión**.</span><span class="sxs-lookup"><span data-stu-id="bca7e-125">The following illustration shows the **Write a review** dialog box that appears when a customer selects **Write a review**.</span></span> <span data-ttu-id="bca7e-126">El cliente puede usar este cuadro de diálogo para enviar una clasificación y una revisión.</span><span class="sxs-lookup"><span data-stu-id="bca7e-126">The customer can use this dialog box to submit a rating and a review.</span></span>

![Cuadro de diálogo Escribir una opinión](media/rnr-eCommerce-write-review-module.png)

<span data-ttu-id="bca7e-128">En la tabla siguiente se muestra la propiedad del módulo de escribir una opinión que tiene que configurarse en la herramienta de creación.</span><span class="sxs-lookup"><span data-stu-id="bca7e-128">The following table shows the write review module property that needs to be configured in the authoring tool.</span></span>

| <span data-ttu-id="bca7e-129">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="bca7e-129">Property name</span></span> | <span data-ttu-id="bca7e-130">Valor</span><span class="sxs-lookup"><span data-stu-id="bca7e-130">Value</span></span>        | <span data-ttu-id="bca7e-131">Descripción de la propiedad</span><span class="sxs-lookup"><span data-stu-id="bca7e-131">Property description</span></span>                 |
|---------------|--------------|--------------------------------------|
| <span data-ttu-id="bca7e-132">Nombre</span><span class="sxs-lookup"><span data-stu-id="bca7e-132">Name</span></span>          | <span data-ttu-id="bca7e-133">Escribir opinión</span><span class="sxs-lookup"><span data-stu-id="bca7e-133">Write review</span></span> | <span data-ttu-id="bca7e-134">El nombre del módulo de escribir opinión.</span><span class="sxs-lookup"><span data-stu-id="bca7e-134">The name of the write review module.</span></span> |

### <a name="ratings-histogram-module"></a><span data-ttu-id="bca7e-135">Módulo de histograma de clasificaciones</span><span class="sxs-lookup"><span data-stu-id="bca7e-135">Ratings histogram module</span></span>

<span data-ttu-id="bca7e-136">El módulo del histograma de clasificaciones muestra un histograma de clasificaciones.</span><span class="sxs-lookup"><span data-stu-id="bca7e-136">The ratings histogram module shows a ratings histogram.</span></span> <span data-ttu-id="bca7e-137">Este módulo normalmente aparece entre el módulo de escribir opinión y el módulo de lista de opiniones de productos en un PDP.</span><span class="sxs-lookup"><span data-stu-id="bca7e-137">This module typically appears between the write review module and the product reviews list module on a PDP.</span></span>

<span data-ttu-id="bca7e-138">El módulo del histograma de calificaciones no requiere ninguna configuración.</span><span class="sxs-lookup"><span data-stu-id="bca7e-138">The ratings histogram module requires no configuration.</span></span> <span data-ttu-id="bca7e-139">Solo tiene que agregar el módulo en la plantilla PDP.</span><span class="sxs-lookup"><span data-stu-id="bca7e-139">You just have to add the module in the PDP template.</span></span> 

<span data-ttu-id="bca7e-140">En las siguientes ilustraciones se muestran el aspecto de una plantilla PDP en Dynamics 365 Commerce cuando se configuran los módulos de clasificaciones y opiniones para su visualización en PDP.</span><span class="sxs-lookup"><span data-stu-id="bca7e-140">The following illustrations shows what a PDP template looks like in Dynamics 365 Commerce when ratings and reviews modules are configured for display on PDPs.</span></span>

![Plantilla PDP cuando se configuran las clasificaciones y las opiniones para su visualización en PDP](media/rnr-eCommerce-pdp-reviews-modules.png)

### <a name="product-reviews-list-module"></a><span data-ttu-id="bca7e-142">Módulo de lista de opiniones de productos</span><span class="sxs-lookup"><span data-stu-id="bca7e-142">Product reviews list module</span></span>

<span data-ttu-id="bca7e-143">El módulo de lista de opiniones de productos muestra una lista de opiniones de productos junto con las opciones de ordenación, filtrado y paginación.</span><span class="sxs-lookup"><span data-stu-id="bca7e-143">The product reviews list module shows a list of product reviews together with sort, filter, and pagination options.</span></span> <span data-ttu-id="bca7e-144">Este módulo aparece normalmente después del módulo del histograma de clasificaciones en un PDP.</span><span class="sxs-lookup"><span data-stu-id="bca7e-144">This module typically appears after the ratings histogram module on a PDP.</span></span>

<span data-ttu-id="bca7e-145">En la tabla siguiente se muestra las propiedades del módulo de lista de opiniones de productos que se tienen que configurar en la herramienta de creación.</span><span class="sxs-lookup"><span data-stu-id="bca7e-145">The following table shows the product reviews list module properties that need to be configured in the authoring tool.</span></span>

| <span data-ttu-id="bca7e-146">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="bca7e-146">Property name</span></span>              | <span data-ttu-id="bca7e-147">Valor</span><span class="sxs-lookup"><span data-stu-id="bca7e-147">Value</span></span> | <span data-ttu-id="bca7e-148">Descripción de la propiedad</span><span class="sxs-lookup"><span data-stu-id="bca7e-148">Property description</span></span> |
|----------------------------|-------| ---------------------|
| <span data-ttu-id="bca7e-149">Opiniones que se muestran en cada página</span><span class="sxs-lookup"><span data-stu-id="bca7e-149">Reviews shown on each page</span></span> | <span data-ttu-id="bca7e-150">10</span><span class="sxs-lookup"><span data-stu-id="bca7e-150">10</span></span>    | <span data-ttu-id="bca7e-151">El número de opiniones que se deben mostrar al mismo tiempo en un PDP.</span><span class="sxs-lookup"><span data-stu-id="bca7e-151">The number of reviews that should be shown at a time on a PDP.</span></span> <span data-ttu-id="bca7e-152">Se incluyen los botones **Siguiente** y **Anterior**, de modo que los usuarios puedan moverse por las páginas de opiniones.</span><span class="sxs-lookup"><span data-stu-id="bca7e-152">**Next** and **Previous** buttons are included, so that users can move through the pages of reviews.</span></span> |

#### <a name="ratings-histogram--summary-view"></a><span data-ttu-id="bca7e-153">Histograma de clasificaciones: vista de resumen</span><span class="sxs-lookup"><span data-stu-id="bca7e-153">Ratings histogram – Summary view</span></span>

<span data-ttu-id="bca7e-154">El módulo de lista de opiniones de productos incluye una franja donde puede agregar un módulo de histograma de clasificaciones.</span><span class="sxs-lookup"><span data-stu-id="bca7e-154">The product reviews list module includes a slot where you can add a ratings histogram module.</span></span> <span data-ttu-id="bca7e-155">La ilustración siguiente muestra cómo puede agregar un módulo de histograma de clasificaciones en el módulo de la lista de opiniones de productos en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bca7e-155">The following illustration shows how you can add a ratings histogram module in the product reviews list module in Dynamics 365 Commerce.</span></span>

![Adición de un módulo de histograma de clasificaciones en un módulo de lista de opiniones de productos](media/rnr-eCommerce-pdp-rating-histogram-summary.png)

## <a name="configure-a-site-to-show-ratings-and-reviews"></a><span data-ttu-id="bca7e-157">Configurar un sitio para mostrar clasificaciones y opiniones</span><span class="sxs-lookup"><span data-stu-id="bca7e-157">Configure a site to show ratings and reviews</span></span>

<span data-ttu-id="bca7e-158">Los valores de configuración para clasificaciones y opiniones, como el id. de inquilino, la longitud del texto de opinión y la longitud del título de la opinión, se configuran en el nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="bca7e-158">Configuration values for ratings and reviews, such as the tenant ID, review text length, and review title length, are configured at the site level.</span></span> 

<span data-ttu-id="bca7e-159">Para configurar un sitio para que muestre clasificaciones y opiniones, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="bca7e-159">To configure a site to show ratings and reviews, follow these steps.</span></span> 

1. <span data-ttu-id="bca7e-160">Vaya a **Inicio \> Sitios**.</span><span class="sxs-lookup"><span data-stu-id="bca7e-160">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="bca7e-161">Seleccione el nombre de su sitio.</span><span class="sxs-lookup"><span data-stu-id="bca7e-161">Select the name of your site.</span></span> 
1. <span data-ttu-id="bca7e-162">Vaya a **Administración del sitio \> Extensibilidad**.</span><span class="sxs-lookup"><span data-stu-id="bca7e-162">Go to **Site management \> Extensibility**.</span></span> 
1. <span data-ttu-id="bca7e-163">En el campo **Longitud máxima del texto de la opinión**, especifique el número máximo de caracteres que puede tener el texto de la opinión (por ejemplo, **1000**).</span><span class="sxs-lookup"><span data-stu-id="bca7e-163">In the **Review Text Max Length** field, enter the maximum number of characters that review text can have (for example, **1000**).</span></span> 
1. <span data-ttu-id="bca7e-164">En el campo **Longitud máxima del título de la opinión**, especifique el número máximo de caracteres que pueden tener los títulos de opinión (por ejemplo, **55**).</span><span class="sxs-lookup"><span data-stu-id="bca7e-164">In the **Review Title Max Length** field, enter the maximum number of characters that review titles can have (for example, **55**).</span></span> 
1. <span data-ttu-id="bca7e-165">Seleccione **Guardar y publicar**.</span><span class="sxs-lookup"><span data-stu-id="bca7e-165">Select **Save and Publish**.</span></span> 

<span data-ttu-id="bca7e-166">La ilustración siguiente muestra el aspecto de esta configuración en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bca7e-166">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Configuración de un sitio para mostrar clasificaciones y opiniones](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a><span data-ttu-id="bca7e-168">Vincular una clasificación de producto a la sección de revisiones de un PDP</span><span class="sxs-lookup"><span data-stu-id="bca7e-168">Link a product rating to the Reviews section of a PDP</span></span>

<span data-ttu-id="bca7e-169">Una clasificación de producto se muestra debajo del título del producto en la parte superior del PDP.</span><span class="sxs-lookup"><span data-stu-id="bca7e-169">A product rating is shown below the product title at the top of PDP.</span></span> <span data-ttu-id="bca7e-170">La clasificación del producto se puede configurar para que esté vinculada a la sección **Revisiones** del mismo PDP.</span><span class="sxs-lookup"><span data-stu-id="bca7e-170">The product rating can be configured so that it's linked to the **Reviews** section of the same PDP.</span></span> 

<span data-ttu-id="bca7e-171">Para vincular una clasificación de producto a la sección **Revisiones** del PDP, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="bca7e-171">To link a product rating to the **Reviews** section of the PDP, follow these steps.</span></span>

1. <span data-ttu-id="bca7e-172">Abra la plantilla PDP.</span><span class="sxs-lookup"><span data-stu-id="bca7e-172">Open the PDP template.</span></span> 
1. <span data-ttu-id="bca7e-173">Vaya a **Configuración del módulo de contenedor de cuadro de compra**.</span><span class="sxs-lookup"><span data-stu-id="bca7e-173">Go to **Buy box container module settings**.</span></span>
1. <span data-ttu-id="bca7e-174">En **Cuadro de compra**, seleccione **Clasificaciones de producto** y la casilla **Módulo de vincular el clic para opiniones completas**.</span><span class="sxs-lookup"><span data-stu-id="bca7e-174">Under **Buy box**, select **Product ratings**, and then select the **Link the click to full reviews module** check box.</span></span>

<span data-ttu-id="bca7e-175">La ilustración siguiente muestra el aspecto de esta configuración en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bca7e-175">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Vinculación de una clasificación de producto a la sección de revisiones de un PDP](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a><span data-ttu-id="bca7e-177">Configurar el vínculo para la página de directiva y privacidad</span><span class="sxs-lookup"><span data-stu-id="bca7e-177">Configure the link for the privacy and policy page</span></span>

<span data-ttu-id="bca7e-178">Para configurar el vínculo para la página de directiva y privacidad, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="bca7e-178">To configure the link for the privacy and policy page, follow these steps.</span></span>

1. <span data-ttu-id="bca7e-179">Vaya a **Inicio \> Sitios**.</span><span class="sxs-lookup"><span data-stu-id="bca7e-179">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="bca7e-180">Seleccione el nombre de su sitio.</span><span class="sxs-lookup"><span data-stu-id="bca7e-180">Select the name of your site.</span></span> 
1. <span data-ttu-id="bca7e-181">Vaya a **Administración del sitio \> Extensibilidad**.</span><span class="sxs-lookup"><span data-stu-id="bca7e-181">Go to **Site management \> Extensibility**</span></span>
1. <span data-ttu-id="bca7e-182">En la pestaña **Rutas**, en **Directiva y privacidad RNR**, seleccione **Agregar un vínculo**.</span><span class="sxs-lookup"><span data-stu-id="bca7e-182">On the **Routes** tab, under **RNR Privacy and Policy**, select **Add a link**.</span></span> <span data-ttu-id="bca7e-183">Si ya se ha introducido un vínculo, y desea reemplazarlo, selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="bca7e-183">If a link is already entered, and you want to replace it, select the link.</span></span> 
1. <span data-ttu-id="bca7e-184">En el cuadro de diálogo **Agregar un vínculo**, seleccione el vínculo para la página de directiva y privacidad y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="bca7e-184">In the **Add a link** dialog box, select the link for the privacy and policy page, and then select **OK**.</span></span> 
1. <span data-ttu-id="bca7e-185">Seleccione **Guardar y publicar**.</span><span class="sxs-lookup"><span data-stu-id="bca7e-185">Select **Save and Publish**.</span></span> 

<span data-ttu-id="bca7e-186">La ilustración siguiente muestra el aspecto de esta configuración en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="bca7e-186">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Configuración del vínculo para la página de directiva y privacidad](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="additional-resources"></a><span data-ttu-id="bca7e-188">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="bca7e-188">Additional resources</span></span>

[<span data-ttu-id="bca7e-189">Visión general de clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="bca7e-189">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="bca7e-190">Optar por usar clasificaciones y revisiones de usuario</span><span class="sxs-lookup"><span data-stu-id="bca7e-190">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="bca7e-191">Administrar clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="bca7e-191">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="bca7e-192">Sincronizar clasificaciones de productos en Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="bca7e-192">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
