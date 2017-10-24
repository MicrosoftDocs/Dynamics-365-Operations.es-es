---
title: "Depreciación con amortización degresiva del 150%"
description: "Este artículo le ofrece una visión general del método de depreciación Depreciación con amortización degresiva del 150%."
author: saraschi2
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
ms.custom: 13891
ms.assetid: 36d1112d-921c-4fff-abe0-0ff2429848d3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 20572163bd32d059323cbb80e606ae344d70b7be
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="150-percent-reducing-balance-depreciation"></a><span data-ttu-id="a9afa-103">Depreciación con amortización degresiva del 150%</span><span class="sxs-lookup"><span data-stu-id="a9afa-103">150 percent reducing balance depreciation</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="a9afa-104">Este artículo le ofrece una visión general del método de depreciación Depreciación con amortización degresiva del 150%.</span><span class="sxs-lookup"><span data-stu-id="a9afa-104">This article gives an overview of the 150 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="a9afa-105">Al configurar un método de depreciación de activos fijos y seleccionar el valor **Depreciación degresiva del 150%** en el campo **Método** de la página **Métodos de depreciación**, los activos fijos que se asignan al método de depreciación se deprecian por el mismo porcentaje en cada período de depreciación.</span><span class="sxs-lookup"><span data-stu-id="a9afa-105">When you set up a fixed asset depreciation profile and select **150% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> <span data-ttu-id="a9afa-106">Este porcentaje se calcula en función del tiempo de vida del activo.</span><span class="sxs-lookup"><span data-stu-id="a9afa-106">This percentage is calculated based on the service life of the asset.</span></span> <span data-ttu-id="a9afa-107">Por ejemplo, si un activo tiene un tiempo de vida de cinco años, el porcentaje se calcula como 30 por ciento (150% ÷ 5).</span><span class="sxs-lookup"><span data-stu-id="a9afa-107">For example, if an asset has a service life of five years, the percentage is calculated as 30 percent (150% ÷ 5).</span></span> 

<span data-ttu-id="a9afa-108">Para configurar una depreciación con amortización degresiva del 150%, también debe seleccionar opciones en los campos **Año de depreciación** y **Frecuencia de períodos** en la página **Métodos de depreciación**.</span><span class="sxs-lookup"><span data-stu-id="a9afa-108">To set up 150% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="a9afa-109">Las opciones disponibles en el campo **Frecuencia de períodos** varían en función del valor seleccionado en el campo **Año de depreciación**.</span><span class="sxs-lookup"><span data-stu-id="a9afa-109">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="selection-of-depreciation-year"></a><span data-ttu-id="a9afa-110">Selección del año de depreciación</span><span class="sxs-lookup"><span data-stu-id="a9afa-110">Selection of depreciation year</span></span>
<span data-ttu-id="a9afa-111">Puede seleccionar **Calendario** o **Fiscal** en el campo **Año de depreciación** de la página **Métodos de depreciación**.</span><span class="sxs-lookup"><span data-stu-id="a9afa-111">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> 

<span data-ttu-id="a9afa-112">El valor predeterminado es **Calendario**.</span><span class="sxs-lookup"><span data-stu-id="a9afa-112">The default value is **Calendar**.</span></span> <span data-ttu-id="a9afa-113">La selección determina las opciones disponibles en el campo **Frecuencia de períodos**.</span><span class="sxs-lookup"><span data-stu-id="a9afa-113">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="a9afa-114">Este campo define las fechas de registro de acumulación de depreciación a lo largo del año de calendario.</span><span class="sxs-lookup"><span data-stu-id="a9afa-114">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="a9afa-115">Calendario</span><span class="sxs-lookup"><span data-stu-id="a9afa-115">Calendar</span></span>

<span data-ttu-id="a9afa-116">Puede elegir mantener el valor predeterminado en el campo **Año de depreciación**, **Calendario**.</span><span class="sxs-lookup"><span data-stu-id="a9afa-116">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="a9afa-117">La opción **Calendario** actualiza la base de depreciación el 1 de enero de cada año.</span><span class="sxs-lookup"><span data-stu-id="a9afa-117">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="a9afa-118">Normalmente, la base de depreciación es el valor neto en los libros menos el valor residual.</span><span class="sxs-lookup"><span data-stu-id="a9afa-118">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="a9afa-119">En el ejemplo, más adelante en este tema, la base de depreciación es el numerador en la primera expresión en los cálculos de la columna de cálculos.</span><span class="sxs-lookup"><span data-stu-id="a9afa-119">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="a9afa-120">Si selecciona **Calendario** como año de depreciación, aparecen las siguientes opciones disponibles en el campo **Frecuencia de períodos**:</span><span class="sxs-lookup"><span data-stu-id="a9afa-120">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="a9afa-121">**Anual** registra un importe el 31 de diciembre.</span><span class="sxs-lookup"><span data-stu-id="a9afa-121">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="a9afa-122">**Mensual** registra un importe mensual al final de cada mes del calendario.</span><span class="sxs-lookup"><span data-stu-id="a9afa-122">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="a9afa-123">**Trimestral** registra un importe trimestral al final de cada trimestre de calendario (31 de marzo, 30 de junio, 30 de septiembre y 31 de diciembre).</span><span class="sxs-lookup"><span data-stu-id="a9afa-123">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="a9afa-124">**Semestral** registra un importe semestral en la mitad del año del calendario (30 de junio y 31 de diciembre).</span><span class="sxs-lookup"><span data-stu-id="a9afa-124">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="a9afa-125">**Diariamente** registra el importe de depreciación para el método de depreciación diaria utilizando una transacción para cada día.</span><span class="sxs-lookup"><span data-stu-id="a9afa-125">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="a9afa-126">Fiscal</span><span class="sxs-lookup"><span data-stu-id="a9afa-126">Fiscal</span></span>

<span data-ttu-id="a9afa-127">Si selecciona **Fiscal** en el campo **Año de depreciación**, la depreciación decreciente del 150% se calcula en base al ejercicio fiscal del calendario fiscal especificado para el libro o para el calendario fiscal seleccionado en la página **Libro mayor**.</span><span class="sxs-lookup"><span data-stu-id="a9afa-127">If you select **Fiscal** in the **Depreciation year** field, 150% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="a9afa-128">Los calendarios fiscales se configuran en la página **Calendarios fiscales**.</span><span class="sxs-lookup"><span data-stu-id="a9afa-128">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="a9afa-129">Por ejemplo, para el ejercicio del 1 de julio al 30 de junio, el cálculo de la depreciación comienza el 1 de julio.</span><span class="sxs-lookup"><span data-stu-id="a9afa-129">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="a9afa-130">El ejercicio no puede ser superior ni inferior a los 12 meses.</span><span class="sxs-lookup"><span data-stu-id="a9afa-130">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="a9afa-131">La depreciación se ajusta para cada período.</span><span class="sxs-lookup"><span data-stu-id="a9afa-131">The depreciation is adjusted for each period.</span></span> <span data-ttu-id="a9afa-132">La extensión del siguiente ejercicio se determina por los períodos fiscales configurados en la página **Calendarios fiscales**.</span><span class="sxs-lookup"><span data-stu-id="a9afa-132">The length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="a9afa-133">Si selecciona **Fiscal** como año de depreciación, aparecen las siguientes opciones disponibles en el campo **Frecuencia de períodos**:</span><span class="sxs-lookup"><span data-stu-id="a9afa-133">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="a9afa-134">**Anual** registra el importe total de la depreciación calculada para el ejercicio en el último día del ejercicio.</span><span class="sxs-lookup"><span data-stu-id="a9afa-134">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="a9afa-135">**Período fiscal** registra el importe total de depreciación calculado para el ejercicio.</span><span class="sxs-lookup"><span data-stu-id="a9afa-135">**Fiscal period** posts the total amount of the depreciation that is calculated for the fiscal year.</span></span> <span data-ttu-id="a9afa-136">Este importe se acumula en los períodos fiscales definidos en la página **Calendarios fiscales**.</span><span class="sxs-lookup"><span data-stu-id="a9afa-136">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-150-reducing-balance-depreciation"></a><span data-ttu-id="a9afa-137">Ejemplo de depreciación degresiva del 150%</span><span class="sxs-lookup"><span data-stu-id="a9afa-137">Example of 150% reducing balance depreciation</span></span>
|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="a9afa-138">Coste de adquisición</span><span class="sxs-lookup"><span data-stu-id="a9afa-138">Acquisition cost</span></span>               | <span data-ttu-id="a9afa-139">11.000</span><span class="sxs-lookup"><span data-stu-id="a9afa-139">11,000</span></span> |
| <span data-ttu-id="a9afa-140">Valor residual</span><span class="sxs-lookup"><span data-stu-id="a9afa-140">Salvage value</span></span>                  | <span data-ttu-id="a9afa-141">1.000</span><span class="sxs-lookup"><span data-stu-id="a9afa-141">1,000</span></span>  |
| <span data-ttu-id="a9afa-142">Base de depreciación</span><span class="sxs-lookup"><span data-stu-id="a9afa-142">Depreciation base</span></span>              | <span data-ttu-id="a9afa-143">10.000</span><span class="sxs-lookup"><span data-stu-id="a9afa-143">10,000</span></span> |
| <span data-ttu-id="a9afa-144">Años de tiempo de vida</span><span class="sxs-lookup"><span data-stu-id="a9afa-144">Service life years</span></span>             | <span data-ttu-id="a9afa-145">5</span><span class="sxs-lookup"><span data-stu-id="a9afa-145">5</span></span>      |
| <span data-ttu-id="a9afa-146">Porcentaje de depreciación anual</span><span class="sxs-lookup"><span data-stu-id="a9afa-146">Yearly depreciation percentage</span></span> | <span data-ttu-id="a9afa-147">30%</span><span class="sxs-lookup"><span data-stu-id="a9afa-147">30%</span></span>    |

<span data-ttu-id="a9afa-148">El método de depreciación degresiva del 150% divide el 150 por ciento entre los años de tiempo de vida.</span><span class="sxs-lookup"><span data-stu-id="a9afa-148">The 150% reducing balance method divides 150 percent by the service life years.</span></span> <span data-ttu-id="a9afa-149">El porcentaje se multiplicará por el valor neto en los libros del activo para determinar el importe de depreciación durante el año.</span><span class="sxs-lookup"><span data-stu-id="a9afa-149">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="a9afa-150">Periodo</span><span class="sxs-lookup"><span data-stu-id="a9afa-150">Period</span></span> | <span data-ttu-id="a9afa-151">Cálculo del importe de depreciación anual</span><span class="sxs-lookup"><span data-stu-id="a9afa-151">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="a9afa-152">Valor neto</span><span class="sxs-lookup"><span data-stu-id="a9afa-152">Book value</span></span>             | <span data-ttu-id="a9afa-153">Valor neto en los libros al final del año</span><span class="sxs-lookup"><span data-stu-id="a9afa-153">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|------------------------|---------------------------------------|
| <span data-ttu-id="a9afa-154">Año 1</span><span class="sxs-lookup"><span data-stu-id="a9afa-154">Year 1</span></span> | <span data-ttu-id="a9afa-155">(11.000 - 1.000) × 30% = 3.000</span><span class="sxs-lookup"><span data-stu-id="a9afa-155">(11,000 – 1,000) × 30% = 3,000</span></span>                | <span data-ttu-id="a9afa-156">11.000 - 3.000 = 8.000</span><span class="sxs-lookup"><span data-stu-id="a9afa-156">11,000 – 3,000 = 8,000</span></span> | <span data-ttu-id="a9afa-157">11.000 - 1.000 - 3.000 = 7.000</span><span class="sxs-lookup"><span data-stu-id="a9afa-157">11,000 – 1,000 – 3,000 = 7,000</span></span>        |
| <span data-ttu-id="a9afa-158">Año 2</span><span class="sxs-lookup"><span data-stu-id="a9afa-158">Year 2</span></span> | <span data-ttu-id="a9afa-159">7.000 × 30% = 2.100</span><span class="sxs-lookup"><span data-stu-id="a9afa-159">7,000 × 30% = 2,100</span></span>                           | <span data-ttu-id="a9afa-160">8.000 – 2.100 = 5.900</span><span class="sxs-lookup"><span data-stu-id="a9afa-160">8,000 – 2,100 = 5,900</span></span>  | <span data-ttu-id="a9afa-161">7.000 – 2.100 = 4.900</span><span class="sxs-lookup"><span data-stu-id="a9afa-161">7,000 – 2,100 = 4,900</span></span>                 |
| <span data-ttu-id="a9afa-162">Año 3</span><span class="sxs-lookup"><span data-stu-id="a9afa-162">Year 3</span></span> | <span data-ttu-id="a9afa-163">4.900 × 30% = 1.470</span><span class="sxs-lookup"><span data-stu-id="a9afa-163">4,900 × 30% = 1,470</span></span>                           | <span data-ttu-id="a9afa-164">5.900 - 1.470 = 4.430</span><span class="sxs-lookup"><span data-stu-id="a9afa-164">5,900 – 1,470 = 4,430</span></span>  | <span data-ttu-id="a9afa-165">4.900 - 1.470 = 3.430</span><span class="sxs-lookup"><span data-stu-id="a9afa-165">4,900 – 1,470 = 3,430</span></span>                 |

> [!NOTE]
> <span data-ttu-id="a9afa-166">Normalmente, cuando el importe que se calcula mediante el método de depreciación degresiva del 150% resulta inferior al importe que se calcularía con el método de amortización lineal, se realiza una conversión al método de amortización lineal para la vida restante.</span><span class="sxs-lookup"><span data-stu-id="a9afa-166">Typically, when the amount that is calculated by using the 150% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>




