---
title: Módulo de encabezado
description: En este tema se tratan los módulos de encabezado y se describe como crear encabezados de página en Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: ''
ms.openlocfilehash: efadd19681bbb21ea5b2b469e55bc6f4b0535046
ms.sourcegitcommit: 34e543e807ac8790597f522fe3b4f0266cf4ee56
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/24/2020
ms.locfileid: "3025701"
---
# <a name="header-module"></a><span data-ttu-id="2b6ff-103">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="2b6ff-103">Header module</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="2b6ff-104">En este tema se tratan los módulos de encabezado y se describe como crear encabezados de página en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="2b6ff-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="2b6ff-105">Overview</span></span>

<span data-ttu-id="2b6ff-106">En Dynamics 365 Commerce, un encabezado de página consta de varios módulos, como los de encabezado, menú de navegación, búsqueda, banner promocional y consentimiento de cookies.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-106">In Dynamics 365 Commerce, a page header comprises multiple modules, such as the header, navigation menu, search, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="2b6ff-107">El módulo de encabezado incluye un logotipo del sitio, vínculos a la jerarquía de navegación, vínculos a otras páginas en el sitio, un símbolo de carro, un símbolo de lista de deseos, opciones de inicio de sesión y la barra de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart symbol, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="2b6ff-108">Un módulo de encabezado se optimiza automáticamente para el dispositivo en el que se está viendo el sitio (es decir, un dispositivo de escritorio o un dispositivo móvil).</span><span class="sxs-lookup"><span data-stu-id="2b6ff-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="2b6ff-109">Por ejemplo, en un dispositivo móvil, la barra de navegación se contrae en un botón **Menú** (que a veces se denomina *menú de hamburguesa*).</span><span class="sxs-lookup"><span data-stu-id="2b6ff-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

## <a name="properties-of-a-header-module"></a><span data-ttu-id="2b6ff-110">Propiedades de un módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="2b6ff-110">Properties of a header module</span></span>

<span data-ttu-id="2b6ff-111">Un módulo de encabezado tiene propiedades de **Imagen de logotipo**, **Vínculo de logotipo** y **Mis vínculos de cuenta**.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-111">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="2b6ff-112">Las propiedades **Imagen de logotipo** y **Vínculo de logotipo** se usan para definir un logotipo en la página.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-112">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="2b6ff-113">Para obtener más información, consulte [Agregar un logotipo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="2b6ff-113">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="2b6ff-114">La propiedad **Mis vínculos de cuenta** se puede utilizar para definir las páginas de la cuenta para las que el propietario del sitio desea mostrar vínculos rápidos en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-114">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="2b6ff-115">Módulos disponibles en un módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="2b6ff-115">Modules that are available in a header module</span></span>

<span data-ttu-id="2b6ff-116">Los módulos siguientes se pueden usar en un módulo de encabezado:</span><span class="sxs-lookup"><span data-stu-id="2b6ff-116">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="2b6ff-117">**Menú de navegación**: El menú de navegación representa la jerarquía de navegación de canales y otros vínculos de navegación estáticos.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-117">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="2b6ff-118">La jerarquía de navegación de canales se puede configurar en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-118">The channel navigation hierarchy can be configured in Dynamics 365 Commerce.</span></span> <span data-ttu-id="2b6ff-119">El menú de navegación tiene una propiedad **Origen de navegación** que se utiliza para especificar los elementos del menú de navegación de Retail Server y elementos menú estáticos como un origen.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-119">The navigation menu has a **Navigation Source** property that is used to specify Retail Server navigation menu items and static menu items as a source.</span></span> <span data-ttu-id="2b6ff-120">Si los elementos de menú estáticos se especifican como un origen, se pueden proporcionar vínculos relativos a otras páginas en el sitio.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-120">If static menu items are specified as a source, relative links to other pages on the site can be provided.</span></span> <span data-ttu-id="2b6ff-121">Los artículos configurados aparecerán como navegación de encabezado.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-121">Configured items then appear as header navigation.</span></span> 
- <span data-ttu-id="2b6ff-122">**Búsqueda**: el módulo de búsqueda permite a los usuarios especificar términos de búsqueda para buscar productos.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-122">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="2b6ff-123">La dirección URL de la página de búsqueda predeterminada y los parámetros de consulta de búsqueda deben especificarse en **Valores de configuración del sitio \> Extensiones**.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-123">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="2b6ff-124">El módulo de búsqueda tiene propiedades que le permiten suprimir el botón de búsqueda o la etiqueta según lo requiera.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-124">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="2b6ff-125">El módulo de búsqueda también admite opciones de sugerencia automática, como resultados de búsqueda de productos, palabras clave y categorías.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-125">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

## <a name="create-a-header-module-for-a-page"></a><span data-ttu-id="2b6ff-126">Crear un módulo de encabezado para una página</span><span class="sxs-lookup"><span data-stu-id="2b6ff-126">Create a header module for a page</span></span>

<span data-ttu-id="2b6ff-127">Para crear un módulo de encabezado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-127">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="2b6ff-128">Cree un fragmento llamado **Fragmento de encabezado** y agréguele un módulo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-128">Create a fragment that is named **Header fragment**, and add a container module to it.</span></span>
1. <span data-ttu-id="2b6ff-129">En el panel de propiedades para el módulo de contenedor, establezca la propiedad **Ancho** en **Rellenar contenedor**.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-129">In the property pane for the container module, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="2b6ff-130">Agregue un banner promocional y módulos de consentimiento de cookies al módulo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-130">Add promo banner and cookie consent modules to the container module.</span></span>
1. <span data-ttu-id="2b6ff-131">Agregue otro módulo de contenedor al fragmento y establezca la propiedad **Ancho** en **Rellenar contenedor**.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-131">Add another container module to the fragment, and set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="2b6ff-132">Agregue un módulo de encabezado al segundo módulo de contenedor.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-132">Add a header module to the second container module.</span></span>
1. <span data-ttu-id="2b6ff-133">En la franja **Menú de navegación** del módulo de encabezado, agregue un módulo de menú de navegación.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-133">In the **Navigation menu** slot of the header module, add a navigation menu module.</span></span> 
1. <span data-ttu-id="2b6ff-134">En el panel de propiedades del módulo del menú de navegación, configure las propiedades del módulo del menú de navegación.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-134">In the property pane for the navigation menu module, configure the properties of the navigation menu module.</span></span>
1. <span data-ttu-id="2b6ff-135">En la franja **Buscar** del módulo de encabezado, agregue un módulo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-135">In the **Search** slot of the header module, add a search module.</span></span> 
1. <span data-ttu-id="2b6ff-136">En el panel de propiedades del módulo de búsqueda, configure las propiedades del módulo de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-136">In the property pane for the search module, configure the properties of the search module.</span></span> 
1. <span data-ttu-id="2b6ff-137">Guarde el fragmento de página, termine de editarlo y publíquelo.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-137">Save the page fragment, finish editing it, and publish it.</span></span> 

<span data-ttu-id="2b6ff-138">Para ayudar a garantizar que un encabezado aparece en cada página, siga estos pasos de cada plantilla de página creada para el sitio.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-138">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="2b6ff-139">En la franja **Principal** de la página predeterminada, agregue al encabezado el fragmento de página de encabezado que contiene el módulo de encabezado.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-139">In the **Main** slot of the default page, add the header page fragment that contains the header module to the header.</span></span>
1. <span data-ttu-id="2b6ff-140">Guarde la plantilla, termine de editarla y publíquela.</span><span class="sxs-lookup"><span data-stu-id="2b6ff-140">Save the template, finish editing it, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2b6ff-141">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2b6ff-141">Additional resources</span></span>

[<span data-ttu-id="2b6ff-142">Visión general de kit de inicio</span><span class="sxs-lookup"><span data-stu-id="2b6ff-142">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="2b6ff-143">Módulo Contenedor</span><span class="sxs-lookup"><span data-stu-id="2b6ff-143">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="2b6ff-144">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="2b6ff-144">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="2b6ff-145">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="2b6ff-145">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="2b6ff-146">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="2b6ff-146">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="2b6ff-147">Módulo de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="2b6ff-147">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="2b6ff-148">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="2b6ff-148">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="2b6ff-149">Módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="2b6ff-149">Footer module</span></span>](author-footer-module.md)
