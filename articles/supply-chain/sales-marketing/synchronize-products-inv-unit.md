---
title: Sincronizar productos con unidad de inventario de Supply Chain Management a Field Service
description: En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar productos con unidades de inventario de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 03/13/2019
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
ms.openlocfilehash: 62ed33d101f7d7e47b560c417dc05e5aecc83478
ms.sourcegitcommit: 137e2bd30f0a85bd2e1baf1cf16b993edd2094f9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2020
ms.locfileid: "3546347"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a><span data-ttu-id="4487d-103">Sincronizar productos con unidad de inventario de Supply Chain Management a Field Service</span><span class="sxs-lookup"><span data-stu-id="4487d-103">Synchronize products with inventory unit from Supply Chain Management to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="4487d-104">En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar productos con unidades de inventario de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="4487d-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Dynamics 365 Supply Chain Management to Dynamics 365 Field Service.</span></span>

<span data-ttu-id="4487d-105">[![Sincronización de procesos empresariales entre Supply Chain Management y Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="4487d-105">[![Synchronization of business processes between Supply Chain Management and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="4487d-106">La plantilla **Productos de Field Service con unidad de inventario (Supply Chain Management a Field Service)** usada se basa en la plantilla **Productos de Field Service (Supply Chain Management a Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="4487d-106">The used **Field Service Products with Inventory unit (Supply Chain Management to Field Service)** template is based on the **Field Service Products (Supply Chain Management to Field Service)** template.</span></span> <span data-ttu-id="4487d-107">Para obtener más información, consulte [Sincronizar productos en Supply Chain Management para productos en Field Service](field-service-product.md).</span><span class="sxs-lookup"><span data-stu-id="4487d-107">For more information, see [Synchronize products in Supply Chain Management to products in Field Service](field-service-product.md).</span></span>

<span data-ttu-id="4487d-108">Este tema describe sólo las diferencias entre las dos plantillas:</span><span class="sxs-lookup"><span data-stu-id="4487d-108">This topic only describes the differences between the two templates:</span></span> 
- <span data-ttu-id="4487d-109">**Productos Field Service con unidad de inventario (Supply Chain Management a Sales)**</span><span class="sxs-lookup"><span data-stu-id="4487d-109">**Field Service Products with Inventory unit (Supply Chain Management to Sales)**</span></span>
- <span data-ttu-id="4487d-110">**Productos de Field Service (Supply Chain Management a Field Service)**</span><span class="sxs-lookup"><span data-stu-id="4487d-110">**Field Service Products (Supply Chain Management to Field Service)**</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="4487d-111">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="4487d-111">Templates and tasks</span></span>

<span data-ttu-id="4487d-112">**Nombre de la plantilla en la integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="4487d-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="4487d-113">Productos Field Service con unidad de inventario (Supply Chain Management a Sales)</span><span class="sxs-lookup"><span data-stu-id="4487d-113">Field Service Products with Inventory unit (Supply Chain Management to Sales)</span></span>

<span data-ttu-id="4487d-114">**Nombre de la tarea en el proyecto de integración de datos**:</span><span class="sxs-lookup"><span data-stu-id="4487d-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="4487d-115">Productos</span><span class="sxs-lookup"><span data-stu-id="4487d-115">Products</span></span>

<span data-ttu-id="4487d-116">La plantilla **Productos de Field Service con unidad de inventario (Supply Chain Management a Field Service)** incluye una asignación que no está incluida en la plantilla **Productos de Field Service (Supply Chain Management a Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="4487d-116">The **Field Service Products with Inventory unit (Supply Chain Management to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Supply Chain Managementto Field Service)** template.</span></span> <span data-ttu-id="4487d-117">Esta asignación garantiza que la unidad de inventario necesaria para la sincronización de nivel de inventario esté incluida.</span><span class="sxs-lookup"><span data-stu-id="4487d-117">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```plaintext
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="4487d-118">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="4487d-118">Template mapping in Data integration</span></span>

<span data-ttu-id="4487d-119">Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="4487d-119">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-supply-chain-management-to-field-service-products"></a><span data-ttu-id="4487d-120">Producto de Field Service con unidad de inventario (Supply Chain Management a Field Service): Productos</span><span class="sxs-lookup"><span data-stu-id="4487d-120">Field Service Products with Inventory unit (Supply Chain Management to Field Service): Products</span></span>

<span data-ttu-id="4487d-121">[![Asignación de la plantilla en la integración de datos](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="4487d-121">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
