---
title: Sincronizar pedidos de trabajo con proyecto de Field Service a Supply Chain Management
description: En este artículo se describe las plantillas y la tarea subyacente que se usan para sincronizar pedidos de trabajo con un número de proyecto de Dynamics 365 Field Service a pedidos de ventas en Dynamics 365 Supply Chain Management.
author: Henrikan
ms.date: 03/12/2019
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
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: a43a7f7e900205bdb23fb9a35ca1518369683a42
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860504"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-supply-chain-management"></a>Sincronizar pedidos de trabajo con proyecto de Field Service a Supply Chain Management

[!include[banner](../includes/banner.md)]

En este artículo se describe las plantillas y la tarea subyacente que se usan para sincronizar pedidos de trabajo con un número de proyecto de Dynamics 365 Field Service a pedidos de ventas en Dynamics 365 Supply Chain Management.

[![Sincronización de procesos empresariales entre Supply Chain Management y Field Service.](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

La plantilla **Pedidos de trabajo con proyecto (de Field Service a Supply Chain Management)** se basa en la plantilla **Pedidos de trabajo (de Field Service a Supply Chain Management)**. Para obtener más información, consulte [Sincronizar pedidos de trabajo en Field Service con pedidos de ventas en Supply Chain Management](/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order)

Este artículo describe sólo las diferencias entre las dos plantillas:
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

[![Asignación de plantillas en la integración de datos, pedidos de trabajo con proyecto (Field Service a Supply Chain Management): WorkOrderHeader.](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderheaderproject"></a>Órdenes de trabajo con proyecto (Field Service a Supply Chain Management): WorkOrderHeaderProject

[![Asignación de plantillas en la integración de datos, pedidos de trabajo con proyecto (Field Service a Supply Chain Management): WorkOrderHeaderProject.](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderproduct"></a>Órdenes de trabajo con proyecto (Field Service a Supply Chain Management): WorkOrderProduct

[![Asignación de plantillas en la integración de datos, pedidos de trabajo con proyecto (Field Service a Supply Chain Management): WorkOrderProduct.](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-supply-chain-management-workorderservice"></a>Órdenes de trabajo con proyecto (Field Service a Supply Chain Management): WorkOrderService

[![Asignación de plantillas en la integración de datos, pedidos de trabajo con proyecto (Field Service a Supply Chain Management): WorkOrderService.](./media/FSWOP4.png)](./media/FSWOP4.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]