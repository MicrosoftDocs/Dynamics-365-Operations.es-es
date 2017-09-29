---
title: "Depreciación manual"
description: "Este artículo ofrece una visión general del método de depreciación manual."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 13811
ms.assetid: b0e837c9-515a-4aed-9060-5ec94f37edeb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: e43b9397dd4e362eff9d78f302732e6bcc53d1db
ms.contentlocale: es-es
ms.lasthandoff: 07/18/2017

---

# <a name="manual-depreciation"></a><span data-ttu-id="9f318-103">Depreciación manual</span><span class="sxs-lookup"><span data-stu-id="9f318-103">Manual depreciation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="9f318-104">Este artículo ofrece una visión general del método de depreciación manual.</span><span class="sxs-lookup"><span data-stu-id="9f318-104">This article gives an overview of the manual depreciation method.</span></span>

<span data-ttu-id="9f318-105">Si configura un perfil de depreciación de activos fijos y selecciona **Manual** en el campo **Método** de la página **Perfiles de depreciación**, la depreciación de los activos fijos asignados al perfil de depreciación vendrá determinada por el porcentaje que se especifique para cada intervalo del año natural.</span><span class="sxs-lookup"><span data-stu-id="9f318-105">When you set up a fixed asset depreciation profile and select **Manual** in the **Method** field on the **Depreciation profiles** page, the depreciation of fixed assets that are assigned to the depreciation profile is determined by the percentage that you enter for each interval in the calendar year.</span></span> <span data-ttu-id="9f318-106">Los intervalos para los que configure porcentajes se registran de acuerdo con el valor que seleccione en el campo **Frecuencia de períodos** de la ficha desplegable **General**, en la página **Perfiles de depreciación**.</span><span class="sxs-lookup"><span data-stu-id="9f318-106">The intervals that you set up percentages for are posted according to the value that you select in the **Period frequency** field on the **General** FastTab of the **Depreciation profiles** page.</span></span> <span data-ttu-id="9f318-107">Estos son los valores que se pueden seleccionar:</span><span class="sxs-lookup"><span data-stu-id="9f318-107">Here are the values that you can select:</span></span>

-   <span data-ttu-id="9f318-108">Anual</span><span class="sxs-lookup"><span data-stu-id="9f318-108">Yearly</span></span>
-   <span data-ttu-id="9f318-109">Mensual</span><span class="sxs-lookup"><span data-stu-id="9f318-109">Monthly</span></span>
-   <span data-ttu-id="9f318-110">Trimestral</span><span class="sxs-lookup"><span data-stu-id="9f318-110">Quarterly</span></span>
-   <span data-ttu-id="9f318-111">Semestral</span><span class="sxs-lookup"><span data-stu-id="9f318-111">Half-Yearly</span></span>
-   <span data-ttu-id="9f318-112">Diariamente</span><span class="sxs-lookup"><span data-stu-id="9f318-112">Daily</span></span>

<span data-ttu-id="9f318-113">Tras seleccionar la frecuencia del período, haga clic en **Programaciones manuales** y configure porcentajes para cada intervalo de registro.</span><span class="sxs-lookup"><span data-stu-id="9f318-113">After you select the period frequency, click **Manual schedules**, and set up percentages for each posting interval.</span></span> <span data-ttu-id="9f318-114">Juntos, las programaciones manuales y los intervalos de registro definen el importe de depreciación, tal y como aparece en los siguientes ejemplos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="9f318-114">Together, the manual schedules and the posting intervals define the depreciation amount, as shown in the examples later in this article.</span></span> <span data-ttu-id="9f318-115">La depreciación manual siempre se calcula como un porcentaje del precio de adquisición.</span><span class="sxs-lookup"><span data-stu-id="9f318-115">Manual depreciation is always calculated as a percentage of the acquisition price.</span></span> <span data-ttu-id="9f318-116">En la depreciación manual, los porcentajes especificados en los intervalos de la depreciación no tienen que sumar el 100 por cien.</span><span class="sxs-lookup"><span data-stu-id="9f318-116">For manual depreciation, the percentages that you enter in the intervals of the depreciation don't have to add up to 100 percent.</span></span> <span data-ttu-id="9f318-117">La depreciación manual es un método de depreciación flexible que normalmente se utiliza para definir un perfil de depreciación extraordinario en la página **Libros**, como una depreciación no periódica para objetivos especiales (por ejemplo, para cuestiones impositivas).</span><span class="sxs-lookup"><span data-stu-id="9f318-117">Manual depreciation is a flexible depreciation method that is often used to define an extraordinary depreciation profile on the **Books** page, such as a non-periodic depreciation for special purposes (for example, tax).</span></span>

## <a name="examples"></a><span data-ttu-id="9f318-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="9f318-118">Examples</span></span>
<span data-ttu-id="9f318-119">Precio de adquisición: 11.000,00 Valor residual previsto: 1.000,00 La siguiente tabla muestra los intervalos y los porcentajes que se configuran en la página **Programas de método de depreciación de activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="9f318-119">Acquisition price: 11,000.00 Expected scrap value: 1,000.00 The following table shows the intervals and percentages that you set up on the **Fixed asset depreciation profile schedules** page.</span></span>

| <span data-ttu-id="9f318-120">Número de intervalo</span><span class="sxs-lookup"><span data-stu-id="9f318-120">Interval number</span></span> | <span data-ttu-id="9f318-121">Porcentaje</span><span class="sxs-lookup"><span data-stu-id="9f318-121">Percentage</span></span> |
|-----------------|------------|
| <span data-ttu-id="9f318-122">1</span><span class="sxs-lookup"><span data-stu-id="9f318-122">1</span></span>               | <span data-ttu-id="9f318-123">10,00</span><span class="sxs-lookup"><span data-stu-id="9f318-123">10.00</span></span>      |
| <span data-ttu-id="9f318-124">2</span><span class="sxs-lookup"><span data-stu-id="9f318-124">2</span></span>               | <span data-ttu-id="9f318-125">50,00</span><span class="sxs-lookup"><span data-stu-id="9f318-125">50.00</span></span>      |
| <span data-ttu-id="9f318-126">3</span><span class="sxs-lookup"><span data-stu-id="9f318-126">3</span></span>               | <span data-ttu-id="9f318-127">8,00</span><span class="sxs-lookup"><span data-stu-id="9f318-127">8.00</span></span>       |

<span data-ttu-id="9f318-128">La tabla siguiente muestra cómo se calcula la depreciación para cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="9f318-128">The following table shows how the depreciation for each interval is calculated.</span></span>

|  <span data-ttu-id="9f318-129">Número de intervalo</span><span class="sxs-lookup"><span data-stu-id="9f318-129">Interval number</span></span> | <span data-ttu-id="9f318-130">Cálculo del importe de depreciación anual</span><span class="sxs-lookup"><span data-stu-id="9f318-130">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="9f318-131">Valor neto en los libros al final del intervalo</span><span class="sxs-lookup"><span data-stu-id="9f318-131">Net book value at the end of the interval</span></span> |
|------------------|-----------------------------------------------|-------------------------------------------|
| <span data-ttu-id="9f318-132">1</span><span class="sxs-lookup"><span data-stu-id="9f318-132">1</span></span>                | <span data-ttu-id="9f318-133">(11.000 – 1.000) × 10% = 1.000</span><span class="sxs-lookup"><span data-stu-id="9f318-133">(11,000 – 1,000) × 10% = 1,000</span></span>                | <span data-ttu-id="9f318-134">10.000 (11.000 – 1.000)</span><span class="sxs-lookup"><span data-stu-id="9f318-134">10,000 (11,000 – 1,000)</span></span>                   |
| <span data-ttu-id="9f318-135">2</span><span class="sxs-lookup"><span data-stu-id="9f318-135">2</span></span>                | <span data-ttu-id="9f318-136">(11.000 – 1.000) × 50% = 5.000</span><span class="sxs-lookup"><span data-stu-id="9f318-136">(11,000 – 1,000) × 50% = 5,000</span></span>                | <span data-ttu-id="9f318-137">5.000 (10.000 – 5.000)</span><span class="sxs-lookup"><span data-stu-id="9f318-137">5,000 (10,000 – 5,000)</span></span>                    |
| <span data-ttu-id="9f318-138">3</span><span class="sxs-lookup"><span data-stu-id="9f318-138">3</span></span>                | <span data-ttu-id="9f318-139">(11.000 – 1.000) × 8% = 800</span><span class="sxs-lookup"><span data-stu-id="9f318-139">(11,000 – 1,000) × 8% = 800</span></span>                   | <span data-ttu-id="9f318-140">4.200 (5.000 – 800)</span><span class="sxs-lookup"><span data-stu-id="9f318-140">4,200 (5,000 – 800)</span></span>                       |

<span data-ttu-id="9f318-141">Si selecciona **Mensual** en el campo**Frecuencia de períodos**, se configuran 12 intervalos de programación manual.</span><span class="sxs-lookup"><span data-stu-id="9f318-141">If you select **Monthly** in the **Period frequency** field, you set up 12 manual schedule intervals.</span></span> <span data-ttu-id="9f318-142">La tabla que sigue muestra los importes de depreciación para los dos primeros intervalos.</span><span class="sxs-lookup"><span data-stu-id="9f318-142">The following table shows the depreciation amounts for the first two intervals.</span></span>

| <span data-ttu-id="9f318-143">Intervalo</span><span class="sxs-lookup"><span data-stu-id="9f318-143">Interval</span></span> | <span data-ttu-id="9f318-144">Importe de depreciación</span><span class="sxs-lookup"><span data-stu-id="9f318-144">Depreciation amount</span></span>            |
|----------|--------------------------------|
| <span data-ttu-id="9f318-145">Enero</span><span class="sxs-lookup"><span data-stu-id="9f318-145">January</span></span>  | <span data-ttu-id="9f318-146">(11.000 – 1.000) × 10% = 1.000</span><span class="sxs-lookup"><span data-stu-id="9f318-146">(11,000 – 1,000) × 10% = 1,000</span></span> |
| <span data-ttu-id="9f318-147">Febrero</span><span class="sxs-lookup"><span data-stu-id="9f318-147">February</span></span> | <span data-ttu-id="9f318-148">(11.000 – 1.000) × 50% = 5.000</span><span class="sxs-lookup"><span data-stu-id="9f318-148">(11,000 – 1,000) × 50% = 5,000</span></span> |

<span data-ttu-id="9f318-149">Si selecciona **Semestral** en el campo ****Frecuencia de períodos****, se configuran dos intervalos de programación manual.</span><span class="sxs-lookup"><span data-stu-id="9f318-149">If you select **Half-Yearly** in the ****Period frequency** field**, you set up two manual schedule intervals.</span></span> <span data-ttu-id="9f318-150">La tabla que sigue muestra los importes de depreciación para estos dos primeros intervalos.</span><span class="sxs-lookup"><span data-stu-id="9f318-150">The following table shows the depreciation amounts for those two intervals.</span></span>

| <span data-ttu-id="9f318-151">Intervalo</span><span class="sxs-lookup"><span data-stu-id="9f318-151">Interval</span></span>    | <span data-ttu-id="9f318-152">Importe de depreciación</span><span class="sxs-lookup"><span data-stu-id="9f318-152">Depreciation amount</span></span>            |
|-------------|--------------------------------|
| <span data-ttu-id="9f318-153">30 de junio</span><span class="sxs-lookup"><span data-stu-id="9f318-153">June 30</span></span>     | <span data-ttu-id="9f318-154">(11.000 – 1.000) × 10% = 1.000</span><span class="sxs-lookup"><span data-stu-id="9f318-154">(11,000 – 1,000) × 10% = 1,000</span></span> |
| <span data-ttu-id="9f318-155">31 de diciembre</span><span class="sxs-lookup"><span data-stu-id="9f318-155">December 31</span></span> | <span data-ttu-id="9f318-156">(11.000 – 1.000) × 50% = 5.000</span><span class="sxs-lookup"><span data-stu-id="9f318-156">(11,000 – 1,000) × 50% = 5,000</span></span> |

<span data-ttu-id="9f318-157">El total de porcentajes de todos los intervalos no tiene que ser 100.</span><span class="sxs-lookup"><span data-stu-id="9f318-157">The total of percentages for all intervals doesn't have to be 100.</span></span> <span data-ttu-id="9f318-158">No obstante, recibirá un mensaje si el valor en el campo **Porcentaje acumulado** en la página **Programas de método de depreciación de activos fijos** es distinto a **100**.</span><span class="sxs-lookup"><span data-stu-id="9f318-158">However, you receive a message if the value in the **Cumulative percentage** field on the **Fixed asset depreciation profile schedules** page isn't **100**.</span></span>




