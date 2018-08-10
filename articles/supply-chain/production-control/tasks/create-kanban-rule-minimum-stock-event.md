--- 
title: "Crear una regla kanban con un evento de existencias mínimas"
description: "Este procedimiento se centra en la configuración necesaria para crear una regla kanban usando un evento de existencias mínimas para garantizar que un producto específico siempre está disponible en una ubicación específica."
author: ChristianRytt
manager: AnnBe
ms.date: 08/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0c480b518925a8536ebb77d60fcf1f1a548b097f
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-kanban-rule-using-a-minimum-stock-event"></a>Crear una regla kanban con un evento de existencias mínimas

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento se centra en la configuración necesaria para crear una regla kanban usando un evento de existencias mínimas para garantizar que un producto específico siempre está disponible en una ubicación específica. Una regla kanban se crea para transferir material a la ubicación cuando el nivel de inventario cae por debajo de 200 piezas. Al ejecutar el procesamiento de eventos de pedidos, se crean los kanbans necesarios. La empresa de datos de prueba utilizada para crear esta tarea es USMF. Esta tarea está pensada para el ingeniero de procesos o el administrador de flujo de valor, conforme preparan la producción de un producto nuevo o modificado en un entorno de producción ajustada.


## <a name="create-a-new-kanban-rule"></a>Crear una nueva regla kanban
1. Vaya a Gestión de información de productos > Producción ajustada > Reglas kanban.
2. Haga clic en Nuevo.
3. En el campo Tipo, seleccione "Retirada".
    * Este tipo se usa para crear kanbans de transferencia.  
4. En el campo Estrategia de reabastecimiento, seleccione "Evento".
    * La estrategia de evento se usa para crear la transferencia de los kanbans basados en un evento. Más adelante en el procedimiento, desencadenará kanbans de transferencia mediante el reabastecimiento de existencias.  
5. En el campo Actividad del primer plan, especifique o seleccione un valor.
    * Especifique o seleccione ReplenishSpeakerComponents. Esta actividad de transferencia tiene el almacén de recepción (salida) y ubicación 12, lo que significa que los materiales se moverán a la ubicación 12 del almacén 12.  
6. Expanda la sección Detalles.
7. En el campo Producto, especifique o seleccione un valor.
    * Seleccione M0007.  
8. Expanda la sección Eventos.
9. En el campo Evento de reabastecimiento de existencias, seleccione "Lote".
    * Esto crea kanbans para satisfacer las necesidades de material en la ubicación relacionada durante el procesamiento de evento de pedido.  

## <a name="set-the-minimum-quantity-for-the-item"></a>Establecer la cantidad mínima para el artículo
1. Haga clic para seguir el vínculo en el campo Producto.
2. Haga clic para seguir el vínculo en el campo Número de artículo.
3. Expanda el cuadro informativo Imagen del producto.
4. En el panel de acciones, haga clic en Plan.
5. Haga clic en Cobertura de artículos.
6. Haga clic en Nuevo.
7. En la lista, marque la fila seleccionada.
8. En el campo Almacén, especifique o seleccione un valor.
    * Establezca el almacén en 12.  
9. Establezca el mínimo en “200".

## <a name="run-the-batch-event-creation-job"></a>Ejecutar el trabajo de creación de eventos por lotes
1. Vaya a Control de producción > Tareas periódicas > Procesamiento por lotes de trabajo kanban > Procesamiento de evento de pedido.
2. Haga clic en Aceptar
3. Vaya a Gestión de información de productos > Producción ajustada > Reglas kanban.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Seleccione la regla kanban que creó anteriormente.  
5. Expanda la sección Kanbans.
    * Observe que un kanban se creó para transferir el material necesario para el almacén 12.  


