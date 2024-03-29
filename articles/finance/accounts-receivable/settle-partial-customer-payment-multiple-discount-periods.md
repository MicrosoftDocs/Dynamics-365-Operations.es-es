---
title: Liquidar un pago de cliente parcial con varios períodos de descuento
description: En este artículo se muestra cómo se liquidan los pagos de clientes parciales cuando hay varios períodos de descuento.
author: ShivamPandey-msft
ms.date: 11/15/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.custom: 14471
ms.assetid: b633a7c4-c18d-42e7-91cc-adcdc8a3ba98
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 62defda8831d2915050fc6822f60a905f067fe88
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778451"
---
# <a name="settle-a-partial-customer-payment-that-has-multiple-discount-periods"></a>Liquidar un pago de cliente parcial con varios períodos de descuento

[!include [banner](../includes/banner.md)]

En este artículo se muestra cómo se liquidan los pagos de clientes parciales cuando hay varios períodos de descuento.

Fabrikam ofrece al cliente 4.031 dos períodos de descuento por pronto pago. El cliente recibe un descuento por pronto pago del 2 por ciento si la factura se paga en cinco días, y un descuento por pronto pago del 1 por ciento si la factura se paga en 14 días. Fabrikam también ofrece descuentos por pronto pago en pagos parciales. Los parámetros de liquidación se encuentran en la página **Parámetros de clientes**.

## <a name="invoice"></a>Factura
El 25 de junio, Arnie introduce y registra una factura para 1.000,00 del cliente 4.031. Cuando Arnie revisa los descuentos por pronto pago de esta factura, Arnie ve que el cliente 4031 recibe un descuento de 20,00 si la factura se paga antes del 30 de junio. Si la factura se paga antes del 9 de julio, el cliente recibe un descuento de 10,00.

| Fecha del descuento por pronto pago | Importe de descuento por pronto pago | Importe en divisa de transacción |
|--------------------|----------------------|--------------------------------|
| 30/6/2020          | 20.00                | 980.00                         |
| 9/7/2020           | 10,00                | 990.00                         |
| 25/7/2020          | 0,00                 | 1.000,00                       |

Arnie puede ver esta transacción en la página **Transacciones de cliente**.

| Comprobante   | Tipo de transacción | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo  | Divisa |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10030 | Factura          | 25/6/2020 | 10030   | 1.000,00                             |                                       | 1.000,00 | USD      |

## <a name="partial-payment-before-the-cash-discount-date"></a>Pago parcial antes de la fecha de descuento por pronto pago
El 28 de junio, el cliente 4031 hace un pago parcial de 294,00. Dado que el 28 de junio se encuentra dentro del primer período de descuento por pronto pago, el cliente toma un descuento de 6,00. En la página **Liquidar transacciones**, el valor **Importe de descuento por pronto pago** es 20,00, y el valor **Importe de descuento por pronto pago para aplicar** es 6,00.

| Marcar     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Seleccionado | Normal            | FTI-10030 | 4031    | 25/6/2020 | 25/7/2020 | 10030   | 1.000,00                       | USD      | 294,00           |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones abiertas**. Si no cambia el valor **Importe para liquidar** a **294,00**, los valores de **Importe de descuento por pronto pago** que aparecen variarán. No obstante, se extraerá un valor de 6,00 como descuento por pronto pago cuando se registre el pago, ya que la liquidación ajusta automáticamente por usted **Importe para liquidar**.

| &nbsp;                       | &nbsp;    |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 30/6/2020 |
| Importe de descuento por pronto pago         | 20.00     |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | 0,00      |
| Importe de descuento por pronto pago para aplicar | 6,00      |

Después de que Arnie registre el pago, el saldo de la factura es de 700,00.

## <a name="partial-payment-before-the-second-cash-discount-date"></a>Pago parcial antes antes de la fecha del segundo descuento por pronto pago
El 8 de julio, el cliente paga el resto del importe de la factura. Se aplica un descuento de 7,00 (1 por ciento), ya que el pago se ha realizado dentro del segundo período de descuento por pronto pago.

| Marcar     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Divisa | Importe para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------|-----------------------|----------|------------------|
| Seleccionado | Normal            | FTI-10030 | 4031    | 25/6/2020 | 25/7/2020 | 10030   | 700.00       |            | USD      | 693,00           |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones abiertas**.

| &nbsp;                       | &nbsp;    |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 09/7/2020 |
| Importe de descuento por pronto pago         | 30.00     |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | 6,00      |
| Importe de descuento por pronto pago para aplicar | 7,00      |

El saldo de la factura es ahora de 0,00. Arnie ve la información en la página **Transacciones de clientes**.

| Comprobante    | Tipo de transacción | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo | Divisa |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10030  | Factura          | 25/6/2020 | 10030   | 1.000,00                             |                                       | 0,00    | USD      |
| ARP-10030  |  Pago         | 28/6/2020 |         |                                      | 294,00                                | 0,00    | USD      |
| DISC-10030 |  Descuento por pronto pago   | 28/6/2020 |         |                                      | 6,00                                  | 0,00    | USD      |
| ARP-10031  |  Pago         | 8/7/2020  |         |                                      | 693,00                                | 0,00    | USD      |
| DISC-1031  |  Descuento por pronto pago   | 8/7/2020  |         |                                      | 7.00                                  | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
