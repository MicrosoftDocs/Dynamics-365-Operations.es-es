---
title: Liquidar un pago de cliente parcial y el pago final completamente antes de la fecha de descuento
description: Este artículo proporciona escenarios que muestran cómo registrar pagos parciales para un cliente y aplicar descuentos por pronto pago dentro del período del descuento por pronto pago.
author: abruer
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14491
ms.assetid: 0f07d3ce-a439-43ed-a22e-957ccd36a37b
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f9ae9218a85c50582c8c4999da463833fc91d260
ms.sourcegitcommit: d61c43b6bc04bb8786aa3c47932be0ccd84ebaeb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/14/2020
ms.locfileid: "4006124"
---
# <a name="settle-a-partial-customer-payment-and-the-final-payment-in-full-before-the-discount-date"></a>Liquidar un pago de cliente parcial y el pago final completamente antes de la fecha de descuento

[!include [banner](../includes/banner.md)]

Este artículo proporciona escenarios que muestran cómo registrar pagos parciales para un cliente y aplicar descuentos por pronto pago dentro del período del descuento por pronto pago.

Fabrikam vende productos al cliente 4028. Fabrikam ofrece un descuento por pronto pago del uno por ciento si la factura se paga en 14 días. Las facturas se deben pagar en 30 días. Fabrikam también ofrece descuentos por pronto pago en pagos parciales. Los parámetros de liquidación se encuentran en la página **Parámetros de clientes**.

## <a name="customer-invoice"></a>Factura del cliente
El 25 de junio, Arnie introduce y registra una factura para 1000,00 del cliente 4028. Arnie puede ver esta transacción en la página **Transacciones de cliente**.

| Comprobante   | Tipo de transacción | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo  | Divisa |
|-----------|------------------|-----------|---------|--------------------------------------|---------------------------------------|----------|----------|
| FTI-10010 | Factura          | 25/6/2015 | 10010   | 1000,00                             |                                       | 1000,00 | USD      |

Desde la página **Cliente** o **Transacciones de cliente** , Arnie puede abrir la página **Liquidar transacciones** para ver las fechas y los importes de descuentos por pronto pago disponibles para la factura. La fecha de vencimiento es el 25 de julio, y un descuento por pronto pago de 10,00 está disponible si la factura se paga el 9 de julio.

| Marcar     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Seleccionado | Normal            | FTI-10010 | 4028    | 25/6/2015 | 25/7/2015 | 10010   | 1000,00                       | USD      | 990,00           |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones** correspondiente a la factura marcada.

|    &nbsp;                    |  &nbsp;   |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 7/09/2015 |
| Importe de descuento por pronto pago         | 10,00     |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | 0,00      |
| Importe de descuento por pronto pago para aplicar | 10,00     |

Arnie hace clic en la ficha **Descuento por pronto pago** para ver el importe de descuento.

| Fecha del descuento por pronto pago | Importe de descuento por pronto pago | Importe en divisa de la transacción |
|--------------------|----------------------|--------------------------------|
| 9/7/2015           | 10,00                | 990,00                         |
| 25/7/2015          | 0,00                 | 1000,00                       |

## <a name="partial-payment-by-using-the-enter-customer-payments-page"></a>Pago parcial mediante la página Introducir pagos de cliente
El cliente 4028 envía un pago de 500,00 el 1 de julio. Para especificar este pago, Arnie no hace clic en **Líneas**. En su lugar, registra el pago creando un nuevo diario de pagos y abriendo luego la página **Introducir pagos de cliente**. Especifica la información de pago y marca la factura que ha introducido. Cuando Arnie especifica el importe de **500,00** , introduce también **500,00** en el campo **Importe que hay que pagar** de la cuadrícula. Puesto que Fabrikam permite un descuento por pronto pago en los pagos parciales, ve que también se obtendrá un descuento por pronto pago parcial de 5,05. El cálculo de este descuento es 500,00 ÷ 0,99 × 0,01 = 5,05. (En este cálculo, 500,00 se divide por 0,99, porque hay un descuento del 1 por ciento. Por lo tanto, el cliente paga el 99 por ciento de la factura. A continuación, el resultado se multiplica por el porcentaje de descuento, que es un 1 por ciento, o 0,01. Si el cliente tiene el descuento completo de 10,00, el importe que se debe liquidar será de 990,00). La información de descuento aparece en la cuadrícula en la parte inferior de la página **Introducir pagos de cliente**.

| Importe de descuento por pronto pago para aplicar | Descuento por pronto pago aplicado | Importe que hay que pagar |
|------------------------------|---------------------|---------------|
| 5,05                         | 0,00                | 500,00        |

## <a name="partial-payment-by-using-the-journal-lines"></a>Pago parcial con las líneas de diario
En lugar de abrir la página **Introducir pagos de cliente** en el diario de pagos, Arnie puede hacer clic en **Líneas** para especificar un pago. Se muestra el diario de pagos, donde Arnie puede especificar una línea del cliente 4028. A continuación, Arnie abre la página **Liquidar transacciones** para poder marcar la factura para su liquidación. Arnie marca la factura y cambia el valor del campo **Importe para liquidar** a **-500,00**. De nuevo, ve que el valor del campo **Importe de descuento por pronto pago** es **-10,00** para la factura completa, y que el valor en el campo **Importe de descuento por pronto pago para aplicar** es **-5,05**. Por lo tanto, Arnie está liquidando 505,05 de esta factura.

| Marcar     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Seleccionado | Normal            | FTI-10010 | 4028    | 25/6/2015 | 25/7/2015 | 10010   | 1000,00                       | USD      | 500,00           |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones abiertas**.

|        &nbsp;                | &nbsp;    |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 7/09/2015 |
| Importe de descuento por pronto pago         | 10,00     |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | 0,00      |
| Importe de descuento por pronto pago para aplicar | 5,05      |

Si el cliente desea liquidar exactamente la mitad de la factura, debería emitir un pago de 495,00. En este caso, Arnie especifica **495,00** en el campo **Importe que se va a liquidar**. También se obtendrá el descuento por pronto pago de 5,00, de modo que el importe liquidado total sea 500,00.

| Marcar     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Seleccionado | Normal            | FTI-10010 | 4028    | 25/6/2015 | 25/7/2015 | 10010   | 1000,00                       | USD      | 495,00           |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones abiertas**.

|     &nbsp;                   | &nbsp;    |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 7/09/2015 |
| Importe de descuento por pronto pago         | 10,00     |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | 0,00      |
| Importe de descuento por pronto pago para aplicar | 5,00      |

Arnie cierra la página **Liquidar transacciones**. Una línea de pago de 495,00 se crea en el diario y, a continuación, Arnie registra el diario. Arnie puede revisar las transacciones del cliente en la página **Transacciones de cliente**. En esta página, Arnie observa que la factura tiene un saldo de 500,00. También observa un pago de 495,00 y un descuento de 5,00.

| Comprobante    | Tipo de transacción | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo | Divisa |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10010  | Factura          | 25/6/2015 | 10010   | 1000,00                             |                                       | 500,00  | USD      |
| ARP-10010  |  Pago         | 7/1/2015  |         |                                      | 495,00                                | 0,00    | USD      |
| DISC-10010 |  Descuento por pronto pago   | 7/1/2015  |         |                                      | 5,00                                  | 0,00    | USD      |

## <a name="payment-for-the-remaining-amount"></a>Pago del importe restante
El cliente 4028 paga el importe restante de 495,00 el 8 de julio, dentro del período de descuento por pronto pago. Arnie crea el diario de pagos el 8 de julio y marca la transacción para liquidación. Observa que el importe que se debe liquidar es de 495,00. El valor del campo **Descuento estimado por pronto pago** es **5,00** , dado que el descuento de 5,00 se aplicó previamente.

|   &nbsp;                | &nbsp; |
|-------------------------|--------|
| Total marcado            | 495,00 |
| Descuento estimado por pronto pago | 5,00   |

La información sobre la transacción marcada aparece en la cuadrícula de la página **Liquidar transacciones abiertas**.

| Marcar     | Utilizar el descuento por pronto pago | Comprobante   | Cuenta | Fecha      | Fecha de vencimiento  | Factura | Importe en divisa de la transacción | Divisa | Importe para liquidar |
|----------|-------------------|-----------|---------|-----------|-----------|---------|--------------------------------|----------|------------------|
| Seleccionado | Normal            | FTI-10010 | 4028    | 25/6/2015 | 25/7/2015 | 10010   | 1000,00                       | USD      | 495,00           |

La información de descuento aparece en la parte inferior de la página **Liquidar transacciones abiertas**.

|  &nbsp;                      |  &nbsp;   |
|------------------------------|-----------|
| Fecha del descuento por pronto pago           | 7/09/2015 |
| Importe de descuento por pronto pago         | 10,00     |
| Utilizar el descuento por pronto pago            | Normal    |
| Descuento por pronto pago aplicado          | 5,00      |
| Importe de descuento por pronto pago para aplicar | 5,00      |

Arnie registra este diario y revisa las transacciones del cliente en la página **Transacciones de clientes**. El saldo de la factura es ahora de 0,00, y Arnie puede ver ahora los dos pagos y los dos descuentos por pronto pago.

| Comprobante    | Tipo de transacción | Fecha      | Factura | Importe en débito en divisa de transacción | Importe en crédito en divisa de transacción | Saldo | Divisa |
|------------|------------------|-----------|---------|--------------------------------------|---------------------------------------|---------|----------|
| FTI-10010  | Factura          | 25/6/2015 | 10010   | 1000,00                             |                                       | 0,00    | USD      |
| ARP-10010  | Pago          | 7/1/2015  |         |                                      | 495,00                                | 0,00    | USD      |
| DISC-10010 | Descuento por pronto pago    | 7/1/2015  |         |                                      | 5,00                                  | 0,00    | USD      |
| ARP-10011  | Pago          | 7/8/2015  |         |                                      | 495,00                                | 0,00    | USD      |
| DISC-10011 | Descuento por pronto pago    | 7/8/2015  |         |                                      | 5,00                                  | 0,00    | USD      |





