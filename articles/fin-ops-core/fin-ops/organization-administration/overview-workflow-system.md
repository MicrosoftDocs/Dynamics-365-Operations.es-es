---
title: Visión general del sistema de flujo de trabajo
description: Este tema describe el sistema de flujo de trabajo.
author: ChrisGarty
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 660e01618eea66bc611dd51818694d36993ba9ea
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/19/2020
ms.locfileid: "4797005"
---
# <a name="workflow-system-overview"></a>Visión general del sistema de flujo de trabajo

[!include [banner](../includes/banner.md)]

Este tema describe el sistema de flujo de trabajo.

## <a name="what-is-workflow"></a>¿Qué significa flujo de trabajo?

El término *flujo de trabajo* se puede definir de dos maneras: como sistema y como proceso empresarial.

### <a name="workflow-is-a-system"></a>Flujo de trabajo es un sistema

El flujo de trabajo es un sistema que se ejecuta en Application Object Server (AOS). El sistema de flujo de trabajo proporciona funciones que se pueden usar para crear flujos de trabajo individuales, o procesos empresariales.

### <a name="workflow-is-a-business-process"></a>Flujo de trabajo es un proceso empresarial

Un flujo de trabajo representa un proceso empresarial. El flujo de trabajo define el flujo o movimiento de un documento en el sistema al mostrar quién debe completar una tarea, tomar una decisión o aprobar un documento. Por ejemplo, en la siguiente ilustración se muestra un flujo de trabajo de informes de gastos.

![Flujo de trabajo con elementos que están asignados a usuarios](./media/workflow_user.gif)

Para comprender mejor este flujo de trabajo, supongamos que Sam envía un informe de gastos por un total de 7.000 USD. En esta situación, Ivan debe revisar los recibos que Sam le envía. A continuación, Frank y Sue deben aprobar el informe de gastos. Ahora supongamos que Sam envía un informe de gastos por un total de 11.000 USD. En esa situación, Ivan debe revisar los recibos y Frank, Sue y Ann deben aprobar el informe de gastos.

## <a name="benefits-of-using-the-workflow-system"></a>Ventajas del uso del sistema de flujo de trabajo

El uso del sistema de flujo de trabajo en una organización ofrece varias ventajas:

- **Procesos coherentes**: puede definir cómo determinados documentos —por ejemplo, solicitudes de compra e informes de gastos— se procesan. Al usar el sistema de flujo de trabajo, puede asegurarse de que los documentos se procesarán y aprobarán de manera coherente y eficiente.
- **Visibilidad de procesos**: puede realizar el seguimiento del estado, el historial y las medidas de rendimiento de las instancias de flujo de trabajo. De este modo, puede determinar si se deben realizar cambios en el flujo de trabajo para mejorar la eficiencia.
- **Lista de trabajo centralizada**: los usuarios pueden ver una lista de trabajo centralizada con las tareas y aprobaciones de flujo de trabajo que tienen asignadas.


## <a name="workflow-content"></a>Contenido del flujo de trabajo

+ [Arquitectura del sistema de flujo de trabajo](workflow-system-architecture.md)
+ [Elementos del flujo de trabajo](workflow-elements.md)
+ [Acciones en los procesos de aprobación de flujo de trabajo](workflow-actions.md)
+ [Visión general de la creación de flujos de trabajo](create-workflow.md)
+ [Configurar propiedades del flujo de trabajo](configure-workflow-properties.md)
+ [Configurar tareas manuales en un flujo de trabajo](configure-manual-task-workflow.md)
+ [Configurar tareas automatizadas en un flujo de trabajo](configure-automated-task-workflow.md)
+ [Configurar los procesos de aprobación en un flujo de trabajo](configure-approval-process-workflow.md)
+ [Configurar los pasos de aprobación en un flujo de trabajo](configure-approval-step-workflow.md)
+ [Configurar decisiones manuales en un flujo de trabajo](configure-manual-decision-workflow.md)
+ [Configurar decisiones condicionales en un flujo de trabajo](configure-conditional-decision-workflow.md)
+ [Configurar actividades paralelas en un flujo de trabajo](configure-parallel-activity-workflow.md)
+ [Configurar ramas paralelas en un flujo de trabajo](configure-parallel-branch-workflow.md)
+ [Configurar flujos de trabajo de elementos](configure-line-item-workflow.md)
+ [Preguntas frecuentes sobre flujos de trabajo](workflow-FAQ.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]