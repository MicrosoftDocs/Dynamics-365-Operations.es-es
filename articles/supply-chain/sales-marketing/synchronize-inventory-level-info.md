---
title: Sincronizar información de nivel de inventario de Supply Chain Management a Field Service
description: En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar información de nivel de inventario de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 05/07/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 1228339c12d26f7b91875d15f0daa8da2869cba0
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215916"
---
# <a name="synchronize-inventory-level-information-from-supply-chain-management-to-field-service"></a><span data-ttu-id="b981c-103">Sincronizar información de nivel de inventario de Supply Chain Management a Field Service</span><span class="sxs-lookup"><span data-stu-id="b981c-103">Synchronize inventory level information from Supply Chain Management to Field Service</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b981c-104">En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar información de nivel de inventario de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="b981c-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory-level information from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="b981c-105">[![Sincronización de procesos empresariales entre Supply Chain Management y Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span><span class="sxs-lookup"><span data-stu-id="b981c-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="b981c-106">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="b981c-106">Templates and tasks</span></span>
<span data-ttu-id="b981c-107">La plantilla siguiente y las tareas subyacentes se usan para sincronizar niveles disponibles de inventario de Supply Chain Management a Field Service.</span><span class="sxs-lookup"><span data-stu-id="b981c-107">The following template and underlying tasks are used to synchronize inventory on-hand levels from Supply Chain Management to Field Service.</span></span>

<span data-ttu-id="b981c-108">**Plantilla en la integración de datos**</span><span class="sxs-lookup"><span data-stu-id="b981c-108">**Template in Data integration**</span></span>
- <span data-ttu-id="b981c-109">Inventario de producto (Supply Chain Management a Field Service)</span><span class="sxs-lookup"><span data-stu-id="b981c-109">Product Inventory (Supply Chain Management to Field Service)</span></span>
  
<span data-ttu-id="b981c-110">**Tarea en el proyecto de integración de datos**</span><span class="sxs-lookup"><span data-stu-id="b981c-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="b981c-111">Inventario de producto</span><span class="sxs-lookup"><span data-stu-id="b981c-111">Product inventory</span></span>

<span data-ttu-id="b981c-112">Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de los niveles de inventario:</span><span class="sxs-lookup"><span data-stu-id="b981c-112">The following synchronization tasks are required before synchronization of inventory levels can occur:</span></span>
- <span data-ttu-id="b981c-113">Almacenes (Supply Chain Management a Field Service)</span><span class="sxs-lookup"><span data-stu-id="b981c-113">Warehouses (Supply Chain Management to Field Service)</span></span> 
- <span data-ttu-id="b981c-114">Productos Field Service con unidad de inventario (Supply Chain Management a Sales)</span><span class="sxs-lookup"><span data-stu-id="b981c-114">Field Service products with Inventory unit (Supply Chain Management to Sales)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="b981c-115">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="b981c-115">Entity set</span></span>

| <span data-ttu-id="b981c-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="b981c-116">Field Service</span></span>                      | <span data-ttu-id="b981c-117">Gestión de la cadena de abastecimiento</span><span class="sxs-lookup"><span data-stu-id="b981c-117">Supply Chain Management</span></span>                |
|------------------------------------|----------------------------------------|
| <span data-ttu-id="b981c-118">msdynce_externalproductinventories</span><span class="sxs-lookup"><span data-stu-id="b981c-118">msdynce_externalproductinventories</span></span> | <span data-ttu-id="b981c-119">Inventario de CDS disponible por almacén</span><span class="sxs-lookup"><span data-stu-id="b981c-119">CDS inventory on-hand by warehouse</span></span>     |

## <a name="entity-flow"></a><span data-ttu-id="b981c-120">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="b981c-120">Entity flow</span></span>
<span data-ttu-id="b981c-121">La información de nivel de inventario de Finance and Operations se envía a Field Service para productos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="b981c-121">Inventory-level information from Finance and Operation is sent to Field Service for selected products.</span></span> <span data-ttu-id="b981c-122">La información del nivel de inventario incluye:</span><span class="sxs-lookup"><span data-stu-id="b981c-122">The inventory-level information includes:</span></span> 
- <span data-ttu-id="b981c-123">Cantidad disponible (cantidad física registrada actual ubicada en el almacén)</span><span class="sxs-lookup"><span data-stu-id="b981c-123">On hand quantity (current recorded physical quantity located in the warehouse)</span></span>
- <span data-ttu-id="b981c-124">Cantidad en pedido (cantidad pedida registrada total, como por ejemplo, pedidos de ventas)</span><span class="sxs-lookup"><span data-stu-id="b981c-124">On order quantity (total recorded quantity on order, such as sales orders)</span></span>
- <span data-ttu-id="b981c-125">Cantidad pedida (cantidad pedida registrada total como por ejemplo, pedidos de compras)</span><span class="sxs-lookup"><span data-stu-id="b981c-125">Ordered quantity (total recorded ordered quantity, such as purchase orders)</span></span>

<span data-ttu-id="b981c-126">Esta información se captura por producto emitido para cada almacén y se sincroniza basándose en seguimiento de cambios, cuando cambia el nivel de inventario.</span><span class="sxs-lookup"><span data-stu-id="b981c-126">This information is captured per released product for each warehouse and synchronized based on change tracking, when the inventory level changes.</span></span>

<span data-ttu-id="b981c-127">En Field Service la solución de integración crea diarios de inventario para el delta, para conseguir que los niveles de Field Service coincidan con los niveles en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b981c-127">In Field Service, the integration solution creates inventory journals for the delta, so that the levels in Field Service match the levels in Supply Chain Management.</span></span>

<span data-ttu-id="b981c-128">Supply Chain Management actuará como el maestro de los niveles de inventario.</span><span class="sxs-lookup"><span data-stu-id="b981c-128">Supply Chain Management will act as the master for inventory levels.</span></span> <span data-ttu-id="b981c-129">Por lo tanto es importante configurar la integración de pedidos de trabajo, las transferencias y los ajustes desde Field Service a Supply Chain Management si esta funcionalidad se utiliza en Field Service, junto con la sincronización de los niveles de inventario desde Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b981c-129">Therefore it is important to set up integration for work orders, transfers, and adjustments from Field Service to Supply Chain Management if this functionality is used in Field Service, together with synchronization of inventory levels from Supply Chain Management.</span></span>

<span data-ttu-id="b981c-130">Los productos y los almacenes dónde se han realizado los niveles de inventario se gestionan desde Supply Chain Management y se pueden controlar con la consulta y el filtrado avanzados (Power Query).</span><span class="sxs-lookup"><span data-stu-id="b981c-130">The products and warehouses where inventory levels are mastered from Supply Chain Management can be controlled with the Advanced Query and Filtering (Power Query).</span></span>

> [!NOTE]
> <span data-ttu-id="b981c-131">Es posible crear varios almacenes en Field Services (con **Se mantiene externamente = No**) y después asignarlos a un único almacén en Supply Chain Management, con la funcionalidad de consulta y filtrado avanzados.</span><span class="sxs-lookup"><span data-stu-id="b981c-131">It is possible to create multiple warehouses in Field Services (with **Is Externally Maintained = No**) and then map them to a single warehouse in Supply Chain Management, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="b981c-132">Se usa en situaciones en las que desea que Field Service domine el nivel de inventario detallado y solo envíe actualizaciones a Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b981c-132">This is used in situations where you want Field Service to master the detailed inventory level and only send updates to Supply Chain Management.</span></span> <span data-ttu-id="b981c-133">En este caso Field Service no recibirá actualizaciones del nivel de inventario desde Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b981c-133">In this case, Field Service will not receive inventory-level updates from Supply Chain Management.</span></span> <span data-ttu-id="b981c-134">Para consultar información adicional, vea [Sincronizar los ajustes de inventario desde Field Service a Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) y [Sincronizar pedidos de trabajo en Field Service con pedidos de ventas vinculados a proyecto en Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="b981c-134">For additional information, see [Synchronize inventory adjustments from Field Service to Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="b981c-135">Solución CRM de Field Service</span><span class="sxs-lookup"><span data-stu-id="b981c-135">Field Service CRM solution</span></span>
<span data-ttu-id="b981c-136">La entidad del **inventario de productos externos** solo se usa para back end en la integración.</span><span class="sxs-lookup"><span data-stu-id="b981c-136">The **External product inventory** entity is only used for back end in to the integration.</span></span> <span data-ttu-id="b981c-137">Esta entidad recibe los valores del nivel de inventario de Supply Chain Management en la integración y después transforma estos valores en diarios de inventario manual, que luego cambia los productos de inventario en el almacén.</span><span class="sxs-lookup"><span data-stu-id="b981c-137">This entity receives the inventory level values from Supply Chain Management in the integration and then transforms those values to Manual inventory journals, which then changes the Inventory products in the Warehouse.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="b981c-138">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="b981c-138">Prerequisites and mapping setup</span></span>

### <a name="data-integration"></a><span data-ttu-id="b981c-139">Integración de datos</span><span class="sxs-lookup"><span data-stu-id="b981c-139">Data integration</span></span>
<span data-ttu-id="b981c-140">Para que funcione el proyecto, debe asegurarse de que la clave de Integración esté actualizada para msdynce_externalproductinventories.</span><span class="sxs-lookup"><span data-stu-id="b981c-140">For the project to work, you need to ensure that the Integration key is updated for msdynce_externalproductinventories.</span></span>
1.  <span data-ttu-id="b981c-141">Vaya a **Integración de datos > Conjuntos de conexión**.</span><span class="sxs-lookup"><span data-stu-id="b981c-141">Go to **Data integration > Connection sets**.</span></span>
2.  <span data-ttu-id="b981c-142">Seleccione el Conjunto de conexión utilizado.</span><span class="sxs-lookup"><span data-stu-id="b981c-142">Select the used Connection set.</span></span>
3.  <span data-ttu-id="b981c-143">En la pestaña **Clave de integración**, asegúrese de que las claves siguientes se agreguen a msdynce_externalproductinventories:</span><span class="sxs-lookup"><span data-stu-id="b981c-143">On the **Integration key** tab, ensure that the following keys are added to msdynce_externalproductinventories:</span></span>
      - <span data-ttu-id="b981c-144">msdynce_productnumber (número de producto)</span><span class="sxs-lookup"><span data-stu-id="b981c-144">msdynce_productnumber (Product Number)</span></span>
      - <span data-ttu-id="b981c-145">msdynce_warehouseid (identificador de almacén)</span><span class="sxs-lookup"><span data-stu-id="b981c-145">msdynce_warehouseid (Warehouse ID)</span></span>
      
### <a name="data-integration-project"></a><span data-ttu-id="b981c-146">Proyecto de integración de datos</span><span class="sxs-lookup"><span data-stu-id="b981c-146">Data integration project</span></span>
<span data-ttu-id="b981c-147">Puede aplicar filtros con la consulta y un filtrado avanzados para que sólo determinados productos y almacenes envíen información del nivel de inventario desde Supply Chain Management hasta Field Service.</span><span class="sxs-lookup"><span data-stu-id="b981c-147">You can apply filters with Advanced Query and Filtering so that only certain products and warehouses send inventory-level information from Supply Chain Management to Field Service.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="b981c-148">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="b981c-148">Template mapping in Data integration</span></span>

### <a name="product-inventory-supply-chain-management-to-field-service-product-inventory"></a><span data-ttu-id="b981c-149">Inventario de producto (Supply Chain Management a Field Service): Inventario de producto</span><span class="sxs-lookup"><span data-stu-id="b981c-149">Product inventory (Supply Chain Management to Field Service): Product inventory</span></span>

<span data-ttu-id="b981c-150">[![Asignación de la plantilla en la integración de datos](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span><span class="sxs-lookup"><span data-stu-id="b981c-150">[![Template mapping in Data integration](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span></span>
