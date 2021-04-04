---
title: Artículos fantasma
description: Este tema describe, en detalle, cómo el tipo de línea fantasma puede usarse para las líneas de una lista de materiales (BOM) y una fórmula en Dynamics 365 Supply Chain Management.
author: ShylaThompson
manager: tfehr
ms.date: 06/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SysOperationTemplateForm
audience: Application User
ms.reviewer: kamaybac
ms.custom: 1705903
ms.search.region: Global
ms.author: kamaybac
ms.search.validfrom: ''
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: f927337a317d623ac948e79250343fa6782c20fb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5250390"
---
# <a name="phantom-items"></a><span data-ttu-id="f6b6d-103">Artículos fantasma</span><span class="sxs-lookup"><span data-stu-id="f6b6d-103">Phantom items</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f6b6d-104">Este tema describe, en detalle, cómo el tipo de línea fantasma puede usarse para las líneas de una lista de materiales (BOM) y una fórmula.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-104">This topic describes, in detail, how the Phantom line type can be used for the lines of a bill of materials (BOM) and a formula.</span></span> <span data-ttu-id="f6b6d-105">En la siguiente ilustración, (a) es el L.MAT para el producto H y las parte F y G y (b) es la hoja de ruta de los productos H y la parte F.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-105">In the following illustration, (a) is the BOM for product H and parts F and G, and (b) is the route sheet for products H and part F.</span></span>

![Producto H y parte F](media/product-H-part-F.png)


<span data-ttu-id="f6b6d-107">Esta ilustración muestra un ejemplo de una estructura de L. MAT en dos niveles.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-107">This illustration shows an example of a BOM structure in two levels.</span></span> <span data-ttu-id="f6b6d-108">El producto terminado H representa un producto para un ensamblado de equipo.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-108">Finished product H represents a product for a machine assembly.</span></span> <span data-ttu-id="f6b6d-109">El ensamblado de equipo consta de dos partes, una unidad de iluminación (F) con dos materiales (A y B) y un grupo de materiales de embalaje (G) que también tiene dos materiales (C y D).</span><span class="sxs-lookup"><span data-stu-id="f6b6d-109">The machine assembly consists of two parts, an electrical unit (F) that has two materials (A and B) and a group of packaging materials (G) that also has two materials (C and D).</span></span> <span data-ttu-id="f6b6d-110">Otro material (E) se usa durante el montaje general del equipo.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-110">Another material (E) is used during the general assembly of the machine.</span></span>

![Producto H y parte F](media/product-H-part-B.png)

<span data-ttu-id="f6b6d-112">La ilustración anterior representa el L. MAT de ingeniería del producto H. Esta estructura proporciona una buena visión general de las piezas y los componentes de montaje total del equipo.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-112">The preceding illustration represents the Engineering BOM for product H. This structure provides a good overview of the parts and components of the overall machine assembly.</span></span> <span data-ttu-id="f6b6d-113">Sin embargo, aunque los diseñadores del producto puedan preferir ver la L. MAT representada de esta manera, esta estructura puede que no represente correctamente la forma en que el equipo se construye en planta.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-113">However, although product designers might prefer to see the BOM represented in this way, this structure might not correctly represent the way that the machine is built on the shop floor.</span></span> 

<span data-ttu-id="f6b6d-114">Por ejemplo, la L. MAT de la ilustración anterior indica que la unidad eléctrica F se monta como una parte independiente en un pedido de trabajo individual.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-114">For example, the Engineering BOM in the preceding illustration indicates that electrical unit F is assembled as a separate part on a separate work order.</span></span> <span data-ttu-id="f6b6d-115">Sin embargo, en planta, es posible que se juzgue que es mejor montar la unidad eléctrica como parte del ensamblado total del equipo, no como un pedido de trabajo individual.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-115">However, on the shop floor, it might be judged more optimal to assemble the electrical unit as part of the overall machine assembly, not as a separate work order.</span></span>

<span data-ttu-id="f6b6d-116">Esta L. MAT de ingeniería también indica que la pieza G es una parte independiente.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-116">This Engineering BOM also indicates that part G is a separate part.</span></span> <span data-ttu-id="f6b6d-117">Sin embargo, en esta estructura, la parte G no representa una parte física sino una colección de materiales de embalaje.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-117">However, in this structure, part G doesn’t represent a physical part but a collection of packaging materials.</span></span> 

<span data-ttu-id="f6b6d-118">Por lo tanto, aunque la L. MAT de ingeniería proporciona un gran valor al diseño de un producto y al mantenimiento de dicho diseño, es posible que no sea la forma más lógica de dar soporte al proceso de ejecución de fabricación del producto.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-118">Therefore, although an Engineering BOM provides great value for the design of a product and maintenance of that design, it might not be the most logical way to support the manufacturing execution process of the product.</span></span> <span data-ttu-id="f6b6d-119">Por el contrario, una L. MAT de fabricación representa el mejor modo de crear un producto.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-119">By contrast, a Manufacturing BOM represents the best way to build a product.</span></span>

<span data-ttu-id="f6b6d-120">La ilustración siguiente muestra cómo la L. MAT de ingeniería anterior pasa a ser una L. MAT de fabricación.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-120">The following illustration shows how the preceding Engineering BOM is transitioned into a Manufacturing BOM.</span></span> <span data-ttu-id="f6b6d-121">En este ejemplo, (a) es la L. MAT del producto H, y b es la hoja de ruta del producto H.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-121">In this illustration, (a) is the BOM for product H, and b is the route sheet for product H.</span></span>

<span data-ttu-id="f6b6d-122">En esta estructura, puede ver que no hay noción de las piezas F y G y que los materiales de estas piezas se han elevado al siguiente nivel de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-122">In this structure, you can see that there is no notion of parts F and G, and the materials that these parts consist of have been elevated to the next BOM level.</span></span> 

<span data-ttu-id="f6b6d-123">A diferencia de la lista de materiales de ingeniería, que tenía dos hojas de operaciones, la L. MAT de fabricación solo tiene una hoja de operaciones.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-123">Unlike the Engineering BOM, which had two operations sheets, the Manufacturing BOM has only one operations sheet.</span></span> <span data-ttu-id="f6b6d-124">La operación de embalaja que estaba vinculada a la parte G también se ha elevado y ahora es parte de la hoja de operaciones del producto H. El ensamblado de la unidad de iluminación es la primera operación.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-124">The packaging operation that was linked to part G has also been elevated and is now part of the operations sheet for product H. The assembly of the electrical unit is the first operation.</span></span> <span data-ttu-id="f6b6d-125">Este pedido tiene sentido, porque esta unidad se usa en la siguiente operación, que es el ensamblado de equipo.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-125">This order makes good sense, because this unit is used in the next operation, which is the machine assembly.</span></span> <span data-ttu-id="f6b6d-126">La última operación es la operación de embalaje, que consume dos materiales de embalaje (C y D).</span><span class="sxs-lookup"><span data-stu-id="f6b6d-126">The last operation is the packaging operation, which consumes two packing materials (C and D).</span></span>

<span data-ttu-id="f6b6d-127">La transición entre el MAT de ingeniería y el MAT de fabricación se habilita a través del tipo de línea de L. MAT fantasma.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-127">The transition between the Engineering BOM and the Manufacturing BOM is enabled through the Phantom BOM line type.</span></span> <span data-ttu-id="f6b6d-128">Como el mismo término “fantasma” indica, las partes F G y han desaparecido durante la transición entre los dos tipos de L. MAT.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-128">As the term “phantom” indicates, parts F and G have disappeared during the transition between the two BOM types.</span></span> <span data-ttu-id="f6b6d-129">En este ejemplo, se aplica el tipo de línea fantasma a las L. MAT de las piezas F y G de la L. MAT de ingeniería.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-129">In this example, the Phantom line type is applied to the BOM lines for parts F and G in the Engineering BOM.</span></span> <span data-ttu-id="f6b6d-130">Cuando se crea una producción o un pedido de lote, la L. MAT de ingeniería se copia en el pedido de producción o de lote.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-130">When a production or batch order is created, the Engineering BOM is copied to the production or batch order.</span></span> <span data-ttu-id="f6b6d-131">Posteriormente, cuando se estima el pedido, la transición de la lista de materiales de ingeniería a la L MAT de fabricación se produce, tal como se muestra en las ilustraciones precedentes.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-131">Then, when the order is estimated, the transition from the Engineering BOM to the Manufacturing BOM occurs, as shown in the preceding illustrations.</span></span> <span data-ttu-id="f6b6d-132">En la hoja de operaciones de la segunda ilustración, los materiales de embalaje C y D se introducen para la operación.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-132">From the operations sheet in the second illustration, packaging materials C and D are input for the operation.</span></span> 

## <a name="multilevel-phantom-bom-structures"></a><span data-ttu-id="f6b6d-133">Estructuras L. MAT fantasma de varios niveles</span><span class="sxs-lookup"><span data-stu-id="f6b6d-133">Multilevel phantom BOM structures</span></span>
<span data-ttu-id="f6b6d-134">El tipo de línea fantasma puede usarse en estructuras de varios niveles de L MAT, como se muestra en la siguiente ilustración.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-134">The Phantom line type can be used in multilevel BOM structures, as shown in the following illustration.</span></span> <span data-ttu-id="f6b6d-135">En este ejemplo, (a) es la L. MAT del producto G y (b) es la hoja de ruta de las piezas E y F y el producto G.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-135">In this illustration, (a) is the BOM for product G, and (b) is the route sheet for parts E and F and product G.</span></span> 

![Producto G y parte F con hojas de ruta](media/product-G-route-sheet-G.png)


<span data-ttu-id="f6b6d-137">La ilustración siguiente muestra la L. MAT de fabricación resultante y la hoja de ruta si las líneas de L. MAT de las partes E y F se configuran de modo que el tipo de línea sea fantasma.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-137">The following illustration shows the resulting Manufacturing BOM and route sheet if the BOM lines for parts E and F are configured so that the line type is Phantom.</span></span> <span data-ttu-id="f6b6d-138">En este ejemplo, (a) es la L. MAT del producto G y (b) es la hoja de ruta del producto G.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-138">In this illustration, (a) is the BOM for product G, and (b) is the route sheet for product G.</span></span>

![Producto G](media/product-G.png)


## <a name="phantom-and-route-network"></a><span data-ttu-id="f6b6d-140">Fantasma y red de rutas</span><span class="sxs-lookup"><span data-stu-id="f6b6d-140">Phantom and route network</span></span>
<span data-ttu-id="f6b6d-141">Los L. MAT fantasma también se pueden usar para una L. MAT con una red de rutas.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-141">Phantom BOMs can also be used for a BOM that has a route network.</span></span> <span data-ttu-id="f6b6d-142">En una red de rutas, una o más operaciones se ejecutan en paralelo.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-142">In a route network, one or more operations run in parallel.</span></span> <span data-ttu-id="f6b6d-143">La ilustración siguiente muestra un ejemplo de una red de rutas que se usa en una L. MAT multinivel.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-143">The following illustration shows an example of a route network that is used in a multilevel BOM.</span></span> <span data-ttu-id="f6b6d-144">En este ejemplo, (a) es la L. MAT del producto G y la parte F y (b) es la hoja de ruta del producto G y la parte F, que tiene una red de rutas.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-144">In this illustration, (a) is the BOM for product G and part F, and (b) is the route sheet for product G and part F, which has a route network.</span></span>

![Producto G y parte F](media/product-G-part-F.png)


<span data-ttu-id="f6b6d-146">En la siguiente ilustración, (a) es el la L.MAT del producto G y la parte F y (b) es la hoja de ruta del producto G y la parte F.</span><span class="sxs-lookup"><span data-stu-id="f6b6d-146">In the following illustration, (a) is the BOM for product G and part F, and (b) is the route sheet for product G and part F.</span></span>

![Producto G y parte F con hojas de ruta](media/product-G-part-F-with-route-sheet.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]