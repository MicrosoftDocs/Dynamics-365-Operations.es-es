---
title: Descripción de la liquidación
description: En este tema se proporciona información general sobre el proceso de liquidación. Describe qué tipos de transacción se pueden liquidar, y el momento y el proceso para liquidarlos. También describe los resultados del proceso de liquidación.
author: kweekley
ms.date: 04/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14551"
- intro-internal
ms.assetid: 0968fa71-5984-415b-8689-759a0136d5d1
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-10-31
ms.dyn365.ops.version: 8.0999999999999996
ms.openlocfilehash: 30a96b377d70c74a29e9e90699ccb077c727b20758378b5336660c6c056c6022
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755699"
---
# <a name="settlement-overview"></a>Descripción de la liquidación

[!include [banner](../includes/banner.md)]

En este tema se proporciona información general sobre el proceso de liquidación. Describe qué tipos de transacción se pueden liquidar, y el momento y el proceso para liquidarlos. También describe los resultados del proceso de liquidación.

Durante la liquidación, las transacciones en un documento se aplican a las transacciones en otro documento para aumentar o reducir los saldos de cada documento. Por ejemplo, un pago se puede aplicar a una factura. Pueden liquidarse distintos tipos de transacción, en diferentes momentos y con diferentes métodos. El proceso de liquidación puede también generar nuevas transacciones.

## <a name="what-transactions-can-be-settled"></a>Qué transacciones se pueden liquidar

En Proveedores y Clientes puede tener lugar la liquidación entre los tipos de transacción que afectan al saldo del proveedor o al saldo del cliente. Estos tipos de transacciones pueden incluir facturas, pagos, notas de crédito y tarifas. Cualquier tipo de transacción puede liquidarse con cualquier otro tipo de transacción. Por ejemplo, puede liquidar un pago frente a una factura, una nota de crédito frente a una factura, una factura frente a otra factura y un pago frente a otro pago.

Puede liquidar pagos con una transacción en la misma entidad jurídica o en otra entidad jurídica. En las organizaciones que usan un modelo de pagos centralizados, las [pagos centralizados](set-up-centralized-payments.md) pueden ayudar a simplificar el proceso de pago.

## <a name="when-to-settle-transactions"></a>Cuándo liquidar transacciones

Las transacciones se pueden liquidar cuando se introducen los pagos. Por ejemplo, si hace un pago a un proveedor, normalmente selecciona qué facturas pagar. Al seleccionar facturas, se marcan para la liquidación contra el pago. Cuando los contables de pagos de clientes registran pagos de cliente, pueden marcar las facturas adecuadas para su liquidación, en función de la información que se incluye en cada pago del cliente. Use la página **Liquidar transacciones** para marcar las transacciones para liquidación. Puede abrir esta página desde cualquier factura o pago sin contabilizar. Cuando se registra la transacción, también se registra la liquidación. 

Las transacciones también pueden liquidarse una vez registradas. Puede especificar y registrar un pago de cliente sin liquidarlo con una factura. Sin embargo, es posible que quiera asegurarse de que el pago se liquida con la factura correcta antes de contabilizar la liquidación. La página **Liquidar transacciones** se puede abrir desde las páginas **Todos los clientes** o **Todos los proveedores**, o desde la página **Transacciones** para cualquier cliente o proveedor.

También puede reservar los anticipos registrados para una factura marcando el pago para la liquidación con un pedido de compra o un pedido de ventas. En este caso, el pago todavía tendrá saldo de apertura, pero no se podrá liquidar con otra factura. El pago se liquidará automáticamente con la factura creada a partir del pedido de compra o el pedido de ventas.

## <a name="how-to-settle-transactions"></a>Cómo liquidar transacciones

Las transacciones se pueden liquidar manualmente, automáticamente o mediante una combinación de los dos métodos. La elección de un método de liquidación depende de sus procesos comerciales. En las páginas **Parámetros de proveedores** y **Parámetros de clientes**, puede configurar el proceso de liquidación para que esté alineado con esos procesos empresariales.

Puede crear pagos de proveedores y pagos por domiciliación bancaria de clientes mediante propuestas de pago. Se utiliza una propuesta de pago para seleccionar facturas a pagar. La propuesta de pago se inicia manualmente, y luego el sistema marcará automáticamente las facturas seleccionadas para liquidación cuando se creen los pagos.

Si los pagos se crean manualmente, puede usar la página **Liquidar transacciones** para seleccionar las facturas para la liquidación. Puede seleccionar manualmente las facturas o puede usar la opción **Marcar por prioridad** para tener facturas automáticamente marcadas para liquidación. La opción **Marcar por prioridad** solo está disponible para los clientes. Puede activar esta opción en la pestaña **Prioridad de liquidación** de la página **Parámetros de clientes**.

Si un administrativo de pagos especifica un pago, pero no lo liquida antes de contabilizarlo, el pago puede liquidarse automáticamente. Puede activar la liquidación automática en las páginas **Parámetros de clientes** y **Parámetros de proveedores**. La liquidación automática liquida las transacciones solo en la misma entidad jurídica. No liquida transacciones entre múltiples entidades jurídicas.

Cuando usa la liquidación automática, puede usar la prioridad de liquidación predefinida o bien definir su propia prioridad de liquidación en la página **Parámetros de clientes**. Esta funcionalidad solo está disponible para los clientes.

## <a name="results-of-settlement"></a>Resultados de liquidación

A medida que se liquidan las transacciones, el saldo pendiente de cada transacción se incrementa o se reduce, como corresponda. Normalmente, cuando se liquidan una factura y un pago, el estado y el saldo de cada transacción se actualiza según las reglas siguientes:

- Si el importe del pago es superior al importe de la factura, el saldo de la factura se reduce a 0,00 y la factura se cerrará. El pago permanece abierto y el saldo es la diferencia entre el importe del pago y el importe de la factura.
- Si el importe del pago es inferior al importe de la factura, el saldo del pago se reduce a 0,00 y el pago se cerrará. La factura permanece abierta y el saldo es la diferencia entre el importe de la factura y el importe del pago.
- Si el importe del pago es igual al importe de la factura, el pago y la factura se cerrarán y el saldo de ambos se reduce a 0,00.

Si el [importe del pago es inferior al importe de la factura](../accounts-payable/vendor-payments-partial-amount.md) debido a un descuento por pronto pago, una cancelación o un pago insuficiente, podría llegar a cerrarse la factura y el pago, dependiendo de cómo se configuren las liquidaciones en las páginas **Parámetros de proveedores** y **Parámetros de clientes**.

Las liquidaciones también pueden generar transacciones. Por ejemplo, la liquidación de una factura y un pago puede producir un descuento por pronto pago, una pérdida o un beneficio realizados, ajustes de los impuestos, cancelaciones o diferencias de decimales.

## <a name="identifying-marked-transactions-during-settlement"></a>Identificar transacciones marcadas durante la liquidación

Cuando intente liquidar una transacción, puede observar un símbolo que indica que la transacción está marcada en otra ubicación. En este caso, puede seleccionar la transacción en la página **Liquidar transacciones** y luego seleccionar **Consulta \> Liquidación desde la ventana de liquidación**. La vista para esta consulta muestra diarios, pedidos de ventas, facturas, propuestas de pago y ubicaciones de clientes que podrían estar bloqueando la transacción. Para resolver el problema, puede seleccionar el vínculo para ir directamente desde la consulta a la ubicación bloqueada. Luego puede actualizar el documento con los ajustes necesarios para resolverlo. También puede usar el indicador **Marcado** para identificar otros documentos que están incluidos en la misma ubicación de bloqueo.

## <a name="additional-resources"></a>Recursos adicionales

- [Resto de liquidación](settle-remainder.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]