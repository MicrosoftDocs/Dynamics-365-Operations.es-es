---
title: Creación de órdenes de trabajo
description: En este tema se explica cómo crear órdenes de trabajo en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: b23ed3251b2f6cf4f34b423ce2f85301d6ab31a1
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875877"
---
# <a name="creating-work-orders"></a><span data-ttu-id="16345-103">Creación de órdenes de trabajo</span><span class="sxs-lookup"><span data-stu-id="16345-103">Creating work orders</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


<span data-ttu-id="16345-104">Cuando haya programado trabajos de mantenimiento preventivo, el paso siguiente es crear las órdenes de trabajo para los trabajos.</span><span class="sxs-lookup"><span data-stu-id="16345-104">When you have scheduled preventive maintenance jobs, next step is to create work orders for the jobs.</span></span> <span data-ttu-id="16345-105">Esta tarea se lleva a cabo en uno de los programas de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="16345-105">This is done in one of the maintenance schedules.</span></span> <span data-ttu-id="16345-106">Los trabajos programados en un programa de mantenimiento pueden tener distintos tipos de referencia:</span><span class="sxs-lookup"><span data-stu-id="16345-106">The scheduled jobs in a maintenance schedule can have different reference types:</span></span>

| <span data-ttu-id="16345-107">Tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="16345-107">Reference type</span></span> | <span data-ttu-id="16345-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="16345-108">Description</span></span>                    |
|-----------------------|------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="16345-109">Planes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="16345-109">Maintenance plans</span></span>     | <span data-ttu-id="16345-110">Trabajos de mantenimiento preventivo basados en los tipos de planes de mantenimiento "Hora" o "Contador".</span><span class="sxs-lookup"><span data-stu-id="16345-110">Preventive maintenance jobs based on maintenance plan types "Time" or "Counter".</span></span>                       |
| <span data-ttu-id="16345-111">Rondas de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="16345-111">Maintenance rounds</span></span>    | <span data-ttu-id="16345-112">Trabajos de mantenimiento preventivo que contienen varios activos que requieren un tipo de mantenimiento similar.</span><span class="sxs-lookup"><span data-stu-id="16345-112">Preventive maintenance jobs containing several assets that require a similar type of maintenance.</span></span>           |
| <span data-ttu-id="16345-113">Solicitud de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="16345-113">Maintenance request</span></span>   | <span data-ttu-id="16345-114">Pedido creado manualmente para el mantenimiento o la reparación de un activo, que se puede convertir en una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="16345-114">Manually created request for maintenance or repair of an asset, which can be converted into a work order.</span></span> |


1. <span data-ttu-id="16345-115">Haga clic en **Administración de activos** > **Común** > **Toda la programación de mantenimiento** o **Líneas de programa de mantenimiento abiertas** o **Conjuntos abiertos de la programación de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="16345-115">Click **Asset management** > **Common** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools**.</span></span>

2. <span data-ttu-id="16345-116">Seleccione los trabajos de mantenimiento programados para los que desea crear una orden de trabajo y para hacer clic en **Orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="16345-116">Select the scheduled maintenance jobs for which you want to create a work order and click **Work order**.</span></span> <span data-ttu-id="16345-117">El número total de horas previstas para las líneas seleccionadas se muestra en el campo **Horas de previsión de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="16345-117">The total number of forecast hours for the selected lines is shown in the **Maintenance forecast hours** field.</span></span>

3. <span data-ttu-id="16345-118">En la sección **Parámetros**, seleccione cuántas órdenes de trabajo se deben crear.</span><span class="sxs-lookup"><span data-stu-id="16345-118">In the **Parameters** section, select how many work orders should be created.</span></span> <span data-ttu-id="16345-119">Puede crear una orden de trabajo por línea de programa de mantenimiento o varias órdenes de trabajo función de las selecciones realizadas en la sección **Una orden de trabajo por**.</span><span class="sxs-lookup"><span data-stu-id="16345-119">You can create one work order per maintenance schedule line, or a number of work orders based on your selections in the **One work order per** section.</span></span>

4. <span data-ttu-id="16345-120">Seleccione un **Tipo de orden de trabajo** que se usará en todas las órdenes de trabajo que cree.</span><span class="sxs-lookup"><span data-stu-id="16345-120">Select a **Work order type** that will be used on all the work orders you create.</span></span>

5. <span data-ttu-id="16345-121">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="16345-121">Click **OK**.</span></span> <span data-ttu-id="16345-122">Se crearán una o más órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="16345-122">One or more work orders are created.</span></span>

![Figura 1](media/18-preventive-maintenance.png)

