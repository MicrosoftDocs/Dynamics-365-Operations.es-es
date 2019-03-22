---
title: Sincronizar productos con unidad de inventario de Finance and Operations a Field Service
description: En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar productos con unidades de inventario de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
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
ms.openlocfilehash: 8e421be79fde6103be6344040b6ae6cda0626c5a
ms.sourcegitcommit: d9ed934a142b88340d268fd2bd3753475a3712b0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2019
ms.locfileid: "836311"
---
# <a name="synchronize-products-with-inventory-unit-from-finance-and-operations-to-field-service"></a>Sincronizar productos con unidad de inventario de Finance and Operations a Field Service

[!include[banner](../includes/banner.md)]

En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar productos con unidades de inventario de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.

[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)

La plantilla **Productos de Field Service con unidad de inventario (Finance and Operations a Field Service)** usada se basa en la plantilla **Productos deField Service (Finance and Operations a Field Service)**. Para obtener más información, consulte [Productos de Field Service (de Finance and Operations a Field Service)](field-service-product.md).

Este tema describe sólo las diferencias entre las dos plantillas: 
- **Productos de Field Service con unidad Inventario (desde Finance and Operations a Sales)**
- **Productos de Field Service (de Finance and Operations a Field Service)** 

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
