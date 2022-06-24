---
title: Sincronizar productos de Supply Chain Management con productos de Field Service
description: En este artículo se describen las plantillas y la tarea subyacente que se usan para sincronizar productos de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.
author: Henrikan
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
ms.author: henrikan
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 114550f01f3aed197480fb6830fe913dbfa7b570
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860562"
---
# <a name="synchronize-products-in-supply-chain-management-to-products-in-field-service"></a>Sincronizar productos de Supply Chain Management con productos de Field Service

[!include[banner](../includes/banner.md)]

En este artículo se describen las plantillas y la tarea subyacente que se usan para sincronizar productos de Dynamics 365 Supply Chain Management a Dynamics 365 Field Service.

La plantilla **Productos de Field Service (Supply Chain Management a Field Service)** usada se basa en la plantilla **Productos (Supply Chain Management a Sales) – Direct** del cliente potencial para cobrar. Para obtener más información, consulte [Productos (Supply Chain Management a Sales) – Directo](/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

El artículo solo describe las diferencias entre las plantillas **Productos de Field Service (Supply Chain Management a Field Service)** y **Productos (Supply Chain Management a Sales) – Direct**.

## <a name="templates-and-tasks"></a>Plantillas y tareas

**Nombre de la plantilla en la integración de datos**

- Productos de Field Service (Supply Chain Management a Field Service)

**Nombre de la tarea en el proyecto de integración de datos**

- Productos - productos

La plantilla **Productos de Field Service (Supply Chain Management a Field Service)** incluye un tipo de asignación que no se incluye en plantilla **Productos (Supply Chain Management a Sales) – Direct**. Esta asignación garantiza que el campo Field Service- específico **Tipo de producto de servicio** esté establecido correctamente.

```plaintext
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

Se usa la siguiente asignación de valores.

```plaintext
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

En Supply Chain Management, el valor **Tipo de producto de Field Service** en la entidad de los datos **Productos emitidos vendibles** se calcula del modo siguiente:

- El tipo de producto **Inventario:** = Grupo modelo de productos y artículos, producto que se mantiene en existencias = verdadero
- El tipo de producto **NonInventory:** = Grupo modelo de productos y artículos, producto que se mantiene en existencias = falso
- Tipo de producto **Servicio** = Servicio

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.

### <a name="field-service-products-supply-chain-management-to-field-service-products---products"></a>Productos de Field Service (Supply Chain Management a Field Service): Productos - Productos

[![Asignación de la plantilla en la integración de datos.](./media/FSProduct.png)](./media/FSProduct.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]