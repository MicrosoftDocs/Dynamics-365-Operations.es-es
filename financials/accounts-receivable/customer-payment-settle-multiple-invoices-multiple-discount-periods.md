---
title: "Usar un pago de cliente para liquidar varias facturas que abarcan varios períodos de descuento"
description: "En este artículo se muestra cómo se pagan varias facturas cuando cada factura permite un descuento por pronto pago. Los escenarios de su artículo destacan cómo varían los descuentos por pronto pago que se aplican, en función de cuándo se realiza el pago."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14511
ms.assetid: 3e42ccb5-b9d7-4a70-8db9-4206d10fd433
ms.search.region: Global
ms.author: Shiva.Pandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 108d377995a71400e470158993526a6b447a4066
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017

---

# <a name="use-a-customer-payment-to-settle-multiple-invoices-that-span-multiple-discount-periods"></a>Usar un pago de cliente para liquidar varias facturas que abarcan varios períodos de descuento

[!include[banner](../includes/banner.md)]


En este artículo se muestra cómo se pagan varias facturas cuando cada factura permite un descuento por pronto pago. Los escenarios de su artículo destacan cómo varían los descuentos por pronto pago que se aplican, en función de cuándo se realiza el pago.

Fabrikam vende productos al cliente 4032. Fabrikam ofrece un descuento por pronto pago del uno por ciento si la factura se paga en 14 días. Fabrikam también ofrece descuentos por pronto pago en pagos parciales. Los parámetros de liquidación se encuentran en la página **Parámetros de clientes**.

## <a name="invoices"></a>Facturas
El cliente 4032 tiene tres facturas por un total de 3.000,00:

-   La factura FTI-10040, de 1.000,00, se introdujo el 15 de mayo. Esta factura puede optar a un descuento por pronto pago del uno por ciento si se paga en 14 días.
-   La factura FTI-10041, de 1.000,00, se introdujo el 25 de junio. Esta factura puede optar a un descuento por pronto pago del uno por ciento si se paga en 14 días.
-   La factura FTI-10042, de 1.000,00, se introdujo el 25 de junio. Esta factura puede optar a un descuento por pronto pago del dos por ciento si se paga en cinco días y del uno por ciento si se paga en 14 días.

## <a name="settle-all-invoices-on-june-29"></a>Liquidación de todas las facturas el 29 de junio
Si Arnie crea un diario de pagos para liquidar completamente estas facturas el 29 de junio, el pago es de 2.970,00. El total de todos los importes de descuento es de 30,00. Arnie crea un pago para el cliente 4032 y después abre la página **Liquidar transacciones**. En la página **Liquidar transacciones**, Arnie marca las tres líneas de factura para su liquidación:

-   El pago para la factura FTI-10040 es de 1.000,00. No se ha aplicado ningún descuento por pronto pago.
-   El pago para la factura FTI-10041 es de 990,00. Se obtiene un descuento por pronto pago del uno por ciento, o 10,00.
-   El pago para la factura FTI-10042 es de 980,00. Se obtiene un descuento por pronto pago del dos por ciento, o 20,00.

| Marcar                     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Divisa | Importe para liquidar |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Seleccionado                 | Normal            | FTI-10040 | 4032    | 15/5/2015 | 15/6/2015 | 10040   | 1.000,00                             |                                       | USD      | 1.000,00         |
| Seleccionado                 | Normal            | FTI-10041 | 4032    | 25/6/2015 | 25/7/2015 | 10041   | 1.000,00                             |                                       | USD      | 990,00           |
| Seleccionado y resaltado | Normal            | FTI-10042 | 4032    | 25/6/2015 | 25/7/2015 | 10042   | 1.000,00                             |                                       | USD      | 980,00           |

Después de registrar el pago, el saldo del cliente es 0,00.

## <a name="settle-all-invoices-on-july-1"></a>Liquidación de todas las facturas el 1 de julio
Si Arnie crea un diario de pagos para liquidar completamente estas facturas el 1 de julio, el pago es de 2.980,00. Arnie crea un pago para el cliente 4032 y después abre la página **Liquidar transacciones**. En la página **Liquidar transacciones**, Arnie marca las tres líneas de factura para su liquidación:

-   El pago para la factura FTI-10040 es de 1.000,00. No se ha aplicado ningún descuento por pronto pago.
-   El pago para la factura FTI-10041 es de 990,00. Se obtiene un descuento por pronto pago del uno por ciento, o 10,00.
-   El pago para la factura FTI-10042 es de 990,00. Se obtiene un descuento por pronto pago del uno por ciento, o 10,00. Aunque el 1 de julio es posterior al período apto para el descuento del dos por ciento, entra en el período apto para el uno por ciento de descuento.

| Marcar                     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Divisa | Importe para liquidar |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Seleccionado                 | Normal            | FTI-10040 | 4032    | 15/5/2015 | 15/6/2015 | 10040   | 1.000,00                             |                                       | USD      | 1.000,00         |
| Seleccionado                 | Normal            | FTI-10041 | 4032    | 25/6/2015 | 25/7/2015 | 10041   | 1.000,00                             |                                       | USD      | 990,00           |
| Seleccionado y resaltado | Normal            | FTI-10042 | 4032    | 25/6/2015 | 25/7/2015 | 10042   | 1.000,00                             |                                       | USD      | 990,00           |

## <a name="partial-settlement-on-june-29"></a>Liquidación parcial el 29 de junio
El cliente 4.032 puede pagar un importe parcial, como la mitad de cada factura. Arnie crea un pago para el cliente 4032 y después abre la página **Liquidar transacciones**. En la página **Liquidar transacciones**, Arnie marca las tres líneas de factura para su liquidación. En cada línea, especifica el importe que liquidar en función de las instrucciones que el cliente ha proporcionado. Cuando Arnie selecciona una línea, ve el importe del descuento de dicha línea y el importe de descuento por pronto pago aplicado. Dado que el cliente paga la mitad de la factura, Arnie ve que el valor del campo **Importe de descuento por pronto pago** de la factura FTI-10042 es **20,00**, pero el valor del campo **Descuento por pronto pago aplicado** es **10,00**. El importe del pago es de 1.485,00.

| Marcar                     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Divisa | Importe para liquidar |
|--------------------------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------------|---------------------------------------|----------|------------------|
| Seleccionado                 | Normal            | FTI-10040 | 4032    | 15/5/2015 | 15/6/2015 | 10040   | 1.000,00                             |                                       | USD      | 500,00           |
| Seleccionado                 | Normal            | FTI-10041 | 4032    | 25/6/2015 | 25/7/2015 | 10041   | 1.000,00                             |                                       | USD      | 495,00           |
| Seleccionado y resaltado | Normal            | FTI-10042 | 4032    | 25/6/2015 | 25/7/2015 | 10042   | 1.000,00                             |                                       | USD      | 490,00           |

Arnie también puede especificar manualmente el importe de pago de 1.485,00 antes de abrir la página **Liquidar transacciones**. Si Arnie especifica manualmente el importe del pago y después marca las tres transacciones, pero no ajusta el valor del campo **Importe para liquidar** para cada transacción, recibe el siguiente mensaje al cerrar la página:

> El importe total de las transacciones marcadas es distinto al del diario. ¿Desea cambiar el importe del diario?

Si Arnie desea que el importe del pago sea de solo 1.485,00, debe hacer clic en **No** y, continuación, registrar el diario. Las transacciones se liquidan como sigue:

1.  La factura FTI-10040 se ha liquidado totalmente por un valor de 1.000,00, ya que se introdujo el 15 de mayo y es la factura más antigua. No se ha aplicado ningún descuento por pronto pago. El importe restante de la transacción de pago es de 485,00.
2.  No se ha liquidado ningún importe de la factura FTI-10041. Las facturas FTI-10041 y FTI-10042 se introdujeron la misma fecha. Sin embargo, un descuento del uno por ciento está disponible para la factura FTI-10041 y un descuento del dos por ciento está disponible para la factura FTI-10042. Dado que un mejor descuento está disponible para la factura FTI-10042, los 485,00 restantes se liquidan con la factura FTI-10042.
3.  La factura FTI-10042 se liquida con los restantes 485,00. Fabrikam ofrece descuentos parciales. En este caso, el descuento es 9,90 (= 485,00 ÷ 0,98 × 0,02). El importe (485,00) se divide por 0,98, porque hay un descuento del dos por ciento (de modo que el cliente paga el 98 por ciento de la factura). A continuación, el resultado se multiplica por el porcentaje de descuento o 2 por ciento. El pago de 485,00 más el descuento de 9,90 suman 494,90. El importe de la factura original es de 1.000,00. Por lo tanto, la transacción tiene un saldo de 505,10 (= 1.000,00 – 494,90).

Arnie ve la información en la página **Transacciones de clientes**.

| Comprobante    | Tipo de transacción | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo  | Divisa |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10040  | Factura          | 15/5/2015 | 10040   | 1.000,00                             |                                       | 0,00     | USD      |
| FTI-10041  | Factura          | 25/6/2015 | 10041   | 1.000,00                             |                                       | 1.000,00 | USD      |
| FTI-10042  | Factura          | 25/6/2015 | 10042   | 1.000,00                             |                                       | 505,10   | USD      |
| ARP-10040  | Pago          | 29/6/2015 |         |                                      | 1.485,00                              | 0,00     | USD      |
| DISC-10040 | Descuento por pronto pago    | 29/6/2015 |         |                                      | 9,90                                  | 0,00     | USD      |






