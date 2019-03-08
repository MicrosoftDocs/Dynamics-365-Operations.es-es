---
title: Sincronizar productos con unidad de inventario de Finance and Operations a Field Service
description: En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar productos con unidades de inventario de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
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
ms.openlocfilehash: 5d3767c1a499f3d888d8fc2ce06c2837442e39f0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "359253"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a><span data-ttu-id="0f272-103">Sincronizar productos con unidad de inventario de Finance and Operations a Field Service</span><span class="sxs-lookup"><span data-stu-id="0f272-103">Synchronize products with inventory unit from Finance and Operations to Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="0f272-104">En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar productos con unidades de inventario de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="0f272-104">This topic discusses the templates and underlying task that are used to synchronize products with inventory unit from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="0f272-105">[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span><span class="sxs-lookup"><span data-stu-id="0f272-105">[![Synchronization of business processes between Finance and Operations and Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)</span></span>

<span data-ttu-id="0f272-106">La plantilla **Productos de Field Service (Finance and Operations a Field Service)** usada se basa en la plantilla **Productos (Finance and Operations to Sales) – Direct** del cliente potencial para cobrar.</span><span class="sxs-lookup"><span data-stu-id="0f272-106">The used **Field Service Products (Finance and Operations to Field Service)** template is based on the **Products (Finance and Operations to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="0f272-107">Para obtener más información, consulte [Productos (Finance and Operations a Sales) – Directo](products-template-mapping-direct.md).</span><span class="sxs-lookup"><span data-stu-id="0f272-107">For more information, see [Products (Finance and Operations to Sales) – Direct](products-template-mapping-direct.md).</span></span>

<span data-ttu-id="0f272-108">El tema solo describe las diferencias entre las plantillas **Productos de Field Service (Finance and Operations a Field Service)** y **Productos (Finance and Operations a Sales) – Directo**.</span><span class="sxs-lookup"><span data-stu-id="0f272-108">This topic only describes the differences between the **Field Service Products (Finance and Operations to Field Service)** and **Field Service Products (Finance and Operations to Field Service)** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="0f272-109">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="0f272-109">Templates and tasks</span></span>

<span data-ttu-id="0f272-110">**Nombre de la plantilla en la integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="0f272-110">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="0f272-111">Productos de Field Service con unidad Inventario (desde Finance and Operations a Sales)</span><span class="sxs-lookup"><span data-stu-id="0f272-111">Field Service Products with Inventory unit (Finance and Operations to Sales)</span></span>

<span data-ttu-id="0f272-112">**Nombre de la tarea en el proyecto de integración de datos**:</span><span class="sxs-lookup"><span data-stu-id="0f272-112">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="0f272-113">Productos</span><span class="sxs-lookup"><span data-stu-id="0f272-113">Products</span></span>

<span data-ttu-id="0f272-114">La plantilla **Productos de Field Service con unidad de inventario (Finance and Operations a Field Service)** incluye una asignación que no se incluye en la plantilla **Productos deField Service (Finance and Operations a Field Service)**.</span><span class="sxs-lookup"><span data-stu-id="0f272-114">The **Field Service Products with Inventory unit (Finance and Operations to Field Service)** template includes one mapping that isn't included in the **Field Service Products (Finance and Operations to Field Service)** template.</span></span> <span data-ttu-id="0f272-115">Esta asignación garantiza que la unidad de inventario necesaria para la sincronización de nivel de inventario esté incluida.</span><span class="sxs-lookup"><span data-stu-id="0f272-115">This mapping ensures that the Inventory unit needed for inventory level synchronization is included.</span></span>

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="0f272-116">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="0f272-116">Template mapping in Data integration</span></span>

<span data-ttu-id="0f272-117">Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="0f272-117">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-with-inventory-unit-finance-and-operations-to-field-service-products"></a><span data-ttu-id="0f272-118">Producto de Field Service con unidad de inventario (Finance and Operations a Field Service): productos</span><span class="sxs-lookup"><span data-stu-id="0f272-118">Field Service Products with Inventory unit (Finance and Operations to Field Service): Products</span></span>

<span data-ttu-id="0f272-119">[![Asignación de la plantilla en la integración de datos](./media/FSProduct1.png)](./media/FSProduct1.png)</span><span class="sxs-lookup"><span data-stu-id="0f272-119">[![Template mapping in Data integration](./media/FSProduct1.png)](./media/FSProduct1.png)</span></span>
