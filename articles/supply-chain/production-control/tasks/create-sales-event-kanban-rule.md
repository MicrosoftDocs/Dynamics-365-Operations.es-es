---
title: Crear una regla kanban de eventos de ventas
description: Este procedimiento se centra en la configuración necesaria para crear una regla kanban que se activará durante la creación de pedidos de ventas.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, SalesTableListPage, SalesCreateOrder, SalesTable, LeanPeggingTree
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3cd2b579e542b9f905fc51b63f2120e5a5c883ae
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7566656"
---
# <a name="create-a-sales-event-kanban-rule"></a>Crear una regla kanban de eventos de ventas

[!include [banner](../../includes/banner.md)]

Este procedimiento se centra en la configuración necesaria para crear una regla kanban que se activará durante la creación de pedidos de ventas. La regla kanban de evento reaprovisiona los requisitos que se originan de las líneas de pedidos de ventas. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Está pensado para el ingeniero de procesos o el administrador de flujo de valor, ya que preparan la producción de un producto nuevo o modificado.




## <a name="create-a-new-kanban-rule"></a>Crear una nueva regla kanban
1. Vaya a Reglas kanban.
2. Haga clic en Nuevo.
3. En el campo Estrategia de reabastecimiento, seleccione "Evento".
    * La selección de evento significa que la regla kanban se activa por un evento, por ejemplo, la creación de una línea de pedido de ventas.   Esto se aplica a áreas donde cada kanban debe cubrir una demanda específica.  
4. En el campo Actividad del primer plan, especifique o seleccione un valor.
    * Seleccione Ensamblado final.  
5. Expanda la sección Detalles.
6. En el campo Producto, especifique o seleccione un valor.
    * Seleccione L0050.  

## <a name="define-an-event"></a>Definir un evento
1. Expanda la sección Eventos.
2. En el campo Evento de ventas, seleccione "Automático".
    * Al seleccionar el evento de ventas Automático, esta regla kanban se activará automáticamente cuando una línea de ventas coincida con el producto y la ubicación de recepción. En este procedimiento, es el producto L0050 del almacén 13.  
3. Establezca la Cantidad mínima de eventos en "50".
    * Con una cantidad de evento mínima de 50, la regla kanban solo se activará por eventos con una cantidad de 50 o más.  
4. Expanda la sección Flujo de producción.
    * Observe que la Ubicación de recepción es el almacén 13. Esto significa que esta regla kanban se activará para esta ubicación.  
    * En este ejemplo, una línea de ventas para el producto L0050, con una cantidad de 50 o más, en el almacén 13, activará esta regla kanban.  

## <a name="create-sales-line-to-trigger-event-kanban-rule"></a>Crear línea de ventas para activar la regla kanban de evento
1. Vaya a Todos los pedidos de ventas.
    * Se muestra una advertencia cuando se guarda la regla kanban, lo que significa que los kanbans se crearán en tiempo real durante la creación de pedidos de ventas.  
2. Haga clic en Nuevo.
3. En el campo Cuenta de cliente, especifique o seleccione un valor.
    * Por ejemplo, seleccione US-003.  
4. Haga clic en Aceptar
5. En el campo Código de artículo, escriba 'L0050'.
6. En el campo Sitio, escriba "1".
    * Seleccione el sitio 1 porque el almacén 13 se encuentra en el sitio 1.  
7. En el campo Almacén, especifique o seleccione un valor.
    * Establezca el almacén en 13.  
8. Establezca el valor de cantidad en '75'.
    * Escriba una cantidad de 50 o superior, para activar la regla kanban creada.  

## <a name="verify-that-kanban-is-created"></a>Comprobar que se creó el kanban
1. Haga clic en Producto y suministro.
2. Haga clic en Ver diagrama de árbol.
    * Observe que se crea un kanban con la misma cantidad que la línea de ventas. También puede ver las emisiones de material necesarias para producir L0050. Este es el último paso de este procedimiento.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]