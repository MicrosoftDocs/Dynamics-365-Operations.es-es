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
ms.openlocfilehash: 06d7ff272ecb79abded3c3d3ade1f6bc0ef1f095
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/12/2019
ms.locfileid: "1742364"
---
# <a name="synchronize-products-in-finance-and-operations-to-products-in-field-service"></a>Sincronizar productos de Finance and Operations con productos de Field Service

[!include[banner](../includes/banner.md)]

En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar productos de Microsoft Dynamics 365 for Finance and Operations a Microsoft Dynamics 365 for Field Service.

La plantilla **Productos de Field Service (Fin and Ops to Field Service)** usada se basa en la plantilla **Productos (Fin and Ops to Sales) – Direct** del cliente potencial para cobrar. Para obtener más información, consulte [Productos (Fin and Ops to Sales) – Direct](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

El tema solo describe las diferencias entre las plantillas **Productos de Field Service (Fin and Ops to Field Service)** y **Productos (Fin and Ops to Sales) – Direct**.

## <a name="templates-and-tasks"></a>Plantillas y tareas

**Nombre de la plantilla en la integración de datos:**

- Productos Field Service (Fin and Ops to Field Service)

**Nombre de la tarea en el proyecto de integración de datos**:

- Productos - productos

La plantilla **Productos de Field Service (Fin and Ops to Field Service)** incluye una asignación que no está incluida en la plantilla **Productos (Fin and Ops to Sales) – Direct**. Esta asignación garantiza que el campo Field Service- específico **Tipo de producto de servicio** esté establecido correctamente.

```
FIELDSERVICEPRODUCTTYPE        Fn        msdyn_fieldserciveproducttype
```

Se usa la siguiente asignación de valores.

```
inventory     :  690970000
nonInventory  :  690970001 
service       :  690970002 
```

En Finance and Operations, el valor **Tipo de producto de Field Service** en la entidad de los datos **Productos emitidos vendibles** se calcula del modo siguiente:

- El tipo de producto**Inventario:** = Grupo modelo de productos y artículos, producto que se mantiene en existencias = verdadero
- El tipo de producto**NonInventory:** = Grupo modelo de productos y artículos, producto que se mantiene en existencias = falso
- Tipo de producto **Servicio** = Servicio

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.

### <a name="field-service-products-fin-and-ops-to-field-service-products---products"></a>Productos de Field Service (de Fin and Ops a Field Service): productos - productos

[![Asignación de la plantilla en la integración de datos](./media/FSProduct.png)](./media/FSProduct.png)
