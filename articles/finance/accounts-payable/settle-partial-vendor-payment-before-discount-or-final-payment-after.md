---
title: Liquidar un pago parcial antes de la fecha de descuento y un pago final después de la fecha de descuento
description: Este tema le guía por un escenario donde se realizan múltiples pagos parciales, algunos dentro del período del descuento por pronto pago y otros fuera del período de descuento por pronto pago.
author: abruer
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14411
ms.assetid: 302ad6ae-28ee-4899-9f6b-f74424a5f50c
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7331b4b2ad48cfa380497336d4ac22c8723568b5
ms.sourcegitcommit: 1d2eeacad11c28889681504cdc509c90e3e8ea86
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "8716758"
---
# <a name="settle-partial-payment-before-discount-date-and-final-payment-after-discount-date"></a>Liquidar un pago parcial antes de la fecha de descuento y un pago final después de la fecha de descuento

[!include [banner](../includes/banner.md)]

Este tema le guía por un escenario donde se realizan múltiples pagos parciales, algunos dentro del período del descuento por pronto pago y otros fuera del período de descuento por pronto pago.

Fabrikam compra bienes del proveedor 3057. Fabrikam recibe un descuento por pronto pago del 1 por ciento si la factura se paga en 14 días. Las facturas se deben pagar en 30 días. El proveedor también permite que Fabrikam aproveche descuentos por pronto pago sobre pagos parciales. Los parámetros de liquidación se encuentran en la página **Parámetros de proveedores**.

## <a name="invoice-on-june-25"></a>Factura el 25 de junio
El 25 de junio, Arnie introduce y registra una factura para 1.000,00 del proveedor 3057. April puede ver esta transacción en la página **Transacciones de proveedor**.

| Comprobante   | Tipo de transacción | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo   | Divisa |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10020 | Factura          | 25/6/2015 | 10020   |                                      | 1.000,00                              | -1.000,00 | USD      |

## <a name="partial-payment-on-july-2"></a>Pago parcial el 2 de julio
El 2 de julio, April quiere liquidar 300,00 de esta factura. El pago puede optar a un descuento, ya que Fabrikam acepta descuentos en los pagos parciales. Por lo tanto, April paga 297,00 y aprovecha un descuento de 3,00. Crea un diario de pagos y especifica una línea para el proveedor 3057. A continuación, abre la página **Liquidar transacciones** para marcar la factura para su liquidación.

| Marcar     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Seleccionado | Normal            | Inv-10020 | 3057    | 25/6/2015 | 25/7/2015 | 10020   | -1.000,00                      | USD      | -297,00          |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones abiertas**.

| Campo                        | Valor     |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 09/7/2015 |
| Importe de descuento por pronto pago         | -10,00    |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | 0,00      |
| Importe de descuento por pronto pago para aplicar | -3,00     |

A continuación, April registra el pago. La factura tiene ahora un saldo de 700,00. April puede ver esta transacción en la página **Transacciones de proveedor**.

| Comprobante    | Tipo de transacción | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo | Divisa |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Factura          | 25/6/2015 | 10020   |                                      | 1.000,00                              | -700,00 | USD      |
| APP-10020  | Pago          | 7/1/2015  |         | 297,00                               |                                       | 0,00    | USD      |
| DISC-10020 | Descuento por pronto pago    | 7/1/2015  |         | 3,00                                 |                                       | 0,00    | USD      |

## <a name="remaining-payment-on-july-15-use-cash-discount--normal"></a>Pago restante el 15 de julio, uso de descuento por pronto pago = Normal
April paga el resto de la factura el 15 de julio, tras el período de descuento. En la página **Liquidar transacciones abiertas** no se muestra ningún importe de descuento en el campo **Descuento estimado por pronto pago**, y el valor del campo **Importe de descuento por pronto pago** es **0,00**. Cuando April pague el importe restante de 700,00, no se aplicará ningún descuento adicional.

| Marcar     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Seleccionado | Normal            | Inv-10020 | 3057    | 25/6/2015 | 25/7/2015 | 10020   | -700,00                        | USD      | -700,00          |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones**. April puede observar que ya ha aprovechado un descuento de 3,00.

| Campo                        | Valor     |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 09/7/2015 |
| Importe de descuento por pronto pago         | 0,00      |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | -3,00     |
| Importe de descuento por pronto pago para aplicar | 0,00      |

A continuación, April registra el pago. Cuando abre la página **Transacciones de proveedor**, observa que la factura tiene un saldo de 0,00. También puede ver que existen dos pagos. Un pago es de 297,00 con un descuento de 3,00 y el otro pago es de 700,00.

| Comprobante    | Tipo de transacción | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo | Divisa |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Factura          | 25/6/2015 | 10020   |                                      | 1.000,00                              | 0,00    | USD      |
| APP-10020  | Pago          | 7/1/2015  |         | 297,00                               |                                       | 0,00    | USD      |
| DISC-10020 | Descuento por pronto pago    | 7/1/2015  |         | 3,00                                 |                                       | 0,00    | USD      |
| APP-10021  | Pago          | 15/7/2015 |         | 700,00                               |                                       | 0,00    | USD      |

## <a name="remaining-payment-on-july-15-use-cash-discount--always"></a>Pago restante el 15 de julio, uso de descuento por pronto pago = Siempre
Si el proveedor permite a April disfrutar de un descuento aunque pague después de la fecha de descuento, puede cambiar el valor del campo **Utilizar descuento por pronto pago** a **Siempre**. El ajuste **Calcular descuento por pronto pago para pagos parciales** se anula y se obtiene el descuento. El importe del pago es de 693,00 y el descuento corresponde al importe restante de 7,00.

| Marcar     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Divisa | Importe para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Seleccionado | Siempre            | Inv-10020 | 3057    | 25/6/2015 | 25/7/2015 | 10020   | 700,00                               |                                       | USD      | -693,00          |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones**.

| Campo                        | Valor     |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 09/7/2015 |
| Importe de descuento por pronto pago         | 7.00      |
| Utilizar el descuento por pronto pago            | Siempre    |
| Descuento por pronto pago aplicado          | -3,00     |
| Importe de descuento por pronto pago para aplicar | -7,00     |

A continuación, April registra el pago. Cuando abre la página **Transacciones de proveedor**, observa que la factura tiene un saldo de 0,00. También puede ver que existen dos pagos. Un pago es de 297,00 con un descuento de 3,00 y el otro pago es de 693,00 con un descuento de 7,00.

| Comprobante    | Tipo de transacción | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo | Divisa |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10020  | Factura          | 25/6/2015 | 10020   |                                      | 1.000,00                              | 0,00    | USD      |
| APP-10020  | Pago          | 7/1/2015  |         | 297,00                               |                                       | 0,00    | USD      |
| DISC-10020 | Descuento por pronto pago    | 7/1/2015  |         | 3,00                                 |                                       | 0,00    | USD      |
| APP-10021  | Pago          | 15/7/2015 |         | 693,00                               |                                       | 0,00    | USD      |
| DISC-10021 | Descuento por pronto pago    | 15/7/2015 |         | 7,00                                 |                                       | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
