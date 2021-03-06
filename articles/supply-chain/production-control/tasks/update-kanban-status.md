---
title: Actualizar estado de trabajos kanban
description: Cuando un kanban se vacía por error o se debe vaciar un kanban recibido, es necesario actualizar el estado del kanban.
author: ChristianRytt
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Kanban, KanbanResetEmpty
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 5a0e03da4671ffec4ecf4835b20a00ef87971c94
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5831827"
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