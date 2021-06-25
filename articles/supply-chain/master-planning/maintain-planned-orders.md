---
title: Mantener pedidos planificados
description: En este tema se proporciona información sobre el modo de administrar pedidos planificados. Describe cómo puede actualizar el estado de los pedidos planificados, ponerlos en firme y filtrar por pedidos planificados que tengan el mismo estado que un pedido planificado seleccionado.
author: roxanadiaconu
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransPo, ReqTransFirmLog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7f16a666cef5625fb159265ddc7237ad0eb45927
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "6187659"
---
# <a name="maintain-planned-orders"></a><span data-ttu-id="191d3-104">Mantener pedidos planificados</span><span class="sxs-lookup"><span data-stu-id="191d3-104">Maintain planned orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="191d3-105">En este tema se proporciona información sobre el modo de administrar pedidos planificados.</span><span class="sxs-lookup"><span data-stu-id="191d3-105">This topic provides information about how to manage planned orders.</span></span> <span data-ttu-id="191d3-106">Describe cómo puede actualizar el estado de los pedidos planificados, ponerlos en firme y filtrar por pedidos planificados que tengan el mismo estado que un pedido planificado seleccionado.</span><span class="sxs-lookup"><span data-stu-id="191d3-106">It describes how you can update the status of planned orders, firm them, and filter for planned orders that have the same status as a selected planned order.</span></span>

<span data-ttu-id="191d3-107">Puede gestionar pedidos planificados desde el espacio de trabajo **Planificación maestra**, la lista **Pedido planificado** o las listas **Pedidos de producción planificados**, **Pedidos de compra planificados** y **Transferencia planificada**.</span><span class="sxs-lookup"><span data-stu-id="191d3-107">You can manage planned orders from the **Master planning** workspace, the **Planned order** list, or the **Planned production orders**, **Planned purchase orders**, and **Planned transfer** lists.</span></span> 

## <a name="planned-order-status"></a><span data-ttu-id="191d3-108">Estado de pedido planificado</span><span class="sxs-lookup"><span data-stu-id="191d3-108">Planned order status</span></span>
<span data-ttu-id="191d3-109">Puede usar el campo **Estado** para ayudar a realizar un seguimiento del progreso.</span><span class="sxs-lookup"><span data-stu-id="191d3-109">You can use the **Status** field to help track your progress.</span></span> <span data-ttu-id="191d3-110">Se usan los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="191d3-110">The following values are used:</span></span>

-   <span data-ttu-id="191d3-111">Cuando la planificación maestra genera pedidos planificados, estos tienen un estado **No procesado**.</span><span class="sxs-lookup"><span data-stu-id="191d3-111">When master planning generates planned orders, the planned orders have a status of **Unprocessed**.</span></span>
-   <span data-ttu-id="191d3-112">Si decide no poner en firme un pedido planificado, puede darle un estado **Finalizado**.</span><span class="sxs-lookup"><span data-stu-id="191d3-112">If you decide not to firm a planned order, you can give it a status of **Completed**.</span></span>
-   <span data-ttu-id="191d3-113">Si desea consolidar un pedido planificado, puede cambiar el estado a **Aprobado**.</span><span class="sxs-lookup"><span data-stu-id="191d3-113">If you want to firm a planned order, you can change the status to **Approved**.</span></span> <span data-ttu-id="191d3-114">Los pedidos planificados con estado **Aprobado** se respetan por la planificación maestra, por lo que no se modifican ni se eliminan durante una ejecución de planificación maestra posterior.</span><span class="sxs-lookup"><span data-stu-id="191d3-114">Planned orders with **Approved** status are respected by master planning, so they are not modified or deleted during a later master planning run.</span></span> <span data-ttu-id="191d3-115">Para lograr esto, la lógica de planificación copia los pedidos planificados **Aprobados** desde la versión anterior del plan a la nueva versión del plan durante la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="191d3-115">To achieve this, the planning logic copies the **Approved** planned orders from the old plan version to the new plan version during master planning.</span></span>

## <a name="firming-planned-orders"></a><span data-ttu-id="191d3-116">Consolidar pedidos planificados</span><span class="sxs-lookup"><span data-stu-id="191d3-116">Firming planned orders</span></span> 
<span data-ttu-id="191d3-117">Al consolidar los pedidos planificados, se crean los pedidos reales.</span><span class="sxs-lookup"><span data-stu-id="191d3-117">By firming planned orders, real orders are created.</span></span> <span data-ttu-id="191d3-118">También se llaman *pedidos liberados* o *abiertos*.</span><span class="sxs-lookup"><span data-stu-id="191d3-118">These are also known as *released* or *open orders*.</span></span> <span data-ttu-id="191d3-119">Al poner en firme un pedido planificado, este se mueve a la sección de pedidos del módulo relevante.</span><span class="sxs-lookup"><span data-stu-id="191d3-119">When a planned order is firmed, it's moved to the orders section of the relevant module.</span></span>

<span data-ttu-id="191d3-120">Puede seleccionar dos opciones de consolidación en la página **Pedidos planificados**:</span><span class="sxs-lookup"><span data-stu-id="191d3-120">You can select two firming options from the **Planned orders** page:</span></span>

-   <span data-ttu-id="191d3-121">**Consolidar**: esto consolidará uno o varios pedidos planificados seleccionados.</span><span class="sxs-lookup"><span data-stu-id="191d3-121">**Firm** – This will firm one or multiple selected planned orders.</span></span>
-   <span data-ttu-id="191d3-122">**Consolidar todos**: esto consolidará todos los pedidos planificados en el filtro.</span><span class="sxs-lookup"><span data-stu-id="191d3-122">**Firm all** – This will firm all planned orders in the filter.</span></span> <span data-ttu-id="191d3-123">Al usar **Consolidar todos**, no es necesario que seleccione el pedido planificado, todos los pedidos planificados en el filtro se consolidarán.</span><span class="sxs-lookup"><span data-stu-id="191d3-123">Using **Firm all** you don’t have to select the planned order, all planned orders within the filter will be firmed.</span></span> <span data-ttu-id="191d3-124">Esta opción resulta útil si está consolidando un número elevado de pedidos planificados.</span><span class="sxs-lookup"><span data-stu-id="191d3-124">This option can be useful if you are firming a high number of planned orders.</span></span>

> [!NOTE]
> <span data-ttu-id="191d3-125">Puede llevar el seguimiento de un pedido planificado que se ha consolidado desde **Historial de consolidación** en **Formulario de pedidos planificados > Ver > Historial de consolidación**.</span><span class="sxs-lookup"><span data-stu-id="191d3-125">You can track a planned order that was firmed from **Firming history** under **Planned orders form > View > Firming history**.</span></span>

## <a name="parallelize-firming"></a><span data-ttu-id="191d3-126">Paralelizar la puesta en firme</span><span class="sxs-lookup"><span data-stu-id="191d3-126">Parallelize firming</span></span>
<span data-ttu-id="191d3-127">Si tiene previsto consolidar muchos pedidos al mismo tiempo, una ejecución en paralelo puede mejorar el tiempo de ejecución o el rendimiento.</span><span class="sxs-lookup"><span data-stu-id="191d3-127">If you are planning to firm many orders at the same time, parallelizing the run can improve the run time or performance.</span></span> <span data-ttu-id="191d3-128">Esta opción está disponible al consolidar múltiples pedidos planificados con **Consolidar** o **Consolidar todos**.</span><span class="sxs-lookup"><span data-stu-id="191d3-128">This option is available when firming multiple planned orders with either **Firm** or **Firm all**.</span></span> <span data-ttu-id="191d3-129">Están disponibles los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="191d3-129">The following parameters are available:</span></span>

-   <span data-ttu-id="191d3-130">**Consolidar en paralelo**: si se establece en **Sí** el proceso de consolidación se hará en paralelo con el número de subprocesos definidos en **Número de subprocesos**.</span><span class="sxs-lookup"><span data-stu-id="191d3-130">**Parallelize firming** – If **Yes**, the firming process will be parallelized with the number of threads defined in **Number of threads**.</span></span>
-   <span data-ttu-id="191d3-131">**Número de subprocesos**: controla el número de subprocesos utilizados para ejecutar en paralelo en proceso de consolidación.</span><span class="sxs-lookup"><span data-stu-id="191d3-131">**Number of threads** – Controls the number of threads used to parallelize the firming process.</span></span> <span data-ttu-id="191d3-132">El parámetro se muestra solo cuando **Consolidación en paralelo** se establece en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="191d3-132">The parameter is only shown when **Parallelize firming** is set to **Yes**.</span></span>

> [!NOTE]
> <span data-ttu-id="191d3-133">La opción para **Paralelizar la puesta en firme** solo se muestra cuando se selecciona más de un pedido planificado para la puesta en firme.</span><span class="sxs-lookup"><span data-stu-id="191d3-133">The option for **Parallelize firming** is only shown when you have more than one planned order selected for firming.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="191d3-134">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="191d3-134">Additional resources</span></span>

[<span data-ttu-id="191d3-135">Visión general de los planes maestros</span><span class="sxs-lookup"><span data-stu-id="191d3-135">Master plans overview</span></span>](master-plans.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]