---
title: Reducir la depreciación del saldo después de una división
description: Este tema describe el método que se usa en Activos fijos para calcular la depreciación después de que un activo se haya dividido mediante el método de reducción de saldo.
author: moaamer
manager: Ann Beebe
ms.date: 11/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-11-17
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 615d17c71b904d426081d4c57492ba7e95c2c749
ms.sourcegitcommit: 65f9e2584c0530b1a71655aae09101691726b47f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2020
ms.locfileid: "4650683"
---
# <a name="reduce-balance-depreciation-after-a-split"></a><span data-ttu-id="de472-103">Reducir la depreciación del saldo después de una división</span><span class="sxs-lookup"><span data-stu-id="de472-103">Reduce balance depreciation after a split</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="de472-104">Este tema describe el método que se usa en Activos fijos para calcular la depreciación después de que un activo se haya dividido en forma de otro activo mediante el método de reducción de saldo.</span><span class="sxs-lookup"><span data-stu-id="de472-104">This topic describes the method that is used in Fixed assets to calculate depreciation after an asset is split to another asset by using the reduce balance method.</span></span> <span data-ttu-id="de472-105">El año de depreciación que se configura en el libro de activos es el año fiscal.</span><span class="sxs-lookup"><span data-stu-id="de472-105">The depreciation year that is configured in the asset book is the fiscal year.</span></span> <span data-ttu-id="de472-106">Para más información, consulte [Reducir la depreciación del saldo](reduce-balance-depreciation.md) y [Dividir un activo fijo](tasks/split-fixed-asset.md).</span><span class="sxs-lookup"><span data-stu-id="de472-106">For more information, see [Reduce balance depreciation](reduce-balance-depreciation.md) and [Split a fixed asset](tasks/split-fixed-asset.md).</span></span>

<span data-ttu-id="de472-107">Si divide un activo fijo durante un período fiscal posterior al período en el que se adquirió el activo, la depreciación del saldo reducido contabilizará el valor neto en los libros (NBV) del activo para el año anterior.</span><span class="sxs-lookup"><span data-stu-id="de472-107">If you split a fixed asset during a fiscal period that is later than the period when the asset was acquired, the reduced balance depreciation will account for the asset's net book value (NBV) for the previous year.</span></span> <span data-ttu-id="de472-108">También tendrá en cuenta las transacciones de ajuste de adquisición y depreciación que se generaron a partir de la transacción que dividió el activo.</span><span class="sxs-lookup"><span data-stu-id="de472-108">It will also account for the acquisition and depreciation adjustment transactions that were generated from the transaction that split the asset.</span></span> <span data-ttu-id="de472-109">Este comportamiento supone que el activo se adquirió en un año fiscal y se dividió en un año fiscal posterior.</span><span class="sxs-lookup"><span data-stu-id="de472-109">This behavior assumes that the asset was acquired in one fiscal year and split in a later fiscal year.</span></span> <span data-ttu-id="de472-110">El monto que debe depreciarse para el activo original después de la división refleja el NBV del activo antes de que se dividiera el activo y la transacción de ajuste de adquisición y depreciación que se registró para la división.</span><span class="sxs-lookup"><span data-stu-id="de472-110">The amount that must be depreciated for the original asset after the split reflects the asset's NBV before the asset was split, and the acquisition and depreciation adjustment transaction that was posted for the split.</span></span>

<span data-ttu-id="de472-111">Por ejemplo, están en vigor las siguientes condiciones:</span><span class="sxs-lookup"><span data-stu-id="de472-111">For example, the following conditions are in effect:</span></span>

- <span data-ttu-id="de472-112">El período fiscal es del 30 de junio al 1 de julio.</span><span class="sxs-lookup"><span data-stu-id="de472-112">The fiscal period is from June 30 to July 1.</span></span>
- <span data-ttu-id="de472-113">El porcentaje de saldo de reducción es del 18 por ciento, y un activo se adquiere en junio de 2019 a un precio de adquisición de 10.000 $.</span><span class="sxs-lookup"><span data-stu-id="de472-113">The reducing balance percentage is 18 percent, and an asset is acquired in June 2019 at an acquisition price of $10,000.</span></span>
- <span data-ttu-id="de472-114">La depreciación del primer año fiscal es igual a 18.000 $, la depreciación mensual es igual a 150 $, y luego el activo se deprecia hasta noviembre de 2019, por un importe de 738,75 $.</span><span class="sxs-lookup"><span data-stu-id="de472-114">The depreciation of the first fiscal year equals $18,000, the monthly depreciation equals $150, and the asset is then depreciated until November 2019, in the amount of $738.75.</span></span>
- <span data-ttu-id="de472-115">En noviembre de 2019, el 80 por ciento del activo se divide en otro activo fijo.</span><span class="sxs-lookup"><span data-stu-id="de472-115">In November 2019, 80 percent of the asset is split to another fixed asset.</span></span>

<span data-ttu-id="de472-116">[![Reducir la depreciación del saldo después de una división](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)</span><span class="sxs-lookup"><span data-stu-id="de472-116">[![Reduce balance depreciation after a split](./media/reduce-balance-depreciation-after-split.png)](./media/reduce-balance-depreciation-after-split.png)</span></span>

<span data-ttu-id="de472-117">La cantidad a depreciar del activo original es 1.822,25 $.</span><span class="sxs-lookup"><span data-stu-id="de472-117">The amount to depreciate for the original asset is $1,822.25.</span></span> <span data-ttu-id="de472-118">Esta cantidad es igual al NBV antes de que se contabilice la transacción dividida (9.111,25), más el ajuste de adquisición que se genera durante la contabilización de la transacción dividida (- 8.000 $), más el ajuste de depreciación que se genera durante la transacción dividida (711 $).</span><span class="sxs-lookup"><span data-stu-id="de472-118">This amount equals the NBV before the split transaction is posted ($9,111.25), plus the acquisition adjustment that is generated during posting of the split transaction (-$8,000), plus the depreciation adjustment that is generated during the split transaction ($711).</span></span> <span data-ttu-id="de472-119">Por lo tanto, la depreciación para el segundo año es (1.822,25 × 18 por ciento) ÷ 12 = 27,33 $.</span><span class="sxs-lookup"><span data-stu-id="de472-119">Therefore, the depreciation for the second year is (1,822.25 × 18 percent) ÷ 12 = $27.33.</span></span>

<span data-ttu-id="de472-120">La cantidad a depreciar para el nuevo activo fijo en el primer año es (8.000 × 18 por ciento) ÷ 12 = 120 $.</span><span class="sxs-lookup"><span data-stu-id="de472-120">The amount to depreciate for the new fixed asset in the first year is (8,000 × 18 percent) ÷ 12 = $120.</span></span>
