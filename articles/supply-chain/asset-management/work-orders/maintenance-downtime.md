---
title: Tiempo de inactividad por mantenimiento
description: En este tema se describe el tiempo de inactividad por mantenimiento en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: cc79dc1b5911679586fa560142ada5add1a881d2
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918253"
---
# <a name="maintenance-downtime"></a><span data-ttu-id="0846f-103">Tiempo de inactividad por mantenimiento</span><span class="sxs-lookup"><span data-stu-id="0846f-103">Maintenance downtime</span></span>


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

<span data-ttu-id="0846f-104">Puede crear registros de tiempo de inactividad por mantenimiento en el activo seleccionado en una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="0846f-104">You can create maintenance downtime registrations on the asset selected on a work order.</span></span> <span data-ttu-id="0846f-105">Esto resulta útil si desea registrar el tiempo de inactividad por mantenimiento en una o más máquinas en el área de producción.</span><span class="sxs-lookup"><span data-stu-id="0846f-105">This is useful if you want to register maintenance downtime on one or more machines in the production area.</span></span> <span data-ttu-id="0846f-106">En primer lugar, cree los códigos de motivo del tiempo de inactividad por mantenimiento que desee usar, por ejemplo, desglose y detención planificada.</span><span class="sxs-lookup"><span data-stu-id="0846f-106">First, you create the maintenance downtime reason codes that you want to use, for example, breakdown and planned stop.</span></span> <span data-ttu-id="0846f-107">Esto se hace en **Códigos de motivo del tiempo de inactividad por mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="0846f-107">This is done in **Maintenance downtime reason codes**.</span></span> <span data-ttu-id="0846f-108">A continuación, puede crear registros de tiempo de inactividad por mantenimiento en **Tiempo de inactividad por mantenimiento** y agregar códigos de motivo relevantes.</span><span class="sxs-lookup"><span data-stu-id="0846f-108">Next, you can create maintenance downtime registrations in **Maintenance downtime** and add the relevant reason codes.</span></span>

## <a name="create-maintenance-downtime-reason-codes"></a><span data-ttu-id="0846f-109">Crear códigos de motivo del tiempo de inactividad por mantenimiento</span><span class="sxs-lookup"><span data-stu-id="0846f-109">Create maintenance downtime reason codes</span></span>

1. <span data-ttu-id="0846f-110">Haga clic en **Administración de activos** > **Configuración** > **Órdenes de trabajo** > **Códigos de motivo del tiempo de inactividad por mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="0846f-110">Click **Asset management** > **Setup** > **Work orders** > **Maintenance downtime reason codes**.</span></span>

2. <span data-ttu-id="0846f-111">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0846f-111">Click **New**.</span></span>

3. <span data-ttu-id="0846f-112">Inserte un identificador en el campo **Código de motivo del tiempo de inactividad por mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="0846f-112">Insert an ID in the **Maintenance downtime reason code** field.</span></span>

4. <span data-ttu-id="0846f-113">Inserte un nombre para el código de motivo en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="0846f-113">Insert a name for the reason code in the **Name** field.</span></span>

5. <span data-ttu-id="0846f-114">Seleccione la casilla **Inclusión de KPI** si el código de motivo debe incluirse en cálculos de KPI activos.</span><span class="sxs-lookup"><span data-stu-id="0846f-114">Select the **KPI include** check box if the reason code should be included in asset KPI calculations.</span></span> <span data-ttu-id="0846f-115">Normalmente, las detenciones de producción planificadas no deben incluirse en los cálculos de KPI ya que no afectan al rendimiento previsto.</span><span class="sxs-lookup"><span data-stu-id="0846f-115">Generally, planned production stops should not be included in KPI calculations as they do not impact expected performance.</span></span>

6. <span data-ttu-id="0846f-116">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0846f-116">Click **Save**.</span></span>

![Figura 1](media/15-work-orders.png)


<span data-ttu-id="0846f-118">Cuando haya creado los códigos de motivo del tiempo de inactividad por mantenimiento que desea usar, puede crear registros de tiempo de inactividad por mantenimiento para órdenes de trabajo y activos.</span><span class="sxs-lookup"><span data-stu-id="0846f-118">When you have created the maintenance downtime reason codes you want to use, you can create maintenance downtime registrations for work orders and assets.</span></span>


## <a name="create-maintenance-downtime-registrations"></a><span data-ttu-id="0846f-119">Crear registros del tiempo de inactividad por mantenimiento</span><span class="sxs-lookup"><span data-stu-id="0846f-119">Create maintenance downtime registrations</span></span>

1. <span data-ttu-id="0846f-120">Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="0846f-120">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="0846f-121">Seleccione la orden de trabajo y haga clic en **Tiempo de inactividad por mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="0846f-121">Select the work order and click **Maintenance downtime**.</span></span>

3. <span data-ttu-id="0846f-122">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0846f-122">Click **New**.</span></span>

4. <span data-ttu-id="0846f-123">Inserte el intervalo de fecha y hora para el registro de tiempo de inactividad por mantenimiento en los campos **Desde** y **Hasta**.</span><span class="sxs-lookup"><span data-stu-id="0846f-123">Insert date and time interval for the maintenance downtime registration in the **From** and **To** fields.</span></span>

5. <span data-ttu-id="0846f-124">Al salir del campo **Hasta**, la duración en horas se inserta automáticamente en el campo **Duración**.</span><span class="sxs-lookup"><span data-stu-id="0846f-124">When you leave the **To** field, the duration in hours is automatically inserted in the **Duration** field.</span></span>

6. <span data-ttu-id="0846f-125">Seleccione un código de motivo en el campo **Código de motivo del tiempo de inactividad por mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="0846f-125">Select a reason code in the **maintenance downtime reason code** field.</span></span>

7. <span data-ttu-id="0846f-126">Repita los pasos 3-6 si desea agregar más registros.</span><span class="sxs-lookup"><span data-stu-id="0846f-126">Repeat steps 3-6 if you want to add more registrations.</span></span>

8. <span data-ttu-id="0846f-127">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0846f-127">Click **Save**.</span></span>


![Figura 2](media/16-work-orders.png)


<span data-ttu-id="0846f-129">El calendario usado para calcular un registro de tiempo de inactividad por mantenimiento depende de la selección en la configuración de activos y parámetros.</span><span class="sxs-lookup"><span data-stu-id="0846f-129">The calendar used to calculate a maintenance downtime registration depends on your selection in the setup of assets and parameters.</span></span> <span data-ttu-id="0846f-130">Si se selecciona un recurso en un activo en la ficha desplegable **Todos los activos fijos** > **Activo fijo** > campo **Recurso**, se utiliza la configuración del calendario para el grupo de recursos asociado, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="0846f-130">If a resource is selected on an asset in **All assets** > **Fixed asset** FastTab > **Resource** field, the calendar set up for the associated resource group is used, as shown in the following figure.</span></span>

![Figura 3](media/17-work-orders.png)


<span data-ttu-id="0846f-132">Si no se selecciona ningún recurso en el activo, se utiliza el calendario estándar de **Parámetros de administración de activos**, como se muestra en la siguiente figura.</span><span class="sxs-lookup"><span data-stu-id="0846f-132">If no resource is selected on the asset, the standard calendar selected in **Asset management parameters** is used, as shown in the following figure.</span></span>

![Figura 4](media/18-work-orders.png)


<span data-ttu-id="0846f-134">Haga clic en **Administración de activos de la empresa** > **Consultas** > **Tiempo de inactividad por mantenimiento** para obtener una visión general de todos los registros de tiempo de inactividad por mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="0846f-134">Click **Enterprise asset management** > **Inquiries** > **Maintenance downtime** to see an overview of all maintenance downtime registrations.</span></span>

>[!NOTE]
><span data-ttu-id="0846f-135">Todos los calendarios utilizados en el módulo **Administración de activos** se configuran en **Administración de la organización** > **Configuración** > **Calendarios** > **Calendarios**.</span><span class="sxs-lookup"><span data-stu-id="0846f-135">All calendars used in the **Asset Management** module are set up in **Organization administration** > **Setup** > **Calendars** > **Calendars**.</span></span>

