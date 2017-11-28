---
title: "Visión general de pedidos de cliente"
description: "Este tema proporciona información acerca de los pedidos de cliente en Retail Modern POS (MPOS). Los pedidos de cliente también se conocen como pedidos especiales. El tema incluye una discusión de parámetros y flujos de transacción relacionados."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260594
ms.assetid: 6fc835ef-d62e-4f23-9d49-50299be642ca
ms.search.region: global
ms.search.industry: Retail
ms.author: anpurush
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ce6774ede836eb29e6ef2cd8d4baa9efb931020c
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="customer-orders-overview"></a>Visión general de pedidos de cliente

[!include[banner](includes/banner.md)]


Este tema proporciona información acerca de los pedidos de cliente en Retail Modern POS (MPOS). Los pedidos de cliente también se conocen como pedidos especiales. El tema incluye una discusión de parámetros y flujos de transacción relacionados.

En un mundo de comercio de varios canales simultáneos, muchos minoristas ofrecen la opción de pedidos de cliente, o pedidos especiales, para cumplir diferentes requisitos de producto y de cumplimiento. Aquí hay algunas situaciones habituales:

-   Un cliente desea que los productos se entreguen en una dirección específica en una fecha específica.
-   Un cliente desea elegir productos de una tienda o de una ubicación diferente de la tienda o de la ubicación donde el cliente compró los productos.
-   Un cliente desea que otra persona recoja los productos que el cliente compró.

Los minoristas también utilizan pedidos de cliente para minimizar las ventas perdidas que, de no ser así, la falta de existencias podría provocar; la mercancía se puede entregar o recoger en una hora o un lugar distintos.

## <a name="set-up-customer-orders"></a>Configurar pedidos de cliente
A continuación se muestran algunos de los parámetros que se pueden configurar en la página **Parámetros comerciales** para definir cómo se realizan los pedidos de cliente:

-   **Porcentaje de depósito predeterminado**: permite especificar el importe que el cliente debe pagar como depósito para que el pedido se pueda confirmar. Se calcula el importe de depósito predeterminado como porcentaje del valor del pedido. En función de los privilegios, un socio de la tienda puede anular el importe mediante **Anular depósito**.
-   **Porcentaje de cargo de cancelación**: si se aplica un cargo cuando un pedido de cliente se cancela, especifique el importe de dicho cargo.
-   **Código de cargo de cancelación**: si se aplica un cargo cuando un pedido de cliente se cancela, dicho cargo se reflejará mediante un código de cargo en el pedido de ventas. Use este parámetro para definir el código del cargo de cancelación.
-   **Código de cargo de envío**: los minoristas pueden cargar una cuota adicional por enviar mercancía a un cliente. El importe del cargo de envío se reflejará mediante un código codificado en el pedido de ventas. Use este parámetro para asignar el código de cargo de envío a los cargos de envío en el pedido del cliente.
-   **Devolver los gastos de envío**: especifique si los gastos de envío que están asociados a un pedido de cliente son reembolsables.
-   **Importe máximo sin aprobación**: si los cargos de envío son reembolsables, especifique el importe máximo de las devoluciones de cargos de envío en los pedidos de devolución. Si se supera este importe, la anulación de administrador se requiere para continuar con la devolución. Para incluir los siguientes escenarios, una devolución de cargos de envío puede superar el importe que se pagó originalmente:
    -   Los cargos se aplican en el nivel del encabezado del pedido de ventas, y cuando una cierta cantidad de una línea de productos se devuelve, la devolución máxima de cargos de envío permitida para los productos y la cantidad no se puede determinar por la forma en que funciona para todos los clientes al por menor.
    -   Los cargos de envío se tienen por cada instancia de envío. Si un cliente devuelve varias veces productos y la directiva del distribuidor especifica que el distribuidor se hará cargo de los cargos de devolución de envío, los cargos de devolución de envío serán más elevados que los cargos de envío reales.

## <a name="transaction-flow-for-customer-orders"></a>Flujo de transacciones para pedidos de cliente
### <a name="create-a-customer-order-in-retail-modern-pos"></a>Cree un pedido de cliente en Retail Modern POS

1.  Agregue un cliente a la transacción.
2.  Agregue productos al carro.
3.  Haga clic en **Crear pedido de cliente** y después seleccione el tipo de pedido. El tipo de pedido puede ser **Pedido de cliente** o **Presupuesto**.
4.  Haga clic en **Envío seleccionado** o en **Enviar todo** para enviar los productos a una dirección de la cuenta de cliente, especifique la fecha de envío solicitada, y especifique los cargos de envío.
5.  Haga clic en **Recoger la selección** o en **Recoger todo** para seleccionar los productos que se cogerán en la tienda actual o en otro almacén en una fecha específica.
6.  Cobre el importe del depósito, si se requiere un depósito.

### <a name="edit-an-existing-customer-order"></a>Edición de un pedido de cliente ya existente

1.  En la página principal, haga clic en **Encontrar un pedido**.
2.  Busque y seleccione el pedido que desea editar. En la parte inferior de la página, haga clic en **Editar**.

### <a name="pick-up-an-order"></a>Elegir pedido

1.  En la página principal, haga clic en **Encontrar un pedido**.
2.  Seleccione el pedido que desea recoger. En la parte inferior de la página, haga clic en **Picking y embalaje**.
3.  Haga clic en **Recoger**.

### <a name="cancel-an-order"></a>Cancelar un pedido

1.  En la página principal, haga clic en **Encontrar un pedido**.
2.  Seleccione el pedido que se va a cancelar. En la parte inferior de la página, haga clic en **Cancelar**.

#### <a name="create-a-return-order"></a>Crear un pedido de devolución

1.  En la página principal, haga clic en **Encontrar un pedido**.
2.  Seleccione el pedido que se ha de devolver, seleccione la factura del pedido y seleccione la línea de productos para que la mercancía vuelva.
3.  En la parte inferior de la página, haga clic en **Pedido de devolución**.

## <a name="asynchronous-transaction-flow-for-customer-orders"></a>Flujo de transacciones asíncrono para pedidos de cliente
Los pedidos de cliente se pueden crear en el cliente de punto de venta (PDV) en modo sincrónico o modo asincrónico.

### <a name="enable-customer-orders-to-be-created-in-asynchronous-mode"></a>Habilite los pedidos de cliente que se crearán en modo asincrónico

1.  Haga clic en **Retail** &gt; **Configuración de canal** &gt; **Configuración de PDV** &gt; **Perfiles de PDV** &gt; **Perfiles de funcionalidad**.
2.  En la ficha desplegable **General**, establezca la opción **Crear pedido de cliente en modo asincrónico** en **Sí**.

Cuando la opción **Crear pedido de cliente en modo asincrónico** está establecida en **Sí**, los pedidos de cliente se crean siempre en modo asincrónico, incluso si Retail Transaction Service (RTS) está disponible. Si establece esta opción en **No**, los pedidos de cliente siempre se crean en modo sincrónico mediante RTS. Cuando los pedidos de cliente se crean en modo asincrónico, se extraen y se insertan en Retail mediante trabajos de extracción (P). Los pedidos de ventas correspondientes se crean en Retail cuando **Sincronizar pedidos** se ejecuta manualmente o mediante un proceso por lotes.

<a name="see-also"></a>Consulte también
--------

[Pedidos de cliente híbridos](hybrid-customer-orders.md)




