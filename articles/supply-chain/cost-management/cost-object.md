---
title: Objetos de coste
description: Este artículo proporciona información sobre objetos de costes y explica cómo se acumulan los costes y las cantidades. Un objeto de coste es una entidad para la que se acumulan los costes y las cantidades. Una entidad de objeto de coste puede ser producto o variantes de producto, como variantes para estilo y color.
author: AndersGirke
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 8ee7c170d5a330c0080931a67c1548eb0d3522bb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232407"
---
# <a name="cost-objects"></a><span data-ttu-id="dd232-105">Objetos de coste</span><span class="sxs-lookup"><span data-stu-id="dd232-105">Cost objects</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="dd232-106">Este artículo proporciona información sobre objetos de costes y explica cómo se acumulan los costes y las cantidades.</span><span class="sxs-lookup"><span data-stu-id="dd232-106">This article provides information about costs objects, and explains how costs and quantities are accumulated.</span></span> <span data-ttu-id="dd232-107">Un objeto de coste es una entidad para la que se acumulan los costes y las cantidades.</span><span class="sxs-lookup"><span data-stu-id="dd232-107">A cost object is an entity that costs and quantities are accumulated for.</span></span> <span data-ttu-id="dd232-108">Una entidad de objeto de coste puede ser producto o variantes de producto, como variantes para estilo y color.</span><span class="sxs-lookup"><span data-stu-id="dd232-108">A cost object entity can be either a product or product variants, such as variants for style and color.</span></span>  

## <a name="cost-objects"></a><span data-ttu-id="dd232-109">Objetos de coste</span><span class="sxs-lookup"><span data-stu-id="dd232-109">Cost objects</span></span>

<span data-ttu-id="dd232-110">La página **Objetos de coste** muestra todos los objetos de coste que se registran en un producto.</span><span class="sxs-lookup"><span data-stu-id="dd232-110">The **Cost objects** page lists all cost objects that are registered on a product.</span></span> <span data-ttu-id="dd232-111">Los objetos de coste se definen por datos desde los siguientes orígenes:</span><span class="sxs-lookup"><span data-stu-id="dd232-111">The cost objects are defined by data from the following sources:</span></span>

-   <span data-ttu-id="dd232-112">Producto</span><span class="sxs-lookup"><span data-stu-id="dd232-112">Product</span></span>
-   <span data-ttu-id="dd232-113">Grupo de dimensiones de producto</span><span class="sxs-lookup"><span data-stu-id="dd232-113">Product dimension group</span></span>
-   <span data-ttu-id="dd232-114">Grupo de dimensiones de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="dd232-114">Storage dimension group</span></span>
-   <span data-ttu-id="dd232-115">Grupo de dimensiones de seguimiento</span><span class="sxs-lookup"><span data-stu-id="dd232-115">Tracking dimension group</span></span>

<span data-ttu-id="dd232-116">**Nota:** Un objeto de coste representa un elemento de coste solo del tipo **Material directo**.</span><span class="sxs-lookup"><span data-stu-id="dd232-116">**Note:** A cost object represents a cost element of the **Direct material** type only.</span></span> <span data-ttu-id="dd232-117">Un objeto de coste y un objeto de inventario difieren de la forma en que un objeto de coste está definido por las dimensiones de inventario seleccionadas para el inventario financiero.</span><span class="sxs-lookup"><span data-stu-id="dd232-117">A cost object and an inventory object differ in the way that a cost object is defined by the inventory dimensions that are selected for financial inventory.</span></span> <span data-ttu-id="dd232-118">Por ejemplo, un artículo tiene la configuración siguiente:</span><span class="sxs-lookup"><span data-stu-id="dd232-118">For example, an item has the following configuration:</span></span>

-   <span data-ttu-id="dd232-119">**Sitio:** Inventario físico = Sí, Inventario financiero = Sí</span><span class="sxs-lookup"><span data-stu-id="dd232-119">**Site:** Physical inventory = Yes, Financial inventory = Yes</span></span>
-   <span data-ttu-id="dd232-120">**Almacén:** Inventario físico = Sí, Inventario financiero = No</span><span class="sxs-lookup"><span data-stu-id="dd232-120">**Warehouse:** Physical inventory = Yes, Financial inventory = No</span></span>
-   <span data-ttu-id="dd232-121">**N.º de lote:** Inventario físico = Sí, Inventario financiero = No</span><span class="sxs-lookup"><span data-stu-id="dd232-121">**Batch No.:** Physical inventory = Yes, Financial inventory = No</span></span>

<span data-ttu-id="dd232-122">La tabla siguiente muestra qué es un objeto de coste y qué es un objeto de inventario.</span><span class="sxs-lookup"><span data-stu-id="dd232-122">The following table shows what is a cost object and what is an inventory object.</span></span>

| <span data-ttu-id="dd232-123">Tipo de objeto</span><span class="sxs-lookup"><span data-stu-id="dd232-123">Object type</span></span>      | <span data-ttu-id="dd232-124">Número de artículo</span><span class="sxs-lookup"><span data-stu-id="dd232-124">Item number</span></span> | <span data-ttu-id="dd232-125">Sitio</span><span class="sxs-lookup"><span data-stu-id="dd232-125">Site</span></span> | <span data-ttu-id="dd232-126">Almacén</span><span class="sxs-lookup"><span data-stu-id="dd232-126">Warehouse</span></span> | <span data-ttu-id="dd232-127">N.º de lote</span><span class="sxs-lookup"><span data-stu-id="dd232-127">Batch No.</span></span> |
|------------------|-------------|------|-----------|-----------|
| <span data-ttu-id="dd232-128">Objeto de coste</span><span class="sxs-lookup"><span data-stu-id="dd232-128">Cost object</span></span>      | <span data-ttu-id="dd232-129">x</span><span class="sxs-lookup"><span data-stu-id="dd232-129">x</span></span>           | <span data-ttu-id="dd232-130">x</span><span class="sxs-lookup"><span data-stu-id="dd232-130">x</span></span>    |           |           |
| <span data-ttu-id="dd232-131">Objeto de inventario</span><span class="sxs-lookup"><span data-stu-id="dd232-131">Inventory object</span></span> | <span data-ttu-id="dd232-132">x</span><span class="sxs-lookup"><span data-stu-id="dd232-132">x</span></span>           | <span data-ttu-id="dd232-133">x</span><span class="sxs-lookup"><span data-stu-id="dd232-133">x</span></span>    |  <span data-ttu-id="dd232-134">x</span><span class="sxs-lookup"><span data-stu-id="dd232-134">x</span></span>        | <span data-ttu-id="dd232-135">x</span><span class="sxs-lookup"><span data-stu-id="dd232-135">x</span></span>         |

## <a name="accumulation-of-costs-and-quantities"></a><span data-ttu-id="dd232-136">Acumulación de costes y cantidades</span><span class="sxs-lookup"><span data-stu-id="dd232-136">Accumulation of costs and quantities</span></span>
-   <span data-ttu-id="dd232-137">El valor del campo **Valor** es una suma de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="dd232-137">The value in the **Value** fieldis a sum of the following values:</span></span>
    -   <span data-ttu-id="dd232-138">Importe de coste físico</span><span class="sxs-lookup"><span data-stu-id="dd232-138">Physical cost amount</span></span>
    -   <span data-ttu-id="dd232-139">Importe de coste financiero</span><span class="sxs-lookup"><span data-stu-id="dd232-139">Financial cost amount</span></span>
    -   <span data-ttu-id="dd232-140">Ajustes</span><span class="sxs-lookup"><span data-stu-id="dd232-140">Adjustments</span></span>
-   <span data-ttu-id="dd232-141">El valor del campo **Cantidad** es una suma de los valores siguientes:</span><span class="sxs-lookup"><span data-stu-id="dd232-141">The value in the **Quantity** field is a sum of the following values:</span></span>
    -   <span data-ttu-id="dd232-142">Recibido</span><span class="sxs-lookup"><span data-stu-id="dd232-142">Received</span></span>
    -   <span data-ttu-id="dd232-143">Deducido</span><span class="sxs-lookup"><span data-stu-id="dd232-143">Deducted</span></span>
    -   <span data-ttu-id="dd232-144">Cantidad registrada</span><span class="sxs-lookup"><span data-stu-id="dd232-144">Posted quantity</span></span>
-   <span data-ttu-id="dd232-145">El campo **Coste unitario promedio** es un campo calculado.</span><span class="sxs-lookup"><span data-stu-id="dd232-145">The **Average unit cost** field is a calculated field.</span></span> <span data-ttu-id="dd232-146">El valor se calcula dividiendo el valor **Valor** por el valor **Cantidad**.</span><span class="sxs-lookup"><span data-stu-id="dd232-146">The value is calculated by dividing the **Value** value by the **Quantity** value.</span></span>

<span data-ttu-id="dd232-147">**Nota**: El parámetro **Incluir valor físico en coste** no tiene ningún efecto en los cálculos precedentes.</span><span class="sxs-lookup"><span data-stu-id="dd232-147">**Note:** The \*\*Include physical value \*\*parameter has no effect on the preceding calculations.</span></span>

<a name="additional-resources"></a><span data-ttu-id="dd232-148">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="dd232-148">Additional resources</span></span>
--------

[<span data-ttu-id="dd232-149">Grupo de dimensiones de producto</span><span class="sxs-lookup"><span data-stu-id="dd232-149">Product dimension group</span></span>](https://technet.microsoft.com/library/aa499382.aspx)

[<span data-ttu-id="dd232-150">Grupo de dimensiones de almacenamiento</span><span class="sxs-lookup"><span data-stu-id="dd232-150">Storage dimension group</span></span>](https://technet.microsoft.com/library/hh209317.aspx)

[<span data-ttu-id="dd232-151">Grupo de dimensiones de seguimiento</span><span class="sxs-lookup"><span data-stu-id="dd232-151">Tracking dimension group</span></span>](https://technet.microsoft.com/library/hh209465.aspx)

[<span data-ttu-id="dd232-152">Novedades y cambios</span><span class="sxs-lookup"><span data-stu-id="dd232-152">What's new or changed</span></span>](../../fin-and-ops/get-started/whats-new-changed.md)

[<span data-ttu-id="dd232-153">Entradas de costes</span><span class="sxs-lookup"><span data-stu-id="dd232-153">Cost entries</span></span>](cost-entries.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]