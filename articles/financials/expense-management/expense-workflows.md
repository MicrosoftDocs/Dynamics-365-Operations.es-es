---
title: Configurar flujos de trabajo de los gastos
description: Puede configurar un proceso de flujo de trabajo que se usa para revisar y aprobar documentos de gastos y viajes.
author: saraschi2
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: cf35406b43c1ec40a7c248b970559b65fcd8a6c6
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="set-up-workflows-for-expense"></a>Configurar flujos de trabajo de los gastos

[!include [banner](../includes/banner.md)]

 Puede configurar un proceso de flujo de trabajo que se usa para revisar y aprobar documentos de gastos y viajes. Los documentos para los que pueden definirse los flujos de trabajo incluyen informes de gastos, pedidos de viaje y solicitudes de anticipo.

Un flujo de trabajo representa un proceso empresarial. El flujo de trabajo define cómo se gestiona un documento en el sistema e indica quién debe completar una tarea o aprobar un documento. El uso del sistema de flujo de trabajo en su organización le ofrece varias ventajas:

-   **Procesos coherentes**: puede definir el proceso de aprobación para documentos específicos como, por ejemplo, solicitudes de compra e informes de gastos. El sistema de flujo de trabajo le ayuda a garantizar que los documentos se procesan y se aprueban de manera coherente y eficaz.

-   Visibilidad de procesos: puede realizar el seguimiento del estado, el historial y las medidas de rendimiento de una instancia de flujo de trabajo determinada. De este modo puede determinar si los cambios deben realizarse en el flujo de trabajo para mejorar la eficacia.

-   Lista de trabajo centralizada: los usuarios pueden ver una lista de trabajo centralizada para ver las tareas y aprobaciones de flujo de trabajo que tienen asignadas. 

**Tipos de flujo de trabajo que puede crear**

En la siguiente tabla se describen los tipos de flujo de trabajo que se pueden crear en **Gastos**.


|              <strong>Tipo</strong>              |                   <strong>Use este tipo para</strong>                   |
|-------------------------------------------------|-----------------------------------------------------------------------|
|         <strong>Informe de gastos</strong>         |            Cree flujos de trabajo de aprobación para los informes de gastos.             |
|  <strong>Registro automático de informe de gastos</strong>   |        Cree flujos de trabajo del registro automático para los informes de gastos.        |
|       <strong>Elemento de línea de gastos</strong>        |     Cree flujos de trabajo de aprobación para los artículos de línea en los informes de gastos.      |
| <strong>Registro automático de artículo de línea de gasto</strong> | Cree flujos de trabajo de registro automático para los artículos de línea en los informes de gastos. |
|       <strong>Pedido de viaje</strong>       |          Cree flujos de trabajo de aprobación para solicitudes de viaje.           |
|      <strong>Solicitud de anticipo</strong>      |         Cree flujos de aprobación para las solicitudes de anticipo.          |
|        <strong>Devolución de impuestos de IVA</strong>        | Cree flujos de trabajo de aprobación para la devolución del impuesto sobre el valor añadido (VAT).  |


