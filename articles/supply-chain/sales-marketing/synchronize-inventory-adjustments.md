---
title: Sincronizar las transferencias y los ajustes de inventario desde Field Service a Finance and Operations
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar los ajustes y transferencias de inventario desde Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: 79a1cfac3fa94223cc9af73e758ce95fd47065c9
ms.contentlocale: es-es
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a><span data-ttu-id="1bf63-103">Sincronizar los ajustes de inventario desde Field Service a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1bf63-103">Synchronize inventory adjustments from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="1bf63-104">En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar los ajustes y transferencias de inventario desde Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="1bf63-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory adjustments and transfers from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="1bf63-105">[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span><span class="sxs-lookup"><span data-stu-id="1bf63-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="1bf63-106">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="1bf63-106">Templates and tasks</span></span>
<span data-ttu-id="1bf63-107">La plantilla y las tareas subyacentes siguientes se usan para ejecutar la sincronización de los ajustes y transferencias de inventario desde Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="1bf63-107">The following template and underlying tasks are used to run synchronization of inventory adjustments and transfers from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="1bf63-108">**Nombre de las plantillas en la integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="1bf63-108">**Name of the templates in Data integration:**</span></span>
- <span data-ttu-id="1bf63-109">Ajuste de inventario (desde Field Service a Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="1bf63-109">Inventory Adjustment (Field Service to Finance and Operations)</span></span>
- <span data-ttu-id="1bf63-110">Transferencias de inventario (desde Field Service a Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="1bf63-110">Inventory Transfers (Field Service to Finance and Operations)</span></span>

<span data-ttu-id="1bf63-111">**Nombres de las tareas en los proyectos de integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="1bf63-111">**Names of the tasks in the Data integration projects:**</span></span>
- <span data-ttu-id="1bf63-112">Ajustes de inventario</span><span class="sxs-lookup"><span data-stu-id="1bf63-112">Inventory Adjustments</span></span>
- <span data-ttu-id="1bf63-113">Transferencias de inventario</span><span class="sxs-lookup"><span data-stu-id="1bf63-113">Inventory Transfers</span></span>

## <a name="entity-set"></a><span data-ttu-id="1bf63-114">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="1bf63-114">Entity set</span></span>
| <span data-ttu-id="1bf63-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="1bf63-115">Field Service</span></span>                     | <span data-ttu-id="1bf63-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1bf63-116">Finance and Operations</span></span>                             |
|-----------------------------------|----------------------------------------------------|
| <span data-ttu-id="1bf63-117">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="1bf63-117">msdyn_inventoryadjustmentproducts</span></span> |   <span data-ttu-id="1bf63-118">Encabezados y líneas de diario de ajustes de inventario de CDS</span><span class="sxs-lookup"><span data-stu-id="1bf63-118">CDS Inventory adjustment journal headers and lines</span></span> |
| <span data-ttu-id="1bf63-119">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="1bf63-119">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="1bf63-120">Encabezados y líneas de diario de transferencia de inventario de CDS</span><span class="sxs-lookup"><span data-stu-id="1bf63-120">CDS inventory transfer journal headers and lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="1bf63-121">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="1bf63-121">Entity flow</span></span>
<span data-ttu-id="1bf63-122">Los ajustes y las transferencias de inventario realizados en Field Service se sincronizarán con Finance and Operations una vez que se cambia **Estado de Registrar** de creado a registrado.</span><span class="sxs-lookup"><span data-stu-id="1bf63-122">Inventory adjustments and transfers made in Field Service will synchronize to Finance and Operations, once the **Post status** is changed from Created to Posted.</span></span> <span data-ttu-id="1bf63-123">Cuando esto sucede el pedido de ajuste o transferencia se bloquea y se convierte en de solo lectura, ya que los ajustes y transferencias pueden ser enviados a Finance and Operations y por tanto no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="1bf63-123">When this happen the adjustment or transfer order will be locked and become read-only, as adjustments and transfers might be posted in Finance and Operations and therefor can't be modified.</span></span>
<span data-ttu-id="1bf63-124">En Finance and Operations puede configurar un trabajo por lotes para registrar automáticamente los diarios de inventario de ajustes y transferencias generados con la integración.</span><span class="sxs-lookup"><span data-stu-id="1bf63-124">In Finance and Operations you can setup a batch job to automatically post the adjustments and transfer inventory journals generated with the integration.</span></span> <span data-ttu-id="1bf63-125">Consulte el requisito previo siguiente para obtener información sobre cómo habilitar el trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="1bf63-125">See prerequisite below for details on how to enable the batch job.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="1bf63-126">Solución CRM de Field Service</span><span class="sxs-lookup"><span data-stu-id="1bf63-126">Field Service CRM solution</span></span> 
<span data-ttu-id="1bf63-127">El campo de la unidad de inventario se ha agregado a la entidad del producto.</span><span class="sxs-lookup"><span data-stu-id="1bf63-127">The Inventory Unit field has been added to the Product entity.</span></span> <span data-ttu-id="1bf63-128">Este campo es necesario ya que la unidad de inventario y ventas no siempre es la misma en Operations y para el inventario de almacén en Operations necesitamos la unidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="1bf63-128">This field is needed since the Sales and Inventory Unit is not always the same in Operations, and for the Warehouse Inventory in operations we need the Inventory Unit.</span></span>
<span data-ttu-id="1bf63-129">Cuando establece el producto en un producto de ajuste de inventario para los ajustes y las transferencias de inventario, la unidad se obtendrá del valor producto de inventario de los productos.</span><span class="sxs-lookup"><span data-stu-id="1bf63-129">When you set the Product on an Inventory Adjustment Product for both Inventory Adjustments and Inventory Transfers the Unit will be fetched from the Products Inventory Product value.</span></span> <span data-ttu-id="1bf63-130">Si se encuentra un valor el campo Unidad se bloquea en el producto de ajuste de inventario</span><span class="sxs-lookup"><span data-stu-id="1bf63-130">If a value is found the Unit field will be locked on the Inventory Adjustment Product</span></span>

<span data-ttu-id="1bf63-131">El campo de registro de estado se ha agregado a la entidad de ajuste de inventario y a la entidad de transferencia de inventario.</span><span class="sxs-lookup"><span data-stu-id="1bf63-131">The Post Status field has been added to both the Inventory Adjustment entity and the Inventory Transfer entity.</span></span> <span data-ttu-id="1bf63-132">Este campo se usa como filtro para cuando un ajuste o una transferencia se envía a Operations.</span><span class="sxs-lookup"><span data-stu-id="1bf63-132">This field is used as a filter for when a adjustment or transfer is sent to Operations.</span></span> <span data-ttu-id="1bf63-133">El valor predeterminado pasa a Creado (1) y no se envía a Operations.</span><span class="sxs-lookup"><span data-stu-id="1bf63-133">The field is defaulted to Created (1) and its then not sent over to Operations.</span></span> <span data-ttu-id="1bf63-134">Una vez que lo cambia a Registrado (2) se envía a Operaciones, pero ya no podrá cambiar nada en el ajuste o la transferencia ni agregar cualquier nueva línea.</span><span class="sxs-lookup"><span data-stu-id="1bf63-134">Ones you change is to Posted (2) It is sent over to operations, but you will then no longer be able to change anything in the Adjustment or Transfer or add any new lines to it.</span></span>
<span data-ttu-id="1bf63-135">El campo de secuencia numérica se ha agregado a la entidad del producto de ajuste de inventario.</span><span class="sxs-lookup"><span data-stu-id="1bf63-135">The Number Sequence field has been added to the Inventory Adjustment Product entity.</span></span> <span data-ttu-id="1bf63-136">Este campo ayuda a que la integración tenga un número único, para que la integración sepa cuándo crear y cuándo hacer actualizaciones.</span><span class="sxs-lookup"><span data-stu-id="1bf63-136">This field helps the integration to have a Unique number, so the integration knows when to do creates and when to do updates.</span></span> <span data-ttu-id="1bf63-137">Al crear su primer producto de ajuste de inventario creará un nuevo registro en la entidad P2C AutoNumber para mantener la serie numérica y el prefijo que se usa.</span><span class="sxs-lookup"><span data-stu-id="1bf63-137">When you create your first Inventory Adjustment Product it will create a new record in the P2C AutoNumber entity to maintain the number series and the prefix that is used.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="1bf63-138">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="1bf63-138">Prerequisites and mapping setup</span></span>

### <a name="in-finance-and-operations"></a><span data-ttu-id="1bf63-139">En Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="1bf63-139">In Finance and Operations</span></span>
<span data-ttu-id="1bf63-140">Los diarios de inventario de integración generados mediante la integración se pueden registrar automáticamente con un trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="1bf63-140">The integration inventory journals generated by the integration can automatically be posted with a batch job.</span></span> <span data-ttu-id="1bf63-141">Esto se habilita desde: Gestión del inventario > Tareas periódicas > integración de CDS > Registrar diarios de inventario de integración</span><span class="sxs-lookup"><span data-stu-id="1bf63-141">This is enabled from: Inventory management > Periodic tasks > CDS integration > Post integration inventory journals</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="1bf63-142">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="1bf63-142">Template mapping in Data integration</span></span>

<span data-ttu-id="1bf63-143">Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="1bf63-143">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="inventory-adjustment-field-service-to-finance-and-operations-inventory-adjustment"></a><span data-ttu-id="1bf63-144">Ajuste de inventario (desde Field Service a Finance and Operations): ajuste de inventario</span><span class="sxs-lookup"><span data-stu-id="1bf63-144">Inventory Adjustment (Field Service to Finance and Operations): Inventory Adjustment</span></span>

<span data-ttu-id="1bf63-145">[![Asignación de la plantilla en la integración de datos](./media/FSAdj1.png)](./media/FSAdj1.png)</span><span class="sxs-lookup"><span data-stu-id="1bf63-145">[![Template mapping in Data integration](./media/FSAdj1.png)](./media/FSAdj1.png)</span></span>


### <a name="inventory-transfer-field-service-to-finance-and-operations-inventory-transfer"></a><span data-ttu-id="1bf63-146">Transferencia de inventario (desde Field Service a Finance and Operations): transferencia de inventario</span><span class="sxs-lookup"><span data-stu-id="1bf63-146">Inventory Transfer (Field Service to Finance and Operations): Inventory Transfer</span></span>

<span data-ttu-id="1bf63-147">[![Asignación de la plantilla en la integración de datos](./media/FSTrans1.png)](./media/FSTrans1.png)</span><span class="sxs-lookup"><span data-stu-id="1bf63-147">[![Template mapping in Data integration](./media/FSTrans1.png)](./media/FSTrans1.png)</span></span>

