---
title: Facturas de anticipo frente a anticipos
description: "Este artículo describe y contrasta los dos métodos que las organizaciones pueden usar para los pagos anticipados (anticipos). En un método, crea una factura de anticipo asociada a un pedido de compra. En el otro método, crea asientos del diario de anticipos creando entradas de diario y marcándolas como asientos del diario de anticipos."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, PurchTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 15871
ms.assetid: a0bb5220-73d4-48ae-84d0-46a171c224fa
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: c4f127007cea1d8ccd0b4e9ea637f0674775278d
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="prepayment-invoices-vs-prepayments"></a>Facturas de anticipo frente a anticipos

[!include[banner](../includes/banner.md)]


Este artículo describe y contrasta los dos métodos que las organizaciones pueden usar para los pagos anticipados (anticipos). En un método, crea una factura de anticipo asociada a un pedido de compra. En el otro método, crea asientos del diario de anticipos creando entradas de diario y marcándolas como asientos del diario de anticipos.

Las organizaciones pueden emitir anticipos o pagos por adelantado a proveedores por bienes o servicios antes de que estos se satisfagan. Se pueden usar dos métodos para emitir anticipos a los proveedores. Para minimizar el riesgo, puede realizar un seguimiento de los anticipos definiéndolos en pedidos de compra. Para este método, debe crear una factura en anticipo asociada a un pedido de compra. Este método se denomina facturación en anticipo. Las organizaciones que no deseen seguir los pagos por adelantado o anticipos tan de cerca o que no reciben una factura en anticipo del proveedor pueden usar asientos del diario de anticipos en lugar del método de factura en anticipo. Para crear asientos del diario de anticipos, cree entradas de diario y márquelas como asientos del diario de anticipos. Para este método no podrá realizar un seguimiento de los anticipos entregados a un proveedor en relación con los pedidos de compra. Sin embargo, puede marcar un prepago registrado para su liquidación con respecto a un pedido de compra.

## <a name="when-to-use-prepayment-invoicing-vs-prepayments"></a>Cuándo usar facturas en anticipo frente a anticipos
| Factura en anticipo                                                                | Pagos por adelantado                                                              |
|-------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| Defina un valor de anticipo en el pedido de compra.                                    | No se define un valor de anticipo en el pedido de compra.                    |
| Clave: deben registrarse una factura en anticipo y una factura final.                       | No se debe haber registrada ninguna factura en anticipo.                                    |
| El pasivo para el anticipo se mantiene en la cuenta de anticipo, no la cuenta de proveedores. | El pasivo para el anticipo se mantiene en la cuenta de proveedores.                  |
| El saldo del proveedor no refleja el valor del anticipo en el proceso.     | El saldo del proveedor refleja el valor del anticipo en el proceso. |
| La facturación en anticipo está disponible solo en Proveedores.                         | Los anticipos están disponibles en Clientes y Proveedores.    |

## <a name="overview-of-the-prepayment-process"></a>Información general del proceso de anticipo
Las prácticas de contabilidad de muchos países o regiones exigen que los anticipos (pagos por adelantado) de un cliente o a un proveedor no se registren en las cuentas de resumen habituales del cliente o proveedor. En su lugar, estos pagos por adelantado se registran en cuentas contables especiales para ellos. Cuando se crea un pedido de compra o ventas, se emite una factura al cliente o desde el proveedor. Al pagarla, el asiento de anticipo y de anticipo de impuestos en las cuentas contables de anticipos se invierten, y los importes de factura se registran automáticamente en las cuentas de resumen habituales. Siga estos pasos para crear un anticipo:

1.  Configure un perfil de contabilización para anticipos.
2.  En los parámetros de clientes y proveedores, en **Impuestos y contabilidad**, seleccione el nuevo perfil de contabilización mediante el parámetro **Perfil de registro para diario de pagos con pagos por adelantado**.
3.  Cree un diario de pagos y, a continuación, cree el nuevo pago.
4.  Puede marcar el pago como un anticipo. Si el pago se marca como anticipo, el pago se registra en las cuentas contables definidas en el perfil de contabilización que se configura en los pasos 1 y 2. Además, si el pago se marca como anticipo, se calculan los impuestos. Algunos gobiernos exigen pagar los impuestos cuando se registra un anticipo, incluso si no hay una factura.
5.  Registre el pago por adelantado.
6.  Opcional: puede liquidar el pago por adelantado con respecto al pedido de compra o el pedido de ventas antes de crear la factura. En la página del pedido de ventas o de compra, en el panel de acciones, use **Liquidar transacciones**.
7.  Cuando el proveedor entregue los bienes o servicios, registre la factura. Si se liquidó el anticipo con el pedido de compra o de ventas en el paso 6, el anticipo se liquida automáticamente con la factura que creada. Si no liquidó el anticipo con el pedido de compra o el pedido de ventas, puede hacerlo manualmente con la factura mediante **Liquidar transacciones**, en la página del cliente o del proveedor. El importe del anticipo a continuación se revierte de la cuenta contable de proveedor y cliente temporal. Además, si se han calculado los impuestos, estos se revierten, ya que la factura tiene los impuestos reales.

## <a name="overview-of-the-prepayment-invoicing-process"></a>Información general del proceso de facturación en anticipo
Las facturas en anticipo son una práctica empresarial habitual. Un proveedor emite facturas en anticipo para exigir un depósito en la compra antes de que se satisfaga el pedido de compra. Por ejemplo, algunos proveedores piden un anticipo para ciertos bienes o servicios personalizados. Si un proveedor emite una factura que exige un anticipo, puede usar la función de factura en anticipo. Se puede definir un valor de anticipo en el pedido de compra, se registra y se paga una factura en anticipo y, a continuación, la factura en anticipo se aplica a la factura final. Siga estos pasos para crear un anticipo:

1.  El agente de compra crea, confirma y envía un pedido de compra para el cual el proveedor ha pedido un anticipo. El valor del anticipo se define en el pedido de compra como parte del acuerdo.
2.  El proveedor envía una factura de anticipo.
3.  El coordinador de Proveedores registra la factura en anticipo con el pedido de compra y, a continuación, se paga la factura de anticipo.
4.  Cuando el proveedor entrega los bienes o servicios y se reciben las facturas de proveedor, el coordinador de Proveedores aplica el importe de anticipo pagado en la factura.
5.  El coordinador de Proveedores paga y liquida el importe restante de la factura.





