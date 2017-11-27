---
title: "Índices de impuestos en función de la base marginal y los métodos de cálculo"
description: "Este tema explica cómo los valores de los campos Base marginal y Método de cálculo determinan los índices de impuestos en transacciones de compras y ventas."
author: twheeloc
manager: AnnBe
ms.date: 10/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 7171
ms.assetid: 381fc309-b32a-4927-b5b8-fa1c31b0bd72
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: bf0f8f2e3f553ea181e8cc9ab5b712fce64a89d4
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="sales-tax-rates-based-on-the-marginal-base-and-calculation-methods"></a><span data-ttu-id="c86fe-103">Índices de impuestos en función de la base marginal y los métodos de cálculo</span><span class="sxs-lookup"><span data-stu-id="c86fe-103">Sales tax rates based on the Marginal base and Calculation methods</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="c86fe-104">Este tema explica cómo los valores de los campos Base marginal y Método de cálculo determinan los índices de impuestos en transacciones de compras y ventas.</span><span class="sxs-lookup"><span data-stu-id="c86fe-104">This topic explains how the values in the fields Marginal base and Calculation method determine the tax rate(s) in sales and purchase transactions.</span></span>

<span data-ttu-id="c86fe-105">La base marginal en la ficha desplegable Cálculo de la página Códigos de impuestos determina qué importe usar para seleccionar las tasas de impuestos adecuadas para los índices en la página Valores de código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="c86fe-105">The Marginal base on the Calculation FastTab on the Sales tax codes page determines which amount is used to pick the appropriate tax rate(s) from the rates in the Sales tax code values page.</span></span> <span data-ttu-id="c86fe-106">El tipo de importe en el campo Base marginal, junto con el método del campo Método de cálculo, determinan la lógica para buscar las tasas de impuestos correctas para una transacción.</span><span class="sxs-lookup"><span data-stu-id="c86fe-106">The amount type in the Marginal base field in combination with the method in the Calculation method field determines the logic to find the correct tax rate(s) for a transaction.</span></span> 

<span data-ttu-id="c86fe-107">Las distintas combinaciones de los valores de estos campos permiten obtener cálculos de impuestos muy diferentes, tal y como se muestra en los siguientes ejemplos.</span><span class="sxs-lookup"><span data-stu-id="c86fe-107">Various combinations of values in these fields produce very different sales tax calculations, as shown by the following examples.</span></span> <span data-ttu-id="c86fe-108">En estos ejemplos se utilizan los mismos valores de intervalo de impuestos, los cuales se configuran para cada código de impuestos en la página Valores de códigos de impuestos.</span><span class="sxs-lookup"><span data-stu-id="c86fe-108">The examples use the same tax interval values, which are set up for each tax code in the Sales tax codes values page.</span></span> <span data-ttu-id="c86fe-109">Para abrir esta página, haga clic en Código de impuestos &gt; Valores en la página Códigos de impuestos.</span><span class="sxs-lookup"><span data-stu-id="c86fe-109">To open this page, click Sales tax code &gt; Values in the Sales tax codes page.</span></span>

> [!Important]                                                                                                                  
> <span data-ttu-id="c86fe-110">Si la base marginal de uno o más de los códigos de impuestos se basa en unidades o importes de línea, el valor del campo Método de cálculo de la página Parámetros de contabilidad general se debe establecer en Línea.</span><span class="sxs-lookup"><span data-stu-id="c86fe-110">If the Marginal base on one or more of your sales tax codes is based on line amounts or units, the value of the Calculation method field in the General ledger parameters page must be set to Line.</span></span> |

## <a name="net-amount-per-line"></a><span data-ttu-id="c86fe-111"> Importe neto por línea</span><span class="sxs-lookup"><span data-stu-id="c86fe-111">Net amount per line</span></span>
<span data-ttu-id="c86fe-112">Seleccione esta opción para determinar las tasas de impuestos en base al importe neto de las líneas de la factura, sin incluir los demás impuestos.</span><span class="sxs-lookup"><span data-stu-id="c86fe-112">Select this option to determine sales tax rates based on the net amount for the invoice lines, excluding any other taxes.</span></span>

### <a name="example"></a><span data-ttu-id="c86fe-113">ejemplo</span><span class="sxs-lookup"><span data-stu-id="c86fe-113">Example</span></span>

<span data-ttu-id="c86fe-114">Los índices de impuestos se configuran en los siguientes intervalos.</span><span class="sxs-lookup"><span data-stu-id="c86fe-114">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="c86fe-115">Intervalo de importe</span><span class="sxs-lookup"><span data-stu-id="c86fe-115">Amount interval</span></span>    | <span data-ttu-id="c86fe-116">Índice de impuestos</span><span class="sxs-lookup"><span data-stu-id="c86fe-116">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="c86fe-117">0 - 50</span><span class="sxs-lookup"><span data-stu-id="c86fe-117">0 - 50</span></span>             | <span data-ttu-id="c86fe-118">30%</span><span class="sxs-lookup"><span data-stu-id="c86fe-118">30%</span></span>      |
| <span data-ttu-id="c86fe-119">50 - 100</span><span class="sxs-lookup"><span data-stu-id="c86fe-119">50 - 100</span></span>           | <span data-ttu-id="c86fe-120">20%</span><span class="sxs-lookup"><span data-stu-id="c86fe-120">20%</span></span>      |
| <span data-ttu-id="c86fe-121">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="c86fe-121">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="c86fe-122">10%</span><span class="sxs-lookup"><span data-stu-id="c86fe-122">10%</span></span>      |

> [!NOTE]                                                                                                             
> <span data-ttu-id="c86fe-123">El límite superior de cero (0) del último intervalo quiere decir que todos los importes superiores a 100 se incluyen en el intervalo.</span><span class="sxs-lookup"><span data-stu-id="c86fe-123">The upper limit of zero (0) in the last interval means that all amounts that exceed 100 are included in the interval.</span></span>

<span data-ttu-id="c86fe-124">Base marginal: **Importe neto por línea**</span><span class="sxs-lookup"><span data-stu-id="c86fe-124">Marginal base: **Net amount per line**</span></span> 

<span data-ttu-id="c86fe-125">Método de cálculo: **Intervalo**</span><span class="sxs-lookup"><span data-stu-id="c86fe-125">Calculation method: **Interval**</span></span> 

<span data-ttu-id="c86fe-126">Supongamos que compra 8 lámparas que cuestan 25,00 cada una.</span><span class="sxs-lookup"><span data-stu-id="c86fe-126">You buy 8 lamps that cost 25.00 each.</span></span> 

<span data-ttu-id="c86fe-127">El importe neto de la línea de factura es 200,00.</span><span class="sxs-lookup"><span data-stu-id="c86fe-127">The net amount for the invoice line is 200.00.</span></span> 

<span data-ttu-id="c86fe-128">El impuesto se calcula del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c86fe-128">The tax is calculated as follows:</span></span> 

<span data-ttu-id="c86fe-129">Importe total de impuestos = 50 x 30% + 50 x 20% + 100 x 10% = 15 + 10 + 10 = 35,00.</span><span class="sxs-lookup"><span data-stu-id="c86fe-129">Total sales tax = 50 x 30% + 50 x 20% + 100 x 10% = 15 + 10 + 10 = 35.00</span></span> 

<span data-ttu-id="c86fe-130">Importe total de la factura = 200,00 + 35,00 = 235,00.</span><span class="sxs-lookup"><span data-stu-id="c86fe-130">Total invoice amount = 200.00 + 35.00 = 235.00</span></span> 

<span data-ttu-id="c86fe-131">**Variación**</span><span class="sxs-lookup"><span data-stu-id="c86fe-131">**Variation**</span></span> 

<span data-ttu-id="c86fe-132">Si la factura tiene dos líneas de cuatro artículos en cada línea, el importe neto por línea es 100,00 y los impuestos se calculan del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="c86fe-132">If the invoice has two lines with four items on each line, the net amount on each line is 100.00 and the sales tax is calculated as follows:</span></span> 

<span data-ttu-id="c86fe-133">Línea 1 de impuestos = 50 x 30% + 50 x 20% = 15 + 10 = 25,00.</span><span class="sxs-lookup"><span data-stu-id="c86fe-133">Sales tax line 1 = 50 x 30% + 50 x 20% = 15 + 10 = 25.00</span></span> 

<span data-ttu-id="c86fe-134">Línea 2 de impuestos = 50 x 30% + 50 x 20% = 15 + 10 = 25,00.</span><span class="sxs-lookup"><span data-stu-id="c86fe-134">Sales tax line 2 = 50 x 30% + 50 x 20% = 15 + 10 = 25.00</span></span> 

<span data-ttu-id="c86fe-135">Total de impuestos = 25,00 + 25,00 = 50,00</span><span class="sxs-lookup"><span data-stu-id="c86fe-135">Total sales tax = 25.00 + 25.00 = 50.00</span></span> 

<span data-ttu-id="c86fe-136">Importe total de la factura = 200,00 + 50,00 = 250,00.</span><span class="sxs-lookup"><span data-stu-id="c86fe-136">Total invoice amount = 200.00 + 50.00 = 250.00</span></span>

## <a name="net-amount-per-unit"></a><span data-ttu-id="c86fe-137"> Importe neto por unidad</span><span class="sxs-lookup"><span data-stu-id="c86fe-137">Net amount per unit</span></span>
<span data-ttu-id="c86fe-138">Seleccione esta opción para determinar las tasas de impuestos en base al valor de cada unidad, sin incluir los demás impuestos.</span><span class="sxs-lookup"><span data-stu-id="c86fe-138">Select this option to determine sales tax rates based on the value of each unit, excluding any other taxes.</span></span> <span data-ttu-id="c86fe-139">Cuando se selecciona una base marginal basada en unidad, también se tiene que especificar una unidad para el código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="c86fe-139">When a unit based Marginal base is selected then also a Unit has to be specified for the Sales tax code.</span></span>

### <a name="example"></a><span data-ttu-id="c86fe-140">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c86fe-140">Example</span></span>

<span data-ttu-id="c86fe-141">Los índices de impuestos se configuran en los siguientes intervalos.</span><span class="sxs-lookup"><span data-stu-id="c86fe-141">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="c86fe-142">Importe</span><span class="sxs-lookup"><span data-stu-id="c86fe-142">Amount</span></span>             | <span data-ttu-id="c86fe-143">Índice de impuestos</span><span class="sxs-lookup"><span data-stu-id="c86fe-143">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="c86fe-144">0 - 50</span><span class="sxs-lookup"><span data-stu-id="c86fe-144">0 - 50</span></span>             | <span data-ttu-id="c86fe-145">30%</span><span class="sxs-lookup"><span data-stu-id="c86fe-145">30%</span></span>      |
| <span data-ttu-id="c86fe-146">50 - 100</span><span class="sxs-lookup"><span data-stu-id="c86fe-146">50 - 100</span></span>           | <span data-ttu-id="c86fe-147">20%</span><span class="sxs-lookup"><span data-stu-id="c86fe-147">20%</span></span>      |
| <span data-ttu-id="c86fe-148">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="c86fe-148">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="c86fe-149">10%</span><span class="sxs-lookup"><span data-stu-id="c86fe-149">10%</span></span>      |

<span data-ttu-id="c86fe-150">Base marginal: **Importe neto por unidad**</span><span class="sxs-lookup"><span data-stu-id="c86fe-150">Marginal base: **Net amount per unit**</span></span> 

<span data-ttu-id="c86fe-151">Método de cálculo: **Importe completo**</span><span class="sxs-lookup"><span data-stu-id="c86fe-151">Calculation method: **Whole amount**</span></span> 

<span data-ttu-id="c86fe-152">Supongamos que compra 8 lámparas que cuestan 25,00 cada una.</span><span class="sxs-lookup"><span data-stu-id="c86fe-152">You buy 8 lamps that cost 25.00 each.</span></span> 

<span data-ttu-id="c86fe-153">El importe neto de la línea de factura es 200,00.</span><span class="sxs-lookup"><span data-stu-id="c86fe-153">The net amount for the invoice line is 200.00.</span></span> 

<span data-ttu-id="c86fe-154">Los impuestos se calculan como sigue: Impuestos por unidad = 25,00 x 30% = 7,50 Impuestos totales = 7,50 x 8 unidades = 60,00 Importes de factura total = 200,00 + 60,00 = 260,00</span><span class="sxs-lookup"><span data-stu-id="c86fe-154">The tax is calculated as follows: Sales tax per unit = 25.00 x 30% = 7.50 Total sales tax = 7.50 x 8 units = 60.00 Total invoice amount = 200.00 + 60.00 = 260.00</span></span>

## <a name="net-amount-of-invoice-balance"></a><span data-ttu-id="c86fe-155"> Importe neto del saldo de la factura</span><span class="sxs-lookup"><span data-stu-id="c86fe-155">Net amount of invoice balance</span></span>

<span data-ttu-id="c86fe-156">Seleccione esta opción para determinar las tasas de impuestos en base al valor total de la factura, sin incluir los demás impuestos.</span><span class="sxs-lookup"><span data-stu-id="c86fe-156">Select this option to determine sales tax rates based on the total value for the invoice, excluding any other taxes.</span></span>

### <a name="example"></a><span data-ttu-id="c86fe-157">ejemplo</span><span class="sxs-lookup"><span data-stu-id="c86fe-157">Example</span></span>

<span data-ttu-id="c86fe-158">Los índices de impuestos se configuran en los siguientes intervalos.</span><span class="sxs-lookup"><span data-stu-id="c86fe-158">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="c86fe-159">Importe</span><span class="sxs-lookup"><span data-stu-id="c86fe-159">Amount</span></span>            | <span data-ttu-id="c86fe-160">Índice de impuestos</span><span class="sxs-lookup"><span data-stu-id="c86fe-160">Tax rate</span></span> |
|-------------------|----------|
| <span data-ttu-id="c86fe-161">0 - 50</span><span class="sxs-lookup"><span data-stu-id="c86fe-161">0 - 50</span></span>            | <span data-ttu-id="c86fe-162">30%</span><span class="sxs-lookup"><span data-stu-id="c86fe-162">30%</span></span>      |
| <span data-ttu-id="c86fe-163">50 - 100</span><span class="sxs-lookup"><span data-stu-id="c86fe-163">50 - 100</span></span>          | <span data-ttu-id="c86fe-164">20%</span><span class="sxs-lookup"><span data-stu-id="c86fe-164">20%</span></span>      |
| <span data-ttu-id="c86fe-165">100 -0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="c86fe-165">100 -0 (&gt; 100)</span></span> | <span data-ttu-id="c86fe-166">10%</span><span class="sxs-lookup"><span data-stu-id="c86fe-166">10%</span></span>      |

<span data-ttu-id="c86fe-167">Base marginal: **Importe neto del saldo de la factura**</span><span class="sxs-lookup"><span data-stu-id="c86fe-167">Marginal base: **Net amount of invoice balance**</span></span> 

<span data-ttu-id="c86fe-168">Método de cálculo: **Intervalo** Una factura de ventas tiene 2 líneas con 4 lámparas en cada línea de 25,00 cada una.</span><span class="sxs-lookup"><span data-stu-id="c86fe-168">Calculation method: **Interval** A sales invoice has 2 lines with 4 lamps on each lines for 25.00 each.</span></span> <span data-ttu-id="c86fe-169">El importe neto del saldo de la factura es 4 x 25,00 + 4 x 25,00 = 200,00.</span><span class="sxs-lookup"><span data-stu-id="c86fe-169">The net amount of invoice balance is 4 x 25.00 + 4 x 25.00 = 200.00.</span></span> <span data-ttu-id="c86fe-170">Los impuestos se calculan como sigue: Total de impuestos = 50 x 0,30 + 50 x 0,20 + 100 x 0,10 = 15 + 10 + 10 = 35,00 Importe total de factura = 200,00 + 35,00 = 235,00</span><span class="sxs-lookup"><span data-stu-id="c86fe-170">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 100 x 0.10 = 15 + 10 + 10 = 35.00 Total invoice amount = 200.00 + 35.00 = 235.00</span></span>

## <a name="gross-amount-per-line"></a><span data-ttu-id="c86fe-171"> Importe bruto por línea</span><span class="sxs-lookup"><span data-stu-id="c86fe-171">Gross amount per line</span></span>

<span data-ttu-id="c86fe-172">Seleccione esta opción para determinar las tasas de impuestos en base al valor de la línea, incluidos los demás impuestos para esa línea.</span><span class="sxs-lookup"><span data-stu-id="c86fe-172">Select this option to determine sales tax rates based on the value of the line including all other taxes for that line.</span></span>

> [!NOTE]
> <span data-ttu-id="c86fe-173">En un grupo de impuestos, solo puede tener un código de impuestos con esta selección en el campo Base marginal.</span><span class="sxs-lookup"><span data-stu-id="c86fe-173">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field.</span></span>

### <a name="example"></a><span data-ttu-id="c86fe-174">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c86fe-174">Example</span></span>

<span data-ttu-id="c86fe-175">Los índices de impuestos se configuran en los siguientes intervalos.</span><span class="sxs-lookup"><span data-stu-id="c86fe-175">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="c86fe-176">Importe</span><span class="sxs-lookup"><span data-stu-id="c86fe-176">Amount</span></span>             | <span data-ttu-id="c86fe-177">Índice de impuestos</span><span class="sxs-lookup"><span data-stu-id="c86fe-177">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="c86fe-178">0 - 50</span><span class="sxs-lookup"><span data-stu-id="c86fe-178">0 - 50</span></span>             | <span data-ttu-id="c86fe-179">30%</span><span class="sxs-lookup"><span data-stu-id="c86fe-179">30%</span></span>      |
| <span data-ttu-id="c86fe-180">50 - 100</span><span class="sxs-lookup"><span data-stu-id="c86fe-180">50 - 100</span></span>           | <span data-ttu-id="c86fe-181">20%</span><span class="sxs-lookup"><span data-stu-id="c86fe-181">20%</span></span>      |
| <span data-ttu-id="c86fe-182">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="c86fe-182">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="c86fe-183">10%</span><span class="sxs-lookup"><span data-stu-id="c86fe-183">10%</span></span>      |

<span data-ttu-id="c86fe-184">Base marginal: **Importe bruto por línea** Método de cálculo: **Intervalo** Hay además otro código de impuestos calculado para un arancel especial de 5,00 en cada lámpara.</span><span class="sxs-lookup"><span data-stu-id="c86fe-184">Marginal base: **Gross amount per line** Calculation method: **Interval** Additionally there is another tax code calculated for a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="c86fe-185">Los aranceles se añaden al importe neto antes del cálculo de impuestos de ventas.</span><span class="sxs-lookup"><span data-stu-id="c86fe-185">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="c86fe-186">Supongamos que compra 8 lámparas que cuestan 25,00 cada una.</span><span class="sxs-lookup"><span data-stu-id="c86fe-186">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="c86fe-187">El importe neto de la línea de factura es 200,00.</span><span class="sxs-lookup"><span data-stu-id="c86fe-187">The net amount for the invoice line is 200.00.</span></span> <span data-ttu-id="c86fe-188">El importe bruto de la línea de factura es 8 x 25,00 + 8 x 5,00 = 240,00.</span><span class="sxs-lookup"><span data-stu-id="c86fe-188">The gross amount for the invoice line is 8 x 25.00 + 8 x 5.00 = 240.00.</span></span> <span data-ttu-id="c86fe-189">Los impuestos se calculan como sigue: Impuestos totales = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 20 + 14 = 39,00 Arancel total = 5,00 x 8 = 40,00 Importe total de factura = 200,00 + 39,00 + 40,00 = 279,00</span><span class="sxs-lookup"><span data-stu-id="c86fe-189">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 140 x 0.10 = 15 + 20 + 14 = 39.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 39.00 + 40.00 = 279.00</span></span>

<span data-ttu-id="c86fe-190">**Variación**</span><span class="sxs-lookup"><span data-stu-id="c86fe-190">**Variation**</span></span> 

<span data-ttu-id="c86fe-191">Si la factura se crea con 2 líneas de de factura con 4 artículos en cada línea, el importe neto por línea de factura es 100,00 euros.</span><span class="sxs-lookup"><span data-stu-id="c86fe-191">If the invoice is created by using 2 invoice lines with 4 items on each line, the net amount per invoice line is 100.00.</span></span> <span data-ttu-id="c86fe-192">El importe bruto (incluidos los aranceles 4 x 5,00) por línea de factura sería 120,00, y se crearían los impuestos como sigue: Factura de impuestos línea 1 = 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 Factura de impuestos línea 2 = 50 x 0,30 + 50 x 0,20 + 20 x 0,10 = 15 + 10 + 2 = 27,00 Impuestos totales = 27,00 + 27,00 = 54,00 Arancel total = 5,00 x 8 = 40,00 Importe total de factura = 200,00 + 54,00 + 40,00 = 294,00</span><span class="sxs-lookup"><span data-stu-id="c86fe-192">The gross amount (including the duty of 4 x 5.00) per invoice line would be 120.00, and the sales tax is created as follows: Sales tax invoice line 1 = 50 x 0.30 + 50 x 0.20 + 20 x 0.10 = 15 + 10 + 2 = 27.00 Sales tax invoice line 2 = 50 x 0.30 + 50 x 0.20 + 20 x 0.10 = 15 + 10 + 2 = 27.00 Total sales tax = 27.00 + 27.00 = 54.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 54.00 + 40.00 = 294.00</span></span>

## <a name="gross-amount-per-unit"></a><span data-ttu-id="c86fe-193"> Importe bruto por unidad</span><span class="sxs-lookup"><span data-stu-id="c86fe-193">Gross amount per unit</span></span>

<span data-ttu-id="c86fe-194">Seleccione esta opción para determinar las tasas de impuestos en base al valor de la unidad, incluidos los demás impuestos.</span><span class="sxs-lookup"><span data-stu-id="c86fe-194">Select this option to determine sales tax rates based on the value of the unit including any other taxes.</span></span>

> [!NOTE]
> <span data-ttu-id="c86fe-195">En un grupo de impuestos, solo puede tener un código de impuestos con esta selección en el campo Base marginal.</span><span class="sxs-lookup"><span data-stu-id="c86fe-195">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field.</span></span>

### <a name="example"></a><span data-ttu-id="c86fe-196">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c86fe-196">Example</span></span>

<span data-ttu-id="c86fe-197">Los índices de impuestos se configuran en los siguientes intervalos.</span><span class="sxs-lookup"><span data-stu-id="c86fe-197">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="c86fe-198">Importe</span><span class="sxs-lookup"><span data-stu-id="c86fe-198">Amount</span></span>             | <span data-ttu-id="c86fe-199">Índice de impuestos</span><span class="sxs-lookup"><span data-stu-id="c86fe-199">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="c86fe-200">0 - 50</span><span class="sxs-lookup"><span data-stu-id="c86fe-200">0 - 50</span></span>             | <span data-ttu-id="c86fe-201">30%</span><span class="sxs-lookup"><span data-stu-id="c86fe-201">30%</span></span>      |
| <span data-ttu-id="c86fe-202">50 - 100</span><span class="sxs-lookup"><span data-stu-id="c86fe-202">50 - 100</span></span>           | <span data-ttu-id="c86fe-203">20%</span><span class="sxs-lookup"><span data-stu-id="c86fe-203">20%</span></span>      |
| <span data-ttu-id="c86fe-204">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="c86fe-204">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="c86fe-205">10%</span><span class="sxs-lookup"><span data-stu-id="c86fe-205">10%</span></span>      |

<span data-ttu-id="c86fe-206">Base marginal: **Importe bruto por unidad** Existen un arancel especial de 5,00 en cada lámpara.</span><span class="sxs-lookup"><span data-stu-id="c86fe-206">Marginal base: **Gross amount per unit** There is a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="c86fe-207">Los aranceles se añaden al importe neto antes del cálculo de impuestos de ventas.</span><span class="sxs-lookup"><span data-stu-id="c86fe-207">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="c86fe-208">Supongamos que compra 8 lámparas que cuestan 25,00 cada una.</span><span class="sxs-lookup"><span data-stu-id="c86fe-208">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="c86fe-209">El importe bruto por unidad es 30,00.</span><span class="sxs-lookup"><span data-stu-id="c86fe-209">The gross amount per unit is 30.00.</span></span> <span data-ttu-id="c86fe-210">Los impuestos se calculan como sigue: Impuestos por unidad = 30 x 30% = 9,00 Impuestos totales = 9,00 x 8 = 72,00 Arancel total = 5,00 x 8 = 40,00 Importe total de factura = 200,00 + 72,00 + 40,00 = 312,00</span><span class="sxs-lookup"><span data-stu-id="c86fe-210">The tax is calculated as follows: Sales tax per unit = 30 x 30% = 9.00 Total sales tax = 9.00 x 8 = 72.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 72.00 + 40.00 = 312.00</span></span>

## <a name="invoice-total-incl-other-sales-tax-amounts"></a><span data-ttu-id="c86fe-211"> Total de la factura incluidos otros impuestos</span><span class="sxs-lookup"><span data-stu-id="c86fe-211">Invoice total incl. other sales tax amounts</span></span>

<span data-ttu-id="c86fe-212">Seleccione esta opción para determinar las tasas de impuestos en base al valor total de la factura, incluidos los demás impuestos.</span><span class="sxs-lookup"><span data-stu-id="c86fe-212">Select this option to determine sales tax rates based on the total value for the invoice including any other taxes.</span></span>
> [!NOTE]
> <span data-ttu-id="c86fe-213">En un grupo de impuestos, solo puede tener un código de impuestos con esta selección en el campo Base marginal</span><span class="sxs-lookup"><span data-stu-id="c86fe-213">In a sales tax group, you can only have one sales tax code with this selection in the Marginal base field</span></span>

### <a name="example"></a><span data-ttu-id="c86fe-214">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="c86fe-214">Example</span></span>

<span data-ttu-id="c86fe-215">Los índices de impuestos se configuran en los siguientes intervalos.</span><span class="sxs-lookup"><span data-stu-id="c86fe-215">The sales tax rates are set up in the following intervals.</span></span>

| <span data-ttu-id="c86fe-216">Importe</span><span class="sxs-lookup"><span data-stu-id="c86fe-216">Amount</span></span>             | <span data-ttu-id="c86fe-217">Índice de impuestos</span><span class="sxs-lookup"><span data-stu-id="c86fe-217">Tax rate</span></span> |
|--------------------|----------|
| <span data-ttu-id="c86fe-218">0 - 50</span><span class="sxs-lookup"><span data-stu-id="c86fe-218">0 - 50</span></span>             | <span data-ttu-id="c86fe-219">30%</span><span class="sxs-lookup"><span data-stu-id="c86fe-219">30%</span></span>      |
| <span data-ttu-id="c86fe-220">50 - 100</span><span class="sxs-lookup"><span data-stu-id="c86fe-220">50 - 100</span></span>           | <span data-ttu-id="c86fe-221">20%</span><span class="sxs-lookup"><span data-stu-id="c86fe-221">20%</span></span>      |
| <span data-ttu-id="c86fe-222">100 - 0 (&gt; 100)</span><span class="sxs-lookup"><span data-stu-id="c86fe-222">100 - 0 (&gt; 100)</span></span> | <span data-ttu-id="c86fe-223">10%</span><span class="sxs-lookup"><span data-stu-id="c86fe-223">10%</span></span>      |

<span data-ttu-id="c86fe-224">Base marginal: **Total de factura incluidos otros importes de impuestos** Método de cálculo: **Intervalo** </span><span class="sxs-lookup"><span data-stu-id="c86fe-224">Marginal base: **Invoice total incl. other sales tax amounts** Calculation method: **Interval** </span></span>  
<span data-ttu-id="c86fe-225">Existen unos aranceles especiales que gravan las lámparas de 5,00.</span><span class="sxs-lookup"><span data-stu-id="c86fe-225">There is a special duty of 5.00 on each lamp.</span></span> <span data-ttu-id="c86fe-226">Los aranceles se añaden al importe neto antes del cálculo de impuestos de ventas.</span><span class="sxs-lookup"><span data-stu-id="c86fe-226">The duty is added to the net amount before the sales tax calculation.</span></span> <span data-ttu-id="c86fe-227">Supongamos que compra 8 lámparas que cuestan 25,00 cada una.</span><span class="sxs-lookup"><span data-stu-id="c86fe-227">You buy 8 lamps that cost 25.00 each.</span></span> <span data-ttu-id="c86fe-228">El importe neto de la factura es 200,00.</span><span class="sxs-lookup"><span data-stu-id="c86fe-228">The net amount for the invoice is 200.00.</span></span> <span data-ttu-id="c86fe-229">El importe bruto de la factura es 200,00 + (8 x 5,00) = 240,00.</span><span class="sxs-lookup"><span data-stu-id="c86fe-229">The gross amount for the invoice is 200.00 + (8 x 5.00) = 240.00.</span></span> <span data-ttu-id="c86fe-230">Los impuestos se calculan como sigue: Impuestos totales = 50 x 0,30 + 50 x 0,20 + 140 x 0,10 = 15 + 10 + 14 = 39,00 Arancel total = 5,00 x 8 = 40,00 Importe total de factura = 200,00 + 39,00 + 40,00 = 279,00</span><span class="sxs-lookup"><span data-stu-id="c86fe-230">The tax is calculated as follows: Total sales tax = 50 x 0.30 + 50 x 0.20 + 140 x 0.10 = 15 + 10 + 14 = 39.00 Total duty = 5.00 x 8 = 40.00 Total invoice amount = 200.00 + 39.00 + 40.00 = 279.00</span></span>

<span data-ttu-id="c86fe-231">Para obtener más información, consulte [Importe completo y opciones de cálculo de intervalo para los códigos de impuestos](whole-amount-interval-options-sales-tax-codes.md) y [Métodos de cálculo de impuestos en el campo Origen](sales-tax-calculation-methods-origin-field.md).</span><span class="sxs-lookup"><span data-stu-id="c86fe-231">For more information, see [Whole amount and Interval calculation options for sales tax codes](whole-amount-interval-options-sales-tax-codes.md) and [Sales tax calculation methods in the Origin field](sales-tax-calculation-methods-origin-field.md).</span></span>




