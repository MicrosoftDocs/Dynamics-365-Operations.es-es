---
title: "Depreciación con amortización degresiva del 175%"
description: "Este tema le ofrece una visión general del método de depreciación Depreciación con amortización degresiva del 175%."
author: saraschi2
manager: AnnBe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13911
ms.assetid: cc5d001f-bcfe-4602-9ec1-9e265e9fd188
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 8f78eb06930eab26d300fba6fd28333a5ce39cf8
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="175-percent-reducing-balance-depreciation"></a><span data-ttu-id="50742-103">Depreciación con amortización degresiva del 175%</span><span class="sxs-lookup"><span data-stu-id="50742-103">175 percent reducing balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="50742-104">Este tema le ofrece una visión general del método de depreciación Depreciación con amortización degresiva del 175%.</span><span class="sxs-lookup"><span data-stu-id="50742-104">This topic gives an overview of the 175 percent reducing balance method of depreciation.</span></span>

<span data-ttu-id="50742-105">Al configurar un método de depreciación de activos fijos y seleccionar el valor **Depreciación degresiva del 175%** en el campo **Método** de la página **Métodos de depreciación**, los activos fijos que se asignan al método de depreciación se deprecian por el mismo porcentaje en cada período de depreciación.</span><span class="sxs-lookup"><span data-stu-id="50742-105">When you set up a fixed asset depreciation profile and select **175% reducing balance** in the **Method** field on the **Depreciation profiles** page, fixed assets that are assigned the depreciation profile are depreciated by the same percentage in each depreciation period.</span></span> 

<span data-ttu-id="50742-106">Para configurar una depreciación con amortización degresiva del 175%, también debe seleccionar opciones en los campos **Año de depreciación** y **Frecuencia de períodos** en la página **Métodos de depreciación**.</span><span class="sxs-lookup"><span data-stu-id="50742-106">To set up 175% reducing balance depreciation, you must also select options in the **Depreciation year** field and the **Period frequency** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="50742-107">Las opciones disponibles en el campo **Frecuencia de períodos** varían en función del valor seleccionado en el campo **Año de depreciación**.</span><span class="sxs-lookup"><span data-stu-id="50742-107">The options that are available in the **Period frequency** field vary, depending on the value that is selected in the **Depreciation year** field.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="50742-108">Selección de un año de depreciación</span><span class="sxs-lookup"><span data-stu-id="50742-108">Select a depreciation year</span></span>
<span data-ttu-id="50742-109">Puede seleccionar **Calendario** o **Fiscal** en el campo **Año de depreciación** de la página **Métodos de depreciación**.</span><span class="sxs-lookup"><span data-stu-id="50742-109">You can select either **Calendar** or **Fiscal** in the **Depreciation year** field on the **Depreciation profiles** page.</span></span> <span data-ttu-id="50742-110">El valor predeterminado es **Calendario**.</span><span class="sxs-lookup"><span data-stu-id="50742-110">The default value is **Calendar**.</span></span> 

<span data-ttu-id="50742-111">La selección determina las opciones disponibles en el campo **Frecuencia de períodos**.</span><span class="sxs-lookup"><span data-stu-id="50742-111">Your selection determines the options that are available in the **Period frequency** field.</span></span> <span data-ttu-id="50742-112">Este campo define las fechas de registro de acumulación de depreciación a lo largo del año de calendario.</span><span class="sxs-lookup"><span data-stu-id="50742-112">This field defines the depreciation accrual posting dates and amounts throughout the calendar year.</span></span>

### <a name="calendar"></a><span data-ttu-id="50742-113">Calendario</span><span class="sxs-lookup"><span data-stu-id="50742-113">Calendar</span></span>

<span data-ttu-id="50742-114">Puede elegir mantener el valor predeterminado en el campo **Año de depreciación**, **Calendario**.</span><span class="sxs-lookup"><span data-stu-id="50742-114">You can keep the default value in the **Depreciation year** field, **Calendar**.</span></span> 

<span data-ttu-id="50742-115">La opción **Calendario** actualiza la base de depreciación el 1 de enero de cada año.</span><span class="sxs-lookup"><span data-stu-id="50742-115">The **Calendar** option updates the depreciation base on January 1 of each year.</span></span> <span data-ttu-id="50742-116">Normalmente, la base de depreciación es el valor neto en los libros menos el valor residual.</span><span class="sxs-lookup"><span data-stu-id="50742-116">Typically, the depreciation base is the net book value minus the scrap value.</span></span> <span data-ttu-id="50742-117">En el ejemplo, más adelante en este tema, la base de depreciación es el numerador en la primera expresión en los cálculos de la columna de cálculos.</span><span class="sxs-lookup"><span data-stu-id="50742-117">In the examples later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="50742-118">Si selecciona **Calendario** como año de depreciación, aparecen las siguientes opciones disponibles en el campo **Frecuencia de períodos**:</span><span class="sxs-lookup"><span data-stu-id="50742-118">If you select **Calendar** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="50742-119">**Anual** registra un importe el 31 de diciembre.</span><span class="sxs-lookup"><span data-stu-id="50742-119">**Yearly** posts an amount on December 31.</span></span>
-   <span data-ttu-id="50742-120">**Mensual** registra un importe mensual al final de cada mes del calendario.</span><span class="sxs-lookup"><span data-stu-id="50742-120">**Monthly** posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="50742-121">**Trimestral** registra un importe trimestral al final de cada trimestre de calendario (31 de marzo, 30 de junio, 30 de septiembre y 31 de diciembre).</span><span class="sxs-lookup"><span data-stu-id="50742-121">**Quarterly** posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="50742-122">**Semestral** registra un importe semestral en la mitad del año del calendario (30 de junio y 31 de diciembre).</span><span class="sxs-lookup"><span data-stu-id="50742-122">**Half-Yearly** posts a half-yearly amount at the calendar half year (June 30 and December 31).</span></span>
-   <span data-ttu-id="50742-123">**Diariamente** registra el importe de depreciación para el método de depreciación diaria utilizando una transacción para cada día.</span><span class="sxs-lookup"><span data-stu-id="50742-123">**Daily** posts the depreciation amount for the daily depreciation method by using one transaction for each day.</span></span>

### <a name="fiscal"></a><span data-ttu-id="50742-124">Fiscal</span><span class="sxs-lookup"><span data-stu-id="50742-124">Fiscal</span></span>

<span data-ttu-id="50742-125">Si selecciona **Fiscal** en el campo **Año de depreciación**, la depreciación decreciente del 175% se calcula en base al ejercicio fiscal del calendario fiscal especificado para el libro o para el calendario fiscal seleccionado en la página **Libro mayor**.</span><span class="sxs-lookup"><span data-stu-id="50742-125">If you select **Fiscal** in the **Depreciation year** field, 175% reducing balance depreciation is calculated based on the fiscal year for the fiscal calendar that is specified for the book, or for the fiscal calendar that is selected on the **Ledger** page.</span></span> <span data-ttu-id="50742-126">Los calendarios fiscales se configuran en la página **Calendarios fiscales**.</span><span class="sxs-lookup"><span data-stu-id="50742-126">Fiscal calendars are set up on the **Fiscal calendars** page.</span></span> <span data-ttu-id="50742-127">Para obtener más información, consulte [Calendarios fiscales, ejercicios y períodos.](../budgeting/fiscal-calendars-fiscal-years-periods.md).</span><span class="sxs-lookup"><span data-stu-id="50742-127">For more information, see [Fiscal calendars, fiscal years, and periods](../budgeting/fiscal-calendars-fiscal-years-periods.md).</span></span>

<span data-ttu-id="50742-128">Por ejemplo, para el ejercicio del 1 de julio al 30 de junio, el cálculo de la depreciación comienza el 1 de julio.</span><span class="sxs-lookup"><span data-stu-id="50742-128">For example, for the fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="50742-129">El ejercicio no puede ser superior ni inferior a los 12 meses.</span><span class="sxs-lookup"><span data-stu-id="50742-129">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="50742-130">La depreciación se ajusta automáticamente para cada período y la extensión del siguiente ejercicio se determina mediante la configuración de los períodos de la página **Calendarios fiscales**.</span><span class="sxs-lookup"><span data-stu-id="50742-130">The depreciation is automatically adjusted for each period, and the length of the next fiscal year is determined by the setup of periods on the **Fiscal calendars** page.</span></span> 

<span data-ttu-id="50742-131">Si selecciona **Fiscal** como año de depreciación, aparecen las siguientes opciones disponibles en el campo **Frecuencia de períodos**:</span><span class="sxs-lookup"><span data-stu-id="50742-131">If you select **Fiscal** as the depreciation year, the following options are available in the **Period frequency** field:</span></span>

-   <span data-ttu-id="50742-132">**Anual** registra el importe total de la depreciación calculada para el ejercicio en el último día del ejercicio.</span><span class="sxs-lookup"><span data-stu-id="50742-132">**Yearly** posts the total amount of the depreciation that is calculated for the fiscal year on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="50742-133">**Período fiscal** calcula el importe total de depreciación para el ejercicio.</span><span class="sxs-lookup"><span data-stu-id="50742-133">**Fiscal period** calculates the total amount of the depreciation for the fiscal year.</span></span> <span data-ttu-id="50742-134">Este importe se acumula en los períodos fiscales definidos en la página **Calendarios fiscales**.</span><span class="sxs-lookup"><span data-stu-id="50742-134">This amount is accrued into the fiscal periods that are defined on the **Fiscal calendars** page.</span></span>

## <a name="example-of-175-reducing-balance-depreciation"></a><span data-ttu-id="50742-135">Ejemplo de depreciación con amortización degresiva del 175%</span><span class="sxs-lookup"><span data-stu-id="50742-135">Example of 175% reducing balance depreciation</span></span>

|                                |        |
|--------------------------------|--------|
| <span data-ttu-id="50742-136">Coste de adquisición</span><span class="sxs-lookup"><span data-stu-id="50742-136">Acquisition cost</span></span>               | <span data-ttu-id="50742-137">11.000</span><span class="sxs-lookup"><span data-stu-id="50742-137">11,000</span></span> |
| <span data-ttu-id="50742-138">Valor residual</span><span class="sxs-lookup"><span data-stu-id="50742-138">Salvage value</span></span>                  | <span data-ttu-id="50742-139">1.000</span><span class="sxs-lookup"><span data-stu-id="50742-139">1,000</span></span>  |
| <span data-ttu-id="50742-140">Base de depreciación</span><span class="sxs-lookup"><span data-stu-id="50742-140">Depreciation base</span></span>              | <span data-ttu-id="50742-141">10.000</span><span class="sxs-lookup"><span data-stu-id="50742-141">10,000</span></span> |
| <span data-ttu-id="50742-142">Años de tiempo de vida</span><span class="sxs-lookup"><span data-stu-id="50742-142">Service life years</span></span>             | <span data-ttu-id="50742-143">5</span><span class="sxs-lookup"><span data-stu-id="50742-143">5</span></span>      |
| <span data-ttu-id="50742-144">Porcentaje de depreciación anual</span><span class="sxs-lookup"><span data-stu-id="50742-144">Yearly depreciation percentage</span></span> | <span data-ttu-id="50742-145">35%</span><span class="sxs-lookup"><span data-stu-id="50742-145">35%</span></span>    |

<span data-ttu-id="50742-146">El método de depreciación degresiva del 175% divide el 175 por ciento entre los años de tiempo de vida.</span><span class="sxs-lookup"><span data-stu-id="50742-146">The 175% reducing balance depreciation method divides 175 percent by the service life years.</span></span> <span data-ttu-id="50742-147">El porcentaje se multiplicará por el valor neto en los libros del activo para determinar el importe de depreciación durante el año.</span><span class="sxs-lookup"><span data-stu-id="50742-147">That percentage will be multiplied by the net book value of the asset to determine the depreciation amount for the year.</span></span>

| <span data-ttu-id="50742-148">Periodo</span><span class="sxs-lookup"><span data-stu-id="50742-148">Period</span></span> | <span data-ttu-id="50742-149">Cálculo del importe de depreciación anual</span><span class="sxs-lookup"><span data-stu-id="50742-149">Calculation of the yearly depreciation amount</span></span> | <span data-ttu-id="50742-150">Valor neto</span><span class="sxs-lookup"><span data-stu-id="50742-150">Book value</span></span>                  | <span data-ttu-id="50742-151">Valor neto en los libros al final del año</span><span class="sxs-lookup"><span data-stu-id="50742-151">Net book value at the end of the year</span></span> |
|--------|-----------------------------------------------|-----------------------------|---------------------------------------|
| <span data-ttu-id="50742-152">Año 1</span><span class="sxs-lookup"><span data-stu-id="50742-152">Year 1</span></span> | <span data-ttu-id="50742-153">(11.000 - 1.000) × 35% = 3.500</span><span class="sxs-lookup"><span data-stu-id="50742-153">(11,000 – 1,000) × 35% = 3,500</span></span>                | <span data-ttu-id="50742-154">11.000 - 3.500 = 7.500</span><span class="sxs-lookup"><span data-stu-id="50742-154">11,000 – 3,500 = 7,500</span></span>      | <span data-ttu-id="50742-155">11.000 - 1.000 - 3.500 = 6.500</span><span class="sxs-lookup"><span data-stu-id="50742-155">11,000 – 1,000 – 3,500 = 6,500</span></span>        |
| <span data-ttu-id="50742-156">Año 2</span><span class="sxs-lookup"><span data-stu-id="50742-156">Year 2</span></span> | <span data-ttu-id="50742-157">6.500 × 35% = 2.275</span><span class="sxs-lookup"><span data-stu-id="50742-157">6,500 × 35% = 2,275</span></span>                           | <span data-ttu-id="50742-158">7.500 - 2.275 = 5.225</span><span class="sxs-lookup"><span data-stu-id="50742-158">7,500 – 2,275 = 5,225</span></span>       | <span data-ttu-id="50742-159">6.500 - 2.275 = 4.225</span><span class="sxs-lookup"><span data-stu-id="50742-159">6,500 – 2,275 = 4,225</span></span>                 |
| <span data-ttu-id="50742-160">Año 3</span><span class="sxs-lookup"><span data-stu-id="50742-160">Year 3</span></span> | <span data-ttu-id="50742-161">4.225 × 35% = 1.478,75</span><span class="sxs-lookup"><span data-stu-id="50742-161">4,225 × 35% = 1,478.75</span></span>                        | <span data-ttu-id="50742-162">5.225 - 1.478,75 = 3.746,25</span><span class="sxs-lookup"><span data-stu-id="50742-162">5,225 – 1,478.75 = 3,746.25</span></span> | <span data-ttu-id="50742-163">4.225 - 1.478,75 = 2.746,25</span><span class="sxs-lookup"><span data-stu-id="50742-163">4,225 – 1,478.75 = 2,746.25</span></span>           |

> [!NOTE] 
> <span data-ttu-id="50742-164">Normalmente, cuando el importe que se calcula mediante el método de depreciación degresiva del 175% resulta inferior al importe que se calcularía con el método de amortización lineal, se realiza una conversión al método de amortización lineal para la vida restante.</span><span class="sxs-lookup"><span data-stu-id="50742-164">Typically, when the amount that is calculated by using the 175% reducing balance depreciation method becomes less than the amount that would be calculated by using the straight line method, there is a conversion to the straight line method for the remaining life.</span></span>




