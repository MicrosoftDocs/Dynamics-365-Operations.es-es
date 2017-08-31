--- 
title: Actualizar estado de trabajos kanban
description: "Cuando un kanban se vacía por error o se debe vaciar un kanban recibido, es necesario actualizar el estado del kanban."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2016
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: caf7dead2da14e1ff76e205e7477b1eb11a2ca52
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="update-kanban-status"></a>Actualizar estado de trabajos kanban

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cuando un kanban se vacía por error o se debe vaciar un kanban recibido, es necesario actualizar el estado del kanban. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este procedimiento se va a utilizar para el supervisor de planta.


## <a name="find-the-kanban"></a>Encuentre el kanban.
1. Vaya a Control de producción > Kanban > Kanbans.
2. Abra el filtro de columna Estado de la unidad de administración de material.
3. Haga clic en Borrar.
    * Esto restablece los filtros.  
4. Use el filtro rápido para buscar registros. Por ejemplo, filtre por el campo Número de tarjeta con un valor de "000149".

## <a name="change-emptied-status-to-received-status"></a>Cambiar el estado vaciado al estado recibido
1. Haga clic en Unidad de gestión de material invertida.
2. Haga clic en Aceptar
    * Observe que el estado de la Unidad de gestión de material es Recibido.  

## <a name="change-received-status-to-emptied-status"></a>Cambiar el estado recibido al estado vaciado
1. Haga clic en Vaciar kanban.
2. En la lista, marque la fila seleccionada.
    * Observe que el estado de la Unidad de gestión de material es Vaciado.  


