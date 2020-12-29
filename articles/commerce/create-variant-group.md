---
title: Crear un grupo de variantes
description: En este tema se describe cómo crear un grupo de variantes de tamaño, estilo o color para un producto en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: RetailSizeGroupTable, ConfigGroupIdLookup, RetailStyleGroupTable
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 5d9279e1076796bb455429e5ff004c89ec5829e7
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415533"
---
# <a name="create-a-variant-group"></a><span data-ttu-id="9cd35-103">Crear un grupo de variantes</span><span class="sxs-lookup"><span data-stu-id="9cd35-103">Create a variant group</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="9cd35-104">En este tema se describe cómo crear un grupo de variantes de tamaño, estilo o color para un producto en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9cd35-104">This topic describes how to create a size, style, or color variant group for a product in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="9cd35-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="9cd35-105">Overview</span></span>

<span data-ttu-id="9cd35-106">Dynamics 365 Commerce admite múltiples variantes para productos.</span><span class="sxs-lookup"><span data-stu-id="9cd35-106">Dynamics 365 Commerce supports multiple variants for products.</span></span> <span data-ttu-id="9cd35-107">Es ideal para configurar grupos de variantes para diferentes categorías de productos.</span><span class="sxs-lookup"><span data-stu-id="9cd35-107">It is ideal to set up variant groups for different product categories.</span></span> <span data-ttu-id="9cd35-108">Por ejemplo, se puede crear un grupo de tallas de camisetas, con tallas extra pequeñas, pequeñas, medianas, grandes y extra grandes, o se puede crear un grupo de colores para incluir todos los colores disponibles de un producto.</span><span class="sxs-lookup"><span data-stu-id="9cd35-108">For example, a size group can be created for t-shirts with sizes extra small, small, medium, large, and extra large, or a color group could be created to include all available colors of a product.</span></span> <span data-ttu-id="9cd35-109">Se deben agregar los grupos de variantes antes de agregar los productos.</span><span class="sxs-lookup"><span data-stu-id="9cd35-109">Variant groups should be added before products are added.</span></span>

<span data-ttu-id="9cd35-110">En este tema vamos a crear y configurar un grupo de tamaños.</span><span class="sxs-lookup"><span data-stu-id="9cd35-110">In this topic, a size group will be created and configured.</span></span> <span data-ttu-id="9cd35-111">Se pueden usar procedimientos similares para agregar y configurar grupos de estilos y grupos de colores.</span><span class="sxs-lookup"><span data-stu-id="9cd35-111">Similar procedures can be used for adding and configuring style groups and color groups.</span></span>

## <a name="create-a-size-group"></a><span data-ttu-id="9cd35-112">Crear un grupo de tamaños</span><span class="sxs-lookup"><span data-stu-id="9cd35-112">Create a size group</span></span>

<span data-ttu-id="9cd35-113">Para crear un grupo de tamaños, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9cd35-113">To create a size group, follow these steps.</span></span>
 
1. <span data-ttu-id="9cd35-114">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Productos y categorías \> Grupos de variantes \> Grupos de tamaños**.</span><span class="sxs-lookup"><span data-stu-id="9cd35-114">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Variant groups \> Size groups**.</span></span>
1. <span data-ttu-id="9cd35-115">En el panel de acciones, seleccione **Nueva**.</span><span class="sxs-lookup"><span data-stu-id="9cd35-115">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="9cd35-116">En el campo **Grupo de tamaños**, especifique un nombre único para el grupo de tamaños.</span><span class="sxs-lookup"><span data-stu-id="9cd35-116">In the **Size group** box, enter a name for the size group.</span></span>
1. <span data-ttu-id="9cd35-117">Especifique una descripción adecuada en el cuadro **Descripción**.</span><span class="sxs-lookup"><span data-stu-id="9cd35-117">In the **Description** box, enter an appropriate description.</span></span>
1. <span data-ttu-id="9cd35-118">En el panel de acciones, seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="9cd35-118">On the action pane, select **Save**.</span></span>

## <a name="add-attributes-to-the-size-group"></a><span data-ttu-id="9cd35-119">Agregar atributos al grupo de tamaños</span><span class="sxs-lookup"><span data-stu-id="9cd35-119">Add attributes to the size group</span></span>

<span data-ttu-id="9cd35-120">Para agregar atributos a un grupo de tamaños, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9cd35-120">To add attributes to a size group, follow these steps.</span></span>

1. <span data-ttu-id="9cd35-121">En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Productos y categorías \> Grupos de variantes \> Grupos de tamaños**.</span><span class="sxs-lookup"><span data-stu-id="9cd35-121">In the navigation pane, go to **Modules \> Retail and commerce \> Products and categories \> Variant groups \> Size groups**</span></span>
1. <span data-ttu-id="9cd35-122">En el panel de navegación, seleccione un grupo de tamaños.</span><span class="sxs-lookup"><span data-stu-id="9cd35-122">In the navigation pane, select a size group.</span></span>
1. <span data-ttu-id="9cd35-123">En **Líneas de grupo de tamaños**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="9cd35-123">Under **Size group lines**, select **Add**.</span></span>
1. <span data-ttu-id="9cd35-124">En el cuadro **Talla**, especifique una cadena que represente el tamaño (por ejemplo, "XL").</span><span class="sxs-lookup"><span data-stu-id="9cd35-124">In the **Size** box, enter a string representing the size (for example, "XL").</span></span>
1. <span data-ttu-id="9cd35-125">En el cuadro **Nombre del tamaño**, escriba un nombre para el tamaño (por ejemplo, "Extra grande").</span><span class="sxs-lookup"><span data-stu-id="9cd35-125">In the **Size name** box, enter a name for the size (for example, "Extra Large").</span></span>
1. <span data-ttu-id="9cd35-126">En el cuadro **Peso de reabastecimiento**, escriba un número que represente el peso de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="9cd35-126">In the **Replenishment weight** box, enter a number representing the replenishment weight.</span></span>
1. <span data-ttu-id="9cd35-127">En el cuadro **Número del código de barras**, escriba un número que represente el código de barras.</span><span class="sxs-lookup"><span data-stu-id="9cd35-127">In the **Number in bar code** box, enter a number representing the bar code.</span></span>
1. <span data-ttu-id="9cd35-128">En el cuadro **Orden de visualización**, escriba un número que represente el orden de visualización.</span><span class="sxs-lookup"><span data-stu-id="9cd35-128">In the **Display order** box, enter a number representing the display order.</span></span>
1. <span data-ttu-id="9cd35-129">Cuando haya terminado de agregar tamaños, seleccione **Guardar** en el panel de acciones.</span><span class="sxs-lookup"><span data-stu-id="9cd35-129">When finished adding sizes, select **Save** on the action pane.</span></span>

<span data-ttu-id="9cd35-130">La siguiente imagen muestra un ejemplo de grupo de tamaños para "tallas de camisetas informales".</span><span class="sxs-lookup"><span data-stu-id="9cd35-130">The following image shows an example of a size group for "casual shirt sizes".</span></span>

![Crear grupo de tamaños](media/create-variant-group.png)

## <a name="additional-resources"></a><span data-ttu-id="9cd35-132">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9cd35-132">Additional resources</span></span>

[<span data-ttu-id="9cd35-133">Visión general del producto</span><span class="sxs-lookup"><span data-stu-id="9cd35-133">Product information overview</span></span>](../supply-chain/pim/product-information.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="9cd35-134">Configurar productos comerciales</span><span class="sxs-lookup"><span data-stu-id="9cd35-134">Set up retail products</span></span>](set-up-retail-products.md)

[<span data-ttu-id="9cd35-135">Dimensiones de producto</span><span class="sxs-lookup"><span data-stu-id="9cd35-135">Product dimensions</span></span>](../supply-chain/pim/product-dimensions.md?toc=/dynamics365/commerce/toc.json)
