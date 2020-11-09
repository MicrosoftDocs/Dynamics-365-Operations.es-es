---
title: Módulo del menú de navegación
description: En este tema se tratan los módulos de menú de navegación y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/01/2020
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
ms.openlocfilehash: b0e8168ca9ec9ca68011650a73cc09983deca645
ms.sourcegitcommit: 765056b5dc1d0a8c27e56ff2cbd310ad3349ff09
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2020
ms.locfileid: "4055746"
---
# <a name="navigation-menu-module"></a><span data-ttu-id="159c9-103">Módulo del menú de navegación</span><span class="sxs-lookup"><span data-stu-id="159c9-103">Navigation menu module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="159c9-104">En este tema se tratan los módulos de menú de navegación y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="159c9-104">This topic covers navigation menu modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="159c9-105">Información general</span><span class="sxs-lookup"><span data-stu-id="159c9-105">Overview</span></span>

<span data-ttu-id="159c9-106">El propósito principal de los módulos de menú de navegación es permitir que los usuarios del sitio naveguen por productos y páginas del sitio de acuerdo con la jerarquía de navegación del canal definida en la central de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="159c9-106">The primary purpose of navigation menu modules is to allow site users to browse products and site pages according to the channel navigation hierarchy defined in Dynamics 365 Commerce headquarters.</span></span> <span data-ttu-id="159c9-107">Los elementos configurados en un módulo del menú de navegación aparecen como navegación del encabezado del sitio.</span><span class="sxs-lookup"><span data-stu-id="159c9-107">Items configured in a navigation menu module appear as site header navigation.</span></span> <span data-ttu-id="159c9-108">Los módulos del menú de navegación también admiten elementos de menú estáticos que se vinculan a otras páginas en un sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="159c9-108">Navigation menu modules also support static menu items that link to other pages on an e-Commerce site.</span></span>

<span data-ttu-id="159c9-109">El módulo de menú de navegación se puede agregar al módulo de encabezado de una página.</span><span class="sxs-lookup"><span data-stu-id="159c9-109">The navigation menu module can be added to the header module of a page.</span></span> <span data-ttu-id="159c9-110">En el tema Fabrikam, el menú de navegación muestra dos niveles por defecto.</span><span class="sxs-lookup"><span data-stu-id="159c9-110">In the Fabrikam theme, the navigation menu shows two levels by default.</span></span> <span data-ttu-id="159c9-111">En el tema Starter, el menú de navegación muestra tres niveles por defecto.</span><span class="sxs-lookup"><span data-stu-id="159c9-111">In the Starter theme, the navigation menu shows three levels by default.</span></span> <span data-ttu-id="159c9-112">Para cambiar el número de niveles, se requiere una extensión de vista en el tema.</span><span class="sxs-lookup"><span data-stu-id="159c9-112">To change to the number of levels, a view extension is required on the theme.</span></span>

<span data-ttu-id="159c9-113">La siguiente ilustración muestra un ejemplo de un menú de navegación para el sitio de Fabrikam con dos niveles de jerarquía de categorías y algunos elementos de menú estáticos.</span><span class="sxs-lookup"><span data-stu-id="159c9-113">The following illustration shows an example of a navigation menu for the Fabrikam site with two levels of category hierarchy and some static menu items.</span></span>
<span data-ttu-id="159c9-114">![Ejemplo de un módulo de menú de navegación](./media/ecommerce-header.png)</span><span class="sxs-lookup"><span data-stu-id="159c9-114">![Example of a navigation meu module](./media/ecommerce-header.png)</span></span>

## <a name="navigation-menu-module-properties"></a><span data-ttu-id="159c9-115">Propiedades del módulo del menú de navegación</span><span class="sxs-lookup"><span data-stu-id="159c9-115">Navigation menu module properties</span></span>

| <span data-ttu-id="159c9-116">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="159c9-116">Property name</span></span>             | <span data-ttu-id="159c9-117">Valor</span><span class="sxs-lookup"><span data-stu-id="159c9-117">Value</span></span>                 | <span data-ttu-id="159c9-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="159c9-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="159c9-119">Origen</span><span class="sxs-lookup"><span data-stu-id="159c9-119">Source</span></span>                  | <span data-ttu-id="159c9-120">**Minorista** , **Creación manual** , **Creación minorista y manual**</span><span class="sxs-lookup"><span data-stu-id="159c9-120">**Retail** , **Manual authoring** , **Retail and manual authoring**</span></span> | <span data-ttu-id="159c9-121">El valor **Minorista** permite que la jerarquía de navegación del canal de la sede de Commerce se muestre en el menú de navegación.</span><span class="sxs-lookup"><span data-stu-id="159c9-121">The **Retail** value allows the channel navigation hierarchy from Commerce headquarters to be displayed on the navigation menu.</span></span> <span data-ttu-id="159c9-122">El valor **Autoría manual** permite seleccionar elementos estáticos del menú.</span><span class="sxs-lookup"><span data-stu-id="159c9-122">The **Manual authoring** value allows static menu items to be curated.</span></span> <span data-ttu-id="159c9-123">El valor **Autoría minorista y manual** permite una combinación de ambos.</span><span class="sxs-lookup"><span data-stu-id="159c9-123">The **Retail and manual authoring** value allows a mix of both.</span></span> |
| <span data-ttu-id="159c9-124">Mostrar imágenes de categoría</span><span class="sxs-lookup"><span data-stu-id="159c9-124">Show category images</span></span> | <span data-ttu-id="159c9-125">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="159c9-125">**True** or **False**</span></span>    | <span data-ttu-id="159c9-126">Cuando está habilitada, esta propiedad muestra imágenes de categoría en el menú de navegación como se define en la central de Commerce para cada categoría.</span><span class="sxs-lookup"><span data-stu-id="159c9-126">When enabled, this property displays category images on the navigation menu as defined in Commerce headquarters for each category.</span></span> <span data-ttu-id="159c9-127">Agregado en la versión 10.0.14 de Commerce.</span><span class="sxs-lookup"><span data-stu-id="159c9-127">Added in Commerce release 10.0.14.</span></span> |
| <span data-ttu-id="159c9-128">Habilitar el menú de navegación de varios niveles</span><span class="sxs-lookup"><span data-stu-id="159c9-128">Enable multi-level navigation menu</span></span> | <span data-ttu-id="159c9-129">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="159c9-129">**True** or **False**</span></span> | <span data-ttu-id="159c9-130">Cuando esta propiedad está habilitada, el menú de navegación puede mostrar varios niveles de la jerarquía de navegación.</span><span class="sxs-lookup"><span data-stu-id="159c9-130">When this property is enabled, the navigation menu can show multiple levels of the navigation hierarchy.</span></span> <span data-ttu-id="159c9-131">Esta característica solo está disponible en Dynamics 365 Commerce versión 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="159c9-131">This feature is available in the Dynamics 365 Commerce 10.0.15 release.</span></span> |
| <span data-ttu-id="159c9-132">Número de niveles</span><span class="sxs-lookup"><span data-stu-id="159c9-132">Number of levels</span></span> | <span data-ttu-id="159c9-133">entero</span><span class="sxs-lookup"><span data-stu-id="159c9-133">integer</span></span> | <span data-ttu-id="159c9-134">Esta propiedad define el número de niveles que deben mostrarse si la propiedad **Habilitar el menú de navegación de varios niveles** está establecida en **Verdadero**.</span><span class="sxs-lookup"><span data-stu-id="159c9-134">This property defines the numbers of levels that should be shown if the **Enable multilevel navigation menu** property is set to **True**.</span></span> |
| <span data-ttu-id="159c9-135">Elemento de menú estático</span><span class="sxs-lookup"><span data-stu-id="159c9-135">Static menu item</span></span>| <span data-ttu-id="159c9-136">Matriz de valores</span><span class="sxs-lookup"><span data-stu-id="159c9-136">Array of values</span></span>| <span data-ttu-id="159c9-137">Elementos de menú estáticos que asocian un nombre de elemento de menú con un enlace a una página de sitio estática.</span><span class="sxs-lookup"><span data-stu-id="159c9-137">Static menu items that associate a menu item name with a link to a static site page.</span></span> <span data-ttu-id="159c9-138">Puede crear elementos de menú debajo de otros elementos de menú.</span><span class="sxs-lookup"><span data-stu-id="159c9-138">You can create menu items below other menu items.</span></span> <span data-ttu-id="159c9-139">De forma predeterminada, los menús estáticos aparecen en el nivel raíz y se agregarán a la jerarquía de navegación del canal si existe.</span><span class="sxs-lookup"><span data-stu-id="159c9-139">By default, static menus appear at the root level and will be appended to the channel navigation hierarchy if it exists.</span></span> |
| <span data-ttu-id="159c9-140">Mostrar menú raíz</span><span class="sxs-lookup"><span data-stu-id="159c9-140">Show root menu</span></span> | <span data-ttu-id="159c9-141">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="159c9-141">**True** or **False**</span></span> | <span data-ttu-id="159c9-142">Cuando esta propiedad está habilitada, el menú de navegación se puede definir en una raíz personalizada (por ejemplo, **Comprar ahora** ).</span><span class="sxs-lookup"><span data-stu-id="159c9-142">When this property is enabled, the navigation menu can be defined under a custom root (for example, **Shop now** ).</span></span> <span data-ttu-id="159c9-143">Esta característica solo está disponible en Dynamics 365 Commerce versión 10.0.15.</span><span class="sxs-lookup"><span data-stu-id="159c9-143">This feature is available in the Dynamics 365 Commerce 10.0.15 release.</span></span> |
| <span data-ttu-id="159c9-144">Menú raíz</span><span class="sxs-lookup"><span data-stu-id="159c9-144">Root menu</span></span> | <span data-ttu-id="159c9-145">cadena</span><span class="sxs-lookup"><span data-stu-id="159c9-145">string</span></span> | <span data-ttu-id="159c9-146">Esta propiedad se puede utilizar con el fin de definir texto para una raíz personalizada si la propiedad **Mostrar menú raíz** está establecida en **Verdadero**.</span><span class="sxs-lookup"><span data-stu-id="159c9-146">This property can be used to define text for a custom root if the **Show root menu** property is set to **True**.</span></span> |

<span data-ttu-id="159c9-147">La siguiente ilustración muestra un ejemplo de una imagen de categoría que se muestra en el menú de navegación del sitio de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="159c9-147">The following illustration shows an example of a category image displayed on the navigation menu for the Fabrikam site.</span></span>
<span data-ttu-id="159c9-148">![Ejemplo de un módulo de menú de navegación con imágenes de categoría](./media/ecommerce-categoryimages.PNG)</span><span class="sxs-lookup"><span data-stu-id="159c9-148">![Example of a navigation meu module with category images](./media/ecommerce-categoryimages.PNG)</span></span>

## <a name="add-a-navigation-menu-module-to-a-header-module"></a><span data-ttu-id="159c9-149">Agregar un módulo de menú de navegación a un módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="159c9-149">Add a navigation menu module to a header module</span></span>

<span data-ttu-id="159c9-150">Para obtener detalles sobre cómo agregar un módulo de menú de navegación a un módulo de encabezado, consulte [Módulo de encabezado](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="159c9-150">For details about how to add a navigation menu module to a header module, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="159c9-151">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="159c9-151">Additional resources</span></span>

[<span data-ttu-id="159c9-152">Descripción general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="159c9-152">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="159c9-153">Módulo de navegación</span><span class="sxs-lookup"><span data-stu-id="159c9-153">Breadcrumb module</span></span>](add-breadcrumb.md)

[<span data-ttu-id="159c9-154">Módulo selector de sitio</span><span class="sxs-lookup"><span data-stu-id="159c9-154">Site selector module</span></span>](site-selector.md)

[<span data-ttu-id="159c9-155">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="159c9-155">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="159c9-156">Cumplimiento de cookies</span><span class="sxs-lookup"><span data-stu-id="159c9-156">Cookie compliance</span></span>](cookie-compliance.md)

[<span data-ttu-id="159c9-157">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="159c9-157">Header module</span></span>](author-header-module.md)
