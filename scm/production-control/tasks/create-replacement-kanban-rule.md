--- 
title: "Crear una nueva regla kanban de sustitución"
description: "Este procedimiento se centra en el reemplazo de una regla kanban existente por una nueva regla kanban en una fecha específica."
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
ms.openlocfilehash: 58b12edbbdcf77429c32193dfd850bc53f4c26a8
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="create-a-replacement-kanban-rule"></a>Crear una nueva regla kanban de sustitución

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento se centra en el reemplazo de una regla kanban existente por una nueva regla kanban en una fecha específica. Esto es útil cuando los cambios del flujo de producción o las reglas de reabastecimiento necesitan coordinarse y programarse. La empresa de datos de demostración usada para crear el procedimiento es USMF. Este procedimiento está pensado para el ingeniero de procesos o el administrador de flujo de valor cuando preparan la producción para un flujo de producción cambiado o una nueva regla de reabastecimiento. Esta tarea reemplaza la regla kanban 000022 por una nueva regla y aumenta la cantidad máxima de 48 a 100 para la nueva regla.


## <a name="select-a-kanban-rule-to-replace"></a>Seleccionar una regla kanban para reemplazar
1. Vaya a Reglas kanban.
2. En la lista, busque y seleccione el registro deseado.
    * Seleccione una regla 000022.  

## <a name="create-a-replacement-kanban-rule"></a>Crear una nueva regla kanban de sustitución
1. Haga clic en Reemplazar regla kanban.
2. En el campo Fecha de vigencia, especifique una fecha y una hora.
    * Seleccione una fecha en el futuro, por ejemplo, una semana desde ahora. Esta es la fecha y la hora en la que la nueva regla kanban se convierte en activa y reemplaza la regla kanban anterior.  
    * Si la regla kanban cambia la ruta en el flujo de producción, se puede seleccionar otra actividad.  En este procedimiento, mantendremos la actividad sin tocar.  
3. Haga clic en Aceptar
    * Observe que se crea una nueva regla kanban para reemplazar la regla kanban 000022.  
    * La fecha de vigencia se establece en función de la fecha elegida cuando reemplaza la regla kanban.  
4. En la lista, busque y seleccione el registro deseado.
    * Seleccione la regla kanban reemplazada 000022.  
    * Observe que la regla kanban reemplazada tiene la misma fecha que la fecha de vencimiento ya que es la fecha de cuándo expirará.  
5. En la lista, seleccione la fila 1.
    * Seleccione la nueva regla kanban en la parte superior de la lista. Esta es la regla kanban con el número regla kanban mayor.  
6. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Haga clic en el número de la regla kanban para abrir la regla kanban.  

## <a name="modify-maximum-quantity-for-the-replacement-kanban-rule"></a>Modificar la cantidad máxima para la regla kanban de sustitución
1. Defina la cantidad máxima en "100".
    * Expanda la ficha desplegable Cantidades para ver el campo Cantidad máxima. El cambio de la cantidad máxima a 100 le permitirá que se procesen hasta 100 kanbans.    Este es el último paso de esta tarea.  


