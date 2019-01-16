---
title: Sincronizar almacenes de Finance and Operations a Field Service
description: En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar almacenes de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 10/10/2018
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
ms.openlocfilehash: eb8ba6051777e27bd44504a8160118e8096b1435
ms.contentlocale: es-es
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-warehouses-from-finance-and-operations-to-field-service"></a><span data-ttu-id="58706-103">Sincronizar almacenes de Finance and Operations a Field Service</span><span class="sxs-lookup"><span data-stu-id="58706-103">Synchronize warehouses from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="58706-104">En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar almacenes de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="58706-104">This topic discusses the templates and underlying tasks that are used to synchronize warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="58706-105">[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span><span class="sxs-lookup"><span data-stu-id="58706-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSWarehouseOW.png)](./media/FSWarehouseOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="58706-106">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="58706-106">Templates and tasks</span></span>
<span data-ttu-id="58706-107">La plantilla y las tareas subyacentes siguientes se usan para ejecutar la sincronización de almacenes desde Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="58706-107">The following template and underlying tasks are used to run synchronization of warehouses from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="58706-108">**Nombre de la plantilla en la integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="58706-108">**Name of the template in Data integration:**</span></span>
- <span data-ttu-id="58706-109">Almacenes (desde Finance and Operations a Field Service)</span><span class="sxs-lookup"><span data-stu-id="58706-109">Warehouses (Finance and Operations to Field Service)</span></span>

<span data-ttu-id="58706-110">**Nombres de las tareas en el proyecto de integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="58706-110">**Names of the tasks in the Data integration project:**</span></span>
- <span data-ttu-id="58706-111">Almacén</span><span class="sxs-lookup"><span data-stu-id="58706-111">Warehouse</span></span>

## <a name="entity-set"></a><span data-ttu-id="58706-112">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="58706-112">Entity set</span></span>
| <span data-ttu-id="58706-113">Field Service</span><span class="sxs-lookup"><span data-stu-id="58706-113">Field Service</span></span>    | <span data-ttu-id="58706-114">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="58706-114">Finance and Operations</span></span>                 |
|------------------|----------------------------------------|
| <span data-ttu-id="58706-115">msdyn_warehouses</span><span class="sxs-lookup"><span data-stu-id="58706-115">msdyn_warehouses</span></span> | <span data-ttu-id="58706-116">Almacenes</span><span class="sxs-lookup"><span data-stu-id="58706-116">Warehouses</span></span>                             |

## <a name="entity-flow"></a><span data-ttu-id="58706-117">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="58706-117">Entity flow</span></span>
<span data-ttu-id="58706-118">Los almacenes creados y mantenidos en Finance and Operations se pueden sincronizar con Field Service mediante un proyecto de integración de datos del Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="58706-118">Warehouses that are created and maintained in Finance and Operations can be synchronized to Field Service via a Common Data Service (CDS) Data integration project.</span></span> <span data-ttu-id="58706-119">Los almacenes deseados que se sincronizan con Field Service se pueden controlar con la consulta y un filtrado avanzado en el proyecto.</span><span class="sxs-lookup"><span data-stu-id="58706-119">The desired warehouses that synchronize to Field Service can be controlled with the Advanced query and filtering on the project.</span></span> <span data-ttu-id="58706-120">Los almacenes que se sincronizan desde Finance and Operations se crean en Field Service con el campo Se mantienen externamente establecido en Sí y el registro se convierte en sólo lectura.</span><span class="sxs-lookup"><span data-stu-id="58706-120">Warehouses that synchronize from Finance and Operations are created in Field Service with the field Is maintained externally set to Yes and the record is made read only.</span></span>
<span data-ttu-id="58706-121">Solución CRM Field Service Para admitir la integración entre Field Service y Finance and Operations, la funcionalidad adicional de la solución de CRM Field Service es necesaria.</span><span class="sxs-lookup"><span data-stu-id="58706-121">Field Service CRM solution To support the integration between Field Service and Finance and Operations, additional functionality from the Field Service CRM solution is required.</span></span> <span data-ttu-id="58706-122">La solución incluye los siguientes cambios.</span><span class="sxs-lookup"><span data-stu-id="58706-122">The solution includes the following changes.</span></span>
<span data-ttu-id="58706-123">El campo **Se mantiene externamente** se ha agregado a la entidad **Almacén (msdyn_warehouses)** .</span><span class="sxs-lookup"><span data-stu-id="58706-123">The field **Is Maintained Externally** has been added to the **Warehouse (msdyn_warehouses)** entity.</span></span> <span data-ttu-id="58706-124">Este campo ayuda a identificar si el almacén se administra desde Operations o si sólo existe en Field Service.</span><span class="sxs-lookup"><span data-stu-id="58706-124">This field helps to identify If the Warehouse is handled from Operations or if It only exists in Field Service.</span></span>
- <span data-ttu-id="58706-125">Sí - El almacén se ha originado en Finance and Operations y no se podrá editar en Sales.</span><span class="sxs-lookup"><span data-stu-id="58706-125">Yes – The warehouse originated from Finance and Operations and won't be editable in Sales.</span></span>
- <span data-ttu-id="58706-126">No – el almacén se especificó directamente en Field Service y se mantiene aquí.</span><span class="sxs-lookup"><span data-stu-id="58706-126">No – The warehouse was entered directly in Field Service and is maintained here.</span></span>

<span data-ttu-id="58706-127">El campo **Se mantiene externamente** ayuda a controlar la sincronización de los niveles de inventario, los ajustes, las transferencias y uso en pedidos de trabajo.</span><span class="sxs-lookup"><span data-stu-id="58706-127">The **Is Externally Maintained** field helps control the synchronization of inventory levels, adjustments, transfers and usage on work orders.</span></span> <span data-ttu-id="58706-128">Solo los almacenes con **Se mantiene externamente** = Sí se pueden usar para sincronizarse directamente con el mismo almacén en el otro sistema.</span><span class="sxs-lookup"><span data-stu-id="58706-128">Only warehouses with **Is Externally Maintained** = Yes can be used to synchronize directly to the same warehouse in the other system.</span></span> 

<span data-ttu-id="58706-129">Nota: Es posible crear varios almacenes en Field Services (con **Mantenido externamente** = No) y después asignarlos a un único almacén en Finance and Operations, con la funcionalidad de consulta y filtrado avanzados.</span><span class="sxs-lookup"><span data-stu-id="58706-129">Note: It is possible to create multiple warehouses in Field Services (with **Is Externally Maintained** = No) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="58706-130">Se usa en situaciones en las que desea que Field Service domine el nivel de inventario detallado y sólo envíe actualizaciones a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="58706-130">This is used in situations where you want Field service to master the detailed inventory level and just send updates to Finance and Operations.</span></span> <span data-ttu-id="58706-131">En este caso Field Service no recibirá actualizaciones del nivel de inventario desde Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="58706-131">In this case Field service will not receive inventory level updates from Finance and Operations.</span></span> <span data-ttu-id="58706-132">Vea información adicional en Sincronizar los ajustes de inventario desde Field Service a Finance and Operations y Sincronizar pedidos de trabajo en Field Service con pedidos de ventas vinculados a proyecto en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="58706-132">See additional information in Synchronize inventory adjustments from Field Service to Finance and Operations and Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="58706-133">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="58706-133">Prerequisites and mapping setup</span></span>
### <a name="in-the-data-integration-project"></a><span data-ttu-id="58706-134">En el proyecto de integración de datos</span><span class="sxs-lookup"><span data-stu-id="58706-134">In the Data Integration project</span></span>
<span data-ttu-id="58706-135">Antes de sincronizar los almacenes asegúrese de actualizar la consulta y el filtrado avanzados en el proyecto para incluir solo los almacenes que desea llevar de Finance and Operations a Field Service.</span><span class="sxs-lookup"><span data-stu-id="58706-135">Before synchronization of the warehouses make sure to update the Advanced query and filtering on the project to only include the warehouses that you want to bring from Finance and Operations to Field Service.</span></span> <span data-ttu-id="58706-136">Tenga en cuenta que necesitará el almacén de Field Service para aplicarlo en pedidos de trabajo, ajustes y transferencias.</span><span class="sxs-lookup"><span data-stu-id="58706-136">Note that you will need the warehouse in Field Service to apply it on work orders, adjustments and transfers.</span></span>  

<span data-ttu-id="58706-137">Asegúrese de que haya una **clave de integración** para **msdyn_warehouses**</span><span class="sxs-lookup"><span data-stu-id="58706-137">Ensure the **Integration key** exist for **msdyn_warehouses**</span></span>
1. <span data-ttu-id="58706-138">Ir a integración de datos</span><span class="sxs-lookup"><span data-stu-id="58706-138">Go to Data Integration</span></span>
2. <span data-ttu-id="58706-139">Seleccione la ficha **Conjunto de conexión**</span><span class="sxs-lookup"><span data-stu-id="58706-139">Select **Connection Set** tab</span></span>
3. <span data-ttu-id="58706-140">Seleccione el conjunto de conexión utilizado para la sincronización de pedidos de trabajo</span><span class="sxs-lookup"><span data-stu-id="58706-140">Select the Connection set used for Work order synchronization</span></span>
4. <span data-ttu-id="58706-141">Seleccione la ficha **Tecla de integración**</span><span class="sxs-lookup"><span data-stu-id="58706-141">Select **Integration key** tab</span></span>
5. <span data-ttu-id="58706-142">Busque msdyn_warehouses y compruebe que se haya agregado la clave **msdyn_name (nombre)**.</span><span class="sxs-lookup"><span data-stu-id="58706-142">Find msdyn_warehouses and check that the key **msdyn_name (name)** is added.</span></span> <span data-ttu-id="58706-143">Si no se muestra, agréguela haciendo clic en **Agregar clave** y en **Guardar** en la parte superior de la página</span><span class="sxs-lookup"><span data-stu-id="58706-143">If it is not shown, add it by click **Add key** and click **Save** in the top of the page</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="58706-144">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="58706-144">Template mapping in Data integration</span></span>

<span data-ttu-id="58706-145">Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="58706-145">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="warehouses-finance-and-operations-to-field-service-warehouse"></a><span data-ttu-id="58706-146">Almacenes (desde Finance and Operations a Field Service): almacén</span><span class="sxs-lookup"><span data-stu-id="58706-146">Warehouses (Finance and Operations to Field Service): Warehouse</span></span>

<span data-ttu-id="58706-147">[![Asignación de la plantilla en la integración de datos](./media/Warehouse1.png)](./media/Warehouse1.png)</span><span class="sxs-lookup"><span data-stu-id="58706-147">[![Template mapping in Data integration](./media/Warehouse1.png)](./media/Warehouse1.png)</span></span>

