---
title: Sincronizar pedidos de trabajo con proyectos desde Field Service a Finance and Operations
description: En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar pedidos de trabajo con un número de proyecto de Microsoft Dynamics 365 for Field Service a pedidos de ventas en Microsoft Dynamics 365 for Finance and Operations.
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
ms.openlocfilehash: 6b61411a5a235e2d0aad8bb25ae4a3bfcf1248d1
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "329859"
---
# <a name="synchronize-work-orders-with-project-from-field-service-to-finance-and-operations"></a>Sincronizar pedidos de trabajo con proyectos desde Field Service a Finance and Operations

[!include[banner](../includes/banner.md)]

En este tema se describe las plantillas y la tarea subyacente que se usan para sincronizar pedidos de trabajo con un número de proyecto de Microsoft Dynamics 365 for Field Service a pedidos de ventas en Microsoft Dynamics 365 for Finance and Operations.

[![Sincronización de procesos empresariales entre Finance and Operations y Field Service](./media/FSSOprojectOW.png)](./media/FSSOprojectOW.png)

La plantilla **Productos de Field Service (Finance and Operations a Field Service)** usada se basa en la plantilla **Productos (Finance and Operations to Sales) – Direct** del cliente potencial para cobrar. Para obtener más información, consulte [Productos (Finance and Operations a Sales) – Directo](https://docs.microsoft.com/en-us/dynamics365/unified-operations/supply-chain/sales-marketing/products-template-mapping-direct).

El tema solo describe las diferencias entre las plantillas **Productos de Field Service (Finance and Operations a Field Service)** y **Productos (Finance and Operations a Sales) – Directo**.

La principal diferencia es que esta plantilla incluye la asignación del número de proyecto asignado al pedido de trabajo en Field Service, asegurándose de que el pedido de ventas creado en Finance and Operations incluye el número de proyecto y que la facturación puede suceder en el proyecto relacionado. Asimismo esta plantilla usa opciones avanzadas de consulta y filtrado.

## <a name="templates-and-tasks"></a>Plantillas y tareas

**Nombre de la plantilla en la integración de datos:**

- Pedidos de trabajo con proyecto (de Field Service a Finance and Operations)

**Nombre de la tarea en el proyecto de integración de datos**:

- WorkOrderHeader
- WorkOrderHeaderProject
- WorkOrderProduct
- WorkOrderService

## <a name="field-service-crm-solution"></a>Solución CRM de Field Service
El campo **Proyecto externo** se ha agregado a la entidad del pedido de trabajo. Este campo etiqueta la búsqueda y la compra de su orden de trabajo con un proyecto. Después el pedido de ventas se conectará con un proyecto en Finance and Operations. Una vez que el **estado del sistema** cambia de Abierto - En progreso (690,970,000) a un estado más alto, el campo **Proyecto externo** se bloquea y no puede agregar, quitar o cambiar el valor.

## <a name="template-mapping-in-data-integration"></a>Asignación de la plantilla en la integración de datos

Las siguientes ilustraciones muestran la asignación de plantilla en la integración de datos.

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheader"></a>Pedidos de trabajo con proyecto (de Field Service a Finance and Operations): WorkOrderHeader

[![Asignación de la plantilla en la integración de datos](./media/FSWOP1.png)](./media/FSWOP1.png)

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderheaderproject"></a>Pedidos de trabajo con proyecto (de Field Service a Finance and Operations): WorkOrderHeaderProject

[![Asignación de la plantilla en la integración de datos](./media/FSWOP2.png)](./media/FSWOP2.png)

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderproduct"></a>Pedidos de trabajo con proyecto (de Field Service a Finance and Operations): WorkOrderProduct

[![Asignación de la plantilla en la integración de datos](./media/FSWOP3.png)](./media/FSWOP3.png)

### <a name="work-orders-with-project-field-service-to-finance-and-operations-workorderservice"></a>Pedidos de trabajo con proyecto (de Field Service a Finance and Operations): WorkOrderService

[![Asignación de la plantilla en la integración de datos](./media/FSWOP4.png)](./media/FSWOP4.png)
