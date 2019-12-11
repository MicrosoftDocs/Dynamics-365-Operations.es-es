---
title: Módulo de encabezado
description: En este tema se tratan los módulos de encabezado y se describe cómo crearlos en Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: ''
ms.openlocfilehash: d393701dacb88ab03a4b56724d93c794da6bb5c8
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697284"
---
# <a name="header-module"></a><span data-ttu-id="25a6f-103">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="25a6f-103">Header module</span></span>

<span data-ttu-id="25a6f-104">[!include [banner](includes/preview-banner.md)] [!include [banner](includes/banner.md)]</span><span class="sxs-lookup"><span data-stu-id="25a6f-104">[!include [banner]includes/preview-banner.md)] [!include [banner](includes/banner.md)]</span></span>

<span data-ttu-id="25a6f-105">En este tema se tratan los módulos de encabezado y se describe cómo crearlos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="25a6f-105">This topic covers header modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="25a6f-106">Visión general</span><span class="sxs-lookup"><span data-stu-id="25a6f-106">Overview</span></span>

<span data-ttu-id="25a6f-107">Un módulo de encabezado es un contenedor especial que se usa para alojar todos los módulos que se mostrarán en un encabezado de página.</span><span class="sxs-lookup"><span data-stu-id="25a6f-107">A header module is a special container that is used to host all the modules that will be shown in a page's header.</span></span> <span data-ttu-id="25a6f-108">Por ejemplo, puede incluir el logotipo de su sitio, vínculos a la jerarquía de navegación, vínculos a otras páginas del sitio y la barra de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="25a6f-108">For example, it can include your site logo, links to the navigation hierarchy, links to other pages on the site, and the search bar.</span></span>

<span data-ttu-id="25a6f-109">Un módulo de encabezado se optimiza automáticamente para el dispositivo en el que se está viendo el sitio (es decir, un dispositivo de escritorio o un dispositivo móvil).</span><span class="sxs-lookup"><span data-stu-id="25a6f-109">A header module is automatically optimized for the device that the site is being viewed on (that is, a desktop device or a mobile device).</span></span> <span data-ttu-id="25a6f-110">Por ejemplo, en un dispositivo móvil, la barra de navegación se contrae en un botón **Menú** (que a veces se denomina *menú de hamburguesa*).</span><span class="sxs-lookup"><span data-stu-id="25a6f-110">For example, on a mobile device, the navigation bar is collapsed into a **Menu** button (which is sometimes referred to as a *hamburger menu*).</span></span>

## <a name="properties-of-a-header"></a><span data-ttu-id="25a6f-111">Propiedades de un encabezado</span><span class="sxs-lookup"><span data-stu-id="25a6f-111">Properties of a header</span></span>

<span data-ttu-id="25a6f-112">Como los contenedores genéricos, un módulo de encabezado admite las propiedades de **encabezado** y **ancho**.</span><span class="sxs-lookup"><span data-stu-id="25a6f-112">Like generic containers, a header module supports the **heading** and **width** properties.</span></span>

<span data-ttu-id="25a6f-113">Un módulo de cabecera tiene varias franjas.</span><span class="sxs-lookup"><span data-stu-id="25a6f-113">A header module has multiple slots.</span></span> <span data-ttu-id="25a6f-114">Por ejemplo, hay franjas para un mensaje informativo, un menú de navegación, un logotipo, una barra de búsqueda, un icono de carro, un icono de lista de deseos e información de cuenta.</span><span class="sxs-lookup"><span data-stu-id="25a6f-114">For example, there are slots for an informational message, navigation menu, logo, search bar, cart icon, wish list icon, and account information.</span></span> <span data-ttu-id="25a6f-115">Cada franja admite un conjunto concreto de módulos.</span><span class="sxs-lookup"><span data-stu-id="25a6f-115">Each slot supports a specific set of modules.</span></span>

## <a name="modules-that-are-available-in-a-header-module"></a><span data-ttu-id="25a6f-116">Módulos disponibles en un módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="25a6f-116">Modules that are available in a header module</span></span>

<span data-ttu-id="25a6f-117">Los módulos siguientes se pueden usar en un módulo de encabezado:</span><span class="sxs-lookup"><span data-stu-id="25a6f-117">The following modules can be used in a header module:</span></span>

- <span data-ttu-id="25a6f-118">**Menú de navegación**: El menú de navegación representa la jerarquía de navegación de canales y otros vínculos de navegación estáticos.</span><span class="sxs-lookup"><span data-stu-id="25a6f-118">**Navigation menu** – The navigation menu represents the channel navigation hierarchy and other static navigation links.</span></span> <span data-ttu-id="25a6f-119">La jerarquía de navegación de canales se puede configurar en Dynamics 365 Retail.</span><span class="sxs-lookup"><span data-stu-id="25a6f-119">The channel navigation hierarchy can be configured in Dynamics 365 Retail.</span></span> <span data-ttu-id="25a6f-120">Los artículos configurados aparecerán como navegación de encabezado.</span><span class="sxs-lookup"><span data-stu-id="25a6f-120">Configured items then appear as header navigation.</span></span> <span data-ttu-id="25a6f-121">Además, se pueden configurar los vínculos de navegación estáticos y se pueden proporcionar los vínculos relativos a otras páginas del sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="25a6f-121">In addition, static navigation links can be configured, and relative links to other pages on the e-Commerce site can be provided.</span></span> <span data-ttu-id="25a6f-122">El propio encabezado se puede alinear a la izquierda, a la derecha o al centro.</span><span class="sxs-lookup"><span data-stu-id="25a6f-122">The header itself can be aligned left, right, or center.</span></span>
- <span data-ttu-id="25a6f-123">**Icono de carro**: El icono de carro es un icono especial que representa el carro.</span><span class="sxs-lookup"><span data-stu-id="25a6f-123">**Cart icon** – The cart icon is a special icon that represents the cart.</span></span> <span data-ttu-id="25a6f-124">Se muestra en el encabezado e indica el número de artículos del carro.</span><span class="sxs-lookup"><span data-stu-id="25a6f-124">It's shown in the header and indicates the number of items in the cart.</span></span> <span data-ttu-id="25a6f-125">Un vínculo a la página del carro debe acompañar al icono del carro, para poder redirigir a los clientes a la página del carro cuando interactúan con el icono.</span><span class="sxs-lookup"><span data-stu-id="25a6f-125">A link to the cart page should accompany the cart icon, so that customers can be redirected to the cart page when they interact with the icon.</span></span>
- <span data-ttu-id="25a6f-126">**Icono de lista de deseos**: El icono de la lista de deseos se muestra en el encabezado e indica el número de artículos que se han agregado a la lista de deseos del cliente.</span><span class="sxs-lookup"><span data-stu-id="25a6f-126">**Wish list icon** – The wish list icon is shown in the header and indicates the number of items that have been added to the customer's wish list.</span></span> <span data-ttu-id="25a6f-127">Un vínculo a la página de lista de deseos debe acompañar a este icono, para poder redirigir a los clientes a la página de la lista de deseos cuando interactúan con el icono.</span><span class="sxs-lookup"><span data-stu-id="25a6f-127">A link to the wish list page should accompany this icon, so that customers can be redirected to the wish list page when they interact with the icon.</span></span>
- <span data-ttu-id="25a6f-128">**Módulo de inicio de sesión**: El módulo de inicio de sesión se muestra en el encabezado.</span><span class="sxs-lookup"><span data-stu-id="25a6f-128">**Sign-in module** – The sign-in module is shown in the header.</span></span> <span data-ttu-id="25a6f-129">Permite a los clientes iniciar sesión en su cuenta o registrarse para una cuenta.</span><span class="sxs-lookup"><span data-stu-id="25a6f-129">It lets customers either sign in to their account or sign up for an account.</span></span> <span data-ttu-id="25a6f-130">Si el cliente ya ha iniciado sesión, el módulo se puede configurar para mostrar vínculos a la página de la cuenta, a la página de historial de pedidos o a otra página.</span><span class="sxs-lookup"><span data-stu-id="25a6f-130">If the customer is already signed in, the module can be configured to show links to the account page, order history page, or another page.</span></span>
- <span data-ttu-id="25a6f-131">**Módulo de logotipo**: Este módulo muestra el logotipo que representa al minorista y a la marca.</span><span class="sxs-lookup"><span data-stu-id="25a6f-131">**Logo module** – This module shows the logo that represents the retailer and brand.</span></span> <span data-ttu-id="25a6f-132">Es una imagen con un vínculo.</span><span class="sxs-lookup"><span data-stu-id="25a6f-132">It's an image that has a link.</span></span> <span data-ttu-id="25a6f-133">El vínculo se configura normalmente para que tenga una redirección a la página principal. Por tanto, los clientes pueden regresar rápidamente a la página principal desde cualquier página del sitio.</span><span class="sxs-lookup"><span data-stu-id="25a6f-133">The link is typically configured so that it has a redirect to the home page, Therefore, customers can quickly return to the home page from any page on the site.</span></span>
- <span data-ttu-id="25a6f-134">**Alerta**: Aparece una alerta en el encabezado y se utiliza para mostrar un mensaje en línea que se aplica a todas las páginas del sitio.</span><span class="sxs-lookup"><span data-stu-id="25a6f-134">**Alert** – An alert appears in the header and is used to show an inline message that applies to all pages on the site.</span></span> <span data-ttu-id="25a6f-135">Por ejemplo, una alerta puede mostrar un mensaje como “La venta anual finaliza en 2 días”.</span><span class="sxs-lookup"><span data-stu-id="25a6f-135">For example, an alert might show a message such as "Annual sale ends in 2 days."</span></span>
- <span data-ttu-id="25a6f-136">**Barra de búsqueda**: La barra de la búsqueda permite a los usuarios especificar términos de búsqueda de modo que puedan buscar los productos.</span><span class="sxs-lookup"><span data-stu-id="25a6f-136">**Search bar** – The search bar lets users enter search terms so that they can search for products.</span></span> <span data-ttu-id="25a6f-137">El módulo se debe configurar con la dirección URL de la página de resultados de la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="25a6f-137">The module must be configured with the URL of the search results page.</span></span> <span data-ttu-id="25a6f-138">El parámetro de la cadena de consulta se puede configurar (el valor predeterminado es **“q”**).</span><span class="sxs-lookup"><span data-stu-id="25a6f-138">The query string parameter can be configured (the default value is **"q"**).</span></span> <span data-ttu-id="25a6f-139">La barra de búsqueda tiene una franja de sugerencia automática donde se debe agregar el módulo de sugerencia automática.</span><span class="sxs-lookup"><span data-stu-id="25a6f-139">The search bar has an autosuggest slot where the autosuggest module should be added.</span></span>
- <span data-ttu-id="25a6f-140">**Sugerencia automática**: El módulo de sugerencia automática muestra resultados automáticamente.</span><span class="sxs-lookup"><span data-stu-id="25a6f-140">**Autosuggest** – The autosuggest module shows automatically suggested results.</span></span> <span data-ttu-id="25a6f-141">Estos resultados pueden ser palabras clave, productos o categorías donde se encuentra el término de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="25a6f-141">These results can be keywords, products, or categories where the search term is found.</span></span>

## <a name="create-a-header-module"></a><span data-ttu-id="25a6f-142">Crear un módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="25a6f-142">Create a header module</span></span>

<span data-ttu-id="25a6f-143">Para crear un módulo de encabezado, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="25a6f-143">To create a header module, follow these steps.</span></span>

1. <span data-ttu-id="25a6f-144">Cree un fragmento de página que incluya un módulo de encabezado.</span><span class="sxs-lookup"><span data-stu-id="25a6f-144">Create a page fragment that includes a header module.</span></span>
1. <span data-ttu-id="25a6f-145">Agregue módulos a las franjas del módulo de encabezado.</span><span class="sxs-lookup"><span data-stu-id="25a6f-145">Add modules to the slots in the header module.</span></span>
1. <span data-ttu-id="25a6f-146">Actualice la configuración para cada módulo.</span><span class="sxs-lookup"><span data-stu-id="25a6f-146">Update the settings for each module.</span></span>
1. <span data-ttu-id="25a6f-147">Guarde el fragmento de página.</span><span class="sxs-lookup"><span data-stu-id="25a6f-147">Save the page fragment.</span></span> 
1. <span data-ttu-id="25a6f-148">Proteja la página y publíquela.</span><span class="sxs-lookup"><span data-stu-id="25a6f-148">Check in the page, and publish it.</span></span>

<span data-ttu-id="25a6f-149">Para ayudar a garantizar que un encabezado aparece en cada página, siga estos pasos de cada plantilla de página creada para el sitio.</span><span class="sxs-lookup"><span data-stu-id="25a6f-149">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="25a6f-150">En la página predeterminada, agregue el fragmento de página que contiene el módulo de encabezado en el encabezado de la franja principal.</span><span class="sxs-lookup"><span data-stu-id="25a6f-150">On the default page, add the page fragment containing the header module to the header in the main slot.</span></span>
1. <span data-ttu-id="25a6f-151">Guarde la plantilla.</span><span class="sxs-lookup"><span data-stu-id="25a6f-151">Save the template.</span></span> 
1. <span data-ttu-id="25a6f-152">Proteja la plantilla y publíquela.</span><span class="sxs-lookup"><span data-stu-id="25a6f-152">Check in the template, and publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="25a6f-153">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="25a6f-153">Additional resources</span></span>

[<span data-ttu-id="25a6f-154">Visión general de kit de inicio</span><span class="sxs-lookup"><span data-stu-id="25a6f-154">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="25a6f-155">Módulo Contenedor</span><span class="sxs-lookup"><span data-stu-id="25a6f-155">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="25a6f-156">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="25a6f-156">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="25a6f-157">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="25a6f-157">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="25a6f-158">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="25a6f-158">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="25a6f-159">Módulo de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="25a6f-159">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="25a6f-160">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="25a6f-160">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="25a6f-161">Módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="25a6f-161">Footer module</span></span>](author-footer-module.md)
