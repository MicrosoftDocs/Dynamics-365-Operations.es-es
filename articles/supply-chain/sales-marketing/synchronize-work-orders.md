---
title: Sincronizar pedidos de trabajo con proyecto de Field Service a Supply Chain Management
description: En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar pedidos de trabajo con un número de proyecto de Dynamics 365 Field Service a pedidos de ventas en Dynamics 365 Supply Chain Management.
author: ChristianRytt
manager: tfehr
ms.date: 03/12/2019
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
ms.openlocfilehash: 5ebf23c5c831e9dad5d13c72f82eb3eeb30da853
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3215870"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-supply-chain-management"></a>Sincronizar pedidos de trabajo con proyecto de Field Service a Supply Chain Management

[!include[banner](../includes/banner.md)]

En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar pedidos de trabajo con un número de proyecto de Dynamics 365 Field Service a pedidos de ventas en Dynamics 365 Supply Chain Management.

[![Sincronización de procesos empresariales entre Supply Chain Management y Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

La plantilla **Pedidos de trabajo con proyecto (de Field Service a Supply Chain Management)** se basa en la plantilla **Pedidos de trabajo (de Field Service a Supply Chain Management)**. Para obtener más información, consulte [Sincronizar pedidos de trabajo en Field Service con pedidos de ventas en Supply Chain Management](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order)

Este tema describe sólo las diferencias entre las dos plantillas:
- **Órdenes de trabajo con proyecto (Field Service a Supply Chain Management)**
- **Órdenes de trabajo (Field Service a Supply Chain Management)**

La principal diferencia es que esta plantilla incluye la asignación del número de proyecto asignado al pedido de trabajo en Field Service, asegurándose de que el pedido de ventas creado en Supply Chain Management incluye el número de proyecto y que la facturación puede suceder en el proyecto relacionado. Asimismo esta plantilla usa opciones avanzadas de consulta y filtrado.

## <a name="templates-and-tasks"></a>Plantillas y tareas

**Nombre de la plantilla en la integración de datos:**

- Órdenes de trabajo con proyecto (Field Service a Supply Chain Management)

**Nombre de la tarea en el proyecto de integración de datos**:

- WorkOrderHeader
- WorkOrderHeaderProject
- WorkOrderProduct
- WorkOrderService

## <a name="field-service-crm-solution"></a>Solución CRM de Field Service
El campo **Proyecto externo** se ha agregado a la entidad del pedido de trabajo. Este campo etiqueta la búsqueda y la compra de su orden de trabajo con un proyecto. Después el pedido de ventas se conectará con un proyecto en Supply Chain Management. Cuando el **Estado del sistema** cambia de Abierto - En progreso (690,970,000) a un estado más alto, el campo **Proyecto externo** se bloquea y no puede agregar, quitar o cambiar el valor.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheader"></a>Órdenes de trabajo con proyecto (Field Service a Supply Chain Management): WorkOrderHeader

[![Asignación de la plantilla en la integración de datos](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheaderproject"></a>Órdenes de trabajo con proyecto (Field Service a Supply Chain Management): WorkOrderHeaderProject

[![Asignación de la plantilla en la integración de datos](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderproduct"></a>Órdenes de trabajo con proyecto (Field Service a Supply Chain Management): WorkOrderProduct

[![Asignación de la plantilla en la integración de datos](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderservice"></a>Órdenes de trabajo con proyecto (Field Service a Supply Chain Management): WorkOrderService

[![Asignación de la plantilla en la integración de datos](./media/FSWOP4.png)](./media/FSWOP4.png)
