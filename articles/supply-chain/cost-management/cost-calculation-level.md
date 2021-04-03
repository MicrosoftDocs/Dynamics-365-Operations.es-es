---
title: Nivel de cálculo de costes
description: Este tema describe el nivel de lista de materiales (BOM) que se denomina Nivel de cálculo de costes. Este nivel BOM excluye los pedidos de producción y lote de sus cálculos.
author: AndersGirke
manager: tfehr
ms.date: 04/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 1cfbbb6aadbd24a0352776285f6c60ff10f59549
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251035"
---
# <a name="cost-calculation-level"></a><span data-ttu-id="1c6c3-104">Nivel de cálculo de costes</span><span class="sxs-lookup"><span data-stu-id="1c6c3-104">Cost calculation level</span></span>

<span data-ttu-id="1c6c3-105">El nivel de lista de materiales (BOM) que se denomina **Nivel de cálculo de costes** excluye pedidos de producción y pedidos por lotes de sus cálculos.</span><span class="sxs-lookup"><span data-stu-id="1c6c3-105">The bill of materials (BOM) level that is named **Cost calculation level** excludes production orders and batch orders from its calculations.</span></span> <span data-ttu-id="1c6c3-106">El sistema usa este nivel cuando ejecuta cálculos de costes en versiones de costes.</span><span class="sxs-lookup"><span data-stu-id="1c6c3-106">The system uses this level when it runs cost calculations in costing versions.</span></span> <span data-ttu-id="1c6c3-107">En procesos como el recálculo y el cierre del inventario, el sistema utiliza en su lugar el nivel BOM **Nivel de costes**.</span><span class="sxs-lookup"><span data-stu-id="1c6c3-107">In processes such as recalculation and inventory close, the system uses the **Costing level** BOM level instead.</span></span>

<span data-ttu-id="1c6c3-108">El siguiente escenario simple muestra las diferencias entre Nivel BOM de **Nivel de cálculo de costes** y el nivel BOM **Nivel de costes**.</span><span class="sxs-lookup"><span data-stu-id="1c6c3-108">The following simple scenario shows the differences between the **Cost calculation level** BOM level and the **Costing level** BOM level.</span></span>

<span data-ttu-id="1c6c3-109">Tiene tres productos: A, B y C. El producto C es el componente del producto B, y el producto B es el componente del producto A.</span><span class="sxs-lookup"><span data-stu-id="1c6c3-109">You have three products: A, B, and C. Product C is the component of product B, and product B is the component of product A.</span></span>

- <span data-ttu-id="1c6c3-110">**Nivel de costes** asigna los siguientes niveles de lista de materiales:</span><span class="sxs-lookup"><span data-stu-id="1c6c3-110">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="1c6c3-111">**Producto A:** 0</span><span class="sxs-lookup"><span data-stu-id="1c6c3-111">**Product A:** 0</span></span>
    - <span data-ttu-id="1c6c3-112">**Producto B:** 1</span><span class="sxs-lookup"><span data-stu-id="1c6c3-112">**Product B:** 1</span></span>
    - <span data-ttu-id="1c6c3-113">**Producto C:** 2</span><span class="sxs-lookup"><span data-stu-id="1c6c3-113">**Product C:** 2</span></span>

- <span data-ttu-id="1c6c3-114">**Nivel de cálculo de costes** asigna los siguientes niveles de lista de materiales:</span><span class="sxs-lookup"><span data-stu-id="1c6c3-114">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="1c6c3-115">**Producto A:** 0</span><span class="sxs-lookup"><span data-stu-id="1c6c3-115">**Product A:** 0</span></span>
    - <span data-ttu-id="1c6c3-116">**Producto B:** 1</span><span class="sxs-lookup"><span data-stu-id="1c6c3-116">**Product B:** 1</span></span>
    - <span data-ttu-id="1c6c3-117">**Producto C:** 2</span><span class="sxs-lookup"><span data-stu-id="1c6c3-117">**Product C:** 2</span></span>

<span data-ttu-id="1c6c3-118">Luego se crea una orden de producción para el producto C, y el producto A se agrega a la lista de materiales de la orden de producción.</span><span class="sxs-lookup"><span data-stu-id="1c6c3-118">A production order for product C is then created, and product A is added to the production order BOM.</span></span> <span data-ttu-id="1c6c3-119">Una vez estimado el pedido, los niveles de la lista de materiales se actualizan de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="1c6c3-119">After the order is estimated, BOM levels are updated in the following way:</span></span>

- <span data-ttu-id="1c6c3-120">**Nivel de costes** asigna los siguientes niveles de lista de materiales:</span><span class="sxs-lookup"><span data-stu-id="1c6c3-120">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="1c6c3-121">**Producto B:** 1</span><span class="sxs-lookup"><span data-stu-id="1c6c3-121">**Product B:** 1</span></span>
    - <span data-ttu-id="1c6c3-122">**Producto C:** 2</span><span class="sxs-lookup"><span data-stu-id="1c6c3-122">**Product C:** 2</span></span>
    - <span data-ttu-id="1c6c3-123">**Producto A:** 3</span><span class="sxs-lookup"><span data-stu-id="1c6c3-123">**Product A:** 3</span></span>

- <span data-ttu-id="1c6c3-124">**Nivel de cálculo de costes** asigna los siguientes niveles de lista de materiales:</span><span class="sxs-lookup"><span data-stu-id="1c6c3-124">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="1c6c3-125">**Producto A:** 0</span><span class="sxs-lookup"><span data-stu-id="1c6c3-125">**Product A:** 0</span></span>
    - <span data-ttu-id="1c6c3-126">**Producto B:** 1</span><span class="sxs-lookup"><span data-stu-id="1c6c3-126">**Product B:** 1</span></span>
    - <span data-ttu-id="1c6c3-127">**Producto C:** 2</span><span class="sxs-lookup"><span data-stu-id="1c6c3-127">**Product C:** 2</span></span>

<span data-ttu-id="1c6c3-128">Este comportamiento garantiza que los cambios en las listas de materiales de órdenes de producción no afecten los cálculos de costes posteriores.</span><span class="sxs-lookup"><span data-stu-id="1c6c3-128">This behavior ensures that changes to production order BOMs don't affect subsequent cost calculations.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]