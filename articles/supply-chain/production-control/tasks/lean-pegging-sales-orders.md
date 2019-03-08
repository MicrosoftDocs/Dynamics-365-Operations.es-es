---
title: Diagrama de árbol lean de pedidos de ventas
description: Este procedimiento se centra en validar el diagrama de árbol de una línea de ventas donde el artículo se produce con kanbans.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2e2448dfd83304d4f7e5dfc8ce0d02cdac998779
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "340370"
---
# <a name="lean-pegging-from-sales-orders"></a><span data-ttu-id="747a5-103">Diagrama de árbol lean de pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="747a5-103">Lean pegging from sales orders</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="747a5-104">Este procedimiento se centra en validar el diagrama de árbol de una línea de ventas donde el artículo se produce con kanbans.</span><span class="sxs-lookup"><span data-stu-id="747a5-104">This procedure focuses on validating the pegging tree from a sales line where the item is produced with kanbans.</span></span> <span data-ttu-id="747a5-105">Después de validar el diagrama de árbol, se planifican todos los trabajos kanban.</span><span class="sxs-lookup"><span data-stu-id="747a5-105">After validating the pegging tree, all the kanban jobs are planned.</span></span> <span data-ttu-id="747a5-106">Esto resulta útil para escenarios de pedidos donde el creador del pedido necesita asegurarse de que la producción puede comenzar inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="747a5-106">This is useful for order scenarios where the order taker needs to ensure that production can start right away.</span></span> <span data-ttu-id="747a5-107">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="747a5-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="747a5-108">Este procedimiento está pensado para el creador del pedido avanzado que trabaja en una empresa lean.</span><span class="sxs-lookup"><span data-stu-id="747a5-108">This procedure is intended for the advanced order taker working in a lean company.</span></span>


## <a name="create-a-sales-order-for-a-kanban-controlled-item"></a><span data-ttu-id="747a5-109">Crear un pedido de ventas para un artículo controlado por kanban</span><span class="sxs-lookup"><span data-stu-id="747a5-109">Create a sales order for a kanban controlled item</span></span>
1. <span data-ttu-id="747a5-110">Vaya a Todos los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="747a5-110">Go to All sales orders.</span></span>
2. <span data-ttu-id="747a5-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="747a5-111">Click New.</span></span>
3. <span data-ttu-id="747a5-112">En el campo Cuenta de cliente, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="747a5-112">In the Customer account field, enter or select a value.</span></span>
    * <span data-ttu-id="747a5-113">Use US-001.</span><span class="sxs-lookup"><span data-stu-id="747a5-113">Use US-001.</span></span>  
4. <span data-ttu-id="747a5-114">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="747a5-114">Click OK.</span></span>
5. <span data-ttu-id="747a5-115">En el campo Código de artículo, escriba 'L0001'.</span><span class="sxs-lookup"><span data-stu-id="747a5-115">In the Item number field, type 'L0001'.</span></span>
6. <span data-ttu-id="747a5-116">Establezca el valor de cantidad en '30'.</span><span class="sxs-lookup"><span data-stu-id="747a5-116">Set Quantity to '30'.</span></span>
    * <span data-ttu-id="747a5-117">Es importante que la cantidad sea mayor de 24 para activar la regla kanban de evento.</span><span class="sxs-lookup"><span data-stu-id="747a5-117">It is important that the quantity is higher than 24 in order to trigger the event kanban rule.</span></span>  

## <a name="open-a-pegging-tree"></a><span data-ttu-id="747a5-118">Abrir un árbol de diagrama de árbol</span><span class="sxs-lookup"><span data-stu-id="747a5-118">Open a pegging tree</span></span> 
1. <span data-ttu-id="747a5-119">Haga clic en Producto y suministro.</span><span class="sxs-lookup"><span data-stu-id="747a5-119">Click Product and supply.</span></span>
2. <span data-ttu-id="747a5-120">Haga clic en Ver diagrama de árbol.</span><span class="sxs-lookup"><span data-stu-id="747a5-120">Click View pegging tree.</span></span>
    * <span data-ttu-id="747a5-121">Tenga en cuenta que el diagrama de árbol muestra todos los niveles del diagrama de árbol necesario para la línea de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="747a5-121">Notice that the pegging tree shows all levels of the pegging needed for the sales order line.</span></span> <span data-ttu-id="747a5-122">En este caso, hay dos niveles de kanbans y todos los componentes necesarios.</span><span class="sxs-lookup"><span data-stu-id="747a5-122">In this case, there are two levels of kanbans and all the required components.</span></span>  

## <a name="plan-the-pegging-tree"></a><span data-ttu-id="747a5-123">Planificar el diagrama de árbol</span><span class="sxs-lookup"><span data-stu-id="747a5-123">Plan the pegging tree</span></span>
1. <span data-ttu-id="747a5-124">En el árbol, seleccione "Línea de ventas 000832\Kanban 000558".</span><span class="sxs-lookup"><span data-stu-id="747a5-124">In the tree, select 'Sales line 000832\Kanban 000558'.</span></span>
2. <span data-ttu-id="747a5-125">Expanda la sección Trabajos kanban.</span><span class="sxs-lookup"><span data-stu-id="747a5-125">Expand the Kanban jobs section.</span></span>
    * <span data-ttu-id="747a5-126">Observe que el estado de trabajo del trabajo es Sin planificar.</span><span class="sxs-lookup"><span data-stu-id="747a5-126">Notice that the job status for the kanban job is Not planned.</span></span>  
3. <span data-ttu-id="747a5-127">Haga clic en Planificar todo el diagrama de árbol.</span><span class="sxs-lookup"><span data-stu-id="747a5-127">Click Plan entire pegging tree.</span></span>
    * <span data-ttu-id="747a5-128">Esto planeará todos los trabajos kanban en el diagrama de árbol, cambiando el estado del trabajo de Sin planificar a Planificado.</span><span class="sxs-lookup"><span data-stu-id="747a5-128">This will plan all kanban jobs in the pegging tree, changing the Job status from Not planned to Planned.</span></span>  
4. <span data-ttu-id="747a5-129">Actualice la página.</span><span class="sxs-lookup"><span data-stu-id="747a5-129">Refresh the page.</span></span>
    * <span data-ttu-id="747a5-130">Observe que el estado del trabajo kanban cambió de Sin planificar a Planificado.</span><span class="sxs-lookup"><span data-stu-id="747a5-130">Notice that the kanban Job status changed from Not planned to Planned.</span></span>  
5. <span data-ttu-id="747a5-131">En el árbol, seleccione "Sales line 000832\Kanban 000558\Issue for L0001\Kanban 000559".</span><span class="sxs-lookup"><span data-stu-id="747a5-131">In the tree, select 'Sales line 000832\Kanban 000558\Issue for L0001\Kanban 000559'.</span></span>
    * <span data-ttu-id="747a5-132">El trabajo para el segundo kanban también se planifica, ya que se planifica el diagrama de árbol completo.</span><span class="sxs-lookup"><span data-stu-id="747a5-132">The job for the second kanban is also planned, because the entire pegging tree is planned.</span></span> <span data-ttu-id="747a5-133">Observe que el estado del trabajo kanban se cambia de Sin planificar a Planificado.</span><span class="sxs-lookup"><span data-stu-id="747a5-133">Notice that the kanban job status is changed from Not planned to Planned.</span></span>  

