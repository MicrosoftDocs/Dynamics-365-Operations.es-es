---
title: Actualizar estado de trabajos kanban
description: Cuando un kanban se vacía por error o se debe vaciar un kanban recibido, es necesario actualizar el estado del kanban.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3fd19febe38d5d0a201d5a50bc57ddb541e12051
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574362"
---
# <a name="update-kanban-status"></a>Actualizar estado de trabajos kanban

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]