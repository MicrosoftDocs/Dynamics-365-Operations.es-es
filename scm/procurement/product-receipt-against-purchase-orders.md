---
title: "Recepción de producto frente a pedidos de compra"
description: "Este artículo describe las distintas opciones para registrar productos como recibidos."
author: FrankDahl
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations, Retail
ms.custom: 93113
ms.assetid: d4ec3e86-fce2-4546-911b-e0acf64c8887
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: a192688315adb2d83f349c525c5d8f70309375db
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017

---

# <a name="product-receipt-against-purchase-orders"></a>Recepción de producto frente a pedidos de compra

[!include[banner](../includes/banner.md)]

[!include[retail name](../includes/retail-name.md)]


Este artículo describe las distintas opciones para registrar productos como recibidos.

La recepción de producto es el proceso de registro de que se han recibido los productos que se han pedido, de manera que las líneas de pedido de compra se pueden procesar para facturación. En algunos casos, los productos pasan por un pre-registro, donde se registra información adicional del proveedor antes de que se reciban los productos. Cuando llegan los productos, se marcan primero como **Registrado**. Los productos pueden pasar después por procesos adicionales, como la gestión de la calidad antes de que finalmente se marquen como **Recibido**.

## <a name="preregistration-asn"></a>Pre-registro (Aviso de envío por adelantado)
Los proveedores pueden compartir información acerca de los productos que se enviarán. En este caso, puede registrar los productos para registrar esta información antes de que se reciban los productos. Al registrar previamente los productos, reduce la cantidad de trabajo que se requiere durante el registro y la recepción de los artículos. Los proveedores pueden proporcionar información de producto de manera electrónica a través de un aviso de envío por adelantado que, a continuación, se registra automáticamente en el sistema. La información del aviso de envío por adelantado incluye la cantidad de productos que se van a enviar y la fecha en la que se enviarán. El aviso de envío por adelantado también puede incluir información como números de serie o de lote. El registro del aviso de envío por adelantado se produce en el módulo **Administración de transporte**.

## <a name="registration"></a>Registro
El registro de recepción de producto a menudo se produce en los muelles de llegada de un almacén. Se realiza mediante un dispositivo manual o a través de diarios de llegada. Como alternativa, puede registrar manualmente la recepción de producto mediante la acción **Registro** de la página **Pedido de compra**. En ambos casos, los productos se marcan como **Registrado**. Tenga en cuenta que los productos no se han marcado todavía como **Recibido**.  

Los productos que se reciben en un almacén podrían pasar por una inspección de calidad antes de ubicarse en el inventario. Los pedidos de calidad o las órdenes de cuarentena se pueden utilizar para realizar una inspección de calidad. Si se utilizan los pedidos de calidad, puede configurar el proceso de bloquear productos temporalmente a través de una reserva mientras se inspeccionan. Si se usan órdenes de cuarentena, los productos se mueven a otro almacén para inspección. Este almacén se conoce como el almacén de cuarentena. En ambos procesos de inspección de calidad, algunas de las mercancías se podrían dar de baja, porque no se ajustan a las expectativas de calidad o porque la inspección de calidad implica pruebas destructivas de una muestra del producto.

## <a name="product-receipt"></a>Recepción de producto
A menudo, la acción **Recepción de producto** de la página **Pedidos de compra** se utiliza para marcar productos como **Recibido** en el PC. La página **Registro de recepción de productos** tiene varias opciones para la cantidad que se contabiliza como recibido. Por ejemplo, puede establecer el campo **Cantidad** en **Cantidad pedida** o **Cantidad que se recibe ahora**. De forma alternativa, si se ha utilizado un proceso de llegada a almacén, a menudo establecerá este campo en **Cantidad registrada**. Puede modificar las cantidades de cada línea de pedido que se marcarán como **Recibido**, para dar cuenta de discrepancias, como entrega incompleta y entrega en exceso. Durante la recepción de producto, debe especificar un identificador de recepción de producto, que normalmente es una referencia al albarán del proveedor. Este identificador es necesario para contabilidad, porque permite comprobaciones o auditorías de albaranes de proveedor frente a lo que se ha recibido y el gasto o el inventario contabilizado.  

Si un empleado pidió mercancías mediante una solicitud compra, a ese empleado se le puede pedir que confirme la recepción del producto él o ella misma. Configure este comportamiento utilizando un flujo de trabajo. Puede configurar las condiciones de flujo de trabajo para que coincidan con el proceso empresarial.  

Los pedidos de compra pueden crearse para productos que no están pensados como inventario pero se consideran un gasto. Esta categoría incluye líneas de pedido donde los productos se marcan como **Sin existencias** por su grupo de modelos de inventario y también las líneas que utilizan categorías de compras. En este caso, los elementos pueden no pasar por el registro de llegada y recepción en el almacén. En su lugar, la acción **Recepción de producto** se utiliza para registrar el recibo directamente en el pedido de compra y la recepción se basa en la cantidad pedida, no una cantidad registrada.  

Puede crear líneas de pedido de compra donde la opción **Nuevo activo fijo** está habilitada. Esta opción indica que se debe considerar la compra un activo fijo en lugar de inventario. En este caso, las reglas de determinación de activos fijos que se han configurado determinan si la compra del producto o de la categoría supera los umbrales específicos y deben considerarse por tanto un activo y pasar por la administración de activos fijos. Las compras también se pueden realizar hacia un activo fijo existente. En este caso, el importe se ajusta según corresponda.  

Puede seleccionar varios pedidos y procesar la recepción en todos esos pedidos juntos. Este enfoque no se utiliza con mucha frecuencia, pero puede que desee utilizarlo si un proveedor ha consolidado los envíos para usted en una sola carga. Durante la recepción de producto en la compra, hay una función para realizar las actualizaciones conjuntas. Las actualizaciones conjuntas que le permiten publicar un solo albarán del proveedor para más de un pedido de compra.  

Los pedidos de compra pueden crearse a partir de un pedido de ventas en el que se ha seleccionado la opción **Entrega directa**. Cuando se utiliza la entrega directa, los productos nunca llegan al propio almacén, pero se envían directamente del proveedor al cliente. En este caso, la recepción se suele registrar directamente en el pedido de compra. La recepción se puede realizar automáticamente, como a través de la integración de intercambio electrónico de datos (EDI) con el proveedor. De forma alternativa, si el pedido de compra es un pedido de compra entre empresas vinculadas, Microsoft Dynamics 365 for Finance and Operations automatiza la recepción del pedido de ventas entre empresas vinculadas cuando se produce el envío. Cuando se utiliza la entrega directa, los productos se siguen contabilizando como inventario, a pesar de que no llegan físicamente al almacén. Por tanto, cuando se registre la recepción de producto en el pedido de compra, el pedido de ventas se actualiza automáticamente con un albarán, para que el cambio general en el inventario sea 0 (cero). En los escenarios de entrega directa, no debería requerir el pre-registro. Si utiliza almacenes que están habilitados para la gestión de almacenes, puede eludir el requisito para el registro de matrícula especificando un almacén virtual en su lugar. Especifique este almacén en el campo **Almacén de entrega directa** del producto. 

Una vez que se ha procesado la recepción de producto en el pedido de compra, el estado del pedido de compra se establece en **Recibido** para indicar que se puede procesar la factura para el pedido. Puede revisar los detalles acerca de los productos que ya se han recibido en la página **Diarios de recepción de productos**.  

Puede tener acceso a esta página desde el grupo de acción **Recibo** de la página **Pedido de compra**. La información en los diarios incluye detalles acerca de las cantidades, las fechas y las dimensiones.

<a name="see-also"></a>Consulte también
--------

[Visión general de pedidos de compra](purchase-order-overview.md)

[Creación de pedido de compra](purchase-order-creation.md)

[Confirmación y aprobación del pedido de compra](purchase-order-approval-confirmation.md)

[Visión general de facturas de proveedores](/dynamics365/unified-operations/financials/accounts-payable/vendor-invoices-overview)




