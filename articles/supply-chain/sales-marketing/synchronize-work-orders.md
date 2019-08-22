---
title: Sincronizar pedidos de trabajo con proyectos desde Field Service a Finance and Operations
description: En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar pedidos de trabajo con un número de proyecto de Microsoft Dynamics 365 for Field Service a pedidos de ventas en Microsoft Dynamics 365 for Finance and Operations.
author: ChristianRytt
manager: AnnBe
ms.date: 03/12/2019
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
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 77358513ffdf791ab10d6efe1b84f598ffb5ec26
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1843418"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a>Sincronizar pedidos de trabajo con proyectos desde Field Service a Finance and Operations

[!include[banner](../includes/banner.md)]

En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar pedidos de trabajo con un número de proyecto de Microsoft Dynamics 365 for Field Service a pedidos de ventas en Microsoft Dynamics 365 for Finance and Operations.

[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

La plantilla **Pedidos de trabajo con proyecto (de Field Service a Fin and Ops)** se basa en la plantilla **Pedidos de trabajo (de Field Service a Fin and Ops)**. Para obtener más información, consulte [Sincronizar pedidos de trabajo en Field Service con pedidos de ventas en Finance and Operations](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/field-service-work-order)

Este tema describe sólo las diferencias entre las dos plantillas:
- **Pedidos de trabajo con proyecto (de Field Service a Fin and Ops)**
- **Pedidos de trabajo (de Field Service a Fin and Ops)**

La principal diferencia es que esta plantilla incluye la asignación del número de proyecto asignado al pedido de trabajo en Field Service, asegurándose de que el pedido de ventas creado en Finance and Operations incluye el número de proyecto y que la facturación puede suceder en el proyecto relacionado. Asimismo esta plantilla usa opciones avanzadas de consulta y filtrado.

## <a name="templates-and-tasks"></a>Plantillas y tareas

**Nombre de la plantilla en la integración de datos:**

- Pedidos de trabajo con proyecto (de Field Service a Fin and Ops)

**Nombre de la tarea en el proyecto de integración de datos**:

- WorkOrderHeader
- WorkOrderHeaderProject
- WorkOrderProduct
- WorkOrderService

## <a name="field-service-crm-solution"></a>Solución CRM de Field Service
El campo **Proyecto externo** se ha agregado a la entidad del pedido de trabajo. Este campo etiqueta la búsqueda y la compra de su orden de trabajo con un proyecto. Después el pedido de ventas se conectará con un proyecto en Finance and Operations. Una vez que el **estado del sistema** cambia de Abierto - En progreso (690,970,000) a un estado más alto, el campo **Proyecto externo** se bloquea y no puede agregar, quitar o cambiar el valor.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheader"></a>Pedidos de trabajo con proyecto (de Field Service a Fin and Ops): WorkOrderHeader

[![Asignación de la plantilla en la integración de datos](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderheaderproject"></a>Pedidos de trabajo con proyecto (de Field Service a Fin and Ops): WorkOrderHeaderProject

[![Asignación de la plantilla en la integración de datos](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderproduct"></a>Pedidos de trabajo con proyecto (de Field Service a Fin and Ops): WorkOrderProduct

[![Asignación de la plantilla en la integración de datos](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-fin-and-ops-workorderservice"></a>Pedidos de trabajo con proyecto (de Field Service a Fin and Ops): WorkOrderService

[![Asignación de la plantilla en la integración de datos](./media/FSWOP4.png)](./media/FSWOP4.png)
