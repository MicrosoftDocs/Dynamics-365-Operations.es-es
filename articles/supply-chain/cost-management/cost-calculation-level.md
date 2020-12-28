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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2020-04-23
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 52b77e794ee38add556ac01d62c973b38c48a548
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436764"
---
# <a name="cost-calculation-level"></a><span data-ttu-id="85ab5-104">Nivel de cálculo de costes</span><span class="sxs-lookup"><span data-stu-id="85ab5-104">Cost calculation level</span></span>

<span data-ttu-id="85ab5-105">El nivel de lista de materiales (BOM) que se denomina **Nivel de cálculo de costes** excluye pedidos de producción y pedidos por lotes de sus cálculos.</span><span class="sxs-lookup"><span data-stu-id="85ab5-105">The bill of materials (BOM) level that is named **Cost calculation level** excludes production orders and batch orders from its calculations.</span></span> <span data-ttu-id="85ab5-106">El sistema usa este nivel cuando ejecuta cálculos de costes en versiones de costes.</span><span class="sxs-lookup"><span data-stu-id="85ab5-106">The system uses this level when it runs cost calculations in costing versions.</span></span> <span data-ttu-id="85ab5-107">En procesos como el recálculo y el cierre del inventario, el sistema utiliza en su lugar el nivel BOM **Nivel de costes**.</span><span class="sxs-lookup"><span data-stu-id="85ab5-107">In processes such as recalculation and inventory close, the system uses the **Costing level** BOM level instead.</span></span>

<span data-ttu-id="85ab5-108">El siguiente escenario simple muestra las diferencias entre Nivel BOM de **Nivel de cálculo de costes** y el nivel BOM **Nivel de costes**.</span><span class="sxs-lookup"><span data-stu-id="85ab5-108">The following simple scenario shows the differences between the **Cost calculation level** BOM level and the **Costing level** BOM level.</span></span>

<span data-ttu-id="85ab5-109">Tiene tres productos: A, B y C. El producto C es el componente del producto B, y el producto B es el componente del producto A.</span><span class="sxs-lookup"><span data-stu-id="85ab5-109">You have three products: A, B, and C. Product C is the component of product B, and product B is the component of product A.</span></span>

- <span data-ttu-id="85ab5-110">**Nivel de costes** asigna los siguientes niveles de lista de materiales:</span><span class="sxs-lookup"><span data-stu-id="85ab5-110">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="85ab5-111">**Producto A:** 0</span><span class="sxs-lookup"><span data-stu-id="85ab5-111">**Product A:** 0</span></span>
    - <span data-ttu-id="85ab5-112">**Producto B:** 1</span><span class="sxs-lookup"><span data-stu-id="85ab5-112">**Product B:** 1</span></span>
    - <span data-ttu-id="85ab5-113">**Producto C:** 2</span><span class="sxs-lookup"><span data-stu-id="85ab5-113">**Product C:** 2</span></span>

- <span data-ttu-id="85ab5-114">**Nivel de cálculo de costes** asigna los siguientes niveles de lista de materiales:</span><span class="sxs-lookup"><span data-stu-id="85ab5-114">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="85ab5-115">**Producto A:** 0</span><span class="sxs-lookup"><span data-stu-id="85ab5-115">**Product A:** 0</span></span>
    - <span data-ttu-id="85ab5-116">**Producto B:** 1</span><span class="sxs-lookup"><span data-stu-id="85ab5-116">**Product B:** 1</span></span>
    - <span data-ttu-id="85ab5-117">**Producto C:** 2</span><span class="sxs-lookup"><span data-stu-id="85ab5-117">**Product C:** 2</span></span>

<span data-ttu-id="85ab5-118">Luego se crea una orden de producción para el producto C, y el producto A se agrega a la lista de materiales de la orden de producción.</span><span class="sxs-lookup"><span data-stu-id="85ab5-118">A production order for product C is then created, and product A is added to the production order BOM.</span></span> <span data-ttu-id="85ab5-119">Una vez estimado el pedido, los niveles de la lista de materiales se actualizan de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="85ab5-119">After the order is estimated, BOM levels are updated in the following way:</span></span>

- <span data-ttu-id="85ab5-120">**Nivel de costes** asigna los siguientes niveles de lista de materiales:</span><span class="sxs-lookup"><span data-stu-id="85ab5-120">**Costing level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="85ab5-121">**Producto B:** 1</span><span class="sxs-lookup"><span data-stu-id="85ab5-121">**Product B:** 1</span></span>
    - <span data-ttu-id="85ab5-122">**Producto C:** 2</span><span class="sxs-lookup"><span data-stu-id="85ab5-122">**Product C:** 2</span></span>
    - <span data-ttu-id="85ab5-123">**Producto A:** 3</span><span class="sxs-lookup"><span data-stu-id="85ab5-123">**Product A:** 3</span></span>

- <span data-ttu-id="85ab5-124">**Nivel de cálculo de costes** asigna los siguientes niveles de lista de materiales:</span><span class="sxs-lookup"><span data-stu-id="85ab5-124">**Cost calculation level** assigns the following BOM levels:</span></span>

    - <span data-ttu-id="85ab5-125">**Producto A:** 0</span><span class="sxs-lookup"><span data-stu-id="85ab5-125">**Product A:** 0</span></span>
    - <span data-ttu-id="85ab5-126">**Producto B:** 1</span><span class="sxs-lookup"><span data-stu-id="85ab5-126">**Product B:** 1</span></span>
    - <span data-ttu-id="85ab5-127">**Producto C:** 2</span><span class="sxs-lookup"><span data-stu-id="85ab5-127">**Product C:** 2</span></span>

<span data-ttu-id="85ab5-128">Este comportamiento garantiza que los cambios en las listas de materiales de órdenes de producción no afecten los cálculos de costes posteriores.</span><span class="sxs-lookup"><span data-stu-id="85ab5-128">This behavior ensures that changes to production order BOMs don't affect subsequent cost calculations.</span></span>
