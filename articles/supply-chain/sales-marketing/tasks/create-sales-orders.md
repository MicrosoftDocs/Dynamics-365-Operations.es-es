---
title: Crear pedidos de ventas
description: Este procedimiento muestra cómo crear un pedido de ventas.
author: omulvad
manager: tfehr
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable, InventDimParmFixed, InventProductDimensionLookup, SalesTotals
audience: Application User, SalesTableDelete, SalesTableListPagePreviewPage, SalesUpdateRemain
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9aa353ad771844abc0860f06d9bc22b9f4adce92
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436657"
---
# <a name="create-sales-orders"></a>Crear pedidos de ventas

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo crear un pedido de ventas. Puede utilizar el procedimiento en la empresa USMF de los datos de prueba. Normalmente los pedidos de ventas los crea un procesador del pedido de ventas. 

## <a name="enter-sales-order-header-details"></a>Especificar los detalles del encabezado del pedido de ventas
1. Vaya a **Panel de navegación > Módulos > Ventas y marketing > Pedidos de ventas > Todos los pedidos de ventas**.
2. Seleccione **Nuevo**.
3. En el campo **Cuenta de cliente**, seleccione el botón desplegable para abrir la búsqueda.
4. En la lista, busque y seleccione el registro del cliente.
    - Para este ejemplo, seleccione el número de cliente US-004.  
5. Seleccione **Aceptar**.

## <a name="enter-sales-order-line-details"></a>Especificar los detalles de línea del pedido de ventas
    
Los productos vendidos por la organización pueden venir en variantes que se diferencian por dimensiones como configuración, color, tamaño y estilo. Además, los productos se pueden configurar para usar dimensiones de almacenamiento, como sitio, almacén y pallet, y dimensiones de bastidor, como lote y números de serie. Cuando se asignan estas dimensiones, debe seleccionar valores para las dimensiones de la línea de pedido. Para mejorar la eficacia de entrada de pedidos, puede decidir agregar los campos de dimensión respectivos a la cuadrícula del pedido.
    
1. En la sección **Líneas de pedido de ventas**, seleccione **Línea de pedido de ventas**.
2. Seleccione **Dimensiones**.
    
    Para este ejemplo, seleccione las dimensiones de color, sitio y almacén. Las dimensiones que seleccione aquí aparecerán en la cuadrícula del pedido de ventas. Si desea que persistan sus selecciones, establezca la opción **Guardar configuración** en Sí.
    
3. Seleccione **Aceptar**.
4. En el campo **Código de artículo**, seleccione el botón desplegable para abrir la búsqueda.
5. Para este ejemplo, seleccione el código de artículo T0004.
    - Si el artículo forma parte de una categoría de ventas, el nombre del artículo aparecerá automáticamente en el campo Categoría de ventas.  
    - Si los campos de dimensión del producto contienen ya un valor, esto se debe a que el valor se ha copiado del registro de producto donde se define como dimensión de producto predeterminada. Puede cambiar el valor predeterminado en cualquier momento.   
6. En el campo **Color**, seleccione el botón desplegable para abrir la búsqueda.
7. En la lista, busque y seleccione el registro deseado.
8. En el campo **Cantidad**, especifique un número.
    - Si el artículo se vende en unidades distintas a las que se usaron cuando se compró, se produjo y se almacenó, y hay una unidad de ventas de medida establecida en el registro de producto, este valor se mostrará en el campo **Unidad**. Puede modificar el valor en cualquier momento.   
    - Si el campo **Sitio** ya contiene un valor, este se ha copiado del encabezado del pedido o de la configuración de pedido asociados con el producto. Puede modificar el valor en cualquier momento. Si el campo está vacío, seleccione un valor.   
    - Si el campo **Precio unitario** ya contiene un valor, este se ha copiado de un acuerdo comercial válido o del registro de producto. (El precio unitario también puede provenir de un acuerdo de venta, pero el proceso para crear pedidos de ventas de acuerdos de venta es diferente al que está que se muestra aquí). Si el campo está vacío, escriba un valor.   
    - El campo **Descuento** incluye un importe de descuento por unidad de producto. Para calcular el importe bruto de descuento de línea, el valor del descuento se multiplica por la cantidad de línea. Si el campo **Descuento** ya contiene un valor, este se ha copiado de un acuerdo comercial válido. Si el campo está vacío y desea otorgar al cliente un descuento de línea, escriba un valor.  
    - El campo **Porcentaje de descuento** contiene un valor de porcentaje en el que se va a reducir la línea importe bruto total.  Si el campo **Porcentaje de descuento** ya contiene un valor, este se ha copiado de un acuerdo comercial válido. Si el campo está vacío y desea otorgar al cliente un descuento de línea, escriba un valor. 
    - El campo **Importe neto** contiene un valor que se calcula en función de la cantidad de la línea y el precio unitario ajustado con descuentos.  Puede reemplazar el valor calculado por otro diferente.  

## <a name="review-the-order-totals"></a>Revisar los totales del pedido
1. En el **Panel de acciones**, seleccione **Pedido de ventas**.
2. Seleccione **Totales**.
    
    La página **Totales** muestra los detalles sobre todo el pedido. Esto incluye el importe del subtotal, que es una suma de todos los importes netos de línea ajustados según los eventuales descuentos de línea, el importe bruto de factura, que es un importe subtotal ajustado en función de eventuales descuentos, gastos e impuestos del nivel de pedido, la situación de límite de crédito del cliente, etc. El importe de la factura es el importe que aparecerá en el documento de factura del cliente.  
    
3. Seleccione **Aceptar**.
