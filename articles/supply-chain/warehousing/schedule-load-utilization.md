---
title: "Programar utilización de carga"
description: "En este tema se explica cómo configurar y programar la carga para un almacén."
author: MarkusFogelberg
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSSpaceUtilSetup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 15f3735f79671ac41789d39a5473722a5f35fde0
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---

# <a name="schedule-load-utilization"></a><span data-ttu-id="b7a8e-103">Programar utilización de carga</span><span class="sxs-lookup"><span data-stu-id="b7a8e-103">Schedule load utilization</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b7a8e-104">Puede programar la utilización de carga para los tipos de ubicación seleccionados, y además proyectar la utilización de carga actual y futura.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-104">You can schedule load utilization for selected location types, and you can also project the current and future load utilization.</span></span> <span data-ttu-id="b7a8e-105">Puede proyectar la carga para uno o varios sitios, para las unidades de carga (zona o almacén), o para una combinación de una zona y un almacén.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-105">You can project the load for one or more sites, for the load units (zone or warehouse), or for a combination of a zone and a warehouse.</span></span>

## <a name="schedule-and-view-the-load-for-a-warehouse-or-site"></a><span data-ttu-id="b7a8e-106">Programación y ver la carga de un almacén o un sitio</span><span class="sxs-lookup"><span data-stu-id="b7a8e-106">Schedule and view the load for a warehouse or site</span></span>

<span data-ttu-id="b7a8e-107">Para programar la carga para sitios, almacenes o zonas, crea una configuración de utilización de espacio y la asocia con un plan maestro.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-107">To schedule the load for sites, warehouses, or zones, you create a space utilization setup and associate it with a master plan.</span></span>

<span data-ttu-id="b7a8e-108">En la configuración de la utilización de espacio se usan tipos de ubicación, como **Ubicación de almacenaje** y **Ubicación de picking**, para especificar cómo se debe proyectar la utilización del espacio.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-108">In the space utilization setup, you use location types, such as **Bulk location** and **Picking location**, to specify how space utilization should be projected.</span></span> <span data-ttu-id="b7a8e-109">También especifica un modo de carga de almacenamiento, como **Zona**.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-109">You also specify a storage load mode, such as **Zone**.</span></span>

<span data-ttu-id="b7a8e-110">La proyección de la utilización de espacio futura se basa en la información que se calcula en el plan maestro asociado.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-110">The projection of future space utilization is based on information that is calculated on the associated master plan.</span></span> <span data-ttu-id="b7a8e-111">Los planes maestros prevén la planificación de recursos para pedidos entrantes y salientes para producción y operaciones.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-111">Master plans forecast the resource planning for incoming and outgoing orders for production and operations.</span></span> <span data-ttu-id="b7a8e-112">La proyección del espacio disponible se basa en la relación entre la configuración de la utilización del espacio y el plan maestro seleccionado.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-112">The projection of available space is based on the relation between the space utilization setup and the selected master plan.</span></span>

<span data-ttu-id="b7a8e-113">Mediante el modo de carga de almacenamiento que ha seleccionado en la configuración de utilización del espacio, puede especificar si la carga se debe proyectar para cada almacén o zona, o si las proyecciones deben incluir información sobre almacenes y zonas.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-113">By using the storage load mode that you selected in the space utilization setup, you can specify whether the load should be projected for each warehouse or zone, or whether the projections should include information about both warehouses and zones.</span></span> <span data-ttu-id="b7a8e-114">También especifica si las ubicaciones bloqueadas se excluyen del cálculo de la utilización de carga.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-114">You also specify whether blocked locations should be excluded from the calculation of load utilization.</span></span>

<span data-ttu-id="b7a8e-115">Puede proyectar la utilización del espacio generando el informe **Utilización de carga de almacén** .</span><span class="sxs-lookup"><span data-stu-id="b7a8e-115">You can project the space utilization by generating the **Warehouse load utilization** report.</span></span> <span data-ttu-id="b7a8e-116">Cuando genera este informe, puede especificar si la utilización de carga se debe proyectar para cada sitio, entre sitios o para la unidad de carga seleccionada, como zona o almacén.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-116">When you generate this report, you can specify whether the load utilization should be projected for each site, across sites, or for the selected load unit, such as zone or warehouse.</span></span>

### <a name="create-a-space-utilization-setup-for-a-warehouse"></a><span data-ttu-id="b7a8e-117">Crear una configuración de utilización de espacio para un almacén</span><span class="sxs-lookup"><span data-stu-id="b7a8e-117">Create a space utilization setup for a warehouse</span></span>

1. <span data-ttu-id="b7a8e-118">Seleccione **Gestión del inventario** \> **Configuración** \> **Supervisión de almacén** \> **Uso del espacio**.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-118">Select **Inventory management** \> **Setup** \> **Warehouse monitoring** \> **Space utilization**.</span></span>
2. <span data-ttu-id="b7a8e-119">Seleccione **Nuevo** para crear una configuración de uso del espacio.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-119">Select **New** to create a space utilization setup.</span></span> <span data-ttu-id="b7a8e-120">Especificar un id. y un nombre para la nueva configuración</span><span class="sxs-lookup"><span data-stu-id="b7a8e-120">Specify an ID and a name for the new setup.</span></span>
3. <span data-ttu-id="b7a8e-121">En el campo **Modo de carga de almacenamiento**, seleccione si la visión general de la utilización del espacio debe mostrar información por almacén, zona, o almacén y zona.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-121">In the **Storage load mode** field, select whether the overview of space utilization should show information by warehouse, zone, or warehouse and zone.</span></span>
4. <span data-ttu-id="b7a8e-122">Establezca la opción **Excluir ubicaciones bloqueadas** en **Sí** para excluir las ubicaciones de inventario bloqueadas del cálculo de espacio disponible.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-122">Set the **Exclude blocked locations** option to **Yes** to exclude blocked inventory locations from the calculation of available space.</span></span> <span data-ttu-id="b7a8e-123">Puede bloquear una ubicación de inventario para entrada y salida especificando la causa del bloqueo de la ubicación en el campo **Entrada bloqueada** o **Salida bloqueada** en la ficha desplegable **Otros** de la página **Ubicaciones del inventario**.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-123">You can block an inventory location for input and output by specifying a blocking cause for the location in the **Input blocked** or **Output blocked** field on the **Other** FastTab on the **Inventory locations** page.</span></span>
5. <span data-ttu-id="b7a8e-124">En la ficha desplegable **Tipo de ubicación**, seleccione los tipos de ubicación que desea incluir en el cálculo de utilización del espacio.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-124">On the **Location type** FastTab, select the location types to include in the space utilization calculation.</span></span> <span data-ttu-id="b7a8e-125">Debe seleccionar al menos un tipo de ubicación de la proyección.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-125">You must select at least one location type for the projection.</span></span>

### <a name="associate-a-space-utilization-setup-with-a-master-plan"></a><span data-ttu-id="b7a8e-126">Asociar una configuración de utilización de espacio con un plan maestro</span><span class="sxs-lookup"><span data-stu-id="b7a8e-126">Associate a space utilization setup with a master plan</span></span>

1. <span data-ttu-id="b7a8e-127">Seleccione **Gestión del inventario** \> **Tareas periódicas** \> **Programar utilización de carga**.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-127">Select **Inventory management** \> **Periodic tasks** \> **Schedule load utilization**.</span></span>
2. <span data-ttu-id="b7a8e-128">En el campo **Plan maestro**, seleccione un plan maestro.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-128">In the **Master plan** field, select a master plan.</span></span>
3. <span data-ttu-id="b7a8e-129">En el campo **Número de días**, especifique el número de días que desea incluir en la proyección de las cargas de trabajo actuales y futuras.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-129">In the **Number of days** field, specify the number of days to include in the projection of current and future workloads.</span></span>
4. <span data-ttu-id="b7a8e-130">En el campo **Uso del espacio**, seleccione la configuración de la utilización de espacio que desea usar para la proyección de las cargas de trabajo actuales y futuras.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-130">In the **Space utilization** field, select the space utilization setup to use for the projection of current and future workloads.</span></span>

### <a name="specify-the-load-utilization-projection-and-view-information"></a><span data-ttu-id="b7a8e-131">Especificar la proyección de utilización de carga y ver la información</span><span class="sxs-lookup"><span data-stu-id="b7a8e-131">Specify the load utilization projection and view information</span></span>

1. <span data-ttu-id="b7a8e-132">Seleccione **Gestión del inventario** \> **Consultas e informes** \> **Informes de inventario físico** \> **Utilización de carga de almacén**.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-132">Select **Inventory management** \> **Inquiries and reports** \> **Physical inventory reports** \> **Warehouse load utilization**.</span></span>
2. <span data-ttu-id="b7a8e-133">En el campo **Mostrar por**, seleccione el nivel de proyección de utilización del espacio:</span><span class="sxs-lookup"><span data-stu-id="b7a8e-133">In the **Show by** field, select the level of the space utilization projection:</span></span>

    - <span data-ttu-id="b7a8e-134">**Sitio**: proyectar la utilización del espacio para cada sitio.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-134">**Site** – Project the space utilization for each site.</span></span> <span data-ttu-id="b7a8e-135">Esta proyección resulta útil si, por ejemplo, desea ver todos los almacenes para un sitio de manera que pueda equilibrar la utilización de espacio entre los almacenes.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-135">This projection is useful if, for example, you want to view all the warehouses for a site so that you can balance the space utilization between the warehouses.</span></span>
    - <span data-ttu-id="b7a8e-136">**Unidad de carga**: proyectar la utilización del espacio para zonas o almacenes.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-136">**Load unit** – Project the space utilization for zones or warehouses.</span></span> <span data-ttu-id="b7a8e-137">El espacio disponible se proyecta en conformidad con el valor seleccionado en el campo **Modo de carga de almacenamiento** de la página **Uso del espacio** al crear la configuración de la utilización de espacio.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-137">The available space is then projected according to the value that you selected in the **Storage load mode** field on the **Space utilization** page when you created the space utilization setup.</span></span>

3. <span data-ttu-id="b7a8e-138">Siga uno de estos pasos, según el valor seleccionado en el paso anterior:</span><span class="sxs-lookup"><span data-stu-id="b7a8e-138">Follow one of these steps, depending on the value that you selected in the previous step:</span></span>

    - <span data-ttu-id="b7a8e-139">Si seleccionó **Sitio** en el campo **Mostrar por**, el campo **Sitio** está disponible.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-139">If you selected **Site** in the **Show by** field, the **Site** field is available.</span></span> <span data-ttu-id="b7a8e-140">Seleccione uno o varios sitios para incluirlos en la proyección.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-140">Select one or more sites to include in the projection.</span></span>
    - <span data-ttu-id="b7a8e-141">Si seleccionó **Unidad de carga** en el campo **Mostrar por**, el campo **Unidad de carga** está disponible.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-141">If you selected **Load unit** in the **Show by** field, the **Load unit** field is available.</span></span> <span data-ttu-id="b7a8e-142">Seleccione la unidad de carga.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-142">Select the load unit.</span></span>

4. <span data-ttu-id="b7a8e-143">En el campo **Tipo de carga**, seleccione **Volumen** o **Peso** para especificar la unidad operativa de almacén para la que desea proyectar espacio.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-143">In the **Load type** field, select **Volume** or **Weight** to specify the warehouse operating unit to project space for.</span></span>
5. <span data-ttu-id="b7a8e-144">En el campo **Configuración de utilización del espacio**, seleccione la configuración de la utilización del espacio en la que se basará la proyección.</span><span class="sxs-lookup"><span data-stu-id="b7a8e-144">In the **Space utilization setup** field, select the space utilization setup that the projection should be based on.</span></span>

