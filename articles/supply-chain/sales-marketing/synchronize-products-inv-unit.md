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
ms.openlocfilehash: 911c5cc79ae359bbb77d31f366ccfeabf282a33e
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436997"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a>Sincronizar productos con unidad de inventario de Supply Chain Management a Field Service

[!include[banner](../includes/banner.md)]

En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar productos con unidades de inventario de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.

[![Sincronización de procesos empresariales entre Supply Chain Management y Field Service](./media/FSProductsOW.png)](./media/FSProductsOW.png)

La plantilla **Productos de Field Service con unidad de inventario (Supply Chain Management a Field Service)** usada se basa en la plantilla **Productos de Field Service (Supply Chain Management a Field Service)**. Para obtener más información, consulte [Sincronizar productos en Supply Chain Management para productos en Field Service](field-service-product.md).

Este tema describe sólo las diferencias entre las dos plantillas: 
- **Productos Field Service con unidad de inventario (Supply Chain Management a Sales)**
- **Productos de Field Service (Supply Chain Management a Field Service)** 

## <a name="templates-and-tasks"></a>Plantillas y tareas

**Nombre de la plantilla en la integración de datos:**

- Productos Field Service con unidad de inventario (Supply Chain Management a Sales)

**Nombre de la tarea en el proyecto de integración de datos**:

- Productos

La plantilla **Productos de Field Service con unidad de inventario (Supply Chain Management a Field Service)** incluye una asignación que no está incluida en la plantilla **Productos de Field Service (Supply Chain Management a Field Service)**. Esta asignación garantiza que la unidad de inventario necesaria para la sincronización de nivel de inventario esté incluida.

```plaintext
INVENTORYUNITSYMBOL [INVENTORYUNITSYMBOL]         Fn        msdynce_inventoryunit.name [Inventory Unit(Name)] 
```

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.

### <a name="field-service-products-with-inventory-unit-supply-chain-management-to-field-service-products"></a>Producto de Field Service con unidad de inventario (Supply Chain Management a Field Service): Productos

[![Asignación de la plantilla en la integración de datos](./media/FSProduct1.png)](./media/FSProduct1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]