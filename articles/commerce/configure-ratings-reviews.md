---
title: Configurar clasificaciones y revisiones
description: Este tema describe cómo configurar el sitio de comercio electrónico para mostrar clasificaciones y opiniones de clientes en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 02/17/2020
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
ms.openlocfilehash: edd2082b5d2cafcb955f8e3c7762bcba523ac479
ms.sourcegitcommit: 0dace221e8874021dd212271567666f717d39793
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2020
ms.locfileid: "3071575"
---
# <a name="configure-ratings-and-reviews"></a><span data-ttu-id="2b587-103">Configurar clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="2b587-103">Configure ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2b587-104">Este tema describe cómo configurar el sitio de comercio electrónico para mostrar clasificaciones y opiniones de clientes en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2b587-104">This topic describes how to configure your e-Commerce site to show customer ratings and reviews in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="2b587-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="2b587-105">Overview</span></span>

<span data-ttu-id="2b587-106">Las clasificaciones y opiniones en sitios web de comercio electrónico ayudan a los clientes a obtener información acerca de los productos antes de tomar una decisión de compra, al mostrarles qué piensan otros clientes acerca de esos productos.</span><span class="sxs-lookup"><span data-stu-id="2b587-106">Ratings and reviews on e-Commerce websites help customers learn about products before they make a purchase decision by showing them what other customers think about those products.</span></span> <span data-ttu-id="2b587-107">Para los sitios web de comercio electrónicos, las clasificaciones y opiniones son también un mecanismo para obtener los comentarios de los clientes acerca de los productos.</span><span class="sxs-lookup"><span data-stu-id="2b587-107">For e-Commerce websites, ratings and reviews are also a mechanism for collecting customer feedback about products.</span></span> 

## <a name="configure-a-site-to-show-ratings-and-reviews"></a><span data-ttu-id="2b587-108">Configurar un sitio para mostrar clasificaciones y opiniones</span><span class="sxs-lookup"><span data-stu-id="2b587-108">Configure a site to show ratings and reviews</span></span>

<span data-ttu-id="2b587-109">Los valores de configuración para clasificaciones y opiniones, como el id. de inquilino, la longitud del texto de opinión y la longitud del título de la opinión, se configuran en el nivel de sitio.</span><span class="sxs-lookup"><span data-stu-id="2b587-109">Configuration values for ratings and reviews, such as the tenant ID, review text length, and review title length, are configured at the site level.</span></span> 

<span data-ttu-id="2b587-110">Para configurar un sitio para que muestre clasificaciones y opiniones, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2b587-110">To configure a site to show ratings and reviews, follow these steps.</span></span> 

1. <span data-ttu-id="2b587-111">Vaya a **Inicio \> Sitios**.</span><span class="sxs-lookup"><span data-stu-id="2b587-111">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="2b587-112">Seleccione el nombre de su sitio.</span><span class="sxs-lookup"><span data-stu-id="2b587-112">Select the name of your site.</span></span> 
1. <span data-ttu-id="2b587-113">Ir **Configuraciones del sitio \> Extensiones**.</span><span class="sxs-lookup"><span data-stu-id="2b587-113">Go to **Site settings \> Extensions**.</span></span> 
1. <span data-ttu-id="2b587-114">En el campo **Longitud máxima del texto de la opinión**, especifique el número máximo de caracteres que puede tener el texto de la opinión (por ejemplo, **1000**).</span><span class="sxs-lookup"><span data-stu-id="2b587-114">In the **Review text max length** field, enter the maximum number of characters that review text can have (for example, **1000**).</span></span> 
1. <span data-ttu-id="2b587-115">En el campo **Longitud máxima del título de la opinión**, especifique el número máximo de caracteres que pueden tener los títulos de opinión (por ejemplo, **55**).</span><span class="sxs-lookup"><span data-stu-id="2b587-115">In the **Review title max length** field, enter the maximum number of characters that review titles can have (for example, **55**).</span></span> 
1. <span data-ttu-id="2b587-116">Seleccione **Guardar y publicar**.</span><span class="sxs-lookup"><span data-stu-id="2b587-116">Select **Save and Publish**.</span></span> 

<span data-ttu-id="2b587-117">La ilustración siguiente muestra el aspecto de esta configuración en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2b587-117">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Configuración de un sitio para mostrar clasificaciones y opiniones](media/rnr-eCommerce-site-appsettings.png)

## <a name="link-a-product-rating-to-the-reviews-section-of-a-pdp"></a><span data-ttu-id="2b587-119">Vincular una clasificación de producto a la sección de revisiones de un PDP</span><span class="sxs-lookup"><span data-stu-id="2b587-119">Link a product rating to the Reviews section of a PDP</span></span>

<span data-ttu-id="2b587-120">Una clasificación de producto se muestra debajo del título del producto en la parte superior del PDP.</span><span class="sxs-lookup"><span data-stu-id="2b587-120">A product rating is shown below the product title at the top of PDP.</span></span> <span data-ttu-id="2b587-121">La clasificación del producto se puede configurar para que esté vinculada a la sección **Revisiones** del mismo PDP.</span><span class="sxs-lookup"><span data-stu-id="2b587-121">The product rating can be configured so that it's linked to the **Reviews** section of the same PDP.</span></span> 

<span data-ttu-id="2b587-122">Para vincular una clasificación de producto a la sección **Revisiones** del PDP, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2b587-122">To link a product rating to the **Reviews** section of the PDP, follow these steps.</span></span>

1. <span data-ttu-id="2b587-123">Abra la plantilla PDP.</span><span class="sxs-lookup"><span data-stu-id="2b587-123">Open the PDP template.</span></span> 
1. <span data-ttu-id="2b587-124">Vaya a **Configuración del módulo de contenedor de cuadro de compra**.</span><span class="sxs-lookup"><span data-stu-id="2b587-124">Go to **Buy box container module settings**.</span></span>
1. <span data-ttu-id="2b587-125">En **Cuadro de compra**, seleccione **Clasificaciones de producto** y la casilla **Módulo de vincular el clic para opiniones completas**.</span><span class="sxs-lookup"><span data-stu-id="2b587-125">Under **Buy box**, select **Product ratings**, and then select the **Link the click to full reviews module** check box.</span></span>

<span data-ttu-id="2b587-126">La ilustración siguiente muestra el aspecto de esta configuración en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2b587-126">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Vinculación de una clasificación de producto a la sección de revisiones de un PDP](media/rnr-eCommerce-buy-box-rating-summary.png)

## <a name="configure-the-link-for-the-privacy-and-policy-page"></a><span data-ttu-id="2b587-128">Configurar el vínculo para la página de directiva y privacidad</span><span class="sxs-lookup"><span data-stu-id="2b587-128">Configure the link for the privacy and policy page</span></span>

<span data-ttu-id="2b587-129">Para configurar el vínculo para la página de directiva y privacidad, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2b587-129">To configure the link for the privacy and policy page, follow these steps.</span></span>

1. <span data-ttu-id="2b587-130">Vaya a **Inicio \> Sitios**.</span><span class="sxs-lookup"><span data-stu-id="2b587-130">Go to **Home \> Sites**.</span></span>
1. <span data-ttu-id="2b587-131">Seleccione el nombre de su sitio.</span><span class="sxs-lookup"><span data-stu-id="2b587-131">Select the name of your site.</span></span> 
1. <span data-ttu-id="2b587-132">Ir **Configuraciones del sitio \> Extensiones**.</span><span class="sxs-lookup"><span data-stu-id="2b587-132">Go to **Site settings \> Extensions**.</span></span>
1. <span data-ttu-id="2b587-133">En la pestaña **Rutas**, en **Directiva y privacidad RNR**, seleccione **Agregar un vínculo**.</span><span class="sxs-lookup"><span data-stu-id="2b587-133">On the **Routes** tab, under **RNR Privacy and Policy**, select **Add a link**.</span></span> <span data-ttu-id="2b587-134">Si ya se ha introducido un vínculo, y desea reemplazarlo, selecciónelo.</span><span class="sxs-lookup"><span data-stu-id="2b587-134">If a link is already entered, and you want to replace it, select the link.</span></span> 
1. <span data-ttu-id="2b587-135">En el cuadro de diálogo **Agregar un vínculo**, seleccione el vínculo para la página de directiva y privacidad y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2b587-135">In the **Add a link** dialog box, select the link for the privacy and policy page, and then select **OK**.</span></span> 
1. <span data-ttu-id="2b587-136">Seleccione **Guardar y publicar**.</span><span class="sxs-lookup"><span data-stu-id="2b587-136">Select **Save and Publish**.</span></span> 

<span data-ttu-id="2b587-137">La ilustración siguiente muestra el aspecto de esta configuración en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2b587-137">The following illustration shows what this configuration looks like in Dynamics 365 Commerce.</span></span>

![Configuración del vínculo para la página de directiva y privacidad](media/rnr-eCommerce-rnr-privacy-policy-link.png)

## <a name="configure-ratings-and-reviews-modules-on-product-details-pages"></a><span data-ttu-id="2b587-139">Configure los módulos de valoraciones y reseñas en las páginas de detalles del producto</span><span class="sxs-lookup"><span data-stu-id="2b587-139">Configure ratings and reviews modules on product details pages</span></span>

<span data-ttu-id="2b587-140">Para obtener información sobre la configuración de módulos de valoraciones y reseñas en las páginas de detalles del producto, consulte [Módulos de valoraciones y comentarios](ratings-reviews-modules.md).</span><span class="sxs-lookup"><span data-stu-id="2b587-140">For information on configuring ratings and reviews modules on product details pages, see [Ratings and reviews modules](ratings-reviews-modules.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2b587-141">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2b587-141">Additional resources</span></span>

[<span data-ttu-id="2b587-142">Visión general de clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="2b587-142">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="2b587-143">Optar por usar clasificaciones y revisiones de usuario</span><span class="sxs-lookup"><span data-stu-id="2b587-143">Opt in to use ratings and reviews</span></span>](opt-in-ratings-reviews.md)

[<span data-ttu-id="2b587-144">Administrar clasificaciones y revisiones</span><span class="sxs-lookup"><span data-stu-id="2b587-144">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="2b587-145">Configure los módulos de valoraciones y reseñas en las páginas de detalles del producto</span><span class="sxs-lookup"><span data-stu-id="2b587-145">Configure ratings and reviews modules on product details pages</span></span>](ratings-reviews-modules.md)

[<span data-ttu-id="2b587-146">Sincronizar clasificaciones de productos en Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="2b587-146">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
