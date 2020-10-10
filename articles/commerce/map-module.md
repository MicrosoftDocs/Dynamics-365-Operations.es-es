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
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: d2cbc67a186a76647a4f7ddc7942b15d3e469ece
ms.sourcegitcommit: 8028fbc5b9585e87d3331ea02577ff82ede090af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "3817215"
---
# <a name="map-module"></a><span data-ttu-id="624f0-103">Módulo de mapa</span><span class="sxs-lookup"><span data-stu-id="624f0-103">Map module</span></span>

[!include [banner](includes/banner.md)]


<span data-ttu-id="624f0-104">En este tema se tratan los módulos de mapa y se describe cómo configurarlos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="624f0-104">This topic covers map modules and describes how to configure them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="624f0-105">Información general</span><span class="sxs-lookup"><span data-stu-id="624f0-105">Overview</span></span>

<span data-ttu-id="624f0-106">Un módulo de mapa muestra las ubicaciones de las tiendas en un mapa interactivo que se representa utilizando el [Control web de Bing Maps V8](https://docs.microsoft.com/bingmaps/v8-web-control/).</span><span class="sxs-lookup"><span data-stu-id="624f0-106">A map module shows the locations of stores on an interactive map that is rendered by using the [Bing Maps V8 Web Control](https://docs.microsoft.com/bingmaps/v8-web-control/).</span></span> <span data-ttu-id="624f0-107">Se requiere una clave de la API de Bing Maps, y debe agregarse a la página de parámetros compartidos en la Central de Commerce.</span><span class="sxs-lookup"><span data-stu-id="624f0-107">A Bing Maps API key is required and must be added to the shared parameters page in Commerce headquarters.</span></span> <span data-ttu-id="624f0-108">Los módulos de mapa proporcionan diferentes vistas, como Carretera, Aérea y A pie de calle, que los usuarios pueden seleccionar para ver las ubicaciones de los mapas.</span><span class="sxs-lookup"><span data-stu-id="624f0-108">Map modules provide different views, such as Road, Aerial, and Streetside, that users can select to view map locations.</span></span> <span data-ttu-id="624f0-109">También permiten interacciones como hacer zoom y usar la ubicación del usuario.</span><span class="sxs-lookup"><span data-stu-id="624f0-109">They also allow for interactions such as zooming and using the user's location.</span></span>

<span data-ttu-id="624f0-110">Un módulo de mapa funciona junto con el módulo selector de tiendas para determinar las ubicaciones geográficas de las tiendas que deben representarse en un mapa.</span><span class="sxs-lookup"><span data-stu-id="624f0-110">A map module works in conjunction with the store selector module to determine the geographic locations of stores that must be rendered on a map.</span></span> <span data-ttu-id="624f0-111">El selector de tienda y los módulos de mapa interactúan cuando un usuario selecciona una tienda en uno de esos módulos en una página del sitio.</span><span class="sxs-lookup"><span data-stu-id="624f0-111">Store selector and map modules interact when a user selects a store in one of those modules on a site page.</span></span> <span data-ttu-id="624f0-112">Los módulos de mapas se pueden ampliar para otros escenarios, más allá de la interacción con los módulos de selector de tienda.</span><span class="sxs-lookup"><span data-stu-id="624f0-112">Map modules can be extended for other scenarios, beyond interaction with store selector modules.</span></span> <span data-ttu-id="624f0-113">Sin embargo, se requiere la personalización del módulo.</span><span class="sxs-lookup"><span data-stu-id="624f0-113">However, module customization is required.</span></span>

> [!NOTE]
> <span data-ttu-id="624f0-114">El módulo map está disponible en la versión Dynamics 365 Commerce 10.0.13.</span><span class="sxs-lookup"><span data-stu-id="624f0-114">The map module is available in the Dynamics 365 Commerce 10.0.13 release.</span></span>

<span data-ttu-id="624f0-115">La siguiente imagen muestra un ejemplo de un módulo de mapa utilizado en una página ubicación de tiendas.</span><span class="sxs-lookup"><span data-stu-id="624f0-115">The following image shows an example of a map module that is used on a store locations page.</span></span>

![Ejemplo de un módulo selector de tienda](./media/ecommerce-Storelocator.PNG)

## <a name="module-properties"></a><span data-ttu-id="624f0-117">Propiedades del módulo</span><span class="sxs-lookup"><span data-stu-id="624f0-117">Module properties</span></span>

| <span data-ttu-id="624f0-118">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="624f0-118">Property name</span></span>             | <span data-ttu-id="624f0-119">Valor</span><span class="sxs-lookup"><span data-stu-id="624f0-119">Value</span></span>                 | <span data-ttu-id="624f0-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="624f0-120">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="624f0-121">Cabecera</span><span class="sxs-lookup"><span data-stu-id="624f0-121">Heading</span></span> | <span data-ttu-id="624f0-122">Texto</span><span class="sxs-lookup"><span data-stu-id="624f0-122">Text</span></span> | <span data-ttu-id="624f0-123">El encabezado del módulo.</span><span class="sxs-lookup"><span data-stu-id="624f0-123">The heading for the module.</span></span> |
| <span data-ttu-id="624f0-124">Opciones de chincheta: icono predeterminado</span><span class="sxs-lookup"><span data-stu-id="624f0-124">Pushpin options: Default icon</span></span> | <span data-ttu-id="624f0-125">Imagen</span><span class="sxs-lookup"><span data-stu-id="624f0-125">Image</span></span> | <span data-ttu-id="624f0-126">La imagen del símbolo de chincheta, que se usará para las tiendas que se aparecen en un mapa.</span><span class="sxs-lookup"><span data-stu-id="624f0-126">The pushpin symbol image to use for stores that are shown on a map.</span></span> |
| <span data-ttu-id="624f0-127">Opciones de chincheta: icono activo</span><span class="sxs-lookup"><span data-stu-id="624f0-127">Pushpin options: Active icon</span></span> | <span data-ttu-id="624f0-128">Imagen</span><span class="sxs-lookup"><span data-stu-id="624f0-128">Image</span></span> | <span data-ttu-id="624f0-129">La imagen del símbolo de chincheta, que se usará para las tiendas seleccionadas en un mapa.</span><span class="sxs-lookup"><span data-stu-id="624f0-129">The pushpin symbol image to use for a store that is selected on a map.</span></span> |
| <span data-ttu-id="624f0-130">Opciones de chincheta: color de icono predeterminado</span><span class="sxs-lookup"><span data-stu-id="624f0-130">Pushpin options: Default icon color</span></span> | <span data-ttu-id="624f0-131">Cadena de caracteres</span><span class="sxs-lookup"><span data-stu-id="624f0-131">Character string</span></span> | <span data-ttu-id="624f0-132">El texto o valor hexadecimal para el color de los símbolos de chincheta en un mapa.</span><span class="sxs-lookup"><span data-stu-id="624f0-132">The text or hexadecimal value for the color of pushpin symbols on a map.</span></span> |
| <span data-ttu-id="624f0-133">Opciones de chincheta: color icono activo</span><span class="sxs-lookup"><span data-stu-id="624f0-133">Pushpin options: Active icon color</span></span> | <span data-ttu-id="624f0-134">Cadena de caracteres</span><span class="sxs-lookup"><span data-stu-id="624f0-134">Character string</span></span> | <span data-ttu-id="624f0-135">El texto o valor hexadecimal para el color de los símbolos de chincheta seleccionados en un mapa.</span><span class="sxs-lookup"><span data-stu-id="624f0-135">The text or hexadecimal value for the color of selected pushpin symbols on a map.</span></span> |
| <span data-ttu-id="624f0-136">Mostrar índice</span><span class="sxs-lookup"><span data-stu-id="624f0-136">Show index</span></span> | <span data-ttu-id="624f0-137">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="624f0-137">**True** or **False**</span></span> | <span data-ttu-id="624f0-138">Si esta propiedad se establece en **True**, cada símbolo de chincheta que indica una tienda mostrará un índice.</span><span class="sxs-lookup"><span data-stu-id="624f0-138">If this property is set to **True**, every pushpin symbol that indicates a store will show an index.</span></span> <span data-ttu-id="624f0-139">Este índice coincidirá con el índice en la vista de lista que muestra el módulo selector de tienda.</span><span class="sxs-lookup"><span data-stu-id="624f0-139">This index will match the index in the list view that the store selector module shows.</span></span> |

## <a name="add-allowed-mapping-urls-to-a-sites-content-security-policy-directives"></a><span data-ttu-id="624f0-140">Agregar direcciones URL de asignación permitidas a las directivas de política de seguridad de contenido de un sitio</span><span class="sxs-lookup"><span data-stu-id="624f0-140">Add allowed mapping URLs to a site's content security policy directives</span></span>

<span data-ttu-id="624f0-141">Para que el módulo de mapas interactúe con Bing Maps, debe asegurarse de que las siguientes direcciones URL de asignación estén permitidas (también conocidas como "pertenecientes a la lista blanca") según la directiva de seguridad de contenido (CSP) de su sitio.</span><span class="sxs-lookup"><span data-stu-id="624f0-141">For the maps module to interact with Bing Maps, you must ensure that the following mapping URLs are allowed (also known as "whitelisted") per your site's content security policy (CSP).</span></span> <span data-ttu-id="624f0-142">Esta configuración se realiza en el creador de sitios de Commerce, agregando las direcciones URL permitidas a varias directivas CSP del sitio (por ejemplo, **img-src**).</span><span class="sxs-lookup"><span data-stu-id="624f0-142">This setup is done in Commerce site builder, by adding allowed URLs to various site CSP directives (for example, **img-src**).</span></span> <span data-ttu-id="624f0-143">Para más información, consulte [Directiva de seguridad de contenido](manage-csp.md).</span><span class="sxs-lookup"><span data-stu-id="624f0-143">For more information, see [Content security policy](manage-csp.md).</span></span> 

- <span data-ttu-id="624f0-144">Para la directiva **connect-src**, agregue **&#42;.bing.com**.</span><span class="sxs-lookup"><span data-stu-id="624f0-144">To the **connect-src** directive, add **&#42;.bing.com**.</span></span>
- <span data-ttu-id="624f0-145">Para la directiva **img-src**, agregue **&#42;.virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="624f0-145">To the **img-src** directive, add **&#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="624f0-146">A la directiva **script-src**, agregue **&#42;.bing.com, &#42;.virtualearth.net**.</span><span class="sxs-lookup"><span data-stu-id="624f0-146">To the **script-src** directive, add **&#42;.bing.com, &#42;.virtualearth.net**.</span></span>
- <span data-ttu-id="624f0-147">Para la directiva **script style-src**, agregue **&#42;.bing.com**.</span><span class="sxs-lookup"><span data-stu-id="624f0-147">To the **script style-src** directive, add **&#42;.bing.com**.</span></span>

## <a name="add-a-map-module-to-a-page"></a><span data-ttu-id="624f0-148">Agregar un módulo de mapa a una página</span><span class="sxs-lookup"><span data-stu-id="624f0-148">Add a map module to a page</span></span>

<span data-ttu-id="624f0-149">Para obtener información detallada sobre cómo configurar un módulo de mapa en una página, vea [Módulo selector de tienda](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="624f0-149">For detailed information about how to configure a map module on a page, see [Store selector module](store-selector.md).</span></span> 
 
## <a name="additional-resources"></a><span data-ttu-id="624f0-150">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="624f0-150">Additional resources</span></span>

[<span data-ttu-id="624f0-151">Visión general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="624f0-151">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="624f0-152">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="624f0-152">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="624f0-153">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="624f0-153">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="624f0-154">Módulo de selector de tienda</span><span class="sxs-lookup"><span data-stu-id="624f0-154">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="624f0-155">Administrar Mapas de Bing para su organización</span><span class="sxs-lookup"><span data-stu-id="624f0-155">Manage Bing Maps for your organization</span></span>](./dev-itpro/manage-bing-maps.md)

[<span data-ttu-id="624f0-156">Control web de Bing Maps V8</span><span class="sxs-lookup"><span data-stu-id="624f0-156">Bing Maps V8 Web Control</span></span>](https://docs.microsoft.com/bingmaps/v8-web-control/)
