---
title: "Descripción de la liquidación"
description: "En este artículo se proporciona información general sobre el proceso de liquidación. Describe los tipos de transacciones que se pueden liquidar, cuándo y cómo se pueden liquidar las transacciones y los resultados del proceso de liquidación."
author: kweekley
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14551
ms.assetid: 0968fa71-5984-415b-8689-759a0136d5d1
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4d45db11c1d5bf7a58f9117fca75679ddfababf5
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="settlement-overview"></a>Descripción de la liquidación

[!include[banner](../includes/banner.md)]


En este artículo se proporciona información general sobre el proceso de liquidación. Describe los tipos de transacciones que se pueden liquidar, cuándo y cómo se pueden liquidar las transacciones y los resultados del proceso de liquidación.

Durante la liquidación, las transacciones en un documento se aplican a las transacciones en otro documento para aumentar o reducir los saldos de cada documento. Por ejemplo, un pago se puede aplicar a una factura. Los distintos tipos de transacción pueden liquidarse, en diferentes horas, y con distintos métodos. La liquidación puede hacer que se generen nuevas transacciones.

## <a name="what-transactions-can-be-settled"></a>Qué transacciones se pueden liquidar
La liquidación dentro de Proveedores y Clientes puede tener lugar entre los tipos de transacción que afectan al saldo del proveedor o al saldo del cliente, como facturas, pagos, notas de crédito y cuotas. Cualquier tipo de transacción puede liquidarse con cualquier otro tipo de transacción. Por ejemplo, puede liquidar un pago con una factura, una nota de crédito con una factura, una factura con una factura y un pago con un pago. Puede liquidar pagos con una transacción en la misma entidad jurídica o en otra entidad jurídica. En las organizaciones que usan un modelo de pagos centralizados, las [pagos centralizados](set-up-centralized-payments.md) pueden ayudar a simplificar el proceso de pago.

## <a name="when-to-settle-transactions"></a>Cuándo liquidar transacciones
Las transacciones se pueden liquidar a la hora de entrada de pago. Por ejemplo, si hace un pago a un proveedor, selecciona normalmente las facturas para pagar. Al seleccionar facturas, se marcan para la liquidación contra el pago. Cuando los vendedores de pago de clientes registran un pago de cliente, pueden marcar las facturas adecuadas para la liquidación, en función de la información que se incluye en el pago del cliente. La página **Liquidar transacciones** se usa para marcar las transacciones para liquidación. Esta página se puede abrir desde cualquier factura o pago sin registrar. Cuando se registra la transacción, también se registra la liquidación. Las transacciones también pueden liquidarse una vez registradas. Puede especificar y registrar un pago de cliente sin liquidarlo con una factura. Sin embargo, es posible que deba realizar una consulta en primer lugar para asegurarse de que el pago se liquida con la factura correcta. La página **Liquidar transacciones** se puede abrir desde las páginas **Todos los clientes** o **Todos los proveedores**, o desde la página **Transacciones** para cualquier cliente o proveedor. También puede reservar los anticipos registrados para una factura marcando el pago para la liquidación con un pedido de compra o un pedido de ventas. En este caso, el pago todavía tendrá saldo de apertura, pero no se podrá liquidar con otra factura. El pago se liquidará automáticamente con la factura creada a partir del pedido de compra o el pedido de ventas.

## <a name="how-to-settle-transactions"></a>Cómo liquidar transacciones
Las transacciones se pueden liquidar manualmente, automáticamente o mediante una combinación de los dos métodos. La opción de un método de liquidación depende de los procesos empresariales, que después se pueden implementar a través de la configuración de la liquidación en los parámetros de Proveedores y de Clientes. Puede crear pagos de proveedor y pagos por domiciliación bancaria del cliente mediante una propuesta de pago, que se usa para seleccionar facturas para pagar. La propuesta de pago se inicia manualmente, pero por otra parte Microsoft Dynamics 365 for Finance and Operations marcará automáticamente las facturas seleccionadas para la liquidación cuando se creen los pagos. Si los pagos se crean manualmente, puede usar la página **Liquidar transacciones** para seleccionar las facturas para la liquidación. Puede seleccionar manualmente las facturas o puede usar la opción **Marcar por prioridad** para tener facturas automáticamente marcadas para liquidación. La opción **Marcar por prioridad** solo está disponible para los clientes. Para habilitar esta opción, use la página **Prioridad liquidación** de parámetros de clientes. Si un administrativo de pagos especifica un pago, pero no lo liquida antes de registrarlo, el pago se podrá liquidar automáticamente. Puede habilitar la liquidación automática en los parámetros de proveedores y de clientes. Cuando usa la liquidación automática, puede usar el orden predefinido de liquidación o bien definir su propio orden de prioridad de liquidación en los parámetros de clientes. Esta funcionalidad solo está disponible para los clientes.

## <a name="results-of-settlement"></a>Resultados de liquidación
A medida que se liquidan las transacciones, el saldo pendiente de cada transacción se actualizan o se reduce como corresponda. En un escenario típico en el que se liquidan una factura y un pago, el estado y el saldo de cada transacción se actualiza según las reglas siguientes:

-   Si el importe del pago es superior al importe de la factura, el saldo de la factura se reduce a 0,00 y la factura se cerrará. El pago permanece abierto y el saldo es el importe en el que el pago excede el importe de la factura.
-   Si el importe del pago es inferior al importe de la factura, el saldo del pago se reduce a 0,00 y el pago se cerrará. La factura permanece abierta y el saldo es el importe en el que se pagó una parte de la factura.
-   Si el importe del pago es igual al importe de la factura, el pago y la factura se cerrarán y el saldo de ambos es 0,00.

Si un [pago es inferior al importe de la factura](../accounts-payable/vendor-payments-partial-amount.md) debido a un descuento por pronto pago, una cancelación o un pago insuficiente, la factura y el pago pueden seguir cerrados, en función de la configuración de la liquidación en los parámetros de proveedores y de clientes. La liquidación también puede generar transacciones. Por ejemplo, la liquidación de una factura y un pago puede producir un descuento por pronto pago, una pérdida o un beneficio realizados, ajustes de los impuestos, cancelaciones o diferencias de decimales.




