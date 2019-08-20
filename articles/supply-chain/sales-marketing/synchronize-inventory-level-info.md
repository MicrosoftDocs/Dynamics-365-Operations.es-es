---
title: Sincronizar la información de nivel de inventario desde Finance and Operations a Field Service
description: En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar información de nivel de inventario de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 05/07/2019
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
ms.openlocfilehash: 6b56eb545f87c31ef30d6a897f48539068583486
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843442"
---
# <a name="synchronize-inventory-level-information-from-finance-and-operations-to-field-service"></a><span data-ttu-id="a8d54-103">Sincronizar información de nivel de inventario de Finance and Operations a Field Service</span><span class="sxs-lookup"><span data-stu-id="a8d54-103">Synchronize inventory level information from Finance and Operations to Field Service</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="a8d54-104">En este tema se describe las plantillas y las tareas subyacentes que se usan para sincronizar información de nivel de inventario de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="a8d54-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory-level information from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="a8d54-105">[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span><span class="sxs-lookup"><span data-stu-id="a8d54-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="a8d54-106">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="a8d54-106">Templates and tasks</span></span>
<span data-ttu-id="a8d54-107">La plantilla siguiente y las tareas subyacentes se usan para sincronizar niveles disponibles de inventario de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="a8d54-107">The following template and underlying tasks are used to synchronize inventory on-hand levels from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="a8d54-108">**Plantilla en la integración de datos**</span><span class="sxs-lookup"><span data-stu-id="a8d54-108">**Template in Data integration**</span></span>
- <span data-ttu-id="a8d54-109">Inventario de productos (Fin and Ops a Field Service)</span><span class="sxs-lookup"><span data-stu-id="a8d54-109">Product Inventory (Fin and Ops to Field Service)</span></span>
  
<span data-ttu-id="a8d54-110">**Tarea en el proyecto de integración de datos**</span><span class="sxs-lookup"><span data-stu-id="a8d54-110">**Task in the Data integration project**</span></span>
- <span data-ttu-id="a8d54-111">Inventario de producto</span><span class="sxs-lookup"><span data-stu-id="a8d54-111">Product inventory</span></span>

<span data-ttu-id="a8d54-112">Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de los niveles de inventario:</span><span class="sxs-lookup"><span data-stu-id="a8d54-112">The following synchronization tasks are required before synchronization of inventory levels can occur:</span></span>
- <span data-ttu-id="a8d54-113">Almacenes (Fin and Ops a Field Service)</span><span class="sxs-lookup"><span data-stu-id="a8d54-113">Warehouses (Fin and Ops to Field Service)</span></span> 
- <span data-ttu-id="a8d54-114">Productos de Field Service con unidad Inventario (Fin and Ops a Sales)</span><span class="sxs-lookup"><span data-stu-id="a8d54-114">Field Service products with Inventory unit (Fin and Ops to Sales)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="a8d54-115">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="a8d54-115">Entity set</span></span>

| <span data-ttu-id="a8d54-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="a8d54-116">Field Service</span></span>                      | <span data-ttu-id="a8d54-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a8d54-117">Finance and Operations</span></span>                 |
|------------------------------------|----------------------------------------|
| <span data-ttu-id="a8d54-118">msdynce_externalproductinventories</span><span class="sxs-lookup"><span data-stu-id="a8d54-118">msdynce_externalproductinventories</span></span> | <span data-ttu-id="a8d54-119">Inventario de CDS disponible por almacén</span><span class="sxs-lookup"><span data-stu-id="a8d54-119">CDS inventory on-hand by warehouse</span></span>     |

## <a name="entity-flow"></a><span data-ttu-id="a8d54-120">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="a8d54-120">Entity flow</span></span>
<span data-ttu-id="a8d54-121">La información de nivel de inventario de Finance and Operations se envía a Field Service para productos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="a8d54-121">Inventory-level information from Finance and Operation is sent to Field Service for selected products.</span></span> <span data-ttu-id="a8d54-122">La información del nivel de inventario incluye:</span><span class="sxs-lookup"><span data-stu-id="a8d54-122">The inventory-level information includes:</span></span> 
- <span data-ttu-id="a8d54-123">Cantidad disponible (cantidad física registrada actual ubicada en el almacén)</span><span class="sxs-lookup"><span data-stu-id="a8d54-123">On hand quantity (current recorded physical quantity located in the warehouse)</span></span>
- <span data-ttu-id="a8d54-124">Cantidad en pedido (cantidad pedida registrada total, como por ejemplo, pedidos de ventas)</span><span class="sxs-lookup"><span data-stu-id="a8d54-124">On order quantity (total recorded quantity on order, such as sales orders)</span></span>
- <span data-ttu-id="a8d54-125">Cantidad pedida (cantidad pedida registrada total como por ejemplo, pedidos de compras)</span><span class="sxs-lookup"><span data-stu-id="a8d54-125">Ordered quantity (total recorded ordered quantity, such as purchase orders)</span></span>

<span data-ttu-id="a8d54-126">Esta información se captura por producto emitido para cada almacén y se sincroniza basándose en seguimiento de cambios, cuando cambia el nivel de inventario.</span><span class="sxs-lookup"><span data-stu-id="a8d54-126">This information is captured per released product for each warehouse and synchronized based on change tracking, when the inventory level changes.</span></span>

<span data-ttu-id="a8d54-127">En Field Service la solución de integración crea diarios de inventario para el delta, para conseguir que los niveles de Field Service coincidan con los niveles en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a8d54-127">In Field Service, the integration solution creates inventory journals for the delta, so that the levels in Field Service match the levels in Finance and Operations.</span></span>

<span data-ttu-id="a8d54-128">Finance and Operations actuará como el maestro de los niveles de inventario.</span><span class="sxs-lookup"><span data-stu-id="a8d54-128">Finance and Operations will act as the master for inventory levels.</span></span> <span data-ttu-id="a8d54-129">Por lo tanto es importante configurar la integración de pedidos de trabajo, las transferencias y los ajustes desde Field Service a Finance and Operations si esta funcionalidad se utiliza en Field Service, junto con la sincronización de los niveles de inventario desde Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a8d54-129">Therefore it is important to set up integration for work orders, transfers, and adjustments from Field Service to Finance and Operations if this functionality is used in Field Service, together with synchronization of inventory levels from Finance and Operations.</span></span>

<span data-ttu-id="a8d54-130">Los productos y los almacenes dónde se han realizado los niveles de inventario se gestionan desde Finance and Operations y se pueden controlar con la consulta y el filtrado avanzados (Power Query).</span><span class="sxs-lookup"><span data-stu-id="a8d54-130">The products and warehouses where inventory levels are mastered from Finance and Operations can be controlled with the Advanced Query and Filtering (Power Query).</span></span>

> [!NOTE]
> <span data-ttu-id="a8d54-131">Es posible crear varios almacenes en Field Services (con **Se mantiene externamente = No**) y después asignarlos a un único almacén en Finance and Operations, con la funcionalidad de consulta y filtrado avanzados.</span><span class="sxs-lookup"><span data-stu-id="a8d54-131">It is possible to create multiple warehouses in Field Services (with **Is Externally Maintained = No**) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="a8d54-132">Se usa en situaciones en las que desea que Field Service domine el nivel de inventario detallado y solo envíe actualizaciones a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a8d54-132">This is used in situations where you want Field Service to master the detailed inventory level and only send updates to Finance and Operations.</span></span> <span data-ttu-id="a8d54-133">En este caso Field Service no recibirá actualizaciones del nivel de inventario desde Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a8d54-133">In this case, Field Service will not receive inventory-level updates from Finance and Operations.</span></span> <span data-ttu-id="a8d54-134">Para consultar información adicional, vea [Sincronizar los ajustes de inventario desde Field Service a Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) y [Sincronizar pedidos de trabajo en Field Service con pedidos de ventas vinculados a proyecto en Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span><span class="sxs-lookup"><span data-stu-id="a8d54-134">For additional information, see [Synchronize inventory adjustments from Field Service to Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/synchronize-inventory-adjustments) and [Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order).</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="a8d54-135">Solución CRM de Field Service</span><span class="sxs-lookup"><span data-stu-id="a8d54-135">Field Service CRM solution</span></span>
<span data-ttu-id="a8d54-136">La entidad del **inventario de productos externos** solo se usa para back end en la integración.</span><span class="sxs-lookup"><span data-stu-id="a8d54-136">The **External product inventory** entity is only used for back end in to the integration.</span></span> <span data-ttu-id="a8d54-137">Esta entidad recibe los valores del nivel de inventario de Finance and Operations en la integración y después transforma estos valores en diarios de inventario manual, que luego cambia los productos de inventario en el almacén.</span><span class="sxs-lookup"><span data-stu-id="a8d54-137">This entity receives the inventory level values from Finance and Operations in the integration and then transforms those values to Manual inventory journals, which then changes the Inventory products in the Warehouse.</span></span>

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="a8d54-138">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="a8d54-138">Prerequisites and mapping setup</span></span>

### <a name="data-integration"></a><span data-ttu-id="a8d54-139">Integración de datos</span><span class="sxs-lookup"><span data-stu-id="a8d54-139">Data integration</span></span>
<span data-ttu-id="a8d54-140">Para que funcione el proyecto, debe asegurarse de que la clave de Integración esté actualizada para msdynce_externalproductinventories.</span><span class="sxs-lookup"><span data-stu-id="a8d54-140">For the project to work, you need to ensure that the Integration key is updated for msdynce_externalproductinventories.</span></span>
1.  <span data-ttu-id="a8d54-141">Vaya a **Integración de datos > Conjuntos de conexión**.</span><span class="sxs-lookup"><span data-stu-id="a8d54-141">Go to **Data integration > Connection sets**.</span></span>
2.  <span data-ttu-id="a8d54-142">Seleccione el Conjunto de conexión utilizado.</span><span class="sxs-lookup"><span data-stu-id="a8d54-142">Select the used Connection set.</span></span>
3.  <span data-ttu-id="a8d54-143">En la pestaña **Clave de integración**, asegúrese de que las claves siguientes se agreguen a msdynce_externalproductinventories:</span><span class="sxs-lookup"><span data-stu-id="a8d54-143">On the **Integration key** tab, ensure that the following keys are added to msdynce_externalproductinventories:</span></span>
      - <span data-ttu-id="a8d54-144">msdynce_productnumber (número de producto)</span><span class="sxs-lookup"><span data-stu-id="a8d54-144">msdynce_productnumber (Product Number)</span></span>
      - <span data-ttu-id="a8d54-145">msdynce_warehouseid (identificador de almacén)</span><span class="sxs-lookup"><span data-stu-id="a8d54-145">msdynce_warehouseid (Warehouse ID)</span></span>
      
### <a name="data-integration-project"></a><span data-ttu-id="a8d54-146">Proyecto de integración de datos</span><span class="sxs-lookup"><span data-stu-id="a8d54-146">Data integration project</span></span>
<span data-ttu-id="a8d54-147">Puede aplicar filtros con la consulta y un filtrado avanzados para que sólo determinados productos y almacenes envíen información del nivel de inventario desde Finance and Operations hasta Field Service.</span><span class="sxs-lookup"><span data-stu-id="a8d54-147">You can apply filters with Advanced Query and Filtering so that only certain products and warehouses send inventory-level information from Finance and Operations to Field Service.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="a8d54-148">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="a8d54-148">Template mapping in Data integration</span></span>

### <a name="product-inventory-fin-and-ops-to-field-service-product-inventory"></a><span data-ttu-id="a8d54-149">Inventario de productos (Fin and Ops a Field Service): inventario de productos</span><span class="sxs-lookup"><span data-stu-id="a8d54-149">Product inventory (Fin and Ops to Field Service): Product inventory</span></span>

<span data-ttu-id="a8d54-150">[![Asignación de la plantilla en la integración de datos](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span><span class="sxs-lookup"><span data-stu-id="a8d54-150">[![Template mapping in Data integration](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span></span>
