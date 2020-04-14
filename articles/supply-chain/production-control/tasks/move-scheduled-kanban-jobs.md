---
title: Desplazamiento de trabajos kanban programados
description: Este procedimiento se centra en mover trabajos kanban de proceso planificados a un período diferente.
author: ChristianRytt
manager: AnnBe
ms.date: 11/07/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanJobSchedulingListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: cad61ad292f80d6092ecea679645f729469b8a8f
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149007"
---
# <a name="move-scheduled-kanban-jobs"></a>Desplazamiento de trabajos kanban programados

[!include [banner](../../includes/banner.md)]

Este procedimiento se centra en mover trabajos kanban de proceso planificados a un período diferente. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este procedimiento está pensado para el supervisor de planta o el planificador de producción que trabajan con kanbans.

## <a name="select-scheduled-kanban-jobs"></a>Selección de trabajos kanban programados. 

1. Vaya a **Control de producción > Kanban > Programación de trabajos kanban**. 

2. En el campo **Celda de trabajo**, haga clic en el botón desplegable para abrir la búsqueda. 

3. En la lista, marque la fila seleccionada. 
   - Seleccione la celda de trabajo 1250. 
4. Haga clic en **Seleccionar**. 

5. En el campo **Mostrar estado del trabajo**, seleccione **Programado**. Esto filtra la lista de trabajos para mostrar solo los trabajos kanban programados. 

## <a name="move-kanban-jobs-to-a-different-period"></a>Desplazamiento de trabajos kanban a otro período diferente. 

1. En la lista, busque y seleccione el registro deseado. Seleccione un trabajo con estado de **trabajo Planificado**, por ejemplo, un trabajo programado el 20 de diciembre de 2012, en el campo **Período planificado**. A continuación, mueva el trabajo al período anterior. 

2. Haga clic en **Período anterior**. 

3. Haga clic en **Fin** para mover el trabajo al final de la lista de trabajos como el último trabajo en el período anterior. 

4. En la lista, busque y seleccione el registro deseado. Seleccione un trabajo con estado de **trabajo Planificado**, por ejemplo, un trabajo programado el 18 de diciembre de 2012, en el campo **Período planificado**. A continuación, mueva el trabajo al período siguiente. 

5. Haga clic en **Período siguiente**. 

6. Haga clic en **Inicio** para mover el trabajo al inicio de la lista de trabajos como el primer trabajo en el período anterior. 

## <a name="move-a-job-within-a-period"></a>Mover un trabajo dentro de un período. 

1. En la lista, busque y seleccione el registro deseado. Seleccione un trabajo con estado Planificado, por ejemplo, el segundo trabajo programado el 19 de diciembre de 2012, en el campo **Período planificado**. A continuación, mueva el trabajo dentro del período planificado. 

2. Haga clic en **Hacia adelante.** Observe cómo el trabajo baja una línea en la lista. 

3. Haga clic en **Regresivo**. Observe cómo el trabajo sube una línea en la lista.
