---
title: Mantener pedidos planificados
description: "En este tema se proporciona información sobre el modo de administrar pedidos planificados. Describe cómo puede actualizar el estado de los pedidos planificados, ponerlos en firme y filtrar por pedidos planificados que tengan el mismo estado que un pedido planificado seleccionado."
author: roxanadiaconu
manager: AnnBe
ms.date: 10/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
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
ms.translationtype: HT
ms.sourcegitcommit: 657c19896b20a514dc5308bf7fb086085b482fec
ms.openlocfilehash: bf578d98abc4825c5607ec031da6ab6737c3183a
ms.contentlocale: es-es
ms.lasthandoff: 10/08/2018

---

# <a name="maintain-planned-orders"></a><span data-ttu-id="320b3-104">Mantener pedidos planificados</span><span class="sxs-lookup"><span data-stu-id="320b3-104">Maintain planned orders</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="320b3-105">En este tema se proporciona información sobre el modo de administrar pedidos planificados.</span><span class="sxs-lookup"><span data-stu-id="320b3-105">This topic provides information about how to manage planned orders.</span></span> <span data-ttu-id="320b3-106">Describe cómo puede actualizar el estado de los pedidos planificados, ponerlos en firme y filtrar por pedidos planificados que tengan el mismo estado que un pedido planificado seleccionado.</span><span class="sxs-lookup"><span data-stu-id="320b3-106">It describes how you can update the status of planned orders, firm them, and filter for planned orders that have the same status as a selected planned order.</span></span>

<span data-ttu-id="320b3-107">Puede gestionar pedidos planificados desde el espacio de trabajo **Planificación maestra**, la lista **Pedido planificado** o las listas **Pedidos de producción planificados**, **Pedidos de compra planificados** y **Transferencia planificada**.</span><span class="sxs-lookup"><span data-stu-id="320b3-107">You can manage planned orders from the **Master planning** workspace, the **Planned order** list, or the **Planned production orders**, **Planned purchase orders**, and **Planned transfer** lists.</span></span> <span data-ttu-id="320b3-108">Puede usar el campo **Estado** para ayudar a realizar un seguimiento del progreso.</span><span class="sxs-lookup"><span data-stu-id="320b3-108">You can use the **Status** field to help track your progress.</span></span> <span data-ttu-id="320b3-109">Se usan los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="320b3-109">The following values are used:</span></span>

-   <span data-ttu-id="320b3-110">Cuando la planificación maestra genera pedidos planificados, estos tienen un estado **No procesado**.</span><span class="sxs-lookup"><span data-stu-id="320b3-110">When master planning generates planned orders, the planned orders have a status of **Unprocessed**.</span></span>
-   <span data-ttu-id="320b3-111">Si decide no poner en firme un pedido planificado, puede darle un estado **Finalizado**.</span><span class="sxs-lookup"><span data-stu-id="320b3-111">If you decide not to firm a planned order, you can give it a status of **Completed**.</span></span>
-   <span data-ttu-id="320b3-112">Si decide poner en firme un pedido planificado, puede darle el estado de **Aprobado**.</span><span class="sxs-lookup"><span data-stu-id="320b3-112">When you decide to firm a planned order, you can give it a status of **Approved**.</span></span> <span data-ttu-id="320b3-113">Este estado indica que aprueba poner en firme el pedido planificado pero que aún no está puesto en firme.</span><span class="sxs-lookup"><span data-stu-id="320b3-113">This status indicates that you approve firming of the planned order, but it isn't firmed yet.</span></span>

<span data-ttu-id="320b3-114">**Nota:** un pedido planificado aprobado se transfiere en su estado actual al siguiente cálculo de planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="320b3-114">**Note:** An approved planned order is transferred, in its current state, to the next master planning calculation.</span></span> <span data-ttu-id="320b3-115">Puede poner en firme los pedidos planificados haciendo clic en **En firme**.</span><span class="sxs-lookup"><span data-stu-id="320b3-115">You can firm planned orders by clicking **Firm**.</span></span> <span data-ttu-id="320b3-116">Puede poner en firme los siguientes pedidos planificados:</span><span class="sxs-lookup"><span data-stu-id="320b3-116">You can firm the following planned orders:</span></span>

-   <span data-ttu-id="320b3-117">El pedido planificado que está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="320b3-117">The planned order that is selected.</span></span>
-   <span data-ttu-id="320b3-118">Varios pedidos planificados.</span><span class="sxs-lookup"><span data-stu-id="320b3-118">Multiple planned orders.</span></span>
-   <span data-ttu-id="320b3-119">Los pedidos planificados generados por una expansión desde la página **Expansión**.</span><span class="sxs-lookup"><span data-stu-id="320b3-119">Planned orders that are generated by an explosion from the **Explosion** page.</span></span> <span data-ttu-id="320b3-120">Haga clic en **Pedidos planificados**, seleccione el pedido planificado y, a continuación, haga clic en **En firme**.</span><span class="sxs-lookup"><span data-stu-id="320b3-120">Click **Planned orders**, select the planned order, and then click **Firm**.</span></span>

<span data-ttu-id="320b3-121">Al poner en firme un pedido planificado, este se mueve a la sección de pedidos del módulo relevante.</span><span class="sxs-lookup"><span data-stu-id="320b3-121">When a planned order is firmed, it's moved to the orders section of the relevant module.</span></span> 

<a name="additional-resources"></a><span data-ttu-id="320b3-122">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="320b3-122">Additional resources</span></span>
--------

[<span data-ttu-id="320b3-123">Planes maestros</span><span class="sxs-lookup"><span data-stu-id="320b3-123">Master plans</span></span>](master-plans.md)




