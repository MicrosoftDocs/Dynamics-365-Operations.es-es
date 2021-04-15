---
title: Módulo de encabezado
description: En este tema se tratan los módulos de encabezado y se describe como crear encabezados de página en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 10/20/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 6b14178431b281daa827749781dd16481f8bfb74
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799929"
---
# <a name="header-module"></a><span data-ttu-id="f71d5-103">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="f71d5-103">Header module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f71d5-104">En este tema se tratan los módulos de encabezado y se describe como crear encabezados de página en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f71d5-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="f71d5-105">En Dynamics 365 Commerce, un encabezado de página se configura como un fragmento de página que incluye los módulos de encabezado, banner promocional y consentimiento de cookies.</span><span class="sxs-lookup"><span data-stu-id="f71d5-105">In Dynamics 365 Commerce, a page header is configured as a page fragment that includes the header, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="f71d5-106">El módulo de encabezado incluye un logotipo del sitio, vínculos a la jerarquía de navegación, vínculos a otras páginas en el sitio, un módulo de icono de carro, un símbolo de lista de deseos, opciones de inicio de sesión y la barra de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="f71d5-106">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart icon module, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="f71d5-107">Un módulo de encabezado se optimiza automáticamente para el dispositivo en el que se está viendo el sitio (es decir, un dispositivo de escritorio o un dispositivo móvil).</span><span class="sxs-lookup"><span data-stu-id="f71d5-107">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="f71d5-108">Por ejemplo, en un dispositivo móvil, la barra de navegación se contrae en un botón **Menú** (que a veces se denomina *menú de hamburguesa*).</span><span class="sxs-lookup"><span data-stu-id="f71d5-108">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

<span data-ttu-id="f71d5-109">La siguiente imagen muestra un ejemplo de un módulo de encabezado en una página de sitio.</span><span class="sxs-lookup"><span data-stu-id="f71d5-109">The following image shows an example of a header module on a home page.</span></span>

![Ejemplo de módulo de cabecera](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a><span data-ttu-id="f71d5-111">Propiedades de un módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="f71d5-111">Properties of a header module</span></span>

<span data-ttu-id="f71d5-112">Un módulo de encabezado tiene propiedades de **Imagen de logotipo**, **Vínculo de logotipo** y **Mis vínculos de cuenta**.</span><span class="sxs-lookup"><span data-stu-id="f71d5-112">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="f71d5-113">Las propiedades **Imagen de logotipo** y **Vínculo de logotipo** se usan para definir un logotipo en la página.</span><span class="sxs-lookup"><span data-stu-id="f71d5-113">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="f71d5-114">Para obtener más información, consulte [Agregar un logotipo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="f71d5-114">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="f71d5-115">La propiedad **Mis vínculos de cuenta** se puede utilizar para definir las páginas de la cuenta para las que el propietario del sitio desea mostrar vínculos rápidos en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="f71d5-115">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-within-a-header-module"></a><span data-ttu-id="f71d5-116">Módulos disponibles en un módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="f71d5-116">Modules that are available within a header module</span></span>

<span data-ttu-id="f71d5-117">Los módulos siguientes se pueden usar en un módulo de encabezado:</span><span class="sxs-lookup"><span data-stu-id="f71d5-117">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="f71d5-118">**Menú de navegación**: El menú de navegación representa la jerarquía de navegación de canales y otros vínculos de navegación estáticos.</span><span class="sxs-lookup"><span data-stu-id="f71d5-118">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="f71d5-119">Para obtener más información, consulte [Módulo del menú de navegación](nav-menu-module.md).</span><span class="sxs-lookup"><span data-stu-id="f71d5-119">For more information, see [Navigation menu module](nav-menu-module.md).</span></span>

- <span data-ttu-id="f71d5-120">**Búsqueda**: el módulo de búsqueda permite a los usuarios especificar términos de búsqueda para buscar productos.</span><span class="sxs-lookup"><span data-stu-id="f71d5-120">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="f71d5-121">La dirección URL de la página de búsqueda predeterminada y los parámetros de consulta de búsqueda deben especificarse en **Valores de configuración del sitio \> Extensiones**.</span><span class="sxs-lookup"><span data-stu-id="f71d5-121">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="f71d5-122">El módulo de búsqueda tiene propiedades que le permiten suprimir el botón de búsqueda o la etiqueta según lo requiera.</span><span class="sxs-lookup"><span data-stu-id="f71d5-122">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="f71d5-123">El módulo de búsqueda también admite opciones de sugerencia automática, como resultados de búsqueda de productos, palabras clave y categorías.</span><span class="sxs-lookup"><span data-stu-id="f71d5-123">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

- <span data-ttu-id="f71d5-124">**Ícono de carrito** - El módulo de icono de carrito representa el icono de carrito, que muestra la cantidad de artículos en el carrito en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="f71d5-124">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="f71d5-125">Para más información, ver [Módulo de icono de carrito](cart-icon-module.md).</span><span class="sxs-lookup"><span data-stu-id="f71d5-125">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

- <span data-ttu-id="f71d5-126">**Selector de sitio**: el módulo selector de sitio permite a los usuarios navegar por diferentes sitios predefinidos, según el mercado, las regiones y las configuraciones regionales.</span><span class="sxs-lookup"><span data-stu-id="f71d5-126">**Site selector** - The site selector module lets users browse across different predefined sites, based on market, regions, and locales.</span></span> <span data-ttu-id="f71d5-127">Para obtener más información, consulte [Módulo selector de sitio](site-selector.md).</span><span class="sxs-lookup"><span data-stu-id="f71d5-127">For more information, see [Site selector module](site-selector.md).</span></span>

- <span data-ttu-id="f71d5-128">**Selector de tienda**: el módulo selector de tienda se puede incluir en una franja de selector de tienda del módulo de encabezado.</span><span class="sxs-lookup"><span data-stu-id="f71d5-128">**Store selector** - The store selector module can be included in a header module's store selector slot.</span></span> <span data-ttu-id="f71d5-129">Permite a los usuarios encontrar tiendas cercanas y navegar por ellas.</span><span class="sxs-lookup"><span data-stu-id="f71d5-129">It lets users browse and find nearby stores.</span></span> <span data-ttu-id="f71d5-130">Los usuarios también pueden especificar una tienda preferida.</span><span class="sxs-lookup"><span data-stu-id="f71d5-130">Users can also specify a preferred store.</span></span> <span data-ttu-id="f71d5-131">Esa tienda se mostrará en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="f71d5-131">That store will then be shown in the header.</span></span> <span data-ttu-id="f71d5-132">Cuando el módulo selector de tienda está incluido en el módulo de encabezado, su propiedad **Modo** debe establecerse en **Buscar tiendas**.</span><span class="sxs-lookup"><span data-stu-id="f71d5-132">When the store selector module is included in the header module, its **Mode** property must be set to **Find stores**.</span></span> <span data-ttu-id="f71d5-133">Para obtener más información, consulte [Módulo selector de tienda](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="f71d5-133">For more information, see [Store selector module](store-selector.md).</span></span>

> [!NOTE]
> - <span data-ttu-id="f71d5-134">La compatibilidad con el uso del icono de carro en los módulos de encabezado está disponible en Dynamics 365 Commerce 10.0.11.</span><span class="sxs-lookup"><span data-stu-id="f71d5-134">Support for using the cart icon module in header modules is available in the Dynamics 365 Commerce 10.0.11 release.</span></span>
> - <span data-ttu-id="f71d5-135">La compatibilidad con el uso del módulo selector de sitio en los módulos de encabezado está disponible en Dynamics 365 Commerce 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="f71d5-135">Support for using the site selector module in header modules is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>
> - <span data-ttu-id="f71d5-136">La compatibilidad con el uso del módulo selector de tienda en los módulos de encabezado está disponible en Dynamics 365 Commerce 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="f71d5-136">Support for using the store selector module in header modules is available in the Dynamics 365 Commerce 10.0.15 release.</span></span>

## <a name="create-a-header-fragment-for-a-page"></a><span data-ttu-id="f71d5-137">Crear un fragmento de encabezado para una página</span><span class="sxs-lookup"><span data-stu-id="f71d5-137">Create a header fragment for a page</span></span>

<span data-ttu-id="f71d5-138">Para crear un fragmento de encabezado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="f71d5-138">To create a header fragment, follow these steps.</span></span>

1. <span data-ttu-id="f71d5-139">Vaya a **Fragmentos** y seleccione **Nuevo** para crear un nuevo fragmento.</span><span class="sxs-lookup"><span data-stu-id="f71d5-139">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="f71d5-140">En el cuadro de diálogo **Nuevo fragmento**, seleccione el módulo **Contenedor**, especifique un nombre para el fragmento y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f71d5-140">In the **New fragment** dialog box, select the **Container** module, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="f71d5-141">Seleccione el espacio **Contenedor predeterminado** y luego, en el panel de propiedades de la derecha, establezca la propiedad **Anchura** en **Rellenar pantalla**.</span><span class="sxs-lookup"><span data-stu-id="f71d5-141">Select the **Default container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill Screen**.</span></span>
1. <span data-ttu-id="f71d5-142">En el espacio **Contenedor predeterminado**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="f71d5-142">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f71d5-143">En el cuadro de diálogo **Agregar módulo**, seleccione los módulos Banner promocional y **Consentimiento de cookies**, **Encabezado** y **Banner promocional** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f71d5-143">In the **Add Module** dialog box, select the **Cookie consent**, **Header**, and **Promo banner** modules, and then select **OK**.</span></span>
1. <span data-ttu-id="f71d5-144">En el panel de propiedades del módulo **Banner promocional**, seleccione **Agregar mensaje** y luego seleccione **Mensaje**.</span><span class="sxs-lookup"><span data-stu-id="f71d5-144">In the properties pane of the **Promo banner** module, select **Add Message**, and then select **Message**.</span></span>
1. <span data-ttu-id="f71d5-145">En el cuadro de diálogo **Mensaje**, agregue el texto y los vínculos para el contenido promocional y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f71d5-145">In the **Message** dialog box, add text and links for the promotional content, and then select **OK**.</span></span>
1. <span data-ttu-id="f71d5-146">En el panel de propiedades del módulo **Consentimiento de cookies**, agregue y configure texto y un vínculo a la página de privacidad del sitio.</span><span class="sxs-lookup"><span data-stu-id="f71d5-146">In the properties pane of the **Cookie consent** module, add and configure text and a link to the site privacy page.</span></span>
1. <span data-ttu-id="f71d5-147">En el espacio **Menú de navegación** del módulo de encabezado, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="f71d5-147">In the **Navigation menu** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f71d5-148">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Menú de navegación** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f71d5-148">In the **Add Module** dialog box, select the **Navigation menu** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f71d5-149">En el panel de propiedades del módulo del menú de navegación, en **Fuente para el menú de navegación**, seleccione **Retail Server**.</span><span class="sxs-lookup"><span data-stu-id="f71d5-149">In the property pane for the navigation menu module, under **Source for navigation menu**, select **Retail Server**.</span></span>
1. <span data-ttu-id="f71d5-150">En el panel de propiedades del módulo del menú de navegación, en **Elementos de menú estáticos**, seleccione **Agregar elemento de menú** y luego seleccione **Elemento de menú**.</span><span class="sxs-lookup"><span data-stu-id="f71d5-150">In the property pane for the navigation menu module, under **Static menu items**, select **Add Menu item**, and then select **Menu item**.</span></span> 
1. <span data-ttu-id="f71d5-151">En el cuadro de diálogo **Elemento de menú**, en **Texto del elemento de menú** escriba "Contacto".</span><span class="sxs-lookup"><span data-stu-id="f71d5-151">In the **Menu item** dialog box, under **Menu Item Text** enter "Contact."</span></span>
1. <span data-ttu-id="f71d5-152">En el cuadro de diálogo **Elemento de menú**, en **Destino de vínculo de elemento de menú**, seleccione **Agregar un vínculo**.</span><span class="sxs-lookup"><span data-stu-id="f71d5-152">In the **Menu item** dialog box, under **Menu Item Link target** select **Add a link**.</span></span>
1. <span data-ttu-id="f71d5-153">En el cuadro de diálogo **Agregar un vínculo**, seleccione la dirección URL para la página "Contacto" del sitio y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f71d5-153">In the **Add a link** dialog box, select the URL for the site's "Contact" page, and then select **OK**.</span></span>  
1. <span data-ttu-id="f71d5-154">En el cuadro de diálogo **Elemento de menú**, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f71d5-154">In the **Menu item** dialog box, select **OK**.</span></span>
1. <span data-ttu-id="f71d5-155">En el espacio **Búsqueda** del módulo de encabezado, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="f71d5-155">In the **Search** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f71d5-156">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Búsqueda** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f71d5-156">In the **Add Module** dialog box, select the **Search** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f71d5-157">En el panel de propiedades del módulo del módulo de búsqueda, configure las propiedades según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f71d5-157">In the property pane for the search module, configure the properties as needed.</span></span>
1. <span data-ttu-id="f71d5-158">En el espacio **Icono de carro** del módulo de encabezado, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="f71d5-158">In the **Cart icon** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f71d5-159">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Icono de carro** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f71d5-159">In the **Add Module** dialog box, select the **Cart icon** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f71d5-160">En el panel de propiedades del módulo del icono de carro, configure las propiedades según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f71d5-160">In the property pane for the cart icon module, configure the properties as needed.</span></span> <span data-ttu-id="f71d5-161">Si desea que el icono del carro muestre un resumen del carro (también conocido como minicarro) cuando los usuarios coloquen el cursor sobre él, seleccione **Mostrar minicarro**.</span><span class="sxs-lookup"><span data-stu-id="f71d5-161">If you want the cart icon to display a cart summary (also known as a mini cart) when users hover over it, select **Show mini cart**.</span></span>
1. <span data-ttu-id="f71d5-162">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger el fragmento y luego seleccione **Publicar** para publicarlo.</span><span class="sxs-lookup"><span data-stu-id="f71d5-162">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="f71d5-163">Para ayudar a garantizar que un encabezado aparece en cada página, siga estos pasos de cada plantilla de página creada para el sitio.</span><span class="sxs-lookup"><span data-stu-id="f71d5-163">To help ensure that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="f71d5-164">En el espacio **Encabezado** del módulo **Página predeterminada**, agregue el fragmento de pie de página que ha creado.</span><span class="sxs-lookup"><span data-stu-id="f71d5-164">In the **Header** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="f71d5-165">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="f71d5-165">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f71d5-166">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f71d5-166">Additional resources</span></span>

[<span data-ttu-id="f71d5-167">Visión general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="f71d5-167">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="f71d5-168">Módulo de contenedor</span><span class="sxs-lookup"><span data-stu-id="f71d5-168">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="f71d5-169">Módulo de icono de carro</span><span class="sxs-lookup"><span data-stu-id="f71d5-169">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="f71d5-170">Módulo de banner promocional</span><span class="sxs-lookup"><span data-stu-id="f71d5-170">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="f71d5-171">Módulo del menú de navegación</span><span class="sxs-lookup"><span data-stu-id="f71d5-171">Navigation Menu module</span></span>](nav-menu-module.md) 

[<span data-ttu-id="f71d5-172">Consentimiento de cookies</span><span class="sxs-lookup"><span data-stu-id="f71d5-172">Cookie consent</span></span>](cookie-consent-module.md)

[<span data-ttu-id="f71d5-173">Módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="f71d5-173">Footer module</span></span>](author-footer-module.md)

[<span data-ttu-id="f71d5-174">Módulo selector de sitio</span><span class="sxs-lookup"><span data-stu-id="f71d5-174">Site selector module</span></span>](site-selector.md)

[<span data-ttu-id="f71d5-175">Módulo de selector de tienda</span><span class="sxs-lookup"><span data-stu-id="f71d5-175">Store selector module</span></span>](store-selector.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]