---
title: Depreciación manual
description: Este artículo ofrece una visión general del método de depreciación manual.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13811
ms.assetid: b0e837c9-515a-4aed-9060-5ec94f37edeb
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 84cde511ab0b5cbe4b99e72832bf548336b6b28c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447465"
---
# <a name="manual-depreciation"></a><span data-ttu-id="1f1fe-103">Depreciación manual</span><span class="sxs-lookup"><span data-stu-id="1f1fe-103">Manual depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="1f1fe-104">Este artículo ofrece una visión general del método de depreciación manual.</span><span class="sxs-lookup"><span data-stu-id="1f1fe-104">This article gives an overview of the manual depreciation method.</span></span>

<span data-ttu-id="1f1fe-105">Si configura un perfil de depreciación de activos fijos y selecciona **Manual** en el campo **Método** de la página **Perfiles de depreciación**, la depreciación de los activos fijos asignados al perfil de depreciación vendrá determinada por el porcentaje que se especifique para cada intervalo del año natural.</span><span class="sxs-lookup"><span data-stu-id="1f1fe-105">When you set up a fixed asset depreciation profile and select **Manual** in the **Method** field on the **Depreciation profiles** page, the depreciation of fixed assets that are assigned to the depreciation profile is determined by the percentage that you enter for each interval in the calendar year.</span></span> <span data-ttu-id="1f1fe-106">Los intervalos para los que configure porcentajes se registran de acuerdo con el valor que seleccione en el campo **Frecuencia de períodos** de la ficha desplegable **General**, en la página **Perfiles de depreciación**.</span><span class="sxs-lookup"><span data-stu-id="1f1fe-106">The intervals that you set up percentages for are posted according to the value that you select in the **Period frequency** field on the **General** FastTab of the **Depreciation profiles** page.</span></span> <span data-ttu-id="1f1fe-107">Estos son los valores que se pueden seleccionar:</span><span class="sxs-lookup"><span data-stu-id="1f1fe-107">Here are the values that you can select:</span></span>

-   <span data-ttu-id="1f1fe-108">Anual</span><span class="sxs-lookup"><span data-stu-id="1f1fe-108">Yearly</span></span>
-   <span data-ttu-id="1f1fe-109">Mensual</span><span class="sxs-lookup"><span data-stu-id="1f1fe-109">Monthly</span></span>
-   <span data-ttu-id="1f1fe-110">Trimestral</span><span class="sxs-lookup"><span data-stu-id="1f1fe-110">Quarterly</span></span>
-   <span data-ttu-id="1f1fe-111">Semestral</span><span class="sxs-lookup"><span data-stu-id="1f1fe-111">Half-Yearly</span></span>
-   <span data-ttu-id="1f1fe-112">Diariamente</span><span class="sxs-lookup"><span data-stu-id="1f1fe-112">Daily</span></span>

<span data-ttu-id="1f1fe-113">Tras seleccionar la frecuencia del período, haga clic en **Programaciones manuales** y configure porcentajes para cada intervalo de registro.</span><span class="sxs-lookup"><span data-stu-id="1f1fe-113">After you select the period frequency, click **Manual schedules**, and set up percentages for each posting interval.</span></span> <span data-ttu-id="1f1fe-114">Juntos, las programaciones manuales y los intervalos de registro definen el importe de depreciación, tal y como aparece en los siguientes ejemplos de este artículo.</span><span class="sxs-lookup"><span data-stu-id="1f1fe-114">Together, the manual schedules and the posting intervals define the depreciation amount, as shown in the examples later in this article.</span></span> <span data-ttu-id="1f1fe-115">La depreciación manual siempre se calcula como un porcentaje del precio de adquisición.</span><span class="sxs-lookup"><span data-stu-id="1f1fe-115">Manual depreciation is always calculated as a percentage of the acquisition price.</span></span> <span data-ttu-id="1f1fe-116">En la depreciación manual, los porcentajes especificados en los intervalos de la depreciación no tienen que sumar el 100 por cien.</span><span class="sxs-lookup"><span data-stu-id="1f1fe-116">For manual depreciation, the percentages that you enter in the intervals of the depreciation don't have to add up to 100 percent.</span></span> <span data-ttu-id="1f1fe-117">La depreciación manual es un método de depreciación flexible que normalmente se utiliza para definir un perfil de depreciación extraordinario en la página **Libros**, como una depreciación no periódica para objetivos especiales (por ejemplo, para cuestiones impositivas).</span><span class="sxs-lookup"><span data-stu-id="1f1fe-117">Manual depreciation is a flexible depreciation method that is often used to define an extraordinary depreciation profile on the **Books** page, such as a non-periodic depreciation for special purposes (for example, tax).</span></span>

## <a name="examples"></a><span data-ttu-id="1f1fe-118">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="1f1fe-118">Examples</span></span>
<span data-ttu-id="1f1fe-119">Precio de adquisición: 11.000,00 Valor residual previsto: 1.000,00 La siguiente tabla muestra los intervalos y los porcentajes que se configuran en la página **Programas de método de depreciación de activos fijos**.</span><span class="sxs-lookup"><span data-stu-id="1f1fe-119">Acquisition price: 11,000.00 Expected scrap value: 1,000.00 The following table shows the intervals and percentages that you set up on the **Fixed asset depreciation profile schedules** page.</span></span>

| <span data-ttu-id="1f1fe-120">Número de intervalo</span><span class="sxs-lookup"><span data-stu-id="1f1fe-120">Interval number</span></span> | <span data-ttu-id="1f1fe-121">Porcentaje</span><span class="sxs-lookup"><span data-stu-id="1f1fe-121">Percentage</span></span> |
|-----------------|------------|
| <span data-ttu-id="1f1fe-122">1</span><span class="sxs-lookup"><span data-stu-id="1f1fe-122">1</span></span>               | <span data-ttu-id="1f1fe-123">10,00</span><span class="sxs-lookup"><span data-stu-id="1f1fe-123">10.00</span></span>      |
| <span data-ttu-id="1f1fe-124">2</span><span class="sxs-lookup"><span data-stu-id="1f1fe-124">2</span></span>               | <span data-ttu-id="1f1fe-125">50,00</span><span class="sxs-lookup"><span data-stu-id="1f1fe-125">50.00</span></span>      |
| <span data-ttu-id="1f1fe-126">3</span><span class="sxs-lookup"><span data-stu-id="1f1fe-126">3</span></span>               | <span data-ttu-id="1f1fe-127">8,00</span><span class="sxs-lookup"><span data-stu-id="1f1fe-127">8.00</span></span>       |

<span data-ttu-id="1f1fe-128">La tabla siguiente muestra cómo se calcula la depreciación para cada intervalo.</span><span class="sxs-lookup"><span data-stu-id="1f1fe-128">The following table shows how the depreciation for each interval is calculated.</span></span>

|  <span data-ttu-id="1f1fe-129">Número de intervalo</span><span class="sxs-lookup"><span data-stu-id="1f1fe-129">Interval number</span></span> | <span data-ttu-id="1f1fe-130">Cálculo del importe de depreciación anual</span><span class="sxs-lookup"><span data-stu-id="1f1fe-130">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="1f1fe-131">Valor neto en los libros al final del intervalo</span><span class="sxs-lookup"><span data-stu-id="1f1fe-131">Net book value at the end of the interval</span></span> |
|------------------|-----------------------------------------------|-------------------------------------------|
| <span data-ttu-id="1f1fe-132">1</span><span class="sxs-lookup"><span data-stu-id="1f1fe-132">1</span></span>                | <span data-ttu-id="1f1fe-133">(11.000 – 1.000) × 10% = 1.000</span><span class="sxs-lookup"><span data-stu-id="1f1fe-133">(11,000 – 1,000) × 10% = 1,000</span></span>                | <span data-ttu-id="1f1fe-134">10.000 (11.000 – 1.000)</span><span class="sxs-lookup"><span data-stu-id="1f1fe-134">10,000 (11,000 – 1,000)</span></span>                   |
| <span data-ttu-id="1f1fe-135">2</span><span class="sxs-lookup"><span data-stu-id="1f1fe-135">2</span></span>                | <span data-ttu-id="1f1fe-136">(11.000 – 1.000) × 50% = 5.000</span><span class="sxs-lookup"><span data-stu-id="1f1fe-136">(11,000 – 1,000) × 50% = 5,000</span></span>                | <span data-ttu-id="1f1fe-137">5.000 (10.000 – 5.000)</span><span class="sxs-lookup"><span data-stu-id="1f1fe-137">5,000 (10,000 – 5,000)</span></span>                    |
| <span data-ttu-id="1f1fe-138">3</span><span class="sxs-lookup"><span data-stu-id="1f1fe-138">3</span></span>                | <span data-ttu-id="1f1fe-139">(11.000 – 1.000) × 8% = 800</span><span class="sxs-lookup"><span data-stu-id="1f1fe-139">(11,000 – 1,000) × 8% = 800</span></span>                   | <span data-ttu-id="1f1fe-140">4.200 (5.000 – 800)</span><span class="sxs-lookup"><span data-stu-id="1f1fe-140">4,200 (5,000 – 800)</span></span>                       |

<span data-ttu-id="1f1fe-141">Si selecciona **Mensual** en el campo **Frecuencia de períodos**, se configuran 12 intervalos de programación manual.</span><span class="sxs-lookup"><span data-stu-id="1f1fe-141">If you select **Monthly** in the **Period frequency** field, you set up 12 manual schedule intervals.</span></span> <span data-ttu-id="1f1fe-142">La tabla que sigue muestra los importes de depreciación para los dos primeros intervalos.</span><span class="sxs-lookup"><span data-stu-id="1f1fe-142">The following table shows the depreciation amounts for the first two intervals.</span></span>

| <span data-ttu-id="1f1fe-143">Intervalo</span><span class="sxs-lookup"><span data-stu-id="1f1fe-143">Interval</span></span> | <span data-ttu-id="1f1fe-144">Importe de depreciación</span><span class="sxs-lookup"><span data-stu-id="1f1fe-144">Depreciation amount</span></span>            |
|----------|--------------------------------|
| <span data-ttu-id="1f1fe-145">Enero</span><span class="sxs-lookup"><span data-stu-id="1f1fe-145">January</span></span>  | <span data-ttu-id="1f1fe-146">(11.000 – 1.000) × 10% = 1.000</span><span class="sxs-lookup"><span data-stu-id="1f1fe-146">(11,000 – 1,000) × 10% = 1,000</span></span> |
| <span data-ttu-id="1f1fe-147">Febrero</span><span class="sxs-lookup"><span data-stu-id="1f1fe-147">February</span></span> | <span data-ttu-id="1f1fe-148">(11.000 – 1.000) × 50% = 5.000</span><span class="sxs-lookup"><span data-stu-id="1f1fe-148">(11,000 – 1,000) × 50% = 5,000</span></span> |

<span data-ttu-id="1f1fe-149">Si selecciona <strong>Semestral</strong> en el campo *<strong><em>Frecuencia del período</em>*</strong>, se configuran dos intervalos de programación manual.</span><span class="sxs-lookup"><span data-stu-id="1f1fe-149">If you select <strong>Half-Yearly</strong> in the *<strong><em>Period frequency</em>* field</strong>, you set up two manual schedule intervals.</span></span> <span data-ttu-id="1f1fe-150">La tabla que sigue muestra los importes de depreciación para estos dos primeros intervalos.</span><span class="sxs-lookup"><span data-stu-id="1f1fe-150">The following table shows the depreciation amounts for those two intervals.</span></span>

| <span data-ttu-id="1f1fe-151">Intervalo</span><span class="sxs-lookup"><span data-stu-id="1f1fe-151">Interval</span></span>    | <span data-ttu-id="1f1fe-152">Importe de depreciación</span><span class="sxs-lookup"><span data-stu-id="1f1fe-152">Depreciation amount</span></span>            |
|-------------|--------------------------------|
| <span data-ttu-id="1f1fe-153">30 de junio</span><span class="sxs-lookup"><span data-stu-id="1f1fe-153">June 30</span></span>     | <span data-ttu-id="1f1fe-154">(11.000 – 1.000) × 10% = 1.000</span><span class="sxs-lookup"><span data-stu-id="1f1fe-154">(11,000 – 1,000) × 10% = 1,000</span></span> |
| <span data-ttu-id="1f1fe-155">31 de diciembre</span><span class="sxs-lookup"><span data-stu-id="1f1fe-155">December 31</span></span> | <span data-ttu-id="1f1fe-156">(11.000 – 1.000) × 50% = 5.000</span><span class="sxs-lookup"><span data-stu-id="1f1fe-156">(11,000 – 1,000) × 50% = 5,000</span></span> |

<span data-ttu-id="1f1fe-157">El total de porcentajes de todos los intervalos no tiene que ser 100.</span><span class="sxs-lookup"><span data-stu-id="1f1fe-157">The total of percentages for all intervals doesn't have to be 100.</span></span> <span data-ttu-id="1f1fe-158">No obstante, recibirá un mensaje si el valor en el campo **Porcentaje acumulado** en la página **Programas de método de depreciación de activos fijos** es distinto a **100**.</span><span class="sxs-lookup"><span data-stu-id="1f1fe-158">However, you receive a message if the value in the **Cumulative percentage** field on the **Fixed asset depreciation profile schedules** page isn't **100**.</span></span>



