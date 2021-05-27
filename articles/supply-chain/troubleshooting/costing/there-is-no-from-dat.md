---
title: No hay un valor de Fecha inicial en la pestaña Precios activos de la página Precio de artículo
description: No hay un valor de Fecha inicial en la pestaña Precios activos de la página Precio de artículo.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventItemPrice
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 3dd13f6a3e5ce3c894e96f420358d337f2e43dba
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026896"
---
# <a name="there-is-no-from-date-value-on-the-active-prices-tab-of-the-item-price-page"></a><span data-ttu-id="18d25-103">No hay un valor de Fecha inicial en la pestaña Precios activos de la página Precio de artículo</span><span class="sxs-lookup"><span data-stu-id="18d25-103">There is no From date value on the Active prices tab of the Item price page</span></span>

<span data-ttu-id="18d25-104">Número de KB: 4613548</span><span class="sxs-lookup"><span data-stu-id="18d25-104">KB number: 4613548</span></span>

## <a name="symptoms"></a><span data-ttu-id="18d25-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="18d25-105">Symptoms</span></span>

<span data-ttu-id="18d25-106">No hay un valor de **Fecha inicial** en la pestaña **Precios activos** de la página **Precio de artículo**.</span><span class="sxs-lookup"><span data-stu-id="18d25-106">There is no **From date** value on the **Active prices** tab of the **Item price** page.</span></span>

## <a name="resolution"></a><span data-ttu-id="18d25-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="18d25-107">Resolution</span></span>

<span data-ttu-id="18d25-108">El valor **Fecha inicial** (fecha de vigencia) que se establece en el precio pendiente no se transfiere al precio activo.</span><span class="sxs-lookup"><span data-stu-id="18d25-108">The **From date** value (effective date) that is set on the pending price isn't transferred to the active price.</span></span>

<span data-ttu-id="18d25-109">La primera vez que se especifica un registro de coste de artículo, presenta un estado de *Pendiente* y una fecha de vigencia prevista.</span><span class="sxs-lookup"><span data-stu-id="18d25-109">When an item cost record is first entered, it has a status of *Pending* and an intended effective date.</span></span> <span data-ttu-id="18d25-110">Al activar el registro de costes de artículo, se actualiza el estado a *Activo* y la fecha de vigencia a la fecha de activación.</span><span class="sxs-lookup"><span data-stu-id="18d25-110">When you activate the item cost record, the status is updated to *Active*, and the effective date is updated to the activation date.</span></span> <span data-ttu-id="18d25-111">Por lo tanto, la fecha de activación del precio activo es siempre la fecha real de activación.</span><span class="sxs-lookup"><span data-stu-id="18d25-111">Therefore, the active price's activation date is always the actual date of the activation.</span></span>

<span data-ttu-id="18d25-112">Para obtener más información, consulte [Información general de las versiones de gestión de costes](../../cost-management/costing-versions.md).</span><span class="sxs-lookup"><span data-stu-id="18d25-112">For more information, see [Costing versions overview](../../cost-management/costing-versions.md).</span></span>
