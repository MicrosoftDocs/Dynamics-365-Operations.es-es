---
title: Descuentos por pronto pago para sobrepagos
description: Este artículo proporcionan escenarios que muestran cómo se gestiona un pago cuando el cliente recibe un descuento por pronto pago pero también paga en exceso.
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustOpenTrans, CustParameters, LedgerJournalTransCustPaym, LedgerJournalTransVendPaym, VendOpenTrans, VendParameters
audience: Application User
ms.reviewer: kfend
ms.custom: 14171
ms.assetid: a94d0fd0-57ba-4054-93c8-519d01d50e19
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9b6e8711870cf961ed1fb75d5a43ac604873c1f1
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/05/2022
ms.locfileid: "8711391"
---
# <a name="cash-discounts-for-overpayments"></a>Descuentos por pronto pago para sobrepagos

[!include [banner](../includes/banner.md)]

Este artículo proporcionan escenarios que muestran cómo se gestiona un pago cuando el cliente recibe un descuento por pronto pago pero también paga en exceso. 

Una factura se considerará sobrepagada cuando el importe del pago sea superior al importe de la factura menos el descuento por pronto pago. Para especificar cómo se gestiona una diferencia obtenible de descuento por pronto pago cuando se sobrepaga una factura, use los campos **Administración del descuento por pronto pago** y **Sobrepago o pago insuficiente máximo** de la página **Parámetros de clientes**. En el siguiente ejemplo, el cliente ha pagado en exceso la factura por 0,50.

| Total de la factura | Descuento por pronto pago disponible | Importe a pagar, incluido el descuento por pronto pago | Importe que el cliente paga realmente |
|---------------|-------------------------|-----------------------------------------------------|-----------------------------------|
| 105,00        | 10,50                   | 94,50                                               | 95,00                             |

## <a name="cash-discount-administration--specific"></a>Administración del descuento por pronto pago = Específico
Si se selecciona **Específico** en el campo **Administración del descuento por pronto pago** de la página **Cuentas para transacciones automáticas**, se obtiene el descuento por pronto pago completo. El importe del sobrepago se registra en una cuenta contable de diferencia de descuento por pronto pago o permanece como saldo en la cuenta del cliente. El funcionamiento dependerá de si el importe del sobrepago se encuentra entre 0,00 y el importe especificado en el campo **Sobrepago o pago insuficiente máximo**, o si el importe del sobrepago es superior al importe de **Sobrepago o pago insuficiente máximo**.

### <a name="scenario-1"></a>Escenario 1

En este caso, el importe del sobrepago está entre 0,00 y el sobrepago o pago insuficiente máximo. Se especifica una factura por un valor de 105,00 con un descuento por pronto pago si la factura se paga en menos de siete días.

| Total de la factura | Descuento por pronto pago disponible | Importe a pagar, incluido el descuento por pronto pago |
|---------------|-------------------------|-----------------------------------------------------|
| 105,00        | 10,50                   | 94,50                                               |

El cliente envía un pago de 95,00 dentro del período de descuento por pronto pago. El pago se liquida con la factura por 105,00. Una vez liquidados la factura y el pago, se crean las siguientes transacciones en Clientes para el cliente.

| Transacción   | Importe | Saldo |
|---------------|--------|---------|
| Factura       | 105,00 | 0,00    |
| Pago       | -95,00 | 0,00    |
| Descuento por pronto pago | -10,50 | 0,00    |

Se generan los asientos contables siguientes para el pago y la liquidación. **Pago**

| Cuenta             | Importe de débito | Importe de crédito |
|---------------------|--------------|---------------|
| Efectivo                | 95,00        |               |
| Clientes |              | 95,00         |

**Liquidación**

| Cuenta                                                                                                          | Importe de débito | Importe de crédito |
|------------------------------------------------------------------------------------------------------------------|--------------|---------------|
| Descuento por pronto pago (el campo **Cuenta principal para descuentos de cliente** en la página **Descuentos por pronto pago**)                 | 10,50        |               |
| Clientes                                                                                              |              | 10,50         |
| Descuento por pronto pago del cliente (el campo **Descuento por pronto pago del cliente** de la página **Cuentas para transacciones automáticas**) |              | 0,50          |
| Clientes                                                                                              | 0,50         |               |

### <a name="scenario-2"></a>Escenario 2

En este caso, el importe del sobrepago supera el sobrepago o pago insuficiente máximo. Se especifica una factura por un valor de 105,00 con un descuento por pronto pago si la factura se paga en menos de siete días.

| Total de la factura | Descuento por pronto pago disponible | Importe a pagar, incluido el descuento por pronto pago |
|---------------|-------------------------|-----------------------------------------------------|
| 105,00        | 10,50                   | 94,50                                               |

El cliente envía un pago de 95,00 dentro del período de descuento por pronto pago. El pago se liquida con la factura por 105,00. Una vez liquidados la factura y el pago, se crean las siguientes transacciones en Clientes para el cliente.

| Transacción   | Importe | Saldo |
|---------------|--------|---------|
| Factura       | 105,00 | 0,00    |
| Pago       | -95,00 | -0,50   |
| Descuento por pronto pago | -10,50 | 0,00    |

El importe del sobrepago de 0,50 se mantendrá como saldo de apertura en el pago y se puede liquidar con otra factura. Se generan los asientos contables siguientes para el pago y la liquidación. **Pago**

| Cuenta             | Importe de débito | Importe de crédito |
|---------------------|--------------|---------------|
| Efectivo                | 95,00        |               |
| Clientes |              | 95,00         |

**Liquidación**

| Cuenta                                                                                          | Importe de débito | Importe de crédito |
|--------------------------------------------------------------------------------------------------|--------------|---------------|
| Descuento por pronto pago (el campo **Cuenta principal para descuentos de cliente** en la página **Descuentos por pronto pago**) | 10,50        |               |
| Clientes                                                                              |              | 10,50         |

## <a name="cash-discount-administration--unspecific"></a>Administración del descuento por pronto pago = No específico
Si se selecciona **No específico** en el campo **Administración del descuento por pronto pago** de la página **Cuentas para transacciones automáticas**, el importe de descuento por pronto pago se deduce del importe del sobrepago. Este funcionamiento se aplica siempre, independientemente de si el importe del sobrepago está por encima o por debajo del importe que se especifica en el campo **Sobrepago o pago insuficiente máximo**.

### <a name="scenario-3"></a>Escenario 3

En este caso, se especifica una factura por un valor de 105,00 con un descuento por pronto pago si la factura se paga en menos de siete días.

| Total de la factura | Descuento por pronto pago disponible | Importe a pagar, incluido el descuento por pronto pago |
|---------------|-------------------------|-----------------------------------------------------|
| 105,00        | 10,50                   | 94,50                                               |

El cliente envía un pago de 95,00 dentro de la fecha de descuento por pronto pago. El pago se liquida con la factura por 105,00. Una vez liquidados la factura y el pago, se crean las siguientes transacciones en Clientes para el cliente.

| Transacción   | Importe | Saldo |
|---------------|--------|---------|
| Factura       | 105,00 | 0,00    |
| Pago       | -95,00 | -0,00   |
| Descuento por pronto pago | -10,00 | 0,00    |

El importe del descuento por pronto pago se reduce de 10,50 a 10,00. El pago y la factura se consideran liquidados. **Pago**

| Cuenta             | Importe de débito | Importe de crédito |
|---------------------|--------------|---------------|
| Efectivo                | 95,00        |               |
| Clientes |              | 95,00         |

**Liquidación**

| Cuenta                                                                                          | Importe de débito | Importe de crédito |
|--------------------------------------------------------------------------------------------------|--------------|---------------|
| Descuento por pronto pago (el campo **Cuenta principal para descuentos de cliente** en la página **Descuentos por pronto pago**) | 10,50        |               |
| Clientes                                                                              |              | 10,50         |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
