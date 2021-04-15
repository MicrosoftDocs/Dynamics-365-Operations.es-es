---
title: Depreciación de factor
description: Este artículo ofrece una visión general del método de depreciación de factor.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13831
ms.assetid: 2b6c4fe4-02ff-4191-bcad-32f1f34c15f2
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8adfc91251ba1707c688fac6da04adaa9af1a47f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5815701"
---
# <a name="factor-depreciation"></a><span data-ttu-id="52345-103">Depreciación de factor</span><span class="sxs-lookup"><span data-stu-id="52345-103">Factor depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="52345-104">Este artículo ofrece una visión general del método de depreciación de factor.</span><span class="sxs-lookup"><span data-stu-id="52345-104">This article gives an overview of the factor depreciation method.</span></span>

<span data-ttu-id="52345-105">Los factores son porcentajes que se utilizan para depreciar activos.</span><span class="sxs-lookup"><span data-stu-id="52345-105">Factors are the percentages that are used to depreciate assets.</span></span> <span data-ttu-id="52345-106">Cuando se configura un perfil de amortización de activos fijos y se selecciona **Factor** en el campo **Método** de la página **Métodos de depreciación**, puede configurar una depreciación progresiva, degresiva o lineal:</span><span class="sxs-lookup"><span data-stu-id="52345-106">When you set up a fixed asset depreciation profile and select **Factor** in the **Method** field on the **Depreciation profiles** page, you can set up progressive, digressive, or straight line depreciation:</span></span>

-   <span data-ttu-id="52345-107">En la depreciación progresiva, el importe de depreciación aumenta cada período de depreciación.</span><span class="sxs-lookup"><span data-stu-id="52345-107">In progressive depreciation, the amount of depreciation increases each depreciation period.</span></span>
-   <span data-ttu-id="52345-108">En la depreciación degresiva, el importe de depreciación por período aumenta con el transcurso del tiempo.</span><span class="sxs-lookup"><span data-stu-id="52345-108">In digressive depreciation, the amount of depreciation per period decreases over time.</span></span>
-   <span data-ttu-id="52345-109">En la depreciación lineal, la depreciación es la misma en cada período.</span><span class="sxs-lookup"><span data-stu-id="52345-109">In straight line depreciation, the depreciation is the same in each period.</span></span>

<span data-ttu-id="52345-110">Las reglas y los ejemplos siguientes indican el modo en que puede configurar los factores para cada tipo de depreciación.</span><span class="sxs-lookup"><span data-stu-id="52345-110">The rules and examples that follow indicate how you can set up factors for each type of depreciation.</span></span> 

> [!NOTE] 
> <span data-ttu-id="52345-111">Cuando selecciona **Factor** en el campo **Método**, se muestran los campos **Factor** e **Intervalo**.</span><span class="sxs-lookup"><span data-stu-id="52345-111">When you select **Factor** in the **Method** field, the **Factor** field and the **Interval** field are displayed.</span></span>

## <a name="progressive-depreciation"></a><span data-ttu-id="52345-112">Depreciación progresiva</span><span class="sxs-lookup"><span data-stu-id="52345-112">Progressive depreciation</span></span>
<span data-ttu-id="52345-113">El valor del campo **Factor** es mayor que **50**.</span><span class="sxs-lookup"><span data-stu-id="52345-113">The value in the **Factor** field is more than **50**.</span></span>

### <a name="example"></a><span data-ttu-id="52345-114">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="52345-114">Example</span></span>

<span data-ttu-id="52345-115">El precio de adquisición es de 100.000, el factor es 70, el tiempo de vida es de 10 años, y la depreciación comienza el 1 de enero.</span><span class="sxs-lookup"><span data-stu-id="52345-115">The acquisition price is 100,000, the factor is 70, the service life is 10 years, and depreciation starts on January 1.</span></span> <span data-ttu-id="52345-116">Las cantidades de depreciación y de valor neto en los libros sólo se muestran los primeros seis años del tiempo de vida.</span><span class="sxs-lookup"><span data-stu-id="52345-116">The depreciation amounts and net book value amounts are shown only for the first six years of service life.</span></span>

| <span data-ttu-id="52345-117">Año</span><span class="sxs-lookup"><span data-stu-id="52345-117">Year</span></span> | <span data-ttu-id="52345-118">Período</span><span class="sxs-lookup"><span data-stu-id="52345-118">Period</span></span>      | <span data-ttu-id="52345-119">Importe de depreciación</span><span class="sxs-lookup"><span data-stu-id="52345-119">Depreciation amount</span></span> | <span data-ttu-id="52345-120">Importe del valor neto en los libros</span><span class="sxs-lookup"><span data-stu-id="52345-120">Net book value amount</span></span> |
|------|-------------|---------------------|-----------------------|
| <span data-ttu-id="52345-121">1</span><span class="sxs-lookup"><span data-stu-id="52345-121">1</span></span>    | <span data-ttu-id="52345-122">31 de diciembre</span><span class="sxs-lookup"><span data-stu-id="52345-122">December 31</span></span> | <span data-ttu-id="52345-123">307,69</span><span class="sxs-lookup"><span data-stu-id="52345-123">307.69</span></span>              | <span data-ttu-id="52345-124">99.692,31</span><span class="sxs-lookup"><span data-stu-id="52345-124">99,692.31</span></span>             |
| <span data-ttu-id="52345-125">2</span><span class="sxs-lookup"><span data-stu-id="52345-125">2</span></span>    | <span data-ttu-id="52345-126">31 de diciembre</span><span class="sxs-lookup"><span data-stu-id="52345-126">December 31</span></span> | <span data-ttu-id="52345-127">1.447,21</span><span class="sxs-lookup"><span data-stu-id="52345-127">1,447.21</span></span>            | <span data-ttu-id="52345-128">98.245,10</span><span class="sxs-lookup"><span data-stu-id="52345-128">98,245.10</span></span>             |
| <span data-ttu-id="52345-129">3</span><span class="sxs-lookup"><span data-stu-id="52345-129">3</span></span>    | <span data-ttu-id="52345-130">31 de diciembre</span><span class="sxs-lookup"><span data-stu-id="52345-130">December 31</span></span> | <span data-ttu-id="52345-131">3.104,50</span><span class="sxs-lookup"><span data-stu-id="52345-131">3,104.50</span></span>            | <span data-ttu-id="52345-132">95.140,60</span><span class="sxs-lookup"><span data-stu-id="52345-132">95,140.60</span></span>             |
| <span data-ttu-id="52345-133">4</span><span class="sxs-lookup"><span data-stu-id="52345-133">4</span></span>    | <span data-ttu-id="52345-134">31 de diciembre</span><span class="sxs-lookup"><span data-stu-id="52345-134">December 31</span></span> | <span data-ttu-id="52345-135">5.150,21</span><span class="sxs-lookup"><span data-stu-id="52345-135">5,150.21</span></span>            | <span data-ttu-id="52345-136">89.990,39</span><span class="sxs-lookup"><span data-stu-id="52345-136">89,990.39</span></span>             |
| <span data-ttu-id="52345-137">5</span><span class="sxs-lookup"><span data-stu-id="52345-137">5</span></span>    | <span data-ttu-id="52345-138">31 de diciembre</span><span class="sxs-lookup"><span data-stu-id="52345-138">December 31</span></span> | <span data-ttu-id="52345-139">7.522,95</span><span class="sxs-lookup"><span data-stu-id="52345-139">7,522.95</span></span>            | <span data-ttu-id="52345-140">82.467,44</span><span class="sxs-lookup"><span data-stu-id="52345-140">82,467.44</span></span>             |
| <span data-ttu-id="52345-141">6</span><span class="sxs-lookup"><span data-stu-id="52345-141">6</span></span>    | <span data-ttu-id="52345-142">31 de diciembre</span><span class="sxs-lookup"><span data-stu-id="52345-142">December 31</span></span> | <span data-ttu-id="52345-143">10.184,06</span><span class="sxs-lookup"><span data-stu-id="52345-143">10,184.06</span></span>           | <span data-ttu-id="52345-144">72.283,38</span><span class="sxs-lookup"><span data-stu-id="52345-144">72,283.38</span></span>             |

## <a name="digressive-depreciation"></a><span data-ttu-id="52345-145">Depreciación degresiva</span><span class="sxs-lookup"><span data-stu-id="52345-145">Digressive depreciation</span></span>
<span data-ttu-id="52345-146">El valor del campo **Factor** es menor que **50**.</span><span class="sxs-lookup"><span data-stu-id="52345-146">The value in the **Factor** field is less than **50**.</span></span>

### <a name="example"></a><span data-ttu-id="52345-147">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="52345-147">Example</span></span>

<span data-ttu-id="52345-148">El precio de adquisición es de 100.000, el factor es 20, el tiempo de vida es de 10 años, y la depreciación comienza el 1 de enero.</span><span class="sxs-lookup"><span data-stu-id="52345-148">The acquisition price is 100,000, the factor is 20, the service life is 10 years, and depreciation starts on January 1.</span></span> <span data-ttu-id="52345-149">Las cantidades de depreciación y de valor neto en los libros sólo se muestran los primeros seis años del tiempo de vida.</span><span class="sxs-lookup"><span data-stu-id="52345-149">The depreciation amounts and net book value amounts are shown only for the first six years of service life.</span></span>

| <span data-ttu-id="52345-150">Año</span><span class="sxs-lookup"><span data-stu-id="52345-150">Year</span></span> | <span data-ttu-id="52345-151">Período</span><span class="sxs-lookup"><span data-stu-id="52345-151">Period</span></span>      | <span data-ttu-id="52345-152">Importe de depreciación</span><span class="sxs-lookup"><span data-stu-id="52345-152">Depreciation amount</span></span> | <span data-ttu-id="52345-153">Importe del valor neto en los libros</span><span class="sxs-lookup"><span data-stu-id="52345-153">Net book value amount</span></span> |
|------|-------------|---------------------|-----------------------|
| <span data-ttu-id="52345-154">1</span><span class="sxs-lookup"><span data-stu-id="52345-154">1</span></span>    | <span data-ttu-id="52345-155">31 de diciembre</span><span class="sxs-lookup"><span data-stu-id="52345-155">December 31</span></span> | <span data-ttu-id="52345-156">56.080,43</span><span class="sxs-lookup"><span data-stu-id="52345-156">56,080.43</span></span>           | <span data-ttu-id="52345-157">43.919,57</span><span class="sxs-lookup"><span data-stu-id="52345-157">43,919.57</span></span>             |
| <span data-ttu-id="52345-158">2</span><span class="sxs-lookup"><span data-stu-id="52345-158">2</span></span>    | <span data-ttu-id="52345-159">31 de diciembre</span><span class="sxs-lookup"><span data-stu-id="52345-159">December 31</span></span> | <span data-ttu-id="52345-160">10.665,70</span><span class="sxs-lookup"><span data-stu-id="52345-160">10,665.70</span></span>           | <span data-ttu-id="52345-161">33.253,87</span><span class="sxs-lookup"><span data-stu-id="52345-161">33,253.87</span></span>             |
| <span data-ttu-id="52345-162">3</span><span class="sxs-lookup"><span data-stu-id="52345-162">3</span></span>    | <span data-ttu-id="52345-163">31 de diciembre</span><span class="sxs-lookup"><span data-stu-id="52345-163">December 31</span></span> | <span data-ttu-id="52345-164">7.156,22</span><span class="sxs-lookup"><span data-stu-id="52345-164">7,156.22</span></span>            | <span data-ttu-id="52345-165">26.097,65</span><span class="sxs-lookup"><span data-stu-id="52345-165">26,097.65</span></span>             |
| <span data-ttu-id="52345-166">4</span><span class="sxs-lookup"><span data-stu-id="52345-166">4</span></span>    | <span data-ttu-id="52345-167">31 de diciembre</span><span class="sxs-lookup"><span data-stu-id="52345-167">December 31</span></span> | <span data-ttu-id="52345-168">5.538,06</span><span class="sxs-lookup"><span data-stu-id="52345-168">5,538.06</span></span>            | <span data-ttu-id="52345-169">20.559,59</span><span class="sxs-lookup"><span data-stu-id="52345-169">20,559.59</span></span>             |
| <span data-ttu-id="52345-170">5</span><span class="sxs-lookup"><span data-stu-id="52345-170">5</span></span>    | <span data-ttu-id="52345-171">31 de diciembre</span><span class="sxs-lookup"><span data-stu-id="52345-171">December 31</span></span> | <span data-ttu-id="52345-172">4.579,89</span><span class="sxs-lookup"><span data-stu-id="52345-172">4,579.89</span></span>            | <span data-ttu-id="52345-173">15.979,70</span><span class="sxs-lookup"><span data-stu-id="52345-173">15,979.70</span></span>             |
| <span data-ttu-id="52345-174">6</span><span class="sxs-lookup"><span data-stu-id="52345-174">6</span></span>    | <span data-ttu-id="52345-175">31 de diciembre</span><span class="sxs-lookup"><span data-stu-id="52345-175">December 31</span></span> | <span data-ttu-id="52345-176">3.937,36</span><span class="sxs-lookup"><span data-stu-id="52345-176">3,937.36</span></span>            | <span data-ttu-id="52345-177">12.042,34</span><span class="sxs-lookup"><span data-stu-id="52345-177">12,042.34</span></span>             |

## <a name="straight-line-depreciation"></a><span data-ttu-id="52345-178">Depreciación lineal</span><span class="sxs-lookup"><span data-stu-id="52345-178">Straight line depreciation</span></span>
<span data-ttu-id="52345-179">El valor del campo **Factor** es igual a **50**.</span><span class="sxs-lookup"><span data-stu-id="52345-179">The value in the **Factor** field is equal to **50**.</span></span> <span data-ttu-id="52345-180">En este caso, la depreciación es la misma en cada período y debe tener en cuenta las consecuencias de los valores que ha especificado en otros campos, como se describe en [Depreciación con amortización lineal de vida de servicio](straight-line-service-life-depreciation.md).</span><span class="sxs-lookup"><span data-stu-id="52345-180">In this case, the depreciation is the same in each period, and you should consider the implications of the values that you have specified in other fields, as described in [Straight line service life depreciation](straight-line-service-life-depreciation.md).</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]