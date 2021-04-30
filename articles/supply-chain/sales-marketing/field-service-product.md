---
title: Sincronizar productos de Supply Chain Management con productos de Field Service
description: En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar productos de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.
author: ChristianRytt
ms.date: 04/09/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 45a989604d829db715756b6cd206a5675a18acf2
ms.sourcegitcommit: 34b478f175348d99df4f2f0c2f6c0c21b6b2660a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/16/2021
ms.locfileid: "5910000"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a><span data-ttu-id="2d943-103">Sincronizar productos de Supply Chain Management con productos de Field Service</span><span class="sxs-lookup"><span data-stu-id="2d943-103">Synchronize products in Supply Chain Management to products in Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2d943-104">En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar productos de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="2d943-104">This topic discusses the templates and underlying task that are used to synchronize products from Dynamics 365 Supply Chain Management to Dynamics 365  Field Service.</span></span>

<span data-ttu-id="2d943-105">La plantilla **Productos de Field Service (Supply Chain Management a Field Service)** usada se basa en la plantilla **Productos (Supply Chain Management a Sales) – Direct** del cliente potencial para cobrar.</span><span class="sxs-lookup"><span data-stu-id="2d943-105">The used **Field Service Products (Supply Chain Management to Field Service)** template is based on the **Products (Supply Chain Management to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="2d943-106">Para obtener más información, consulte [Productos (Supply Chain Management a Sales) – Directo](/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="2d943-106">For more information, see [Products (Supply Chain Management to Sales) – Direct](/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="2d943-107">El tema solo describe las diferencias entre las plantillas **Productos de Field Service (Supply Chain Management a Field Service)** y **Productos (Supply Chain Management a Sales) – Direct**.</span><span class="sxs-lookup"><span data-stu-id="2d943-107">This topic only describes the differences between the **Field Service Products (Supply Chain Management to Field Service)** and **Products (Supply Chain Management to Sales) – Direct** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="2d943-108">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="2d943-108">Templates and tasks</span></span>

<span data-ttu-id="2d943-109">**Nombre de la plantilla en la integración de datos**</span><span class="sxs-lookup"><span data-stu-id="2d943-109">**Name of the template in Data integration**</span></span>

- <span data-ttu-id="2d943-110">Productos de Field Service (Supply Chain Management a Field Service)</span><span class="sxs-lookup"><span data-stu-id="2d943-110">Field Service Products (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="2d943-111">**Nombre de la tarea en el proyecto de integración de datos**</span><span class="sxs-lookup"><span data-stu-id="2d943-111">**Name of the task in the Data integration project**</span></span>

- <span data-ttu-id="2d943-112">Productos - productos</span><span class="sxs-lookup"><span data-stu-id="2d943-112">Products - Products</span></span>

<span data-ttu-id="2d943-113">La plantilla **Productos de Field Service (Supply Chain Management a Field Service)** incluye un tipo de asignación que no se incluye en plantilla **Productos (Supply Chain Management a Sales) – Direct**.</span><span class="sxs-lookup"><span data-stu-id="2d943-113">The **Field Service Products (Supply Chain Management to Field Service)** template includes one mapping that isn't included in the **Products (Supply Chain Management to Sales) – Direct** template.</span></span> <span data-ttu-id="2d943-114">Esta asignación garantiza que el campo Field Service- específico **Tipo de producto de servicio** esté establecido correctamente.</span><span class="sxs-lookup"><span data-stu-id="2d943-114">This mapping ensures that the required Field Service-specific field **Service Product Type** is set correctly.</span></span>

```plaintext
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

<span data-ttu-id="2d943-115">Se usa la siguiente asignación de valores.</span><span class="sxs-lookup"><span data-stu-id="2d943-115">The following value mapping is used.</span></span>

```plaintext
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

<span data-ttu-id="2d943-116">En Supply Chain Management, el valor **Tipo de producto de Field Service** en la entidad de los datos **Productos emitidos vendibles** se calcula del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2d943-116">In Supply Chain Management, the **Field Service product type** value on the **Sellable released products** data entity is calculated as follows:</span></span>

- <span data-ttu-id="2d943-117">El tipo de producto **Inventario:** = Grupo modelo de productos y artículos, producto que se mantiene en existencias = verdadero</span><span class="sxs-lookup"><span data-stu-id="2d943-117">**Inventory:** Product type = Product and Item model group, Stocked product = True</span></span>
- <span data-ttu-id="2d943-118">El tipo de producto **NonInventory:** = Grupo modelo de productos y artículos, producto que se mantiene en existencias = falso</span><span class="sxs-lookup"><span data-stu-id="2d943-118">**NonInventory:** Product type = Product and Item model group, Stocked product = False</span></span>
- <span data-ttu-id="2d943-119">Tipo de producto **Servicio** = Servicio</span><span class="sxs-lookup"><span data-stu-id="2d943-119">**Service:** Product type = Service</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="2d943-120">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="2d943-120">Template mapping in Data integration</span></span>

<span data-ttu-id="2d943-121">Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="2d943-121">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-supply-chain-management-to-field-service-products---products"></a><span data-ttu-id="2d943-122">Productos de Field Service (Supply Chain Management a Field Service): Productos - Productos</span><span class="sxs-lookup"><span data-stu-id="2d943-122">Field Service Products (Supply Chain Management to Field Service): Products - Products</span></span>

<span data-ttu-id="2d943-123">[![Asignación de la plantilla en la integración de datos](./media/FSProduct.png)](./media/FSProduct.png)</span><span class="sxs-lookup"><span data-stu-id="2d943-123">[![Template mapping in Data integration](./media/FSProduct.png)](./media/FSProduct.png)</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]