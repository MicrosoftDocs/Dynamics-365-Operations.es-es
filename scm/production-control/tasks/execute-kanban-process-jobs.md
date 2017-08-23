--- 
title: Ejecutar trabajos de proceso kanban
description: "Este procedimiento se centra en la ejecución de trabajos de procesos kanban."
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
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 50b5048a5f9277c47444fa69d2c8cc8e36ba7dcd
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="execute-kanban-process-jobs"></a>Ejecutar trabajos de proceso kanban

[!include[task guide banner](../../includes/task-guide-banner.md)]

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


