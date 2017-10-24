---
title: "Visión general del flujo de trabajo"
description: Este tema describe el sistema de flujo de trabajo en Microsoft Dynamics 365 for Finance and Operations.
author: sericks007
manager: AnnBe
ms.date: 08/17/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6622f0e5ed6c38bb8131d13aa02061968862678b
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="workflow-overview"></a>Visión general del flujo de trabajo

[!include[banner](../includes/banner.md)]


Este tema describe el sistema de flujo de trabajo en Microsoft Dynamics 365 for Finance and Operations.

<a name="what-is-workflow"></a>¿Qué significa flujo de trabajo?
-----------------

El término *flujo de trabajo* se puede definir de dos maneras: como sistema y como proceso empresarial.
### <a name="workflow-is-a-system"></a>Flujo de trabajo es un sistema

El flujo de trabajo es un sistema que se instala junto con Dynamics 365 for Finance and Operations y se ejecuta en Application Object Server (AOS). El sistema de flujo de trabajo proporciona funciones que se pueden usar para crear flujos de trabajo individuales, o procesos empresariales.

### <a name="workflow-is-a-business-process"></a>Flujo de trabajo es un proceso empresarial

Un flujo de trabajo representa un proceso empresarial. El flujo de trabajo define el flujo o movimiento de un documento en el sistema al mostrar quién debe completar una tarea, tomar una decisión o aprobar un documento. Por ejemplo, en la siguiente ilustración se muestra un flujo de trabajo de informes de gastos. 

![Flujo de trabajo con elementos que están asignados a usuarios](./media/workflow_user.gif) 

Para comprender mejor este flujo de trabajo, supongamos que Sam envía un informe de gastos por un total de 7.000 USD. En esta situación, Ivan debe revisar los recibos que Sam le envía. A continuación, Frank y Sue deben aprobar el informe de gastos. Ahora supongamos que Sam envía un informe de gastos por un total de 11.000 USD. En esa situación, Ivan debe revisar los recibos y Frank, Sue y Ann deben aprobar el informe de gastos.

## <a name="benefits-of-using-the-workflow-system"></a>Ventajas del uso del sistema de flujo de trabajo

El uso del sistema de flujo de trabajo en una organización ofrece varias ventajas:
-   **Procesos coherentes**: puede definir cómo determinados documentos —por ejemplo, solicitudes de compra e informes de gastos— se procesan. Al usar el sistema de flujo de trabajo, puede asegurarse de que los documentos se procesarán y aprobarán de manera coherente y eficiente.
-   **Visibilidad de procesos**: puede realizar el seguimiento del estado, el historial y las medidas de rendimiento de las instancias de flujo de trabajo. De este modo, puede determinar si se deben realizar cambios en el flujo de trabajo para mejorar la eficiencia.
-   **Lista de trabajo centralizada**: los usuarios pueden ver una lista de trabajo centralizada con las tareas y aprobaciones de flujo de trabajo que tienen asignadas.


## <a name="workflow-content"></a>Contenido del flujo de trabajo

+ [Arquitectura del flujo de trabajo](workflow-system-architecture.md)
+ [Elementos del flujo de trabajo](workflow-elements.md)
+ [Acciones de flujo de trabajo](workflow-actions.md)
+ [Creación de un flujo de trabajo](create-workflow.md)
+ [Configuración de propiedades del flujo de trabajo](configure-workflow-properties.md)
+ [Configuración de una tarea manual en un flujo de trabajo](configure-manual-task-workflow.md)
+ [Configuración de una tarea automatizada en un flujo de trabajo](configure-automated-task-workflow.md)
+ [Configuración de un proceso de aprobación en un flujo de trabajo](configure-approval-process-workflow.md)
+ [Configuración de un paso de aprobación en un flujo de trabajo](configure-approval-step-workflow.md)
+ [Configuración de una decisión manual en un flujo de trabajo](configure-manual-decision-workflow.md)
+ [Configuración de una decisión condicional en un flujo de trabajo](configure-conditional-decision-workflow.md)
+ [Configuración de una actividad paralela en un flujo de trabajo](configure-parallel-activity-workflow.md)
+ [Configuración de rama paralela en un flujo de trabajo](configure-parallel-branch-workflow.md)
+ [Configuración de un flujo de trabajo de elementos](configure-line-item-workflow.md)

