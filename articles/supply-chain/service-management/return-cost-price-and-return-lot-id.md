---
title: "Precio de coste de la devolución e identificador de lote interno de devolución"
description: "Puede que desee que el coste de productos devueltos sea igual al coste que tenían los productos cuando se vendieron al cliente. Puede hacerlo utilizando el **Id. de devolución de lote**."
author: ShylaThompson
manager: AnnBe
ms.date: 04/30/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReturnTableListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: ShylaThompson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: aeba56128ab6c9ab7d244bdf153faba8e96069d6
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="return-cost-price-and-return-lot-id"></a>Precio de coste de la devolución e identificador de lote interno de devolución        

[!include [banner](../includes/banner.md)]



El coste de los productos que se devuelven al inventario se calcula mediante el coste actual de los productos. Sin embargo, puede que desee que el coste de productos devueltos sea igual al coste que tenían los productos cuando se vendieron al cliente. Puede hacerlo utilizando el campo **Id. de devolución de lote** de la ficha desplegable **Detalles de línea** en el formulario **Pedido de ventas**.

Por ejemplo, considere el siguiente escenario. Envía una factura a un cliente. El cliente devuelve posteriormente los productos entregados. Se devuelven los productos a las existencias. En este caso, al abonar al cliente los productos devueltos, el coste de los productos se calcula con su coste actual. Sin embargo, si usa el campo **Id. de devolución de lote**, el coste de los productos devueltos se calculará con el coste de la factura de venta original del cliente.

Para usar un coste distinto al coste actual para devoluciones de un cliente, use uno de los siguientes métodos.

## <a name="method-1-manually-enter-the-return-cost-price"></a>Método 1: especifique manualmente el precio de coste de devolución

De forma predeterminada, al agregar artículos a un pedido de devolución, los artículos se devuelven al inventario al precio de coste actual. Para especificar otro precio de coste de devolución, siga estos pasos.

1.  Haga clic en **Ventas y marketing** \> **Común** \> **Pedidos de devolución** \> **Todos los pedidos de devolución**.

2.  En el **Panel de acciones**, en el grupo **Nuevo**, haga clic en **Pedido de devolución**.

3.  En el formulario **Crear pedido de devolución**, seleccione una cuenta de cliente y, a continuación hacen clic en **Aceptar**.

4.  En el formulario **Pedido de devolución - Número de RMA: %1, %2**, seleccione un artículo y, a continuación, especifique una cantidad negativa en el campo **Cantidad**.

5.  Haga clic en la ficha desplegable **Detalles de línea**.

6.  En la ficha **General**, escriba un valor en el campo **Precio de coste de la devolución**. Se usa este valor cuando las mercancías se devuelven al inventario. Si no especifica un valor, se usa el precio de coste actual cuando las mercancías se devuelven al inventario.

## <a name="method-2-automatically-generate-the-cost-price-based-on-the-customer-invoice-line"></a>Método 2: generar automáticamente el precio de coste según la línea de factura del cliente

Éste es el método preferido para crear líneas de devolución. Para usar el coste de los productos al momento en el que los vendió al cliente, cree un pedido de devolución y especifique la línea de ventas que desea devolver.

1.  Haga clic en **Ventas y marketing** \> **Común** \> **Pedidos de devolución** \> **Todos los pedidos de devolución**.

2.  En el **Panel de acciones**, en el grupo **Nuevo**, haga clic en **Pedido de devolución**.

3.  En el formulario **Crear pedido de devolución**, seleccione una cuenta de cliente y, a continuación hacen clic en **Aceptar**.

4.  En el formulario **Pedido de devolución - Número de RMA: %1, %2**, en el **Panel de acciones**, haga clic en **Buscar pedido de ventas**.

5.  En el formulario **Buscar pedido de ventas**, seleccione la línea de factura que desea devolver y, a continuación, haga clic en **Aceptar**.
    
    En la ficha desplegable **Detalles de línea**, en la ficha **General**, el campo **Id. de devolución de lote** muestra el valor de la línea de ventas original. Además, el campo **Precio de coste de la devolución** muestra el valor de coste de la línea de ventas original.

## <a name="cost-calculation-example"></a>Ejemplo de cálculo de costes

Cuando se usa el campo **Id. de devolución de lote** en una línea del pedido de devolución para especificar el precio de coste de devolución, se utiliza el coste de la línea del pedido de devolución. Si ejecuta la funcionalidad de cierre o de cálculo de inventario, el coste se ajusta en la línea de ventas original. El coste en la línea del pedido de devolución se ajusta automáticamente para reflejar el mismo coste por unidad.

1.  Crear y liberar un producto que se llama Prueba. En el formulario **Detalles de producto emitido**, especifique la siguiente información:
    
    1.  En la ficha desplegable **Gestionar costes**, en el campo **Grupo de artículos**, seleccione el grupo **Piezas**.
    
    2.  En la ficha desplegable **General**, en el campo **Grupo de modelos de artículo**, seleccione **DEF**.
    
    3.  En la ficha desplegable **Compra**, en el campo **Precio**, escriba 10,00 como precio de coste del artículo.
    
    4.  En el **Panel de acciones**, haga clic en **Grupos de dimensiones**. En el campo **Grupo de dimensiones de almacenamiento**, seleccione **Solo sitio y almacén**. En el campo **Grupo de dimensiones de seguimiento**, seleccione **Ninguna dimensión de seguimiento activa**.

2.  Crear un pedido de compra para 10 piezas del artículo Prueba a 6,00 por unidad y registre una factura para el pedido.
    
    Crear un segundo pedido de compra para 10 piezas del artículo Prueba a 8,00 por unidad y registre una factura para el pedido.

3.  Registre una factura para un pedido de ventas para vender cinco piezas del artículo Prueba.
    
    En este caso, la línea de pedido de ventas se calcula en 35,00 (5 piezas \* coste medio 7,00 por pieza).

4.  Crear un pedido de devolución para el cliente. En el formulario **Buscar pedido de ventas**, seleccione la línea de factura y, a continuación, haga clic en **Aceptar**.

5.  En el formulario **Pedido de devolución - Número de RMA: %1, %2**, compruebe que un pedido de devolución se genera para devolver el artículo Prueba. La cantidad del pedido de devolución se establece en -5,00.
    
    El campo **Id. de devolución lote** muestra un identificador de lote. Este identificador de lote se obtiene del pedido de ventas original del artículo que se vendió al cliente. El campo **Precio de coste de la devolución** muestra el precio de coste de la línea de ventas original.

6.  Registe la recepción de los artículos devueltos.

7.  Registre un albarán para los artículos devueltos.

8.  Registre una factura para el pedido de devolución. En la página de lista **Todos los pedidos de ventas** , seleccione un pedido de ventas cuyo tipo de pedido sea **Pedido devuelto**.

9.  Abra el formulario **Transacciones de inventario**. Compruebe que la devolución se calcule en 7,00 por unidad con el valor del campo **Precio de coste de la devolución**, para un total de 35,00 en el campo **Importe de coste**. Puede abrir el formulario **Transacciones de inventario** desde el formulario **Pedido de devolución - Número de RMA: %1, %2** . En la cuadrícula **Líneas**, haga clic en **Inventario** \> **Transacciones**.

10. En la gestión de inventarios y almacenes, use el formulario **Cierre y ajuste** para ejecutar el procedimiento **3. Cerrar**.
    
    Esta acción ajusta el coste de la línea de ventas original que se calculó en -35,00 (5 piezas \* 7,00) en -30,00 (5 piezas \* 6,00). Esto se debe a que el grupo de modelos de inventario se rige por el principio FIFO (primero en entrar, primero en salir), y 6,00 por unidad es el coste FIFO del primer pedido de compra. Además, la acción ajusta el coste de la línea de ventas de devolución para conciliar el coste por unidad en la línea de ventas original. Por lo tanto, el coste de la línea de devolución se ajusta de 35,00 a 30,00.





