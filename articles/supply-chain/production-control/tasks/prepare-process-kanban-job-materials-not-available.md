---
title: Preparación de un trabajo kanban de proceso cuando los materiales no están disponibles para la celda de trabajo
description: Este procedimiento se centra en la preparación de un trabajo kanban de proceso cuando algunos materiales no están disponibles para la celda de trabajo, por lo que es necesario seleccionar materiales del almacén.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanBoardWorkCell
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f75cdbc6ce6f7e427bf266c90428d73c065eac3
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7576745"
---
# <a name="prepare-a-process-kanban-job-when-materials-are-not-available-for-the-work-cell"></a>Preparación de un trabajo kanban de proceso cuando los materiales no están disponibles para la celda de trabajo

[!include [banner](../../includes/banner.md)]

Este procedimiento se centra en la preparación de un trabajo kanban de proceso cuando algunos materiales no están disponibles para la celda de trabajo, por lo que es necesario seleccionar materiales del almacén. Para poder crear este procedimiento, es preciso haber realizado el procedimiento de preparación de un trabajo kanban de proceso cuando los materiales están disponibles. Este procedimiento va destinado al operario de la máquina. La empresa de datos de prueba utilizada para crear este procedimiento es USMF.

1. Vaya a Control de producción > Kanban > Tablero kanban para trabajos de proceso.
2. En el campo Celda de trabajo, haga clic en el botón desplegable para abrir la búsqueda.
3. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Seleccione la celda de trabajo 1250.  
4. En la lista, busque y seleccione el registro deseado.
    * Seleccione Kanban 000356.  
5. En la lista, busque y seleccione el registro deseado.
    * En la lista, desmarque la fila 4. o seleccione la fila 4 si no ha completado la tarea de "Preparación de un proceso de trabajo kanban cuando los materiales están disponibles".  
6. Expanda la sección de la lista de selección.
    * El icono de prohibido en el estado de suministro indica que faltan 48 unidades del artículo P0002 para la celda de trabajo.  

## <a name="transfer-materials-to-work-cell"></a>Transferencia de materiales a la celda de trabajo
1. Expanda la sección Transferir trabajos.
2. Use un filtro rápido para filtrar por el campo Código de artículo con el valor 'P0002'.
3. En la lista, busque y seleccione el registro deseado.
4. Haga clic en Inicio.
    * El proceso de transferencia está en curso.  
5. Haga clic en Completar.
    * El artículo P0002 está ahora disponible en la lista de selección para el trabajo kanban. Esto significa que podemos preparar el kanban con todos los materiales necesarios.  
6. Haga clic en Preparar.
    * Observe que un icono en el estado del trabajo indica que el trabajo está ahora listo.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]