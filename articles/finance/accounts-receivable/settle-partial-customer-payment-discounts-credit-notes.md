---
title: Liquidar un pago de cliente parcial con descuentos en notas de abono de proveedor
description: Este artículo le guía por un escenario en el que se aplica un descuento por pronto pago en una nota de abono cuando la factura original también tenía un descuento por pronto pago.
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
ms.custom: 14564
ms.assetid: d9984cef-ddcf-46bd-816d-c01b8cc5cf48
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3823dd02f9bc2da935ac7e9845c6314d7cbfcfaa
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971661"
---
# <a name="settle-a-partial-customer-payment-that-has-discounts-on-credit-notes"></a>Liquidar un pago de cliente parcial con descuentos en notas de abono de proveedor

[!include [banner](../includes/banner.md)]

Este artículo le guía por un escenario en el que se aplica un descuento por pronto pago en una nota de abono cuando la factura original también tenía un descuento por pronto pago. 

Fabrikam permite hacer descuentos por pronto pago a los clientes en los pagos parciales y también en las notas de abono (notas de crédito). Un descuento por pronto pago se puede aplicar a una nota de abono cuando la nota de abono se emite para una factura en la que se hizo un descuento por pronto pago al cliente. En lugar de proporcionar un crédito por el importe completo, puede abonar en el saldo del cliente un importe que excluya el porcentaje de descuento por pronto pago que se aplica al cliente. Los parámetros de liquidación se encuentran en la página **Parámetros de clientes**.

## <a name="invoice-and-credit-note"></a>Nota de abono y factura
El cliente 4035 tiene una factura de 1000,00 y una nota de abono de 100,00. Cada uno de estos documentos tiene un descuento del 1 por ciento si se paga en 14 días. Arnie puede ver esta información en la página **Transacciones de cliente**.

| Comprobante    | Tipo de transacción | Fecha      | Factura  | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo  | Divisa |
|------------|------------------|-----------|----------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10050  | Factura          | 28/6/2015 | 10050    | 1000,00                             |                                       | 1000,00 | USD      |
| CCRN-10050 | Nota de abono      | 28/6/2015 | CR-10050 |                                      | 100,00                                | -100,00  | USD      |

## <a name="settle-a-credit-note-with-an-invoice"></a>Liquidar una nota de abono con una factura
Desde la página **Transacciones de clientes**, Arnie abre la página **Liquidar transacciones**. Puede usar la página **Liquidar transacciones** para liquidar la nota de abono y la factura. Como parte del proceso de liquidación, ve las fechas y los importes de descuento por pronto pago. Marca los dos documentos y, a continuación, hace clic en **Registrar** para liquidar las transacciones. Existe un descuento de -1,00 en la nota de abono, porque Fabrikam permite descuentos en notas de abono.

| Marcar     | Utilizar el descuento por pronto pago | Comprobante    | Cuenta | Fecha      | Fecha de vencimiento  | Factura  | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|----------|-------------------|------------|---------|-----------|-----------|----------|--------------------------------|----------|------------------|
| Seleccionado | Normal            | FTI-10050  | 4035    | 28/6/2015 | 28/7/2015 | 10050    | 1000,00                       | USD      | 990,00           |
| Seleccionado | Normal            | CCRN-10050 | 4035    | 28/6/2015 | 28/7/2015 | CR-10050 | -100,00                        | USD      | -99,00           |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones**.

- **Fecha del descuento por pronto pago**: 7/12/2015 
- **Importe de descuento por pronto pago**: -1,00     
- **Utilizar el descuento por pronto pago**: Normal    
- **Descuento por pronto pago aplicado**: 0,00      
- **Importe de descuento por pronto pago para aplicar**: -1,00     

La liquidación será de 100,00, e incluirá un pago de 99,00 y un descuento de 1,00.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]