---
title: Creación de pedido de devolución de compra
description: Este procedimiento le muestra cómo crear un pedido de devolución de compras con la acción Nota de abono para copiar líneas de un documento de factura de proveedor a un nuevo pedido de compra.
author: RichardLuan
manager: tfehr
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, PurchCopying, InventMarking, PurchEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 10b3e695ffcd44909be4781eac5d4eaeef199b03
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017068"
---
# <a name="create-a-purchase-return-order"></a>Creación de pedido de devolución de compra

[!include [banner](../../includes/banner.md)]

Este procedimiento le muestra cómo crear un pedido de devolución de compras con la acción Nota de abono para copiar líneas de un documento de factura de proveedor a un nuevo pedido de compra. También le muestra cómo confirmar el pedido y procesar el envío de las mercancías de vuelta al proveedor. El ejemplo mostrado en este procedimiento se puede utilizar en la empresa de datos de demostración USMF. Esta tarea la realizaría normalmente un agente de compras.

## <a name="create-a-new-purchase-return-order"></a>Crear un nuevo pedido de devolución de compras
1. Vaya a **Panel de exploración, Módulos > Adquisición y abastecimiento > Pedidos de compra > Todos los pedidos de compra**. El primer paso es crear un nuevo pedido de compra para usarlo como el pedido de devolución de compra.  
2. Haga clic en **Nuevo**.
3. En el campo **Cuenta de proveedor**, escriba "US-102".
4. Haga clic en **Aceptar**.
5. En el **Panel Acciones**, haga clic en **Compra**.
6. Haga clic en **Nota de abono**. Esta es la página desde la que puede copiar desde una factura de proveedor existente a su pedido de devolución. Esta es la misma página que se utiliza para otras acciones de copia. Sin embargo, como la abrimos desde la acción Nota de abono, la página se configura para admitir la creación de un pedido de devolución que compense facturas de proveedor.  
7. Expanda la sección **Parámetros**.
    - La opción **Invertir el signo** se selecciona automáticamente y no se puede cambiar. Esto garantiza que el signo se cambia para las cantidades y que las líneas de pedido que se agreguen compensarán la factura de proveedor.  
    - La opción **Copiar gastos** se selecciona automáticamente y no se puede cambiar. Esto significa que los cargos de la factura de proveedor se agregan al pedido de devolución de compra para compensar el cargo original. Es posible modificar los cambios en las líneas y encabezado de pedido más adelante.  
    - La opción **Copiar con exactitud** se selecciona automáticamente y no se puede cambiar. Esto garantiza que se realiza una copia exacta de los valores en todos los campos de las líneas y encabezado de la factura de proveedor. Esto significa que un pedido de devolución de compra se crea con valores que coindicen con todos los términos usados con el documento de la factura de proveedor. 
    - La opción **Eliminar las líneas de compra** elimina cualquier línea de pedido de compra que ya existe en el pedido de compra antes de agregar las líneas nuevas. En este ejemplo todavía no hemos agregado líneas al pedido de devolución de compra, por lo que no se produciría ningún efecto. Utilice esta opción con precaución, ya que elimina todas las líneas existentes sin ninguna advertencia adicional.  
    * La opción **Copiar la cabecera de pedido** se selecciona automáticamente y no se puede cambiar. Esto garantiza que la información se copia de la factura de proveedor y se aplica al encabezado del pedido de devolución de compra. Esto es útil porque ayuda a garantizar de que el pedido de devolución de compra compensa la factura con términos similares.  
8. Contraiga la sección **Parámetros**.
9. Expanda la sección **Facturas**. La página se ha abierto desde la acción Nota de abono, por lo que la única opción disponible es copiar la información de facturas de proveedor. Esta etiqueta muestra todas las facturas disponibles para la cuenta de proveedor que se especifica en el pedido de devolución de compra que ha creado anteriormente.   Las facturas se identifican por el asiento de factura o los id. de pedido de compra.
10. Localice la factura de proveedor identificada por el número de factura AP-0006 y resalte esa línea haciendo clic en cualquier campo de esa línea.
11. Para seleccionar la línea, haga clic en la casilla para la línea. Observe que las líneas disponibles en la factura de proveedor se seleccionan automáticamente junto con el pedido. Esta factura de proveedor concreta tiene 2 líneas de pedido. Para este ejemplo, devolveremos parte de la cantidad de la segunda línea.
12. Para resaltar la segunda línea (la que está con el artículo M0006), haga clic en cualquier campo de esa línea.
13. En el campo **Cantidad**, cambie la cantidad a 10. Esta es la cantidad que devolveremos al proveedor. 
14. Para resaltar la primera línea (la que está con el artículo M0005), haga clic en cualquier campo de esa línea.
15. Desactive la casilla para la línea. Solo las líneas que ha seleccionado se copiarán en su pedido.
16. Contraiga la sección **Facturas**.
17. Expanda la sección **Líneas o encabezados seleccionados que se copiarán**. Esta vista le muestra un resumen de todos los documentos y líneas que ha seleccionado para copiarlas en su pedido.  
18. Contraiga la sección **Líneas o encabezados seleccionados que se copiarán**.
19. Haga clic en **Aceptar**. La línea que ha seleccionado se ha copiado ahora en su pedido de devolución de compras. El campo **Cantidad** muestra -10.   
20. En la sección **Línea de pedido de compra** , haga clic en **Inventario**.
21. Haga clic en **Marcado**. La línea de pedido que se creó se marca en la transacción de inventario de la factura del vendedor. Esto garantiza que el inventario que se devuelve al proveedor es el mismo que el inventario que se recibió de ellos anteriormente. Hay algunas situaciones en las que no se produce el marcado, por ejemplo, si el inventario ya se ha marcado como Consumido o si el producto es uno que no utiliza el marcado.  

22. Haga clic en **Aceptar**.

## <a name="confirm-and-record-the-shipment-of-goods"></a>Confirmar y registrar el envío de mercancías
1. Haga clic en **Acciones > confirmar**.
2. En el **Panel Acciones**, haga clic en **Recibir**.
3. Haga clic en **Recepción de producto.**
    - Esta página se utiliza para registrar la recepción de producto para pedidos de compra y también para procesar la devolución de las mercancías al proveedor. Las líneas de pedido con una cantidad negativa significa que se tienen que devolver al proveedor y que el documento que se puede generar de esta página se puede utilizar como albarán para este uso.   
    - En el campo **Cantidad**, seleccione la Cantidad pedida para este ejemplo. Esto garantiza que el envío se procesará para la cantidad pedida completa con la que se crearon las líneas de pedido.   
4. En el campo **Recepción de producto**, escriba un valor. Este campo se utiliza para especificar una referencia que se usará como asiento para el diario de recepción de productos.  
5. Haga clic en **Aceptar**. Las mercancías se han registrado ahora como enviadas en el pedido de devolución de compras y se ha creado un diario de recepción de producto. Puede utilizar la acción Recepción de producto para revisar los diarios creados con el pedido de compra y ver qué se ha recibido o devuelto, y cuándo.  

