---
title: Módulo de mapa
description: En este tema se tratan los módulos de mapa y se describe cómo configurarlos en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
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
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 74991a2979540dab344f39976005250637fab29c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5252591"
---
# <a name="map-module"></a><span data-ttu-id="c52c8-103">Módulo de mapa</span><span class="sxs-lookup"><span data-stu-id="c52c8-103">Map module</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="c52c8-104">En este tema se tratan los módulos de mapa y se describe cómo configurarlos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c52c8-104">This topic covers map modules and describes how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="c52c8-105">Un módulo de mapa muestra las ubicaciones de las tiendas en un mapa interactivo que se representa utilizando el [Control web de Bing Maps V8](https://docs.microsoft.com/bingmaps/v8-web-control/).</span><span class="sxs-lookup"><span data-stu-id="c52c8-105">A map module shows the locations of stores on an interactive map that is rendered by using the [Bing Maps V8 Web Control](https://docs.microsoft.com/bingmaps/v8-web-control/).</span></span> <span data-ttu-id="c52c8-106">Se requiere una clave de la API de Bing Maps, y debe agregarse a la página de parámetros compartidos en la Central de Commerce.</span><span class="sxs-lookup"><span data-stu-id="c52c8-106">A Bing Maps API key is required and must be added to the shared parameters page in Commerce headquarters.</span></span> <span data-ttu-id="c52c8-107">Los módulos de mapa proporcionan diferentes vistas, como Carretera, Aérea y A pie de calle, que los usuarios pueden seleccionar para ver las ubicaciones de los mapas.</span><span class="sxs-lookup"><span data-stu-id="c52c8-107">Map modules provide different views, such as Road, Aerial, and Streetside, that users can select to view map locations.</span></span> <span data-ttu-id="c52c8-108">También permiten interacciones como hacer zoom y usar la ubicación del usuario.</span><span class="sxs-lookup"><span data-stu-id="c52c8-108">They also allow for interactions such as zooming and using the user's location.</span></span>

<span data-ttu-id="c52c8-109">Un módulo de mapa funciona junto con el módulo selector de tiendas para determinar las ubicaciones geográficas de las tiendas que deben representarse en un mapa.</span><span class="sxs-lookup"><span data-stu-id="c52c8-109">A map module works in conjunction with the store selector module to determine the geographic locations of stores that must be rendered on a map.</span></span> <span data-ttu-id="c52c8-110">El selector de tienda y los módulos de mapa interactúan cuando un usuario selecciona una tienda en uno de esos módulos en una página del sitio.</span><span class="sxs-lookup"><span data-stu-id="c52c8-110">Store selector and map modules interact when a user selects a store in one of those modules on a site page.</span></span> <span data-ttu-id="c52c8-111">Los módulos de mapas se pueden ampliar para otros escenarios, más allá de la interacción con los módulos de selector de tienda.</span><span class="sxs-lookup"><span data-stu-id="c52c8-111">Map modules can be extended for other scenarios, beyond interaction with store selector modules.</span></span> <span data-ttu-id="c52c8-112">Sin embargo, se requiere la personalización del módulo.</span><span class="sxs-lookup"><span data-stu-id="c52c8-112">However, module customization is required.</span></span>

> [!NOTE]
> <span data-ttu-id="c52c8-113">El módulo map está disponible en la versión Dynamics 365 Commerce 10.0.13.</span><span class="sxs-lookup"><span data-stu-id="c52c8-113">The map module is available in the Dynamics 365 Commerce 10.0.13 release.</span></span>

<span data-ttu-id="c52c8-114">La siguiente imagen muestra un ejemplo de un módulo de mapa utilizado en una página ubicación de tiendas.</span><span class="sxs-lookup"><span data-stu-id="c52c8-114">The following image shows an example of a map module that is used on a store locations page.</span></span>

![Ejemplo de un módulo selector de tienda](./media/ecommerce-Storelocator.PNG)

## <a name="module-properties"></a><span data-ttu-id="c52c8-116">Propiedades del módulo</span><span class="sxs-lookup"><span data-stu-id="c52c8-116">Module properties</span></span>

| <span data-ttu-id="c52c8-117">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="c52c8-117">Property name</span></span>             | <span data-ttu-id="c52c8-118">Valor</span><span class="sxs-lookup"><span data-stu-id="c52c8-118">Value</span></span>                 | <span data-ttu-id="c52c8-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="c52c8-119">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="c52c8-120">Cabecera</span><span class="sxs-lookup"><span data-stu-id="c52c8-120">Heading</span></span> | <span data-ttu-id="c52c8-121">Texto</span><span class="sxs-lookup"><span data-stu-id="c52c8-121">Text</span></span> | <span data-ttu-id="c52c8-122">El encabezado del módulo.</span><span class="sxs-lookup"><span data-stu-id="c52c8-122">The heading for the module.</span></span> |
| <span data-ttu-id="c52c8-123">Opciones de chincheta: icono predeterminado</span><span class="sxs-lookup"><span data-stu-id="c52c8-123">Pushpin options: Default icon</span></span> | <span data-ttu-id="c52c8-124">Imagen</span><span class="sxs-lookup"><span data-stu-id="c52c8-124">Image</span></span> | <span data-ttu-id="c52c8-125">La imagen del símbolo de chincheta, que se usará para las tiendas que se aparecen en un mapa.</span><span class="sxs-lookup"><span data-stu-id="c52c8-125">The pushpin symbol image to use for stores that are shown on a map.</span></span> |
| <span data-ttu-id="c52c8-126">Opciones de chincheta: icono activo</span><span class="sxs-lookup"><span data-stu-id="c52c8-126">Pushpin options: Active icon</span></span> | <span data-ttu-id="c52c8-127">Imagen</span><span class="sxs-lookup"><span data-stu-id="c52c8-127">Image</span></span> | <span data-ttu-id="c52c8-128">La imagen del símbolo de chincheta, que se usará para las tiendas seleccionadas en un mapa.</span><span class="sxs-lookup"><span data-stu-id="c52c8-128">The pushpin symbol image to use for a store that is selected on a map.</span></span> |
| <span data-ttu-id="c52c8-129">Opciones de chincheta: color de icono predeterminado</span><span class="sxs-lookup"><span data-stu-id="c52c8-129">Pushpin options: Default icon color</span></span> | <span data-ttu-id="c52c8-130">Cadena de caracteres</span><span class="sxs-lookup"><span data-stu-id="c52c8-130">Character string</span></span> | <span data-ttu-id="c52c8-131">El texto o valor hexadecimal para el color de los símbolos de chincheta en un mapa.</span><span class="sxs-lookup"><span data-stu-id="c52c8-131">The text or hexadecimal value for the color of pushpin symbols on a map.</span></span> |
| <span data-ttu-id="c52c8-132">Opciones de chincheta: color icono activo</span><span class="sxs-lookup"><span data-stu-id="c52c8-132">Pushpin options: Active icon color</span></span> | <span data-ttu-id="c52c8-133">Cadena de caracteres</span><span class="sxs-lookup"><span data-stu-id="c52c8-133">Character string</span></span> | <span data-ttu-id="c52c8-134">El texto o valor hexadecimal para el color de los símbolos de chincheta seleccionados en un mapa.</span><span class="sxs-lookup"><span data-stu-id="c52c8-134">The text or hexadecimal value for the color of selected pushpin symbols on a map.</span></span> |
| <span data-ttu-id="c52c8-135">Mostrar índice</span><span class="sxs-lookup"><span data-stu-id="c52c8-135">Show index</span></span> | <span data-ttu-id="c52c8-136">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="c52c8-136">**True** or **False**</span></span> | <span data-ttu-id="c52c8-137">Si esta propiedad se establece en **True**, cada símbolo de chincheta que indica una tienda mostrará un índice.</span><span class="sxs-lookup"><span data-stu-id="c52c8-137">If this property is set to **True**, every pushpin symbol that indicates a store will show an index.</span></span> <span data-ttu-id="c52c8-138">Este índice coincidirá con el índice en la vista de lista que muestra el módulo selector de tienda.</span><span class="sxs-lookup"><span data-stu-id="c52c8-138">This index will match the index in the list view that the store selector module shows.</span></span> |

## <a name="add-allowed-mapping-urls-to-a-sites-content-security-policy-directives"></a><span data-ttu-id="c52c8-139">Agregar direcciones URL de asignación permitidas a las directivas de política de seguridad de contenido de un sitio</span><span class="sxs-lookup"><span data-stu-id="c52c8-139">Add allowed mapping URLs to a site's content security policy directives</span></span>

<span data-ttu-id="c52c8-140">Para que el módulo de mapas interactúe con Bing Maps, debe asegurarse de que las siguientes direcciones URL de asignación estén permitidas según la directiva de seguridad de contenido (CSP) de su sitio.</span><span class="sxs-lookup"><span data-stu-id="c52c8-140">For the maps module to interact with Bing Maps, you must ensure that the following mapping URLs are allowed per your site's content security policy (CSP).</span></span> <span data-ttu-id="c52c8-141">Esta configuración se realiza en el creador de sitios de Commerce, agregando las direcciones URL permitidas a varias directivas CSP del sitio (por ejemplo, **img-src**).</span><span class="sxs-lookup"><span data-stu-id="c52c8-141">This setup is done in Commerce site builder, by adding allowed URLs to various site CSP directives (for example, **img-src**).</span></span> <span data-ttu-id="c52c8-142">Para más información, consulte [Directiva de seguridad de contenido](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="c52c8-142">For more information, see [Content security policy](manage-csp.md).</span></span> 

- <span data-ttu-id="c52c8-143">Para la directiva **connect-src**, agregue **&#42;.bing.com**.</span><span class="sxs-lookup"><span data-stu-id="c52c8-143">To the **connect-src** directive, add **&#42;.bing.com**.</span></span>
- <span data-ttu-id="c52c8-144">Para la directiva **img-src**, agregue **&#42;.virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="c52c8-144">To the **img-src** directive, add **&#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="c52c8-145">A la directiva **script-src**, agregue **&#42;.bing.com, &#42;.virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="c52c8-145">To the **script-src** directive, add **&#42;.bing.com, &#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="c52c8-146">Para la directiva **script style-src**, agregue **&#42;.bing.com**.</span><span class="sxs-lookup"><span data-stu-id="c52c8-146">To the **script style-src** directive, add **&#42;.bing.com**.</span></span>

## <a name="add-a-map-module-to-a-page"></a><span data-ttu-id="c52c8-147">Agregar un módulo de mapa a una página</span><span class="sxs-lookup"><span data-stu-id="c52c8-147">Add a map module to a page</span></span>

<span data-ttu-id="c52c8-148">Para obtener información detallada sobre cómo configurar un módulo de mapa en una página, vea [Módulo selector de tienda](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="c52c8-148">For detailed information about how to configure a map module on a page, see [Store selector module](store-selector.md).</span></span> 
 
## <a name="additional-resources"></a><span data-ttu-id="c52c8-149">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c52c8-149">Additional resources</span></span>

[<span data-ttu-id="c52c8-150">Visión general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="c52c8-150">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="c52c8-151">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="c52c8-151">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="c52c8-152">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="c52c8-152">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="c52c8-153">Módulo de selector de tienda</span><span class="sxs-lookup"><span data-stu-id="c52c8-153">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="c52c8-154">Administrar Mapas de Bing para su organización</span><span class="sxs-lookup"><span data-stu-id="c52c8-154">Manage Bing Maps for your organization</span></span>](./dev-itpro/manage-bing-maps.md)

[<span data-ttu-id="c52c8-155">Control web de Bing Maps V8</span><span class="sxs-lookup"><span data-stu-id="c52c8-155">Bing Maps V8 Web Control</span></span>](https://docs.microsoft.com/bingmaps/v8-web-control/)


[!INCLUDE[footer-include](../includes/footer-banner.md)]