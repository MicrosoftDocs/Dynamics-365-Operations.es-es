---
title: Tiempo de inactividad por mantenimiento
description: En este tema se describe el tiempo de inactividad por mantenimiento en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 10/15/2019
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
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: ad9f1b2a0e63b4fb0d6daceb451c3a1dc1ec7de7
ms.sourcegitcommit: deb87e518a151d8bb084891851a39758938a96e4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/15/2019
ms.locfileid: "2626164"
---
# <a name="maintenance-downtime"></a><span data-ttu-id="53e20-103">Tiempo de inactividad por mantenimiento</span><span class="sxs-lookup"><span data-stu-id="53e20-103">Maintenance downtime</span></span>

[!include [banner](../../includes/banner.md)]


<span data-ttu-id="53e20-104">Puede crear registros de tiempo de inactividad por mantenimiento en el activo seleccionado en una orden de trabajo.</span><span class="sxs-lookup"><span data-stu-id="53e20-104">You can create maintenance downtime registrations on the asset that is selected on a work order.</span></span> <span data-ttu-id="53e20-105">Esta capacidad resulta útil si desea registrar el tiempo de inactividad por mantenimiento en una o más máquinas en el área de producción.</span><span class="sxs-lookup"><span data-stu-id="53e20-105">This capability is useful if you want to register maintenance downtime on one or more machines in the production area.</span></span> <span data-ttu-id="53e20-106">En primer lugar, cree los códigos de motivo del tiempo de inactividad por mantenimiento que desee usar, por ejemplo, **Desglose** y **Parada planificada**.</span><span class="sxs-lookup"><span data-stu-id="53e20-106">You first create the maintenance downtime reason codes that you want to use, such as **Breakdown** and **Planned stop**.</span></span> <span data-ttu-id="53e20-107">Este paso se hace en la página **Códigos de motivo del tiempo de inactividad por mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="53e20-107">This step is done on the **Maintenance downtime reason codes** page.</span></span> <span data-ttu-id="53e20-108">A continuación, puede crear registros de tiempo de inactividad por mantenimiento en la página **Tiempo de inactividad por mantenimiento** y agregar códigos de motivo de inactividad por mantenimiento relevantes.</span><span class="sxs-lookup"><span data-stu-id="53e20-108">You can then create maintenance downtime registrations on the **Maintenance downtime** page and add the relevant maintenance downtime reason codes.</span></span>

## <a name="create-maintenance-downtime-reason-codes"></a><span data-ttu-id="53e20-109">Crear códigos de motivo del tiempo de inactividad por mantenimiento</span><span class="sxs-lookup"><span data-stu-id="53e20-109">Create maintenance downtime reason codes</span></span>

1. <span data-ttu-id="53e20-110">Seleccione **Administración de activos** > **Configuración** > **Órdenes de trabajo** > **Códigos de motivo del tiempo de inactividad por mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="53e20-110">Select **Asset management** > **Setup** > **Work orders** > **Maintenance downtime reason codes**.</span></span>

2. <span data-ttu-id="53e20-111">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="53e20-111">Select **New**.</span></span>

3. <span data-ttu-id="53e20-112">En el campo **Código de motivo del tiempo de inactividad por mantenimiento**, especifique un identificador para el código de motivo del tiempo de inactividad mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="53e20-112">In the **Maintenance downtime reason code** field, enter an ID for the maintenance downtime reason code.</span></span>

4. <span data-ttu-id="53e20-113">Escriba un nombre en el campo **Nombre**.</span><span class="sxs-lookup"><span data-stu-id="53e20-113">In the **Name** field, enter a name.</span></span>

5. <span data-ttu-id="53e20-114">Seleccione la casilla de verificación **Inclusión de KPI** si el código de motivo se debe incluir en los cálculos de los indicadores clave de rendimiento (KPI) para el activo.</span><span class="sxs-lookup"><span data-stu-id="53e20-114">Select the **KPI include** check box if the reason code should be included in calculations of key performance indicators (KPIs) for the asset.</span></span> <span data-ttu-id="53e20-115">Normalmente, las detenciones de producción planificadas no deben incluirse en los cálculos de KPI ya que no afectan al rendimiento previsto.</span><span class="sxs-lookup"><span data-stu-id="53e20-115">In general, planned production stops should not be included in KPI calculations, because they don't affect expected performance.</span></span>

6. <span data-ttu-id="53e20-116">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="53e20-116">Select **Save**.</span></span>

<span data-ttu-id="53e20-117">La ilustración siguiente muestra un ejemplo de página de **Códigos de motivo de inactividad por mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="53e20-117">The illustration below shows an example of the **Maintenance downtime reason codes** page.</span></span>

![Figura 1](media/15-work-orders.png)

<span data-ttu-id="53e20-119"> Cuando haya creado los códigos de motivo del tiempo de inactividad por mantenimiento que desea usar, puede crear registros de tiempo de inactividad por mantenimiento para órdenes de trabajo y activos.</span><span class="sxs-lookup"><span data-stu-id="53e20-119">After you've created the maintenance downtime reason codes that you want to use, you can create maintenance downtime registrations for work orders and assets.</span></span>


## <a name="create-maintenance-downtime-registrations"></a><span data-ttu-id="53e20-120">Crear registros del tiempo de inactividad por mantenimiento</span><span class="sxs-lookup"><span data-stu-id="53e20-120">Create maintenance downtime registrations</span></span>

1. <span data-ttu-id="53e20-121">Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.</span><span class="sxs-lookup"><span data-stu-id="53e20-121">Click **Asset management** > **Common** > **Work orders** > **All work orders** or **Active work orders**.</span></span>

2. <span data-ttu-id="53e20-122">Seleccione la orden de trabajo y, a continuación, en la pestaña **Orden de trabajo**, en el grupo **Activo**, seleccione **Tiempo de inactividad por mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="53e20-122">Select the work order, and then, on the **Work order** tab, in the **Asset** group, select **Maintenance downtime**.</span></span>

3. <span data-ttu-id="53e20-123">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="53e20-123">Select **New**.</span></span>

4. <span data-ttu-id="53e20-124">Defina la fecha y el intervalo de tiempo del registro de tiempo de inactividad por mantenimiento en los campos **Desde** y **Hasta**.</span><span class="sxs-lookup"><span data-stu-id="53e20-124">In the **From** and **To** fields, define the date and time interval for the maintenance downtime registration.</span></span>

>[!NOTE]
><span data-ttu-id="53e20-125">Al salir del campo **Hasta**, la duración en horas se inserta automáticamente en el campo **Duración**.</span><span class="sxs-lookup"><span data-stu-id="53e20-125">When you leave the **To** field, the duration in hours is automatically inserted in the **Duration** field.</span></span>

5. <span data-ttu-id="53e20-126">Seleccione un código de motivo en el campo **Código de motivo del tiempo de inactividad por mantenimiento**.</span><span class="sxs-lookup"><span data-stu-id="53e20-126">In the **maintenance downtime reason code** field, select a reason code.</span></span>

6. <span data-ttu-id="53e20-127">Repita los pasos del 3 al 5 para agregar registros.</span><span class="sxs-lookup"><span data-stu-id="53e20-127">Repeat steps 3 through 5 to add more registrations.</span></span>

7. <span data-ttu-id="53e20-128">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="53e20-128">Select **Save**.</span></span>

<span data-ttu-id="53e20-129">En la ilustración siguiente se muestra un ejemplo de lista de registro de tiempo de inactividad por mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="53e20-129">The illustration below shows an example of maintenance downtime registration.</span></span>

![Figura 2](media/16-work-orders.png)

<span data-ttu-id="53e20-131">El calendario usado para calcular un registro de tiempo de inactividad por mantenimiento depende de la selección en la configuración de activos y parámetros.</span><span class="sxs-lookup"><span data-stu-id="53e20-131">The calendar that is used to calculate a maintenance downtime registration depends on your selection in the setup of assets and parameters.</span></span> <span data-ttu-id="53e20-132">Si se selecciona un recurso en un activo en el campo **Recurso** de la ficha desplegable **Activo fijo** de la página **Todos los activos** , se utiliza la configuración del calendario para el grupo de recursos asociado, como se muestra en la ilustración siguiente.</span><span class="sxs-lookup"><span data-stu-id="53e20-132">If a resource is selected on an asset in the **Resource** field on the **Fixed asset** FastTab of the **All assets** page, the calendar that is set up for the associated resource group is used, as shown in the following illustration.</span></span>

![Figura 3](media/17-work-orders.png)

<span data-ttu-id="53e20-134">Si no se selecciona ningún recurso en el activo, se utiliza el calendario estándar seleccionado en la página **Parámetros de administración de activos**, como se muestra en la siguiente figura.</span><span class="sxs-lookup"><span data-stu-id="53e20-134">If no resource is selected on the asset, the standard calendar that is selected on the **Asset management parameters** page is used, as shown in the following illustration.</span></span>

![Figura 4](media/18-work-orders.png)

<span data-ttu-id="53e20-136">Haga clic en **Administración de activos de la empresa** > **Consultas** > **Tiempo de inactividad por mantenimiento** para obtener una visión general de todos los registros de tiempo de inactividad por mantenimiento.</span><span class="sxs-lookup"><span data-stu-id="53e20-136">To see an overview of all maintenance downtime registrations, click **Asset management** > **Inquiries** > **Maintenance downtime**.</span></span>

>[!NOTE]
><span data-ttu-id="53e20-137">Todos los calendarios utilizados en el módulo **Administración de activos** se configuran en **Administración de la organización** > **Configuración** > **Calendarios** > **Calendarios**.</span><span class="sxs-lookup"><span data-stu-id="53e20-137">All calendars that are used in the **Asset Management** module are set up in **Organization administration** > **Setup** > **Calendars** > **Calendars**.</span></span>

