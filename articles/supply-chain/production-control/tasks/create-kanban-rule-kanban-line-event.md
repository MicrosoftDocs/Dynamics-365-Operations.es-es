--- 
title: "Crear una regla kanban con un evento de línea de kanban"
description: "Este procedimiento crea una regla kanban mediante el evento de línea kanban para desencadenar una extracción de una actividad de proceso."
author: ChristianRytt
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 9ef7b8e920d22cbc4f96676e68a263f2da7f232c
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-kanban-rule-using-a-kanban-line-event"></a>Crear una regla kanban con un evento de línea de kanban

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento crea una regla kanban mediante el evento de línea kanban para desencadenar una extracción de una actividad de proceso. La regla kanban es desencadena por una actividad de proceso kanban, con una cantidad igual o superior a 25 cada una. La empresa de datos de prueba utilizada para crear esta tarea es USMF. Esta tarea está pensada para el ingeniero de procesos o el administrador de flujo de valor, conforme preparan la producción de un producto nuevo o modificado en un entorno de producción ajustada.


## <a name="create-a-kanban-rule"></a>Crear una regla kanban
1. Vaya a Gestión de información de productos > Producción ajustada > Reglas kanban.
2. Haga clic en Nuevo.
3. En el campo Estrategia de reabastecimiento, seleccione "Evento".
    * Esto genera kanbans directamente desde la demanda. Se utiliza para configurar las reglas que definen una situación de fabricación sobre pedido.  
4. En el campo Actividad del primer plan, especifique o seleccione un valor.
    * Especifique o seleccione SpeakerAssemblyAndPolish. La primera actividad de una regla kanban de fabricación es una actividad de proceso en el flujo de producción. Cuando selecciona la actividad, las fechas de validez de la actividad se copian en las fechas de validez de la regla kanban.  
5. Expanda la sección Detalles.
6. En el campo Producto, escriba "L0001".
7. Expanda la sección Eventos.
8. En el campo Evento de línea de kanban, seleccione "Automático".
    * Esto genera kanbans de eventos a petición.  Este campo se utiliza para configurar reglas kanban que reabastecen el material necesario para una actividad de proceso en sentido descendente. Al seleccionar Automático, se crean los kanbans de eventos con la demanda. Se recomienda este configuración si espera ejecutar la producción el mismo día.  
9. Establezca la Cantidad mínima de eventos en "25".
    * Se crean kanbans de evento cuando la cantidad de demanda es igual o superior a este campo. Esto es útil si desea producir una cantidad de pedido menor que este campo en una máquina y mayor que este campo en otra máquina.  
10. Haga clic en Guardar.

## <a name="create-sales-order-and-trigger-kanban-chain"></a>Crear el pedido de ventas y desencadenar la cadena kanban
1. Vaya a Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas.
2. Haga clic en Nuevo.
3. En el campo Cuenta de cliente, especifique o seleccione un valor.
    * Seleccione Cuenta de cliente US-003, Forest Wholesales.  
4. Haga clic en Aceptar
5. En el campo Código de artículo, escriba 'L0001'.
    * L0001 es el artículo para el que ha creado la regla kanban.  
6. Establezca el valor de cantidad en '27'.
    * Porque 27 es superior a la cantidad mínima de 25 en la regla kanban, esto desencadenará un kanban de evento.  
7. En el campo Sitio, escriba "1".
8. En el campo Almacén, especifique o seleccione un valor.
    * Seleccione el almacén 13.  
9. Haga clic en Guardar.

## <a name="view-the-kanban-generated-by-the-kanban-rule"></a>Ver el kanban generado por la regla kanban
1. Vaya a Gestión de información de productos > Producción ajustada > Reglas kanban.
2. En la lista, busque y seleccione el registro deseado.
3. Expanda la sección Kanbans.
    * Observe que se creó un kanban para 27 para procesar la actividad basada en la regla kanban creada.  
    * Este es el último paso.  


