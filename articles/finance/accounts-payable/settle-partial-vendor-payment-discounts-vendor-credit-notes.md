---
title: Liquidar un pago de proveedor parcial con descuentos en notas de abono
description: Este artículo le guía por un escenario donde se liquida una nota de crédito con una factura.
author: abruer
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.custom: 14222
ms.assetid: 2b19f7fd-9ff9-4ee4-bddf-f582946d008e
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6e634796c7143c14a872c721f298f3ab28cbddd6
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5827851"
---
# <a name="settle-a-partial-vendor-payment-that-has-discounts-on-credit-notes"></a>Liquidar un pago de proveedor parcial con descuentos en notas de abono

[!include [banner](../includes/banner.md)]

Este artículo le guía por un escenario donde se liquida una nota de crédito con una factura.

Los proveedores de Fabrikam ofrecen descuentos por pronto pago en notas de abono. El proveedor 3.050 permite que Fabrikam aproveche un descuento por pronto pago del 1 por ciento si una factura se paga en 14 días.

## <a name="invoice-and-credit-memo"></a>Factura y nota de crédito
El 29 de junio, April crea una factura de 1.000,00 del proveedor 3050. El 2 de julio, crea una nota de abono de 200,00. Desde la página **Proveedores**, April abre la página **Liquidar transacciones**. April puede usar la página **Liquidar transacciones** para marcar la nota de abono y la factura para la liquidación. Un descuento de 2,00 se calcula en la nota de abono. Por lo tanto, el valor total de la nota de abono se reduce a 198,00.

| Marcar                     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Seleccionado                 | Normal            | Inv-10070 | 3050    | 29/6/2015 | 29/7/2015 | 10070   | -1.000,00                      | USD      | -990,00          |
| Seleccionado y resaltado | Normal            | CR-10070  | 3050    | 2/7/2015  | 29/7/2015 |         | 200,00                         | USD      | 198,00           |

La información de descuento para la nota de abono aparece en la parte inferior de la página **Liquidar transacciones abiertas**.

| Campo                        | Valor     |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 7/13/2015 |
| Importe de descuento por pronto pago         | 2.00      |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | 0,00      |
| Importe de descuento por pronto pago para aplicar | 2,00      |

April hace clic en **Registrar**. A continuación, revisa la liquidación completada. April observa que se han aplicado 198,00 de la nota de abono y que se ha aplicado un descuento de 2,00. Por lo tanto, el total es de 200,00.

| Marcar                     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura  | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|--------------------------|-------------------|-----------|---------|-----------|-----------|----------|--------------------------------|----------|------------------|
| Seleccionado y resaltado | Normal            | Inv-10070 | 3050    | 29/6/2015 | 29/7/2015 | 10070    | -1.000,00                      | USD      | -200,00          |
| Seleccionado                 | Normal            | CR-10070  | 3050    | 2/7/2015  | 29/7/2015 | CR-10070 | 200,00                         | USD      | 198,00           |

April puede revisar las transacciones del proveedor en la página **Transacciones de proveedor** seleccionando un proveedor en la página **Todos los proveedores** y continuación, en el panel de acciones, hacer clic en **Transacciones**. En esta página, April observa que la factura tiene un saldo de -800,00. También observa una nota de abono de 198,00 y un descuento de 2,00.

| Comprobante    | Tipo de transacción | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo | Divisa |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10070  | Factura          | 29/6/2015 | 10070   |                                      | 1.000,00                              | -800,00 | USD      |
| Inv-10071  |                  | 2/7/2015  | CR10071 | 200,00                               |                                       | 0,00    | USD      |
| DISC-10071 |  Descuento por pronto pago   | 2/7/2015  |         | 2,00                                 |                                       | 0,00    | USD      |
| DISC-10071 |  Descuento por pronto pago   | 2/7/2015  |         |                                      | 2,00                                  | 0,00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]