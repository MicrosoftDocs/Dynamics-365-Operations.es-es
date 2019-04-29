---
title: Sincronizar almacenes de Finance and Operations a Field Service
description: En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar almacenes de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
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
ms.openlocfilehash: 7e6d7626c00b9d7d98ce872652653c36ce7bc975
ms.sourcegitcommit: a6d385db6636ef2b7fb6b24d37a2160c8d5a3c0f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2019
ms.locfileid: "842542"
---
# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a><span data-ttu-id="496b7-103">Sincronizar almacenes de Finance and Operations a Field Service</span><span class="sxs-lookup"><span data-stu-id="496b7-103">Synchronize warehouses from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="496b7-104">En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar almacenes de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="496b7-104">This topic discusses the templates and underlying tasks that are used to synchronize warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="496b7-105">[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span><span class="sxs-lookup"><span data-stu-id="496b7-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="496b7-106">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="496b7-106">Templates and tasks</span></span>
<span data-ttu-id="496b7-107">Se utilizan la plantilla y las tareas subyacentes siguientes para ejecutar la sincronización de almacenes de Microsoft Dynamics 365 for Finance and Operations en Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="496b7-107">The following template and underlying tasks are used to run synchronization of warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="496b7-108">**Plantilla en la integración de datos**</span><span class="sxs-lookup"><span data-stu-id="496b7-108">**Template in Data integration**</span></span>
- <span data-ttu-id="496b7-109">Almacenes (Fin and Ops a Field Service)</span><span class="sxs-lookup"><span data-stu-id="496b7-109">Warehouses (Fin and Ops to Field Service)</span></span>

<span data-ttu-id="496b7-110">**Tarea en el proyecto de integración de datos**</span><span class="sxs-lookup"><span data-stu-id="496b7-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="496b7-111">Almacén</span><span class="sxs-lookup"><span data-stu-id="496b7-111">Warehouse</span></span>

## <a name="entity-set"></a><span data-ttu-id="496b7-112">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="496b7-112">Entity set</span></span>
| <span data-ttu-id="496b7-113">Field Service</span><span class="sxs-lookup"><span data-stu-id="496b7-113">Field Service</span></span>    | <span data-ttu-id="496b7-114">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="496b7-114">Finance and Operations</span></span>                 |
|------------------|----------------------------------------|
| <span data-ttu-id="496b7-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="496b7-115">msdyn_warehouses</span></span> | <span data-ttu-id="496b7-116">Almacenes</span><span class="sxs-lookup"><span data-stu-id="496b7-116">Warehouses</span></span>                             |

## <a name="entity-flow"></a><span data-ttu-id="496b7-117">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="496b7-117">Entity flow</span></span>
<span data-ttu-id="496b7-118">Los almacenes creados y mantenidos en Finance and Operations se pueden sincronizar con Field Service mediante un proyecto de integración de datos del Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="496b7-118">Warehouses that are created and maintained in Finance and Operations can be synchronized to Field Service via a Common Data Service (CDS) Data integration project.</span></span> <span data-ttu-id="496b7-119">Los almacenes que quiere sincronizar con Field Service se pueden controlar con la consulta y un filtrado avanzado en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="496b7-119">The warehouses that you want to synchronize to Field Service can be controlled with the Advanced query and filtering on the project.</span></span> <span data-ttu-id="496b7-120">Los almacenes que se sincronizan desde Finance and Operations se crean en Field Service con el campo **Se mantienen externamente** establecido en **Sí** y el registro se convierte en solo lectura.</span><span class="sxs-lookup"><span data-stu-id="496b7-120">Warehouses that synchronize from Finance and Operations are created in Field Service with the **Is maintained externally** field set to **Yes** and the record is read only.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="496b7-121">Solución CRM de Field Service</span><span class="sxs-lookup"><span data-stu-id="496b7-121">Field Service CRM solution</span></span>
<span data-ttu-id="496b7-122">Para admitir la integración entre Field Service y Finance and Operations, la funcionalidad adicional de la solución de CRM Field Service es necesaria.</span><span class="sxs-lookup"><span data-stu-id="496b7-122">To support the integration between Field Service and Finance and Operations, additional functionality from the Field Service CRM solution is required.</span></span> <span data-ttu-id="496b7-123">En la solución, el campo **Se mantiene externamente** se ha agregado a la entidad **Almacén (msdyn_warehouses)**.</span><span class="sxs-lookup"><span data-stu-id="496b7-123">In the solution, the **Is Maintained Externally** field has been added to the **Warehouse (msdyn_warehouses)** entity.</span></span> <span data-ttu-id="496b7-124">Este campo ayuda a identificar si el almacén se administra desde Finance and Operations o si solo existe en Field Service.</span><span class="sxs-lookup"><span data-stu-id="496b7-124">This field helps to identify if the warehouse is handled from Finance and Operations or if it only exists in Field Service.</span></span> <span data-ttu-id="496b7-125">Los parámetros de este campos son:</span><span class="sxs-lookup"><span data-stu-id="496b7-125">The settings for this field include:</span></span>
- <span data-ttu-id="496b7-126">**Sí** - El almacén se ha originado en Finance and Operations y no se podrá editar en Sales.</span><span class="sxs-lookup"><span data-stu-id="496b7-126">**Yes** – The warehouse originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="496b7-127">**No** – el almacén se especificó directamente en Field Service y se mantiene aquí.</span><span class="sxs-lookup"><span data-stu-id="496b7-127">**No** – The warehouse was entered directly in Field Service and is maintained here.</span></span>

<span data-ttu-id="496b7-128">El campo **Se mantiene externamente** ayuda a controlar la sincronización de los niveles de inventario, los ajustes, las transferencias y uso en pedidos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="496b7-128">The **Is Externally Maintained** field helps control the synchronization of inventory levels, adjustments, transfers, and usage on work orders.</span></span> <span data-ttu-id="496b7-129">Solo los almacenes con **Se mantiene externamente** establecido en **Sí** se pueden usar para sincronizarse directamente con el mismo almacén en el otro sistema.</span><span class="sxs-lookup"><span data-stu-id="496b7-129">Only warehouses with **Is Externally Maintained** set to **Yes** can be used to synchronize directly to the same warehouse in the other system.</span></span> 

> [!NOTE]
> <span data-ttu-id="496b7-130">Es posible crear varios almacenes en Field Service (con **Se mantiene externamente** = No) y después asignarlos a un único almacén en Finance and Operations, con la funcionalidad de consulta y filtrado avanzados.</span><span class="sxs-lookup"><span data-stu-id="496b7-130">It is possible to create multiple warehouses in Field Service (with **Is Externally Maintained** = No) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="496b7-131">Se usa en situaciones en las que desea que Field Service domine el nivel de inventario detallado y solo envíe actualizaciones a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="496b7-131">This is used in situations where you want Field Service to master the detailed inventory level and just send updates to Finance and Operations.</span></span> <span data-ttu-id="496b7-132">En este caso Field Service no recibirá actualizaciones del nivel de inventario desde Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="496b7-132">In this case, Field Service will not receive inventory-level updates from Finance and Operations.</span></span> <span data-ttu-id="496b7-133">Para consultar información adicional, vea [Sincronizar los ajustes de inventario desde Field Service a Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) y [Sincronizar pedidos de trabajo en Field Service con pedidos de ventas vinculados a proyecto en Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="496b7-133">For additional information, see [Synchronize inventory adjustments from Field Service to Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="496b7-134">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="496b7-134">Prerequisites and mapping setup</span></span>
### <a name="data-integration-project"></a><span data-ttu-id="496b7-135">Proyecto de integración de datos</span><span class="sxs-lookup"><span data-stu-id="496b7-135">Data Integration project</span></span>
<span data-ttu-id="496b7-136">Antes de sincronizar los almacenes asegúrese de actualizar la consulta y el filtrado avanzados en el proyecto para incluir solo los almacenes que desea llevar de Finance and Operations a Field Service.</span><span class="sxs-lookup"><span data-stu-id="496b7-136">Before synchronizing the warehouses, make sure to update the Advanced query and filtering on the project to only include the warehouses that you want to bring from Finance and Operations to Field Service.</span></span> <span data-ttu-id="496b7-137">Tenga en cuenta que necesitará el almacén de Field Service para aplicarlo en pedidos de trabajo, ajustes y transferencias.</span><span class="sxs-lookup"><span data-stu-id="496b7-137">Note that you will need the warehouse in Field Service to apply it on work orders, adjustments, and transfers.</span></span>  

<span data-ttu-id="496b7-138">Para asegurarse de que haya una **clave de integración** para **msdyn_warehouses**:</span><span class="sxs-lookup"><span data-stu-id="496b7-138">To ensure that the **Integration key** exists for **msdyn_warehouses**:</span></span>
1. <span data-ttu-id="496b7-139">Vaya a integración de datos.</span><span class="sxs-lookup"><span data-stu-id="496b7-139">Go to Data Integration.</span></span>
2. <span data-ttu-id="496b7-140">Seleccione la ficha **Conjunto de conexión**.</span><span class="sxs-lookup"><span data-stu-id="496b7-140">Select the **Connection Set** tab.</span></span>
3. <span data-ttu-id="496b7-141">Seleccione el conjunto de conexión utilizado para la sincronización de pedidos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="496b7-141">Select the connection set used for work order synchronization.</span></span>
4. <span data-ttu-id="496b7-142">Seleccione la ficha **Tecla de integración**.</span><span class="sxs-lookup"><span data-stu-id="496b7-142">Select the **Integration key** tab.</span></span>
5. <span data-ttu-id="496b7-143">Busque msdyn_warehouses y confirme que se haya agregado la clave **msdyn_name (nombre)**.</span><span class="sxs-lookup"><span data-stu-id="496b7-143">Find msdyn_warehouses and confirm that the key **msdyn_name (name)** is added.</span></span> <span data-ttu-id="496b7-144">Si no se muestra, agréguela haciendo clic en **Agregar clave** y luego en **Guardar** en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="496b7-144">If it is not shown, add it by clicking **Add key** and then click **Save** at the top of the page.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="496b7-145">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="496b7-145">Template mapping in Data integration</span></span>

<span data-ttu-id="496b7-146">La siguiente ilustración muestra la asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="496b7-146">The following illustration shows the template mapping in Data integration.</span></span>

### <a name="warehouses-fin-and-ops-to-field-service-warehouse"></a><span data-ttu-id="496b7-147">Almacenes (Fin and Ops a Field Service): Almacén</span><span class="sxs-lookup"><span data-stu-id="496b7-147">Warehouses (Fin and Ops to Field Service): Warehouse</span></span>

<span data-ttu-id="496b7-148">[![Asignación de la plantilla en la integración de datos](./media/Warehouse1.png)](./media/Warehouse1.png)</span><span class="sxs-lookup"><span data-stu-id="496b7-148">[![Template mapping in Data integration](./media/Warehouse1.png)](./media/Warehouse1.png)</span></span>
