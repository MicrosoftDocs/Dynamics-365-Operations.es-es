---
title: Importe de redondeo para cálculos de depreciación
description: Este artículo describe el campo Depreciación de redondeo que se encuentra en las páginas de Configuración del libro.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetBookTable, AssetDepBookTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 13931
ms.assetid: faf7db87-046f-41d1-9baf-0df66e373e97
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 01c8662f0731abd089c9039c16bb77e39c1d3e51
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976025"
---
# <a name="round-off-amount-for-depreciation-calculations"></a><span data-ttu-id="de34f-103">Importe de redondeo para cálculos de depreciación</span><span class="sxs-lookup"><span data-stu-id="de34f-103">Round-off amount for depreciation calculations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="de34f-104">Este artículo describe el campo Depreciación de redondeo que se encuentra en las páginas de Configuración del libro.</span><span class="sxs-lookup"><span data-stu-id="de34f-104">This article discusses the Round-off depreciation field that is found on the Book setup pages.</span></span>

<span data-ttu-id="de34f-105">Los importes de depreciación de redondeo se establecen para cada libro.</span><span class="sxs-lookup"><span data-stu-id="de34f-105">Round-off depreciation amounts are set for each book.</span></span> <span data-ttu-id="de34f-106">Los importes de depreciación de redondeo se usan en el perfil de depreciación de activos fijos que muestra la depreciación futura y el valor del activo fijo, y también en las propuestas de depreciación.</span><span class="sxs-lookup"><span data-stu-id="de34f-106">Round-off depreciation amounts are used in the fixed asset depreciation profile that shows the future depreciation and value of the fixed asset, and also in depreciation proposals.</span></span> <span data-ttu-id="de34f-107">Introduzca el importe más bajo de la depreciación permitido para el libro.</span><span class="sxs-lookup"><span data-stu-id="de34f-107">Enter the lowest depreciation amount that is allowed for the book.</span></span> 

<span data-ttu-id="de34f-108">Independientemente del redondeo configurado, el importe de depreciación en el período de la última depreciación no se redondea.</span><span class="sxs-lookup"><span data-stu-id="de34f-108">Regardless of the rounding that is set up, the depreciation amount in the last depreciation period isn't rounded.</span></span> <span data-ttu-id="de34f-109">Al final del período de la última depreciación, el valor del activo fijo debe ser 0 (cero) o el valor residual, si se usa el valor residual.</span><span class="sxs-lookup"><span data-stu-id="de34f-109">At the end of the last depreciation period, the value of the fixed asset must be 0 (zero) or the scrap value, if scrap value is used.</span></span>

### <a name="example"></a><span data-ttu-id="de34f-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="de34f-110">Example</span></span>

<span data-ttu-id="de34f-111">La depreciación sin redondeo se calcula como 2.444,44.</span><span class="sxs-lookup"><span data-stu-id="de34f-111">Depreciation without rounding is calculated as 2,444.44.</span></span> <span data-ttu-id="de34f-112">En función de la configuración del redondeo, se sugieren distintos importes, como se indica en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="de34f-112">As the following table shows, the amounts that are suggested vary, depending on how rounding is set up.</span></span>

| <span data-ttu-id="de34f-113">Método de redondeo</span><span class="sxs-lookup"><span data-stu-id="de34f-113">Rounding method</span></span> | <span data-ttu-id="de34f-114">Importe de depreciación</span><span class="sxs-lookup"><span data-stu-id="de34f-114">Depreciation amount</span></span> |
|-----------------|---------------------|
| <span data-ttu-id="de34f-115">Redondeo 0,1</span><span class="sxs-lookup"><span data-stu-id="de34f-115">Rounding 0.1</span></span>    | <span data-ttu-id="de34f-116">2.444,40</span><span class="sxs-lookup"><span data-stu-id="de34f-116">2,444.40</span></span>            |
| <span data-ttu-id="de34f-117">Redondeo 1,00</span><span class="sxs-lookup"><span data-stu-id="de34f-117">Rounding 1.00</span></span>   | <span data-ttu-id="de34f-118">2.444,00</span><span class="sxs-lookup"><span data-stu-id="de34f-118">2,444.00</span></span>            |
| <span data-ttu-id="de34f-119">Redondeo 10,00</span><span class="sxs-lookup"><span data-stu-id="de34f-119">Rounding 10.00</span></span>  | <span data-ttu-id="de34f-120">2.440,00</span><span class="sxs-lookup"><span data-stu-id="de34f-120">2,440.00</span></span>            |
| <span data-ttu-id="de34f-121">Redondeo 100,00</span><span class="sxs-lookup"><span data-stu-id="de34f-121">Rounding 100.00</span></span> | <span data-ttu-id="de34f-122">2.400,00</span><span class="sxs-lookup"><span data-stu-id="de34f-122">2,400.00</span></span>            |





