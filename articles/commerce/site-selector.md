---
title: Módulo selector de sitio
description: En este tema se trata el modulo selector de sitio y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/20/2020
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
ms.openlocfilehash: b4e5f715efcac7f883df99508d282db904be0d80
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665232"
---
# <a name="site-selector-module"></a><span data-ttu-id="87e26-103">Módulo selector de sitio</span><span class="sxs-lookup"><span data-stu-id="87e26-103">Site selector module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="87e26-104">En este tema se trata el modulo selector de sitio y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="87e26-104">This topic covers the site selector module and describes how to add it to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="87e26-105">Información general</span><span class="sxs-lookup"><span data-stu-id="87e26-105">Overview</span></span>

<span data-ttu-id="87e26-106">Cuando una empresa tiene diferentes sitios en mercados, regiones y locales, los usuarios del sitio necesitan una forma fácil de cambiar entre sitios y seleccionar su sitio de compras preferido.</span><span class="sxs-lookup"><span data-stu-id="87e26-106">When a business has different sites across markets, regions, and locales, site users need an easy way to switch between sites and select their preferred shopping site.</span></span> <span data-ttu-id="87e26-107">Para hacer posible este escenario, el módulo selector de sitio permite a los usuarios navegar en varios sitios.</span><span class="sxs-lookup"><span data-stu-id="87e26-107">To accommodate this scenario, the site selector module lets users browse across multiple sites.</span></span>

<span data-ttu-id="87e26-108">El módulo selector de sitio debe configurarse con la lista de sitios (mercados, regiones o locales) que los usuarios del sitio pueden explorar.</span><span class="sxs-lookup"><span data-stu-id="87e26-108">The site selector module must be configured with the list of sites (markets, regions, or locales) that site users can browse.</span></span>

> [!NOTE]
> <span data-ttu-id="87e26-109">El módulo selector de sitio está disponible en la versión Dynamics 365 Commerce 10.0.14.</span><span class="sxs-lookup"><span data-stu-id="87e26-109">The site selector module is available in the Dynamics 365 Commerce 10.0.14 release.</span></span>

<span data-ttu-id="87e26-110">La siguiente ilustración muestra un ejemplo de un módulo selector de sitio que aparece en el encabezado de una página de sitio.</span><span class="sxs-lookup"><span data-stu-id="87e26-110">The following illustration shows an example of a site selector module that is featured in the header of a site page.</span></span>

![Ejemplo de un módulo selector de sitio en el encabezado de una página de sitio](./media/ecommerce-sitepicker.PNG)

## <a name="site-selector-module-properties"></a><span data-ttu-id="87e26-112">Propiedades del módulo selector de sitio</span><span class="sxs-lookup"><span data-stu-id="87e26-112">Site selector module properties</span></span>

| <span data-ttu-id="87e26-113">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="87e26-113">Property name</span></span> | <span data-ttu-id="87e26-114">Valor</span><span class="sxs-lookup"><span data-stu-id="87e26-114">Value</span></span>                 | <span data-ttu-id="87e26-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="87e26-115">Description</span></span> |
|---------------|-----------------------|-------------|
| <span data-ttu-id="87e26-116">Cabecera</span><span class="sxs-lookup"><span data-stu-id="87e26-116">Heading</span></span>       | <span data-ttu-id="87e26-117">Texto</span><span class="sxs-lookup"><span data-stu-id="87e26-117">Text</span></span>                  | <span data-ttu-id="87e26-118">El encabezado del módulo.</span><span class="sxs-lookup"><span data-stu-id="87e26-118">The heading for the module.</span></span> |
| <span data-ttu-id="87e26-119">Opciones de sitio</span><span class="sxs-lookup"><span data-stu-id="87e26-119">Site options</span></span>  | <span data-ttu-id="87e26-120">Nombre, imagen, URL</span><span class="sxs-lookup"><span data-stu-id="87e26-120">Name, Image, URL</span></span>      | <span data-ttu-id="87e26-121">Esta propiedad especifica para cada sitio que se incluye en el módulo un nombre, un vínculo a la página de inicio del sitio y una imagen opcional para mostrar.</span><span class="sxs-lookup"><span data-stu-id="87e26-121">This property specifies a name, a link to the site's home page, and an optional image to show for each site that is included in the module.</span></span> <span data-ttu-id="87e26-122">La imagen puede ser una bandera o alguna representación de un mercado, región o localidad.</span><span class="sxs-lookup"><span data-stu-id="87e26-122">The image can be a flag, or some representation of a market, region, or locale.</span></span> |

## <a name="add-a-site-selector-module-to-a-page"></a><span data-ttu-id="87e26-123">Agregar un módulo selector de sitio a una página</span><span class="sxs-lookup"><span data-stu-id="87e26-123">Add a site selector module to a page</span></span>

<span data-ttu-id="87e26-124">El módulo selector de sitio se puede agregar al [Módulo de encabezado](author-header-module.md) debajo de la ranura del selector de sitio.</span><span class="sxs-lookup"><span data-stu-id="87e26-124">The site selector module can be added to the [Header module](author-header-module.md) under the site selector slot.</span></span> <span data-ttu-id="87e26-125">Una vez agregado, puede definir el encabezado del módulo y las opciones del sitio.</span><span class="sxs-lookup"><span data-stu-id="87e26-125">After it's added, you can define the module heading and site options.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="87e26-126">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="87e26-126">Additional resources</span></span>

[<span data-ttu-id="87e26-127">Descripción general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="87e26-127">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="87e26-128">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="87e26-128">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="87e26-129">Módulo de navegación</span><span class="sxs-lookup"><span data-stu-id="87e26-129">Breadcrumb module</span></span>](add-breadcrumb.md)

[<span data-ttu-id="87e26-130">Módulo de menú de navegación</span><span class="sxs-lookup"><span data-stu-id="87e26-130">Navigation menu module</span></span>](nav-menu-module.md)
