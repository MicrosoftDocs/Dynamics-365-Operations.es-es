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
ms.openlocfilehash: 378fa9498018f9ca0e99e04d04cbf6a28620e308
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5210152"
---
# <a name="round-off-amount-for-depreciation-calculations"></a><span data-ttu-id="173f6-103">Importe de redondeo para cálculos de depreciación</span><span class="sxs-lookup"><span data-stu-id="173f6-103">Round-off amount for depreciation calculations</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="173f6-104">Este artículo describe el campo Depreciación de redondeo que se encuentra en las páginas de Configuración del libro.</span><span class="sxs-lookup"><span data-stu-id="173f6-104">This article discusses the Round-off depreciation field that is found on the Book setup pages.</span></span>

<span data-ttu-id="173f6-105">Los importes de depreciación de redondeo se establecen para cada libro.</span><span class="sxs-lookup"><span data-stu-id="173f6-105">Round-off depreciation amounts are set for each book.</span></span> <span data-ttu-id="173f6-106">Los importes de depreciación de redondeo se usan en el perfil de depreciación de activos fijos que muestra la depreciación futura y el valor del activo fijo, y también en las propuestas de depreciación.</span><span class="sxs-lookup"><span data-stu-id="173f6-106">Round-off depreciation amounts are used in the fixed asset depreciation profile that shows the future depreciation and value of the fixed asset, and also in depreciation proposals.</span></span> <span data-ttu-id="173f6-107">Introduzca el importe más bajo de la depreciación permitido para el libro.</span><span class="sxs-lookup"><span data-stu-id="173f6-107">Enter the lowest depreciation amount that is allowed for the book.</span></span> 

<span data-ttu-id="173f6-108">Independientemente del redondeo configurado, el importe de depreciación en el período de la última depreciación no se redondea.</span><span class="sxs-lookup"><span data-stu-id="173f6-108">Regardless of the rounding that is set up, the depreciation amount in the last depreciation period isn't rounded.</span></span> <span data-ttu-id="173f6-109">Al final del período de la última depreciación, el valor del activo fijo debe ser 0 (cero) o el valor residual, si se usa el valor residual.</span><span class="sxs-lookup"><span data-stu-id="173f6-109">At the end of the last depreciation period, the value of the fixed asset must be 0 (zero) or the scrap value, if scrap value is used.</span></span>

### <a name="example"></a><span data-ttu-id="173f6-110">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="173f6-110">Example</span></span>

<span data-ttu-id="173f6-111">La depreciación sin redondeo se calcula como 2.444,44.</span><span class="sxs-lookup"><span data-stu-id="173f6-111">Depreciation without rounding is calculated as 2,444.44.</span></span> <span data-ttu-id="173f6-112">En función de la configuración del redondeo, se sugieren distintos importes, como se indica en la tabla siguiente.</span><span class="sxs-lookup"><span data-stu-id="173f6-112">As the following table shows, the amounts that are suggested vary, depending on how rounding is set up.</span></span>

| <span data-ttu-id="173f6-113">Método de redondeo</span><span class="sxs-lookup"><span data-stu-id="173f6-113">Rounding method</span></span> | <span data-ttu-id="173f6-114">Importe de depreciación</span><span class="sxs-lookup"><span data-stu-id="173f6-114">Depreciation amount</span></span> |
|-----------------|---------------------|
| <span data-ttu-id="173f6-115">Redondeo 0,1</span><span class="sxs-lookup"><span data-stu-id="173f6-115">Rounding 0.1</span></span>    | <span data-ttu-id="173f6-116">2.444,40</span><span class="sxs-lookup"><span data-stu-id="173f6-116">2,444.40</span></span>            |
| <span data-ttu-id="173f6-117">Redondeo 1,00</span><span class="sxs-lookup"><span data-stu-id="173f6-117">Rounding 1.00</span></span>   | <span data-ttu-id="173f6-118">2.444,00</span><span class="sxs-lookup"><span data-stu-id="173f6-118">2,444.00</span></span>            |
| <span data-ttu-id="173f6-119">Redondeo 10,00</span><span class="sxs-lookup"><span data-stu-id="173f6-119">Rounding 10.00</span></span>  | <span data-ttu-id="173f6-120">2.440,00</span><span class="sxs-lookup"><span data-stu-id="173f6-120">2,440.00</span></span>            |
| <span data-ttu-id="173f6-121">Redondeo 100,00</span><span class="sxs-lookup"><span data-stu-id="173f6-121">Rounding 100.00</span></span> | <span data-ttu-id="173f6-122">2.400,00</span><span class="sxs-lookup"><span data-stu-id="173f6-122">2,400.00</span></span>            |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]