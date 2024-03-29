---
title: Ejecutar trabajos de proceso kanban
description: Este procedimiento se centra en la ejecución de trabajos de procesos kanban.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardWorkCell, KanbanJobStatusUpdate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7ac6f0f6139fe17532f6fbd996b314e0b14f3d90
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566588"
---
# <a name="execute-kanban-process-jobs"></a>Ejecutar trabajos de proceso kanban

[!include [banner](../../includes/banner.md)]

Este procedimiento se centra en la ejecución de trabajos de procesos kanban. El primer trabajo se completa con la cantidad prevista y no tiene errores. El segundo trabajo se completa con errores. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este procedimiento va destinado al operario de la máquina.


## <a name="select-a-kanban-job"></a>Seleccionar un trabajo kanban
1. Vaya a Control de producción > Kanban > Tablero kanban para trabajos de proceso.
2. En el campo Celda de trabajo, haga clic en el botón desplegable para abrir la búsqueda.
3. Haga clic en la fila con el grupo de recursos 1250. Esto filtra la lista Trabajos para mostrar únicamente los trabajos para la celda de trabajo 1250.
    * Marque la fila que tiene el estado de trabajo Planificado.  

## <a name="complete-a-job-with-expected-quantity"></a>Completar un trabajo con cantidad prevista
1. Expanda o contraiga la sección Detalles.
    * En esta sección se muestra información importante sobre el número de la tarjeta, el número de artículo, la cantidad solicitada y el nombre de la actividad.  
2. Expanda o contraiga la sección Instrucciones de producción.
    * En esta sección se muestran las instrucciones de producción para la actividad. Las instrucciones pueden ser texto, imágenes, dibujos y otros documentos.  
3. Haga clic en Inicio.
    * Seleccione un trabajo que no esté completado. Utilice iconos de estado en el campo Estado del trabajo para ver el estado del trabajo.      
4. Haga clic en Completar.
    * El trabajo se completa con la calidad prevista.  

## <a name="complete-a-job-with-errors"></a>Completar un trabajo con errores
1. Haga clic en Inicio.
    * Cuando se complete un trabajo, el siguiente trabajo de la lista se selecciona automáticamente. Este es el motivo por el cual no es necesario seleccionar un trabajo antes de hacer clic en Inicio.  
2. En el panel de acciones, haga clic en Fabricación.
3. Haga clic en Completar (detalles).
4. En la lista, marque la fila seleccionada.
5. En el campo Cantidad con errores, especifique un número.
6. En el campo Cantidad sin errores, especifique un número.
7. Haga clic en Aceptar



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]