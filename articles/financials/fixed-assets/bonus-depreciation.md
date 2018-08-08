---
title: "Depreciación de bonificación"
description: "Este artículo proporciona una visión general de la funcionalidad de depreciación de bonificación."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBonus
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 3621
ms.assetid: 835ec594-744e-461c-a676-1b9abc094173
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 5e05c0c195ddb948547ae008d050686bbcdc6ed3
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---

# <a name="bonus-depreciation"></a><span data-ttu-id="e673a-103">Depreciación de bonificación</span><span class="sxs-lookup"><span data-stu-id="e673a-103">Bonus depreciation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e673a-104">Este artículo proporciona una visión general de la funcionalidad de depreciación de bonificación.</span><span class="sxs-lookup"><span data-stu-id="e673a-104">This article provides an overview of the bonus depreciation functionality.</span></span>

<span data-ttu-id="e673a-105">Para la depreciación de bonificación puede aceptar importes de depreciación adicionales o de bonificación durante el primer año que el activo entra en servicio y se deprecia.</span><span class="sxs-lookup"><span data-stu-id="e673a-105">For bonus depreciation, you can take extra or bonus depreciation amounts during the first year that the asset is put in service and depreciated.</span></span> <span data-ttu-id="e673a-106">La amortización de la bonificación se debe realizar antes de cualquier otro cálculo de depreciación.</span><span class="sxs-lookup"><span data-stu-id="e673a-106">Bonus depreciation must be taken before any other depreciation calculations.</span></span> <span data-ttu-id="e673a-107">Por lo tanto, es preferible usar la depreciación de bonificación con libros donde la función de Registrar en la contabilidad general está deshabilitada.</span><span class="sxs-lookup"><span data-stu-id="e673a-107">Therefore, it's best to use bonus depreciation with books where the Post to general ledger functionality is disabled.</span></span> <span data-ttu-id="e673a-108">Puede usar la opción de **Suprimir transacciones no registradas en la contabilidad general** para eliminar las transacciones históricas para los libros que no registran en la contabilidad general.</span><span class="sxs-lookup"><span data-stu-id="e673a-108">You can use the **Delete transactions not posted to general ledger** option to delete historical transactions for books that don't post to the general ledger.</span></span> <span data-ttu-id="e673a-109">A continuación puede alojar la depreciación de bonificación más adelante en el ciclo de vida del activo eliminando las transacciones de depreciación previamente registradas.</span><span class="sxs-lookup"><span data-stu-id="e673a-109">You can then accommodate bonus depreciation later in the asset life cycle by deleting depreciation transactions that were previously posted.</span></span> 

<span data-ttu-id="e673a-110">Puede calcular la amortización de bonificación mediante el proceso de propuesta, o bien crear transacciones de amortización de bonificación manuales.</span><span class="sxs-lookup"><span data-stu-id="e673a-110">You can calculate bonus depreciation by using the proposal process, or you can create manual bonus depreciation transactions.</span></span> <span data-ttu-id="e673a-111">No se pueden crear transacciones de depreciación de bonificación si existen transacciones de depreciación o transacciones de ajuste de depreciación para ese libro de activos.</span><span class="sxs-lookup"><span data-stu-id="e673a-111">You can't create bonus depreciation transactions if depreciation transactions or depreciation adjustment transactions exist for that asset book.</span></span>

<span data-ttu-id="e673a-112">Cuando usa el proceso de propuesta para calcular la amortización de bonificación, todas las transacciones de bonificación existentes se incluyen en el cálculo de esa base.</span><span class="sxs-lookup"><span data-stu-id="e673a-112">When you use the proposal process to calculate bonus depreciation, all existing bonus transactions are included in the calculation of the basis.</span></span> <span data-ttu-id="e673a-113">El cálculo también incluye las depreciaciones de bonificaciones anteriores que haya introducido manualmente para el activo.</span><span class="sxs-lookup"><span data-stu-id="e673a-113">The calculation also includes any previous bonus depreciations that you manually entered for the asset.</span></span> 

<span data-ttu-id="e673a-114">Si se toma más de una amortización de bonificación para un activo, se tendrá en cuenta la prioridad.</span><span class="sxs-lookup"><span data-stu-id="e673a-114">If more than one bonus depreciation will be taken for an asset, the priority is considered.</span></span> <span data-ttu-id="e673a-115">Cada bonificación reduce la base del activo para la siguiente bonificación.</span><span class="sxs-lookup"><span data-stu-id="e673a-115">Each bonus reduces the asset basis for the next bonus.</span></span> <span data-ttu-id="e673a-116">No se tiene en cuenta el valor residual en la base del activo para los cálculos de amortización de bonificación, y la convención de amortización no se aplica a la amortización de bonificación.</span><span class="sxs-lookup"><span data-stu-id="e673a-116">Salvage value isn't considered in the asset basis for bonus depreciation calculations, and the depreciation convention doesn't apply for bonus depreciation.</span></span> 

<span data-ttu-id="e673a-117">Actualmente en los Estados Unidos, algunas propiedades reúnen los requisitos como propiedad del grupo 179.</span><span class="sxs-lookup"><span data-stu-id="e673a-117">Currently, in the United States, some property qualifies as Section 179 property.</span></span> <span data-ttu-id="e673a-118">Mediante la deducción del grupo 179, puede recuperar todo o parte del coste de algunas propiedades, hasta un límite.</span><span class="sxs-lookup"><span data-stu-id="e673a-118">By using the Section 179 deduction, you can recover all or part of the cost of some property, up to a limit.</span></span> <span data-ttu-id="e673a-119">Puede recuperar el coste deduciéndolo en el año en el que la propiedad se pone en servicio.</span><span class="sxs-lookup"><span data-stu-id="e673a-119">You can recover the cost by deducting it in the year when you put the property in service.</span></span>

## <a name="example"></a><span data-ttu-id="e673a-120">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="e673a-120">Example</span></span>
<span data-ttu-id="e673a-121">Las siguientes depreciaciones de bonificación se asocian a un libro de activos:</span><span class="sxs-lookup"><span data-stu-id="e673a-121">The following bonus depreciations are associated with an asset book:</span></span>

-   <span data-ttu-id="e673a-122">**Grupo 179:** 1.000,00, Prioridad 1</span><span class="sxs-lookup"><span data-stu-id="e673a-122">**Section 179:** 1,000.00, Priority 1</span></span>
-   <span data-ttu-id="e673a-123">**Zona de libertad:** 30 por ciento, Prioridad 2</span><span class="sxs-lookup"><span data-stu-id="e673a-123">**Liberty Zone:** 30 percent, Priority 2</span></span>

<span data-ttu-id="e673a-124">El coste de adquisición de activos es de 5.000,00.</span><span class="sxs-lookup"><span data-stu-id="e673a-124">The asset acquisition cost is 5,000.00.</span></span> <span data-ttu-id="e673a-125">Al calcular la amortización de bonificación, el primer importe de amortización es 1.000,00 para la amortización del grupo 179.</span><span class="sxs-lookup"><span data-stu-id="e673a-125">When bonus depreciation is calculated, the first bonus depreciation amount is 1,000.00 for the Section 179 depreciation.</span></span> 

<span data-ttu-id="e673a-126">El siguiente importe de amortización de bonificación para la amortización de la zona de libertad, se calcula de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="e673a-126">The next bonus depreciation amount, for the Liberty Zone depreciation, is calculated as follows:</span></span> 

<span data-ttu-id="e673a-127">Coste de adquisición: 1.000 (amortización del grupo 179) x 30% = 1.200</span><span class="sxs-lookup"><span data-stu-id="e673a-127">Acquisition cost – 1,000 (Section 179 depreciation) × 30 percent = 1,200</span></span> 

<span data-ttu-id="e673a-128">Si el importe de amortización de bonificación es superior al coste de adquisición restante, el importe de amortización de bonificación es el cálculo de amortización de bonificación o el coste de adquisición restante, cualquiera que sea inferior.</span><span class="sxs-lookup"><span data-stu-id="e673a-128">If the bonus depreciation amount is more than the remaining acquisition cost, the bonus depreciation amount is either the result of the bonus depreciation calculation or the remaining acquisition cost, whichever amount is less.</span></span> 

<span data-ttu-id="e673a-129">Si el coste de adquisición restante es 0 (cero) o menos, las transacciones de depreciación de bonificación no se generan.</span><span class="sxs-lookup"><span data-stu-id="e673a-129">If the remaining acquisition cost is 0 (zero) or less, bonus depreciation transactions isn't generated.</span></span> 

<span data-ttu-id="e673a-130">Cuando la amortización de bonificación se calcula mediante el proceso de propuesta, se crea una transacción de amortización de bonificación para todos los registros de amortización de bonificación asociados al libro amortización de activos.</span><span class="sxs-lookup"><span data-stu-id="e673a-130">When bonus depreciation is calculated by using the proposal process, a bonus depreciation transaction is created for all applicable bonus depreciation records that are associated with the asset book.</span></span> 

<span data-ttu-id="e673a-131">Puede crear un número ilimitado de registros de amortización de bonificación.</span><span class="sxs-lookup"><span data-stu-id="e673a-131">You can create an unlimited number of bonus depreciation records.</span></span> <span data-ttu-id="e673a-132">Cuando haya asignado dichos registros al libro del grupo de activos, se aplican al libro de activos.</span><span class="sxs-lookup"><span data-stu-id="e673a-132">After you assign those records to the asset group book, they are applied to the asset book.</span></span> 

<span data-ttu-id="e673a-133">La amortización de bonificación se inserta como un porcentaje o un importe fijo.</span><span class="sxs-lookup"><span data-stu-id="e673a-133">Bonus depreciation is entered as either a percentage or a fixed amount.</span></span> <span data-ttu-id="e673a-134">Al registrar las propuestas de amortización, las transacciones de amortización de bonificación se registran en el libro como transacciones independientes de las transacciones de amortización.</span><span class="sxs-lookup"><span data-stu-id="e673a-134">When you post depreciation proposals, bonus depreciation transactions are posted to the book as separate transactions from the depreciation transactions.</span></span>




