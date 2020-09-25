---
title: Módulo del menú de navegación
description: En este tema se tratan los módulos de menú de navegación y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
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
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 9f66bbe7bf436ab6360dda7d92d6d51e47eedf16
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761421"
---
# <a name="navigation-menu-module"></a><span data-ttu-id="c514c-103">Módulo del menú de navegación</span><span class="sxs-lookup"><span data-stu-id="c514c-103">Navigation menu module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="c514c-104">En este tema se tratan los módulos de menú de navegación y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c514c-104">This topic covers navigation menu modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c514c-105">Información general</span><span class="sxs-lookup"><span data-stu-id="c514c-105">Overview</span></span>

<span data-ttu-id="c514c-106">El propósito principal de los módulos de menú de navegación es permitir que los usuarios del sitio naveguen por productos y páginas del sitio de acuerdo con la jerarquía de navegación del canal definida en la central de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c514c-106">The primary purpose of navigation menu modules is to allow site users to browse products and site pages according to the channel navigation hierarchy defined in Dynamics 365 Commerce headquarters.</span></span> <span data-ttu-id="c514c-107">Los elementos configurados en un módulo del menú de navegación aparecen como navegación del encabezado del sitio.</span><span class="sxs-lookup"><span data-stu-id="c514c-107">Items configured in a navigation menu module appear as site header navigation.</span></span> <span data-ttu-id="c514c-108">Los módulos del menú de navegación también admiten elementos de menú estáticos que se vinculan a otras páginas en un sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="c514c-108">Navigation menu modules also support static menu items that link to other pages on an e-Commerce site.</span></span>

<span data-ttu-id="c514c-109">El módulo de menú de navegación se puede agregar al módulo de encabezado de una página.</span><span class="sxs-lookup"><span data-stu-id="c514c-109">The navigation menu module can be added to the header module of a page.</span></span> <span data-ttu-id="c514c-110">En el tema Fabrikam, el menú de navegación muestra dos niveles por defecto.</span><span class="sxs-lookup"><span data-stu-id="c514c-110">In the Fabrikam theme, the navigation menu shows two levels by default.</span></span> <span data-ttu-id="c514c-111">En el tema Starter, el menú de navegación muestra tres niveles por defecto.</span><span class="sxs-lookup"><span data-stu-id="c514c-111">In the Starter theme, the navigation menu shows three levels by default.</span></span> <span data-ttu-id="c514c-112">Para cambiar el número de niveles, se requiere una extensión de vista en el tema.</span><span class="sxs-lookup"><span data-stu-id="c514c-112">To change to the number of levels, a view extension is required on the theme.</span></span>

<span data-ttu-id="c514c-113">La siguiente ilustración muestra un ejemplo de un menú de navegación para el sitio de Fabrikam con dos niveles de jerarquía de categorías y algunos elementos de menú estáticos.</span><span class="sxs-lookup"><span data-stu-id="c514c-113">The following illustration shows an example of a navigation menu for the Fabrikam site with two levels of category hierarchy and some static menu items.</span></span>
<span data-ttu-id="c514c-114">![Ejemplo de un módulo de menú de navegación](./media/ecommerce-header.png)</span><span class="sxs-lookup"><span data-stu-id="c514c-114">![Example of a navigation meu module](./media/ecommerce-header.png)</span></span>

## <a name="navigation-menu-module-properties"></a><span data-ttu-id="c514c-115">Propiedades del módulo del menú de navegación</span><span class="sxs-lookup"><span data-stu-id="c514c-115">Navigation menu module properties</span></span>

| <span data-ttu-id="c514c-116">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="c514c-116">Property name</span></span>             | <span data-ttu-id="c514c-117">Valor</span><span class="sxs-lookup"><span data-stu-id="c514c-117">Value</span></span>                 | <span data-ttu-id="c514c-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="c514c-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="c514c-119">Origen</span><span class="sxs-lookup"><span data-stu-id="c514c-119">Source</span></span>                  | <span data-ttu-id="c514c-120">**Minorista**, **Creación manual**, **Creación minorista y manual**</span><span class="sxs-lookup"><span data-stu-id="c514c-120">**Retail**, **Manual authoring**, **Retail and manual authoring**</span></span> | <span data-ttu-id="c514c-121">El valor **Minorista** permite que la jerarquía de navegación del canal de la sede de Commerce se muestre en el menú de navegación.</span><span class="sxs-lookup"><span data-stu-id="c514c-121">The **Retail** value allows the channel navigation hierarchy from Commerce headquarters to be displayed on the navigation menu.</span></span> <span data-ttu-id="c514c-122">El valor **Autoría manual** permite seleccionar elementos estáticos del menú.</span><span class="sxs-lookup"><span data-stu-id="c514c-122">The **Manual authoring** value allows static menu items to be curated.</span></span> <span data-ttu-id="c514c-123">El valor **Autoría minorista y manual** permite una combinación de ambos.</span><span class="sxs-lookup"><span data-stu-id="c514c-123">The **Retail and manual authoring** value allows a mix of both.</span></span> |
| <span data-ttu-id="c514c-124">Mostrar imágenes de categoría</span><span class="sxs-lookup"><span data-stu-id="c514c-124">Show category images</span></span> | <span data-ttu-id="c514c-125">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="c514c-125">**True** or **False**</span></span>    | <span data-ttu-id="c514c-126">Cuando está habilitada, esta propiedad muestra imágenes de categoría en el menú de navegación como se define en la central de Commerce para cada categoría.</span><span class="sxs-lookup"><span data-stu-id="c514c-126">When enabled, this property displays category images on the navigation menu as defined in Commerce headquarters for each category.</span></span> <span data-ttu-id="c514c-127">Agregado en la versión 10.0.14 de Commerce.</span><span class="sxs-lookup"><span data-stu-id="c514c-127">Added in Commerce release 10.0.14.</span></span> |
| <span data-ttu-id="c514c-128">Elemento de menú estático</span><span class="sxs-lookup"><span data-stu-id="c514c-128">Static menu item</span></span>| <span data-ttu-id="c514c-129">Matriz de valores</span><span class="sxs-lookup"><span data-stu-id="c514c-129">Array of values</span></span>| <span data-ttu-id="c514c-130">Elementos de menú estáticos que asocian un nombre de elemento de menú con un enlace a una página de sitio estática.</span><span class="sxs-lookup"><span data-stu-id="c514c-130">Static menu items that associate a menu item name with a link to a static site page.</span></span> <span data-ttu-id="c514c-131">Puede crear elementos de menú debajo de otros elementos de menú.</span><span class="sxs-lookup"><span data-stu-id="c514c-131">You can create menu items below other menu items.</span></span> <span data-ttu-id="c514c-132">De forma predeterminada, los menús estáticos aparecen en el nivel raíz y se agregarán a la jerarquía de navegación del canal si existe.</span><span class="sxs-lookup"><span data-stu-id="c514c-132">By default, static menus appear at the root level and will be appended to the channel navigation hierarchy if it exists.</span></span> |

<span data-ttu-id="c514c-133">La siguiente ilustración muestra un ejemplo de una imagen de categoría que se muestra en el menú de navegación del sitio de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="c514c-133">The following illustration shows an example of a category image displayed on the navigation menu for the Fabrikam site.</span></span>
<span data-ttu-id="c514c-134">![Ejemplo de un módulo de menú de navegación con imágenes de categoría](./media/ecommerce-categoryimages.PNG)</span><span class="sxs-lookup"><span data-stu-id="c514c-134">![Example of a navigation meu module with category images](./media/ecommerce-categoryimages.PNG)</span></span>

## <a name="add-a-navigation-menu-module-to-a-header-module"></a><span data-ttu-id="c514c-135">Agregar un módulo de menú de navegación a un módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="c514c-135">Add a navigation menu module to a header module</span></span>

<span data-ttu-id="c514c-136">Para obtener detalles sobre cómo agregar un módulo de menú de navegación a un módulo de encabezado, consulte [Módulo de encabezado](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="c514c-136">For details about how to add a navigation menu module to a header module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c514c-137">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c514c-137">Additional resources</span></span>

[<span data-ttu-id="c514c-138">Visión general del kit de inicio</span><span class="sxs-lookup"><span data-stu-id="c514c-138">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="c514c-139">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="c514c-139">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="c514c-140">Cumplimiento de cookies</span><span class="sxs-lookup"><span data-stu-id="c514c-140">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="c514c-141">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="c514c-141">Header module</span></span>](author-header-module.md)
