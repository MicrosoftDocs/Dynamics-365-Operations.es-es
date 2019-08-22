---
title: Liquidar un pago de proveedor parcial y el pago final completamente antes de la fecha de descuento
description: Este artículo le guía por un escenario en el que se realizan pagos parciales para una factura de proveedor y se aplica un descuento por pronto pago.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14431
ms.assetid: 6b8e3420-b4c9-4e02-9588-598fe6d3df0d
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0d5961b2459a1c43cee24b611cf73879c6e776a4
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835511"
---
# <a name="settle-a-partial-vendor-payment-and-the-final-payment-in-full-before-the-discount-date"></a>Liquidar un pago de proveedor parcial y el pago final completamente antes de la fecha de descuento

[!include [banner](../includes/banner.md)]

Este artículo le guía por un escenario en el que se realizan pagos parciales para una factura de proveedor y se aplica un descuento por pronto pago.

Fabrikam compra bienes del proveedor 3064. El proveedor ofrece a Fabrikam un descuento por pronto pago del 1 por ciento si la factura se paga en 14 días. Las facturas se deben pagar en 30 días. El proveedor también permite que Fabrikam aproveche descuentos por pronto pago sobre pagos parciales. Los parámetros de liquidación se encuentran en la página **Parámetros de proveedores**. El 25 de junio, April introduce una factura de 1.000,00 del proveedor 3.064.

## <a name="vendor-invoice-on-june-25"></a>Factura de proveedor el 25 de junio
El 25 de junio, Arnie introduce y registra una factura para 1.000,00 del proveedor 3064. April puede ver esta transacción en la página **Transacciones de proveedor**.

| Comprobante   | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo   | Divisa |
|-----------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10010 | 25/6/2015 | 10010   |                                      | 1.000,00                              | -1.000,00 | USD      |

Desde la página **Proveedores**, April abre la página **Liquidar transacciones**. April puede usar la página **Liquidar transacciones** para ver las fechas y los importes de los descuentos por pronto pago. La fecha de vencimiento es el 25 de julio, y un descuento por pronto pago de -10,00 está disponible si la factura se paga el 9 de julio.

| Marcar | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normal            | Inv-10010 | 3064    | 25/6/2015 | 25/7/2015 | 10010   | 1.000,00                       | USD      | 990,00           |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones abiertas**.

|                              |           |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 7/09/2015 |
| Importe de descuento por pronto pago         | -10,00    |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | 0,00      |
| Importe de descuento por pronto pago para aplicar | -10,00    |

April hace clic en la ficha **Descuento por pronto pago** para ver el importe de descuento.

| Fecha del descuento por pronto pago | Importe de descuento por pronto pago | Importe en divisa de la transacción |
|--------------------|----------------------|--------------------------------|
| 9/7/2015           | 10,00                | 990,00                         |
| 25/7/2015          | 0,00                 | 1.000,00                       |

## <a name="partial-payment-on-july-1-by-using-the-settle-transactions-page"></a>Pago parcial el 1 de julio mediante la página Liquidar transacciones
April puede crear un diario de pagos para este pago abriendo la página **Diario de pagos** en Proveedores. Crea un pago nuevo y especifica una línea para el proveedor 3064. A continuación, abre la página **Liquidar transacciones** para marcar la factura para su liquidación. April marca la factura y cambia el valor del campo **Importe para liquidar** a **-500,00**. Ve que el valor del campo **Importe de descuento por pronto pago** es **-10,00** para la factura completa, y que es el valor en el campo **Importe de descuento por pronto pago para aplicar** es **-5,05**. Por lo tanto, April está liquidando -505,05 de esta factura.

| Marcar     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Seleccionado | Normal            | FTI-10010 | 4028    | 25/6/2015 | 25/7/2015 | 10010   | 1.000,00                       | USD      | -500,00          |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones abiertas**.

|                              |           |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 7/09/2015 |
| Importe de descuento por pronto pago         | -10,00    |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | 0,00      |
| Importe de descuento por pronto pago para aplicar | -5,05     |

April desea liquidar exactamente la mitad de la factura. Así pues, marca la el valor del campo **Importe para liquidar** en **-495,00**. El importe total liquidado ahora es 500,00. Este importe incluye el descuento por pronto pago de -5,00.

| Marcar     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Seleccionado | Normal            | FTI-10010 | 4028    | 25/6/2015 | 25/7/2015 | 10010   | 1.000,00                       | USD      | -495,00          |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones abiertas**.

|                              |           |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 7/09/2015 |
| Importe de descuento por pronto pago         | -10,00    |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | 0,00      |
| Importe de descuento por pronto pago para aplicar | -5,00     |

April cierra la página **Liquidar transacciones**. Una línea de pago de 495,00 se crea en el diario y, a continuación, April registra el diario. April puede revisar las transacciones de proveedor en la página **Transacciones de proveedor**. Ve que la factura tiene un saldo de -500,00. También observa un pago de 495,00 y un descuento por pronto pago de 5,00.

| Comprobante    | Tipo de transacción | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo | Divisa |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10010  | Factura          | 25/6/2015 | 10010   |                                      | 1.000,00                              | -500,00 | USD      |
| APP-10010  | Pago          | 7/1/2015  |         | 495,00                               |                                       | 0,00    | USD      |
| DISC-10010 | Descuento por pronto pago    | 7/1/2015  |         | 5,00                                 |                                       | 0,00    | USD      |

## <a name="remaining-amount-paid-on-july-8"></a>Importe restante pagado el 8 de julio
April paga el resto de la factura del proveedor 3.064 el 8 de julio, fecha que se encuentra en el período de descuento por pronto pago. April crea el diario de pagos el 8 de julio y marca la transacción para liquidación. Observa que el importe que se debe liquidar es de 495,00. El valor del campo **Descuento estimado por pronto pago** es **-5,00**, dado que el descuento de 5,00 se aplicó previamente.

|                         |        |
|-------------------------|--------|
| Total marcado            | 495,00 |
| Descuento estimado por pronto pago | -5,00  |

La información sobre la transacción marcada aparece en la cuadrícula de la página **Liquidar transacciones abiertas**.

| Marcar     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Seleccionado | Normal            | FTI-10010 | 4028    | 25/6/2015 | 25/7/2015 | 10010   | 1.000,00                       | USD      | 495,00           |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones abiertas**.

|                              |           |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 7/09/2015 |
| Importe de descuento por pronto pago         | 10,00     |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | 5,00      |
| Importe de descuento por pronto pago para aplicar | 5,00      |

April registra el diario de pagos y revisa las transacciones de proveedor en la página **Transacciones de proveedor**. El saldo de la factura es ahora de 0,00, y April puede ver ahora los dos pagos y los dos descuentos por pronto pago.

| Comprobante    | Tipo de transacción | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo | Divisa |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10010  | Factura          | 25/6/2015 | 10010   |                                      | 1.000,00                              | 0,00    | USD      |
| APP-10010  |  Pago         | 7/1/2015  |         | 495,00                               |                                       | 0,00    | USD      |
| DISC-10010 | Descuento por pronto pago    | 7/1/2015  |         | 5,00                                 |                                       | 0,00    | USD      |
| APP-10011  | Pago          | 7/8/2015  |         | 495,00                               |                                       | 0,00    | USD      |
| DISC-10011 | Descuento por pronto pago    | 7/8/2015  |         | 5,00                                 |                                       | 0,00    | USD      |





