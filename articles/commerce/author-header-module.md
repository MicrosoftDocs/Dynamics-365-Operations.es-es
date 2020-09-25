---
title: Módulo de encabezado
description: En este tema se tratan los módulos de encabezado y se describe como crear encabezados de página en Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 08/31/2020
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
ms.openlocfilehash: eb440a8fb67888c9411ad5998fead4d00982b436
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761233"
---
# <a name="header-module"></a><span data-ttu-id="561b4-103">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="561b4-103">Header module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="561b4-104">En este tema se tratan los módulos de encabezado y se describe como crear encabezados de página en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="561b4-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="561b4-105">Información general</span><span class="sxs-lookup"><span data-stu-id="561b4-105">Overview</span></span>

<span data-ttu-id="561b4-106">En Dynamics 365 Commerce, un encabezado de página se configura como un fragmento de página que incluye los módulos de encabezado, banner promocional y consentimiento de cookies.</span><span class="sxs-lookup"><span data-stu-id="561b4-106">In Dynamics 365 Commerce, a page header is configured as a page fragment that includes the header, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="561b4-107">El módulo de encabezado incluye un logotipo del sitio, vínculos a la jerarquía de navegación, vínculos a otras páginas en el sitio, un módulo de icono de carro, un símbolo de lista de deseos, opciones de inicio de sesión y la barra de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="561b4-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart icon module, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="561b4-108">Un módulo de encabezado se optimiza automáticamente para el dispositivo en el que se está viendo el sitio (es decir, un dispositivo de escritorio o un dispositivo móvil).</span><span class="sxs-lookup"><span data-stu-id="561b4-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="561b4-109">Por ejemplo, en un dispositivo móvil, la barra de navegación se contrae en un botón **Menú** (que a veces se denomina *menú de hamburguesa*).</span><span class="sxs-lookup"><span data-stu-id="561b4-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

<span data-ttu-id="561b4-110">La siguiente imagen muestra un ejemplo de un módulo de encabezado en una página de sitio.</span><span class="sxs-lookup"><span data-stu-id="561b4-110">The following image shows an example of a header module on a home page.</span></span>

![Ejemplo de módulo de cabecera](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a><span data-ttu-id="561b4-112">Propiedades de un módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="561b4-112">Properties of a header module</span></span>

<span data-ttu-id="561b4-113">Un módulo de encabezado tiene propiedades de **Imagen de logotipo**, **Vínculo de logotipo** y **Mis vínculos de cuenta**.</span><span class="sxs-lookup"><span data-stu-id="561b4-113">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="561b4-114">Las propiedades **Imagen de logotipo** y **Vínculo de logotipo** se usan para definir un logotipo en la página.</span><span class="sxs-lookup"><span data-stu-id="561b4-114">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="561b4-115">Para obtener más información, consulte [Agregar un logotipo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="561b4-115">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="561b4-116">La propiedad **Mis vínculos de cuenta** se puede utilizar para definir las páginas de la cuenta para las que el propietario del sitio desea mostrar vínculos rápidos en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="561b4-116">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-within-a-header-module"></a><span data-ttu-id="561b4-117">Módulos disponibles en un módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="561b4-117">Modules that are available within a header module</span></span>

<span data-ttu-id="561b4-118">Los módulos siguientes se pueden usar en un módulo de encabezado:</span><span class="sxs-lookup"><span data-stu-id="561b4-118">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="561b4-119">**Menú de navegación**: El menú de navegación representa la jerarquía de navegación de canales y otros vínculos de navegación estáticos.</span><span class="sxs-lookup"><span data-stu-id="561b4-119">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="561b4-120">Para obtener más información, consulte [Módulo del menú de navegación](nav-menu-module.md).</span><span class="sxs-lookup"><span data-stu-id="561b4-120">For more information, see [Navigation menu module](nav-menu-module.md).</span></span>

- <span data-ttu-id="561b4-121">**Búsqueda**: el módulo de búsqueda permite a los usuarios especificar términos de búsqueda para buscar productos.</span><span class="sxs-lookup"><span data-stu-id="561b4-121">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="561b4-122">La dirección URL de la página de búsqueda predeterminada y los parámetros de consulta de búsqueda deben especificarse en **Valores de configuración del sitio \> Extensiones**.</span><span class="sxs-lookup"><span data-stu-id="561b4-122">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="561b4-123">El módulo de búsqueda tiene propiedades que le permiten suprimir el botón de búsqueda o la etiqueta según lo requiera.</span><span class="sxs-lookup"><span data-stu-id="561b4-123">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="561b4-124">El módulo de búsqueda también admite opciones de sugerencia automática, como resultados de búsqueda de productos, palabras clave y categorías.</span><span class="sxs-lookup"><span data-stu-id="561b4-124">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

- <span data-ttu-id="561b4-125">**Ícono de carrito** - El módulo de icono de carrito representa el icono de carrito, que muestra la cantidad de artículos en el carrito en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="561b4-125">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="561b4-126">Para más información, ver [Módulo de icono de carrito](cart-icon-module.md).</span><span class="sxs-lookup"><span data-stu-id="561b4-126">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

## <a name="create-a-header-fragment-for-a-page"></a><span data-ttu-id="561b4-127">Crear un fragmento de encabezado para una página</span><span class="sxs-lookup"><span data-stu-id="561b4-127">Create a header fragment for a page</span></span>

<span data-ttu-id="561b4-128">Para crear un fragmento de encabezado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="561b4-128">To create a header fragment, follow these steps.</span></span>

1. <span data-ttu-id="561b4-129">Vaya a **Fragmentos** y seleccione **Nuevo** para crear un nuevo fragmento.</span><span class="sxs-lookup"><span data-stu-id="561b4-129">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="561b4-130">En el cuadro de diálogo **Nuevo fragmento**, seleccione el módulo **Contenedor**, especifique un nombre para el fragmento y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="561b4-130">In the **New fragment** dialog box, select the **Container** module, enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="561b4-131">Seleccione el espacio **Contenedor predeterminado** y luego, en el panel de propiedades de la derecha, establezca la propiedad **Anchura** en **Rellenar pantalla**.</span><span class="sxs-lookup"><span data-stu-id="561b4-131">Select the **Default container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill Screen**.</span></span>
1. <span data-ttu-id="561b4-132">En el espacio **Contenedor predeterminado**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="561b4-132">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="561b4-133">En el cuadro de diálogo **Agregar módulo**, seleccione los módulos Banner promocional y **Consentimiento de cookies**, **Encabezado** y **Banner promocional** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="561b4-133">In the **Add Module** dialog box, select the **Cookie consent**, **Header**, and **Promo banner** modules, and then select **OK**.</span></span>
1. <span data-ttu-id="561b4-134">En el panel de propiedades del módulo **Banner promocional**, seleccione **Agregar mensaje** y luego seleccione **Mensaje**.</span><span class="sxs-lookup"><span data-stu-id="561b4-134">In the properties pane of the **Promo banner** module, select **Add Message**, and then select **Message**.</span></span>
1. <span data-ttu-id="561b4-135">En el cuadro de diálogo **Mensaje**, agregue el texto y los vínculos para el contenido promocional y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="561b4-135">In the **Message** dialog box, add text and links for the promotional content, and then select **OK**.</span></span>
1. <span data-ttu-id="561b4-136">En el panel de propiedades del módulo **Consentimiento de cookies**, agregue y configure texto y un vínculo a la página de privacidad del sitio.</span><span class="sxs-lookup"><span data-stu-id="561b4-136">In the properties pane of the **Cookie consent** module, add and configure text and a link to the site privacy page.</span></span>
1. <span data-ttu-id="561b4-137">En el espacio **Menú de navegación** del módulo de encabezado, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="561b4-137">In the **Navigation menu** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="561b4-138">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Menú de navegación** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="561b4-138">In the **Add Module** dialog box, select the **Navigation menu** module, and then select **OK**.</span></span>
1. <span data-ttu-id="561b4-139">En el panel de propiedades del módulo del menú de navegación, en **Fuente para el menú de navegación**, seleccione **Retail Server**.</span><span class="sxs-lookup"><span data-stu-id="561b4-139">In the property pane for the navigation menu module, under **Source for navigation menu**, select **Retail Server**.</span></span>
1. <span data-ttu-id="561b4-140">En el panel de propiedades del módulo del menú de navegación, en **Elementos de menú estáticos**, seleccione **Agregar elemento de menú** y luego seleccione **Elemento de menú**.</span><span class="sxs-lookup"><span data-stu-id="561b4-140">In the property pane for the navigation menu module, under **Static menu items**, select **Add Menu item**, and then select **Menu item**.</span></span> 
1. <span data-ttu-id="561b4-141">En el cuadro de diálogo **Elemento de menú**, en **Texto del elemento de menú** escriba "Contacto".</span><span class="sxs-lookup"><span data-stu-id="561b4-141">In the **Menu item** dialog box, under **Menu Item Text** enter "Contact."</span></span>
1. <span data-ttu-id="561b4-142">En el cuadro de diálogo **Elemento de menú**, en **Destino de vínculo de elemento de menú**, seleccione **Agregar un vínculo**.</span><span class="sxs-lookup"><span data-stu-id="561b4-142">In the **Menu item** dialog box, under **Menu Item Link target** select **Add a link**.</span></span>
1. <span data-ttu-id="561b4-143">En el cuadro de diálogo **Agregar un vínculo**, seleccione la dirección URL para la página "Contacto" del sitio y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="561b4-143">In the **Add a link** dialog box, select the URL for the site's "Contact" page, and then select **OK**.</span></span>  
1. <span data-ttu-id="561b4-144">En el cuadro de diálogo **Elemento de menú**, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="561b4-144">In the **Menu item** dialog box, select **OK**.</span></span>
1. <span data-ttu-id="561b4-145">En el espacio **Búsqueda** del módulo de encabezado, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="561b4-145">In the **Search** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="561b4-146">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Búsqueda** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="561b4-146">In the **Add Module** dialog box, select the **Search** module, and then select **OK**.</span></span>
1. <span data-ttu-id="561b4-147">En el panel de propiedades del módulo del módulo de búsqueda, configure las propiedades según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="561b4-147">In the property pane for the search module, configure the properties as needed.</span></span>
1. <span data-ttu-id="561b4-148">En el espacio **Icono de carro** del módulo de encabezado, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="561b4-148">In the **Cart icon** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="561b4-149">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Icono de carro** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="561b4-149">In the **Add Module** dialog box, select the **Cart icon** module, and then select **OK**.</span></span>
1. <span data-ttu-id="561b4-150">En el panel de propiedades del módulo del icono de carro, configure las propiedades según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="561b4-150">In the property pane for the cart icon module, configure the properties as needed.</span></span> <span data-ttu-id="561b4-151">Si desea que el icono del carro muestre un resumen del carro (también conocido como minicarro) cuando los usuarios coloquen el cursor sobre él, seleccione **Mostrar minicarro**.</span><span class="sxs-lookup"><span data-stu-id="561b4-151">If you want the cart icon to display a cart summary (also known as a mini cart) when users hover over it, select **Show mini cart**.</span></span>
1. <span data-ttu-id="561b4-152">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger el fragmento y luego seleccione **Publicar** para publicarlo.</span><span class="sxs-lookup"><span data-stu-id="561b4-152">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="561b4-153">Para ayudar a garantizar que un encabezado aparece en cada página, siga estos pasos de cada plantilla de página creada para el sitio.</span><span class="sxs-lookup"><span data-stu-id="561b4-153">To help ensure that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="561b4-154">En el espacio **Encabezado** del módulo **Página predeterminada**, agregue el fragmento de pie de página que ha creado.</span><span class="sxs-lookup"><span data-stu-id="561b4-154">In the **Header** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="561b4-155">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="561b4-155">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="561b4-156">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="561b4-156">Additional resources</span></span>

[<span data-ttu-id="561b4-157">Visión general del kit de inicio</span><span class="sxs-lookup"><span data-stu-id="561b4-157">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="561b4-158">Módulo de contenedor</span><span class="sxs-lookup"><span data-stu-id="561b4-158">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="561b4-159">Módulo de icono de carro</span><span class="sxs-lookup"><span data-stu-id="561b4-159">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="561b4-160">Módulo de banner promocional</span><span class="sxs-lookup"><span data-stu-id="561b4-160">Promo banner module</span></span>](add-alert.md)

[<span data-ttu-id="561b4-161">Módulo del menú de navegación</span><span class="sxs-lookup"><span data-stu-id="561b4-161">Navigation Menu module</span></span>](nav-menu-module.md) 

[<span data-ttu-id="561b4-162">Consentimiento de cookies</span><span class="sxs-lookup"><span data-stu-id="561b4-162">Cookie consent</span></span>](cookie-consent-module.md)

[<span data-ttu-id="561b4-163">Módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="561b4-163">Footer module</span></span>](author-footer-module.md)
