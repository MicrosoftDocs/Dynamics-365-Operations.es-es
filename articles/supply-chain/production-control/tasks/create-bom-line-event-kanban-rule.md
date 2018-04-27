--- 
title: "Crear una regla kanban de eventos de línea de L. MAT."
description: "Esta tarea se centra en la configuración necesaria para crear una regla kanban de evento para asegurar el suministro de las líneas de L. MAT de producción en un entorno mixto de producción lean y clásico."
author: ChristianRytt
manager: AnnBe
ms.date: 11/07/2016
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
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 452cc5cf6060b71f91ad43e39e756dc23d759448
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-bom-line-event-kanban-rule"></a>Crear una regla kanban de eventos de línea de L. MAT.

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Esta tarea se centra en la configuración necesaria para crear una regla kanban de evento para asegurar el suministro de las líneas de L. MAT de producción en un entorno mixto de producción lean y clásico. La empresa de datos de prueba utilizada para crear esta tarea es USMF. Esta tarea está pensada para el ingeniero de procesos o el administrador de flujo de valor, ya que preparan la producción de un producto nuevo o modificado.


## <a name="create-a-new-kanban-rule"></a>Crear una nueva regla kanban
1. Vaya a Control de producción > Tareas periódicas > Cálculo de cantidad kanban > Reglas kanban.
2. Haga clic en Nuevo.
3. En el campo Tipo, seleccione "Retirada".
    * El tipo Retirada se usa para crear kanbans de transferencia.  
4. En el campo Estrategia de reabastecimiento, seleccione "Evento".
    * La estrategia de evento se selecciona para crear la transferencia de los kanbans basados en un evento. Más adelante en la guía de tareas, lo desencadenaremos calculando un pedido de producción.  
5. En el campo Actividad del primer plan, especifique o seleccione un valor.
    * Especifique o seleccione ReplenishSpeakerComponents. Esta actividad de transferencia tiene el almacén de recepción (salida) y ubicación 12, lo que significa que el material se moverá a la ubicación 12 del almacén 12.  
6. Expanda la sección Detalles.
7. En el campo Producto, especifique o seleccione M0001.
8. Expanda la sección Eventos.
9. En el campo Evento de línea de L. MAT, seleccione "Automático".
    * Con el campo Evento de línea de L. MAT establecido en Automático, el kanban se creará para satisfacer las necesidades de material para las líneas de L. MAT del pedido de producción.  
10. Cierre la página.

## <a name="create-and-modify-a-new-production-order"></a>Crear y modificar una nueva orden de producción
1. Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.
2. Haga clic en Nuevo pedido de producción.
3. En el campo Número de artículo, especifique o seleccione un valor.
    * Escriba o seleccione “L0001”. Usamos el artículo L0001 porque el artículo M0001 se incluye en la L. MAT para el artículo L0001.  
4. Haga clic en Crear.
5. En la lista, haga clic en el vínculo de la fila para L0001
6. Haga clic en L. MAT.
7. En la lista, haga clic en el vínculo de la fila seleccionada.
8. Haga clic en Editar.
9. En el campo Tipo de línea, seleccione "Suministro asegurado".
    * El suministro asegurado se selecciona para desencadenar la creación de la suministro de un kanban.  
10. Seleccione No en el campo Consumo del recurso.
    * La desactivación de la casilla Consumo del recurso nos permite cambiar el almacén.  
11. Expanda la sección Dimensiones de inventario.
12. En el campo Almacén, escriba "12".
    * El almacén se establece en 12 porque este es el almacén de salida para la actividad de retirada.  
13. En el campo Ubicación, escriba "12".
    * La ubicación se establece en 12 porque este es la ubicación de salida de la actividad de retirada.  
14. Cierre la página.
15. Cierre la página.

## <a name="estimate-the-production-order-and-view-the-kanban-created"></a>Calcular el pedido de producción y ver el kanban creado
1. Haga clic en Estimación.
    * El cálculo del pedido de producción desencadenará la creación del kanban asociado para suministrar el artículo M0001.  
2. Haga clic en Aceptar
3. Cierre la página.
4. Cierre la página.
5. Vaya a Gestión de información de productos > Producción ajustada > Reglas kanban.
6. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Seleccione la regla de kanban de evento creada para el artículo M0001.  
7. Expanda la sección Kanbans.
8. En la lista, marque la fila seleccionada.
    * Observe el kanban creado para suministrar M0001 para el pedido de producción estimado.  
    * Este es el último paso.  


