---
title: Eliminación de un trabajo kanban de la programación
description: Este procedimiento se centra en la eliminación de un trabajo kanban planificado de la programación revirtiendo el estado del trabajo a Sin planificar.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage, SysLookupMultiSelectGrid, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f3e9a512e7f391e08a35fd0eea449af12d81e644
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5828595"
---
# <a name="remove-a-kanban-job-from-the-schedule"></a>Eliminación de un trabajo kanban de la programación

[!include [banner](../../includes/banner.md)]

Este procedimiento se centra en la eliminación de un trabajo kanban planificado de la programación revirtiendo el estado del trabajo a Sin planificar. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este procedimiento está pensado para el supervisor de planta o el planificador de producción.


## <a name="find-a-planned-kanban-job"></a>Búsqueda de un trabajo kanban planificado
1. Vaya a Control de producción > Kanban > Programación de trabajos kanban.
2. En el campo Celda de trabajo, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Seleccione la celda de trabajo 1250.  
4. Haga clic en Seleccionar.
5. En el campo Mostrar estado del trabajo, seleccione Programado.

## <a name="remove-the-planned-kanban-job-from-the-schedule"></a>Eliminación del trabajo kanban planificado de la programación
1. En la lista, busque y seleccione el registro deseado.
    * Seleccione un trabajo con estado Planificado; por ejemplo, un trabajo a partir del 19 de diciembre de 2012.  
2. En el panel de acciones, haga clic en Plan.
3. Haga clic en Invertir estado del trabajo.
4. Haga clic en Aceptar
    * Esto revertirá el estado del trabajo actual de Planificado a Sin planificar, y lo eliminará del panel de tablero de procesos.   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]