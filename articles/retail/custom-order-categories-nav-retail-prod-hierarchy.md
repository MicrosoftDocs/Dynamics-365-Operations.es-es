---
title: Cambiar el orden de clasificación de entidades de comercialización
description: Este tema explica los conceptos relacionados con el control el orden de visualización para diversas entidades relacionadas con la comercialización en Microsoft Dynamics 365 for Retail.
author: ashishharchwani
manager: AnnBe
ms.date: 08/05/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: Category, Retail product hierarchy, Navigation hierarchy
audience: Application User, Merchandising manager, Catalog manager
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 268444
ms.search.region: global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 2be3c1198ac6fff851be1bead2f0995202f1f0e7
ms.sourcegitcommit: e286572ce94a9442a5b3076c3ff5b429be0ed512
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/06/2019
ms.locfileid: "1866170"
---
# <a name="change-the-sort-order-for-merchandising-entities"></a><span data-ttu-id="3db12-103">Cambiar el orden de clasificación de entidades de comercialización</span><span class="sxs-lookup"><span data-stu-id="3db12-103">Change the sort order for merchandising entities</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="3db12-104">Los minoristas consideran el descubrimiento de productos una herramienta principal para la interacción de clientes en todos los canales de venta minorista.</span><span class="sxs-lookup"><span data-stu-id="3db12-104">Retailers consider product discovery a primary tool for customer interaction across all retail channels.</span></span> <span data-ttu-id="3db12-105">La funcionalidad Varios puede ayudar a los clientes a detectar fácilmente productos.</span><span class="sxs-lookup"><span data-stu-id="3db12-105">Various functionality can help customers easily discover products.</span></span> <span data-ttu-id="3db12-106">Por ejemplo, pueden examinar categorías, buscar y filtrar.</span><span class="sxs-lookup"><span data-stu-id="3db12-106">For example, they can browse categories, search, and filter.</span></span>

<span data-ttu-id="3db12-107">Este tema explica los conceptos relacionados con el control el orden de visualización para diversas entidades relacionadas con la comercialización.</span><span class="sxs-lookup"><span data-stu-id="3db12-107">This topic explains the concepts that are related to controlling the display order for various merchandising-related entities.</span></span> <span data-ttu-id="3db12-108">También explica cómo cambiar el orden de clasificación.</span><span class="sxs-lookup"><span data-stu-id="3db12-108">It also explains how to change the sort order.</span></span>

## <a name="overview"></a><span data-ttu-id="3db12-109">Información general</span><span class="sxs-lookup"><span data-stu-id="3db12-109">Overview</span></span>

<span data-ttu-id="3db12-110">La compatibilidad para clasificar diversas entidades relacionadas con la comercialización se ha ampliado.</span><span class="sxs-lookup"><span data-stu-id="3db12-110">The support for sorting various merchandising-related entities has been enhanced.</span></span> <span data-ttu-id="3db12-111">Esta compatibilidad está ahora mejor alineada con los escenarios existentes de clientes, que requerían anteriormente extensiones por parte de socios de implementación.</span><span class="sxs-lookup"><span data-stu-id="3db12-111">This support is now better aligned with existing customer scenarios that previously required extensions from implementation partners.</span></span>

<span data-ttu-id="3db12-112">En las versiones de Microsoft Dynamics 365 for Retail anteriores a la versión 10.0.5, el criterio de clasificación para las categorías de la jerarquía de navegación era alfabético.</span><span class="sxs-lookup"><span data-stu-id="3db12-112">In versions of Microsoft Dynamics 365 for Retail that are earlier than version 10.0.5, the sort order for categories in the navigation hierarchy was alphabetical.</span></span> <span data-ttu-id="3db12-113">La nueva funcionalidad personalizada del orden de clasificación permite a los encargados de comercialización configurar el orden de clasificación para diversas entidades relacionadas con la comercialización en todos los clientes de usuario final.</span><span class="sxs-lookup"><span data-stu-id="3db12-113">The new custom sort order functionality lets merchandising managers configure the sort order for various merchandising-related entities across all end-user clients.</span></span> <span data-ttu-id="3db12-114">Estos clientes incluyen sedes empresariales y centros de llamadas.</span><span class="sxs-lookup"><span data-stu-id="3db12-114">These clients include headquarters (HQ) and call centers.</span></span>

## <a name="configure-the-display-order-for-categories-in-the-retail-product-hierarchy"></a><span data-ttu-id="3db12-115">Configurar el orden de visualización para las categorías de la jerarquía de productos</span><span class="sxs-lookup"><span data-stu-id="3db12-115">Configure the display order for categories in the retail product hierarchy</span></span>

<span data-ttu-id="3db12-116">Antes de poder completar este procedimiento, los datos de prueba se deben instalar en el entorno.</span><span class="sxs-lookup"><span data-stu-id="3db12-116">Before you can complete this procedure, demo data must be installed in your environment.</span></span>

1. <span data-ttu-id="3db12-117">Vaya al **Ventas minoristas** \> Productos y categorías \> Jerarquía de productos comerciales.</span><span class="sxs-lookup"><span data-stu-id="3db12-117">Go to **Retail \> Products and categories \> Retail product hierarchy**.</span></span>
2. <span data-ttu-id="3db12-118">Haga clic en **Editar jerarquía de categoría**.</span><span class="sxs-lookup"><span data-stu-id="3db12-118">Click **Edit category hierarchy**.</span></span>
3. <span data-ttu-id="3db12-119">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3db12-119">Click **Edit**.</span></span>
4. <span data-ttu-id="3db12-120">En el árbol, expanda **ALL \> Action Sports**.</span><span class="sxs-lookup"><span data-stu-id="3db12-120">In the tree, expand **ALL \> Action Sports**.</span></span>
5. <span data-ttu-id="3db12-121">En el árbol, expanda **ALL \> Team Sports**.</span><span class="sxs-lookup"><span data-stu-id="3db12-121">In the tree, expand **ALL \> Team Sports**.</span></span>
6. <span data-ttu-id="3db12-122">En el campo **Orden de visualización**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="3db12-122">In the **Display order** field, enter a number.</span></span> <span data-ttu-id="3db12-123">(El número puede ser negativo).</span><span class="sxs-lookup"><span data-stu-id="3db12-123">(The number can be negative.)</span></span>
7. <span data-ttu-id="3db12-124">Repita los pasos del 4 al 6 para todas las categorías adicionales para las que desee cambiar el orden.</span><span class="sxs-lookup"><span data-stu-id="3db12-124">Repeat steps 4 through 6 for any additional categories that you want to change the order of.</span></span>

<span data-ttu-id="3db12-125">El orden de visualización para la jerarquía de navegación de canal se reflejará en la sede para la jerarquía de productos comerciales y productos liberados por categoría.</span><span class="sxs-lookup"><span data-stu-id="3db12-125">The display order for the channel navigation hierarchy will be reflected in HQ for the retail product hierarchy and released products by category.</span></span>

![Jerarquía de productos comerciales ordenada de forma personalizada con valores negativos](./media/RetailProductHierarchyCustomSortedWithNegativeValues.png)

![Productos liberados por categoría ordenados de forma personalizada en función de la jerarquía de productos](./media/ReleasedProductsByCategoryCustomSortedBasedOnRetailProductHierarchy.png)

## <a name="configure-the-display-order-for-categories-in-the-channel-navigation-hierarchy"></a><span data-ttu-id="3db12-128">Configurar el orden de visualización para las categorías de la jerarquía de navegación de canales</span><span class="sxs-lookup"><span data-stu-id="3db12-128">Configure the display order for categories in the channel navigation hierarchy</span></span>

<span data-ttu-id="3db12-129">Antes de poder completar este procedimiento, los datos de prueba se deben instalar en el entorno.</span><span class="sxs-lookup"><span data-stu-id="3db12-129">Before you can complete this procedure, demo data must be installed in your environment.</span></span>

1. <span data-ttu-id="3db12-130">Vaya a **Venta minorista \> Productos y categorías \> Categorías de navegación de canales**.</span><span class="sxs-lookup"><span data-stu-id="3db12-130">Go to **Retail \> Products and categories \> Channel navigation categories**.</span></span>
2. <span data-ttu-id="3db12-131">En la lista, seleccione la jerarquía **Navegación de moda** .</span><span class="sxs-lookup"><span data-stu-id="3db12-131">In the list, select the **Fashion navigation** hierarchy.</span></span>
3. <span data-ttu-id="3db12-132">Haga clic en **Editar jerarquía de categoría**.</span><span class="sxs-lookup"><span data-stu-id="3db12-132">Click **Edit category hierarchy**.</span></span>
4. <span data-ttu-id="3db12-133">Haga clic en **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3db12-133">Click **Edit**.</span></span>
5. <span data-ttu-id="3db12-134">En el árbol seleccione, **Fashion \> Womenswear \> Womens Shoes**.</span><span class="sxs-lookup"><span data-stu-id="3db12-134">In the tree, select **Fashion \> Womenswear \> Womens Shoes**.</span></span>
6. <span data-ttu-id="3db12-135">En el campo **Orden de visualización**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="3db12-135">In the **Display order** field, enter a number.</span></span>
7. <span data-ttu-id="3db12-136">En el árbol seleccione, **Fashion \> Womenswear \> Tops**.</span><span class="sxs-lookup"><span data-stu-id="3db12-136">In the tree, select **Fashion \> Womenswear \> Tops**.</span></span>

    <span data-ttu-id="3db12-137">Del mismo modo, puede definir el orden de clasificación para las categorías secundarias.</span><span class="sxs-lookup"><span data-stu-id="3db12-137">Likewise, you can define the sort order for the sub-categories.</span></span>

8. <span data-ttu-id="3db12-138">En el árbol seleccione, **Fashion \> Menswear \> Casual Shirts**.</span><span class="sxs-lookup"><span data-stu-id="3db12-138">In the tree, select **Fashion \> Menswear \> Casual Shirts**.</span></span>
9. <span data-ttu-id="3db12-139">En el campo **Orden de visualización**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="3db12-139">In the **Display order** field, enter a number.</span></span>
10. <span data-ttu-id="3db12-140">En el árbol seleccione, **Fashion \> Menswear \> Coats & Jackets**.</span><span class="sxs-lookup"><span data-stu-id="3db12-140">In the tree, select **Fashion \> Menswear \> Coats & Jackets**.</span></span>
11. <span data-ttu-id="3db12-141">En el campo **Orden de visualización**, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="3db12-141">In the **Display order** field, enter a number.</span></span>
12. <span data-ttu-id="3db12-142">Repita los pasos para todas las categorías adicionales para las que desee cambiar el orden.</span><span class="sxs-lookup"><span data-stu-id="3db12-142">Repeat for any additional categories that you want to change the order of.</span></span>

<span data-ttu-id="3db12-143">El orden de visualización para la jerarquía de navegación de canales se refleja en la sede, el catálogo y canales comerciales.</span><span class="sxs-lookup"><span data-stu-id="3db12-143">The display order for the channel navigation hierarchy is reflected in HQ, catalog, and retail channels.</span></span>

![Jerarquía de navegación de canales ordenada de forma personalizada](./media/ChannelNavCustomSorted.png)

![Jerarquía de navegación de catálogos ordenada de forma personalizada en función de la jerarquía de navegación de canales](./media/CatalogNavHierarchyCustomSortedBasedOnChannelNav.png)

![PDV con categorías ordenadas de forma personalizada](./media/POSChannelCategoriesCustomSorted.png)

> [!NOTE]
> <span data-ttu-id="3db12-147">De forma predeterminada, la característica de orden de clasificación personalizado está desactivada.</span><span class="sxs-lookup"><span data-stu-id="3db12-147">By default the custom sort order feature is turned off.</span></span> <span data-ttu-id="3db12-148">Para obtener información sobre cómo activar esta característica y otras, consulte [Administración de características](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).</span><span class="sxs-lookup"><span data-stu-id="3db12-148">To learn how to turn on this feature and other features, see [Feature management](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/get-started/feature-management/feature-management-overview).</span></span>
