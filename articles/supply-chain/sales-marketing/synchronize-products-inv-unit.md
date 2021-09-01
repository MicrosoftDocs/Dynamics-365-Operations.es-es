---
title: Sincronizar productos con unidad de inventario de Supply Chain Management a Field Service
description: En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar productos con unidades de inventario de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.
author: ChristianRytt
ms.date: 03/13/2019
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
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 1312015fe5b9b95a341e9e7170dfc5106f47f0875f89224983e5ec61dd8de5ff
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6717876"
---
# <a name="synchronize-products-with-inventory-unit-from-supply-chain-management-to-field-service"></a>Sincronizar productos con unidad de inventario de Supply Chain Management a Field Service

[!include[banner](../includes/banner.md)]

En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar productos con unidades de inventario de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.

[![Sincronización de procesos empresariales entre Supply Chain Management y Field Service.](./media/FSProductsOW.png)](./media/FSProductsOW.png)

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

[![Asignación de la plantilla en la integración de datos.](./media/FSProduct1.png)](./media/FSProduct1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]