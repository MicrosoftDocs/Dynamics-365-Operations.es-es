---
title: Sincronizar productos de Finance and Operations con productos de Field Service
description: En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar productos de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 04/09/2018
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
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 3f26240ec289f5ddcc2682e598bbf93f516b99af
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562704"
---
# <a name="synchronize-products-in-finance-and-operations-to-products-in-field-service"></a><span data-ttu-id="93d35-103">Sincronizar productos de Finance and Operations con productos de Field Service</span><span class="sxs-lookup"><span data-stu-id="93d35-103">Synchronize products in Finance and Operations to products in Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="93d35-104">En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar productos de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="93d35-104">This topic discusses the templates and underlying task that are used to synchronize products from Microsoft Dynamics 365 for Finance and Operations to Microsoft Dynamics 365 for Field Service.</span></span>

<span data-ttu-id="93d35-105">La plantilla **Productos de Field Service (Fin and Ops to Field Service)** usada se basa en la plantilla **Productos (Fin and Ops to Sales) – Direct** del cliente potencial para cobrar.</span><span class="sxs-lookup"><span data-stu-id="93d35-105">The used **Field Service Products (Fin and Ops to Field Service)** template is based on the **Products (Fin and Ops to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="93d35-106">Para obtener más información, consulte [Productos (Fin and Ops to Sales) – Direct](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="93d35-106">For more information, see [Products (Fin and Ops to Sales) – Direct](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="93d35-107">El tema solo describe las diferencias entre las plantillas **Productos de Field Service (Fin and Ops to Field Service)** y **Productos (Fin and Ops to Sales) – Direct**.</span><span class="sxs-lookup"><span data-stu-id="93d35-107">This topic only describes the differences between the **Field Service Products (Fin and Ops to Field Service)** and **Products (Fin and Ops to Sales) – Direct** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="93d35-108">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="93d35-108">Templates and tasks</span></span>

<span data-ttu-id="93d35-109">**Nombre de la plantilla en la integración de datos:**</span><span class="sxs-lookup"><span data-stu-id="93d35-109">**Name of the template in Data integration:**</span></span>

- <span data-ttu-id="93d35-110">Productos Field Service (Fin and Ops to Field Service)</span><span class="sxs-lookup"><span data-stu-id="93d35-110">Field Service Products (Fin and Ops to Field Service)</span></span>

<span data-ttu-id="93d35-111">**Nombre de la tarea en el proyecto de integración de datos**:</span><span class="sxs-lookup"><span data-stu-id="93d35-111">**Name of the task in the Data integration project:**</span></span>

- <span data-ttu-id="93d35-112">Productos - productos</span><span class="sxs-lookup"><span data-stu-id="93d35-112">Products - Products</span></span>

<span data-ttu-id="93d35-113">La plantilla **Productos de Field Service (Fin and Ops to Field Service)** incluye una asignación que no está incluida en la plantilla **Productos (Fin and Ops to Sales) – Direct**.</span><span class="sxs-lookup"><span data-stu-id="93d35-113">The **Field Service Products (Fin and Ops to Field Service)** template includes one mapping that isn't included in the **Products (Fin and Ops to Sales) – Direct** template.</span></span> <span data-ttu-id="93d35-114">Esta asignación garantiza que el campo Field Service- específico **Tipo de producto de servicio** esté establecido correctamente.</span><span class="sxs-lookup"><span data-stu-id="93d35-114">This mapping ensures that the required Field Service-specific field **Service Product Type** is set correctly.</span></span>

```
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

<span data-ttu-id="93d35-115">Se usa la siguiente asignación de valores.</span><span class="sxs-lookup"><span data-stu-id="93d35-115">The following value mapping is used.</span></span>

```
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

<span data-ttu-id="93d35-116">En Finance and Operations, el valor **Tipo de producto de Field Service** en la entidad de los datos **Productos emitidos vendibles** se calcula del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="93d35-116">In Finance and Operations, the **Field Service product type** value on the **Sellable released products** data entity is calculated as follows:</span></span>

- <span data-ttu-id="93d35-117">El tipo de producto**Inventario:** = Grupo modelo de productos y artículos, producto que se mantiene en existencias = verdadero</span><span class="sxs-lookup"><span data-stu-id="93d35-117">**Inventory:** Product type = Product and Item model group, Stocked product = True</span></span>
- <span data-ttu-id="93d35-118">El tipo de producto**NonInventory:** = Grupo modelo de productos y artículos, producto que se mantiene en existencias = falso</span><span class="sxs-lookup"><span data-stu-id="93d35-118">**NonInventory:** Product type = Product and Item model group, Stocked product = False</span></span>
- <span data-ttu-id="93d35-119">Tipo de producto **Servicio** = Servicio</span><span class="sxs-lookup"><span data-stu-id="93d35-119">**Service:** Product type = Service</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="93d35-120">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="93d35-120">Template mapping in Data integration</span></span>

<span data-ttu-id="93d35-121">Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="93d35-121">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-fin-and-ops-to-field-service-products---products"></a><span data-ttu-id="93d35-122">Productos de Field Service (de Fin and Ops a Field Service): productos - productos</span><span class="sxs-lookup"><span data-stu-id="93d35-122">Field Service Products (Fin and Ops to Field Service): Products - Products</span></span>

<span data-ttu-id="93d35-123">[![Asignación de la plantilla en la integración de datos](./media/FSProduct.png)](./media/FSProduct.png)</span><span class="sxs-lookup"><span data-stu-id="93d35-123">[![Template mapping in Data integration](./media/FSProduct.png)](./media/FSProduct.png)</span></span>
