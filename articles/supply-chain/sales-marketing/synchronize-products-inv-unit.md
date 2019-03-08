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
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a>Sincronizar productos con unidad de inventario de Finance and Operations a Field Service

[!include[banner](../includes/banner.md)]

En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar productos con unidades de inventario de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.

[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)

La plantilla **Productos de Field Service (Finance and Operations a Field Service)** usada se basa en la plantilla **Productos (Finance and Operations to Sales) – Direct** del cliente potencial para cobrar. Para obtener más información, consulte [Productos (Finance and Operations a Sales) – Directo](products-template-mapping-direct.md).

El tema solo describe las diferencias entre las plantillas **Productos de Field Service (Finance and Operations a Field Service)** y **Productos (Finance and Operations a Sales) – Directo**.

## <a name="templates-and-tasks"></a>Plantillas y tareas

**Nombre de la plantilla en la integración de datos:**

- Productos de Field Service con unidad Inventario (desde Finance and Operations a Sales)

**Nombre de la tarea en el proyecto de integración de datos**:

- Productos

La plantilla **Productos de Field Service con unidad de inventario (Finance and Operations a Field Service)** incluye una asignación que no se incluye en la plantilla **Productos deField Service (Finance and Operations a Field Service)**. Esta asignación garantiza que la unidad de inventario necesaria para la sincronización de nivel de inventario esté incluida.

```
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.

### <a name="field-service-products-with-inventory-unit-finance-and-operations-to-field-service-products"></a>Producto de Field Service con unidad de inventario (Finance and Operations a Field Service): productos

[![Asignación de la plantilla en la integración de datos](./media/FSProduct1.png)](./media/FSProduct1.png)
