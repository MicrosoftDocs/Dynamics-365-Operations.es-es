---
title: Objetos de coste
description: Este artículo proporciona información sobre objetos de costes y explica cómo se acumulan los costes y las cantidades. Un objeto de coste es una entidad para la que se acumulan los costes y las cantidades. Una entidad de objeto de coste puede ser producto o variantes de producto, como variantes para estilo y color.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventCostOnhandItem
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19451
ms.assetid: ec776b98-813a-490d-848f-468452d98fac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c6829f24b8efa29b39f5ed742d8ca99e09bcef01
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910362"
---
# <a name="cost-objects"></a><span data-ttu-id="40136-105">Objetos de coste</span><span class="sxs-lookup"><span data-stu-id="40136-105">Cost objects</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="40136-106">Este artículo proporciona información sobre objetos de costes y explica cómo se acumulan los costes y las cantidades.</span><span class="sxs-lookup"><span data-stu-id="40136-106">This article provides information about costs objects, and explains how costs and quantities are accumulated.</span></span> <span data-ttu-id="40136-107">Un objeto de coste es una entidad para la que se acumulan los costes y las cantidades.</span><span class="sxs-lookup"><span data-stu-id="40136-107">A cost object is an entity that costs and quantities are accumulated for.</span></span> <span data-ttu-id="40136-108">Una entidad de objeto de coste puede ser producto o variantes de producto, como variantes para estilo y color.</span><span class="sxs-lookup"><span data-stu-id="40136-108">A cost object entity can be either a product or product variants, such as variants for style and color.</span></span>  

## <a name="cost-objects"></a><span data-ttu-id="40136-109">Objetos de coste</span><span class="sxs-lookup"><span data-stu-id="40136-109">Cost objects</span></span>

<span data-ttu-id="40136-110">La página **Objetos de coste** muestra todos los objetos de coste que se registran en un producto.</span><span class="sxs-lookup"><span data-stu-id="40136-110">The **Cost objects** page lists all cost objects that are registered on a product.</span></span> <span data-ttu-id="40136-111">Los objetos de coste se definen por datos desde los siguientes orígenes:</span><span class="sxs-lookup"><span data-stu-id="40136-111">The cost objects are defined by data from the following sources:</span></span>

-   <span data-ttu-id="40136-112">Producto</span><span class="sxs-lookup"><span data-stu-id="40136-112">Product</span></span>
-   <span data-ttu-id="40136-113">Grupo de dimensiones de producto</span><span class="sxs-lookup"><span data-stu-id="40136-113">Product dimension group</span></span>
-   <span data-ttu-id="40136-114">Grupo de dimensiones de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="40136-114">Storage dimension group</span></span>
-   <span data-ttu-id="40136-115">Grupo de dimensiones de seguimiento</span><span class="sxs-lookup"><span data-stu-id="40136-115">Tracking dimension group</span></span>

<span data-ttu-id="40136-116">**Nota:** Un objeto de coste representa un elemento de coste solo del tipo **Material directo**.</span><span class="sxs-lookup"><span data-stu-id="40136-116">**Note:** A cost object represents a cost element of the **Direct material** type only.</span></span> <span data-ttu-id="40136-117">Un objeto de coste y un objeto de inventario difieren de la forma en que un objeto de coste está definido por las dimensiones de inventario seleccionadas para el inventario financiero.</span><span class="sxs-lookup"><span data-stu-id="40136-117">A cost object and an inventory object differ in the way that a cost object is defined by the inventory dimensions that are selected for financial inventory.</span></span> <span data-ttu-id="40136-118">Por ejemplo, un artículo tiene la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="40136-118">For example, an item has the following configuration:</span></span>

-   <span data-ttu-id="40136-119">**Sitio:** Inventario físico = Sí, Inventario financiero = Sí</span><span class="sxs-lookup"><span data-stu-id="40136-119">**Site:** Physical inventory = Yes, Financial inventory = Yes</span></span>
-   <span data-ttu-id="40136-120">**Almacén:** Inventario físico = Sí, Inventario financiero = No</span><span class="sxs-lookup"><span data-stu-id="40136-120">**Warehouse:** Physical inventory = Yes, Financial inventory = No</span></span>
-   <span data-ttu-id="40136-121">**N.º de lote:** Inventario físico = Sí, Inventario financiero = No</span><span class="sxs-lookup"><span data-stu-id="40136-121">**Batch No.:** Physical inventory = Yes, Financial inventory = No</span></span>

<span data-ttu-id="40136-122">La tabla siguiente muestra qué es un objeto de coste y qué es un objeto de inventario.</span><span class="sxs-lookup"><span data-stu-id="40136-122">The following table shows what is a cost object and what is an inventory object.</span></span>

| <span data-ttu-id="40136-123">Tipo de objeto</span><span class="sxs-lookup"><span data-stu-id="40136-123">Object type</span></span>      | <span data-ttu-id="40136-124">Número de artículo</span><span class="sxs-lookup"><span data-stu-id="40136-124">Item number</span></span> | <span data-ttu-id="40136-125">Sitio</span><span class="sxs-lookup"><span data-stu-id="40136-125">Site</span></span> | <span data-ttu-id="40136-126">Almacén</span><span class="sxs-lookup"><span data-stu-id="40136-126">Warehouse</span></span> | <span data-ttu-id="40136-127">N.º de lote</span><span class="sxs-lookup"><span data-stu-id="40136-127">Batch No.</span></span> |
|------------------|-------------|------|-----------|-----------|
| <span data-ttu-id="40136-128">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="40136-128">Cost object</span></span>      | <span data-ttu-id="40136-129">x</span><span class="sxs-lookup"><span data-stu-id="40136-129">x</span></span>           | <span data-ttu-id="40136-130">x</span><span class="sxs-lookup"><span data-stu-id="40136-130">x</span></span>    |           |           |
| <span data-ttu-id="40136-131">Objeto de inventario</span><span class="sxs-lookup"><span data-stu-id="40136-131">Inventory object</span></span> | <span data-ttu-id="40136-132">x</span><span class="sxs-lookup"><span data-stu-id="40136-132">x</span></span>           | <span data-ttu-id="40136-133">x</span><span class="sxs-lookup"><span data-stu-id="40136-133">x</span></span>    |  <span data-ttu-id="40136-134">x</span><span class="sxs-lookup"><span data-stu-id="40136-134">x</span></span>        | <span data-ttu-id="40136-135">x</span><span class="sxs-lookup"><span data-stu-id="40136-135">x</span></span>         |

## <a name="accumulation-of-costs-and-quantities"></a><span data-ttu-id="40136-136">Acumulación de costes y cantidades</span><span class="sxs-lookup"><span data-stu-id="40136-136">Accumulation of costs and quantities</span></span>
-   <span data-ttu-id="40136-137">El valor del campo **Valor** es una suma de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="40136-137">The value in the **Value** fieldis a sum of the following values:</span></span>
    -   <span data-ttu-id="40136-138">Importe de coste físico</span><span class="sxs-lookup"><span data-stu-id="40136-138">Physical cost amount</span></span>
    -   <span data-ttu-id="40136-139">Importe de coste financiero</span><span class="sxs-lookup"><span data-stu-id="40136-139">Financial cost amount</span></span>
    -   <span data-ttu-id="40136-140">Ajustes</span><span class="sxs-lookup"><span data-stu-id="40136-140">Adjustments</span></span>
-   <span data-ttu-id="40136-141">El valor del campo **Cantidad** es una suma de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="40136-141">The value in the **Quantity** field is a sum of the following values:</span></span>
    -   <span data-ttu-id="40136-142">Recibido</span><span class="sxs-lookup"><span data-stu-id="40136-142">Received</span></span>
    -   <span data-ttu-id="40136-143">Deducido</span><span class="sxs-lookup"><span data-stu-id="40136-143">Deducted</span></span>
    -   <span data-ttu-id="40136-144">Cantidad registrada</span><span class="sxs-lookup"><span data-stu-id="40136-144">Posted quantity</span></span>
-   <span data-ttu-id="40136-145">El campo **Coste unitario promedio** es un campo calculado.</span><span class="sxs-lookup"><span data-stu-id="40136-145">The **Average unit cost** field is a calculated field.</span></span> <span data-ttu-id="40136-146">El valor se calcula dividiendo el valor **Valor** por el valor **Cantidad**.</span><span class="sxs-lookup"><span data-stu-id="40136-146">The value is calculated by dividing the **Value** value by the **Quantity** value.</span></span>

<span data-ttu-id="40136-147">**Nota**: El parámetro **Incluir valor físico en coste** no tiene ningún efecto en los cálculos precedentes.</span><span class="sxs-lookup"><span data-stu-id="40136-147">**Note:** The \*\*Include physical value \*\*parameter has no effect on the preceding calculations.</span></span>

<a name="additional-resources"></a><span data-ttu-id="40136-148">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="40136-148">Additional resources</span></span>
--------

[<span data-ttu-id="40136-149">Grupo de dimensiones de producto</span><span class="sxs-lookup"><span data-stu-id="40136-149">Product dimension group</span></span>](/dynamicsax-2012/appuser-itpro/about-product-dimensions)

[<span data-ttu-id="40136-150">Grupo de dimensiones de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="40136-150">Storage dimension group</span></span>](/dynamicsax-2012//storage-dimension-groups-form)

[<span data-ttu-id="40136-151">Grupo de dimensiones de seguimiento</span><span class="sxs-lookup"><span data-stu-id="40136-151">Tracking dimension group</span></span>](/dynamicsax-2012//tracking-dimension-groups-form)

[<span data-ttu-id="40136-152">Novedades y cambios</span><span class="sxs-lookup"><span data-stu-id="40136-152">What's new or changed</span></span>](../../fin-ops-core/fin-ops/get-started/whats-new-changed.md)

[<span data-ttu-id="40136-153">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="40136-153">Cost entries</span></span>](cost-entries.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]