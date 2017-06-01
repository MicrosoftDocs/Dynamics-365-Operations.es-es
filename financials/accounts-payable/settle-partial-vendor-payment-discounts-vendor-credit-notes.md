---
title: Liquidar un pago de proveedor parcial con descuentos en notas de abono de proveedor
description: "Este artículo le guía por un escenario donde se liquida una nota de crédito con una factura."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14222
ms.assetid: 2b19f7fd-9ff9-4ee4-bddf-f582946d008e
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: f227a630f7d1245d5db810d6d48df2b20f699185
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="settle-a-partial-vendor-payment-that-has-discounts-on-vendor-credit-notes"></a>Liquidar un pago de proveedor parcial con descuentos en notas de abono de proveedor

[!include[banner](../includes/banner.md)]


Este artículo le guía por un escenario donde se liquida una nota de crédito con una factura.

Los proveedores de Fabrikam ofrecen descuentos por pronto pago en notas de abono. El proveedor 3.050 permite que Fabrikam aproveche un descuento por pronto pago del 1 por ciento si una factura se paga en 14 días.

## <a name="invoice-and-credit-memo"></a>Factura y nota de crédito
El 29 de junio, April crea una factura de 1.000,00 del proveedor 3050. El 2 de julio, crea una nota de abono de 200,00. Desde la página **Proveedores**, April abre la página **Liquidar transacciones**. April puede usar la página **Liquidar transacciones** para marcar la nota de abono y la factura para la liquidación. Un descuento de 2,00 se calcula en la nota de abono. Por lo tanto, el valor total de la nota de abono se reduce a 198,00.

| Marcar                     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Seleccionado                 | Normal            | Inv-10070 | 3050    | 29/6/2015 | 29/7/2015 | 10070   | -1.000,00                      | USD      | -990,00          |
| Seleccionado y resaltado | Normal            | CR-10070  | 3050    | 2/7/2015  | 29/7/2015 |         | 200,00                         | USD      | 198,00           |

La información de descuento para la nota de abono aparece en la parte inferior de la página **Liquidar transacciones abiertas**.

|                              |           |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 7/13/2015 |
| Importe de descuento por pronto pago         | 2,00      |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | 0,00      |
| Importe de descuento por pronto pago para aplicar | 2,00      |

April hace clic en **Registrar**. A continuación, revisa la liquidación completada. April observa que se han aplicado 198,00 de la nota de abono y que se ha aplicado un descuento de 2,00. Por lo tanto, el total es de 200,00.

| Marcar                     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura  | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|--------------------------|-------------------|-----------|---------|-----------|-----------|----------|--------------------------------|----------|------------------|
| Seleccionado y resaltado | Normal            | Inv-10070 | 3050    | 29/6/2015 | 29/7/2015 | 10070    | -1.000,00                      | USD      | -200,00          |
| Seleccionado                 | Normal            | CR-10070  | 3050    | 2/7/2015  | 29/7/2015 | CR-10070 | 200,00                         | USD      | 198,00           |

April puede revisar las transacciones del proveedor en la página **Transacciones de proveedor** seleccionando un proveedor en la página **Todos los proveedores**y continuación, en el panel de acciones, hacer clic en **Transacciones**. En esta página, April observa que la factura tiene un saldo de -800,00. También observa una nota de abono de 198,00 y un descuento de 2,00.

| Comprobante    | Tipo de transacción | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo | Divisa |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10070  | Factura          | 29/6/2015 | 10070   |                                      | 1.000,00                              | -800,00 | USD      |
| Inv-10071  |                  | 2/7/2015  | CR10071 | 200,00                               |                                       | 0,00    | USD      |
| DISC-10071 |  Descuento por pronto pago   | 2/7/2015  |         | 2,00                                 |                                       | 0,00    | USD      |
| DISC-10071 |  Descuento por pronto pago   | 2/7/2015  |         |                                      | 2,00                                  | 0,00    | USD      |






