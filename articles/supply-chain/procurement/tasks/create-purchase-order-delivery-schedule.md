---
title: Crear un pedido de compra con una programación de entrega
description: En este tema se demuestra cómo crear una programación de entrega para un pedido de compra.
author: RichardLuan
manager: tfehr
ms.date: 08/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventItemIdLookupPurchase, PurchDeliverySchedule, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b8cbcd46e84ca9e718a0f8f59c106147544a3751
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5021813"
---
# <a name="create-a-purchase-order-with-a-delivery-schedule"></a>Crear un pedido de compra con una programación de entrega

[!include [banner](../../includes/banner.md)]

En este tema se demuestra cómo crear una programación de entrega para un pedido de compra. Se usa una programación de entrega cuando se solicita que se entregue una cantidad de un pedido o un diario en varios envíos. El ejemplo mostrado en esta guía se puede utilizar en la empresa de datos de demostración USMF. Este procedimiento normalmente lo haría un agente de compras.

## <a name="create-a-delivery-schedule"></a>Crear una programación de entrega
1. En el panel de exploración, vaya a **Módulos > Adquisición y abastecimiento > Pedidos de compra > Todos los pedidos de compra**.
2. En el panel de acciones, haga clic en **Nueva**.
3. En el campo **Cuenta de proveedor**, escriba `US-101`.
4. Seleccione **Aceptar**.
5. En el campo **Número de artículo**, especifique `M0001`.
6. En el campo **Cantidad**, especifique `10`.
7. Seleccione **Línea de pedido de compra**.
8. Seleccione **Programación de entrega**.
- La página **Programación de entrega** le permite especificar el número de envíos en los que la cantidad total de la línea de pedido se entregará desde el proveedor.  
- De forma predeterminada, el sistema copia la cantidad total y otros detalles de entrega de la línea de compra original en la primera línea de la programación de entrega. En este ejemplo, crearemos una programación para dos envíos, con la fecha del segundo envío una semana después que la del primero.  
9. En el campo **Cantidad**, cambie la cantidad a `4`.
10. Seleccione **Nuevo**.
11. En el campo **Cantidad**, escriba `6` como la cantidad restante.
- En el campo Fecha de entrega, seleccione una fecha que sea una semana posterior de la fecha de la primera línea de entrega.  
- Puede realizar un seguimiento de la cantidad total que está asignada a las líneas de la programación de entrega si mira los campos **Total** y **Restante**. Cuando la cantidad restante es cero, la cantidad completa de la línea original se ha asignado a la programación.  
12. Expanda la sección **Conversión de gastos**.
- Las opciones aquí permiten controlar cómo se quiere que se distribuyan los gastos en las líneas de programación de entrega. Si selecciona **Copiar importes brutos**, el importe de gasto de la línea del pedido original se copia en cada línea de entrega. La opción **Asignar a líneas de entrega** divide el gasto de línea original en función de la cantidad de cada línea de entrega.  
13. Contraiga la sección **Conversión de gastos**.
14. Seleccione **Aceptar**.
- La programación de entrega se ha aplicado ahora al pedido.  
- La línea de pedido original, ahora conocida como línea comercial, se ha convertido en una línea de pedido con varias entregas. Está marcada con un icono diferenciado y actúa como un encabezado para las líneas de entrega.  
15. Seleccione la segunda línea del pedido, que es la primera de las dos líneas de entrega.
- Las dos líneas nuevas, designadas Líneas de entrega, forman una programación de entrega. El pedido se procesará con dichas líneas y no con la línea original. Si los documentos como confirmaciones, diarios de recepción de productos o facturas se imprimen, solo se muestran las líneas de entrega.  

## <a name="change-the-delivery-schedule"></a>Cambiar la programación de entrega
Puede cambiar la cantidad en las líneas de entrega. Si hace esto, la línea comercial se actualiza automáticamente a la cantidad total de las líneas de entrega.  
1. En el campo **Cantidad** de la primera línea de entrega, cambie la cantidad de `4` a `5`.
2. Seleccione la primera línea de pedido (la línea comercial).  
- La cantidad de la línea comercial se ha cambiado a 11.  

## <a name="process-product-receipt-using-delivery-schedules"></a>Procesar la recepción de producto con programaciones de entrega
Se debe confirmar el pedido de compra para que se pueda procesar la recepción de producto. En este ejemplo, la recepción se registra directamente en el pedido de compra. La recepción también se podría haber registrado cuando las mercancías llegaron al almacén.  
1. En el panel de acciones, selecione **Compra.**
2. Seleccione **Confirmar**.
3. En el panel de acciones, seleccione **Recibir**.
4. Seleccione **Recepción de producto**. En el campo **Recepción de producto**, escriba cualquier valor.
- Este campo se utiliza para especificar una referencia que se usará como asiento para el diario de recepción de productos.  
- En el campo **Cantidad**, seleccione **Cantidad pedida**. Esta opción significa que la recepción se procesará para la cantidad con la que se crearon las líneas de pedido.  
- Asegúrese de que el campo **Imprimir recepción de producto** se establece en **No**. La impresión no es necesaria en este ejemplo.  
5. Expanda la sección **Líneas**.
- Observe cómo se crea la recepción de producto para las dos líneas de entrega y no la línea de pedido original. Si la recepción se ha registrado en el almacén, también se habría registrado en las líneas de programación de entrega.  
6. Contraiga la sección **Líneas**.
7. Seleccione **Aceptar** para registrar la recepción.

