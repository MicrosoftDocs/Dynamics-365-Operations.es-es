---
title: Creación de órdenes de trabajo
description: En este tema se explica cómo crear órdenes de trabajo en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 08/27/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f94f8bc20753e38ce1cb6eccdfbc85c2e491ffad
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3206136"
---
# <a name="creating-work-orders"></a><span data-ttu-id="f94a3-103">Creación de órdenes de trabajo</span><span class="sxs-lookup"><span data-stu-id="f94a3-103">Creating work orders</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="f94a3-104">Cuando haya programado trabajos de mantenimiento preventivo, el paso siguiente es crear las órdenes de trabajo para los trabajos.</span><span class="sxs-lookup"><span data-stu-id="f94a3-104">When you have scheduled preventive maintenance jobs, next step is to create work orders for the jobs.</span></span> <span data-ttu-id="f94a3-105">Esta tarea se lleva a cabo en uno de los programas de mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="f94a3-105">This is done in one of the maintenance schedules.</span></span> <span data-ttu-id="f94a3-106">Los trabajos programados en un programa de mantenimiento pueden tener distintos tipos de referencia:</span><span class="sxs-lookup"><span data-stu-id="f94a3-106">The scheduled jobs in a maintenance schedule can have different reference types:</span></span>

| <span data-ttu-id="f94a3-107">Tipo de referencia</span><span class="sxs-lookup"><span data-stu-id="f94a3-107">Reference type</span></span> | <span data-ttu-id="f94a3-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="f94a3-108">Description</span></span>                    |
|-----------------------|------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f94a3-109">Planes de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="f94a3-109">Maintenance plans</span></span>     | <span data-ttu-id="f94a3-110">Trabajos de mantenimiento preventivo basados en los tipos de planes de mantenimiento "Hora" o "Contador".</span><span class="sxs-lookup"><span data-stu-id="f94a3-110">Preventive maintenance jobs based on maintenance plan types "Time" or "Counter".</span></span>                       |
| <span data-ttu-id="f94a3-111">Rondas de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="f94a3-111">Maintenance rounds</span></span>    | <span data-ttu-id="f94a3-112">Trabajos de mantenimiento preventivo que contienen varios activos que requieren un tipo de mantenimiento similar.</span><span class="sxs-lookup"><span data-stu-id="f94a3-112">Preventive maintenance jobs containing several assets that require a similar type of maintenance.</span></span>           |
| <span data-ttu-id="f94a3-113">Solicitud de mantenimiento</span><span class="sxs-lookup"><span data-stu-id="f94a3-113">Maintenance request</span></span>   | <span data-ttu-id="f94a3-114">Pedido creado manualmente para el mantenimiento o la reparación de un activo, que se puede convertir en una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f94a3-114">Manually created request for maintenance or repair of an asset, which can be converted into a work order.</span></span> |


1. <span data-ttu-id="f94a3-115">Haga clic en **Administración de activos** > **Común** > **Toda la programación de mantenimiento** o **Líneas de programa de mantenimiento abiertas** o **Conjuntos abiertos de la programación de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="f94a3-115">Click **Asset management** > **Common** > **All maintenance schedule** or **Open maintenance schedule lines** or **Open maintenance schedule pools**.</span></span>

2. <span data-ttu-id="f94a3-116">Seleccione los trabajos de mantenimiento programados para los que desea crear una orden de trabajo y para hacer clic en **Orden de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="f94a3-116">Select the scheduled maintenance jobs for which you want to create a work order and click **Work order**.</span></span> <span data-ttu-id="f94a3-117">En el cuadro de diálogo **Crear órdenes de trabajo**, el número total de horas previstas para las líneas seleccionadas se muestra en el campo **Horas de previsión de mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="f94a3-117">In the **Create work orders** dialog, the total number of forecast hours for the selected lines is shown in the **Maintenance forecast hours** field.</span></span>

3. <span data-ttu-id="f94a3-118">En la sección **Parámetros**, seleccione cuántas órdenes de trabajo se deben crear.</span><span class="sxs-lookup"><span data-stu-id="f94a3-118">In the **Parameters** section, select how many work orders should be created.</span></span> <span data-ttu-id="f94a3-119">Puede crear una orden de trabajo por línea de programa de mantenimiento o varias órdenes de trabajo función de las selecciones realizadas en la sección **Una orden de trabajo por**.</span><span class="sxs-lookup"><span data-stu-id="f94a3-119">You can create one work order per maintenance schedule line, or a number of work orders based on your selections in the **One work order per** section.</span></span>

4. <span data-ttu-id="f94a3-120">Seleccione un **Tipo de orden de trabajo** que se usará en todas las órdenes de trabajo que cree.</span><span class="sxs-lookup"><span data-stu-id="f94a3-120">Select a **Work order type** that will be used on all the work orders you create.</span></span> <span data-ttu-id="f94a3-121">La ilustración siguiente muestra un ejemplo del diálogo **Crear órdenes de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="f94a3-121">The illustration below shows an example of the **Create work orders** dialog.</span></span>

![Figura 1](media/18-preventive-maintenance.png)

5. <span data-ttu-id="f94a3-123">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f94a3-123">Click **OK**.</span></span> <span data-ttu-id="f94a3-124">Se crearán una o más órdenes de trabajo.</span><span class="sxs-lookup"><span data-stu-id="f94a3-124">One or more work orders are created.</span></span>

