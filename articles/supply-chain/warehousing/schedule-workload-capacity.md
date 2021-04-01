---
title: Programar capacidad de la carga de trabajo
description: Este tema explica cómo configurar y programar la capacidad de carga de trabajo para los trabajadores de un almacén o para un almacén completo.
author: MarkusFogelberg
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSWorkloadCapacity
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4eac4838a4df8f1f5863f1ce1895e7aded5fb08b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5239287"
---
# <a name="schedule-workload-capacity"></a><span data-ttu-id="2d336-103">Programar capacidad de la carga de trabajo</span><span class="sxs-lookup"><span data-stu-id="2d336-103">Schedule workload capacity</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2d336-104">Puede programar la capacidad de la carga de trabajo para almacenes y también proyectar las cargas de trabajo actuales y futuras para los trabajadores de los almacenes individuales.</span><span class="sxs-lookup"><span data-stu-id="2d336-104">You can schedule workload capacity for warehouses, and you can also project the current and future workloads for the workers in individual warehouses.</span></span> <span data-ttu-id="2d336-105">Puede proyectar la carga de trabajo para el almacén completo o bien, proyectar la carga de trabajo de forma independiente para las cargas de trabajo entrantes y salientes.</span><span class="sxs-lookup"><span data-stu-id="2d336-105">You can project the workload for the whole warehouse, or you can project the workload separately for incoming and outgoing workloads.</span></span>

<span data-ttu-id="2d336-106">Para proyectar la salida de la carga de trabajo para los almacenes seleccionados, los datos de la programación maestra deben estar disponibles para esos almacenes.</span><span class="sxs-lookup"><span data-stu-id="2d336-106">To project workload output for selected warehouses, master scheduling data must be available for those warehouses.</span></span> <span data-ttu-id="2d336-107">Para obtener más información, consulte [Visión general de planes maestros](../master-planning/master-plans.md).</span><span class="sxs-lookup"><span data-stu-id="2d336-107">For more information, see [Master plans overview](../master-planning/master-plans.md).</span></span>

## <a name="schedule-and-view-workloads-for-a-warehouse"></a><span data-ttu-id="2d336-108">Programar y ver cargas de trabajo para un almacén</span><span class="sxs-lookup"><span data-stu-id="2d336-108">Schedule and view workloads for a warehouse</span></span>

<span data-ttu-id="2d336-109">Para programar la capacidad de la carga de trabajo para un almacén, crea una configuración de carga de trabajo para uno o varios almacenes y, a continuación, asocia la configuración de la carga de trabajo con un plan maestro.</span><span class="sxs-lookup"><span data-stu-id="2d336-109">To schedule workload capacity for a warehouse, you create a workload setup for one or more warehouses, and then associate the workload setup with a master plan.</span></span> <span data-ttu-id="2d336-110">En la configuración de la capacidad de la carga de trabajo, puede definir límites para el peso o el volumen de las transacciones entrantes y salientes.</span><span class="sxs-lookup"><span data-stu-id="2d336-110">In the workload capacity setup, you can define limits for the weight or volume for incoming and outgoing transactions.</span></span> <span data-ttu-id="2d336-111">También puede crear más de una configuración para cada almacén y, a continuación, asociar la configuración a planes maestros individuales.</span><span class="sxs-lookup"><span data-stu-id="2d336-111">You can also create more than one setup for each warehouse and then associate the setup with individual master plans.</span></span> <span data-ttu-id="2d336-112">Por ejemplo, puede usar este enfoque para adaptarse a los cambios estacionales en los recursos.</span><span class="sxs-lookup"><span data-stu-id="2d336-112">For example, you might use this approach to accommodate seasonal changes in the workforce.</span></span>

<span data-ttu-id="2d336-113">Si los trabajadores de un almacén trabajan con transacciones para las cargas de trabajo entrantes y salientes, puede configurar la configuración de la capacidad del almacén para proyectar la carga de trabajo en una vista combinada.</span><span class="sxs-lookup"><span data-stu-id="2d336-113">If the workers for a warehouse work with transactions for both incoming and outgoing workloads, you can configure the warehouse capacity setup so that the workload is projected in a combined view.</span></span>

<span data-ttu-id="2d336-114">Para programar y ver cargas de trabajo para los almacenes, debe completar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="2d336-114">To schedule and view workloads for warehouses, you must complete the following tasks:</span></span>

1. <span data-ttu-id="2d336-115">Cree una configuración de la capacidad de la carga de trabajo y defina límites de la capacidad de la carga de trabajo para uno o varios almacenes.</span><span class="sxs-lookup"><span data-stu-id="2d336-115">Create a workload capacity setup and define workload capacity limits for one or more warehouses.</span></span>
2. <span data-ttu-id="2d336-116">Asociar la configuración de la capacidad de la carga de trabajo con un plan maestro para crear las proyecciones de la carga de trabajo y especificar cuánto tiempo se aplicarán las proyecciones.</span><span class="sxs-lookup"><span data-stu-id="2d336-116">Associate the workload capacity setup with a master plan to create workload projections and specify how long those projections will apply.</span></span>

### <a name="create-a-workload-capacity-setup-for-a-warehouse"></a><span data-ttu-id="2d336-117">Crear una configuración de la capacidad de la carga de trabajo para un almacén</span><span class="sxs-lookup"><span data-stu-id="2d336-117">Create a workload capacity setup for a warehouse</span></span>

1. <span data-ttu-id="2d336-118">Seleccione **Gestión del inventario** \> **Configuración** \> **Supervisión de almacén** \> **Capacidad de la carga de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="2d336-118">Select **Inventory management** \> **Setup** \> **Warehouse monitoring** \> **Workload capacity**.</span></span>
2. <span data-ttu-id="2d336-119">En el Panel de acciones, haga clic en **Nuevo** para crear una configuración de capacidad de carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2d336-119">On the Action Pane, select **New** to create a workload capacity setup.</span></span>
3. <span data-ttu-id="2d336-120">En la ficha **Almacenes**, seleccione **Nuevo** y, a continuación, introduzca valores en la línea para asociar un almacén con la configuración de capacidad de la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2d336-120">On the **Warehouses** FastTab, select **New**, and then enter values on the line to associate a warehouse with the workload capacity setup.</span></span>
4. <span data-ttu-id="2d336-121">Active la casilla de verificación **Carga de trabajo combinada de entrada y salida** si el informe **Capacidad de carga de trabajo** muestra la carga de trabajo total de las transacciones entrantes y salientes en una vista.</span><span class="sxs-lookup"><span data-stu-id="2d336-121">Select the **Combined inbound and outbound workload** check box if the **Workload capacity** report should show the total workload for incoming and outgoing transactions in one view.</span></span>
5. <span data-ttu-id="2d336-122">En la ficha desplegable **Tipos de transacciones**, seleccione los tipos de transacción entrantes y salientes a los que se aplicarán los límites de la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2d336-122">On the **Transaction types** FastTab, select the types of incoming and outgoing transactions that the workload limits will apply to.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2d336-123">Debe seleccionar al menos un tipo de transacción para la carga de trabajo entrante y la carga de trabajo saliente.</span><span class="sxs-lookup"><span data-stu-id="2d336-123">You must select at least one transaction type for both the incoming workload and the outgoing workload.</span></span>

#### <a name="define-limits-for-volume-or-weight"></a><span data-ttu-id="2d336-124">Definir límites de volumen o peso</span><span class="sxs-lookup"><span data-stu-id="2d336-124">Define limits for volume or weight</span></span>

<span data-ttu-id="2d336-125">Puede configurar límites para volumen o peso según la limitación que sea relevante para los recursos de almacén.</span><span class="sxs-lookup"><span data-stu-id="2d336-125">You can set up limits for volume or weight, depending on the limitation that is relevant for the warehouse workforce.</span></span> <span data-ttu-id="2d336-126">Los límites que se especifican se incluyen en la proyección de la capacidad de la carga de trabajo que puede ver en el informe **Capacidad de carga de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="2d336-126">The limits that you specify are included in the workload capacity projection that you can view on the **Workload capacity** report.</span></span>

<span data-ttu-id="2d336-127">En la información de proyecto sobre volumen y peso para artículos, se deben especificar para todos los productos el tipo estándar de volumen de un artículo de inventario y el peso de un artículo de inventario.</span><span class="sxs-lookup"><span data-stu-id="2d336-127">To project information about volume and weight for items, the standard volume of one inventory item and the weight of one inventory item must be specified for all products.</span></span> <span data-ttu-id="2d336-128">Los campos que son obligatorios están disponibles en los siguientes grupos de campos en la ficha desplegable **Administrar inventario** de la página **Detalles de producto emitido** :</span><span class="sxs-lookup"><span data-stu-id="2d336-128">The fields that are required are available in the following field groups on the **Manage inventory** FastTab of the **Released product details** page:</span></span>

- <span data-ttu-id="2d336-129">Tratamiento</span><span class="sxs-lookup"><span data-stu-id="2d336-129">Handling</span></span>
- <span data-ttu-id="2d336-130">Dimensiones físicas</span><span class="sxs-lookup"><span data-stu-id="2d336-130">Physical dimensions</span></span>
- <span data-ttu-id="2d336-131">Medidas de peso</span><span class="sxs-lookup"><span data-stu-id="2d336-131">Weight measurements</span></span>

<span data-ttu-id="2d336-132">Si esta información no se especifica correctamente, recibirá un mensaje al generar el informe **Capacidad de carga de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="2d336-132">If this information isn't specified correctly, you receive a message when you generate the **Workload capacity** report.</span></span> <span data-ttu-id="2d336-133">En el informe, puede explorar en profundidad para identificar la información que falta y que es necesaria para proyectar la carga de trabajo futura.</span><span class="sxs-lookup"><span data-stu-id="2d336-133">From the report, you can then drill down to identify the missing information that is required in order to project the future workload.</span></span>

### <a name="associate-a-workload-capacity-setup-with-a-master-plan"></a><span data-ttu-id="2d336-134">Asociar una configuración de capacidad de la carga de trabajo con un plan maestro</span><span class="sxs-lookup"><span data-stu-id="2d336-134">Associate a workload capacity setup with a master plan</span></span>

1. <span data-ttu-id="2d336-135">Seleccione **Gestión del inventario** \> **Periódico** \> **Programar carga de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="2d336-135">Select **Inventory management** \> **Periodic** \> **Schedule workload**.</span></span>
2. <span data-ttu-id="2d336-136">En el campo **Plan maestro**, seleccione el plan maestro que usarlo para las proyecciones de la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2d336-136">In the **Master plan** field, select the master plan to use for workload projections.</span></span>
3. <span data-ttu-id="2d336-137">En el campo **Número de días**, especifique el número de días que cubre la proyección de la carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2d336-137">In the **Number of days** field, specify the number of days that the workload projection covers.</span></span>
4. <span data-ttu-id="2d336-138">En el campo **Carga de trabajo**, seleccione la configuración de la carga de trabajo para asociarla al plan maestro.</span><span class="sxs-lookup"><span data-stu-id="2d336-138">In the **Workload** field, select the workload setup to associate with the master plan.</span></span>

### <a name="view-workload-capacity"></a><span data-ttu-id="2d336-139">Ver capacidad de la carga de trabajo</span><span class="sxs-lookup"><span data-stu-id="2d336-139">View workload capacity</span></span>

1. <span data-ttu-id="2d336-140">Seleccione **Gestión del inventario** \> **Consultas e informes** \> **Informes de inventario físico** \> **Capacidad de carga de trabajo**.</span><span class="sxs-lookup"><span data-stu-id="2d336-140">Select **Inventory management** \> **Inquiries and reports** \> **Physical inventory reports** \> **Workload capacity**.</span></span>
2. <span data-ttu-id="2d336-141">En el campo **Número de columnas**, especifique el número de columnas que desea mostrar en el informe.</span><span class="sxs-lookup"><span data-stu-id="2d336-141">In the **Number of columns** field, specify the number of columns to show on the report.</span></span>
3. <span data-ttu-id="2d336-142">En el campo **Tipo de pedido**, seleccione **Planificado y confirmado**, **Planificado** o **Confirmado** , para indicar el tipo de pedidos que desea proyectar en el informe.</span><span class="sxs-lookup"><span data-stu-id="2d336-142">In the **Order type** field, select **Planned and confirmed**, **Planned**, or **Confirmed** to indicate the type of orders to project on the report.</span></span>
4. <span data-ttu-id="2d336-143">En el campo **Tipo de carga**, seleccione un tipo de carga para especificar si la capacidad de la carga de trabajo se debe proyectarse para volumen o para peso.</span><span class="sxs-lookup"><span data-stu-id="2d336-143">In the **Load type** field, select a load type to specify whether the workload capacity should be projected for volume or weight.</span></span>
5. <span data-ttu-id="2d336-144">En el campo **Capacidad de carga de trabajo**, seleccione una configuración para la capacidad de carga de trabajo.</span><span class="sxs-lookup"><span data-stu-id="2d336-144">In the **Workload capacity** field, select a workload capacity setup.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]