---
title: Sincronizar productos con unidad de inventario de Finance and Operations a Field Service
description: En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar productos con unidades de inventario de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.
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
ms.openlocfilehash: 080672b9a6acd9fd6137580b5b7e14d12cfccf19
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1535868"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a><span data-ttu-id="75fe3-103">Sincronizar productos con unidad de inventario de Finance and Operations a Field Service</span><span class="sxs-lookup"><span data-stu-id="75fe3-103">Synchronize products with inventory unit from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="75fe3-104">En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar productos con unidades de inventario de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="75fe3-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="75fe3-105">[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="75fe3-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="75fe3-106">La plantilla **Productos de Field Service con unidad de inventario (Fin and Ops to Field Service)** usada se basa en la plantilla **Productos deField Service (Fin and Ops to Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="75fe3-106">The used **Field Service Products with Inventory unit (Fin and Ops to Field Service)** template is based on the **Field Service Products (Fin and Ops to Field Service)** template.</span></span> <span data-ttu-id="75fe3-107">Para obtener más información, consulte [Productos de Field Service (de Finance and Operations a Field Service)](field-service-product.md).</span><span class="sxs-lookup"><span data-stu-id="75fe3-107">For more information, see [Field Service Products (Finance and Operations to Field Service)](field-service-product.md).</span></span>

<span data-ttu-id="75fe3-108">Este tema describe sólo las diferencias entre las dos plantillas:</span><span class="sxs-lookup"><span data-stu-id="75fe3-108">This topic only describes the differences between the two templates:</span></span> 
- <span data-ttu-id="75fe3-109">**Productos de Field Service con unidad Inventario (Fin and Ops to Sales)**</span><span class="sxs-lookup"><span data-stu-id="75fe3-109">**Field Service Products with Inventory unit (Fin and Ops to Sales)**</span></span>
- <span data-ttu-id="75fe3-110">**Productos Field Service (Fin and Ops to Field Service)**</span><span class="sxs-lookup"><span data-stu-id="75fe3-110">**Field Service Products (Fin and Ops to Field Service)**</span></span> 

## <a name="templates-and-tasks"></a><span data-ttu-id="75fe3-111">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="75fe3-111">Templates and tasks</span></span>

<span data-ttu-id="75fe3-112">**Nombre de la plantilla en la integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="75fe3-112">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="75fe3-113">Productos de Field Service con unidad Inventario (Fin and Ops to Sales)</span><span class="sxs-lookup"><span data-stu-id="75fe3-113">Field Service Products with Inventory unit (Fin and Ops to Sales)</span></span>

<span data-ttu-id="75fe3-114">**Nombre de la tarea en el proyecto de integración de datos**:</span><span class="sxs-lookup"><span data-stu-id="75fe3-114">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="75fe3-115">Productos</span><span class="sxs-lookup"><span data-stu-id="75fe3-115">Products</span></span>

<span data-ttu-id="75fe3-116">La plantilla **Productos de Field Service con unidad de inventario (Fin and Ops to Field Service)** incluye una asignación que no se incluye en la plantilla **Productos de Field Service (Fin and Ops to Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="75fe3-116">The **Field Service Products with Inventory unit (Fin and Ops to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Fin and Ops to Field Service)** template.</span></span> <span data-ttu-id="75fe3-117">Esta asignación garantiza que la unidad de inventario necesaria para la sincronización de nivel de inventario esté incluida.</span><span class="sxs-lookup"><span data-stu-id="75fe3-117">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="75fe3-118">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="75fe3-118">Template mapping in Data integration</span></span>

<span data-ttu-id="75fe3-119">Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="75fe3-119">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-fin-and-ops-to-field-service-products"></a><span data-ttu-id="75fe3-120">Producto de Field Service con unidad de inventario (Fin and Ops to Field Service): productos</span><span class="sxs-lookup"><span data-stu-id="75fe3-120">Field Service Products with Inventory unit (Fin and Ops to Field Service): Products</span></span>

<span data-ttu-id="75fe3-121">[![Asignación de la plantilla en la integración de datos](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="75fe3-121">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
