---
title: Calcular el consumo de materiales
description: "En este artículo se proporciona información acerca de las diversas opciones relacionadas con el cálculo del consumo de materiales."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMDesignerEditBOM, BOMTable, ProdBOM
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 53401
ms.assetid: 9cff88e4-0425-4707-9178-3c2cb10df7c2
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f674a1f0051ee4b228b8a92f717ef5348a452bed
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="calculate-material-consumption"></a><span data-ttu-id="4b87d-103">Calcular el consumo de materiales</span><span class="sxs-lookup"><span data-stu-id="4b87d-103">Calculate material consumption</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="4b87d-104">En este artículo se proporciona información acerca de las diversas opciones relacionadas con el cálculo del consumo de materiales.</span><span class="sxs-lookup"><span data-stu-id="4b87d-104">This article provides information about various options that are related to the calculation of material consumption.</span></span> 

<span data-ttu-id="4b87d-105">Las siguientes opciones relacionadas con el cálculo del consumo de materiales están disponibles en las fichas **Configuración** y **Consumo de pasos** en la ficha desplegable **Detalles de línea** de la página **Lista de materiales**.</span><span class="sxs-lookup"><span data-stu-id="4b87d-105">The following options that are related to the calculation of material consumption are available on the **Setup** and **Step consumption** tabs on the **Line details** FastTab of the **Bill of materials** page.</span></span>

## <a name="variable-and-constant-consumption"></a><span data-ttu-id="4b87d-106">Consumo constante y variable</span><span class="sxs-lookup"><span data-stu-id="4b87d-106">Variable and constant consumption</span></span>
<span data-ttu-id="4b87d-107">En el campo **El consumo es** puede seleccionar si el consumo se debe calcular como una cantidad constante o una cantidad variable.</span><span class="sxs-lookup"><span data-stu-id="4b87d-107">In the **Consumption is** field, you can select whether consumption should be calculated as a constant quantity or a variable quantity.</span></span> <span data-ttu-id="4b87d-108">Seleccione **Constante** si se precisa una cantidad o un volumen fijo para la producción, independientemente de la cantidad producida.</span><span class="sxs-lookup"><span data-stu-id="4b87d-108">Select **Constant** if a fixed quantity or volume is required for the production, regardless of the quantity that is produced.</span></span> <span data-ttu-id="4b87d-109">Seleccione **Variable**, el ajuste predeterminado, si la cantidad necesaria de material en los productos terminados es proporcional al número de productos terminados que se produzcan.</span><span class="sxs-lookup"><span data-stu-id="4b87d-109">Select **Variable**, which is the default setting, if the required amount of material in the finished goods is proportional to the number of finished goods that are produced.</span></span>

## <a name="calculating-consumption-from-a-formula"></a><span data-ttu-id="4b87d-110">Cálculo del consumo a partir de una fórmula</span><span class="sxs-lookup"><span data-stu-id="4b87d-110">Calculating consumption from a formula</span></span>
<span data-ttu-id="4b87d-111">En el campo **Fórmula** puede configurar varias fórmulas para calcular el consumo de materiales.</span><span class="sxs-lookup"><span data-stu-id="4b87d-111">In the **Formula** field, you can set up various formulas for calculating material consumption.</span></span> <span data-ttu-id="4b87d-112">Si usa el valor predeterminado **Estándar**, no se calcula el consumo a partir de una fórmula.</span><span class="sxs-lookup"><span data-stu-id="4b87d-112">If you use the default value, **Standard**, the consumption isn't calculated from a formula.</span></span> <span data-ttu-id="4b87d-113">Las fórmulas siguientes funcionan conjuntamente con los campos **Alto**, **Ancho**, **Profundidad**, **Densidad** y **Constante**:</span><span class="sxs-lookup"><span data-stu-id="4b87d-113">The following formulas work together with the **Height**, **Width**, **Depth**, **Density**, and **Constant** fields:</span></span>

-   <span data-ttu-id="4b87d-114">Alto \* Constante</span><span class="sxs-lookup"><span data-stu-id="4b87d-114">Height \* Constant</span></span>
-   <span data-ttu-id="4b87d-115">Alto \* Ancho \* Constante</span><span class="sxs-lookup"><span data-stu-id="4b87d-115">Height \* Width \* Constant</span></span>
-   <span data-ttu-id="4b87d-116">Alto \* Ancho \* Profundidad \* Constante</span><span class="sxs-lookup"><span data-stu-id="4b87d-116">Height \* Width \* Depth \* Constant</span></span>
-   <span data-ttu-id="4b87d-117">(Alto \* Ancho \* Profundidad/Densidad) \* Constante</span><span class="sxs-lookup"><span data-stu-id="4b87d-117">(Height \* Width \* Depth / Density) \* Constant</span></span>

## <a name="rounding-up-and-multiples"></a><span data-ttu-id="4b87d-118">Redondeo y múltiplos</span><span class="sxs-lookup"><span data-stu-id="4b87d-118">Rounding up and multiples</span></span>
<span data-ttu-id="4b87d-119">Juntos, los campos **Redondeo para arriba** y **Múltiplos** permiten redondear hacia arriba del valor del consumo de materiales.</span><span class="sxs-lookup"><span data-stu-id="4b87d-119">Together, the **Rounding up** and **Multiples** fields let you round up the material consumption value.</span></span> <span data-ttu-id="4b87d-120">Por ejemplo, puede redondear el valor en función de la unidad de gestión de material en la que se selecciona la materia prima para producción.</span><span class="sxs-lookup"><span data-stu-id="4b87d-120">For example, you can round up the value according to the handling unit in which the raw material is picked for production.</span></span> <span data-ttu-id="4b87d-121">Las siguientes opciones están disponibles en el campo **Redondeo para arriba**: **Cantidad**, **Medida** y **Consumo**.</span><span class="sxs-lookup"><span data-stu-id="4b87d-121">The following options are available in the **Rounding up** field: **Quantity**, **Measurement**, and **Consumption**.</span></span>

### <a name="quantity"></a><span data-ttu-id="4b87d-122">Cantidad</span><span class="sxs-lookup"><span data-stu-id="4b87d-122">Quantity</span></span>

<span data-ttu-id="4b87d-123">Si selecciona **Cantidad** como mecanismo de redondeo, la cantidad debe ser un múltiplo de la cantidad especificada.</span><span class="sxs-lookup"><span data-stu-id="4b87d-123">If you select **Quantity** as the rounding-up mechanism, the quantity must be a multiple of the specified quantity.</span></span> <span data-ttu-id="4b87d-124">Por ejemplo, si se precisan números enteros, seleccione **1** en el campo **Múltiplos**.</span><span class="sxs-lookup"><span data-stu-id="4b87d-124">For example, if whole numbers are required, select **1** in the **Multiples** field.</span></span> <span data-ttu-id="4b87d-125">Los números se redondean a una cantidad divisible por 1.</span><span class="sxs-lookup"><span data-stu-id="4b87d-125">Numbers are then rounded up to a quantity that is divisible by 1.</span></span>

### <a name="measurement"></a><span data-ttu-id="4b87d-126">Medida</span><span class="sxs-lookup"><span data-stu-id="4b87d-126">Measurement</span></span>

<span data-ttu-id="4b87d-127">Normalmente, se selecciona **Medida** como mecanismo de redondeo cuando la materia prima proviene de dimensiones específicas.</span><span class="sxs-lookup"><span data-stu-id="4b87d-127">Typically, you select **Measurement** as the rounding-up mechanism when the raw material comes in specific dimensions.</span></span> <span data-ttu-id="4b87d-128">Por ejemplo, hace falta una pieza de tubo de metal de dos metros para un producto terminado, y el tubo de metal se almacena en longitudes de 4,5 metros.</span><span class="sxs-lookup"><span data-stu-id="4b87d-128">For example, a piece of 2-meter metal tube is required for a finished good, and the metal tube is stored in 4.5-meter lengths.</span></span> <span data-ttu-id="4b87d-129">En este caso, el mecanismo de redondeo **Medida** se puede usar para calcular cuántos tubos de metal se requieren para producir un número específico de piezas del producto terminado.</span><span class="sxs-lookup"><span data-stu-id="4b87d-129">In this case, the **Measurement** rounding-up mechanism can be used to calculate how many metal tubes are required to produce a specific number of pieces of the finished good.</span></span> <span data-ttu-id="4b87d-130">En este ejemplo, el campo **Fórmula** se ha establecido en **Alto \* Constante**.</span><span class="sxs-lookup"><span data-stu-id="4b87d-130">For this example, the **Formula** field is set to **Height \* Constant**.</span></span> <span data-ttu-id="4b87d-131">El campo **Alto** se ha establecido en **2** para indicar la longitud del tubo necesaria para el producto terminado.</span><span class="sxs-lookup"><span data-stu-id="4b87d-131">The **Height** field is set to **2** to indicate the length of the tube that is required for the finished good.</span></span> <span data-ttu-id="4b87d-132">El campo **Múltiplo** se ha establecido en **4,5** para indicar que el tubo se selecciona en longitudes de 4,5 metros.</span><span class="sxs-lookup"><span data-stu-id="4b87d-132">The **Multiple** field is set to **4.5** to indicate that the tube is picked in lengths of 4.5 meters.</span></span> <span data-ttu-id="4b87d-133">Este es el cálculo:</span><span class="sxs-lookup"><span data-stu-id="4b87d-133">Here is the calculation:</span></span>

1.  <span data-ttu-id="4b87d-134">Número de múltiplos necesarios para 10 piezas del producto terminado: 10 ÷ 2 = 5 piezas</span><span class="sxs-lookup"><span data-stu-id="4b87d-134">Number of multiples that are required for 10 pieces of the finished good: 10 ÷ 2 = 5 pieces</span></span>
2.  <span data-ttu-id="4b87d-135">Consumo total: 4,5 × 5 = 22,5 metros de tubo de metal</span><span class="sxs-lookup"><span data-stu-id="4b87d-135">Total consumption:  4.5 × 5 = 22.5 meters of metal tube</span></span>

<span data-ttu-id="4b87d-136">Se asume que se desechan 0,5 metros de tubo por cada cinco piezas de tubo consumidas.</span><span class="sxs-lookup"><span data-stu-id="4b87d-136">It's assumed that 0.5 meter of tube is scrapped for every five pieces of tube that are consumed.</span></span>

### <a name="consumption"></a><span data-ttu-id="4b87d-137">Consumo</span><span class="sxs-lookup"><span data-stu-id="4b87d-137">Consumption</span></span>

<span data-ttu-id="4b87d-138">Normalmente, se selecciona**Consumo** como mecanismo de redondeo cuando la materia prima se debe seleccionar en cantidades completas de una unidad de gestión de material del producto específico.</span><span class="sxs-lookup"><span data-stu-id="4b87d-138">Typically, you select **Consumption** as the rounding-up mechanism when raw material must be picked in whole quantities of a specific handling unit of the product.</span></span> <span data-ttu-id="4b87d-139">Por ejemplo, se usan dos cuartos de pintura para producir una pieza de un producto terminado, y la pintura se selecciona en botes de 25 cuartos.</span><span class="sxs-lookup"><span data-stu-id="4b87d-139">For example, 2 quarts of paint are used to produce one piece of a finished good, and the paint is picked in 25-quart cans.</span></span> <span data-ttu-id="4b87d-140">En este caso, se puede usar el mecanismo de redondeo **Consumo** para redondear el consumo a números enteros de botes de 25 cuartos de galón.</span><span class="sxs-lookup"><span data-stu-id="4b87d-140">In this case, the **Consumption** rounding-up mechanism can be used to round up consumption to whole numbers of 25-quart cans.</span></span> <span data-ttu-id="4b87d-141">Este es el cálculo de la cantidad de pintura requerida si se deben producir 180 piezas del producto terminado:</span><span class="sxs-lookup"><span data-stu-id="4b87d-141">Here is the calculation for the amount of paint that is required if 180 pieces of the finished good must be produced:</span></span>

1.  <span data-ttu-id="4b87d-142">Pintura necesaria, sin la parte desechada: 180 × 2 = 360 cuartos de galón</span><span class="sxs-lookup"><span data-stu-id="4b87d-142">Paint that is required, excluding scrap: 180 × 2 = 360 quarts</span></span>
2.  <span data-ttu-id="4b87d-143">Número de botes: 360 ÷ 25 = 14,4, que se redondea a 15</span><span class="sxs-lookup"><span data-stu-id="4b87d-143">Number of cans: 360 ÷ 25 = 14.4, which is rounded up to 15</span></span>
3.  <span data-ttu-id="4b87d-144">Pintura necesaria, con la parte desechada: 15 × 25 = 375 cuartos de galón</span><span class="sxs-lookup"><span data-stu-id="4b87d-144">Paint that is required, including scrap: 15 × 25 = 375 quarts</span></span>

## <a name="step-consumption"></a><span data-ttu-id="4b87d-145">Consumo de pasos</span><span class="sxs-lookup"><span data-stu-id="4b87d-145">Step consumption</span></span>
<span data-ttu-id="4b87d-146">El consumo de pasos se usa para calcular el consumo constante en intervalos de cantidad.</span><span class="sxs-lookup"><span data-stu-id="4b87d-146">Step consumption is used to calculate constant consumption in quantity intervals.</span></span> <span data-ttu-id="4b87d-147">Si selecciona **Consumo de pasos** en el campo **Fórmula** de la pestaña **Configuración**, puede agregar información acerca de los pasos en la pestaña **Consumo de pasos**. La cantidad consumida fija se puede configurar en intervalos de la cantidad producida.</span><span class="sxs-lookup"><span data-stu-id="4b87d-147">If you select **Step consumption** in the **Formula** field on the **Setup** tab, you can add information about the steps on the **Step consumption** tab. The fixed consumed quantity can be set up in intervals of the produced quantity.</span></span> <span data-ttu-id="4b87d-148">Por ejemplo, el consumo de pasos se ha configurado como se muestra en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="4b87d-148">For example, step consumption is set up as shown in the following table.</span></span>

| <span data-ttu-id="4b87d-149">Serie inicial</span><span class="sxs-lookup"><span data-stu-id="4b87d-149">From series</span></span> | <span data-ttu-id="4b87d-150">Cantidad</span><span class="sxs-lookup"><span data-stu-id="4b87d-150">Quantity</span></span> |
|-------------|----------|
| <span data-ttu-id="4b87d-151">0,00</span><span class="sxs-lookup"><span data-stu-id="4b87d-151">0.00</span></span>        | <span data-ttu-id="4b87d-152">10,0000</span><span class="sxs-lookup"><span data-stu-id="4b87d-152">10.0000</span></span>  |
| <span data-ttu-id="4b87d-153">100,00</span><span class="sxs-lookup"><span data-stu-id="4b87d-153">100.00</span></span>      | <span data-ttu-id="4b87d-154">20,0000</span><span class="sxs-lookup"><span data-stu-id="4b87d-154">20.0000</span></span>  |
| <span data-ttu-id="4b87d-155">200,00</span><span class="sxs-lookup"><span data-stu-id="4b87d-155">200.00</span></span>      | <span data-ttu-id="4b87d-156">40,0000</span><span class="sxs-lookup"><span data-stu-id="4b87d-156">40.0000</span></span>  |

<span data-ttu-id="4b87d-157">La cantidad de la lista de materiales es 1 y la cantidad de producción es 110.</span><span class="sxs-lookup"><span data-stu-id="4b87d-157">The bill of materials (BOM) quantity is 1, and the production quantity is 110.</span></span> <span data-ttu-id="4b87d-158">La fórmula para el consumo es de (cantidad) de serie = Consumo.</span><span class="sxs-lookup"><span data-stu-id="4b87d-158">The formula for the consumption is From series (Quantity) = Consumption.</span></span> <span data-ttu-id="4b87d-159">Dado que la cantidad de producción es 110, entra en la serie inicial 100.</span><span class="sxs-lookup"><span data-stu-id="4b87d-159">Because the production quantity is 110, it falls into the "From 100 series."</span></span> <span data-ttu-id="4b87d-160">Así pues, la cantidad es 20.</span><span class="sxs-lookup"><span data-stu-id="4b87d-160">Therefore, the quantity is 20.</span></span>




