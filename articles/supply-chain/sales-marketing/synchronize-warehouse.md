---
title: Sincronizar almacenes de Supply Chain Management a Field Service
description: En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar almacenes de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: b55a0b9e54eabdcdbd3f858cf3725b8fe833f65d
ms.sourcegitcommit: 0099fb24f5f40ff442020b488ef4171836c35c48
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/23/2019
ms.locfileid: "2653403"
---
# <a name="synchronize-warehouses-from-supply-chain-management-to-field-service"></a><span data-ttu-id="68ba4-103">Sincronizar almacenes de Supply Chain Management a Field Service</span><span class="sxs-lookup"><span data-stu-id="68ba4-103">Synchronize warehouses from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="68ba4-104">En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar almacenes de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="68ba4-104">This topic discusses the templates and underlying tasks that are used to synchronize warehouses from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="68ba4-105">[![Sincronización de procesos empresariales entre Supply Chain Management y Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span><span class="sxs-lookup"><span data-stu-id="68ba4-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="68ba4-106">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="68ba4-106">Templates and tasks</span></span>
<span data-ttu-id="68ba4-107">La plantilla siguiente y las tareas subyacentes se usan para ejecutar sincronización de almacenes de Supply Chain Management a Field Service.</span><span class="sxs-lookup"><span data-stu-id="68ba4-107">The following template and underlying tasks are used to run synchronization of warehouses from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="68ba4-108">**Plantilla en la integración de datos**</span><span class="sxs-lookup"><span data-stu-id="68ba4-108">**Template in Data integration**</span></span>
- <span data-ttu-id="68ba4-109">Almacenes (Supply Chain Management a Field Service)</span><span class="sxs-lookup"><span data-stu-id="68ba4-109">Warehouses (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="68ba4-110">**Tarea en el proyecto de integración de datos**</span><span class="sxs-lookup"><span data-stu-id="68ba4-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="68ba4-111">Almacén</span><span class="sxs-lookup"><span data-stu-id="68ba4-111">Warehouse</span></span>

## <a name="entity-set"></a><span data-ttu-id="68ba4-112">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="68ba4-112">Entity set</span></span>
| <span data-ttu-id="68ba4-113">Field Service</span><span class="sxs-lookup"><span data-stu-id="68ba4-113">Field Service</span></span>    | <span data-ttu-id="68ba4-114">Gestión de la cadena de abastecimiento</span><span class="sxs-lookup"><span data-stu-id="68ba4-114">Supply Chain Management</span></span>                 |
|------------------|----------------------------------------|
| <span data-ttu-id="68ba4-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="68ba4-115">msdyn_warehouses</span></span> | <span data-ttu-id="68ba4-116">Almacenes</span><span class="sxs-lookup"><span data-stu-id="68ba4-116">Warehouses</span></span>                             |

## <a name="entity-flow"></a><span data-ttu-id="68ba4-117">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="68ba4-117">Entity flow</span></span>
<span data-ttu-id="68ba4-118">Los almacenes creados y mantenidos en Supply Chain Management se pueden sincronizar con Field Service mediante un proyecto de integración de datos del Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="68ba4-118">Warehouses that are created and maintained in Supply Chain Management can be synchronized to Field Service via a Common Data Service (CDS) Data integration project.</span></span> <span data-ttu-id="68ba4-119">Los almacenes que quiere sincronizar con Field Service se pueden controlar con la consulta y un filtrado avanzado en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="68ba4-119">The warehouses that you want to synchronize to Field Service can be controlled with the Advanced query and filtering on the project.</span></span> <span data-ttu-id="68ba4-120">Los almacenes que se sincronizan desde Supply Chain Management se crean en Field Service con el campo **Se mantienen externamente** establecido en **Sí** y el registro se convierte en solo lectura.</span><span class="sxs-lookup"><span data-stu-id="68ba4-120">Warehouses that synchronize from Supply Chain Management are created in Field Service with the **Is maintained externally** field set to **Yes** and the record is read only.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="68ba4-121">Solución CRM de Field Service</span><span class="sxs-lookup"><span data-stu-id="68ba4-121">Field Service CRM solution</span></span>
<span data-ttu-id="68ba4-122">Para admitir la integración entre Field Service y Supply Chain Management, la funcionalidad adicional de la solución de CRM Field Service es necesaria.</span><span class="sxs-lookup"><span data-stu-id="68ba4-122">To support the integration between Field Service and Supply Chain Management, additional functionality from the Field Service CRM solution is required.</span></span> <span data-ttu-id="68ba4-123">En la solución, el campo **Se mantiene externamente** se ha agregado a la entidad **Almacén (msdyn_warehouses)**.</span><span class="sxs-lookup"><span data-stu-id="68ba4-123">In the solution, the **Is Maintained Externally** field has been added to the **Warehouse (msdyn_warehouses)** entity.</span></span> <span data-ttu-id="68ba4-124">Este campo ayuda a identificar si el almacén se administra desde Supply Chain Management o si solo existe en Field Service.</span><span class="sxs-lookup"><span data-stu-id="68ba4-124">This field helps to identify if the warehouse is handled from Supply Chain Management or if it only exists in Field Service.</span></span> <span data-ttu-id="68ba4-125">Los parámetros de este campos son:</span><span class="sxs-lookup"><span data-stu-id="68ba4-125">The settings for this field include:</span></span>
- <span data-ttu-id="68ba4-126">**Sí** - El almacén se ha originado en Supply Chain Management y no se podrá editar en Sales.</span><span class="sxs-lookup"><span data-stu-id="68ba4-126">**Yes** – The warehouse originated from Supply Chain Management and won't be editable in Sales.</span></span>
- <span data-ttu-id="68ba4-127">**No** – el almacén se especificó directamente en Field Service y se mantiene aquí.</span><span class="sxs-lookup"><span data-stu-id="68ba4-127">**No** – The warehouse was entered directly in Field Service and is maintained here.</span></span>

<span data-ttu-id="68ba4-128">El campo **Se mantiene externamente** ayuda a controlar la sincronización de los niveles de inventario, los ajustes, las transferencias y uso en pedidos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="68ba4-128">The **Is Externally Maintained** field helps control the synchronization of inventory levels, adjustments, transfers, and usage on work orders.</span></span> <span data-ttu-id="68ba4-129">Solo los almacenes con **Se mantiene externamente** establecido en **Sí** se pueden usar para sincronizarse directamente con el mismo almacén en el otro sistema.</span><span class="sxs-lookup"><span data-stu-id="68ba4-129">Only warehouses with **Is Externally Maintained** set to **Yes** can be used to synchronize directly to the same warehouse in the other system.</span></span> 

> [!NOTE]
> <span data-ttu-id="68ba4-130">Es posible crear varios almacenes en Field Service (con **Se mantiene externamente** = No) y después asignarlos a un único almacén, con la funcionalidad de consulta y filtrado avanzados.</span><span class="sxs-lookup"><span data-stu-id="68ba4-130">It is possible to create multiple warehouses in Field Service (with **Is Externally Maintained** = No) and then map them to a single warehouse, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="68ba4-131">Se usa en situaciones en las que desea que Field Service domine el nivel de inventario detallado y solo envíe actualizaciones a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="68ba4-131">This is used in situations where you want Field Service to master the detailed inventory level and just send updates to Supply Chain Management.</span></span> <span data-ttu-id="68ba4-132">En este caso Field Service no recibirá actualizaciones del nivel de inventario desde Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="68ba4-132">In this case, Field Service will not receive inventory-level updates from Supply Chain Management.</span></span> <span data-ttu-id="68ba4-133">Para consultar información adicional, vea [Sincronizar los ajustes de inventario desde Field Service a Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) y [Sincronizar pedidos de trabajo en Field Service con pedidos de ventas vinculados a proyecto en Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="68ba4-133">For additional information, see [Synchronize inventory adjustments from Field Service to Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="68ba4-134">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="68ba4-134">Prerequisites and mapping setup</span></span>
### <a name="data-integration-project"></a><span data-ttu-id="68ba4-135">Proyecto de integración de datos</span><span class="sxs-lookup"><span data-stu-id="68ba4-135">Data Integration project</span></span>
<span data-ttu-id="68ba4-136">Antes de sincronizar los almacenes asegúrese de actualizar la consulta y el filtrado avanzados en el proyecto para incluir solo los almacenes que desea llevar de Supply Chain Management a Field Service.</span><span class="sxs-lookup"><span data-stu-id="68ba4-136">Before synchronizing the warehouses, make sure to update the Advanced query and filtering on the project to only include the warehouses that you want to bring from Supply Chain Management to Field Service.</span></span> <span data-ttu-id="68ba4-137">Tenga en cuenta que necesitará el almacén de Field Service para aplicarlo en pedidos de trabajo, ajustes y transferencias.</span><span class="sxs-lookup"><span data-stu-id="68ba4-137">Note that you will need the warehouse in Field Service to apply it on work orders, adjustments, and transfers.</span></span>  

<span data-ttu-id="68ba4-138">Para asegurarse de que haya una **clave de integración** para **msdyn_warehouses**:</span><span class="sxs-lookup"><span data-stu-id="68ba4-138">To ensure that the **Integration key** exists for **msdyn_warehouses**:</span></span>
1. <span data-ttu-id="68ba4-139">Vaya a integración de datos.</span><span class="sxs-lookup"><span data-stu-id="68ba4-139">Go to Data Integration.</span></span>
2. <span data-ttu-id="68ba4-140">Seleccione la ficha **Conjunto de conexión**.</span><span class="sxs-lookup"><span data-stu-id="68ba4-140">Select the **Connection Set** tab.</span></span>
3. <span data-ttu-id="68ba4-141">Seleccione el conjunto de conexión utilizado para la sincronización de pedidos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="68ba4-141">Select the connection set used for work order synchronization.</span></span>
4. <span data-ttu-id="68ba4-142">Seleccione la ficha **Tecla de integración**.</span><span class="sxs-lookup"><span data-stu-id="68ba4-142">Select the **Integration key** tab.</span></span>
5. <span data-ttu-id="68ba4-143">Busque msdyn_warehouses y confirme que se haya agregado la clave **msdyn_name (nombre)**.</span><span class="sxs-lookup"><span data-stu-id="68ba4-143">Find msdyn_warehouses and confirm that the key **msdyn_name (name)** is added.</span></span> <span data-ttu-id="68ba4-144">Si no se muestra, agréguela haciendo clic en **Agregar clave** y luego en **Guardar** en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="68ba4-144">If it is not shown, add it by clicking **Add key** and then click **Save** at the top of the page.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="68ba4-145">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="68ba4-145">Template mapping in Data integration</span></span>

<span data-ttu-id="68ba4-146">La siguiente ilustración muestra la asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="68ba4-146">The following illustration shows the template mapping in Data integration.</span></span>

### <a name="warehouses-supply-chain-management-to-field-service-warehouse"></a><span data-ttu-id="68ba4-147">Almacenes (Supply Chain Management a Field Service): Almacén</span><span class="sxs-lookup"><span data-stu-id="68ba4-147">Warehouses (Supply Chain Management to Field Service): Warehouse</span></span>

<span data-ttu-id="68ba4-148">[![Asignación de la plantilla en la integración de datos](./media/Warehouse1.png)](./media/Warehouse1.png)</span><span class="sxs-lookup"><span data-stu-id="68ba4-148">[![Template mapping in Data integration](./media/Warehouse1.png)](./media/Warehouse1.png)</span></span>
