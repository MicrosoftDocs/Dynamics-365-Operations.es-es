---
title: Crear un pedido de compra
description: Este artículo muestra cómo crear un pedido de compra manualmente.
author: GalynaFedorova
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder, InventDimParmFixed, InventItemIdLookupPurchase, InventProductDimensionLookup, PurchTotals
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a04a9f4a512a307efecb19703cd3df638ba5ff5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856088"
---
# <a name="create-a-purchase-order"></a>Crear un pedido de compra

[!include [banner](../../includes/banner.md)]

Este artículo muestra cómo crear un pedido de compra manualmente. Es más habitual que los pedidos de compra se crean automáticamente como resultado de la planificación maestra, de la entrega directa y de otros procesos. Los pedidos de compra normalmente se crean por un agente de compras. El ejemplo que se muestra aquí se puede usar en la empresa de datos de demostración USMF mediante los valores que se sugieren en las notas para los distintos pasos.


## <a name="create-the-purchase-order-header"></a>Crear el encabezado del pedido de compra
1. Vaya a **Panel de exploración, Módulos > Adquisición y abastecimiento > Pedidos de compra > Todos los pedidos de compra**.
2. Seleccione **Nuevo**.
3. Seleccione la cuenta de proveedor **US-101**. Cuando selecciona un proveedor, los detalles del registro de proveedores como la dirección, la cuenta de facturación, las condiciones y el modo de entrega se copiarán como valores predeterminados en el encabezado de pedido. Puede cambiar estos valores cuando lo desee.  
4. Expanda la sección **General**.

    - El campo **Sitio** junto con el campo **Almacén** especifica donde deben entregarse los bienes o servicios adquiridos. La dirección de entrega predeterminada es el sitio. Ambos campos se pueden rellenar con valores configurados para el proveedor seleccionado o puede especificarlos manualmente.  
    - El campo **Fecha de entrega** se usa para especificar cuándo se deben entregar las mercancías y los servicios adquiridos. Puede especificar una sola fecha de entrega para el pedido o se les puede dar fechas de entrega únicas a las líneas de pedido individuales. Si la fecha de entrega especificada aquí no se puede cumplir para productos o servicios concretos dado que tienen plazos más largos, se crearán esas líneas con una fecha de entrega posterior para responder a esto.  

5. Expanda la sección **Administración**. El campo **Pedido** se puede utilizar para especificar quién está configurando el pedido. Esto puede ser conveniente para compartir con el proveedor en el caso de que necesiten ponerse en contacto con esa persona. Al campo se le puede asignar un valor automáticamente si la cuenta del usuario actual está asociada a un nombre en la página **Usuarios**.  
6. Seleccione **Aceptar**. Ahora se ha creado el encabezado de pedido. Cuando trabaje con líneas de pedido de compra, solo se mostrará un resumen de la información de encabezado. Si necesita ver el resto de la información, seleccione **Encabezado**.  

## <a name="add-a-purchase-order-line"></a>Agregar una línea de pedido de compra
1. Seleccione **Línea de pedido de compra**.
2. Seleccione **Dimensiones**. Los productos pueden estar en variantes que se diferencian por dimensiones, como color, tamaño o estilo. También se pueden configurar los productos para usar dimensiones de almacenamiento, como el sitio y el almacén. También hay dimensiones de seguimiento opcionales, como números de serie y lote. Para mejorar la eficacia de la entrada de pedidos, puede agregar los campos de dimensión que usa comúnmente directamente a la cuadrícula del pedido.  
3. Active la casilla **Color**. Opcional: si selecciona el campo **Guardar configuración**, las dimensiones que haya elegido también se mostrarán en la cuadrícula de la línea de pedido la próxima vez que abra la página del pedido de compra.  
4. Seleccione **Aceptar**.
5. En el campo **Código de artículo**, seleccione **T0004**.

    - Las líneas de pedido se crean para productos y servicios especificando un número de artículo, o como gastos especificando una categoría de compras. 
    - El campo **Categoría** de compras se usa para agregar líneas en las que los artículos adquiridos se gastan directamente, en lugar de entrar en inventario. Esto significa que si necesita gastar una compra puede hacerlo creando una línea de pedido de compra que especifique una categoría de compras, en lugar de crear una línea con un número de artículo. Los artículos también se pueden asociar con una categoría de compras y en este caso, la categoría de compras se muestra solo como informativa.  

6. En el campo **Color**, especifique o seleccione un valor. Los campos **Sitio** y **Almacén** se rellenan normalmente con valores del encabezado de pedido, pero es posible anular los campos si algunas líneas debe entregarse a ubicaciones diferentes.  
7. En el campo **Cantidad**, especifique un número.

    - Seleccione la cantidad que se desea adquirir. El campo **Cantidad** se rellena automáticamente con la cantidad de pedido mínima para el producto si se configura, o con el valor de 1.  
    - El campo **Unidad** indica la unidad de medida para la cantidad pedida. Normalmente, la unidad se proporciona automáticamente desde la unidad de compra en los datos maestro del producto, pero puede cambiarlo.  
    - El campo **Precio unitario** contiene normalmente un valor de un acuerdo de compra o de un acuerdo comercial. Es posible cambiar el precio unitario en líneas de pedido individuales, por ejemplo, si un precio único se negocia con el proveedor.  
    - El campo **Descuento** representa un importe de descuento por unidad. Por tanto, este descuento reduce el precio unitario por el descuento. Este descuento se suministra normalmente de manera automática desde acuerdos de compra o acuerdos comerciales, pero es posible anularlo en líneas individuales si se han negociado descuentos únicos con el proveedor.  
    - Se puede especificar un porcentaje de descuento que deduzca el importe neto para la línea según corresponda. El porcentaje de descuento se suministra a menudo de manera automática desde acuerdos de compra o acuerdos comerciales, pero es posible anularlo en líneas individuales si se ha negociado un porcentaje de descuento único con el proveedor.  
    - El valor del campo **Importe neto** se calcula desde otros campos de la línea que incluyen la cantidad, el precio unitario, el descuento y el porcentaje de descuento. Es posible cambiar el Importe neto, pero entonces los campos **Precio unitario**, **Descuento** y **Porcentaje de descuento** estarán en blanco y cuando registre hacia la línea, el importe registrado será proporcional al importe neto. Normalmente el campo **Importe neto** solo se usa para mostrar el importe neto de la línea.  

8. Expanda la sección **Detalles de línea.**
9. Seleccione la ficha **Entrega**. Se puede asignar una fecha de entrega única a cada línea de pedido. La fecha se hereda del campo del encabezado del pedido de compra, pero puede cambiarla.  

## <a name="review-order-totals"></a>Revisar totales del pedido
1. Seleccione **Totales**.

    - Si no ve la acción **Totales**, haga clic en la pestaña **Pedido de compra** en el panel Acciones.  
    - Este cuadro de diálogo muestra los totales para todo el pedido.  
    - El campo **Selección** le permite cambiar la base de cómo se calculan los totales. Por ejemplo, podría elegir la **Cantidad de recepción de producto** para mostrar los totales relacionados con el importe de los productos que se han recibido o la **Cantidad pedida para mostrar** el importe del producto que se ha pedido.  

2. Seleccione **Aceptar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]