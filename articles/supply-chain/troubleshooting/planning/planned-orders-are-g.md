---
title: La planificación maestra genera pedidos planificados para productos fantasma
description: Al ejecutar la planificación maestra, se crean pedidos planificados para productos fantasma.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: anderso
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1ea4bdb3729d163126234e02524cef331051cd48
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026888"
---
# <a name="master-planning-generates-planned-orders-for-phantom-products"></a><span data-ttu-id="d0007-103">La planificación maestra genera pedidos planificados para productos fantasma</span><span class="sxs-lookup"><span data-stu-id="d0007-103">Master planning generates planned orders for phantom products</span></span>

<span data-ttu-id="d0007-104">Número de KB: 4614729</span><span class="sxs-lookup"><span data-stu-id="d0007-104">KB number: 4614729</span></span>

## <a name="symptoms"></a><span data-ttu-id="d0007-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="d0007-105">Symptoms</span></span>

<span data-ttu-id="d0007-106">Al ejecutar la planificación maestra, se crean pedidos planificados para productos fantasma.</span><span class="sxs-lookup"><span data-stu-id="d0007-106">Planned orders are generated for phantom products after master planning is run.</span></span>

## <a name="resolution"></a><span data-ttu-id="d0007-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="d0007-107">Resolution</span></span>

<span data-ttu-id="d0007-108">La configuración de la opción **Fantasma** para productos lanzados determina el tipo de línea predeterminado en la lista de materiales (BOM).</span><span class="sxs-lookup"><span data-stu-id="d0007-108">The setting of the **Phantom** option for released products determines the default line type on the bill of material (BOM).</span></span> <span data-ttu-id="d0007-109">Cuando la opción **Fantasma** está configurada en *Sí*, el sistema seguirá creando pedidos planificados para el artículo, pero la opción **Requisito derivado directamente** para cada pedido planificado se establecerá en *Sí*.</span><span class="sxs-lookup"><span data-stu-id="d0007-109">When the **Phantom** option is set to *Yes*, the system will still create planned orders for the item, but the **Directly derived requirement** option for each planned order will be set to *Yes*.</span></span> <span data-ttu-id="d0007-110">Por lo tanto, el pedido de producción planificado no se puede confirmar por sí solo.</span><span class="sxs-lookup"><span data-stu-id="d0007-110">Therefore, the planned production order can't be firmed on its own.</span></span> <span data-ttu-id="d0007-111">En cambio, siempre se incluirá automáticamente cuando se confirme el pedido de producción principal.</span><span class="sxs-lookup"><span data-stu-id="d0007-111">Instead, it will always be automatically included when the parent production order is firmed.</span></span> <span data-ttu-id="d0007-112">Además, las líneas de la L. MAT. del pedido fantasma planificado se incluirán en la L. MAT. del pedido de producción principal.</span><span class="sxs-lookup"><span data-stu-id="d0007-112">Additionally, the BOM lines of the planned phantom order will be included in the BOM of the parent production order.</span></span>
