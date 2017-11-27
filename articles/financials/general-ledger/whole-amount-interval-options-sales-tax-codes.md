---
title: "Importe completo y opciones de cálculo de intervalo para los códigos de impuestos"
description: "Este artículo explica las opciones del campo Método de cálculo en códigos de impuestos y cómo se calculan los impuestos para los intervalos y los importes completos."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxData, TaxTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations, Retail
ms.custom: 5624
ms.assetid: 96166db4-b7ca-470b-aeb7-0a66fe0554c4
ms.search.region: Global
ms.author: vstehman
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 6ac0e2abcb5dce58ad16737a0ef689ceaeb50c44
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="whole-amount-and-interval-calculation-options-for-sales-tax-codes"></a><span data-ttu-id="327ca-103">Importe completo y opciones de cálculo de intervalo para los códigos de impuestos</span><span class="sxs-lookup"><span data-stu-id="327ca-103">Whole amount and Interval calculation options for sales tax codes</span></span>

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]



<span data-ttu-id="327ca-104">Este artículo explica las opciones del campo Método de cálculo en códigos de impuestos y cómo se calculan los impuestos para los intervalos y los importes completos.</span><span class="sxs-lookup"><span data-stu-id="327ca-104">This article explains the options for the Calculation method field on sales tax codes and how sales tax is calculated for intervals and whole amounts.</span></span>

<span data-ttu-id="327ca-105">Puede configurar un código de impuestos para que se calcule en función de un importe completo o de un importe de intervalo.</span><span class="sxs-lookup"><span data-stu-id="327ca-105">You can set up a sales tax code to be calculated based on a whole amount or an interval amount.</span></span> <span data-ttu-id="327ca-106">En la página de códigos de impuestos, use el campo Método de cálculo en la ficha desplegable Cálculo para seleccionar cómo calcular un código de impuestos.</span><span class="sxs-lookup"><span data-stu-id="327ca-106">In the Sales tax codes page, use the Calculation method field on the Calculation FastTab to select how to calculate a sales tax code.</span></span>
-   <span data-ttu-id="327ca-107">Importe completo: el índice de impuestos se aplica al importe gravable completo.</span><span class="sxs-lookup"><span data-stu-id="327ca-107">Whole amount – The tax rate is applied to the whole taxable amount.</span></span>
-   <span data-ttu-id="327ca-108">Intervalo: el importe gravable se divide en partes, cada una de las cuales pertenece a un intervalo que tenga un índice de impuestos específico.</span><span class="sxs-lookup"><span data-stu-id="327ca-108">Interval – The taxable amount is divided into parts, each of which falls in a range that has a specific sales tax rate.</span></span> <span data-ttu-id="327ca-109">La parte del importe que pertenece a un intervalo determinado se grava según el índice de impuestos para dicho intervalo.</span><span class="sxs-lookup"><span data-stu-id="327ca-109">The part of the amount that falls in a given interval is taxed according to the tax rate for that interval.</span></span> <span data-ttu-id="327ca-110">Los impuestos son la suma de los importes de impuestos que se calculan para cada importe de intervalo.</span><span class="sxs-lookup"><span data-stu-id="327ca-110">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>
> [!NOTE]                                                                                                                              
> <span data-ttu-id="327ca-111">La opción Intervalo solo está disponible cuando selecciona el campo Método de cálculo en el área Impuestos de la página Parámetros de contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="327ca-111">The Interval option is available only when you select Line in the Calculation method field in the Sales tax area of the General ledger parameters page.</span></span> 

<span data-ttu-id="327ca-112">Los intervalos están colocados en la página de los valores de código de impuestos especificando los importes de límite mínimo y máximo por cada índice de impuestos.</span><span class="sxs-lookup"><span data-stu-id="327ca-112">Intervals are set up in the Sales tax code values page by entering Minimum and Maximum limit amounts per tax rate.</span></span> <span data-ttu-id="327ca-113">Para calcular los impuestos sobre los importes gravables, independientemente del método de cálculo seleccionado, los intervalos deben cumplir las siguientes reglas:</span><span class="sxs-lookup"><span data-stu-id="327ca-113">For taxes to be calculated on all taxable amounts, regardless of which calculation method is selected, intervals must follow these rules:</span></span>
-   <span data-ttu-id="327ca-114">El primer intervalo debe tener un límite mínimo de cero.</span><span class="sxs-lookup"><span data-stu-id="327ca-114">The first interval must have a Minimum limit of zero.</span></span>
-   <span data-ttu-id="327ca-115">El último intervalo debe tener un límite máximo de cero, que indica infinito.</span><span class="sxs-lookup"><span data-stu-id="327ca-115">The last interval must have a Maximum limit of zero, which indicates infinity.</span></span>
-   <span data-ttu-id="327ca-116">El límite máximo de un intervalo debe ser el límite mínimo del intervalo siguiente.</span><span class="sxs-lookup"><span data-stu-id="327ca-116">The Maximum limit of an interval must be the Minimum limit of the next interval.</span></span>

<span data-ttu-id="327ca-117">Si un importe es el límite máximo del intervalo anterior y el límite mínimo del intervalo siguiente, se aplicará al importe el índice de impuestos del primer intervalo.</span><span class="sxs-lookup"><span data-stu-id="327ca-117">If an amount is the Maximum limit of the previous interval and the Minimum limit of the next interval, the sales tax rate of the first interval will be applied to the amount.</span></span> <span data-ttu-id="327ca-118">Si un importe se encuentra fuera de los intervalos definidos por los límites superior e inferior, se aplicará un índice de impuestos de cero.</span><span class="sxs-lookup"><span data-stu-id="327ca-118">If an amount falls outside the intervals that are defined by upper and lower limits, a sales tax rate of zero will be applied.</span></span>

## <a name="example-whole-amount-method-of-calculation"></a><span data-ttu-id="327ca-119">Ejemplo: método de cálculo de importe completo</span><span class="sxs-lookup"><span data-stu-id="327ca-119">Example: Whole amount method of calculation</span></span>
<span data-ttu-id="327ca-120">En la página Valores de código de impuestos, los índices de impuestos se configuran en los siguientes intervalos:</span><span class="sxs-lookup"><span data-stu-id="327ca-120">In the Sales tax code values page, sales tax rates are set up in the following intervals:</span></span>
|                   |                   |              |
|-------------------|-------------------|--------------|
| <span data-ttu-id="327ca-121">**Límite mínimo**</span><span class="sxs-lookup"><span data-stu-id="327ca-121">**Minimum limit**</span></span> | <span data-ttu-id="327ca-122">**Límite máximo**</span><span class="sxs-lookup"><span data-stu-id="327ca-122">**Maximum limit**</span></span> | <span data-ttu-id="327ca-123">**Índice de impuestos**</span><span class="sxs-lookup"><span data-stu-id="327ca-123">**Tax rate**</span></span> |
| <span data-ttu-id="327ca-124">0,00</span><span class="sxs-lookup"><span data-stu-id="327ca-124">0.00</span></span>              | <span data-ttu-id="327ca-125">50,00</span><span class="sxs-lookup"><span data-stu-id="327ca-125">50.00</span></span>             | <span data-ttu-id="327ca-126">30%</span><span class="sxs-lookup"><span data-stu-id="327ca-126">30%</span></span>          |
| <span data-ttu-id="327ca-127">50,00</span><span class="sxs-lookup"><span data-stu-id="327ca-127">50.00</span></span>             | <span data-ttu-id="327ca-128">100,00</span><span class="sxs-lookup"><span data-stu-id="327ca-128">100.00</span></span>            | <span data-ttu-id="327ca-129">20%</span><span class="sxs-lookup"><span data-stu-id="327ca-129">20%</span></span>          |
| <span data-ttu-id="327ca-130">100,00</span><span class="sxs-lookup"><span data-stu-id="327ca-130">100.00</span></span>            | <span data-ttu-id="327ca-131">0,00</span><span class="sxs-lookup"><span data-stu-id="327ca-131">0.00</span></span>              | <span data-ttu-id="327ca-132">10%</span><span class="sxs-lookup"><span data-stu-id="327ca-132">10%</span></span>          |

<span data-ttu-id="327ca-133">Los impuestos se calculan sobre el importe gravable completo.</span><span class="sxs-lookup"><span data-stu-id="327ca-133">The sales tax is calculated on the whole taxable amount.</span></span>

| <span data-ttu-id="327ca-134">Importe gravable (precio)</span><span class="sxs-lookup"><span data-stu-id="327ca-134">Taxable amount (price)</span></span> | <span data-ttu-id="327ca-135">Cálculo</span><span class="sxs-lookup"><span data-stu-id="327ca-135">Calculation</span></span>    | <span data-ttu-id="327ca-136">Impuestos</span><span class="sxs-lookup"><span data-stu-id="327ca-136">Sales tax</span></span> |
|------------------------|----------------|-----------|
| <span data-ttu-id="327ca-137">35,00</span><span class="sxs-lookup"><span data-stu-id="327ca-137">35.00</span></span>                  | <span data-ttu-id="327ca-138">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="327ca-138">35.00 \* 0.30</span></span>  | <span data-ttu-id="327ca-139">10,50</span><span class="sxs-lookup"><span data-stu-id="327ca-139">10.50</span></span>     |
| <span data-ttu-id="327ca-140">50,00</span><span class="sxs-lookup"><span data-stu-id="327ca-140">50.00</span></span>                  | <span data-ttu-id="327ca-141">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="327ca-141">50.00 \* 0.30</span></span>  | <span data-ttu-id="327ca-142">15:00</span><span class="sxs-lookup"><span data-stu-id="327ca-142">15.00</span></span>     |
| <span data-ttu-id="327ca-143">85,00</span><span class="sxs-lookup"><span data-stu-id="327ca-143">85.00</span></span>                  | <span data-ttu-id="327ca-144">85,00 \* 0,20</span><span class="sxs-lookup"><span data-stu-id="327ca-144">85.00 \* 0.20</span></span>  | <span data-ttu-id="327ca-145">17,00</span><span class="sxs-lookup"><span data-stu-id="327ca-145">17.00</span></span>     |
| <span data-ttu-id="327ca-146">305,00</span><span class="sxs-lookup"><span data-stu-id="327ca-146">305.00</span></span>                 | <span data-ttu-id="327ca-147">305,00 \* 0,10</span><span class="sxs-lookup"><span data-stu-id="327ca-147">305.00 \* 0.10</span></span> | <span data-ttu-id="327ca-148">30,50</span><span class="sxs-lookup"><span data-stu-id="327ca-148">30.50</span></span>     |

## <a name="example-interval-method-of-calculation"></a><span data-ttu-id="327ca-149">Ejemplo: método de cálculo de intervalo</span><span class="sxs-lookup"><span data-stu-id="327ca-149">Example: Interval method of calculation</span></span>
<span data-ttu-id="327ca-150">En la página Valores, los índices de impuestos se configuran en los siguientes intervalos:</span><span class="sxs-lookup"><span data-stu-id="327ca-150">In the Values page, sales tax rates are set up in the following intervals:</span></span>

|                   |                   |              |
|-------------------|-------------------|--------------|
| <span data-ttu-id="327ca-151">**Límite mínimo**</span><span class="sxs-lookup"><span data-stu-id="327ca-151">**Minimum limit**</span></span> | <span data-ttu-id="327ca-152">**Límite máximo**</span><span class="sxs-lookup"><span data-stu-id="327ca-152">**Maximum limit**</span></span> | <span data-ttu-id="327ca-153">**Índice de impuestos**</span><span class="sxs-lookup"><span data-stu-id="327ca-153">**Tax rate**</span></span> |
| <span data-ttu-id="327ca-154">0,00</span><span class="sxs-lookup"><span data-stu-id="327ca-154">0.00</span></span>              | <span data-ttu-id="327ca-155">50,00</span><span class="sxs-lookup"><span data-stu-id="327ca-155">50.00</span></span>             | <span data-ttu-id="327ca-156">30%</span><span class="sxs-lookup"><span data-stu-id="327ca-156">30%</span></span>          |
| <span data-ttu-id="327ca-157">50,00</span><span class="sxs-lookup"><span data-stu-id="327ca-157">50.00</span></span>             | <span data-ttu-id="327ca-158">100,00</span><span class="sxs-lookup"><span data-stu-id="327ca-158">100.00</span></span>            | <span data-ttu-id="327ca-159">20%</span><span class="sxs-lookup"><span data-stu-id="327ca-159">20%</span></span>          |
| <span data-ttu-id="327ca-160">100,00</span><span class="sxs-lookup"><span data-stu-id="327ca-160">100.00</span></span>            | <span data-ttu-id="327ca-161">0,00</span><span class="sxs-lookup"><span data-stu-id="327ca-161">0.00</span></span>              | <span data-ttu-id="327ca-162">10%</span><span class="sxs-lookup"><span data-stu-id="327ca-162">10%</span></span>          |

<span data-ttu-id="327ca-163">Los impuestos son la suma de los importes de impuestos que se calculan para cada importe de intervalo.</span><span class="sxs-lookup"><span data-stu-id="327ca-163">The sales tax is the sum of the tax amounts that are calculated for each amount interval.</span></span>

| <span data-ttu-id="327ca-164">Importe gravable (precio)</span><span class="sxs-lookup"><span data-stu-id="327ca-164">Taxable amount (price)</span></span> | <span data-ttu-id="327ca-165">Cálculo</span><span class="sxs-lookup"><span data-stu-id="327ca-165">Calculation</span></span>                                                               | <span data-ttu-id="327ca-166">Impuestos</span><span class="sxs-lookup"><span data-stu-id="327ca-166">Sales tax</span></span> |
|------------------------|---------------------------------------------------------------------------|-----------|
| <span data-ttu-id="327ca-167">35,00</span><span class="sxs-lookup"><span data-stu-id="327ca-167">35.00</span></span>                  | <span data-ttu-id="327ca-168">35,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="327ca-168">35.00 \* 0.30</span></span>                                                             | <span data-ttu-id="327ca-169">10,50</span><span class="sxs-lookup"><span data-stu-id="327ca-169">10.50</span></span>     |
| <span data-ttu-id="327ca-170">50,00</span><span class="sxs-lookup"><span data-stu-id="327ca-170">50.00</span></span>                  | <span data-ttu-id="327ca-171">50,00 \* 0,30</span><span class="sxs-lookup"><span data-stu-id="327ca-171">50.00 \* 0.30</span></span>                                                             | <span data-ttu-id="327ca-172">15:00</span><span class="sxs-lookup"><span data-stu-id="327ca-172">15.00</span></span>     |
| <span data-ttu-id="327ca-173">85,00</span><span class="sxs-lookup"><span data-stu-id="327ca-173">85.00</span></span>                  | <span data-ttu-id="327ca-174">(50,00 \* 0,30 = 15,00) + (35,00 \* 0,20 = 7,00)</span><span class="sxs-lookup"><span data-stu-id="327ca-174">(50.00 \* 0.30 = 15.00) + (35.00 \* 0.20 = 7.00)</span></span>                          | <span data-ttu-id="327ca-175">22,00</span><span class="sxs-lookup"><span data-stu-id="327ca-175">22.00</span></span>     |
| <span data-ttu-id="327ca-176">305,00</span><span class="sxs-lookup"><span data-stu-id="327ca-176">305.00</span></span>                 | <span data-ttu-id="327ca-177">(50,00 \* 0,30 = 15,00) + (50,00 \* 0,20 = 10,00) + (205 \* 0,10 = 20,50)</span><span class="sxs-lookup"><span data-stu-id="327ca-177">(50.00 \* 0.30 = 15.00) + (50.00 \* 0.20 = 10.00) + (205 \* 0.10 = 20.50)</span></span> | <span data-ttu-id="327ca-178">45,50</span><span class="sxs-lookup"><span data-stu-id="327ca-178">45.50</span></span>     |

 

<span data-ttu-id="327ca-179">Para obtener más información, consulte [Determinación de los índices de impuestos de ventas en función de los campos Base marginal y Método de cálculo](marginal-base-field.md)</span><span class="sxs-lookup"><span data-stu-id="327ca-179">For more information, see [Determining sale tax rates based on the Marginal base and Calculation method fields](marginal-base-field.md).</span></span>






