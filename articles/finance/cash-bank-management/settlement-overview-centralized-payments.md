---
title: Vista general de la liquidación para pagos centralizados
description: Este tema describe el acuerdo para pagos centralizados para Microsoft Dynamics 365 Finance.
author: abruer
manager: AnnBe
ms.date: 08/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 222414
ms.assetid: 610f6858-0f37-4d0f-8c68-bab5a971ef4a
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e66d5aac0c2ed966727ef569ac5345fcd91b841e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4989211"
---
# <a name="settlement-overview-for-centralized-payments"></a>Vista general de la liquidación para pagos centralizados

[!include [banner](../includes/banner.md)]

Las organizaciones que constan de diversas entidades jurídicas pueden crear y administrar pagos con una entidad jurídica que controle todos los pagos. De esta forma, se elimina la necesidad de introducir la misma transacción en las diversas entidades jurídicas y se obtiene un importante ahorro de tiempo al racionalizar el proceso de propuestas de pago, el proceso de liquidación, la edición de transacciones abiertas y la edición de transacciones cerradas de los pagos centralizados. 

Cuando se indica un pago de cliente o proveedor en una entidad jurídica y se liquida con una factura que se ha especificado en otra entidad jurídica, las transacciones de la liquidación aplicable y las transacciones de destinatario de pago y de remitente de pago se generan automáticamente para cada entidad jurídica. Se crea un registro de liquidación para cada combinación de factura y pago en la transacción. Cada registro de liquidación se asigna a un nuevo número de asiento, basado en la serie de secuencia numérica del comprobante de pago especificada en la página de **Parámetros de cuentas de clientes** para clientes y en la página de **Parámetros de cuentas de proveedores** para proveedores. 

Si se generan registros de liquidación adicionales para descuentos por pronto pago, revalorizaciones de divisa extranjera, diferencias de decimales, sobrepagos o pagos insuficientes, éstos se asignan en la última fecha de la transacción de pago o factura. Si la liquidación se efectúa una vez registrado el pago, los registros de liquidación usan la fecha de registro de la liquidación especificada en la página **Liquidación de transacciones abiertas**.

## <a name="posting-types-transaction-types-and-default-descriptions"></a>Tipos de registro, tipos de transacción y descripciones predeterminadas

Las transacciones de asientos de liquidación de empresas vinculadas usan el tipo de registro de la liquidación de empresas vinculadas, la liquidación de clientes de empresas vinculadas y los tipos de transacción de liquidación del proveedor de empresas vinculadas. En la página **Descripciones predeterminadas** se puede configurar la información para el tipo de transacción. 

Los siguientes tipos de transacción están disponibles para usarlos en liquidaciones entre empresas y de empresas únicas.

-   Liquidación
-   Descuento por pronto pago
-   Revalorizaciones de divisa extranjera (incluidas las realizadas y las no realizadas)
-   Diferencias de decimales
-   Sobrepago/pago insuficiente

También se pueden definir descripciones predeterminadas para los asientos de liquidación de empresas vinculadas.

## <a name="currency-exchange-gains-or-losses"></a>Pérdidas o ganancias por cambio de divisa

El tipo de cambio que se usa para las transacciones de cliente o proveedor se almacena en la transacción. Las pérdidas o los beneficios realizados de cambios de divisas se registran en la entidad jurídica de factura o la entidad jurídica del pago, en función de la opción que seleccionada en el campo **Registro de pérdidas o beneficios del cambio de divisas** de la página **Contabilidad de empresas vinculadas** para la entidad jurídica del pago. Los siguientes ejemplos usan estas divisas:
-   Divisa de contabilidad de pago: EUR
-   Divisa de contabilidad de factura: USD
-   Divisa de la transacción de pago: DKK
-   Divisa de transacción de factura: CAD

### <a name="currency-calculations"></a>Cálculos de divisas

Al liquidar una factura especificada en una entidad jurídica con un pago especificado en otra entidad jurídica, la divisa de la transacción de pago (DKK) se convierte mediante tres pasos:
1.  Se convierte a la divisa de contabilidad de pago (EURO) usando los tipos de cambio de la entidad jurídica del pago.
2.  Se convierte a la divisa de contabilidad de factura (USD).
3.  Se convierte a la divisa de la transacción de factura (CAD), mediante los tipos de cambio de la entidad jurídica de facturación.

El proceso de conversión usa los tipos de cambio de la fecha de pago. Si el importe de pago resultante en la divisa de la transacción de la factura (CAD) es igual al importe de la factura (CAD), la factura se considerará totalmente pagada. 

Si se abre la página **Liquidación de transacciones abiertas** desde un diario de pagos en que el importe de pago no se ha indicado, el importe a liquidar se calculará en función de las facturas seleccionadas para la liquidación en la página **Liquidación de transacciones abiertas**. El importe a liquidar se convierte en tres pasos:
1.  Se convierte a la divisa de contabilidad de factura (USD), mediante los tipos de cambio de la entidad jurídica de facturación en la fecha de pago.
2.  Se convierte a la divisa de contabilidad de pago (EUR), mediante los tipos de cambio de la entidad jurídica de facturación en la fecha de pago.
3.  Se convierte a la divisa de la transacción de pago (DKK).

El importe de pago resultante se transfiere a la línea del diario de pagos cuando se cierra la página **Liquidación de transacciones abiertas**.

### <a name="posting-for-gain-or-loss-because-of-different-accounting-currencies"></a>Registro para la ganancia o pérdida debido a distintas divisas de contabilidad

Si existe una pérdida o ganancia por cambio de divisas, se registrará en la entidad jurídica especificada en el campo **Registro de pérdidas o beneficios del cambio de divisas** en la página **Contabilidad de empresas vinculadas** para la entidad jurídica del pago. El importe de pérdida o ganancia se convertirá a la divisa de contabilidad de la entidad jurídica en la que el importe de ganancia o pérdida está registrado, mediante el tipo de cambio definido para esa entidad jurídica.

## <a name="cash-discounts"></a>Descuentos por pronto pago

Los descuentos generados durante el proceso de liquidación entre empresas se registran en la entidad jurídica de facturación o en la entidad jurídica de pago, en función de la opción seleccionada en el campo **Registro del descuento por pronto pago** de la página **Contabilidad de empresas vinculadas** para la entidad jurídica de pago. En la entidad jurídica de facturación se genera una transacción de liquidación correspondiente.

## <a name="overpayments-and-underpayments"></a>Sobrepagos y pagos insuficientes

Las tolerancias de diferencias de decimales y sobrepagos/pagos insuficientes, se determinan en función de la entidad jurídica pagadora para los sobrepagos, y en función de la entidad jurídica de facturación para los pagos insuficientes. La cuenta de registro que se usa viene determinada por la configuración del campo **Administración de descuentos de efectivo** de la página **Parámetros de clientes** y el campo **Administración de descuentos de efectivo** de la página **Parámetros de proveedores**.

-   Si la configuración de administración del descuento es Determinada, o si la configuración es Indeterminada y el descuento aplicable se ha registrado en una entidad jurídica diferente a la del sobrepago, se usa la cuenta automática para descuentos de Cliente, descuentos de Proveedor o Diferencia de decimales de la divisa contable. Puede especificar estas cuentas en la página **Cuentas para transacciones automáticas**.
-   Si la configuración de administración del descuento es Indeterminada y el descuento se ha registrado en la misma entidad jurídica que el sobrepago (la entidad jurídica pagadora y la de facturación son la misma), se ajustará la cuenta de descuentos de efectivo. Por ejemplo, si se liquida una factura para 100,00 con un descuento por pronto pago disponible de 3,00 con un pago de 98,00, la cuenta de descuentos por pronto pago se ajustará para 1,00. El importe de descuento neto es 2,00.
-   Si la configuración de administración del descuento es Indeterminada, el descuento se ha registrado en la misma entidad jurídica que el sobrepago y el sobrepago o pago insuficiente se ha liquidado con varias facturas con descuentos de efectivo, la cuenta de descuentos se ajustará para la última factura.

Si la selección de administración del descuento es Indeterminada, se aplicarán reglas de liquidación de pago no específico, únicamente en las siguientes situaciones:
-   Existe un sobrepago.
-   El sobrepago se liquida con una o varias facturas con descuentos por pronto pago.
-   El descuento por pronto pago se registra en la misma entidad jurídica que el sobrepago.

En el resto de situaciones, los sobrepagos o pagos insuficientes se registrarán en la cuenta automática para Descuento de cliente, descuento de proveedor o diferencia de decimales en la divisa contable.

## <a name="sales-tax"></a>Impuestos
Las transacciones de impuestos permanecen en la entidad jurídica en las que se han registrado originalmente. 

Si se han registrado impuestos para un pago adelantado, la liquidación entre empresas invierte los impuestos del pago adelantado en la entidad jurídica en que se ha efectuado. Los impuestos de la entidad jurídica de facturación permanecen en la entidad jurídica de facturación.

## <a name="financial-dimensions"></a>Dimensiones financieras
Para los pagos de clientes, las transacciones de destinatario de pago y de remitente de pago de la entidad jurídica pagadora usan las dimensiones financieras especificadas para la cuenta de resumen de clientes del pago que se liquida. En la entidad jurídica de facturación, las transacciones de destinatario de pago y de remitente de pago usan las dimensiones financieras especificadas para la cuenta de resumen de clientes de la factura que se liquida. 

Para los pagos de proveedores, las transacciones de destinatario de pago y de remitente de pago de la entidad jurídica del pago usan las dimensiones financieras especificadas para la cuenta de resumen de proveedores del pago que se liquida. En la entidad jurídica de facturación, las transacciones de destinatario de pago y de remitente de pago usan las dimensiones financieras especificadas para la cuenta de resumen de proveedores de la factura que se liquida.

## <a name="withholding-tax"></a>Retención de impuestos
La cuenta del proveedor asociada a la factura se usa para determinar si la retención de impuestos se debe calcular. Si se aplica la retención de impuestos, se calcula en la entidad jurídica asociada a la factura. Si las entidades jurídicas usan distintas divisas, se usará el tipo de cambio de la entidad jurídica asociada con la factura.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]