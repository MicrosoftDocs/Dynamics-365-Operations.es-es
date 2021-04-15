---
title: Crear un grupo de variantes
description: En este tema se describe cómo crear un grupo de variantes de tamaño, estilo o color para un producto en Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailSizeGroupTable, ConfigGroupIdLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 0462958d8225de145a8d886b096f96cd3f2cb5c5
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799550"
---
# <a name="create-a-variant-group"></a><span data-ttu-id="dbf6e-103">Crear un grupo de variantes</span><span class="sxs-lookup"><span data-stu-id="dbf6e-103">Create a variant group</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="dbf6e-104">En este tema se describe cómo crear un grupo de variantes de tamaño, estilo o color para un producto en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="dbf6e-104">This topic describes how to create a size, style, or color variant group for a product in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="dbf6e-105">Información general</span><span class="sxs-lookup"><span data-stu-id="dbf6e-105">Overview</span></span>

<span data-ttu-id="dbf6e-106">Dynamics 365 Commerce admite múltiples variantes para productos.</span><span class="sxs-lookup"><span data-stu-id="dbf6e-106">Dynamics 365 Commerce supports multiple variants for products.</span></span> <span data-ttu-id="dbf6e-107">Es ideal para configurar grupos de variantes para diferentes categorías de productos.</span><span class="sxs-lookup"><span data-stu-id="dbf6e-107">It is ideal to set up variant groups for different product categories.</span></span> <span data-ttu-id="dbf6e-108">Por ejemplo, se puede crear un grupo de tallas de camisetas, con tallas extra pequeñas, pequeñas, medianas, grandes y extra grandes, o se puede crear un grupo de colores para incluir todos los colores disponibles de un producto.</span><span class="sxs-lookup"><span data-stu-id="dbf6e-108">For example, a size group can be created for t-shirts with sizes extra small, small, medium, large, and extra large, or a color group could be created to include all available colors of a product.</span></span> <span data-ttu-id="dbf6e-109">Se deben agregar los grupos de variantes antes de agregar los productos.</span><span class="sxs-lookup"><span data-stu-id="dbf6e-109">Variant groups should be added before products are added.</span></span>

<span data-ttu-id="dbf6e-110">En este tema vamos a crear y configurar un grupo de tamaños.</span><span class="sxs-lookup"><span data-stu-id="dbf6e-110">In this topic, a size group will be created and configured.</span></span> <span data-ttu-id="dbf6e-111">Se pueden usar procedimientos similares para agregar y configurar grupos de estilos y grupos de colores.</span><span class="sxs-lookup"><span data-stu-id="dbf6e-111">Similar procedures can be used for adding and configuring style groups and color groups.</span></span>

## <a name="create-a-size-group"></a><span data-ttu-id="dbf6e-112">Crear un grupo de tamaños</span><span class="sxs-lookup"><span data-stu-id="dbf6e-112">Create a size group</span></span>

<span data-ttu-id="dbf6e-113">Para crear un grupo de tamaños, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="dbf6e-113">To create a size group, follow these steps.</span></span>
 
1. <span data-ttu-id="dbf6e-114">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Productos y categorías \> Grupos de variantes \> Grupos de tamaños**.</span><span class="sxs-lookup"><span data-stu-id="dbf6e-114">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Variant groups \> Size groups**.</span></span>
1. <span data-ttu-id="dbf6e-115">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="dbf6e-115">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="dbf6e-116">En el campo **Grupo de tamaños**, especifique un nombre único para el grupo de tamaños.</span><span class="sxs-lookup"><span data-stu-id="dbf6e-116">In the **Size group** box, enter a name for the size group.</span></span>
1. <span data-ttu-id="dbf6e-117">Especifique una descripción adecuada en el cuadro **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="dbf6e-117">In the **Description** box, enter an appropriate description.</span></span>
1. <span data-ttu-id="dbf6e-118">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="dbf6e-118">On the action pane, select **Save**.</span></span>

## <a name="add-attributes-to-the-size-group"></a><span data-ttu-id="dbf6e-119">Agregar atributos al grupo de tamaños</span><span class="sxs-lookup"><span data-stu-id="dbf6e-119">Add attributes to the size group</span></span>

<span data-ttu-id="dbf6e-120">Para agregar atributos a un grupo de tamaños, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="dbf6e-120">To add attributes to a size group, follow these steps.</span></span>

1. <span data-ttu-id="dbf6e-121">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Productos y categorías \> Grupos de variantes \> Grupos de tamaños**.</span><span class="sxs-lookup"><span data-stu-id="dbf6e-121">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Variant groups \> Size groups**</span></span>
1. <span data-ttu-id="dbf6e-122">En el panel de navegación, seleccione un grupo de tamaños.</span><span class="sxs-lookup"><span data-stu-id="dbf6e-122">In the navigation pane, select a size group.</span></span>
1. <span data-ttu-id="dbf6e-123">En **Líneas de grupo de tamaños**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="dbf6e-123">Under **Size group lines**, select **Add**.</span></span>
1. <span data-ttu-id="dbf6e-124">En el cuadro **Talla**, especifique una cadena que represente el tamaño (por ejemplo, "XL").</span><span class="sxs-lookup"><span data-stu-id="dbf6e-124">In the **Size** box, enter a string representing the size (for example, "XL").</span></span>
1. <span data-ttu-id="dbf6e-125">En el cuadro **Nombre del tamaño**, escriba un nombre para el tamaño (por ejemplo, "Extra grande").</span><span class="sxs-lookup"><span data-stu-id="dbf6e-125">In the **Size name** box, enter a name for the size (for example, "Extra Large").</span></span>
1. <span data-ttu-id="dbf6e-126">En el cuadro **Peso de reabastecimiento**, escriba un número que represente el peso de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="dbf6e-126">In the **Replenishment weight** box, enter a number representing the replenishment weight.</span></span>
1. <span data-ttu-id="dbf6e-127">En el cuadro **Número del código de barras**, escriba un número que represente el código de barras.</span><span class="sxs-lookup"><span data-stu-id="dbf6e-127">In the **Number in bar code** box, enter a number representing the bar code.</span></span>
1. <span data-ttu-id="dbf6e-128">En el cuadro **Orden de visualización**, escriba un número que represente el orden de visualización.</span><span class="sxs-lookup"><span data-stu-id="dbf6e-128">In the **Display order** box, enter a number representing the display order.</span></span>
1. <span data-ttu-id="dbf6e-129">Cuando haya terminado de agregar tamaños, seleccione **Guardar** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="dbf6e-129">When finished adding sizes, select **Save** on the action pane.</span></span>

<span data-ttu-id="dbf6e-130">La siguiente imagen muestra un ejemplo de grupo de tamaños para "tallas de camisetas informales".</span><span class="sxs-lookup"><span data-stu-id="dbf6e-130">The following image shows an example of a size group for "casual shirt sizes".</span></span>

![Crear grupo de tamaños](media/create-variant-group.png)

## <a name="additional-resources"></a><span data-ttu-id="dbf6e-132">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="dbf6e-132">Additional resources</span></span>

[<span data-ttu-id="dbf6e-133">Visión general del producto</span><span class="sxs-lookup"><span data-stu-id="dbf6e-133">Product information overview</span></span>](../supply-chain/pim/product-information.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="dbf6e-134">Configurar productos comerciales</span><span class="sxs-lookup"><span data-stu-id="dbf6e-134">Set up retail products</span></span>](set-up-retail-products.md)

[<span data-ttu-id="dbf6e-135">Dimensiones de producto</span><span class="sxs-lookup"><span data-stu-id="dbf6e-135">Product dimensions</span></span>](../supply-chain/pim/product-dimensions.md?toc=/dynamics365/commerce/toc.json)


[!INCLUDE[footer-include](../includes/footer-banner.md)]