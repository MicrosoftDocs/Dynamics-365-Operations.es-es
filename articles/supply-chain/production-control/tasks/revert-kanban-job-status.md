---
title: Invertir estado del trabajo kanban
description: Este procedimiento se centra en la inversión de un estado de trabajo kanban incorrecto.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3f9026aff0f54dd2a61cb0f35705b002a125610f
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3148869"
---
# <a name="revert-kanban-job-status"></a>Invertir estado del trabajo kanban

[!include [banner](../../includes/banner.md)]

Este procedimiento se centra en la inversión de un estado de trabajo kanban incorrecto. Esto resulta útil en el caso de que el operador de máquina actualice el trabajo incorrecto o establezca el estado incorrecto por error. En este procedimiento, un trabajo kanban se registra como preparado por error y el estado se revierte. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este procedimiento está pensado para el supervisor de planta o el operador de máquina que trabaja en una empresa de lean manufacturing.


## <a name="open-process-board-for-the-work-cell"></a>Abrir el tablero de proceso para la celda de trabajo
1. Vaya a Tablero kanban para trabajos de proceso.
2. En el campo Celda de trabajo, especifique o seleccione un valor.
    * Seleccione la celda de trabajo 1260.  

## <a name="prepare-kanban-job"></a>Preparar el trabajo kanban
1. Haga clic en Preparar.
    * Si no puede hacer clic en Preparar porque aparece atenuado, asegúrese de que el trabajo kanban seleccionado tiene el estado Planificado, que se indica con el icono de kanban vacío. Si se produce un error en Preparar, asegúrese de que todos los materiales de la Lista de selección están disponibles.  
2. En la lista, seleccione el trabajo preparado.
    * Seleccione el primer trabajo que acaba de preparar.  
    * Observe que el estado de los trabajos es preparado, lo que se indica con un triángulo dentro del icono de kanban.  

## <a name="revert-the-status-of-the-prepared-kanban-job"></a>Revertir el estado del trabajo kanban preparado
1. En la lista, marque la fila seleccionada.
    * Seleccione el primer trabajo que se preparó.  
2. En el panel de acciones, haga clic en Fabricación.
3. Haga clic en Revertir estado.
    * Puede usar una regla kanban alternativa cuando las siguientes condiciones sean verdaderas: - La estrategia de reabastecimiento es la misma para ambas reglas.  - La versión del flujo de producción es la misma para ambas reglas.  - El producto que se suministra es el mismo para ambas reglas.  - Todas las actividades en sentido descendente configuradas para la última actividad de las reglas kanban debe ser las mismas para ambas reglas.  - Se deben configurar las mismas dimensiones de inventario proporcionadas para ambas reglas.  - El estado de la unidad de gestión de material debe ser No asignado.  - La configuración para kanbans de eventos debe ser la misma.  
    * Asegúrese de que el estado nuevo es Planificado.  
4. Haga clic en Aceptar
5. En la lista, desmarque la fila seleccionada.
    * Seleccione el mismo trabajo.  
    * Observe que el estado del trabajo kanban se revierte a Planificado, lo que se indica con un icono de kanban vacío.  

