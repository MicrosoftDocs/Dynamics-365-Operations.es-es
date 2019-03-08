---
title: Convenciones y métodos de depreciación
description: Este artículo proporciona una visión general de las convenciones de depreciación y los métodos de depreciación que son compatibles con Microsoft Dynamics 365 for Finance and Operations.
author: ShylaThompson
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetDepreciationProfile, AssetGroupBookSetup, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3441
ms.assetid: 1d8267b1-86a8-44bf-8814-f56b5d45a0ae
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: be8e05a386178b9172a906109e015269dc72b32e
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "331124"
---
# <a name="depreciation-methods-and-conventions"></a><span data-ttu-id="0ff3e-103">Convenciones y métodos de depreciación</span><span class="sxs-lookup"><span data-stu-id="0ff3e-103">Depreciation methods and conventions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0ff3e-104">Este artículo proporciona una visión general de las convenciones de depreciación y los métodos de depreciación que son compatibles con Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="0ff3e-104">This article provides an overview of the depreciation conventions and depreciation methods that are supported by Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="0ff3e-105">Puede seleccionar varios métodos de depreciación y convenciones de amortizaciones.</span><span class="sxs-lookup"><span data-stu-id="0ff3e-105">You can select various depreciation methods and conventions.</span></span> <span data-ttu-id="0ff3e-106">El objetivo de los métodos es ubicar el valor depreciable del activo fijo en períodos fiscales.</span><span class="sxs-lookup"><span data-stu-id="0ff3e-106">The purpose of the methods is to allocate the depreciable value of the fixed asset into fiscal periods.</span></span> <span data-ttu-id="0ff3e-107">El valor depreciable del activo fijo es el precio de la adquisición reducido por el valor residual, si lo hubiere.</span><span class="sxs-lookup"><span data-stu-id="0ff3e-107">The depreciable value of the fixed asset is the acquisition price, reduced by a scrap value, if any.</span></span> 

<span data-ttu-id="0ff3e-108">Si utiliza convenciones de amortización y modifica la última fecha de ejecución de la depreciación de un activo que se salta algunas depreciaciones, la depreciación del último año puede ser mayor o menor de lo esperado.</span><span class="sxs-lookup"><span data-stu-id="0ff3e-108">If you are using depreciation conventions and you modify the last depreciation run date for an asset, which then causes some depreciations to be skipped, the depreciation for the last year might be more than or less than is expected.</span></span> <span data-ttu-id="0ff3e-109">La depreciación se ajusta con el número de períodos de depreciación afectados por la modificación de la última fecha de ejecución de la depreciación.</span><span class="sxs-lookup"><span data-stu-id="0ff3e-109">The depreciation is adjusted by the number of depreciation periods affected by the modification of the last depreciation run date.</span></span>

<span data-ttu-id="0ff3e-110">Por ejemplo, si utiliza la convención de amortización de medio año durante tres años, la amortización ocurrirá normalmente a lo largo de 3 1/2 años.</span><span class="sxs-lookup"><span data-stu-id="0ff3e-110">For example, if you are using the Half year depreciation convention over three years, depreciation ordinarily occurs over 3 1/2 years.</span></span> <span data-ttu-id="0ff3e-111">Si cambia la última fecha de ejecución de la depreciación durante los 3 1/2 años, el último año de depreciación cambiará el número de períodos afectados.</span><span class="sxs-lookup"><span data-stu-id="0ff3e-111">If you change the last depreciation run date during the 3 1/2 years, the last year of depreciation moves out the number of periods affected.</span></span> <span data-ttu-id="0ff3e-112">Si cambia la fecha en tres meses, el último año tendrá un valor de depreciación de nueve meses, cuando normalmente serían seis meses.</span><span class="sxs-lookup"><span data-stu-id="0ff3e-112">If you move the date by three months, the last year will have nine months’ worth of depreciation, when ordinarily there would be six months’ worth of depreciation.</span></span>

<span data-ttu-id="0ff3e-113">Puede seleccionar entre las siguientes convenciones de amortización.</span><span class="sxs-lookup"><span data-stu-id="0ff3e-113">You can select from the following depreciation conventions.</span></span>


-   <span data-ttu-id="0ff3e-114">Medio año</span><span class="sxs-lookup"><span data-stu-id="0ff3e-114">Half year</span></span>
-   <span data-ttu-id="0ff3e-115">Mes completo</span><span class="sxs-lookup"><span data-stu-id="0ff3e-115">Full month</span></span>
-   <span data-ttu-id="0ff3e-116">Medio trimestre</span><span class="sxs-lookup"><span data-stu-id="0ff3e-116">Mid quarter</span></span>
-   <span data-ttu-id="0ff3e-117">Medio mes (primero de mes)</span><span class="sxs-lookup"><span data-stu-id="0ff3e-117">Mid month (1st of month)</span></span>
-   <span data-ttu-id="0ff3e-118">Medio mes (el día 15 del mes)</span><span class="sxs-lookup"><span data-stu-id="0ff3e-118">Mid month (15th of month)</span></span>
-   <span data-ttu-id="0ff3e-119">Medio año (inicio de año)</span><span class="sxs-lookup"><span data-stu-id="0ff3e-119">Half year (start of year)</span></span>
-   <span data-ttu-id="0ff3e-120">Medio año (próximo año)</span><span class="sxs-lookup"><span data-stu-id="0ff3e-120">Half year (next year)</span></span>

<span data-ttu-id="0ff3e-121">Puede seleccionar entre los siguientes métodos de amortización.</span><span class="sxs-lookup"><span data-stu-id="0ff3e-121">You can select from the following depreciation methods.</span></span>
-   <span data-ttu-id="0ff3e-122">Tiempo de vida de depreciación lineal</span><span class="sxs-lookup"><span data-stu-id="0ff3e-122">Straight line service life</span></span>
-   <span data-ttu-id="0ff3e-123">Depreciación degresiva</span><span class="sxs-lookup"><span data-stu-id="0ff3e-123">Reducing balance</span></span>
-   <span data-ttu-id="0ff3e-124">Manual</span><span class="sxs-lookup"><span data-stu-id="0ff3e-124">Manual</span></span>
-   <span data-ttu-id="0ff3e-125">Factor</span><span class="sxs-lookup"><span data-stu-id="0ff3e-125">Factor</span></span>
-   <span data-ttu-id="0ff3e-126">Consumo</span><span class="sxs-lookup"><span data-stu-id="0ff3e-126">Consumption</span></span>
-   <span data-ttu-id="0ff3e-127">Tiempo de vida restante de depreciación lineal</span><span class="sxs-lookup"><span data-stu-id="0ff3e-127">Straight line life remaining</span></span>
-   <span data-ttu-id="0ff3e-128">Depreciación degresiva del 200%</span><span class="sxs-lookup"><span data-stu-id="0ff3e-128">200% reducing balance</span></span>
-   <span data-ttu-id="0ff3e-129">Depreciación degresiva del 175%</span><span class="sxs-lookup"><span data-stu-id="0ff3e-129">175% reducing balance</span></span>
-   <span data-ttu-id="0ff3e-130">Depreciación degresiva del 150%</span><span class="sxs-lookup"><span data-stu-id="0ff3e-130">150% reducing balance</span></span>
-   <span data-ttu-id="0ff3e-131">Depreciación degresiva del 125%</span><span class="sxs-lookup"><span data-stu-id="0ff3e-131">125% reducing balance</span></span>





<a name="additional-resources"></a><span data-ttu-id="0ff3e-132">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="0ff3e-132">Additional resources</span></span>
--------

[<span data-ttu-id="0ff3e-133">Depreciación de activos fijos</span><span class="sxs-lookup"><span data-stu-id="0ff3e-133">Fixed asset depreciation</span></span>](fixed-asset-depreciation.md)

[<span data-ttu-id="0ff3e-134">Tiempo de vida de depreciación lineal</span><span class="sxs-lookup"><span data-stu-id="0ff3e-134">Straight line service life depreciation</span></span>](Straight-line-service-life-depreciation.md)

[<span data-ttu-id="0ff3e-135">Reducción de la depreciación del saldo</span><span class="sxs-lookup"><span data-stu-id="0ff3e-135">Reducing balance depreciation</span></span>](reduce-balance-depreciation.md)

[<span data-ttu-id="0ff3e-136">Depreciación manual</span><span class="sxs-lookup"><span data-stu-id="0ff3e-136">Manual depreciation</span></span>](manual-depreciation.md)

[<span data-ttu-id="0ff3e-137">Depreciación de factor</span><span class="sxs-lookup"><span data-stu-id="0ff3e-137">Factor depreciation</span></span>](factor-depreciation.md)

[<span data-ttu-id="0ff3e-138">Depreciación de consumo</span><span class="sxs-lookup"><span data-stu-id="0ff3e-138">Consumption depreciation</span></span>](consumption-depreciation.md)

[<span data-ttu-id="0ff3e-139">Tiempo de vida restante de depreciación lineal</span><span class="sxs-lookup"><span data-stu-id="0ff3e-139">Straight line life remaining depreciation</span></span>](straight-line-life-remaining-depreciation.md)

[<span data-ttu-id="0ff3e-140">Depreciación con amortización degresiva del 125%</span><span class="sxs-lookup"><span data-stu-id="0ff3e-140">125 percent reducing balance depreciation</span></span>](125-percent-reducing-balance-depreciation.md)

[<span data-ttu-id="0ff3e-141">Depreciación con amortización degresiva del 150%</span><span class="sxs-lookup"><span data-stu-id="0ff3e-141">150 percent reducing balance depreciation</span></span>](150-percent-reducing-balance-depreciation.md)

[<span data-ttu-id="0ff3e-142">Depreciación con amortización degresiva del 175%</span><span class="sxs-lookup"><span data-stu-id="0ff3e-142">175 percent reducing balance depreciation</span></span>](175-percent-reducing-balance-depreciation.md)

[<span data-ttu-id="0ff3e-143">Depreciación con amortización degresiva del 200%</span><span class="sxs-lookup"><span data-stu-id="0ff3e-143">200 percent reducing balance depreciation</span></span>](200-percent-reducing-balance-depreciation.md)



