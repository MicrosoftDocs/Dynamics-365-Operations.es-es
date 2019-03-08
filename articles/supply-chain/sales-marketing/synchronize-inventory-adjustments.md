---
title: Sincronizar las transferencias y los ajustes de inventario desde Field Service a Finance and Operations
description: En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar transferencias y ajustes de inventario de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 01/14/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: aa54945cea5821da163e1f6ea1747ac29b31a3ce
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "308377"
---
# <a name="synchronize-inventory-adjustments-from-field-service-to-finance-and-operations"></a><span data-ttu-id="9cb17-103">Sincronizar los ajustes de inventario desde Field Service a Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9cb17-103">Synchronize inventory adjustments from Field Service to Finance and Operations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="9cb17-104">En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar transferencias y ajustes de inventario de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="9cb17-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory adjustments and transfers from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="9cb17-105">[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span><span class="sxs-lookup"><span data-stu-id="9cb17-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="9cb17-106">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="9cb17-106">Templates and tasks</span></span>
<span data-ttu-id="9cb17-107">La plantilla siguiente y las tareas subyacentes se usan para sincronizar transferencias y ajustes de inventario de Microsoft Dynamics 365 for Field Service a Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9cb17-107">The following template and underlying tasks are used to synchronize inventory adjustments and transfers from Microsoft Dynamics 365 for Field Service to Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="9cb17-108">**Plantillas en la integración de datos**</span><span class="sxs-lookup"><span data-stu-id="9cb17-108">**Templates in Data integration**</span></span>
- <span data-ttu-id="9cb17-109">Ajuste de inventario (desde Field Service a Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="9cb17-109">Inventory Adjustment (Field Service to Finance and Operations)</span></span>
- <span data-ttu-id="9cb17-110">Transferencias de inventario (desde Field Service a Finance and Operations)</span><span class="sxs-lookup"><span data-stu-id="9cb17-110">Inventory Transfers (Field Service to Finance and Operations)</span></span>

<span data-ttu-id="9cb17-111">**Tareas en los proyectos de integración de datos**</span><span class="sxs-lookup"><span data-stu-id="9cb17-111">**Tasks in the Data integration projects**</span></span>
- <span data-ttu-id="9cb17-112">Ajustes de inventario</span><span class="sxs-lookup"><span data-stu-id="9cb17-112">Inventory Adjustments</span></span>
- <span data-ttu-id="9cb17-113">Transferencias de inventario</span><span class="sxs-lookup"><span data-stu-id="9cb17-113">Inventory Transfers</span></span>

## <a name="entity-set"></a><span data-ttu-id="9cb17-114">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="9cb17-114">Entity set</span></span>
| <span data-ttu-id="9cb17-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="9cb17-115">Field Service</span></span>                     | <span data-ttu-id="9cb17-116">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9cb17-116">Finance and Operations</span></span>                             |
|-----------------------------------|----------------------------------------------------|
| <span data-ttu-id="9cb17-117">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="9cb17-117">msdyn_inventoryadjustmentproducts</span></span> |   <span data-ttu-id="9cb17-118">Encabezados y líneas de diario de ajustes de inventario de CDS</span><span class="sxs-lookup"><span data-stu-id="9cb17-118">CDS Inventory adjustment journal headers and lines</span></span> |
| <span data-ttu-id="9cb17-119">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="9cb17-119">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="9cb17-120">Encabezados y líneas de diario de transferencia de inventario de CDS</span><span class="sxs-lookup"><span data-stu-id="9cb17-120">CDS inventory transfer journal headers and lines</span></span>   |

## <a name="entity-flow"></a><span data-ttu-id="9cb17-121">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="9cb17-121">Entity flow</span></span>
<span data-ttu-id="9cb17-122">Los ajustes y las transferencias de inventario realizados en Field Service se sincronizarán con Finance and Operations después de que se cambie **Estado de Registrar** de **creado** a **registrado**.</span><span class="sxs-lookup"><span data-stu-id="9cb17-122">Inventory adjustments and transfers made in Field Service will synchronize to Finance and Operations after the **Post status** changes from **Created** to **Posted**.</span></span> <span data-ttu-id="9cb17-123">Si esto ocurre, el ajuste o el pedido de transferencia será bloqueado y se convertirá en de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="9cb17-123">When this occurs, the adjustment or the transfer order will be locked and become read only.</span></span> <span data-ttu-id="9cb17-124">Esto significa que los ajustes y las transferencias se pueden registrar en Finance and Operations, pero no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="9cb17-124">This means that adjustments and transfers can be posted in Finance and Operations, but cannot be modified.</span></span> <span data-ttu-id="9cb17-125">En Finance and Operations puede configurar un trabajo por lotes para registrar automáticamente los diarios de inventario de ajustes y transferencias que se han generado durante la integración.</span><span class="sxs-lookup"><span data-stu-id="9cb17-125">In Finance and Operations, you can set up a batch job to automatically post the adjustments and transfer inventory journals that have been generated during the integration.</span></span> <span data-ttu-id="9cb17-126">Consulte los siguientes requisitos previos para obtener información sobre cómo habilitar el trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="9cb17-126">See the following prerequisites for details on how to enable the batch job.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="9cb17-127">Solución CRM de Field Service</span><span class="sxs-lookup"><span data-stu-id="9cb17-127">Field Service CRM solution</span></span> 
<span data-ttu-id="9cb17-128">El campo **unidad de inventario** se ha agregado a la entidad **Producto**.</span><span class="sxs-lookup"><span data-stu-id="9cb17-128">The **Inventory unit** field has been added to the **Product** entity.</span></span> <span data-ttu-id="9cb17-129">Este campo es necesario ya que la unidad de inventario y ventas no siempre es la misma en Finance and Operations y la unidad de inventario es necesaria en el inventario de almacén en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9cb17-129">This field is needed because the Sales and Inventory unit is not always the same in Finance and Operations, and the Inventory Unit is needed for the Warehouse Inventory in Finance and Operations.</span></span>
<span data-ttu-id="9cb17-130">Cuando establece el producto en un producto de ajuste de inventario para los ajustes y las transferencias de inventario, la unidad se obtendrá del valor de producto de inventario.</span><span class="sxs-lookup"><span data-stu-id="9cb17-130">When you set the product on an Inventory adjustment product for both Inventory adjustments and Inventory transfers, the unit will be fetched from the inventory product value.</span></span> <span data-ttu-id="9cb17-131">Si se encuentra un valor el campo **Unidad** se bloquea en el producto de ajuste de inventario.</span><span class="sxs-lookup"><span data-stu-id="9cb17-131">If a value is found, the **Unit** field will be locked on the Inventory adjustment product.</span></span>

<span data-ttu-id="9cb17-132">El campo de **registro de estado** se ha agregado a la entidad de **ajuste de inventario** y a la entidad de **transferencia de inventario**.</span><span class="sxs-lookup"><span data-stu-id="9cb17-132">The **Post status** field has been added to both the **Inventory adjustment** entity and the **Inventory transfer** entity.</span></span> <span data-ttu-id="9cb17-133">Este campo se usa como filtro cuando un ajuste o una transferencia se envía a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9cb17-133">This field is used as a filter when an adjustment or transfer is sent to Finance and Operations.</span></span> <span data-ttu-id="9cb17-134">El valor predeterminado para este campo es Creado (1), aunque no se envía a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9cb17-134">The default for this field is Created (1), however it is not sent to Finance and Operations.</span></span> <span data-ttu-id="9cb17-135">Cuando actualiza el valor en Registrado (2), este se envía a Finance and Operations, pero después ya no podrá cambiar el ajuste o la transferencia ni agregar líneas nuevas.</span><span class="sxs-lookup"><span data-stu-id="9cb17-135">When you update the value to Posted (2), it is sent to Finance and Operations, but after that you will no longer be able to change the adjustment or transfer or add new lines.</span></span>

<span data-ttu-id="9cb17-136">El campo de **secuencia numérica** se ha agregado a la entidad del **producto de ajuste de inventario**.</span><span class="sxs-lookup"><span data-stu-id="9cb17-136">The **Number sequence** field has been added to the **Inventory adjustment product** entity.</span></span> <span data-ttu-id="9cb17-137">Este campo garantiza que la integración tiene un número único, por lo que la integración puede crear y actualizar el ajuste.</span><span class="sxs-lookup"><span data-stu-id="9cb17-137">This field ensures that the integration has a unique number, so the integration can create and update the adjustment.</span></span> <span data-ttu-id="9cb17-138">Al crear su primer producto de ajuste de inventario creará un nuevo registro en la entidad **P2C AutoNumber** para mantener la serie numérica y el prefijo que se usa.</span><span class="sxs-lookup"><span data-stu-id="9cb17-138">When you create your first inventory adjustment product, it will create a new record in the **P2C AutoNumber** entity to maintain the number series and the prefix that is used.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="9cb17-139">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="9cb17-139">Prerequisites and mapping setup</span></span>

### <a name="finance-and-operations"></a><span data-ttu-id="9cb17-140">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="9cb17-140">Finance and Operations</span></span>
<span data-ttu-id="9cb17-141">Los diarios de inventario de integración generados mediante la integración se pueden registrar automáticamente mediante un trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="9cb17-141">The integration inventory journals generated by the integration can automatically be posted using a batch job.</span></span> <span data-ttu-id="9cb17-142">Esto se habilita desde: **Gestión del inventario > Tareas periódicas > integración de CDS > Registrar diarios de inventario de integración**.</span><span class="sxs-lookup"><span data-stu-id="9cb17-142">This is enabled from **Inventory management > Periodic tasks > CDS integration > Post integration inventory journals**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="9cb17-143">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="9cb17-143">Template mapping in Data integration</span></span>

<span data-ttu-id="9cb17-144">Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="9cb17-144">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="inventory-adjustment-field-service-to-finance-and-operations-inventory-adjustment"></a><span data-ttu-id="9cb17-145">Ajuste de inventario (desde Field Service a Finance and Operations): ajuste de inventario</span><span class="sxs-lookup"><span data-stu-id="9cb17-145">Inventory adjustment (Field Service to Finance and Operations): Inventory adjustment</span></span>

<span data-ttu-id="9cb17-146">[![Asignación de la plantilla en la integración de datos](./media/FSAdj1.png)](./media/FSAdj1.png)</span><span class="sxs-lookup"><span data-stu-id="9cb17-146">[![Template mapping in Data integration](./media/FSAdj1.png)](./media/FSAdj1.png)</span></span>


### <a name="inventory-transfer-field-service-to-finance-and-operations-inventory-transfer"></a><span data-ttu-id="9cb17-147">Transferencia de inventario (desde Field Service a Finance and Operations): transferencia de inventario</span><span class="sxs-lookup"><span data-stu-id="9cb17-147">Inventory transfer (Field Service to Finance and Operations): Inventory transfer</span></span>

<span data-ttu-id="9cb17-148">[![Asignación de la plantilla en la integración de datos](./media/FSTrans1.png)](./media/FSTrans1.png)</span><span class="sxs-lookup"><span data-stu-id="9cb17-148">[![Template mapping in Data integration](./media/FSTrans1.png)](./media/FSTrans1.png)</span></span>
