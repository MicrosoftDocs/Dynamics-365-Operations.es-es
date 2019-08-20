---
title: Transferencia de materiales con trabajos kanban
description: Este procedimiento se centra en la ejecución de un trabajo kanban de retirada para transferir materiales.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanBoardTransferJob
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dedfe39a125e6aa6e9f7ffa62f0d7575153103e1
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835840"
---
# <a name="transfer-materials-with-kanban-jobs"></a>Transferencia de materiales con trabajos kanban

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento se centra en la ejecución de un trabajo kanban de retirada para transferir materiales. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este procedimiento va destinado al trabajador de almacén.


## <a name="display-transfer-jobs"></a>Visualización de trabajos de transferencia
1. Vaya a Control de producción > Kanban > Tablero kanban para trabajos de transferencia.
2. Expanda o contraiga la sección Filtros.
    * En la sección Filtros, puede especificar qué trabajos desea ver filtrando por el flujo de producción, el nombre de la actividad, el almacén y la ubicación de origen y el almacén y la ubicación de destino.  
3. En el campo Almacén de origen, escriba "11".
4. En el campo Ubicación de destino, escriba "12".

## <a name="start-a-transfer-job"></a>Iniciar un trabajo de transferencia
1. En la lista, anule la selección de la fila que esté seleccionada, si la hay.
2. En la lista, seleccione la fila 4.
    * Seleccione el primer trabajo con estado Sin planificar. Asegúrese de que este sea el único trabajo seleccionado.  
3. Haga clic en Inicio.
    * Observe que el icono indica que el trabajo se ha iniciado.  

## <a name="select-a-second-transfer-job-and-change-quantity"></a>Selección de un segundo trabajo de transferencia y cambio de cantidad
1. En la lista, busque y seleccione el registro deseado.
    * Puede tener varios trabajos seleccionados, pero por ahora seleccione la fila 5.  
2. En la lista, busque y seleccione el registro deseado.
    * Asegúrese de que el trabajo en el paso anterior es el único seleccionado. Anule la selección del resto de trabajos.  
3. Observe el valor del campo Cantidad de trabajo para hacer referencia a él más adelante.
4. Defina la cantidad del trabajo en "30".
    * ¡Observe la advertencia! No tiene permiso para transferir 30. De acuerdo con la configuración de la regla kanban, solo puede transferir la cantidad original.  
5. Use el valor observado previamente en el campo Cantidad de trabajo.
    * Defina la cantidad de trabajo en el valor anterior.  

## <a name="start-the-second-transfer-job"></a>Inicio del segundo trabajo de transferencia
1. Haga clic en Inicio.
    * Esto iniciará la transferencia del trabajo en la fila 5.  

## <a name="complete-both-transfer-jobs"></a>Finalización de ambos trabajos de transferencia
1. En la lista, seleccione la fila 4.
    * Ahora hay dos trabajos de transferencia seleccionados en la fila 4 y la fila 5.  
2. Haga clic en Completar.
    * Esto completará la transferencia de los dos trabajos.  

