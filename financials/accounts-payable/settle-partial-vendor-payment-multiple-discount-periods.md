---
title: "Liquidar un pago de proveedor parcial con varios períodos de descuento"
description: "Este artículo le guía por un escenario en el que se realizan varios pagos parciales a un proveedor que ofrece varios descuentos por pronto pago."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14262
ms.assetid: af95c48a-afd1-476c-978d-e34995100be4
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 4fd4fdf6150d4160d07d8a9b8027a40d1c22cf7d
ms.lasthandoff: 03/31/2017


---

# <a name="settle-a-partial-vendor-payment-that-has-multiple-discount-periods"></a>Liquidar un pago de proveedor parcial con varios períodos de descuento

[!include[banner](../includes/banner.md)]


Este artículo le guía por un escenario en el que se realizan varios pagos parciales a un proveedor que ofrece varios descuentos por pronto pago. 

El proveedor 3054 ofrece a Fabrikam un descuento por pronto pago del dos por ciento si una factura se paga en cinco días y un descuento por pronto pago del uno por ciento si una factura se paga en 14 días.

## <a name="invoice"></a>Factura
El 28 de junio, April crea una factura de 1.000,00 del proveedor 3054. April puede ver esta transacción en la página **Transacciones de proveedor**.

| Comprobante   | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo   | Divisa |
|-----------|-----------|---------|--------------------------------------|---------------------------------------|-----------|----------|
| Inv-10060 | 28/6/2015 | 10060   |                                      | 1.000,00                              | -1.000,00 | USD      |

Los importes y las fechas de descuento por pronto pago siguientes están disponibles para esta factura.

| Fecha del descuento por pronto pago | Importe de descuento por pronto pago | Importe en divisa de la transacción |
|--------------------|----------------------|--------------------------------|
| 3/7/2015           | 20,00                | 980,00                         |
| 12/7/2015          | 10,00                | 990,00                         |
| 25/7/2015          | 0,00                 | 1.000,00                       |

## <a name="payment-on-july-2"></a>Pago el 2 de julio
El 2 de julio, April quiere pagar 300,00 para esta factura. Crea un pago único mediante la página **Diario de pagos** en Proveedores. Agrega una línea para el proveedor 3054 y especifica un importe de pago de **300,00**. Abril abre después la página **Liquidar transacciones** para marcar la factura que se liquidará. Actualiza el valor del campo **Importe para liquidar** a **300,00** y observa que el valor en el campo **Importe de descuento por pronto pago para aplicar** ha cambiado a **6,12**. Dado que este pago se realiza en el primer período de descuento, se aplica un descuento del 2 por ciento.

| Marcar | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normal            | Inv-10060 | 3054    | 28/6/2015 | 28/7/2015 | 10060   | 1.000,00                       | USD      | 300,00           |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones abiertas**.

|                              |           |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 7/02/2015 |
| Importe de descuento por pronto pago         | -20,00    |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | 0,00      |
| Importe de descuento por pronto pago para aplicar | -6,12     |

Dado que hay disponible un descuento por pronto, April quiere cambiar el importe del pago de modo que el importe liquidado total sea 300,00 para el pago y el descuento por pronto pago. Cambia el valor del campo **Importe para liquidar** a **294,00** y observa que el valor en el campo **Importe de descuento por pronto pago para aplicar** ha cambiado a **6,00**.

| Marcar | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normal            | Inv-10060 | 3054    | 28/6/2015 | 28/7/2015 | 10060   | 1.000,00                       | USD      | 294,00           |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones abiertas**.

|                              |           |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 7/02/2015 |
| Importe de descuento por pronto pago         | -20,00    |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | 0,00      |
| Importe de descuento por pronto pago para aplicar | -6,00     |

April registra el pago. April puede ver las transacciones en la página **Transacciones de proveedor**. April observa que 300,00 se ha aplicado a la factura. Este importe incluye un descuento del 6,00. Por lo tanto, el saldo restante es de 700,00.

| Comprobante    | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo | Divisa |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 28/6/2015 | 10060   |                                      | 1.000,00                              | -700,00 | USD      |
| APP-10060  | 2/7/2015  |         | 294,00                               |                                       | 0,00    | USD      |
| DISC-10060 | 2/7/2015  |         | 6,00                                 |                                       | 0,00    | USD      |

## <a name="payment-on-july-8"></a>Pago el 8 de julio
El 8 de julio, April hace un pago adicional para la factura. Para especificar el importe, abre la página **Liquidar transacciones** y luego hace clic en la ficha **Descuento por pronto pago**. Observa los importes y las fechas de los dos descuentos por pronto pago que están disponibles. Dado que este pago se realiza en el segundo período de descuento, hay disponible un descuento del 1 por ciento, o 5,00. Este importe se calcula como la mitad del 1 por ciento de descuento sobre 1.000,00, o la mitad de 10,00.

| Fecha del descuento por pronto pago | Importe de descuento por pronto pago | Importe en divisa de la transacción |
|--------------------|----------------------|--------------------------------|
| 3/7/2015           | 20,00                | 680,00                         |
| 12/7/2015          | 10,00                | 690,00                         |
| 25/7/2015          | 0,00                 | 700,00                         |

April decide a pagar 495,00 y aprovechar el descuento por pronto pago de 5,00. Así, el importe total liquidado ahora es 500,00.

| Marcar | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
|      | Normal            | Inv-10060 | 3054    | 28/6/2015 | 28/7/2015 | 10060   | 1.000,00                       | USD      | 495,00           |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones abiertas**.

|                              |           |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 12/7/2015 |
| Importe de descuento por pronto pago         | -10,00    |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | -6,00     |
| Importe de descuento por pronto pago para aplicar | -5,00     |

En la página **Transacciones de proveedor**, April ve que el nuevo saldo es 200,00.

| Comprobante    | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo | Divisa |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 28/6/2015 | 10060   |                                      | 1.000,00                              | -200,00 | USD      |
| APP-10060  | 2/7/2015  |         | 294,00                               |                                       | 0,00    | USD      |
| DISC-10060 | 2/7/2015  |         | 6,00                                 |                                       | 0,00    | USD      |
| APP-10061  | 12/7/2015 |         | 495,00                               |                                       | 0,00    | USD      |
| DISC-10061 | 12/7/2015 |         | 5,00                                 |                                       | 0,00    | USD      |

## <a name="payment-on-july-20"></a>Pago el 20 de julio
El 20 de julio, April crea un pago final de 200,00. No se aplica ningún descuento porque el pago es posterior a ambos períodos de descuento. El saldo de la factura es de 0,00.

| Comprobante    | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo | Divisa |
|------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| Inv-10060  | 28/6/2015 | 10060   |                                      | 1.000,00                              | -200,00 | USD      |
| APP-10060  | 2/7/2015  |         | 294,00                               |                                       | 0,00    | USD      |
| DISC-10060 | 2/7/2015  |         | 6,00                                 |                                       | 0,00    | USD      |
| APP-10061  | 12/7/2015 |         | 495,00                               |                                       | 0,00    | USD      |
| DISC-10061 | 12/7/2015 |         | 5,00                                 |                                       | 0,00    | USD      |
| APP-10062  | 7/20/2015 |         | 200,00                               |                                       | 0,00    | USD      |






