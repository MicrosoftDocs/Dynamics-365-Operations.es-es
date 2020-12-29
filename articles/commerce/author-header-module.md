---
title: Módulo de encabezado
description: En este tema se tratan los módulos de encabezado y se describe como crear encabezados de página en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
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
ms.dyn365.ops.version: ''
ms.openlocfilehash: 52069af5ca2211473d4a096ad850b5be1290bba1
ms.sourcegitcommit: eee3523be26369aecdb36c0143a6ee3dab4b7966
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "4415670"
---
# <a name="header-module"></a><span data-ttu-id="85347-103">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="85347-103">Header module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="85347-104">En este tema se tratan los módulos de encabezado y se describe como crear encabezados de página en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="85347-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="85347-105">Información general</span><span class="sxs-lookup"><span data-stu-id="85347-105">Overview</span></span>

<span data-ttu-id="85347-106">En Dynamics 365 Commerce, un encabezado de página se configura como un fragmento de página que incluye los módulos de encabezado, banner promocional y consentimiento de cookies.</span><span class="sxs-lookup"><span data-stu-id="85347-106">In Dynamics 365 Commerce, a page header is configured as a page fragment that includes the header, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="85347-107">El módulo de encabezado incluye un logotipo del sitio, vínculos a la jerarquía de navegación, vínculos a otras páginas en el sitio, un módulo de icono de carro, un símbolo de lista de deseos, opciones de inicio de sesión y la barra de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="85347-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart icon module, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="85347-108">Un módulo de encabezado se optimiza automáticamente para el dispositivo en el que se está viendo el sitio (es decir, un dispositivo de escritorio o un dispositivo móvil).</span><span class="sxs-lookup"><span data-stu-id="85347-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="85347-109">Por ejemplo, en un dispositivo móvil, la barra de navegación se contrae en un botón **Menú** (que a veces se denomina *menú de hamburguesa*).</span><span class="sxs-lookup"><span data-stu-id="85347-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

<span data-ttu-id="85347-110">La siguiente imagen muestra un ejemplo de un módulo de encabezado en una página de sitio.</span><span class="sxs-lookup"><span data-stu-id="85347-110">The following image shows an example of a header module on a home page.</span></span>

![Ejemplo de módulo de cabecera](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a><span data-ttu-id="85347-112">Propiedades de un módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="85347-112">Properties of a header module</span></span>

<span data-ttu-id="85347-113">Un módulo de encabezado tiene propiedades de **Imagen de logotipo**, **Vínculo de logotipo** y **Mis vínculos de cuenta**.</span><span class="sxs-lookup"><span data-stu-id="85347-113">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="85347-114">Las propiedades **Imagen de logotipo** y **Vínculo de logotipo** se usan para definir un logotipo en la página.</span><span class="sxs-lookup"><span data-stu-id="85347-114">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="85347-115">Para obtener más información, consulte [Agregar un logotipo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="85347-115">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="85347-116">La propiedad **Mis vínculos de cuenta** se puede utilizar para definir las páginas de la cuenta para las que el propietario del sitio desea mostrar vínculos rápidos en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="85347-116">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-within-a-header-module"></a><span data-ttu-id="85347-117">Módulos disponibles en un módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="85347-117">Modules that are available within a header module</span></span>

<span data-ttu-id="85347-118">Los módulos siguientes se pueden usar en un módulo de encabezado:</span><span class="sxs-lookup"><span data-stu-id="85347-118">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="85347-119">**Menú de navegación**: El menú de navegación representa la jerarquía de navegación de canales y otros vínculos de navegación estáticos.</span><span class="sxs-lookup"><span data-stu-id="85347-119">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="85347-120">Para obtener más información, consulte [Módulo del menú de navegación](nav-menu-module.md).</span><span class="sxs-lookup"><span data-stu-id="85347-120">For more information, see [Navigation menu module](nav-menu-module.md).</span></span>

- <span data-ttu-id="85347-121">**Búsqueda**: el módulo de búsqueda permite a los usuarios especificar términos de búsqueda para buscar productos.</span><span class="sxs-lookup"><span data-stu-id="85347-121">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="85347-122">La dirección URL de la página de búsqueda predeterminada y los parámetros de consulta de búsqueda deben especificarse en **Valores de configuración del sitio \> Extensiones**.</span><span class="sxs-lookup"><span data-stu-id="85347-122">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="85347-123">El módulo de búsqueda tiene propiedades que le permiten suprimir el botón de búsqueda o la etiqueta según lo requiera.</span><span class="sxs-lookup"><span data-stu-id="85347-123">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="85347-124">El módulo de búsqueda también admite opciones de sugerencia automática, como resultados de búsqueda de productos, palabras clave y categorías.</span><span class="sxs-lookup"><span data-stu-id="85347-124">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

- <span data-ttu-id="85347-125">**Ícono de carrito** - El módulo de icono de carrito representa el icono de carrito, que muestra la cantidad de artículos en el carrito en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="85347-125">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="85347-126">Para más información, ver [Módulo de icono de carrito](cart-icon-module.md).</span><span class="sxs-lookup"><span data-stu-id="85347-126">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

- <span data-ttu-id="85347-127">**Selector de sitio**: el módulo selector de sitio permite a los usuarios navegar por diferentes sitios predefinidos, según el mercado, las regiones y las configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="85347-127">**Site selector** - The site selector module lets users browse across different predefined sites, based on market, regions, and locales.</span></span> <span data-ttu-id="85347-128">Para obtener más información, consulte [Módulo selector de sitio](site-selector.md).</span><span class="sxs-lookup"><span data-stu-id="85347-128">For more information, see [Site selector module](site-selector.md).</span></span>

- <span data-ttu-id="85347-129">**Selector de tienda**: el módulo selector de tienda se puede incluir en una franja de selector de tienda del módulo de encabezado.</span><span class="sxs-lookup"><span data-stu-id="85347-129">**Store selector** - The store selector module can be included in a header module's store selector slot.</span></span> <span data-ttu-id="85347-130">Permite a los usuarios encontrar tiendas cercanas y navegar por ellas.</span><span class="sxs-lookup"><span data-stu-id="85347-130">It lets users browse and find nearby stores.</span></span> <span data-ttu-id="85347-131">Los usuarios también pueden especificar una tienda preferida.</span><span class="sxs-lookup"><span data-stu-id="85347-131">Users can also specify a preferred store.</span></span> <span data-ttu-id="85347-132">Esa tienda se mostrará en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="85347-132">That store will then be shown in the header.</span></span> <span data-ttu-id="85347-133">Cuando el módulo selector de tienda está incluido en el módulo de encabezado, su propiedad **Modo** debe establecerse en **Buscar tiendas**.</span><span class="sxs-lookup"><span data-stu-id="85347-133">When the store selector module is included in the header module, its **Mode** property must be set to **Find stores**.</span></span> <span data-ttu-id="85347-134">Para obtener más información, consulte [Módulo selector de tienda](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="85347-134">For more information, see [Store selector module](store-selector.md).</span></span>

> [!NOTE]
> - <span data-ttu-id="85347-135">La compatibilidad con el uso del icono de carro en los módulos de encabezado está disponible en Dynamics 365 Commerce 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="85347-135">Support for using the cart icon module in header modules is available in the Dynamics 365 Commerce 10.0.11 release.</span></span>
> - <span data-ttu-id="85347-136">La compatibilidad con el uso del módulo selector de sitio en los módulos de encabezado está disponible en Dynamics 365 Commerce 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="85347-136">Support for using the site selector module in header modules is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>
> - <span data-ttu-id="85347-137">La compatibilidad con el uso del módulo selector de tienda en los módulos de encabezado está disponible en Dynamics 365 Commerce 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="85347-137">Support for using the store selector module in header modules is available in the Dynamics 365 Commerce 10.0.15 release.</span></span>

## <a name="create-a-header-fragment-for-a-page"></a><span data-ttu-id="85347-138">Crear un fragmento de encabezado para una página</span><span class="sxs-lookup"><span data-stu-id="85347-138">Create a header fragment for a page</span></span>

<span data-ttu-id="85347-139">Para crear un fragmento de encabezado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="85347-139">To create a header fragment, follow these steps.</span></span>

1. <span data-ttu-id="85347-140">Vaya a **Fragmentos** y seleccione **Nuevo** para crear un nuevo fragmento.</span><span class="sxs-lookup"><span data-stu-id="85347-140">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="85347-141">En el cuadro de diálogo **Nuevo fragmento**, seleccione el módulo **Contenedor**, especifique un nombre para el fragmento y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="85347-141">In the **New fragment** dialog box, select the **Container** module, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="85347-142">Seleccione el espacio **Contenedor predeterminado** y luego, en el panel de propiedades de la derecha, establezca la propiedad **Anchura** en **Rellenar pantalla**.</span><span class="sxs-lookup"><span data-stu-id="85347-142">Select the **Default container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill Screen**.</span></span>
1. <span data-ttu-id="85347-143">En el espacio **Contenedor predeterminado**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="85347-143">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="85347-144">En el cuadro de diálogo **Agregar módulo**, seleccione los módulos Banner promocional y **Consentimiento de cookies**, **Encabezado** y **Banner promocional** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="85347-144">In the **Add Module** dialog box, select the **Cookie consent**, **Header**, and **Promo banner** modules, and then select **OK**.</span></span>
1. <span data-ttu-id="85347-145">En el panel de propiedades del módulo **Banner promocional**, seleccione **Agregar mensaje** y luego seleccione **Mensaje**.</span><span class="sxs-lookup"><span data-stu-id="85347-145">In the properties pane of the **Promo banner** module, select **Add Message**, and then select **Message**.</span></span>
1. <span data-ttu-id="85347-146">En el cuadro de diálogo **Mensaje**, agregue el texto y los vínculos para el contenido promocional y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="85347-146">In the **Message** dialog box, add text and links for the promotional content, and then select **OK**.</span></span>
1. <span data-ttu-id="85347-147">En el panel de propiedades del módulo **Consentimiento de cookies**, agregue y configure texto y un vínculo a la página de privacidad del sitio.</span><span class="sxs-lookup"><span data-stu-id="85347-147">In the properties pane of the **Cookie consent** module, add and configure text and a link to the site privacy page.</span></span>
1. <span data-ttu-id="85347-148">En el espacio **Menú de navegación** del módulo de encabezado, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="85347-148">In the **Navigation menu** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="85347-149">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Menú de navegación** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="85347-149">In the **Add Module** dialog box, select the **Navigation menu** module, and then select **OK**.</span></span>
1. <span data-ttu-id="85347-150">En el panel de propiedades del módulo del menú de navegación, en **Fuente para el menú de navegación**, seleccione **Retail Server**.</span><span class="sxs-lookup"><span data-stu-id="85347-150">In the property pane for the navigation menu module, under **Source for navigation menu**, select **Retail Server**.</span></span>
1. <span data-ttu-id="85347-151">En el panel de propiedades del módulo del menú de navegación, en **Elementos de menú estáticos**, seleccione **Agregar elemento de menú** y luego seleccione **Elemento de menú**.</span><span class="sxs-lookup"><span data-stu-id="85347-151">In the property pane for the navigation menu module, under **Static menu items**, select **Add Menu item**, and then select **Menu item**.</span></span> 
1. <span data-ttu-id="85347-152">En el cuadro de diálogo **Elemento de menú**, en **Texto del elemento de menú** escriba "Contacto".</span><span class="sxs-lookup"><span data-stu-id="85347-152">In the **Menu item** dialog box, under **Menu Item Text** enter "Contact."</span></span>
1. <span data-ttu-id="85347-153">En el cuadro de diálogo **Elemento de menú**, en **Destino de vínculo de elemento de menú**, seleccione **Agregar un vínculo**.</span><span class="sxs-lookup"><span data-stu-id="85347-153">In the **Menu item** dialog box, under **Menu Item Link target** select **Add a link**.</span></span>
1. <span data-ttu-id="85347-154">En el cuadro de diálogo **Agregar un vínculo**, seleccione la dirección URL para la página "Contacto" del sitio y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="85347-154">In the **Add a link** dialog box, select the URL for the site's "Contact" page, and then select **OK**.</span></span>  
1. <span data-ttu-id="85347-155">En el cuadro de diálogo **Elemento de menú**, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="85347-155">In the **Menu item** dialog box, select **OK**.</span></span>
1. <span data-ttu-id="85347-156">En el espacio **Búsqueda** del módulo de encabezado, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="85347-156">In the **Search** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="85347-157">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Búsqueda** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="85347-157">In the **Add Module** dialog box, select the **Search** module, and then select **OK**.</span></span>
1. <span data-ttu-id="85347-158">En el panel de propiedades del módulo del módulo de búsqueda, configure las propiedades según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="85347-158">In the property pane for the search module, configure the properties as needed.</span></span>
1. <span data-ttu-id="85347-159">En el espacio **Icono de carro** del módulo de encabezado, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="85347-159">In the **Cart icon** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="85347-160">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Icono de carro** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="85347-160">In the **Add Module** dialog box, select the **Cart icon** module, and then select **OK**.</span></span>
1. <span data-ttu-id="85347-161">En el panel de propiedades del módulo del icono de carro, configure las propiedades según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="85347-161">In the property pane for the cart icon module, configure the properties as needed.</span></span> <span data-ttu-id="85347-162">Si desea que el icono del carro muestre un resumen del carro (también conocido como minicarro) cuando los usuarios coloquen el cursor sobre él, seleccione **Mostrar minicarro**.</span><span class="sxs-lookup"><span data-stu-id="85347-162">If you want the cart icon to display a cart summary (also known as a mini cart) when users hover over it, select **Show mini cart**.</span></span>
1. <span data-ttu-id="85347-163">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger el fragmento y luego seleccione **Publicar** para publicarlo.</span><span class="sxs-lookup"><span data-stu-id="85347-163">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="85347-164">Para ayudar a garantizar que un encabezado aparece en cada página, siga estos pasos de cada plantilla de página creada para el sitio.</span><span class="sxs-lookup"><span data-stu-id="85347-164">To help ensure that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="85347-165">En el espacio **Encabezado** del módulo **Página predeterminada**, agregue el fragmento de pie de página que ha creado.</span><span class="sxs-lookup"><span data-stu-id="85347-165">In the **Header** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="85347-166">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="85347-166">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="85347-167">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="85347-167">Additional resources</span></span>

[<span data-ttu-id="85347-168">Visión general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="85347-168">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="85347-169">Módulo de contenedor</span><span class="sxs-lookup"><span data-stu-id="85347-169">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="85347-170">Módulo de icono de carro</span><span class="sxs-lookup"><span data-stu-id="85347-170">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="85347-171">Módulo de banner promocional</span><span class="sxs-lookup"><span data-stu-id="85347-171">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="85347-172">Módulo del menú de navegación</span><span class="sxs-lookup"><span data-stu-id="85347-172">Navigation Menu module</span></span>](nav-menu-module.md) 

[<span data-ttu-id="85347-173">Consentimiento de cookies</span><span class="sxs-lookup"><span data-stu-id="85347-173">Cookie consent</span></span>](cookie-consent-module.md)

[<span data-ttu-id="85347-174">Módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="85347-174">Footer module</span></span>](author-footer-module.md)

[<span data-ttu-id="85347-175">Módulo selector de sitio</span><span class="sxs-lookup"><span data-stu-id="85347-175">Site selector module</span></span>](site-selector.md)

[<span data-ttu-id="85347-176">Módulo de selector de tienda</span><span class="sxs-lookup"><span data-stu-id="85347-176">Store selector module</span></span>](store-selector.md)
