---
title: Programación de trabajos kanban
description: Este procedimiento se centra en programar trabajos kanban de proceso para una celda de trabajo concreta.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, KanbanPeriodCapacityPart, SysLookupMultiSelectGrid, KanbanBoardScheduleJobForward
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f97b88a2637e661146e8150cd6535ff32745227a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996810"
---
# <a name="schedule-kanban-jobs"></a>Programación de trabajos kanban

[!include [banner](../../includes/banner.md)]

Este procedimiento se centra en programar trabajos kanban de proceso para una celda de trabajo concreta. El procedimiento de preparación de un trabajo kanban de proceso cuando los materiales no están disponibles es requisito para poder crear este procedimiento. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Esta tarea está pensada para el supervisor de planta y el planificador de producción que trabajan con kanbans.


## <a name="select-kanban-jobs-for-a-work-cell"></a>Selección de trabajos kanban para una celda de trabajo
1. Vaya a Control de producción > Kanban > Programación de trabajos kanban.
2. Expansión del cuadro informativo Capacidad de período
    * Expanda el cuadro informativo Kanban.  
3. En el campo Celda de trabajo, haga clic en el botón desplegable para abrir la búsqueda.
4. En la lista, marque la fila seleccionada.
    * Seleccione la celda de trabajo 1250. Esto filtrará la vista para mostrar únicamente los trabajos para la celda de trabajo 1250.  
5. En la lista, haga clic en el vínculo de la fila seleccionada.
6. Haga clic en Seleccionar.

## <a name="schedule-a-kanban-job-in-the-first-available-period"></a>Programación de un trabajo kanban para el primer período disponible
1. En la lista, marque la fila seleccionada.
    * Seleccione la primera fila de la lista con estado Sin planificar. El icono punteado en el campo Estado de trabajo indica que no ha sido planificado.  
2. Haga clic en Programar.
    * Esto programará el trabajo kanban para el primer período disponible.  
    * Tenga en cuenta que el trabajo kanban se ha movido al final de la lista porque se ha agregado al período a partir de hoy.  
    * Si el período a partir de hoy está reservado por completo, el trabajo se moverá al primer período disponible.  

## <a name="schedule-two-kanban-jobs-for-a-specific-day"></a>Programación de dos trabajos kanban para un día concreto
1. En la lista, seleccione la fila 1.
    * Debe ver que la primera fila tiene el estado Sin planificar en el campo Estado del trabajo.  
2. En la lista, seleccione la fila 2.
    * Debe ver que la segunda fila tiene el estado Sin planificar en el campo Estado del trabajo. Ahora tiene los dos primeros trabajos seleccionados.  
3. Haga clic en Programar a partir de la fecha para abrir el cuadro de diálogo desplegable.
4. Marque la casilla Omitir reacción por escasez de capacidad, o bien quite la marca, según el caso.
    * Esta opción permite anular la reacción por escasez de capacidad predeterminada.  
5. En el campo Reacción por escasez de capacidad, seleccione Agregar al período solicitado.
    * Esta opción garantizará que el trabajo se agregue al período solicitado, independientemente de que la celda de trabajo pueda estar sobrecargada.  
6. Haga clic en Programar.
    * Observe que los dos trabajos se han agregado al período deseado.  
    * En la sección de la Capacidad de período puede ver la carga para cada período. El campo Consumo muestra el consumo programado en este período. Si el consumo programado es superior a la capacidad disponible en este período, se seleccionará el consumo sobrecargado.  

