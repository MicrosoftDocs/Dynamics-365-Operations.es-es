---
title: Sincronizar productos de Supply Chain Management con productos de Field Service
description: En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar productos de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 04/09/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: ffa0616d51127a024bea526c5926a182c0449971
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996746"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a><span data-ttu-id="2f0aa-103">Sincronizar productos de Supply Chain Management con productos de Field Service</span><span class="sxs-lookup"><span data-stu-id="2f0aa-103">Synchronize products in Supply Chain Management to products in Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="2f0aa-104">En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar productos de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-104">This topic discusses the templates and underlying task that are used to synchronize products from Dynamics 365 Supply Chain Management to Dynamics 365  Field Service.</span></span>

<span data-ttu-id="2f0aa-105">La plantilla **Productos de Field Service (Supply Chain Management a Field Service)** usada se basa en la plantilla **Productos (Supply Chain Management a Sales) – Direct** del cliente potencial para cobrar.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-105">The used **Field Service Products (Supply Chain Management to Field Service)** template is based on the **Products (Supply Chain Management to Sales) – Direct** template from Prospect to Cash.</span></span> <span data-ttu-id="2f0aa-106">Para obtener más información, consulte [Productos (Supply Chain Management a Sales) – Directo](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span><span class="sxs-lookup"><span data-stu-id="2f0aa-106">For more information, see [Products (Supply Chain Management to Sales) – Direct](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).</span></span>

<span data-ttu-id="2f0aa-107">El tema solo describe las diferencias entre las plantillas **Productos de Field Service (Supply Chain Management a Field Service)** y **Productos (Supply Chain Management a Sales) – Direct**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-107">This topic only describes the differences between the **Field Service Products (Supply Chain Management to Field Service)** and **Products (Supply Chain Management to Sales) – Direct** templates.</span></span>

## <a name="templates-and-tasks"></a><span data-ttu-id="2f0aa-108">Plantillas y tareas</span><span class="sxs-lookup"><span data-stu-id="2f0aa-108">Templates and tasks</span></span>

<span data-ttu-id="2f0aa-109">**Nombre de la plantilla en la integración de datos**</span><span class="sxs-lookup"><span data-stu-id="2f0aa-109">**Name of the template in Data integration**</span></span>

- <span data-ttu-id="2f0aa-110">Productos de Field Service (Supply Chain Management a Field Service)</span><span class="sxs-lookup"><span data-stu-id="2f0aa-110">Field Service Products (Supply Chain Management to Field Service)</span></span>

<span data-ttu-id="2f0aa-111">**Nombre de la tarea en el proyecto de integración de datos**</span><span class="sxs-lookup"><span data-stu-id="2f0aa-111">**Name of the task in the Data integration project**</span></span>

- <span data-ttu-id="2f0aa-112">Productos - productos</span><span class="sxs-lookup"><span data-stu-id="2f0aa-112">Products - Products</span></span>

<span data-ttu-id="2f0aa-113">La plantilla **Productos de Field Service (Supply Chain Management a Field Service)** incluye un tipo de asignación que no se incluye en plantilla **Productos (Supply Chain Management a Sales) – Direct**.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-113">The **Field Service Products (Supply Chain Management to Field Service)** template includes one mapping that isn't included in the **Products (Supply Chain Management to Sales) – Direct** template.</span></span> <span data-ttu-id="2f0aa-114">Esta asignación garantiza que el campo Field Service- específico **Tipo de producto de servicio** esté establecido correctamente.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-114">This mapping ensures that the required Field Service-specific field **Service Product Type** is set correctly.</span></span>

```plaintext
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

<span data-ttu-id="2f0aa-115">Se usa la siguiente asignación de valores.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-115">The following value mapping is used.</span></span>

```plaintext
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

<span data-ttu-id="2f0aa-116">En Supply Chain Management, el valor **Tipo de producto de Field Service** en la entidad de los datos **Productos emitidos vendibles** se calcula del modo siguiente:</span><span class="sxs-lookup"><span data-stu-id="2f0aa-116">In Supply Chain Management, the **Field Service product type** value on the **Sellable released products** data entity is calculated as follows:</span></span>

- <span data-ttu-id="2f0aa-117">El tipo de producto **Inventario:** = Grupo modelo de productos y artículos, producto que se mantiene en existencias = verdadero</span><span class="sxs-lookup"><span data-stu-id="2f0aa-117">**Inventory:** Product type = Product and Item model group, Stocked product = True</span></span>
- <span data-ttu-id="2f0aa-118">El tipo de producto **NonInventory:** = Grupo modelo de productos y artículos, producto que se mantiene en existencias = falso</span><span class="sxs-lookup"><span data-stu-id="2f0aa-118">**NonInventory:** Product type = Product and Item model group, Stocked product = False</span></span>
- <span data-ttu-id="2f0aa-119">Tipo de producto **Servicio** = Servicio</span><span class="sxs-lookup"><span data-stu-id="2f0aa-119">**Service:** Product type = Service</span></span>

## <a name="template-mapping-in-data-integration"></a><span data-ttu-id="2f0aa-120">Asignación de la plantilla en la integración de datos</span><span class="sxs-lookup"><span data-stu-id="2f0aa-120">Template mapping in Data integration</span></span>

<span data-ttu-id="2f0aa-121">Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.</span><span class="sxs-lookup"><span data-stu-id="2f0aa-121">The following illustrations show the template mapping in Data integration.</span></span>

### <a name="field-service-products-supply-chain-management-to-field-service-products---products"></a><span data-ttu-id="2f0aa-122">Productos de Field Service (Supply Chain Management a Field Service): Productos - Productos</span><span class="sxs-lookup"><span data-stu-id="2f0aa-122">Field Service Products (Supply Chain Management to Field Service): Products - Products</span></span>

<span data-ttu-id="2f0aa-123">[![Asignación de la plantilla en la integración de datos](./media/FSProduct.png)](./media/FSProduct.png)</span><span class="sxs-lookup"><span data-stu-id="2f0aa-123">[![Template mapping in Data integration](./media/FSProduct.png)](./media/FSProduct.png)</span></span>
