---
title: "Programación visual para lean manufacturing"
description: "Este tema proporciona información acerca del tablero de programación kanban, que el planificador de producción puede usar para controlar y optimizar el plan de producción de trabajos kanban."
author: johanhoffmann
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanBoard, KanbanJobSchedulingListPage, LeanProductionFlowVisualization
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: d2ead061fe39c3dcb54d697f246c2c826339b699
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="visual-scheduling-for-lean-manufacturing"></a>Programación visual para lean manufacturing

[!include [banner](../includes/banner.md)]

Este tema proporciona información acerca del tablero de programación kanban, que el planificador de producción puede usar para controlar y optimizar el plan de producción de trabajos kanban.

Este tema proporciona información acerca del tablero de programación kanban, que el planificador de producción puede usar para controlar y optimizar el plan de producción de trabajos kanban.

El tablero de programación kanban permite al planificador de producción controlar y optimizar el plan de producción de trabajos kanban. Hace que el flujo de trabajos kanban sea transparente y ofrece al planificador de la producción una herramienta que optimiza y ajusta el plan de producción para la celda de trabajo de lean manufacturing.

## <a name="visual-scheduling-of-kanban-jobs"></a>Programación visual de trabajos kanban
Un trabajo kanban puede estar formado por uno o varios trabajos kanban. Existen dos tipos de trabajo kanban:

-   Proceso
-   Transferir

Solo puede programar trabajos del tipo **Proceso**. El trabajo kanban y sus propiedades, como el tiempo de actividad, se definen en el flujo kanban de la producción. En el flujo kanban de producción, el trabajo kanban también se asigna a una celda de trabajo. La capacidad diaria de la celda de trabajo se calcula en función de la capacidad de la celda de trabajo que se establece en el grupo de recursos. Está ajustada por el horario de trabajo diario del calendario relacionado. Cuando se programa un trabajo kanban, el trabajo carga la capacidad de la celda de trabajo. El tablero de programación kanban proporciona las características principales siguientes:

-   Una visión general gráfica del plan de producción en una celda de trabajo lean. Esta información general muestra los trabajos planificados del proceso kanban en los períodos definidos.
-   Herramienta que le permite programar trabajos kanban no planificados y reprogramar los trabajos programados anteriormente.

## <a name="kanban-schedule-board"></a>Tablero de programación kanban
La página **Tablero de programación kanban** contiene siete elementos principales, como se muestra en la siguiente ilustración. 

![Tablero de programación kanban](./media/kanban-schedule-board-1024x554.png)
1.  Panel de acciones
2.  Campos de filtro
3.  Botón para trabajos no planificados
4.  Nodo del período
5.  Trabajo kanban
6.  Barra de capacidad
7.  Escala temporal

### <a name="view-the-time-scale"></a>Ver la escala temporal

El tablero se divide en períodos, cada uno representado como un nodo (4). Los nodos del período se enumeran en el eje vertical, y el acceso horizontal representa una escala de tiempo (7) que muestra la duración del período. Un período tiene una duración de un día o una semana. La duración del período viene determinada por la configuración de la celda de trabajo seleccionada para el tablero de programación kanban (2). Para cada nodo del período, el tablero de programación kanban indica en qué medida los trabajos kanban programados están cargando el período. También una indicación de capacidad de proceso máxima para el período. Si el rendimiento programado supera la capacidad de proceso máxima, el período se considera como sobrecargado y aparece un símbolo de advertencia rojo. Un trabajo kanban programado aparece en un período que tiene horas de inicio y fin programadas (5). La longitud del trabajo es igual al tiempo de actividad. Los trabajos kanban aparecen como solapados en un período si los tiempos de actividad superan el ritmo de producción de la celda de trabajo.

### <a name="view-job-status"></a>Ver el estado del trabajo

Más información acerca de un trabajo kanban está disponible en la información sobre herramientas que aparece cuando se pasa el puntero del ratón sobre el trabajo. Un símbolo proporciona información acerca del estado del trabajo. Por ejemplo, un símbolo de un reloj indica que el trabajo kanban ha vencido.

### <a name="use-colors-to-view-the-kanban-schedule-board"></a>Use colores para ver el tablero de programación kanban

Para mejorar la visión general que proporciona el tablero de programación kanban, puede usar colores para distinguir los trabajos kanban. El color de un trabajo kanban se configura en el grupo de programación lean, donde puede agregar los productos que deben producirse en la misma secuencia. El botón **Usar colores de tema** en la ficha **Tablero** del panel de acciones le permite cambiar entre los colores del tema de la aplicación y los colores configurados en el grupo de programación lean. Para cada período, una barra de capacidad (6) indica la cantidad de horas disponibles para el período que se han cargado con trabajos kanban. Si se sobrecarga el período, la barra de la capacidad se muestra más gruesa y en rojo. Todas estas funciones están disponibles en la ficha **Tablero** del panel de acciones (1) en la parte superior de la página **Tablero de programación kanban** .

## <a name="plan-unplanned-jobs"></a>Planificar trabajos no planificados
Puede programar trabajos kanban no planificados desde el cuadro de diálogo **Planificar trabajos no planificados** . Para abrir este cuadro de diálogo, haga clic en el botón **Trabajos no planificados** que muestra el número actual de trabajos no planificados. Como alternativa, haga clic en **Planificar trabajos no planificados** en la ficha **Tablero** del panel de acciones. El cuadro de diálogo muestra una lista de los trabajos kanban no planificados para la celda de trabajo. Puede usar el campo **Filtrar** para filtrar todos los campos de la cuadrícula. Por ejemplo, puede filtrar los trabajos kanban de un producto específico. Una vez que tenga una lista filtrada de los trabajos que desee programar, selecciónelos en la lista y haga clic en **Aceptar**. Para usar la planificación automática para programar los trabajos, establezca la opción **Planificación automática** en **Sí**. En este caso, los trabajos se programan en un período acorde con su fecha de vencimiento. También puede programar los trabajos por período. Basta seleccionar un período en el campo **Período**. La ilustración siguiente muestra un ejemplo del cuadro de diálogo **Planificar trabajos no planificados** . 

![Cuadro de diálogo Planificar trabajos no planificados](./media/plan-unplanned-jobs-1024x564.png)

## <a name="sequence-kanban-jobs-within-the-same-period"></a>Ordenar trabajos kanban dentro del mismo período
Puede cambiar la secuencia de uno o más trabajos seleccionado dentro un período. Esta capacidad pueden ser de utilidad si desea dar prioridad a algunos trabajos dentro del período. Como alternativa, puede que desee ordenar los trabajos que tienen los mismos atributos de producto para optimizar la ejecución del trabajo. Puede cambiar la secuencia con una operación de arrastrar y soltar, o usar los elementos de menú **Hacia atrás** y **Hacia delante** en la ficha **Tablero** del panel de acciones.

## <a name="reassign-kanban-jobs-across-periods"></a>Asignar los trabajos kanban a otro período
Los trabajos pueden asignarse de un período a otro. Esta capacidad puede ser útil si se sobrecarga un período y desea nivelar la cargar con los períodos que tengan capacidad de sobra. Puede reasignar los trabajos con una operación de arrastrar y soltar, o usar los elementos de menú **Período siguiente** y **Período anterior** en la ficha **Tablero** del panel de acciones.

## <a name="open-the-kanban-schedule-board"></a>Abrir el tablero de programación kanban
Puede abrir el tablero de programación kanban mediante el elemento de menú de las siguientes páginas:

-   Página **Área de producción**
-   Página **Programación de trabajos kanban**
-   Página **Visualización de flujo de producción**


<a name="additional-resources"></a>Recursos adicionales
--------

[Lean manufacturing: programación de trabajos kanban](lean-manufacturing-kanban-job-scheduling.md)


