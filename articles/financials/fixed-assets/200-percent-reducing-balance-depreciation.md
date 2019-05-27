---
title: Depreciación con amortización degresiva del 200%
description: Este artículo le ofrece una visión general del método de depreciación Depreciación con amortización degresiva del 200%.
author: saraschi2
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 13951
ms.assetid: 69b4e010-7683-4dc2-8a06-6d572f37e903
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ec51f9e12e31e81c56fab9e82d0fc18d45beb5e6
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569322"
---
# <a name="200-percent-reducing-balance-depreciation"></a><span data-ttu-id="61c56-103">Depreciación con amortización degresiva del 200%</span><span class="sxs-lookup"><span data-stu-id="61c56-103">200 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="61c56-104">Este artículo le ofrece una visión general del método de depreciación Depreciación con amortización degresiva del 200%.</span><span class="sxs-lookup"><span data-stu-id="61c56-104">This article gives an overview of the 200 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="61c56-105">Al configurar un método de depreciación de activos fijos y seleccionar el valor **Depreciación degresiva del 200%** en el campo **Método** de la página **Métodos de depreciación**, los activos fijos que se asignan al método de depreciación se deprecian por el mismo porcentaje en cada período de depreciación.</span><span class="sxs-lookup"><span data-stu-id="61c56-105">When you set up a fixed asset depreciation profile and select **200% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> <span data-ttu-id="61c56-106">El porcentaje se calcula en función del tiempo de vida del activo.</span><span class="sxs-lookup"><span data-stu-id="61c56-106">The percentage is calculated based on the service life of the asset.</span></span> <span data-ttu-id="61c56-107">Por ejemplo, si un activo tiene un tiempo de vida de cinco años, el porcentaje se calcula como 40 por ciento (200% ÷ 5).</span><span class="sxs-lookup"><span data-stu-id="61c56-107">For example, if an asset has a service life of five years, the percentage is calculated as 40 percent (200% ÷ 5).</span></span> 

<span data-ttu-id="61c56-108">Este método se conoce también como doble saldo decreciente.</span><span class="sxs-lookup"><span data-stu-id="61c56-108">This method is also known as double declining balance.</span></span>

<span data-ttu-id="61c56-109">Para configurar una depreciación con amortización degresiva del 200%, también debe seleccionar opciones en los campos **Año de depreciación** y **Frecuencia de períodos** en la página **Métodos de depreciación**.</span><span class="sxs-lookup"><span data-stu-id="61c56-109">To set up 200% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="61c56-110">Las opciones disponibles en el campo **Frecuencia de períodos** varían en función del valor seleccionado en el campo **Año de depreciación**.</span><span class="sxs-lookup"><span data-stu-id="61c56-110">The options that are available in the **Period frequency** field vary, depending on the value that you select in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="61c56-111">Selección de un año de depreciación</span><span class="sxs-lookup"><span data-stu-id="61c56-111">Select a depreciation year</span></span>
<span data-ttu-id="61c56-112">Puede seleccionar **Calendario** o **Fiscal** en el campo **Año de depreciación** de la página **Métodos de depreciación**.</span><span class="sxs-lookup"><span data-stu-id="61c56-112">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="61c56-113">El valor predeterminado es **Calendario**.</span><span class="sxs-lookup"><span data-stu-id="61c56-113">The default value is **Calendar**.</span></span> 

<span data-ttu-id="61c56-114">La selección determina las opciones disponibles en el campo **Frecuencia de períodos**.</span><span class="sxs-lookup"><span data-stu-id="61c56-114">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="61c56-115">Este campo define las fechas de registro de acumulación de depreciación a lo largo del año de calendario.</span><span class="sxs-lookup"><span data-stu-id="61c56-115">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="61c56-116">Calendario</span><span class="sxs-lookup"><span data-stu-id="61c56-116">Calendar</span></span>

<span data-ttu-id="61c56-117">Puede elegir mantener el valor predeterminado en el campo **Año de depreciación**, **Calendario**.</span><span class="sxs-lookup"><span data-stu-id="61c56-117">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="61c56-118">La opción **Calendario** actualiza la base de depreciación el 1 de enero de cada año.</span><span class="sxs-lookup"><span data-stu-id="61c56-118">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="61c56-119">Normalmente, la depreciación es el valor neto en los libros menos el valor residual.</span><span class="sxs-lookup"><span data-stu-id="61c56-119">Typically, the depreciation is the net book value minus the scrap value.</span></span> <span data-ttu-id="61c56-120">En el ejemplo, más adelante en este tema, la base de depreciación es el numerador en la primera expresión en los cálculos de la columna de cálculos.</span><span class="sxs-lookup"><span data-stu-id="61c56-120">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="61c56-121">Si selecciona **Calendario** como año de depreciación, aparecen las siguientes opciones disponibles en el campo **Frecuencia de períodos**:</span><span class="sxs-lookup"><span data-stu-id="61c56-121">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="61c56-122">**Anual** registra un importe el 31 de diciembre.</span><span class="sxs-lookup"><span data-stu-id="61c56-122">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="61c56-123">**Mensual** registra un importe mensual al final de cada mes del calendario.</span><span class="sxs-lookup"><span data-stu-id="61c56-123">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="61c56-124">**Trimestral** registra un importe trimestral al final de cada trimestre de calendario (31 de marzo, 30 de junio, 30 de septiembre y 31 de diciembre).</span><span class="sxs-lookup"><span data-stu-id="61c56-124">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="61c56-125">**Semestral** registra un importe semestral en la mitad del año del calendario (30 de junio y 31 de diciembre).</span><span class="sxs-lookup"><span data-stu-id="61c56-125">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="61c56-126">**Diariamente** registra el importe de depreciación para el método de depreciación diaria utilizando una transacción para cada día.</span><span class="sxs-lookup"><span data-stu-id="61c56-126">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="61c56-127">Fiscal</span><span class="sxs-lookup"><span data-stu-id="61c56-127">Fiscal</span></span>

<span data-ttu-id="61c56-128">Si selecciona **Fiscal** en el campo **Año de depreciación**, la depreciación degresiva del 200% se calcula en base al ejercicio fiscal del calendario fiscal especificado para el libro o para el calendario fiscal seleccionado en la página **Libro mayor**.</span><span class="sxs-lookup"><span data-stu-id="61c56-128">If you select **Fiscal** in the **Depreciation** year field, 200% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="61c56-129">Los calendarios fiscales se configuran en la página **Calendarios fiscales**.</span><span class="sxs-lookup"><span data-stu-id="61c56-129">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="61c56-130">Por ejemplo, para el ejercicio del 1 de julio al 30 de junio, el cálculo de la depreciación comienza el 1 de julio.</span><span class="sxs-lookup"><span data-stu-id="61c56-130">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="61c56-131">El ejercicio no puede ser superior ni inferior a los 12 meses.</span><span class="sxs-lookup"><span data-stu-id="61c56-131">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="61c56-132">La depreciación se ajusta para cada período.</span><span class="sxs-lookup"><span data-stu-id="61c56-132">The depreciation is adjusted for each period.</span></span> <span data-ttu-id="61c56-133">La extensión del siguiente ejercicio se determina por los períodos fiscales configurados en la página **Calendarios fiscales**.</span><span class="sxs-lookup"><span data-stu-id="61c56-133">The length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="61c56-134">Si selecciona **Fiscal** como año de depreciación, aparecen las siguientes opciones disponibles en el campo **Frecuencia de períodos**:</span><span class="sxs-lookup"><span data-stu-id="61c56-134">When **Fiscal** is selected as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="61c56-135">**Anual** registra el importe total de la depreciación calculada para el ejercicio como un importe de la última fecha del ejercicio.</span><span class="sxs-lookup"><span data-stu-id="61c56-135">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year as one amount, on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="61c56-136">**Período fiscal** registra el importe total de depreciación calculado para el ejercicio.</span><span class="sxs-lookup"><span data-stu-id="61c56-136">**Fiscal period** posts the total amount of the depreciation that is calculated for the fiscal year.</span></span> <span data-ttu-id="61c56-137">Este importe se acumula en los períodos fiscales definidos en la página **Calendarios fiscales**.</span><span class="sxs-lookup"><span data-stu-id="61c56-137">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-200-reducing-balance-depreciation"></a><span data-ttu-id="61c56-138">Ejemplo de depreciación degresiva del 200%</span><span class="sxs-lookup"><span data-stu-id="61c56-138">Example of 200% reducing balance depreciation</span></span>

|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="61c56-139">Coste de adquisición</span><span class="sxs-lookup"><span data-stu-id="61c56-139">Acquisition cost</span></span>               | <span data-ttu-id="61c56-140">11.000</span><span class="sxs-lookup"><span data-stu-id="61c56-140">11,000</span></span> |
| <span data-ttu-id="61c56-141">Valor residual</span><span class="sxs-lookup"><span data-stu-id="61c56-141">Salvage value</span></span>                  | <span data-ttu-id="61c56-142">1.000</span><span class="sxs-lookup"><span data-stu-id="61c56-142">1, 000</span></span> |
| <span data-ttu-id="61c56-143">Base de depreciación</span><span class="sxs-lookup"><span data-stu-id="61c56-143">Depreciation base</span></span>              | <span data-ttu-id="61c56-144">10.000</span><span class="sxs-lookup"><span data-stu-id="61c56-144">10,000</span></span> |
| <span data-ttu-id="61c56-145">Años de tiempo de vida</span><span class="sxs-lookup"><span data-stu-id="61c56-145">Service life years</span></span>             | <span data-ttu-id="61c56-146">5</span><span class="sxs-lookup"><span data-stu-id="61c56-146">5</span></span>      |
| <span data-ttu-id="61c56-147">Porcentaje de depreciación anual</span><span class="sxs-lookup"><span data-stu-id="61c56-147">Yearly depreciation percentage</span></span> | <span data-ttu-id="61c56-148">40%</span><span class="sxs-lookup"><span data-stu-id="61c56-148">40%</span></span>    |

<span data-ttu-id="61c56-149">El método de depreciación degresiva del 200% divide el 200 por ciento entre los años de tiempo de vida.</span><span class="sxs-lookup"><span data-stu-id="61c56-149">The 200% reducing balance method divides 200 percent by the service life years.</span></span> <span data-ttu-id="61c56-150">El porcentaje se multiplicará por el valor neto en los libros del activo para determinar el importe de depreciación durante el año.</span><span class="sxs-lookup"><span data-stu-id="61c56-150">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="61c56-151">Periodo</span><span class="sxs-lookup"><span data-stu-id="61c56-151">Period</span></span> | <span data-ttu-id="61c56-152">Cálculo del importe de depreciación anual</span><span class="sxs-lookup"><span data-stu-id="61c56-152">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="61c56-153">Valor neto</span><span class="sxs-lookup"><span data-stu-id="61c56-153">Book value</span></span>             | <span data-ttu-id="61c56-154">Valor neto en los libros al final del año</span><span class="sxs-lookup"><span data-stu-id="61c56-154">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| <span data-ttu-id="61c56-155">Año 1</span><span class="sxs-lookup"><span data-stu-id="61c56-155">Year 1</span></span> | <span data-ttu-id="61c56-156">(11.000 – 1.000) × 40% = 4.000</span><span class="sxs-lookup"><span data-stu-id="61c56-156">(11,000 – 1,000) × 40% = 4,000</span></span>                | <span data-ttu-id="61c56-157">11.000 - 4.000 = 7.000</span><span class="sxs-lookup"><span data-stu-id="61c56-157">11,000 – 4,000 = 7,000</span></span> | <span data-ttu-id="61c56-158">11.000 - 1.000 – 4.000 = 6.000</span><span class="sxs-lookup"><span data-stu-id="61c56-158">11,000 – 1,000 – 4,000 = 6,000</span></span>        |
| <span data-ttu-id="61c56-159">Año 2</span><span class="sxs-lookup"><span data-stu-id="61c56-159">Year 2</span></span> | <span data-ttu-id="61c56-160">6.000 × 40% = 2.400</span><span class="sxs-lookup"><span data-stu-id="61c56-160">6,000 × 40% = 2,400</span></span>                           | <span data-ttu-id="61c56-161">7.000 - 2.400 = 4.600</span><span class="sxs-lookup"><span data-stu-id="61c56-161">7,000 – 2,400 = 4,600</span></span>  | <span data-ttu-id="61c56-162">6.000 - 2.400 = 3.600</span><span class="sxs-lookup"><span data-stu-id="61c56-162">6,000 – 2,400 = 3,600</span></span>                 |
| <span data-ttu-id="61c56-163">Año 3</span><span class="sxs-lookup"><span data-stu-id="61c56-163">Year 3</span></span> | <span data-ttu-id="61c56-164">3.600 × 40% = 1.440</span><span class="sxs-lookup"><span data-stu-id="61c56-164">3,600 × 40% = 1,440</span></span>                           | <span data-ttu-id="61c56-165">4.600 - 1.440 = 3.160</span><span class="sxs-lookup"><span data-stu-id="61c56-165">4,600 – 1,440 = 3,160</span></span>  | <span data-ttu-id="61c56-166">3.600 - 1.440 = 2.160</span><span class="sxs-lookup"><span data-stu-id="61c56-166">3,600 – 1,440 = 2,160</span></span>                 |

> [!NOTE] 
> <span data-ttu-id="61c56-167">Normalmente, cuando el importe que se calcula mediante el método de depreciación degresiva del 200% resulta inferior al importe que se calcularía con el método de amortización lineal, se realiza una conversión al método de amortización lineal para la vida restante.</span><span class="sxs-lookup"><span data-stu-id="61c56-167">Typically, when the amount that is calculated by using the 200% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>



