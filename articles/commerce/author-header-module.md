---
title: Módulo de encabezado
description: En este tema se tratan los módulos de encabezado y se describe como crear encabezados de página en Microsoft Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: e7dde3ba1ad375b309ae66cc6d31ccad85615e45
ms.sourcegitcommit: 81f162f2d50557d7afe292c8d326618ba0bc3259
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/11/2020
ms.locfileid: "3686631"
---
# <a name="header-module"></a><span data-ttu-id="9231f-103">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="9231f-103">Header module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9231f-104">En este tema se tratan los módulos de encabezado y se describe como crear encabezados de página en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9231f-104">This topic covers header modules and describes how to create page headers in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9231f-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="9231f-105">Overview</span></span>

<span data-ttu-id="9231f-106">En Dynamics 365 Commerce, un encabezado de página consta de varios módulos, como los de encabezado, menú de navegación, búsqueda, banner promocional y consentimiento de cookies.</span><span class="sxs-lookup"><span data-stu-id="9231f-106">In Dynamics 365 Commerce, a page header comprises multiple modules, such as the header, navigation menu, search, promo banner, and cookie consent modules.</span></span> 

<span data-ttu-id="9231f-107">El módulo de encabezado incluye un logotipo del sitio, vínculos a la jerarquía de navegación, vínculos a otras páginas en el sitio, un símbolo de carro, un símbolo de lista de deseos, opciones de inicio de sesión y la barra de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9231f-107">The header module includes a site logo, links to the navigation hierarchy, links to other pages on the site, a cart symbol, a wishlist symbol, sign-in options, and the search bar.</span></span> <span data-ttu-id="9231f-108">Un módulo de encabezado se optimiza automáticamente para el dispositivo en el que se está viendo el sitio (es decir, un dispositivo de escritorio o un dispositivo móvil).</span><span class="sxs-lookup"><span data-stu-id="9231f-108">A header module is automatically optimized for the device that the site is being viewed on (in other words, for a desktop device or a mobile device).</span></span> <span data-ttu-id="9231f-109">Por ejemplo, en un dispositivo móvil, la barra de navegación se contrae en un botón **Menú** (que a veces se denomina *menú de hamburguesa*).</span><span class="sxs-lookup"><span data-stu-id="9231f-109">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

<span data-ttu-id="9231f-110">La siguiente imagen muestra un ejemplo de un módulo de encabezado en una página de sitio.</span><span class="sxs-lookup"><span data-stu-id="9231f-110">The following image shows an example of a header module on a home page.</span></span>

![Ejemplo de módulo de cabecera](./media/ecommerce-header.png)

## <a name="properties-of-a-header-module"></a><span data-ttu-id="9231f-112">Propiedades de un módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="9231f-112">Properties of a header module</span></span>

<span data-ttu-id="9231f-113">Un módulo de encabezado tiene propiedades de **Imagen de logotipo**, **Vínculo de logotipo** y **Mis vínculos de cuenta**.</span><span class="sxs-lookup"><span data-stu-id="9231f-113">A header module supports **Logo image**, **Logo link**, and **My account links** properties.</span></span> 

<span data-ttu-id="9231f-114">Las propiedades **Imagen de logotipo** y **Vínculo de logotipo** se usan para definir un logotipo en la página.</span><span class="sxs-lookup"><span data-stu-id="9231f-114">The **Logo image** and **Logo link** properties are used to define a logo on the page.</span></span> <span data-ttu-id="9231f-115">Para obtener más información, consulte [Agregar un logotipo](add-logo.md).</span><span class="sxs-lookup"><span data-stu-id="9231f-115">For more information, see [Add a logo](add-logo.md).</span></span> 

<span data-ttu-id="9231f-116">La propiedad **Mis vínculos de cuenta** se puede utilizar para definir las páginas de la cuenta para las que el propietario del sitio desea mostrar vínculos rápidos en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="9231f-116">The **My account links** property can be used to define account pages that the site owner wants to show quick links for in the header.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="9231f-117">Módulos disponibles en un módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="9231f-117">Modules that are available in a header module</span></span>

<span data-ttu-id="9231f-118">Los módulos siguientes se pueden usar en un módulo de encabezado:</span><span class="sxs-lookup"><span data-stu-id="9231f-118">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="9231f-119">**Menú de navegación**: El menú de navegación representa la jerarquía de navegación de canales y otros vínculos de navegación estáticos.</span><span class="sxs-lookup"><span data-stu-id="9231f-119">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="9231f-120">La jerarquía de navegación de canales se puede configurar en Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9231f-120">The channel navigation hierarchy can be configured in Dynamics 365 Commerce.</span></span> <span data-ttu-id="9231f-121">El menú de navegación tiene una propiedad **Origen de navegación** que se utiliza para especificar los elementos del menú de navegación de Retail Server y elementos menú estáticos como un origen.</span><span class="sxs-lookup"><span data-stu-id="9231f-121">The navigation menu has a **Navigation Source** property that is used to specify Retail Server navigation menu items and static menu items as a source.</span></span> <span data-ttu-id="9231f-122">Si los elementos de menú estáticos se especifican como un origen, se pueden proporcionar vínculos relativos a otras páginas en el sitio.</span><span class="sxs-lookup"><span data-stu-id="9231f-122">If static menu items are specified as a source, relative links to other pages on the site can be provided.</span></span> <span data-ttu-id="9231f-123">Los artículos configurados aparecerán como navegación de encabezado.</span><span class="sxs-lookup"><span data-stu-id="9231f-123">Configured items then appear as header navigation.</span></span> 

- <span data-ttu-id="9231f-124">**Búsqueda**: el módulo de búsqueda permite a los usuarios especificar términos de búsqueda para buscar productos.</span><span class="sxs-lookup"><span data-stu-id="9231f-124">**Search** – The search module lets users enter search terms to search for products.</span></span> <span data-ttu-id="9231f-125">La dirección URL de la página de búsqueda predeterminada y los parámetros de consulta de búsqueda deben especificarse en **Valores de configuración del sitio \> Extensiones**.</span><span class="sxs-lookup"><span data-stu-id="9231f-125">The URL of the default search page and the search query parameters must be provided at **Site Settings \> Extensions**.</span></span> <span data-ttu-id="9231f-126">El módulo de búsqueda tiene propiedades que le permiten suprimir el botón de búsqueda o la etiqueta según lo requiera.</span><span class="sxs-lookup"><span data-stu-id="9231f-126">The search module has properties that let you suppress the search button or label as you require.</span></span> <span data-ttu-id="9231f-127">El módulo de búsqueda también admite opciones de sugerencia automática, como resultados de búsqueda de productos, palabras clave y categorías.</span><span class="sxs-lookup"><span data-stu-id="9231f-127">The search module also supports auto-suggest options, such as product, keyword, and category search results.</span></span>

- <span data-ttu-id="9231f-128">**Ícono de carrito** - El módulo de icono de carrito representa el icono de carrito, que muestra la cantidad de artículos en el carrito en un momento dado.</span><span class="sxs-lookup"><span data-stu-id="9231f-128">**Cart icon** - The cart icon module represents the cart icon, which shows the number of items in the cart at any given time.</span></span> <span data-ttu-id="9231f-129">Para más información, ver [Módulo de icono de carrito](cart-icon-module.md).</span><span class="sxs-lookup"><span data-stu-id="9231f-129">For more information, see [Cart icon module](cart-icon-module.md).</span></span>

## <a name="create-a-header-module-for-a-page"></a><span data-ttu-id="9231f-130">Crear un módulo de encabezado para una página</span><span class="sxs-lookup"><span data-stu-id="9231f-130">Create a header module for a page</span></span>

<span data-ttu-id="9231f-131">Para crear un módulo de encabezado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9231f-131">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="9231f-132">Vaya a **Fragmentos** y seleccione **Nuevo** para crear un nuevo fragmento.</span><span class="sxs-lookup"><span data-stu-id="9231f-132">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="9231f-133">En el cuadro de diálogo **Nuevo fragmento de página**, seleccione el módulo **Contenedor**, especifique un nombre para el fragmento de la página y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9231f-133">In the **New page fragment** dialog box, select the **Container** module, enter a name for the page fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="9231f-134">Seleccione el espacio **Contenedor predeterminado** y luego, en el panel de propiedades de la derecha, establezca la propiedad **Anchura** en **Rellenar contenedor**.</span><span class="sxs-lookup"><span data-stu-id="9231f-134">Select the **Default container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="9231f-135">En el espacio **Contenedor predeterminado**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="9231f-135">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="9231f-136">En el cuadro de diálogo **Agregar módulo**, seleccione los módulos **Banner promocional** y **Consentimiento de cookies** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9231f-136">In the **Add Module** dialog box, select the **Promo banner** and **Cookie consent** modules, and then select **OK**.</span></span>
1. <span data-ttu-id="9231f-137">En el espacio **Contenedor predeterminado**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="9231f-137">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="9231f-138">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9231f-138">In the **Add Module** dialog box, select the **Container** module, and then select **OK**.</span></span>
1. <span data-ttu-id="9231f-139">Seleccione el espacio **Contenedor** y luego, en el panel de propiedades de la derecha, establezca la propiedad **Anchura** en **Rellenar contenedor**.</span><span class="sxs-lookup"><span data-stu-id="9231f-139">Select the **Container** slot, and then, in the properties pane on the right, set the **Width** property to **Fill container**.</span></span>
1. <span data-ttu-id="9231f-140">En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="9231f-140">In the **Container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="9231f-141">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Encabezado** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9231f-141">In the **Add Module** dialog box, select the **Header** module, and then select **OK**.</span></span>
1. <span data-ttu-id="9231f-142">En el espacio **Menú de navegación** del módulo de encabezado, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="9231f-142">In the **Navigation menu** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="9231f-143">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Menú de navegación** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9231f-143">In the **Add Module** dialog box, select the **Navigation menu** module, and then select **OK**.</span></span>
1. <span data-ttu-id="9231f-144">En el panel de propiedades del módulo del menú de navegación, configure las propiedades según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9231f-144">In the property pane for the navigation menu module, configure the properties as needed.</span></span>
1. <span data-ttu-id="9231f-145">En el espacio **Búsqueda** del módulo de encabezado, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="9231f-145">In the **Search** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="9231f-146">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Búsqueda** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9231f-146">In the **Add Module** dialog box, select the **Search** module, and then select **OK**.</span></span>
1. <span data-ttu-id="9231f-147">En el panel de propiedades del módulo del módulo de búsqueda, configure las propiedades según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9231f-147">In the property pane for the search module, configure the properties as needed.</span></span>
1. <span data-ttu-id="9231f-148">En el espacio **Icono de carro** del módulo de encabezado, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="9231f-148">In the **Cart icon** slot of the header module, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="9231f-149">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Icono de carro** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9231f-149">In the **Add Module** dialog box, select the **Cart icon** module, and then select **OK**.</span></span>
1. <span data-ttu-id="9231f-150">En el panel de propiedades del módulo del icono de carro, configure las propiedades según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="9231f-150">In the property pane for the cart icon module, configure the properties as needed.</span></span> <span data-ttu-id="9231f-151">Si desea que el icono del carro muestre un resumen del carro (también conocido como minicarro) cuando los usuarios coloquen el cursor sobre él, seleccione **Mostrar minicarro**.</span><span class="sxs-lookup"><span data-stu-id="9231f-151">If you want the cart icon to display a cart summary (also known as a mini cart) when users hover over it, select **Show mini cart**.</span></span>
1. <span data-ttu-id="9231f-152">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger el fragmento y luego seleccione **Publicar** para publicarlo.</span><span class="sxs-lookup"><span data-stu-id="9231f-152">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="9231f-153">Para ayudar a garantizar que un encabezado aparece en cada página, siga estos pasos de cada plantilla de página creada para el sitio.</span><span class="sxs-lookup"><span data-stu-id="9231f-153">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="9231f-154">En el espacio **Encabezado** del módulo **Página predeterminada**, agregue el fragmento de pie de página que ha creado.</span><span class="sxs-lookup"><span data-stu-id="9231f-154">In the **Header** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="9231f-155">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="9231f-155">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9231f-156">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9231f-156">Additional resources</span></span>

[<span data-ttu-id="9231f-157">Visión general del kit de inicio</span><span class="sxs-lookup"><span data-stu-id="9231f-157">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="9231f-158">Módulo Contenedor</span><span class="sxs-lookup"><span data-stu-id="9231f-158">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="9231f-159">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="9231f-159">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="9231f-160">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="9231f-160">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="9231f-161">Módulo de icono de carrito</span><span class="sxs-lookup"><span data-stu-id="9231f-161">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="9231f-162">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="9231f-162">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="9231f-163">Módulo de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="9231f-163">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="9231f-164">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="9231f-164">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="9231f-165">Módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="9231f-165">Footer module</span></span>](author-footer-module.md)
