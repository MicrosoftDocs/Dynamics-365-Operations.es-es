---
title: Mantener pedidos planificados
description: En este tema se proporciona información sobre el modo de administrar pedidos planificados. Describe cómo puede actualizar el estado de los pedidos planificados, ponerlos en firme y filtrar por pedidos planificados que tengan el mismo estado que un pedido planificado seleccionado.
author: roxanadiaconu
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5ddf2c7b4c67bec6c29387c78d1fdb021d85d702
ms.sourcegitcommit: 620e15555d176eec3905b48d5001af1c50107ce6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/09/2019
ms.locfileid: "1993449"
---
# <a name="maintain-planned-orders"></a><span data-ttu-id="a1c2e-104">Mantener pedidos planificados</span><span class="sxs-lookup"><span data-stu-id="a1c2e-104">Maintain planned orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a1c2e-105">En este tema se proporciona información sobre el modo de administrar pedidos planificados.</span><span class="sxs-lookup"><span data-stu-id="a1c2e-105">This topic provides information about how to manage planned orders.</span></span> <span data-ttu-id="a1c2e-106">Describe cómo puede actualizar el estado de los pedidos planificados, ponerlos en firme y filtrar por pedidos planificados que tengan el mismo estado que un pedido planificado seleccionado.</span><span class="sxs-lookup"><span data-stu-id="a1c2e-106">It describes how you can update the status of planned orders, firm them, and filter for planned orders that have the same status as a selected planned order.</span></span>

<span data-ttu-id="a1c2e-107">Puede gestionar pedidos planificados desde el espacio de trabajo **Planificación maestra**, la lista **Pedido planificado** o las listas **Pedidos de producción planificados**, **Pedidos de compra planificados** y **Transferencia planificada**.</span><span class="sxs-lookup"><span data-stu-id="a1c2e-107">You can manage planned orders from the **Master planning** workspace, the **Planned order** list, or the **Planned production orders**, **Planned purchase orders**, and **Planned transfer** lists.</span></span> 

## <a name="planned-order-status"></a><span data-ttu-id="a1c2e-108">Estado de pedido planificado</span><span class="sxs-lookup"><span data-stu-id="a1c2e-108">Planned order status</span></span>
<span data-ttu-id="a1c2e-109">Puede usar el campo **Estado** para ayudar a realizar un seguimiento del progreso.</span><span class="sxs-lookup"><span data-stu-id="a1c2e-109">You can use the **Status** field to help track your progress.</span></span> <span data-ttu-id="a1c2e-110">Se usan los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="a1c2e-110">The following values are used:</span></span>

-   <span data-ttu-id="a1c2e-111">Cuando la planificación maestra genera pedidos planificados, estos tienen un estado **No procesado**.</span><span class="sxs-lookup"><span data-stu-id="a1c2e-111">When master planning generates planned orders, the planned orders have a status of **Unprocessed**.</span></span>
-   <span data-ttu-id="a1c2e-112">Si decide no poner en firme un pedido planificado, puede darle un estado **Finalizado**.</span><span class="sxs-lookup"><span data-stu-id="a1c2e-112">If you decide not to firm a planned order, you can give it a status of **Completed**.</span></span>
-   <span data-ttu-id="a1c2e-113">Si desea consolidar un pedido planificado, puede cambiar el estado a **Aprobado**.</span><span class="sxs-lookup"><span data-stu-id="a1c2e-113">If you want to firm a planned order, you can change the status to **Approved**.</span></span> <span data-ttu-id="a1c2e-114">Los pedidos planificados con estado **Aprobado** se respetan por la planificación maestra, por lo que no se modifican ni se eliminan.</span><span class="sxs-lookup"><span data-stu-id="a1c2e-114">Planned orders with **Approved** status are respected by master planning, so they are not modified or deleted.</span></span> 

## <a name="firming-planned-orders"></a><span data-ttu-id="a1c2e-115">Consolidar pedidos planificados</span><span class="sxs-lookup"><span data-stu-id="a1c2e-115">Firming planned orders</span></span> 
<span data-ttu-id="a1c2e-116">Al consolidar los pedidos planificados, se crean los pedidos reales.</span><span class="sxs-lookup"><span data-stu-id="a1c2e-116">By firming planned orders, real orders are created.</span></span> <span data-ttu-id="a1c2e-117">Esto también se denomina *liberado* o *pedidos abiertos*.</span><span class="sxs-lookup"><span data-stu-id="a1c2e-117">These are also know as *released* or *open orders*.</span></span> <span data-ttu-id="a1c2e-118">Al poner en firme un pedido planificado, este se mueve a la sección de pedidos del módulo relevante.</span><span class="sxs-lookup"><span data-stu-id="a1c2e-118">When a planned order is firmed, it's moved to the orders section of the relevant module.</span></span>

<span data-ttu-id="a1c2e-119">Puede seleccionar dos opciones de consolidación en la página **Pedidos planificados**:</span><span class="sxs-lookup"><span data-stu-id="a1c2e-119">You can select two firming options from the **Planned orders** page:</span></span>

-   <span data-ttu-id="a1c2e-120">**Consolidar**: esto consolidará uno o varios pedidos planificados seleccionados.</span><span class="sxs-lookup"><span data-stu-id="a1c2e-120">**Firm** – This will firm one or multiple selected planned orders.</span></span>
-   <span data-ttu-id="a1c2e-121">**Consolidar todos**: esto consolidará todos los pedidos planificados en el filtro.</span><span class="sxs-lookup"><span data-stu-id="a1c2e-121">**Firm all** – This will firm all planned orders in the filter.</span></span> <span data-ttu-id="a1c2e-122">Al usar **Consolidar todos**, no es necesario que seleccione el pedido planificado, todos los pedidos planificados en el filtro se consolidarán.</span><span class="sxs-lookup"><span data-stu-id="a1c2e-122">Using **Firm all** you don’t have to select the planned order, all planned orders within the filter will be firmed.</span></span> <span data-ttu-id="a1c2e-123">Esta opción resulta útil si está consolidando un número elevado de pedidos planificados.</span><span class="sxs-lookup"><span data-stu-id="a1c2e-123">This option can be useful if you are firming a high number of planned orders.</span></span>

> [!NOTE]
> <span data-ttu-id="a1c2e-124">Puede llevar el seguimiento de un pedido planificado que se ha consolidado desde **Historial de consolidación** en **Formulario de pedidos planificados > Ver > Historial de consolidación**.</span><span class="sxs-lookup"><span data-stu-id="a1c2e-124">You can track a planned order that was firmed from **Firming history** under **Planned orders form > View > Firming history**.</span></span>

## <a name="parallelize-firming"></a><span data-ttu-id="a1c2e-125">Paralelizar la puesta en firme</span><span class="sxs-lookup"><span data-stu-id="a1c2e-125">Parallelize firming</span></span>
<span data-ttu-id="a1c2e-126">Si tiene previsto consolidar muchos pedidos al mismo tiempo, una ejecución en paralelo puede mejorar el tiempo de ejecución o el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="a1c2e-126">If you are planning to firm many orders at the same time, parallelizing the run can improve the run time or performance.</span></span> <span data-ttu-id="a1c2e-127">Esta opción está disponible al consolidar múltiples pedidos planificados con **Consolidar** o **Consolidar todos**.</span><span class="sxs-lookup"><span data-stu-id="a1c2e-127">This option is available when firming multiple planned orders with either **Firm** or **Firm all**.</span></span> <span data-ttu-id="a1c2e-128">Están disponibles los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="a1c2e-128">The following parameters are available:</span></span>

-   <span data-ttu-id="a1c2e-129">**Consolidar en paralelo**: si se establece en **Sí** el proceso de consolidación se hará en paralelo con el número de subprocesos definidos en **Número de subprocesos**.</span><span class="sxs-lookup"><span data-stu-id="a1c2e-129">**Parallelize firming** – If **Yes**, the firming process will be parallelized with the number of threads defined in **Number of threads**.</span></span>
-   <span data-ttu-id="a1c2e-130">**Número de subprocesos**: controla el número de subprocesos utilizados para ejecutar en paralelo en proceso de consolidación.</span><span class="sxs-lookup"><span data-stu-id="a1c2e-130">**Number of threads** – Controls the number of threads used to parallelize the firming process.</span></span> <span data-ttu-id="a1c2e-131">El parámetro se muestra solo cuando **Consolidación en paralelo** se establece en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="a1c2e-131">The parameter is only shown when **Parallelize firming** is set to **Yes**.</span></span>


<a name="additional-resources"></a><span data-ttu-id="a1c2e-132">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="a1c2e-132">Additional resources</span></span>
--------

[<span data-ttu-id="a1c2e-133">Planes maestros</span><span class="sxs-lookup"><span data-stu-id="a1c2e-133">Master plans</span></span>](master-plans.md)



