---
title: Grupos de revalorización de activos fijos
description: Este tema proporciona información acerca de la revalorización de activos fijos para España.
author: EvgenyPopovMBS
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetRevaluationGroup, AssetBookTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 264994
ms.search.region: Spain
ms.author: epopov
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 180a1f61507f258709950409485371e73187ecfe
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1549525"
---
# <a name="fixed-asset-revaluation-groups"></a><span data-ttu-id="6d033-103">Grupos de revalorización de activos fijos</span><span class="sxs-lookup"><span data-stu-id="6d033-103">Fixed asset revaluation groups</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6d033-104">Este tema proporciona información acerca de la revalorización de activos fijos para España.</span><span class="sxs-lookup"><span data-stu-id="6d033-104">This topic provides information about fixed asset revaluation groups for Spain.</span></span>

<span data-ttu-id="6d033-105">Los grupos de revalorización se usan para configurar condiciones de revalorización para el activo fijo.</span><span class="sxs-lookup"><span data-stu-id="6d033-105">Revaluation groups are used to set up revaluation conditions for the fixed asset.</span></span> <span data-ttu-id="6d033-106">Por ejemplo, el grupo de revalorización podría ser un factor o una fecha de revalorización.</span><span class="sxs-lookup"><span data-stu-id="6d033-106">For example, the revaluation group could be a factor or revaluation date.</span></span> <span data-ttu-id="6d033-107">El valor del grupo de revalorización se usará en el diario de activos fijos para las propuestas de revalorización y para los ajustes de valores individuales de transacciones de revalorización.</span><span class="sxs-lookup"><span data-stu-id="6d033-107">Value from the revaluation group will be used in the fixed asset journal for revaluation proposals and for individual value adjustments of revaluation transactions.</span></span> <span data-ttu-id="6d033-108">Para revalorizar un activo fijo debe especificar el grupo de revalorización en la página **Libros**.</span><span class="sxs-lookup"><span data-stu-id="6d033-108">To revaluate a fixed asset, you must specify the revaluation group on the **Books** page.</span></span> <span data-ttu-id="6d033-109">El valor del grupo de revalorización se usará en el diario de activos fijos para las propuestas de revalorización y para los ajustes de valores individuales de transacciones de revalorización.</span><span class="sxs-lookup"><span data-stu-id="6d033-109">Value from the revaluation group will be used in the fixed asset journal for revaluation proposals and for individual value adjustments of revaluation transactions.</span></span>

## <a name="revaluation-group-setup"></a><span data-ttu-id="6d033-110">Configuración de grupo de revalorización</span><span class="sxs-lookup"><span data-stu-id="6d033-110">Revaluation group setup</span></span>
<span data-ttu-id="6d033-111">Puede configurar un grupo de revalorización en la página **Grupos de revalorización**.</span><span class="sxs-lookup"><span data-stu-id="6d033-111">You can set up a revaluation group in the **Revaluation groups** page.</span></span> <span data-ttu-id="6d033-112">El panel superior, cree un identificador para el grupo de revalorización.</span><span class="sxs-lookup"><span data-stu-id="6d033-112">In the upper pane, create an identifier for the revaluation group.</span></span> <span data-ttu-id="6d033-113">En el panel inferior, especifique la fecha de la revalorización y el factor por el que se aumentará o disminuirá el valor.</span><span class="sxs-lookup"><span data-stu-id="6d033-113">In the lower pane, enter the date of the revaluation and the factor that the value will increase or decrease by.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6d033-114"><strong>Campo</strong></span><span class="sxs-lookup"><span data-stu-id="6d033-114"><strong>Field</strong></span></span></td>
<td><span data-ttu-id="6d033-115"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="6d033-115"><strong>Description</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6d033-116"><strong>Grupo de revalorización</strong></span><span class="sxs-lookup"><span data-stu-id="6d033-116"><strong>Revaluation group</strong></span></span></td>
<td><span data-ttu-id="6d033-117">Especificar la identificación del grupo de revalorización.</span><span class="sxs-lookup"><span data-stu-id="6d033-117">Enter the identification of the revaluation group.</span></span> <span data-ttu-id="6d033-118">En el caso de los activos fijos que se van a configurar para la revalorización, el grupo de revalorización se debe asignar al activo fijo por modelo de valor.</span><span class="sxs-lookup"><span data-stu-id="6d033-118">For fixed assets that will be set up for revaluation, a revaluation group must be allocated to the fixed asset per value model.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6d033-119"><strong>Descripción</strong></span><span class="sxs-lookup"><span data-stu-id="6d033-119"><strong>Description</strong></span></span></td>
<td><span data-ttu-id="6d033-120">Especifique la descripción del grupo de revalorización que describe el propósito de cada grupo.</span><span class="sxs-lookup"><span data-stu-id="6d033-120">Enter the description of the revaluation group that describes the purpose of each group.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6d033-121"><strong>Fecha</strong></span><span class="sxs-lookup"><span data-stu-id="6d033-121"><strong>Date</strong></span></span></td>
<td><span data-ttu-id="6d033-122">Especificar la fecha a partir de la cual es válido el factor de revalorización.</span><span class="sxs-lookup"><span data-stu-id="6d033-122">Enter the date from which the revaluation factor is valid.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6d033-123"><strong>Factor</strong></span><span class="sxs-lookup"><span data-stu-id="6d033-123"><strong>Factor</strong></span></span></td>
<td><span data-ttu-id="6d033-124">Especificar el factor y el precio de adquisición que determina la propuesta de revalorización del activo fijo.</span><span class="sxs-lookup"><span data-stu-id="6d033-124">Enter the factor and the acquisition price that determines the revaluation proposal for the fixed asset.</span></span> <span data-ttu-id="6d033-125">Por ejemplo, supongamos que el importe de la adquisición es de 100.000.</span><span class="sxs-lookup"><span data-stu-id="6d033-125">For example, suppose the acquisition amount was 100,000.</span></span> <span data-ttu-id="6d033-126">Con la ecuación <em>Importe de la adquisición - (importe de adquisición \* factor)</em>, la siguiente tabla muestra el resultado de distintos factores.</span><span class="sxs-lookup"><span data-stu-id="6d033-126">Using the equation <em>Acquisition amount - (Acquisition amount \* factor),</em> the following table displays the result of different factors.</span></span>
<table>
<tbody>
<tr class="odd">
<td><span data-ttu-id="6d033-127"><strong>Factor</strong></span><span class="sxs-lookup"><span data-stu-id="6d033-127"><strong>Factor</strong></span></span></td>
<td><span data-ttu-id="6d033-128"><strong>Fórmula</strong></span><span class="sxs-lookup"><span data-stu-id="6d033-128"><strong>Formula</strong></span></span></td>
<td><span data-ttu-id="6d033-129"><strong>Transacción</strong> </span><span class="sxs-lookup"><span data-stu-id="6d033-129"><strong>Transaction</strong></span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6d033-130">1</span><span class="sxs-lookup"><span data-stu-id="6d033-130">1</span></span></td>
<td><span data-ttu-id="6d033-131">100.000 - (100.000 \* 1)</span><span class="sxs-lookup"><span data-stu-id="6d033-131">100,000 - (100,000 \* 1)</span></span></td>
<td><span data-ttu-id="6d033-132">Sin transacción</span><span class="sxs-lookup"><span data-stu-id="6d033-132">No transaction</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="6d033-133">10</span><span class="sxs-lookup"><span data-stu-id="6d033-133">10</span></span></td>
<td><span data-ttu-id="6d033-134">100.000 - (100.000 \* 10)</span><span class="sxs-lookup"><span data-stu-id="6d033-134">100,000 - (100,000 \* 10)</span></span></td>
<td><span data-ttu-id="6d033-135">Débito 900.000</span><span class="sxs-lookup"><span data-stu-id="6d033-135">900,000 Debit</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="6d033-136">0.5</span><span class="sxs-lookup"><span data-stu-id="6d033-136">0.5</span></span></td>
<td><span data-ttu-id="6d033-137">100.000 - (100.000 \* 0,5)</span><span class="sxs-lookup"><span data-stu-id="6d033-137">100,000 - (100,000 \* 0.5)</span></span></td>
<td><span data-ttu-id="6d033-138">Crédito 50.000</span><span class="sxs-lookup"><span data-stu-id="6d033-138">50,000 Credit</span></span></td>
</tr>
</tbody>
</table></td>
</tr>
</tbody>
</table>





