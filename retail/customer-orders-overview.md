---
title: "Visión general de los pedidos de cliente"
description: "Este tema proporciona información acerca de los pedidos de cliente en el sistema POS moderno al por menor MPOS (). Los pedidos de cliente también se conocen como pedidos especiales. El tema incluye una discusión de parámetros relacionados con la transacción y flujos."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 2f466dfe53ccf0be15ed0793b4a6dd371bdacc0d
ms.lasthandoff: 03/31/2017


---

# <a name="customer-orders-overview"></a>Visión general de los pedidos de cliente

Este tema proporciona información acerca de los pedidos de cliente en el sistema POS moderno al por menor MPOS (). Los pedidos de cliente también se conocen como pedidos especiales. El tema incluye una discusión de parámetros relacionados con la transacción y flujos.

En un mundo de ventas al por menor de omni- canal, muchos minoristas ofrece la opción de pedidos de cliente, o de pedidos especiales, cumplir diferentes requisitos del producto y de cumplimiento. Aquí hay algunas situaciones habituales:

-   Un cliente desea los productos que se entregarán una dirección específica en una fecha específica.
-   Un cliente desea ser elegidas productos de una tienda o desde una ubicación diferente de la tienda o de la ubicación donde se compró el cliente estos productos.
-   Un cliente desea cualquier otro para recoger los productos que compró el cliente.

Los minoristas también utilizan pedidos de cliente minimizar de ventas perdido que las no está dentro del sistema comunes podrían provocar de otro modo, ya que la mercancía se puede entregar o recoger en una hora distinta o un lugar.

## <a name="set-up-customer-orders"></a>Pedidos de cliente de instalación
A continuación se muestran algunos de los parámetros que se pueden liquidar en ** los parámetros de ventas ** la página para definir cómo se realizan los pedidos de cliente:

-   ** Porcentaje predeterminado del depósito ** permite especificar el importe que el cliente pagará como un depósito antes de que el pedido se pueda confirmada. Se calcula el importe predeterminado del depósito como porcentaje del valor del pedido. En función de privilegios, un socio de la tienda puede anular poder el importe mediante ** Anulación de depósito **.
-   ** El porcentaje del gasto de cancelación ** – si se aplica un gasto cuando un pedido de cliente se cancela, especifique el importe de dicho cargo.
-   ** El cargo de cancelación código ** – si se aplica un gasto cuando un pedido de cliente se cancela, reflejarán a dicho cargo bajo cargo codificado en el pedido de ventas en Microsoft Dynamics AX. Use este parámetro para definir el código del gasto de cancelación.
-   ** ** – Los minoristas codificados gastos de envío se pueden cargar un índice extra para la mercancía de envío a un cliente. El importe del gasto de envío se reflejará en cargo codificado en el pedido de ventas en Dynamics AX. Use este parámetro para asignar el gasto de envío código a los gastos de envío en el pedido de cliente.
-   ** Los gastos de envío de la devolución ** – especifican si los gastos de envío que están asociados a un pedido de clientes son reembolsables.
-   ** El importe máximo sin aprobar ** – si los gastos de envío son reembolsables, especifique el importe máximo de devoluciones de gastos de envío a través de pedidos de devolución. Si se supera este importe, la anulación de administrador se requiere para continuar con la devolución. Para adaptar los siguientes escenarios, una devolución de gastos de envío puede superar el importe que estaba originalmente pagado:
    -   Aplicar los gastos en el nivel del encabezado del pedido de ventas, y cuando una cierta cantidad de una línea de productos se devuelve, la devolución máxima de gastos de envío permitido para los productos y la cantidad no se puede determinar por la forma en que trabaja para todos los clientes al por menor.
    -   Los gastos de envío se contraen para cada instancia de envío. Si varias veces de productos de las devoluciones de clientes, y la directiva del distribuidor especifica que los minoristas llevará el coste de gastos de envío de devolución, los gastos de envío de devolución que se más los gastos de envío reales.

## <a name="transaction-flow-for-customer-orders"></a>Flujo de la transacción para los pedidos de cliente
### <a name="create-a-customer-order-in-retail-modern-pos"></a>Crear un pedido de cliente en el sistema POS moderno al por menor

1.  Agregue un cliente a la transacción.
2.  Agregar productos al carro.
3.  Haga clic ** cree el pedido de cliente **, y después seleccione el tipo de pedido. El tipo de pedido puede ser o ** pedido de cliente o ** ** ** presupuesto.
4.  Haga clic ** envío seleccionada o ** ** registrar todos ** registrar los productos una dirección en la cuenta de cliente, especifique la fecha de envío solicitada, y especificar gastos de envío.
5.  Haga clic en para escoja ** seleccionado arriba o ** ** tome ** a todos los productos para que se cogidos de la tienda actual o a otro almacén en una fecha específica.
6.  Obtenga el importe del depósito, si se requiere un depósito.

### <a name="edit-an-existing-customer-order"></a>Editar un pedido de cliente existente

1.  En la página principal, haga clic en ** encuentre un pedido **.
2.  Busque y seleccione el pedido que desee editar. En la parte inferior de la página, haga clic en ** ** edición.

### <a name="pick-up-an-order"></a>Coja un pedido

1.  En la página principal, haga clic en ** encuentre un pedido **.
2.  Seleccione el pedido de recoger. En la parte inferior de la página, haga clic en ** recogida y ** embalaje.
3.  Haga clic en coja ** **.

### <a name="cancel-an-order"></a>Cancelar un pedido

1.  En la página principal, haga clic en ** encuentre un pedido **.
2.  Seleccione el pedido para cancelar. En la parte inferior de la página, haga clic en ** ** cancelación.

#### <a name="create-a-return-order"></a>Crear un pedido de devolución

1.  En la página principal, haga clic en ** encuentre un pedido **.
2.  Seleccione el pedido de volver, seleccione la factura para el pedido, y seleccione la línea de productos para que la mercancía vuelva.
3.  En la parte inferior de la página, haga clic en ** pedido de devolución **.

## <a name="asynchronous-transaction-flow-for-customer-orders"></a>Flujo asincrónico de la transacción para los pedidos de cliente
Los pedidos de cliente se pueden realizar en el cliente de (POS) de punto de venta en modo sincrónico o moda asincrónico.

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a>Habilite los pedidos de cliente que se creará en modo asincrónico

1.  En Dynamics AX, haga clic en ** al por menor y comercio ** &gt; ** el canal configurar ** &gt; ** Configuración de PDV ** &gt; ** perfil de Retail POS ** &gt; ** los perfiles de funcionalidad **.
2.  En ** general ** la ficha desplegable, establezca ** cree el pedido de cliente en modo de async ** la opción ** Sí **.

** Cuando cree el pedido de cliente en modo de async ** la opción está establecida ** Sí **, los pedidos de cliente se realizan siempre en modo asincrónico, incluso si Retail Transaction Service al por menor (RTS) disponible. Si establece esta opción ** ninguna **, los pedidos de cliente realizan siempre a modo sincrónico mediante RTS. Cuando los pedidos de cliente se crean en modo, son asincrónicos y extraen insertan en Dynamics AX por trabajos de extracción (P). Los pedidos de ventas correspondientes se crean en Dynamics AX ** cuando sincronice los pedidos ** se ejecuta manualmente o mediante un proceso por lotes.

<a name="see-also"></a>Consulte también
--------

[Pedidos de cliente híbridos] (hybrid-customer-orders.md)


