---
title: Importe completo y opciones de cálculo de intervalo para los códigos de impuestos
description: Este artículo explica las opciones del campo Método de cálculo en códigos de impuestos y cómo se calculan los impuestos para los intervalos y los importes completos.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TaxData, TaxTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 5624
ms.assetid: 96166db4-b7ca-470b-aeb7-0a66fe0554c4
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 48569da2d504e4c380ca89bfec4450ad1b9888e5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842377"
---
# <a name="whole-amount-and-interval-calculation-options-for-sales-tax-codes"></a><span data-ttu-id="6f576-103">Importe completo y opciones de cálculo de intervalo para los códigos de impuestos</span><span class="sxs-lookup"><span data-stu-id="6f576-103">Whole amount and Interval calculation options for sales tax codes</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6f576-104">Este artículo explica las opciones del campo Método de cálculo en códigos de impuestos y cómo se calculan los impuestos para los intervalos y los importes completos.</span><span class="sxs-lookup"><span data-stu-id="6f576-104">This article explains the options for the Calculation method field on sales tax codes and how sales tax is calculated for intervals and whole amounts.</span></span>

<span data-ttu-id="6f576-105">Puede configurar un código de impuestos para que se calcule en función de un importe completo o de un importe de intervalo.</span><span class="sxs-lookup"><span data-stu-id="6f576-105">You can set up a sales tax code to be calculated based on a whole amount or an interval amount.</span></span> <span data-ttu-id="6f576-106">En la página de códigos de impuestos, use el campo Método de cálculo en la ficha desplegable Cálculo para seleccionar cómo calcular un código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="6f576-106">In the Sales tax codes page, use the Calculation method field on the Calculation FastTab to select how to calculate a sales tax code.</span></span>
- <span data-ttu-id="6f576-107">Importe completo: el índice de impuestos se aplica al importe gravable completo.</span><span class="sxs-lookup"><span data-stu-id="6f576-107">Whole amount – The tax rate is applied to the whole taxable amount.</span></span>
- <span data-ttu-id="6f576-108">Intervalo: el importe gravable se divide en partes, cada una de las cuales pertenece a un intervalo que tenga un índice de impuestos específico.</span><span class="sxs-lookup"><span data-stu-id="6f576-108">Interval – The taxable amount is divided into parts, each of which falls in a range that has a specific sales tax rate.</span></span> <span data-ttu-id="6f576-109">La parte del importe que pertenece a un intervalo determinado se grava según el índice de impuestos para dicho intervalo.</span><span class="sxs-lookup"><span data-stu-id="6f576-109">The part of the amount that falls in a given interval is taxed according to the tax rate for that interval.</span></span> <span data-ttu-id="6f576-110">Los impuestos son la suma de los importes de impuestos que se calculan para cada importe de intervalo.</span><span class="sxs-lookup"><span data-stu-id="6f576-110">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>
  > [!NOTE]                                                                                                                              
  > <span data-ttu-id="6f576-111">La opción Intervalo solo está disponible cuando selecciona el campo Método de cálculo en el área Impuestos de la página Parámetros de contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="6f576-111">The Interval option is available only when you select Line in the Calculation method field in the Sales tax area of the General ledger parameters page.</span></span> 

<span data-ttu-id="6f576-112">Los intervalos están colocados en la página de los valores de código de impuestos especificando los importes de límite mínimo y máximo por cada índice de impuestos.</span><span class="sxs-lookup"><span data-stu-id="6f576-112">Intervals are set up in the Sales tax code values page by entering Minimum and Maximum limit amounts per tax rate.</span></span> <span data-ttu-id="6f576-113">Para calcular los impuestos sobre los importes gravables, independientemente del método de cálculo seleccionado, los intervalos deben cumplir las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="6f576-113">For taxes to be calculated on all taxable amounts, regardless of which calculation method is selected, intervals must follow these rules:</span></span>
-   <span data-ttu-id="6f576-114">El primer intervalo debe tener un límite mínimo de cero.</span><span class="sxs-lookup"><span data-stu-id="6f576-114">The first interval must have a Minimum limit of zero.</span></span>
-   <span data-ttu-id="6f576-115">El último intervalo debe tener un límite máximo de cero, que indica infinito.</span><span class="sxs-lookup"><span data-stu-id="6f576-115">The last interval must have a Maximum limit of zero, which indicates infinity.</span></span>
-   <span data-ttu-id="6f576-116">El límite máximo de un intervalo debe ser el límite mínimo del intervalo siguiente.</span><span class="sxs-lookup"><span data-stu-id="6f576-116">The Maximum limit of an interval must be the Minimum limit of the next interval.</span></span>

<span data-ttu-id="6f576-117">Si un importe es el límite máximo del intervalo anterior y el límite mínimo del intervalo siguiente, se aplicará al importe el índice de impuestos del primer intervalo.</span><span class="sxs-lookup"><span data-stu-id="6f576-117">If an amount is the Maximum limit of the previous interval and the Minimum limit of the next interval, the sales tax rate of the first interval will be applied to the amount.</span></span> <span data-ttu-id="6f576-118">Si un importe se encuentra fuera de los intervalos definidos por los límites superior e inferior, se aplicará un índice de impuestos de cero.</span><span class="sxs-lookup"><span data-stu-id="6f576-118">If an amount falls outside the intervals that are defined by upper and lower limits, a sales tax rate of zero will be applied.</span></span>

## <a name="example-whole-amount-method-of-calculation"></a><span data-ttu-id="6f576-119">Ejemplo: método de cálculo de importe completo</span><span class="sxs-lookup"><span data-stu-id="6f576-119">Example: Whole amount method of calculation</span></span>
<span data-ttu-id="6f576-120">En la página Valores de código de impuestos, los índices de impuestos se configuran en los siguientes intervalos:</span><span class="sxs-lookup"><span data-stu-id="6f576-120">In the Sales tax code values page, sales tax rates are set up in the following intervals:</span></span>

| <span data-ttu-id="6f576-121">Límite mínimo</span><span class="sxs-lookup"><span data-stu-id="6f576-121">Minimum limit</span></span>     | <span data-ttu-id="6f576-122">Límite máximo</span><span class="sxs-lookup"><span data-stu-id="6f576-122">Maximum limit</span></span>     | <span data-ttu-id="6f576-123">Índice de impuestos</span><span class="sxs-lookup"><span data-stu-id="6f576-123">Tax rate</span></span>     |
|-------------------|-------------------|--------------|
| <span data-ttu-id="6f576-124">0,00</span><span class="sxs-lookup"><span data-stu-id="6f576-124">0.00</span></span>              | <span data-ttu-id="6f576-125">50,00</span><span class="sxs-lookup"><span data-stu-id="6f576-125">50.00</span></span>             | <span data-ttu-id="6f576-126">30%</span><span class="sxs-lookup"><span data-stu-id="6f576-126">30%</span></span>          |
| <span data-ttu-id="6f576-127">50,00</span><span class="sxs-lookup"><span data-stu-id="6f576-127">50.00</span></span>             | <span data-ttu-id="6f576-128">100,00</span><span class="sxs-lookup"><span data-stu-id="6f576-128">100.00</span></span>            | <span data-ttu-id="6f576-129">20%</span><span class="sxs-lookup"><span data-stu-id="6f576-129">20%</span></span>          |
| <span data-ttu-id="6f576-130">100,00</span><span class="sxs-lookup"><span data-stu-id="6f576-130">100.00</span></span>            | <span data-ttu-id="6f576-131">0,00</span><span class="sxs-lookup"><span data-stu-id="6f576-131">0.00</span></span>              | <span data-ttu-id="6f576-132">10%</span><span class="sxs-lookup"><span data-stu-id="6f576-132">10%</span></span>          |

<span data-ttu-id="6f576-133">Los impuestos se calculan sobre el importe gravable completo.</span><span class="sxs-lookup"><span data-stu-id="6f576-133">The sales tax is calculated on the whole taxable amount.</span></span>

| <span data-ttu-id="6f576-134">Importe gravable (precio)</span><span class="sxs-lookup"><span data-stu-id="6f576-134">Taxable amount (price)</span></span> | <span data-ttu-id="6f576-135">Cálculo</span><span class="sxs-lookup"><span data-stu-id="6f576-135">Calculation</span></span>    | <span data-ttu-id="6f576-136">Impuestos</span><span class="sxs-lookup"><span data-stu-id="6f576-136">Sales tax</span></span> |
|------------------------|----------------|-----------|
| <span data-ttu-id="6f576-137">35,00</span><span class="sxs-lookup"><span data-stu-id="6f576-137">35.00</span></span>                  | <span data-ttu-id="6f576-138">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="6f576-138">35.00 \* 0.30</span></span>  | <span data-ttu-id="6f576-139">10,50</span><span class="sxs-lookup"><span data-stu-id="6f576-139">10.50</span></span>     |
| <span data-ttu-id="6f576-140">50,00</span><span class="sxs-lookup"><span data-stu-id="6f576-140">50.00</span></span>                  | <span data-ttu-id="6f576-141">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="6f576-141">50.00 \* 0.30</span></span>  | <span data-ttu-id="6f576-142">15:00</span><span class="sxs-lookup"><span data-stu-id="6f576-142">15.00</span></span>     |
| <span data-ttu-id="6f576-143">85,00</span><span class="sxs-lookup"><span data-stu-id="6f576-143">85.00</span></span>                  | <span data-ttu-id="6f576-144">85,00 \* 0,20</span><span class="sxs-lookup"><span data-stu-id="6f576-144">85.00 \* 0.20</span></span>  | <span data-ttu-id="6f576-145">17,00</span><span class="sxs-lookup"><span data-stu-id="6f576-145">17.00</span></span>     |
| <span data-ttu-id="6f576-146">305,00</span><span class="sxs-lookup"><span data-stu-id="6f576-146">305.00</span></span>                 | <span data-ttu-id="6f576-147">305,00 \* 0,10</span><span class="sxs-lookup"><span data-stu-id="6f576-147">305.00 \* 0.10</span></span> | <span data-ttu-id="6f576-148">30,50</span><span class="sxs-lookup"><span data-stu-id="6f576-148">30.50</span></span>     |

## <a name="example-interval-method-of-calculation"></a><span data-ttu-id="6f576-149">Ejemplo: método de cálculo de intervalo</span><span class="sxs-lookup"><span data-stu-id="6f576-149">Example: Interval method of calculation</span></span>
<span data-ttu-id="6f576-150">En la página Valores, los índices de impuestos se configuran en los siguientes intervalos:</span><span class="sxs-lookup"><span data-stu-id="6f576-150">In the Values page, sales tax rates are set up in the following intervals:</span></span>

| <span data-ttu-id="6f576-151">Límite mínimo</span><span class="sxs-lookup"><span data-stu-id="6f576-151">Minimum limit</span></span>     | <span data-ttu-id="6f576-152">Límite máximo</span><span class="sxs-lookup"><span data-stu-id="6f576-152">Maximum limit</span></span>     | <span data-ttu-id="6f576-153">Índice de impuestos</span><span class="sxs-lookup"><span data-stu-id="6f576-153">Tax rate</span></span>     |
|-------------------|-------------------|--------------|
| <span data-ttu-id="6f576-154">0,00</span><span class="sxs-lookup"><span data-stu-id="6f576-154">0.00</span></span>              | <span data-ttu-id="6f576-155">50,00</span><span class="sxs-lookup"><span data-stu-id="6f576-155">50.00</span></span>             | <span data-ttu-id="6f576-156">30%</span><span class="sxs-lookup"><span data-stu-id="6f576-156">30%</span></span>          |
| <span data-ttu-id="6f576-157">50,00</span><span class="sxs-lookup"><span data-stu-id="6f576-157">50.00</span></span>             | <span data-ttu-id="6f576-158">100,00</span><span class="sxs-lookup"><span data-stu-id="6f576-158">100.00</span></span>            | <span data-ttu-id="6f576-159">20%</span><span class="sxs-lookup"><span data-stu-id="6f576-159">20%</span></span>          |
| <span data-ttu-id="6f576-160">100,00</span><span class="sxs-lookup"><span data-stu-id="6f576-160">100.00</span></span>            | <span data-ttu-id="6f576-161">0,00</span><span class="sxs-lookup"><span data-stu-id="6f576-161">0.00</span></span>              | <span data-ttu-id="6f576-162">10%</span><span class="sxs-lookup"><span data-stu-id="6f576-162">10%</span></span>          |

<span data-ttu-id="6f576-163">Los impuestos son la suma de los importes de impuestos que se calculan para cada importe de intervalo.</span><span class="sxs-lookup"><span data-stu-id="6f576-163">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>

| <span data-ttu-id="6f576-164">Importe gravable (precio)</span><span class="sxs-lookup"><span data-stu-id="6f576-164">Taxable amount (price)</span></span> | <span data-ttu-id="6f576-165">Cálculo</span><span class="sxs-lookup"><span data-stu-id="6f576-165">Calculation</span></span>                                                               | <span data-ttu-id="6f576-166">Impuestos</span><span class="sxs-lookup"><span data-stu-id="6f576-166">Sales tax</span></span> |
|------------------------|---------------------------------------------------------------------------|-----------|
| <span data-ttu-id="6f576-167">35,00</span><span class="sxs-lookup"><span data-stu-id="6f576-167">35.00</span></span>                  | <span data-ttu-id="6f576-168">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="6f576-168">35.00 \* 0.30</span></span>                                                             | <span data-ttu-id="6f576-169">10,50</span><span class="sxs-lookup"><span data-stu-id="6f576-169">10.50</span></span>     |
| <span data-ttu-id="6f576-170">50,00</span><span class="sxs-lookup"><span data-stu-id="6f576-170">50.00</span></span>                  | <span data-ttu-id="6f576-171">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="6f576-171">50.00 \* 0.30</span></span>                                                             | <span data-ttu-id="6f576-172">15:00</span><span class="sxs-lookup"><span data-stu-id="6f576-172">15.00</span></span>     |
| <span data-ttu-id="6f576-173">85,00</span><span class="sxs-lookup"><span data-stu-id="6f576-173">85.00</span></span>                  | <span data-ttu-id="6f576-174">(50,00 \* 0,30 = 15,00) + (35,00 \* 0,20 = 7,00)</span><span class="sxs-lookup"><span data-stu-id="6f576-174">(50.00 \* 0.30 = 15.00) + (35.00 \* 0.20 = 7.00)</span></span>                          | <span data-ttu-id="6f576-175">22,00</span><span class="sxs-lookup"><span data-stu-id="6f576-175">22.00</span></span>     |
| <span data-ttu-id="6f576-176">305,00</span><span class="sxs-lookup"><span data-stu-id="6f576-176">305.00</span></span>                 | <span data-ttu-id="6f576-177">(50,00 \* 0,30 = 15,00) + (50,00 \* 0,20 = 10,00) + (205 \* 0,10 = 20,50)</span><span class="sxs-lookup"><span data-stu-id="6f576-177">(50.00 \* 0.30 = 15.00) + (50.00 \* 0.20 = 10.00) + (205 \* 0.10 = 20.50)</span></span> | <span data-ttu-id="6f576-178">45.50</span><span class="sxs-lookup"><span data-stu-id="6f576-178">45.50</span></span>     |



<span data-ttu-id="6f576-179">Para obtener más información, consulte [Impuestos basados en los métodos de Base marginal y Cálculo](marginal-base-field.md)</span><span class="sxs-lookup"><span data-stu-id="6f576-179">For more information, see [Sales tax rates based on the Marginal base and Calculation methods](marginal-base-field.md).</span></span>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]