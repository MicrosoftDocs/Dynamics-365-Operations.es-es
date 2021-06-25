---
title: Programación de trabajo kanban para lean manufacturing
description: Este artículo proporciona información acerca del control visual sobre la programación del trabajo kanban y las distintas maneras de programar trabajos kanban.
author: cvocph
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardScheduleJobForward, KanbanBoardShowJobs, KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 52961
ms.assetid: fe3b4822-6140-4b02-bebb-1fc17be2bce8
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0d0cbaf6b8440dbbb71146a34cbbe949cfe78d0c
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "6190049"
---
# <a name="kanban-job-scheduling-for-lean-manufacturing"></a>Programación de trabajo kanban para lean manufacturing

[!include [banner](../includes/banner.md)]

Este artículo proporciona información acerca del control visual sobre la programación del trabajo kanban y las distintas maneras de programar trabajos kanban.  

La página **Programación de trabajo** ofrece control visual acerca de las programaciones de las celdas de trabajo de lean manufacturing. Ofrece una visión general de todos los trabajos kanban y ofrece varias capacidades de filtrado. Desde esta página, puede mover al resto de las páginas relacionadas con la configuración y la ejecución del kanban.

## <a name="automatic-scheduling-of-kanban-jobs"></a>Programación automática de trabajos kanban
La programación puede ser activada automáticamente si define el parámetro **Cantidad de planificación automática** en la regla kanban. Si establece **Cantidad de planificación automática** en **1**, cada trabajo kanban se planifica inmediatamente cuando se crea. El resultado es una serie de operaciones tipo "se la queda el primero que las extrae". Si establece **Cantidad de planificación automática** en un valor que sea mayor que 1, se agrupan los trabajos kanban antes de que se planifiquen. 

Este concepto permite que los tamaños kanban se reduzcan por debajo de los tamaños económicos reales del lote. Por ejemplo, el tamaño económico de lote para un artículo específico (o familia de artículos) es 30. En lugar de crear kanbans que usan la cantidad de producto, 30, puede configurar la regla kanban de modo que tenga una cantidad de producto de 10 y un valor de **Cantidad de planificación automática** de **3**. Aunque la planificación automática programa los trabajos kanban para la celda de trabajo solo cuando existen tres trabajos no planificados, es completamente transparente para el planificador y el supervisor de planta que dos trabajos no planificados pueden aguardar ejecución. El planificador o jefe de planta pude llevar estos dos trabajos a producción planificándolos manualmente o creaando kanbans adicionales.

## <a name="manual-scheduling"></a>Programación manual
Para la programación manual, Microsoft Dynamics AX 2012 presentó el panel de programación kanban. La programación manual se puede combinar con la programación automática. El panel de programación kanban le permite planificar y dejar de planificar trabajos, moverlos en secuencia o moverlos de un período a otro. Los trabajos que se basan en una regla kanban en la que el valor **Planificación automática** es mayor que **0** se pueden dejar de planificar manualmente. Sin embargo, estos trabajos se volverán a planificar cuando se produzca el próximo evento automático de planificación (es decir, cuando se crea un nuevo kanban). Las siguientes opciones están disponibles para la programación manual:

-   **Programación** programa los trabajos seleccionados en función de su fecha de vencimiento. (Esta opción es similar a la planificación automática.)
-   **Programación hacia delante a partir de la fecha** intenta programar los trabajos seleccionados en función de su fecha de vencimiento pero restringe el resultado mediante la fecha de inicio más temprana especificada.
-   **Hacia atrás** mueve hacia atrás los trabajos programados seleccionados en la secuencia dentro del período.
-   **Hacia adelante** mueve hacia adelante los trabajos programados seleccionados en la secuencia dentro del período.
-   **Período anterior** mueve los trabajos programados seleccionados al inicio o al final del período anterior.
-   **Período siguiente** mueve los trabajos programados seleccionados al inicio o al final del período siguiente.
-   **Plan** &gt; **Invertir estado de trabajo** le permite desprogramar un trabajo programado.

## <a name="lean-scheduling-groups"></a>Grupos de programación lean
Cada color representa un grupo de programación lean. Los grupos de programación lean pueden definirse libremente como grupos genéricos o grupos que pertenecen a una sola celda de trabajo. Los elementos y la dimensiones se pueden asignar a los grupos de programación libremente. Por ejemplo, en una celda de pintura, un grupo de programación puede representar un color del producto. En el trabajo que se realizado siguiendo requisitos específicos de las herramientas, los elementos se pueden agrupar por requisito de herramienta, y una celda de trabajo de embalaje puede agrupar los elementos por plantilla. El uso de colores para los grupos de programación lean es opcional pero muy recomendable. Mejora la visibilidad en el estado del plan. Por ejemplo, es muy fácil ver qué colores se producen cada día, y puede ver fácilmente cómo se puede optimizar este trabajo.

## <a name="work-cell-capacity-and-period-capacity"></a>La capacidad de la celda de trabajo la capacidad del período
La capacidad de la celda de trabajo lean siempre es capacidad concurrente. Es decir, varios trabajos pueden estar activos en una celda de trabajo al mismo tiempo. se puede hacer un seguimiento de la capacidad de dos modos: capacidad de proceso y horas.

### <a name="throughput"></a>Capacidad de proceso

La capacidad de una celda de trabajo está definida por la cantidad de la capacidad media de proceso de un período de referencia (día laborable, semana o mes estándar). Después se calcula la capacidad real por día o semana en función de los horarios de trabajo del calendario asignado a la celda de trabajo. La capacidad que se carga por trabajo es la cantidad de trabajo, ajustada por el coeficiente de capacidad de proceso del elemento en la celda de trabajo.

### <a name="hours"></a>Horas

La capacidad disponible por día o por semana se define por el calendario asignado a la celda de trabajo. La capacidad que se carga por trabajo es el tiempo de ciclo de la actividad, ajustada por la cantidad (cantida de actividad predeterminada comparada con la cantidad real de trabajo) y el coeficiente de capacidad de proceso del elemento en la celda de trabajo.

#### <a name="period-capacity-factbox"></a>Cuadro informativo de capacidad de período

La página de lista de la **Programación de trabajo kanban** contiene un cuadro informativo que muestra la capacidad disponible y reservada del período para la celda de trabajo seleccionada. En función de los períodos seleccionados de la programación en el modelo de flujo de producción, los períodos muestran días o semanas.

## <a name="additional-resources"></a>Recursos adicionales





[!INCLUDE[footer-include](../../includes/footer-banner.md)]