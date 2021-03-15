---
title: Liquidar un pago parcial antes de la fecha de descuento con un pago final después de la fecha de descuento
description: En este artículo se aborda el efecto de liquidar pagos de las facturas para los clientes. El escenario se centra en los efectos del subdiario, no en la Contabilidad general.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.custom: 14584
ms.assetid: e54936f5-053b-4ed3-b778-42c7e9aeb7cf
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ad922bc6c9378078012b7a838909e4074b48f263
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4979073"
---
# <a name="settle-partial-payment-before-discount-date-with-final-payment-after-discount-date"></a>Liquidar un pago parcial antes de la fecha de descuento con un pago final después de la fecha de descuento

[!include [banner](../includes/banner.md)]

En este artículo se aborda el efecto de liquidar pagos de las facturas para los clientes. El escenario se centra en los efectos del subdiario, no en la Contabilidad general.

Fabrikam vende productos al cliente 4027. Fabrikam ofrece un descuento por pronto pago del uno por ciento si la factura se paga en 14 días. Las facturas se deben pagar en 30 días. Fabrikam también ofrece descuentos por pronto pago en pagos parciales. Los parámetros de liquidación se encuentran en la página **Parámetros de clientes**.

## <a name="invoice"></a>Factura
El 25 de junio, Arnie introduce y registra una factura de 1.000,00 del cliente 4.027. Arnie puede ver esta transacción si usa el botón **Transacciones** en la página **Clientes**.

| Comprobante   | Tipo de transacción | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo  | Divisa |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10020 | Factura          | 25/6/2015 | 10020   | 1.000,00                             |                                       | 1.000,00 | USD      |

## <a name="partial-payment-before-the-cash-discount-date"></a>Pago parcial antes de la fecha de descuento por pronto pago
El 2 de julio, el cliente 4027 hace un pago parcial de 297,00 para la factura. El pago puede optar a un descuento por pronto pago, porque Fabrikam ofrece descuentos por pronto pago en los pagos parciales y el pago parcial se realiza antes de la fecha de descuento por pronto pago. Por lo tanto, el cliente 4027 aprovecha un descuento por pronto pago de 3,00. Arnie registra el pago del cliente 4027 mediante el diario de pagos. A continuación, Arnie abre la página **Liquidar transacciones** para poder marcar la factura para su liquidación.

| Marcar     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en débito en divisa de transacción | Divisa | Importe para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|----------|------------------|
| Seleccionado | Normal            | FTI-10020 | 4027    | 25/6/2015 | 25/7/2015 | 10020   | 1.000,00                             | USD      | 297,00           |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones abiertas**. Si no cambia el valor de **Importe para liquidar** a 297,00, los valores de **Importe de descuento por pronto pago** que aparecen variarán. No obstante, se extraerá un valor de 3,00 como descuento por pronto pago cuando se registre el pago, ya que la liquidación ajusta automáticamente el valor de **Importe para liquidar**.

|                              |           |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 09/7/2015 |
| Importe de descuento por pronto pago         | 10,00     |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | 0,00      |
| Importe de descuento por pronto pago para aplicar | 3,00      |

Arnie registra este pago. La factura tiene ahora un saldo de 700,00. Se pueden ver las siguientes transacciones para el cliente.

| Comprobante    | Tipo de transacción | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo | Divisa |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10020  | Factura          | 25/6/2015 | 10020   | 1.000,00                             |                                       | 700,00  | USD      |
| ARP-10020  |  Pago         | 1/7/2015  |         |                                      | 297,00                                | 0,00    | USD      |
| DISC-10020 |  Descuento por pronto pago   | 1/7/2015  |         |                                      | 3,00                                  | 0,00    | USD      |

## <a name="remaining-payment-after-the-cash-discount-date"></a>Pago restante después de la fecha de descuento por pronto pago
El 11 de julio, que es después del período de descuento, el cliente 4027 paga el resto de la factura. En la página **Liquidar transacciones**, no aparece ningún importe de descuento en el campo **Descuento estimado por pronto pago** y el valor del campo **Importe de descuento por pronto pago** es **0,00**. Cuando el cliente 4027 paga el importe restante de 700,00, no se aplica ningún descuento adicional.

| Marcar     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en débito en divisa de transacción | Divisa | Importe para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|----------|------------------|
| Seleccionado | Normal            | FTI-10020 | 4027    | 25/6/2015 | 25/7/2015 | 10020   | 700,00                               | USD      | 700,00           |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones abiertas**.

|                              |           |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 09/7/2015 |
| Importe de descuento por pronto pago         | 0,00      |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | 3,00      |
| Importe de descuento por pronto pago para aplicar | 0,00      |

Si Arnie cambia el valor en el campo **Utilizar descuento por pronto pago** a **Siempre**, se invalida el ajuste **Calcular descuento por pronto pago para pagos parciales** y se obtiene el descuento por pronto pago. El importe del pago cambia a 693,00 y el descuento por pronto pago corresponde al importe restante de 7,00.

| Marcar     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Divisa | Importe para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Seleccionado | Siempre            | FTI-10020 | 4027    | 25/6/2015 | 25/7/2015 | 10020   | 700,00                               |                                       | USD      | 693,00           |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones abiertas**.

|                              |           |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 09/7/2015 |
| Importe de descuento por pronto pago         | 7,00      |
| Utilizar el descuento por pronto pago            | Siempre    |
| Descuento por pronto pago aplicado          | 3,00      |
| Importe de descuento por pronto pago para aplicar | 7,00      |

Arnie cambia de nuevo el valor del campo **Utilizar descuento por pronto pago** a **Normal** porque no desea permitir que este cliente aproveche el descuento por pronto pago restante de 7,00. A continuación, Arnie registra el pago. Cuando Arnie abre la página **Transacciones de cliente**, observa que la factura tiene un saldo de 0,00. También puede ver que existen dos pagos. Un pago es de 297,00 con un descuento por pronto pago de 3,00 y el otro pago es de 700,00.

| Comprobante    | Tipo de transacción | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo | Divisa |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10020  | Factura          | 25/6/2015 | 10020   | 1.000,00                             |                                       | 0,00    | USD      |
| ARP-10020  |                  | 1/7/2015  |         |                                      | 297,00                                | 0,00    | USD      |
| DISC-10020 |                  | 1/7/2015  |         |                                      | 3,00                                  | 0,00    | USD      |
| ARP-10021  |                  | 11/7/2015 |         |                                      | 700,00                                | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]