---
title: "Sincronizar la información de nivel de inventario desde Finance and Operations a Field Service"
description: "En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar la información de nivel de inventario desde Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service."
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
ms.openlocfilehash: 3ccc4d406fa4f9800dcdf8697a91892408783196
ms.contentlocale: es-es
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-inventory-level-information-from-finance-and-operations-to-field-service"></a><span data-ttu-id="f46d7-103">Sincronizar la información de nivel de inventario desde Finance and Operations a Field Service</span><span class="sxs-lookup"><span data-stu-id="f46d7-103">Synchronize inventory level information from Finance and Operations to Field Service</span></span> 

[!include[banner](../includes/banner.md)]

<span data-ttu-id="f46d7-104">En este tema se describen las plantillas y las tareas subyacentes que se usan para sincronizar la información de nivel de inventario desde Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="f46d7-104">This topic discusses the templates and underlying tasks that are used to synchronize inventory level information from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="f46d7-105">[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span><span class="sxs-lookup"><span data-stu-id="f46d7-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSOnHandOW.png)](./media/FSOnHandOW.png)</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="f46d7-106">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="f46d7-106">Templates and tasks</span></span>
<span data-ttu-id="f46d7-107">La plantilla y las tareas subyacentes siguientes se usan para ejecutar la sincronización de los niveles de inventario disponibles desde Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="f46d7-107">The following template and underlying tasks are used to run synchronization of inventory on-hand levels from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="f46d7-108">**Nombre de la plantilla en la integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="f46d7-108">**Name of the template in Data integration:**</span></span>
- <span data-ttu-id="f46d7-109">Inventario de producto (desde Finance and Operations a Field Service)</span><span class="sxs-lookup"><span data-stu-id="f46d7-109">Product Inventory (Finance and Operations to Field Service)</span></span>
  
<span data-ttu-id="f46d7-110">**Nombres de las tareas en el proyecto de integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="f46d7-110">**Names of the tasks in the Data integration project:**</span></span>
- <span data-ttu-id="f46d7-111">Inventario de producto</span><span class="sxs-lookup"><span data-stu-id="f46d7-111">Product inventory</span></span>

<span data-ttu-id="f46d7-112">Las siguientes tareas de sincronización son necesarias antes de que pueda producirse la sincronización de los niveles de inventario:</span><span class="sxs-lookup"><span data-stu-id="f46d7-112">The following synchronization tasks are required before synchronization of inventory levels can occur:</span></span>
- <span data-ttu-id="f46d7-113">Almacenes (desde Finance and Operations a Field Service)</span><span class="sxs-lookup"><span data-stu-id="f46d7-113">Warehouses (Finance and Operations to Field Service)</span></span> 
- <span data-ttu-id="f46d7-114">Productos de Field Service con unidad Inventario (desde Finance and Operations a Sales)</span><span class="sxs-lookup"><span data-stu-id="f46d7-114">Field Service Products with Inventory unit (Finance and Operations to Sales)</span></span> 

## <a name="entity-set"></a><span data-ttu-id="f46d7-115">Conjunto de entidades</span><span class="sxs-lookup"><span data-stu-id="f46d7-115">Entity set</span></span>

| <span data-ttu-id="f46d7-116">Field Service</span><span class="sxs-lookup"><span data-stu-id="f46d7-116">Field Service</span></span>                      | <span data-ttu-id="f46d7-117">Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f46d7-117">Finance and Operations</span></span>                 |
|------------------------------------|----------------------------------------|
| <span data-ttu-id="f46d7-118">msdynce_externalproductinventories</span><span class="sxs-lookup"><span data-stu-id="f46d7-118">msdynce_externalproductinventories</span></span> | <span data-ttu-id="f46d7-119">Inventario de CDS disponible por almacén</span><span class="sxs-lookup"><span data-stu-id="f46d7-119">CDS inventory on-hand by warehouse</span></span>     |

## <a name="entity-flow"></a><span data-ttu-id="f46d7-120">Flujo de la entidad</span><span class="sxs-lookup"><span data-stu-id="f46d7-120">Entity flow</span></span>
<span data-ttu-id="f46d7-121">La información de nivel de inventario de Finance and Operations se envía a Field Service para productos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="f46d7-121">Inventory level information from Finance and Operation is send to Field Service for selected products.</span></span> <span data-ttu-id="f46d7-122">La información del nivel de inventario incluye:</span><span class="sxs-lookup"><span data-stu-id="f46d7-122">The inventory level information include:</span></span> 
- <span data-ttu-id="f46d7-123">Cantidad disponible (cantidad físicamente registrada actual ubicada en el almacén)</span><span class="sxs-lookup"><span data-stu-id="f46d7-123">On hand quantity (current recorded physically quantity located in the warehouse)</span></span>
- <span data-ttu-id="f46d7-124">Cantidad en pedido (cantidad pedida registrada total - por ejemplo, pedidos de ventas)</span><span class="sxs-lookup"><span data-stu-id="f46d7-124">On order quantity (total recorded quantity on order - i.e. sales orders)</span></span>
- <span data-ttu-id="f46d7-125">Cantidad pedida (cantidad pedida registrada total - por ejemplo, pedidos de compras)</span><span class="sxs-lookup"><span data-stu-id="f46d7-125">Ordered quantity (total recorded ordered quantity - i.e. purchase orders)</span></span>

<span data-ttu-id="f46d7-126">Esta información se captura por producto emitido para cada almacén y se sincroniza basándose en seguimiento de cambios, cuando cambia el nivel de inventario.</span><span class="sxs-lookup"><span data-stu-id="f46d7-126">This information is captured per released product for each warehouse and synchronized based on change tracking, when the inventory level changes.</span></span>

<span data-ttu-id="f46d7-127">En Field Service la solución de integración crea diarios de inventario para el delta, para conseguir que los niveles de Field Service coincidan con los niveles en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f46d7-127">In Field Service the integration solution create inventory journals for the delta, to get the levels in Field Service to match the levels in Finance and Operations.</span></span>

<span data-ttu-id="f46d7-128">Finance and Operations actuará como el maestro de los niveles de inventario.</span><span class="sxs-lookup"><span data-stu-id="f46d7-128">Finance and Operations will act as the master for inventory levels.</span></span> <span data-ttu-id="f46d7-129">Es importante configurar la integración de workorders, las transferencias y los ajustes desde Field Service a Finance and Operations si esta funcionalidad se utiliza en Field Service, junto con la sincronización de los niveles de inventario desde Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f46d7-129">So it is important to setup integration for workorders, transfers and adjustments from Field Service to Finance and Operations if the this functionality is used in Field Service, together with synchronization of inventory levels from Finance and Operations.</span></span>

<span data-ttu-id="f46d7-130">Los productos y los almacenes dónde se han realizado los niveles de inventario se gestionan desde Finance and Operations y se pueden controlar con la consulta y el filtrado avanzados (Power Query).</span><span class="sxs-lookup"><span data-stu-id="f46d7-130">The products and warehouses where inventory levels are mastered from Finance and Operations can be controlled with the Advanced Query and Filtering (Power Query).</span></span>

<span data-ttu-id="f46d7-131">Nota: Es posible crear varios almacenes en Field Services (con Mantenido externamente = No) y después asignarlos a un único almacén en Finance and Operations, con la funcionalidad de consulta y filtrado avanzados.</span><span class="sxs-lookup"><span data-stu-id="f46d7-131">Note: It is possible to create multiple warehouses in Field Services (with Is Externally Maintained = No) and then map them to a single warehouse in Finance and Operations, with the Advanced query and filtering functionality.</span></span> <span data-ttu-id="f46d7-132">Se usa en situaciones en las que desea que Field Service domine el nivel de inventario detallado y sólo envíe actualizaciones a Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f46d7-132">This is used in situations where you want Field service to master the detailed inventory level and just send updates to Finance and Operations.</span></span> <span data-ttu-id="f46d7-133">En este caso Field Service no recibirá actualizaciones del nivel de inventario desde Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f46d7-133">In this case Field service will not receive inventory level updates from Finance and Operations.</span></span> <span data-ttu-id="f46d7-134">Vea información adicional en Sincronizar los ajustes de inventario desde Field Service a Finance and Operations y Sincronizar pedidos de trabajo en Field Service con pedidos de ventas vinculados a proyecto en Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f46d7-134">See additional information in Synchronize inventory adjustments from Field Service to Finance and Operations and Synchronize work orders in Field Service to sales orders linked to project in Finance and Operations.</span></span>

## <a name="field-service-crm-solution"></a><span data-ttu-id="f46d7-135">Solución CRM de Field Service</span><span class="sxs-lookup"><span data-stu-id="f46d7-135">Field Service CRM solution</span></span>
<span data-ttu-id="f46d7-136">La entidad del inventario de productos externos es una nueva entidad que sólo se usa para el servidor en la integración.</span><span class="sxs-lookup"><span data-stu-id="f46d7-136">The External Product Inventory entity is a new entity that’s only used for backend in the integration.</span></span> <span data-ttu-id="f46d7-137">Recibe los valores del nivel de inventario de Finance and Operations en la integración y después transforma estos valores en diarios de inventario manual, que luego cambia los productos de inventario en el almacén.</span><span class="sxs-lookup"><span data-stu-id="f46d7-137">It receives the inventory level values from Finance and Operations in the integration and then transforms those values to Manuel Inventory journals, that then changes the Inventory Products on the Warehouse.</span></span> 

## <a name="prerequisites-and-mapping-setup"></a><span data-ttu-id="f46d7-138">Condiciones previas y configuración de asignación</span><span class="sxs-lookup"><span data-stu-id="f46d7-138">Prerequisites and mapping setup</span></span>

### <a name="in-the-data-integration-project"></a><span data-ttu-id="f46d7-139">En el proyecto de integración de datos</span><span class="sxs-lookup"><span data-stu-id="f46d7-139">In the Data Integration project</span></span>
<span data-ttu-id="f46d7-140">Aplicación de filtros con la consulta y un filtrado avanzado para controlar que sólo los productos y los almacenes deseados envían información del nivel de inventario desde Finance and Operations hasta Field Service.</span><span class="sxs-lookup"><span data-stu-id="f46d7-140">Apply filters with the Advanced  Query and Filtering to control that only desired products and warehouses send inventory level information from Finance and Operations to Field Service.</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="f46d7-141">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="f46d7-141">Template mapping in Data integration</span></span>

### <a name="product-inventory-finance-and-operations-to-field-service-product-inventory"></a><span data-ttu-id="f46d7-142">Inventario de productos (desde Finance and Operations hasta Field Service): inventario de productos</span><span class="sxs-lookup"><span data-stu-id="f46d7-142">Product Inventory (Finance and Operations to Field Service): Product inventory</span></span>

<span data-ttu-id="f46d7-143">[![Asignación de la plantilla en la integración de datos](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span><span class="sxs-lookup"><span data-stu-id="f46d7-143">[![Template mapping in Data integration](./media/FSinventoryLevel1.png)](./media/FSinventoryLevel1.png)</span></span>

