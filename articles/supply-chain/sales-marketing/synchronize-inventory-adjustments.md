---
title: Sincronizar transferencias y ajustes de inventario de Field Service a Supply Chain Management
description: En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar transferencias y ajustes de inventario de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 04/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: fce407a66c339f2ece4bbc37b30243a2ed172d0a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251898"
---
# <a name="synchronize-inventory-transfers-and-adjustments-from-field-service-to-supply-chain-management"></a><span data-ttu-id="f331c-103">Sincronizar transferencias y ajustes de inventario de Field Service a Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="f331c-103">Synchronize inventory transfers and adjustments from Field Service to Supply Chain Management</span></span>

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="f331c-104">En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar transferencias y ajustes de inventario de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="f331c-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory adjustments and transfers from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="f331c-105">[![Sincronización de procesos empresariales entre Supply Chain Management y Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span><span class="sxs-lookup"><span data-stu-id="f331c-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSTransAdjOW.png)](./media/FSTransAdjOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="f331c-106">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="f331c-106">Templates and tasks</span></span>
<span data-ttu-id="f331c-107">La plantilla siguiente y las tareas subyacentes se usan para sincronizar ajustes y transferencias de inventario de Field Service a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f331c-107">The following template and underlying tasks are used to synchronize inventory adjustments and transfers from Field Service to Supply Chain Management.</span></span>

<span data-ttu-id="f331c-108">**Plantillas en la integración de datos**</span><span class="sxs-lookup"><span data-stu-id="f331c-108">**Templates in Data integration**</span></span>
- <span data-ttu-id="f331c-109">Ajuste de inventario (Field service a Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="f331c-109">Inventory Adjustment (Field Service to Supply Chain Management)</span></span>
- <span data-ttu-id="f331c-110">Transferencias de inventario (Field service a Supply Chain Management)</span><span class="sxs-lookup"><span data-stu-id="f331c-110">Inventory Transfers (Field Service to Supply Chain Management)</span></span>

<span data-ttu-id="f331c-111">**Tareas en los proyectos de integración de datos**</span><span class="sxs-lookup"><span data-stu-id="f331c-111">**Tasks in the Data integration projects**</span></span>
- <span data-ttu-id="f331c-112">Ajustes de inventario</span><span class="sxs-lookup"><span data-stu-id="f331c-112">Inventory Adjustments</span></span>
- <span data-ttu-id="f331c-113">Transferencias de inventario</span><span class="sxs-lookup"><span data-stu-id="f331c-113">Inventory Transfers</span></span>

## <a name="table-set"></a><span data-ttu-id="f331c-114">Conjunto de tablas</span><span class="sxs-lookup"><span data-stu-id="f331c-114">Table set</span></span>
| <span data-ttu-id="f331c-115">Field Service</span><span class="sxs-lookup"><span data-stu-id="f331c-115">Field Service</span></span>                     | <span data-ttu-id="f331c-116">Gestión de la cadena de abastecimiento</span><span class="sxs-lookup"><span data-stu-id="f331c-116">Supply Chain Management</span></span>                          |
|-----------------------------------|----------------------------------------------------|
| <span data-ttu-id="f331c-117">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="f331c-117">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="f331c-118">Encabezados y líneas de diario de ajustes de inventario de Dataverse</span><span class="sxs-lookup"><span data-stu-id="f331c-118">Dataverse Inventory adjustment journal headers and lines</span></span> |
| <span data-ttu-id="f331c-119">msdyn_inventoryadjustmentproducts</span><span class="sxs-lookup"><span data-stu-id="f331c-119">msdyn_inventoryadjustmentproducts</span></span> | <span data-ttu-id="f331c-120">Encabezados y líneas de diario de transferencia de inventario de Dataverse</span><span class="sxs-lookup"><span data-stu-id="f331c-120">Dataverse inventory transfer journal headers and lines</span></span>   |

## <a name="table-flow"></a><span data-ttu-id="f331c-121">Flujo de tabla</span><span class="sxs-lookup"><span data-stu-id="f331c-121">Table flow</span></span>
<span data-ttu-id="f331c-122">Los ajustes y las transferencias de inventario realizados en Field Service se sincronizarán con Supply Chain Management después de que se cambie **Estado de Registrar** de **creado** a **registrado**.</span><span class="sxs-lookup"><span data-stu-id="f331c-122">Inventory adjustments and transfers made in Field Service will synchronize to Supply Chain Management after the **Post status** changes from **Created** to **Posted**.</span></span> <span data-ttu-id="f331c-123">Si esto ocurre, el ajuste o el pedido de transferencia será bloqueado y se convertirá en de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="f331c-123">When this occurs, the adjustment or the transfer order will be locked and become read only.</span></span> <span data-ttu-id="f331c-124">Esto significa que los ajustes y las transferencias se pueden registrar en Supply Chain Management, pero no se pueden modificar.</span><span class="sxs-lookup"><span data-stu-id="f331c-124">This means that adjustments and transfers can be posted in Supply Chain Management, but cannot be modified.</span></span> <span data-ttu-id="f331c-125">En Supply Chain Management puede configurar un trabajo por lotes para registrar automáticamente los diarios de inventario de ajustes y transferencias que se han generado durante la integración.</span><span class="sxs-lookup"><span data-stu-id="f331c-125">In Supply Chain Management, you can set up a batch job to automatically post the adjustments and transfer inventory journals that have been generated during the integration.</span></span> <span data-ttu-id="f331c-126">Consulte los siguientes requisitos previos para obtener información sobre cómo habilitar el trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="f331c-126">See the following prerequisites for details on how to enable the batch job.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="f331c-127">Solución CRM de Field Service</span><span class="sxs-lookup"><span data-stu-id="f331c-127">Field Service CRM solution</span></span> 
<span data-ttu-id="f331c-128">La columna **Unidad de inventario** se ha agregado a la tabla **Producto**.</span><span class="sxs-lookup"><span data-stu-id="f331c-128">The **Inventory unit** column has been added to the **Product** table.</span></span> <span data-ttu-id="f331c-129">Esta columna es necesario ya que la unidad de inventario y ventas no siempre es la misma en Supply Chain Management y la Unidad de inventario es necesaria en el inventario de almacén en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f331c-129">This column is needed because the Sales and Inventory unit is not always the same in Supply Chain Management, and the Inventory Unit is needed for the Warehouse Inventory in Supply Chain Management.</span></span>
<span data-ttu-id="f331c-130">Cuando establece el producto en un producto de ajuste de inventario para los ajustes y las transferencias de inventario, la unidad se obtendrá del valor de producto de inventario.</span><span class="sxs-lookup"><span data-stu-id="f331c-130">When you set the product on an Inventory adjustment product for both Inventory adjustments and Inventory transfers, the unit will be fetched from the inventory product value.</span></span> <span data-ttu-id="f331c-131">Si se encuentra un valor, la columna **Unidad** se bloqueará en el producto de ajuste de inventario.</span><span class="sxs-lookup"><span data-stu-id="f331c-131">If a value is found, the **Unit** column will be locked on the Inventory adjustment product.</span></span>

<span data-ttu-id="f331c-132">La columna de **Publicar estado** se ha agregado a la tabla de **ajuste de inventario** y a la tabla **transferencia de inventario**.</span><span class="sxs-lookup"><span data-stu-id="f331c-132">The **Post status** column has been added to both the **Inventory adjustment** table and the **Inventory transfer** table.</span></span> <span data-ttu-id="f331c-133">Esta columna se usa como filtro cuando un ajuste o una transferencia se envía a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f331c-133">This column is used as a filter when an adjustment or transfer is sent to Supply Chain Management.</span></span> <span data-ttu-id="f331c-134">El valor predeterminado para esta columna es Creado (1), aunque no se envía a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="f331c-134">The default for this column is Created (1), however it is not sent to Supply Chain Management.</span></span> <span data-ttu-id="f331c-135">Cuando actualiza el valor en Registrado (2), este se envía a Supply Chain Management, pero después ya no podrá cambiar el ajuste o la transferencia ni agregar líneas nuevas.</span><span class="sxs-lookup"><span data-stu-id="f331c-135">When you update the value to Posted (2), it is sent to Supply Chain Management, but after that you will no longer be able to change the adjustment or transfer or add new lines.</span></span>

<span data-ttu-id="f331c-136">La columna **secuencia numérica** se ha agregado a la tabla **producto de ajuste de inventario**.</span><span class="sxs-lookup"><span data-stu-id="f331c-136">The **Number sequence** column has been added to the **Inventory adjustment product** table.</span></span> <span data-ttu-id="f331c-137">Esta columna garantiza que la integración tiene un número único, por lo que la integración puede crear y actualizar el ajuste.</span><span class="sxs-lookup"><span data-stu-id="f331c-137">This column ensures that the integration has a unique number, so the integration can create and update the adjustment.</span></span> <span data-ttu-id="f331c-138">Al crear su primer producto de ajuste de inventario creará un nuevo registro en la tabla **P2C AutoNumber** para mantener la serie numérica y el prefijo que se usa.</span><span class="sxs-lookup"><span data-stu-id="f331c-138">When you create your first inventory adjustment product, it will create a new record in the **P2C AutoNumber** table to maintain the number series and the prefix that is used.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="f331c-139">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="f331c-139">Prerequisites and mapping setup</span></span>

### <a name="supply-chain-management"></a><span data-ttu-id="f331c-140">Gestión de la cadena de abastecimiento</span><span class="sxs-lookup"><span data-stu-id="f331c-140">Supply Chain Management</span></span>
<span data-ttu-id="f331c-141">Los diarios de inventario de integración generados mediante la integración se pueden registrar automáticamente mediante un trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="f331c-141">The integration inventory journals generated by the integration can automatically be posted using a batch job.</span></span> <span data-ttu-id="f331c-142">Esto se habilita desde **Gestión del inventario > Tareas periódicas > integración de Dataverse > Registrar diarios de inventario de integración**.</span><span class="sxs-lookup"><span data-stu-id="f331c-142">This is enabled from **Inventory management > Periodic tasks > Dataverse integration > Post integration inventory journals**.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="f331c-143">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="f331c-143">Template mapping in Data integration</span></span>

<span data-ttu-id="f331c-144">Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="f331c-144">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="inventory-adjustment-field-service-to-supply-chain-management-inventory-adjustment"></a><span data-ttu-id="f331c-145">Ajuste de inventario (Field Service a Supply Chain Management): Ajuste de inventario</span><span class="sxs-lookup"><span data-stu-id="f331c-145">Inventory adjustment (Field Service to Supply Chain Management): Inventory adjustment</span></span>

<span data-ttu-id="f331c-146">[![Asignación de la plantilla en la integración de datos](./media/FSAdj1.png)](./media/FSAdj1.png)</span><span class="sxs-lookup"><span data-stu-id="f331c-146">[![Template mapping in Data integration](./media/FSAdj1.png)](./media/FSAdj1.png)</span></span>


### <a name="inventory-transfer-field-service-to-supply-chain-management-inventory-transfer"></a><span data-ttu-id="f331c-147">Transferencia de inventario (Field Service a Supply Chain Management): Transferencia de inventario</span><span class="sxs-lookup"><span data-stu-id="f331c-147">Inventory transfer (Field Service to Supply Chain Management): Inventory transfer</span></span>

<span data-ttu-id="f331c-148">[![Asignación de la plantilla en la integración de datos](./media/FSTrans1.png)](./media/FSTrans1.png)</span><span class="sxs-lookup"><span data-stu-id="f331c-148">[![Template mapping in Data integration](./media/FSTrans1.png)](./media/FSTrans1.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]