---
title: Facturas de anticipo frente a anticipos
description: Este tema describe y contrasta los dos métodos que las organizaciones pueden usar para los pagos anticipados (anticipos).
author: abruer
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, PurchTable
audience: Application User
ms.reviewer: twheeloc
ms.custom: 15871
ms.assetid: a0bb5220-73d4-48ae-84d0-46a171c224fa
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f05f1d8d2a1fb454f3f227d2cc8138f2b779ff87
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716336"
---
# <a name="prepayment-invoices-vs-prepayments"></a>Facturas de anticipo frente a anticipos

[!include [banner](../includes/banner.md)]

Este tema describe y contrasta los dos métodos que las organizaciones pueden usar para los pagos anticipados (anticipos). Un método crea una factura de anticipo asociada a un pedido de compra. El otro método crea asientos del diario de anticipos creando entradas de diario y marcándolas como asientos del diario de anticipos.

Las organizaciones pueden emitir anticipos o pagos por adelantado a proveedores por bienes o servicios antes de que estos se satisfagan. Se pueden usar dos métodos para emitir anticipos a los proveedores. Para minimizar el riesgo, puede realizar un seguimiento de los anticipos definiéndolos en pedidos de compra. Para este método, debe crear una factura en anticipo asociada a un pedido de compra. Este método se denomina facturación en anticipo. Las organizaciones que no deseen seguir los pagos por adelantado o anticipos tan de cerca o que no reciben una factura en anticipo del proveedor pueden usar asientos del diario de anticipos en lugar del método de factura en anticipo. Para crear asientos del diario de anticipos, cree entradas de diario y márquelas como asientos del diario de anticipos. Para este método no podrá realizar un seguimiento de los anticipos entregados a un proveedor en relación con los pedidos de compra. Sin embargo, puede marcar un prepago registrado para su liquidación con respecto a un pedido de compra.

## <a name="when-to-use-prepayment-invoicing-vs-prepayments"></a>Cuándo usar facturas en anticipo frente a anticipos

| Factura en anticipo                                                                | Pagos por adelantado                                                              |
|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| Defina un valor de anticipo en el pedido de compra.                                    | No se define un valor de anticipo en el pedido de compra.                    |
| Deben registrarse una factura de anticipo y una factura final.                       | No se debe haber registrada ninguna factura en anticipo.                                    |
| El pasivo para el anticipo se mantiene en la cuenta de anticipo, no la cuenta de proveedores. | El pasivo para el anticipo se mantiene en la cuenta de proveedores.                  |
| El saldo del proveedor no refleja el valor del anticipo en el proceso.     | El saldo del proveedor refleja el valor del anticipo en el proceso. |
| La facturación en anticipo está disponible solo en Proveedores.                         | Los anticipos están disponibles en Clientes y Proveedores.    |

## <a name="overview-of-the-prepayment-process"></a>Información general del proceso de anticipo
Las prácticas de contabilidad de muchos países o regiones exigen que los anticipos (pagos por adelantado) de un cliente o a un proveedor no se registren en las cuentas de resumen habituales del cliente o proveedor. En su lugar, estos pagos por adelantado se registran en cuentas contables especiales para ellos. Cuando se crea un pedido de compra o ventas, se emite una factura al cliente o desde el proveedor. Al pagarla, el asiento de anticipo y de anticipo de impuestos en las cuentas contables de anticipos se invierten, y los importes de factura se registran automáticamente en las cuentas de resumen habituales. Siga estos pasos para crear un anticipo:

1.  Configure un perfil de contabilización para anticipos.
2.  En los parámetros de clientes y proveedores, en **Impuestos y contabilidad**, seleccione el nuevo perfil de contabilización mediante el parámetro **Perfil de registro para diario de pagos con pagos por adelantado**.
3.  Cree un diario de pagos y, a continuación, cree el nuevo pago.
4.  Puede marcar el pago como un anticipo. Si el pago se marca como anticipo, se registra en las cuentas contables definidas en el perfil de contabilización que se configura en los pasos 1 y 2. Además, si el pago se marca como anticipo, se calculan los impuestos. Algunos gobiernos exigen pagar los impuestos cuando se registra un anticipo, incluso si no hay una factura.
5.  Registre el pago por adelantado.
6.  Opcional: puede liquidar el pago por adelantado con respecto al pedido de compra o el pedido de ventas antes de crear la factura. En la página del pedido de ventas o de compra, en el panel de acciones, use **Liquidar transacciones**.
7.  Cuando el proveedor entregue los bienes o servicios, registre la factura. Si se liquidó el anticipo con el pedido de compra o de ventas en el paso 6, el anticipo se liquida automáticamente con la factura que creada. Si no liquidó el anticipo con el pedido de compra o el pedido de ventas, puede hacerlo manualmente con la factura mediante **Liquidar transacciones** en la página del cliente o del proveedor. El importe del anticipo a continuación se revierte de la cuenta contable de proveedor y cliente temporal. Además, si se han calculado los impuestos, estos se revierten, ya que la factura tiene los impuestos reales.

## <a name="overview-of-the-prepayment-invoicing-process"></a>Información general del proceso de facturación en anticipo
Las facturas en anticipo son una práctica empresarial habitual. Un proveedor emite facturas en anticipo para exigir un depósito en la compra antes de que se satisfaga el pedido de compra. Por ejemplo, algunos proveedores piden un anticipo para determinados bienes o servicios personalizados. Si un proveedor emite una factura que exige un anticipo, puede usar la función de factura en anticipo. Se puede definir un valor de anticipo en el pedido de compra, registrar y pagar una factura en anticipo y, a continuación, aplicar la factura en anticipo a la factura final. Siga estos pasos para crear un anticipo:

1.  El agente de compra crea, confirma y envía un pedido de compra para el cual el proveedor ha pedido un anticipo. El valor del anticipo se define en el pedido de compra como parte del acuerdo.
2.  El proveedor envía una factura de anticipo.
3.  El coordinador de Proveedores registra la factura en anticipo con el pedido de compra y, a continuación, se paga la factura de anticipo.
4.  El proveedor envía una solicitud de pago, denominada factura de proveedor estándar. Cuando el proveedor entrega los bienes o servicios y se reciben las facturas de proveedor estándar, el coordinador de Proveedores aplica el importe de anticipo ya pagado en la factura estándar.
5.  El coordinador de Proveedores paga y liquida el importe restante de la factura estándar.

## <a name="set-up-parameters-to-enable-the-prepayment-invoicing-process"></a>Configurar parámetros para habilitar el proceso de facturación de pago por anticipado
Se debe definir una cuenta de prepago en la pestaña **Pedido de compra** de la página **Contabilización de inventario** (**Gestión de inventario \> Configuración \> Contabilización \> Contabilización**). La cuenta de prepago se actualizará, normalmente se cargará, cuando se registre la factura de prepago. El saldo en la cuenta de prepago se revertirá cuando se registre la factura estándar que se aplica a la factura de prepago. Si no liquida la factura de prepago en un pago previo a aplicar la factura de prepago a la factura estándar, los asientos contables de la factura de prepago registrada se revertirán cuando se registre la factura estándar.

La cuenta resumida de cuentas por pagar de compensación se define en el perfil **Registro de proveedores**. Para definir el perfil de publicación predeterminado, haga clic en **Proveedores \>Configuración \> Parámetros de proveedores \>Ficha Contabilidad e impuestos \> Perfil de contabilización con factura de proveedor de prepago**.

La **Directiva de solicitudes de prepago** indica si el sistema aplicará automáticamente las facturas de prepago liquidadas a la factura final que se creó manualmente. Las facturas que se crean utilizando una entidad de datos no deberán referirse a la **Directiva de solicitud de prepago**. Deberá aplicar manualmente las facturas de prepago liquidadas a las facturas que se crearon utilizando una entidad de datos. Para definir la directiva, vaya a **Proveedores \>Configuración \> Parámetros de proveedores \> Ficha Contabilidad e impuestos \> Política de solicitud de prepagos**. Si el campo **Directiva de solicitud de prepagos** está configurado en **Automático**, la factura de prepago se marcará automáticamente para su liquidación con la factura final. Si el campo se establece en **Notificación**, se mostrará una indicación visual de que una factura de prepago está disponible para su aplicación cuando se cree la factura final.

## <a name="create-a-purchase-order-that-contains-prepayment-invoice-information"></a>Crear un pedido de compra que contenga información sobre la factura de prepago
Cuando un proveedor le dice que requiere pago por anticipado de los bienes y servicios incluidos en un pedido de compra, debe definir el valor del pago anticipado para el pedido de compra asociado. Vaya a **Proveedores \> Común \> Pedidos de compra \> Todos los pedidos de compra** y busque el pedido de compra del proveedor. En el panel de acciones, seleccione la pestaña **Compra** y, a continuación, elija **Anticipo**. Especifique la información del anticipo, incluyendo la descripción, el valor del anticipo, si es un importe fijo o un porcentaje y una id. de categoría del anticipo. 

Tenga en cuenta que no se permiten varias definiciones de anticipos en un pedido de compra. Si necesita permitir múltiples anticipos en una orden de compra, contabilice los pagos utilizando el diario de pagos en lugar de una factura de anticipo.

El prepago puede eliminarse de la orden de compra a menos que ya haya liquidado un pago contra la factura de prepago registrada o haya contabilizado la factura estándar. Para eliminar una información de prepago de la orden de compra, seleccione **proveedores \> Común \> Pedidos de compra \> Todos los pedidos de compra** y busque el pedido de compra del proveedor. En el panel de acciones, seleccione la pestaña **Compra** y, a continuación, elija **Quitar anticipo**.

## <a name="create-and-post-a-prepayment-invoice"></a>Cree y registre una factura de anticipo
Para registrar la factura de prepago del proveedor, vaya a la página **Factura de proveedor**, seleccionando la opción **Factura de prepago** en la página **Pedidos de compra** (**Proveedores \> Común \> Pedidos de compra \> Todos los pedidos de compra \> Pestaña Factura \> Factura de prepago**). Especifique la información de la factura de anticipo, incluido el número de factura. No puede modificar las cantidades de una factura de anticipo. Si el proveedor ha facturado una cantidad parcial del valor de prepago que se define en la orden de compra, puede actualizar el precio unitario para reflejar el valor parcial.

Al registrar la factura de prepago, la cuenta de prepago y saldo del proveedor se actualizará. También se actualizará el valor **Solicitud de prepago** de la definición de prepago contenida en la orden de compra. Las entradas de dimensión financiera predeterminadas para el comprobante de prepago registrado se tomarán de la información del encabezado del pedido de compra.

## <a name="post-and-settle-payments-for-the-prepayment-invoice"></a>Contabilizar y liquidar pagos de la factura de prepago
A continuación, se pagará la factura de prepago desde la página **Diario de pagos**. Para acceder a los diarios de pago, haga clic en **Proveedores \> Diarios \> Pagos \> Diario de pagos**. Después de contabilizar la liquidación del pago en la factura de prepago, se actualizará el valor de la **Solicitud de prepago restante** del pedido de compra.

Antes de contabilizar la factura estándar para la factura de anticipo, puede revertir la liquidación del pago de la factura de anticipo. Sin embargo, después de aplicar la factura estándar a la factura de anticipo, puede revertir la liquidación del pago de la factura de anticipo.

## <a name="post-the-standard-vendor-invoice-for-the-purchase-order-and-apply-the-prepayment-invoice-to-the-standard-invoice"></a>Registrar la factura de proveedor estándar para la orden de compra y aplicar la factura de prepago a la factura estándar
Registre la factura estándar recibida del proveedor. Como parte de este proceso, puede aplicar la factura de prepago liquidada a la factura del proveedor para que el valor de la factura se reduzca por el importe ya pagado. La aplicación de la factura de prepago a la factura del proveedor garantizará que los asientos contables de la factura de prepago se reviertan.

## <a name="application-of-the-prepayment-invoice-after-posting-the-standard-invoice"></a>Aplicación de la factura de prepago después de contabilizar la factura estándar
Si olvida aplicar el pago por adelantado a la factura del proveedor estándar en el momento de contabilizar la factura del proveedor, el pago por adelantado liquidado estará disponible para aplicarse a otras facturas de este proveedor desde la página **Proveedores** (**Proveedores \> Común \> Proveedores \> Todos los proveedores \> Pestaña Factura \> Aplicar**).

## <a name="reversal-of-the-prepayment-application-process"></a>Reversión del proceso de solicitud de prepago
Si necesita anular o revertir la aplicación de una factura de prepago de una factura estándar, seleccione la acción **Revertir** desde la página **Proveedores** (**Cuentas por pagar \> Común \> Proveedores \> Todos los proveedores \> Pestaña Factura \> Revertir**). Una vez que se revierte la solicitud de anticipo, puede aplicar el anticipo a otra factura estándar. 



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
