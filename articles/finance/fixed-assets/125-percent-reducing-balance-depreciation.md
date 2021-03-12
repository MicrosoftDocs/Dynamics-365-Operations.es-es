---
title: Depreciación con amortización degresiva del 125%
description: Este artículo le ofrece una visión general del método de depreciación Depreciación con amortización degresiva del 125%.
author: saraschi2
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: roschlom
ms.custom: 13871
ms.assetid: 3abc263e-59d6-4f1a-986d-1be388948bd3
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9511917d72a1bb45daf2ce7e4b56d94c17825daf
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4969237"
---
# <a name="125-percent-reducing-balance-depreciation"></a><span data-ttu-id="82eec-103">Depreciación con amortización degresiva del 125%</span><span class="sxs-lookup"><span data-stu-id="82eec-103">125 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="82eec-104">Este artículo le ofrece una visión general del método de depreciación Depreciación con amortización degresiva del 125%.</span><span class="sxs-lookup"><span data-stu-id="82eec-104">This article gives an overview of the 125 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="82eec-105">Al configurar un método de depreciación de activos fijos y seleccionar el valor **Depreciación degresiva del 125%** en el campo **Método** de la página **Métodos de depreciación**, los activos fijos que se asignan al método de depreciación se deprecian por el mismo porcentaje en cada período de depreciación.</span><span class="sxs-lookup"><span data-stu-id="82eec-105">When you set up a fixed asset depreciation profile and select **125% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned to the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> <span data-ttu-id="82eec-106">Este porcentaje se calcula en función del tiempo de vida del activo.</span><span class="sxs-lookup"><span data-stu-id="82eec-106">This percentage is calculated based on the service life of the asset.</span></span> <span data-ttu-id="82eec-107">Por ejemplo, si un activo tiene un tiempo de vida de cinco años, el porcentaje se calcula como 25 por ciento (125% ÷ 5).</span><span class="sxs-lookup"><span data-stu-id="82eec-107">For example, if an asset has a service life of five years, the percentage is calculated as 25 percent (125% ÷ 5).</span></span>

<span data-ttu-id="82eec-108">Para configurar una depreciación con amortización degresiva del 125%, también debe seleccionar opciones en los campos **Año de depreciación** y **Frecuencia de períodos** en la página **Métodos de depreciación**.</span><span class="sxs-lookup"><span data-stu-id="82eec-108">To set up 125% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="82eec-109">Las opciones disponibles en el campo **Frecuencia de períodos** varían en función del valor seleccionado en el campo **Año de depreciación**.</span><span class="sxs-lookup"><span data-stu-id="82eec-109">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="82eec-110">Selección de un año de depreciación</span><span class="sxs-lookup"><span data-stu-id="82eec-110">Select a depreciation year</span></span>
<span data-ttu-id="82eec-111">Puede seleccionar **Calendario** o **Fiscal** en el campo **Año de depreciación** de la página **Métodos de depreciación**.</span><span class="sxs-lookup"><span data-stu-id="82eec-111">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="82eec-112">El valor predeterminado es **Calendario**.</span><span class="sxs-lookup"><span data-stu-id="82eec-112">The default value is **Calendar**.</span></span> 

<span data-ttu-id="82eec-113">La selección determina las opciones disponibles en el campo **Frecuencia de períodos**.</span><span class="sxs-lookup"><span data-stu-id="82eec-113">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="82eec-114">Este campo define las fechas de registro de acumulación de depreciación a lo largo del año de calendario.</span><span class="sxs-lookup"><span data-stu-id="82eec-114">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="82eec-115">Calendario</span><span class="sxs-lookup"><span data-stu-id="82eec-115">Calendar</span></span>

<span data-ttu-id="82eec-116">Puede elegir mantener el valor predeterminado en el campo **Año de depreciación**, **Calendario**.</span><span class="sxs-lookup"><span data-stu-id="82eec-116">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="82eec-117">La opción **Calendario** actualiza la base de depreciación el 1 de enero de cada año.</span><span class="sxs-lookup"><span data-stu-id="82eec-117">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="82eec-118">Normalmente, la base de depreciación es el valor neto en los libros menos el valor residual.</span><span class="sxs-lookup"><span data-stu-id="82eec-118">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="82eec-119">En el ejemplo, más adelante en este tema, la base de depreciación es el numerador en la primera expresión en los cálculos de la columna de cálculos.</span><span class="sxs-lookup"><span data-stu-id="82eec-119">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="82eec-120">Si selecciona **Calendario** como año de depreciación, aparecen las siguientes opciones disponibles en el campo **Frecuencia de períodos**:</span><span class="sxs-lookup"><span data-stu-id="82eec-120">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="82eec-121">**Anual** registra un importe el 31 de diciembre.</span><span class="sxs-lookup"><span data-stu-id="82eec-121">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="82eec-122">**Mensual** registra un importe mensual al final de cada mes del calendario.</span><span class="sxs-lookup"><span data-stu-id="82eec-122">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="82eec-123">**Trimestral** registra un importe trimestral al final de cada trimestre de calendario (31 de marzo, 30 de junio, 30 de septiembre y 31 de diciembre).</span><span class="sxs-lookup"><span data-stu-id="82eec-123">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="82eec-124">**Semestral** registra un importe semestral en la mitad del año del calendario (30 de junio y 31 de diciembre).</span><span class="sxs-lookup"><span data-stu-id="82eec-124">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="82eec-125">**Diariamente** registra el importe de depreciación para el método de depreciación diaria utilizando una transacción para cada día.</span><span class="sxs-lookup"><span data-stu-id="82eec-125">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="82eec-126">Fiscal</span><span class="sxs-lookup"><span data-stu-id="82eec-126">Fiscal</span></span>

<span data-ttu-id="82eec-127">Si selecciona **Fiscal** en el campo **Año de depreciación**, la depreciación degresiva del 125% se calcula en base al ejercicio fiscal del calendario fiscal especificado para el libro o para el calendario fiscal seleccionado en la página **Libro mayor**.</span><span class="sxs-lookup"><span data-stu-id="82eec-127">If you select **Fiscal** in the **Depreciation year** field, 125% reducing depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="82eec-128">Los calendarios fiscales se configuran en la página **Calendarios fiscales**.</span><span class="sxs-lookup"><span data-stu-id="82eec-128">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="82eec-129">Por ejemplo, para el ejercicio del 1 de julio al 30 de junio, el cálculo de la depreciación comienza el 1 de julio.</span><span class="sxs-lookup"><span data-stu-id="82eec-129">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="82eec-130">El ejercicio no puede ser superior ni inferior a los 12 meses.</span><span class="sxs-lookup"><span data-stu-id="82eec-130">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="82eec-131">La depreciación se ajusta automáticamente para cada período y la extensión del siguiente ejercicio se determina mediante la configuración de los períodos de la página **Calendarios fiscales**.</span><span class="sxs-lookup"><span data-stu-id="82eec-131">The depreciation is automatically adjusted for each period, and the length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="82eec-132">Si selecciona **Fiscal** como año de depreciación, aparecen las siguientes opciones disponibles en el campo **Frecuencia de períodos**:</span><span class="sxs-lookup"><span data-stu-id="82eec-132">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="82eec-133">**Anual** registra el importe total de la depreciación calculada para el ejercicio como un importe de la última fecha del ejercicio.</span><span class="sxs-lookup"><span data-stu-id="82eec-133">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year as one amount, on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="82eec-134">**Período fiscal** registra el importe total de depreciación calculado para el ejercicio.</span><span class="sxs-lookup"><span data-stu-id="82eec-134">**Fiscal period** posts the total amount of the depreciation that is calculated for the fiscal year.</span></span> <span data-ttu-id="82eec-135">Este importe se acumula en los períodos fiscales definidos en la página **Calendarios fiscales**.</span><span class="sxs-lookup"><span data-stu-id="82eec-135">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-125-reducing-balance-depreciation"></a><span data-ttu-id="82eec-136">Ejemplo de la depreciación degresiva del 125%</span><span class="sxs-lookup"><span data-stu-id="82eec-136">Example of 125% reducing balance depreciation</span></span>

|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="82eec-137">Coste de adquisición</span><span class="sxs-lookup"><span data-stu-id="82eec-137">Acquisition cost</span></span>               | <span data-ttu-id="82eec-138">11.000</span><span class="sxs-lookup"><span data-stu-id="82eec-138">11,000</span></span> |
| <span data-ttu-id="82eec-139">Valor residual</span><span class="sxs-lookup"><span data-stu-id="82eec-139">Salvage value</span></span>                  | <span data-ttu-id="82eec-140">1.000</span><span class="sxs-lookup"><span data-stu-id="82eec-140">1,000</span></span>  |
| <span data-ttu-id="82eec-141">Base de depreciación</span><span class="sxs-lookup"><span data-stu-id="82eec-141">Depreciation base</span></span>              | <span data-ttu-id="82eec-142">10.000</span><span class="sxs-lookup"><span data-stu-id="82eec-142">10,000</span></span> |
| <span data-ttu-id="82eec-143">Años de tiempo de vida</span><span class="sxs-lookup"><span data-stu-id="82eec-143">Service life years</span></span>             | <span data-ttu-id="82eec-144">5</span><span class="sxs-lookup"><span data-stu-id="82eec-144">5</span></span>      |
| <span data-ttu-id="82eec-145">Porcentaje de depreciación anual</span><span class="sxs-lookup"><span data-stu-id="82eec-145">Yearly depreciation percentage</span></span> | <span data-ttu-id="82eec-146">25%</span><span class="sxs-lookup"><span data-stu-id="82eec-146">25%</span></span>    |

<span data-ttu-id="82eec-147">El método de depreciación degresiva del 125 % divide el 125 por ciento entre los años de tiempo de vida.</span><span class="sxs-lookup"><span data-stu-id="82eec-147">The 125% reducing balance method divides 125 percent by the service life years.</span></span> <span data-ttu-id="82eec-148">El porcentaje se multiplicará por el valor neto en los libros del activo para determinar el importe de depreciación durante el año.</span><span class="sxs-lookup"><span data-stu-id="82eec-148">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="82eec-149">Periodo</span><span class="sxs-lookup"><span data-stu-id="82eec-149">Period</span></span> | <span data-ttu-id="82eec-150">Cálculo del importe de depreciación anual</span><span class="sxs-lookup"><span data-stu-id="82eec-150">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="82eec-151">Valor neto</span><span class="sxs-lookup"><span data-stu-id="82eec-151">Book value</span></span>                    | <span data-ttu-id="82eec-152">Valor neto en los libros al final del año</span><span class="sxs-lookup"><span data-stu-id="82eec-152">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|-------------------------------|---------------------------------------|
| <span data-ttu-id="82eec-153">Año 1</span><span class="sxs-lookup"><span data-stu-id="82eec-153">Year 1</span></span> | <span data-ttu-id="82eec-154">(11.000 - 1.000) × 25% = 2.500</span><span class="sxs-lookup"><span data-stu-id="82eec-154">(11,000 – 1,000) × 25% = 2,500</span></span>                | <span data-ttu-id="82eec-155">(11.000 - 2.500) = 8.500</span><span class="sxs-lookup"><span data-stu-id="82eec-155">(11,000 – 2,500) = 8,500</span></span>      | <span data-ttu-id="82eec-156">(11.000 - 1.000 - 2.500) = 7.500</span><span class="sxs-lookup"><span data-stu-id="82eec-156">(11,000 – 1,000 – 2,500) = 7,500</span></span>      |
| <span data-ttu-id="82eec-157">Año 2</span><span class="sxs-lookup"><span data-stu-id="82eec-157">Year 2</span></span> | <span data-ttu-id="82eec-158">7.500 × 25% = 1.875</span><span class="sxs-lookup"><span data-stu-id="82eec-158">7,500 × 25% = 1,875</span></span>                           | <span data-ttu-id="82eec-159">(8.500 - 1.875) = 6.625</span><span class="sxs-lookup"><span data-stu-id="82eec-159">(8,500 – 1,875) = 6,625</span></span>       | <span data-ttu-id="82eec-160">(7.500 - 1.875) = 5.625</span><span class="sxs-lookup"><span data-stu-id="82eec-160">(7,500 – 1,875) = 5,625</span></span>               |
| <span data-ttu-id="82eec-161">Año 3</span><span class="sxs-lookup"><span data-stu-id="82eec-161">Year 3</span></span> | <span data-ttu-id="82eec-162">5.625 × 25% = 1.406,25</span><span class="sxs-lookup"><span data-stu-id="82eec-162">5,625 × 25% = 1,406.25</span></span>                        | <span data-ttu-id="82eec-163">(6.625 - 1.406,25) = 5.218,75</span><span class="sxs-lookup"><span data-stu-id="82eec-163">(6,625 – 1,406.25) = 5,218.75</span></span> | <span data-ttu-id="82eec-164">(5.625 - 1.406,25) = 4.218,75</span><span class="sxs-lookup"><span data-stu-id="82eec-164">(5,625 – 1,406.25) = 4,218.75</span></span>         |

> [!NOTE] 
> <span data-ttu-id="82eec-165">Normalmente, cuando el importe que se calcula mediante el método de depreciación degresiva del 125% resulta inferior al importe que se calcularía con el método de amortización lineal, se realiza una conversión al método de amortización lineal para la vida restante.</span><span class="sxs-lookup"><span data-stu-id="82eec-165">Typically, when the amount that is calculated by using the 125% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>



