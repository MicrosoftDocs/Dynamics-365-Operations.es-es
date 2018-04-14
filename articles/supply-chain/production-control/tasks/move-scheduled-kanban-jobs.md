--- 
title: Desplazamiento de trabajos kanban programados
description: "Este procedimiento se centra en mover trabajos kanban de proceso planificados a un período diferente."
author: ChristianRytt
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2a12a6859a3a436706822873bc6fdd781e0ef032
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="move-scheduled-kanban-jobs"></a>Desplazamiento de trabajos kanban programados

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento se centra en mover trabajos kanban de proceso planificados a un período diferente. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este procedimiento está pensado para el supervisor de planta o el planificador de producción que trabajan con kanbans.


## <a name="select-scheduled-kanban-jobs"></a>Selección de trabajos kanban programados
1. Gå til Produktionsstyring > Kanban > Tidsplanlægning af kanban-job.
2. !MtCMR!En el campo Celda de trabajo, haga clic en el botón desplegable para abrir la búsqueda. áçêìõý !
3. Markér den valgte række på listen.
    * Seleccione la celda de trabajo 1250.  
4. Klik på Select.
5. Vælg 'Planlagt' i feltet Display job status.
    * Esto filtra la lista de trabajos para mostrar solo los trabajos kanban programados.  

## <a name="move-kanban-jobs-to-a-different-period"></a>Desplazamiento de trabajos kanban a otro período diferente
1. Find og vælg den ønskede post på listen.
    * Seleccione un trabajo con estado de trabajo Planificado, por ejemplo, un trabajo programado el 20 de diciembre de 2012, en el campo Período planificado. A continuación, mueva el trabajo al período anterior.  
2. Klik på Previous period.
3. Klik på End.
    * Esto moverá el trabajo al final de la lista de trabajos como el último trabajo en el período anterior.  
4. Find og vælg den ønskede post på listen.
    * Seleccione un trabajo con estado de trabajo Planificado, por ejemplo, un trabajo programado el 18 de diciembre de 2012 en el campo Período planificado. A continuación, mueva el trabajo al período siguiente.  
5. Klik på Next period.
6. Klik på Start.
    * Esto moverá el trabajo al inicio de la lista de trabajos como el primer trabajo en el período anterior.  

## <a name="task-move-a-job-within-a-period"></a>Tarea: Mover un trabajo dentro de un período
1. Find og vælg den ønskede post på listen.
    * Seleccione un trabajo con estado Planificado, por ejemplo, el segundo trabajo programado el 19 de diciembre de 2012, en el campo Período planificado. A continuación, mueva el trabajo dentro del período planificado.  
2. Klik på Forward.
    * Observe cómo el trabajo baja una línea en la lista.  
3. Klik på Backward.
    * Observe cómo el trabajo sube una línea en la lista.  


