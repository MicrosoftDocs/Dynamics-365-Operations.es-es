---
title: "Reducción de depreciación de saldo"
description: "Este artículo le ofrece una visión general del método de depreciación Depreciación degresiva."
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetDepreciationProfile
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3281
ms.assetid: 1b86763d-d47c-4a6a-a9a6-d97a736750da
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: e36a7e1a5d83a95de53b70b8e3c3b667aae9c6c0
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---

# <a name="reduce-balance-depreciation"></a><span data-ttu-id="cee6e-103">Reducción de depreciación de saldo</span><span class="sxs-lookup"><span data-stu-id="cee6e-103">Reduce balance depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="cee6e-104">Este artículo le ofrece una visión general del método de depreciación Depreciación degresiva.</span><span class="sxs-lookup"><span data-stu-id="cee6e-104">This article gives an overview of the Reducing balance method of depreciation.</span></span>

<span data-ttu-id="cee6e-105">Cuando se configura un método de depreciación de activos fijos y se selecciona Depreciación degresiva en el campo Método de la página Métodos de depreciación, los activos a los que se ha asignado este método de depreciación se deprecian con el mismo porcentaje en cada período de depreciación.</span><span class="sxs-lookup"><span data-stu-id="cee6e-105">When you set up a fixed asset depreciation profile and select Reducing balance in the Method field in the Depreciation profiles page, the assets that have this depreciation profile assigned to them are depreciated by the same percentage in each depreciation period.</span></span>

<span data-ttu-id="cee6e-106">Para configurar la depreciación degresiva, también debe realizar sus selecciones en los campos de la ficha desplegable General y la página Métodos de depreciación.</span><span class="sxs-lookup"><span data-stu-id="cee6e-106">To set up reducing balance depreciation, you must also make selections in fields on the General FastTab of the Depreciation profiles page.</span></span> <span data-ttu-id="cee6e-107">En primer lugar, seleccione un año en el campo Año de depreciación.</span><span class="sxs-lookup"><span data-stu-id="cee6e-107">First, select a year in the Depreciation year field.</span></span> <span data-ttu-id="cee6e-108">En función de la selección, aparecerán distintas opciones en el campo Frecuencia de períodos, tal como se explica en las siguientes secciones.</span><span class="sxs-lookup"><span data-stu-id="cee6e-108">Depending on the selection, different options appear in the Period frequency field, as explained in the following sections.</span></span> 

<span data-ttu-id="cee6e-109">También debe especificar un valor en el campo Porcentaje para el método o perfil de depreciación.</span><span class="sxs-lookup"><span data-stu-id="cee6e-109">You must also enter a value in the Percentage field for the depreciation profile.</span></span> <span data-ttu-id="cee6e-110">Si selecciona la opción Depreciación total, la base de depreciación restante se toma del último período de depreciación y se podría tratar de un importe considerable.</span><span class="sxs-lookup"><span data-stu-id="cee6e-110">If you select the Full depreciation option, the remaining depreciation basis is taken in the last depreciation period and could be a large amount.</span></span> <span data-ttu-id="cee6e-111">Algunos países/regiones no utilizan el cambio a un método de depreciación lineal.</span><span class="sxs-lookup"><span data-stu-id="cee6e-111">Some countries/regions do not use a switchover to a straight line method.</span></span> <span data-ttu-id="cee6e-112">El cambio se realiza cuando el importe del método de depreciación alternativo es mayor o igual que el importe del perfil de depreciación principal y el importe de depreciación utilizado es el del método alternativo.</span><span class="sxs-lookup"><span data-stu-id="cee6e-112">Switchover occurs when the alternative depreciation method amount is greater than or equal to the primary depreciation profile amount, and the depreciation amount taken is the alternative method amount.</span></span> 

<span data-ttu-id="cee6e-113">Puesto que un activo nunca se va a depreciar completamente en base a un cálculo de porcentaje, debe seleccionar la opción Depreciación total para depreciar un activo por completo.</span><span class="sxs-lookup"><span data-stu-id="cee6e-113">Because an asset will never be fully depreciated based on a percentage calculation, you must select the Full depreciation option to fully depreciate an asset.</span></span>

## <a name="select-a-depreciation-year"></a><span data-ttu-id="cee6e-114">Seleccionar un año de depreciación</span><span class="sxs-lookup"><span data-stu-id="cee6e-114">Select a depreciation year</span></span>
<span data-ttu-id="cee6e-115">Puede seleccionar Calendario o Fiscal en el campo Año de depreciación de la página Métodos de depreciación.</span><span class="sxs-lookup"><span data-stu-id="cee6e-115">You can select either Calendar or Fiscal in the Depreciation year field in the Depreciation profiles page.</span></span> <span data-ttu-id="cee6e-116">La selección define las opciones disponibles en el campo Frecuencia de períodos.</span><span class="sxs-lookup"><span data-stu-id="cee6e-116">The selection defines the options that are available in the Period frequency field.</span></span> <span data-ttu-id="cee6e-117">La opción predeterminada es Calendario.</span><span class="sxs-lookup"><span data-stu-id="cee6e-117">The default option is Calendar.</span></span>

### <a name="calendar"></a><span data-ttu-id="cee6e-118">Calendario</span><span class="sxs-lookup"><span data-stu-id="cee6e-118">Calendar</span></span>

<span data-ttu-id="cee6e-119">La opción Calendario actualiza la base de depreciación, que normalmente el valor neto menos el valor residual, el 1 de enero de cada año.</span><span class="sxs-lookup"><span data-stu-id="cee6e-119">The Calendar option updates the depreciation base, which is typically the net book value minus the scrap value, on January 1 of each year.</span></span> <span data-ttu-id="cee6e-120">En el posterior ejemplo de reducción de depreciación del saldo, la base de depreciación es el numerador en la primera expresión en la columna de cálculos.</span><span class="sxs-lookup"><span data-stu-id="cee6e-120">In the reducing balance depreciation example later in this topic, the depreciation base is the numerator in the first expression in the calculations column.</span></span> 

<span data-ttu-id="cee6e-121">Si selecciona Calendario, tiene las siguientes opciones disponibles en el campo Frecuencia de períodos, que define las fechas de registro de acumulación de depreciación a lo largo del año de calendario:</span><span class="sxs-lookup"><span data-stu-id="cee6e-121">If you select Calendar, the following options are available in the Period frequency field, which defines the depreciation accrual posting dates and amounts throughout the calendar year:</span></span>

-   <span data-ttu-id="cee6e-122">Anual registra el 31 de diciembre.</span><span class="sxs-lookup"><span data-stu-id="cee6e-122">Yearly posts on December 31.</span></span>
-   <span data-ttu-id="cee6e-123">Mensual registra un importe mensual al final de cada mes del calendario.</span><span class="sxs-lookup"><span data-stu-id="cee6e-123">Monthly posts a monthly amount at the end of each calendar month.</span></span>
-   <span data-ttu-id="cee6e-124">Trimestral registra un importe trimestral al final de cada trimestre de calendario (31 de marzo, 30 de junio, 30 de septiembre y 31 de diciembre).</span><span class="sxs-lookup"><span data-stu-id="cee6e-124">Quarterly posts a quarterly amount at the end of each calendar quarter (March 31, June 30, September 30, and December 31).</span></span>
-   <span data-ttu-id="cee6e-125">Semestral registra un importe semestral en la mitad del año del calendario (30 de junio y 31 de diciembre).</span><span class="sxs-lookup"><span data-stu-id="cee6e-125">Half-Yearly posts a half-yearly amount at the end of each calendar half-year (June 30 and December 31).</span></span>
-   <span data-ttu-id="cee6e-126">Diariamente registra el importe de depreciación para el método de depreciación diaria utilizando una transacción para cada día.</span><span class="sxs-lookup"><span data-stu-id="cee6e-126">Daily posts the depreciation amount for the daily depreciation method using one transaction for each day.</span></span>

<span data-ttu-id="cee6e-127">Por ejemplo, si selecciona Anual, la depreciación anual se registra una sola vez al año, el 31 de diciembre de cada año.</span><span class="sxs-lookup"><span data-stu-id="cee6e-127">For example, if you select Yearly, the yearly depreciation is posted only one time, on December 31 of each year.</span></span> <span data-ttu-id="cee6e-128">Si selecciona Mensual, la depreciación se registra mensualmente como una doceava parte del importe de depreciación anual.</span><span class="sxs-lookup"><span data-stu-id="cee6e-128">If you select Monthly, the monthly depreciation is posted each month as 1/12 of the yearly depreciation amount.</span></span>

### <a name="fiscal"></a><span data-ttu-id="cee6e-129">Fiscal</span><span class="sxs-lookup"><span data-stu-id="cee6e-129">Fiscal</span></span>

<span data-ttu-id="cee6e-130">Si selecciona Fiscal en el campo Año de depreciación, se utiliza el método de depreciación lineal.</span><span class="sxs-lookup"><span data-stu-id="cee6e-130">If you select Fiscal in the Depreciation year field, the straight line depreciation method is used.</span></span> <span data-ttu-id="cee6e-131">Se calcula en base al ejercicio, que se configura en la página Calendarios fiscales para el calendario fiscal seleccionado en la página libro mayor.</span><span class="sxs-lookup"><span data-stu-id="cee6e-131">It is calculated based on the fiscal year, which is set up in the Fiscal calendars page for the fiscal calendar that is selected in the Ledger page.</span></span> <span data-ttu-id="cee6e-132">Por ejemplo, para el ejercicio del 1 de julio al 30 de junio, el cálculo de la depreciación comienza el 1 de julio.</span><span class="sxs-lookup"><span data-stu-id="cee6e-132">For example, for fiscal year July 1 through June 30, the depreciation calculation starts on July 1.</span></span> <span data-ttu-id="cee6e-133">El ejercicio no puede ser superior ni inferior a los 12 meses.</span><span class="sxs-lookup"><span data-stu-id="cee6e-133">The fiscal year can be longer or shorter than 12 months.</span></span> <span data-ttu-id="cee6e-134">La depreciación se ajusta para cada período fiscal.</span><span class="sxs-lookup"><span data-stu-id="cee6e-134">The depreciation is adjusted for each fiscal period.</span></span> <span data-ttu-id="cee6e-135">La duración del siguiente ejercicio se basa en los períodos fiscales que configura al crear un nuevo ejercicio en la página Calendarios fiscales.</span><span class="sxs-lookup"><span data-stu-id="cee6e-135">The length of the next fiscal year is based on the fiscal periods that you set up when you create a new fiscal year in the Fiscal calendars page.</span></span>


<span data-ttu-id="cee6e-136">Si selecciona Fiscal, aparecen las siguientes opciones disponibles en el campo Frecuencia de períodos:</span><span class="sxs-lookup"><span data-stu-id="cee6e-136">If you select Fiscal, the following options are available in the Period frequency field:</span></span>

-   <span data-ttu-id="cee6e-137">Anual registra el importe total de la depreciación calculada para el ejercicio como un importe de la última fecha del ejercicio.</span><span class="sxs-lookup"><span data-stu-id="cee6e-137">Yearly posts the total amount of the depreciation calculated for the fiscal year as one amount on the last day of the fiscal year.</span></span>
-   <span data-ttu-id="cee6e-138">El periodo fiscal registra el importe total de la depreciación calculada para el ejercicio, que se acumula en los períodos fiscales definidos para el calendario fiscal seleccionado en la página del Libro mayor o el calendario fiscal seleccionado para el libro de un activo fijo.</span><span class="sxs-lookup"><span data-stu-id="cee6e-138">Fiscal period posts the total amount of the depreciation calculated for the fiscal year, which is accrued into the fiscal periods that are defined for the fiscal calendar that is selected in the Ledger page, or for the fiscal calendar that is selected for the book for a fixed asset.</span></span>

## <a name="example-of-reducing-balance-depreciation"></a><span data-ttu-id="cee6e-139">Ejemplo de depreciación degresiva</span><span class="sxs-lookup"><span data-stu-id="cee6e-139">Example of reducing balance depreciation</span></span>

<span data-ttu-id="cee6e-140">Suponga que el precio de adquisición de activos fijos es de 11.000, el valor residual de 1.000 y el factor del porcentaje de depreciación es 30.</span><span class="sxs-lookup"><span data-stu-id="cee6e-140">Suppose that the fixed asset acquisition price is 11,000, the scrap value is 1,000, and the depreciation percentage factor is 30.</span></span> 

<span data-ttu-id="cee6e-141">A través del método de Saldo decreciente, el 30 por ciento de la base de depreciación (valor neto del libro menos el valor residual) se calcula al final del período de depreciación anterior.</span><span class="sxs-lookup"><span data-stu-id="cee6e-141">Using the Reducing balance method, 30 percent of the depreciation base (net book value minus scrap value) is calculated at the end of the previous depreciation period.</span></span> <span data-ttu-id="cee6e-142">En la siguiente tabla se muestra la depreciación para los tres primeros años.</span><span class="sxs-lookup"><span data-stu-id="cee6e-142">Depreciation for the first three years is shown in the following table.</span></span>

| <span data-ttu-id="cee6e-143">Período</span><span class="sxs-lookup"><span data-stu-id="cee6e-143">Period</span></span> | <span data-ttu-id="cee6e-144">Cálculo del importe de depreciación anual</span><span class="sxs-lookup"><span data-stu-id="cee6e-144">Calculation of yearly depreciation amount</span></span> | <span data-ttu-id="cee6e-145">Valor neto en los libros al final del año</span><span class="sxs-lookup"><span data-stu-id="cee6e-145">Net book value at the end of the year</span></span> |
|--------|-------------------------------------------|---------------------------------------|
| <span data-ttu-id="cee6e-146">Año 1</span><span class="sxs-lookup"><span data-stu-id="cee6e-146">Year 1</span></span> | <span data-ttu-id="cee6e-147">(11.000 - 1.000) \* 30% = 3.000</span><span class="sxs-lookup"><span data-stu-id="cee6e-147">(11,000 - 1,000) \* 30% = 3,000</span></span>           | <span data-ttu-id="cee6e-148">(11.000 - 1.000) - 3.000 = 7.000</span><span class="sxs-lookup"><span data-stu-id="cee6e-148">(11,000 - 1,000) - 3,000 = 7,000</span></span>      |
| <span data-ttu-id="cee6e-149">Año 2</span><span class="sxs-lookup"><span data-stu-id="cee6e-149">Year 2</span></span> | <span data-ttu-id="cee6e-150">(7.000 - 1.000) \* 30% = 1.800</span><span class="sxs-lookup"><span data-stu-id="cee6e-150">(7,000 - 1,000) \* 30% = 1,800</span></span>            | <span data-ttu-id="cee6e-151">(7.000 -1.800) = 5.200</span><span class="sxs-lookup"><span data-stu-id="cee6e-151">(7,000 -1,800) = 5,200</span></span>                |
| <span data-ttu-id="cee6e-152">Año 3</span><span class="sxs-lookup"><span data-stu-id="cee6e-152">Year 3</span></span> | <span data-ttu-id="cee6e-153">(5.200 - 1.000) \* 30% = 1.260</span><span class="sxs-lookup"><span data-stu-id="cee6e-153">(5,200 - 1,000) \* 30% = 1,260</span></span>            | <span data-ttu-id="cee6e-154">(5.200 - 1.260) = 3.940</span><span class="sxs-lookup"><span data-stu-id="cee6e-154">(5,200 - 1,260) = 3,940</span></span>               |


-






