---
title: Pagos centralizados para Clientes
description: Las organizaciones que constan de diversas entidades jurídicas pueden crear y administrar pagos con una entidad jurídica única que controle todos los pagos. Por lo tanto, no tiene que especificarse la misma transacción en varias entidades jurídicas. Este artículo proporciona ejemplos que muestran cómo el registro para pagos centralizados se gestiona en distintos escenarios.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 02/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 59942fadb0fb702c59c95f75359f1a3036e4668f
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179835"
---
# <a name="centralized-payments-for-accounts-receivable"></a>Pagos centralizados para Clientes

[!include [banner](../includes/banner.md)]

Las organizaciones que constan de diversas entidades jurídicas pueden crear y administrar pagos con una entidad jurídica única que controle todos los pagos. Por lo tanto, no tiene que especificarse la misma transacción en varias entidades jurídicas. Este artículo proporciona ejemplos que muestran cómo el registro para pagos centralizados se gestiona en distintos escenarios.

Las organizaciones que constan de diversas entidades jurídicas pueden crear y administrar pagos con una entidad jurídica que controle todos los pagos. Por lo tanto, no tiene que especificarse la misma transacción en varias entidades jurídicas. Además, la organización ahorra tiempo, ya que los procesos para las propuestas de pago, las liquidaciones y la edición de transacciones abiertas y cerradas para pagos centralizados se simplifican. 

En una organización de pagos centralizados, existen muchas entidades jurídicas para las operaciones y cada entidad jurídica operativa administra su propia información de facturas de clientes. Los pagos de las entidades jurídicas operativas se reciben desde una única entidad jurídica denominada entidad jurídica del pago. Durante el proceso de liquidación, se generan las transacciones vencidas en el intervalo de fechas aplicable. Puede especificar la entidad jurídica de la organización que recibe las transacciones de pérdidas o de beneficios realizados y cómo se administrarán las transacciones de descuento por pronto pago relacionadas con los pagos centralizados. En la línea de diario de pago centralizado, el **Tipo de cuenta** se debe establecer en el cliente. El **Tipo de cuenta de contrapartida** debe establecerse en banco o libro mayor. La cuenta bancaria debe estar en la empresa actual. 

En los siguientes ejemplos se muestra cómo se gestionan los registros en distintas situaciones. Se usa la siguiente configuración en todos los ejemplos:

-   Las entidades jurídicas son Fabrikam, Fabrikam Este y Fabrikam Oeste. Los pagos de cliente se especifican en Fabrikam.
-   El campo **Registrar descuento por pronto pago** en la página **Contabilidad de empresas vinculadas** está establecido en **Entidad jurídica de la factura**.
-   El campo **Registrar pérdida o ganancia por cambio de divisa** en la página **Contabilidad de empresas vinculadas** está establecido en **Entidad jurídica del pago**.
-   Customer Northwind Traders se ha configurado como cliente en cada entidad jurídica. Los clientes de las distintas entidades jurídicas se identifican como el mismo cliente, ya que comparten el mismo identificador de libreta de direcciones global.

| Id. de libreta de direcciones | Cuenta de cliente | Nombre              | Entidad jurídica  |
|-----------------|------------------|-------------------|---------------|
| 4050            | 4000             | Northwind Traders | Fabrikam      |
| 4050            | 4000             | Northwind Traders | Fabrikam Este |
| 4050            | 10000            | Northwind Traders | Fabrikam Oeste |

## <a name="example-1-customer-payment-of-invoice-from-another-legal-entity"></a>Ejemplo 1: pago de cliente de factura de otra entidad jurídica
Fabrikam recibe un pago de 600,00 de la cuenta de cliente 4000 de Fabrikam, Northwind Traders. El pago se liquida con una factura abierta de la cuenta de cliente 4000 de Fabrikam Este.

### <a name="invoice-is-posted-in-fabrikam-east-for-customer-4000"></a>Se registra la factura del cliente 4000 en Fabrikam Este

| Cuenta                             | Importe de débito | Importe de crédito |
|-------------------------------------|--------------|---------------|
| Clientes (Fabrikam Este) | 600,00       |               |
| Ventas (Fabrikam Este)               |              | 600,00        |

### <a name="payment-is-received-and-posted-in-fabrikam-for-customer-4000"></a>Se recibe y registra el pago del cliente 4000 en Fabrikam

| Cuenta                        | Importe de débito | Importe de crédito |
|--------------------------------|--------------|---------------|
| Efectivo (Fabrikam)                | 600,00       |               |
| Clientes (Fabrikam) |              | 600,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Se liquida el pago de Fabrikam con la factura de Fabrikam Este

**Registro de Fabrikam**

| Cuenta                         | Importe de débito | Importe de crédito |
|---------------------------------|--------------|---------------|
| Clientes (Fabrikam)  | 600,00       |               |
| Importe debido a Fabrikam Este (Fabrikam) |              | 600,00        |

**Registro de Fabrikam Este**

| Cuenta                             | Importe de débito | Importe de crédito |
|-------------------------------------|--------------|---------------|
| Importe debido de Fabrikam (Fabrikam Este)   | 600,00       |               |
| Clientes (Fabrikam Este) |              | 600,00        |

## <a name="example-2-customer-payment-of-invoice-from-another-legal-entity-with-cash-discount"></a>Ejemplo 2: pago de cliente de factura de otra entidad jurídica con descuento por pronto pago
Fabrikam recibe un pago de 580,00 del cliente 4000 de Fabrikam, Northwind Traders. Fabrikam Este tiene una factura abierta para el cliente 4000. La factura tiene un descuento por pronto pago de 20,00. El pago se liquida con las facturas abiertas de Fabrikam Este. El descuento por pronto pago se registra en la entidad jurídica de la factura: Fabrikam Este.

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-customer-4000"></a>Se registra la factura del cliente 4000 de Fabrikam Este en Fabrikam Este

| Cuenta                             | Importe de débito | Importe de crédito |
|-------------------------------------|--------------|---------------|
| Clientes (Fabrikam Este) | 600,00       |               |
| Ventas (Fabrikam Este)               |              | 600,00        |

### <a name="payment-is-received-and-posted-in-fabrikam-for-fabrikam-customer-4000"></a>Se recibe y registra el pago del cliente 4000 de Fabrikam en Fabrikam

| Cuenta                        | Importe de débito | Importe de crédito |
|--------------------------------|--------------|---------------|
| Efectivo (Fabrikam)                | 600,00       |               |
| Clientes (Fabrikam) |              | 600,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Se liquida el pago de Fabrikam con la factura de Fabrikam Este

**Registro de Fabrikam**

| Cuenta                         | Importe de débito | Importe de crédito |
|---------------------------------|--------------|---------------|
| Clientes (Fabrikam)  | 580,00       |               |
| Importe debido a Fabrikam Este (Fabrikam) |              | 580,00        |

**Registro de Fabrikam Este**

| Cuenta                             | Importe de débito | Importe de crédito |
|-------------------------------------|--------------|---------------|
| Importe debido de Fabrikam (Fabrikam Este)   | 580,00       |               |
| Clientes (Fabrikam Este) |              | 580,00        |
| Descuento por pronto pago (Fabrikam Este)       | 20,00        |               |
| Clientes (Fabrikam Este) |              | 20,00         |

## <a name="example-3-customer-payment-of-invoice-from-another-legal-entity-with-realized-exchange-rate-gain"></a>Ejemplo 3: pago de factura de cliente de otra entidad jurídica con ganancias realizadas por tipo de cambio
Fabrikam recibe un pago de 600,00 euros (EUR) del cliente 4000 de Fabrikam, Northwind Traders. El pago se liquida con una factura abierta del cliente 4000 de Fabrikam Este. Se genera una transacción de ganancias en el tipo de cambio de divisa durante el proceso de liquidación.

-   Tipo de cambio de euros (EUR) a dólares estadounidenses (USD) en la fecha de factura: 1,2062
-   Tipo de cambio de euros a dólares USD en la fecha de pago: 1,2277

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-customer-4000"></a>Se registra la factura del cliente 4000 de Fabrikam Este en Fabrikam Este

| Cuenta                             | Importe de débito            | Importe de crédito           |
|-------------------------------------|-------------------------|-------------------------|
| Clientes (Fabrikam Este) | 600,00 EUR / 723,72 dólares USD |                         |
| Ventas (Fabrikam Este)               |                         | 600,00 EUR / 723,72 dólares USD |

### <a name="payment-is-received-and-posted-in-fabrikam-for-fabrikam-customer-4000"></a>Se recibe y registra el pago del cliente 4000 de Fabrikam en Fabrikam

| Cuenta                        | Importe de débito            | Importe de crédito           |
|--------------------------------|-------------------------|-------------------------|
| Efectivo (Fabrikam)                | 600,00 EUR / 736,62 dólares USD |                         |
| Clientes (Fabrikam) |                         | 600,00 EUR / 736,62 dólares USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Se liquida el pago de Fabrikam con la factura de Fabrikam Este

**Registro de Fabrikam**

| Cuenta                         | Importe de débito            | Importe de crédito           |
|---------------------------------|-------------------------|-------------------------|
| Clientes (Fabrikam)  | 600,00 EUR / 736,62 dólares USD |                         |
| Importe debido a Fabrikam Este (Fabrikam) |                         | 600,00 EUR / 736,62 dólares USD |
| Importe debido a Fabrikam Este (Fabrikam) | 0,00 EUR / 12,90 dólares USD    |                         |
| Ganancia realizada (Fabrikam)        |                         | 0,00 EUR / 12,90 dólares USD    |

**Registro de Fabrikam Este**

| Cuenta                             | Importe de débito            | Importe de crédito           |
|-------------------------------------|-------------------------|-------------------------|
| Importe debido de Fabrikam (Fabrikam Este)   | 600,00 EUR / 736,62 dólares USD |                         |
| Clientes (Fabrikam Este) |                         | 600,00 EUR / 736,62 dólares USD |
| Clientes (Fabrikam Este) | 0,00 EUR / 12,90 dólares USD    |                         |
| Importe debido de Fabrikam (Fabrikam Este)   |                         | 0,00 EUR / 12,90 dólares USD    |

## <a name="example-4-customer-payment-of-invoice-from-another-legal-entity-with-cash-discount-and-realized-exchange-rate-gain"></a>Ejemplo 4: pago de cliente de factura de otra entidad jurídica con descuento por pronto pago y ganancia realizada por tipo de cambio
Fabrikam registra un pago del cliente 4000 de Fabrikam, Northwind Traders, de una factura abierta de Fabrikam Este. La factura tiene un descuento por pronto pago y se genera una transacción de impuestos. El pago se liquida con una factura abierta de Fabrikam Este. Se genera una transacción de ganancias en el tipo de cambio de divisa durante el proceso de liquidación. El descuento por pronto pago se registra en la entidad jurídica de la factura (Fabrikam Este) y la ganancia por cambio de divisa se registra en la entidad jurídica del pago (Fabrikam).

-   Tipo de cambio de euros a dólares USD en la fecha de factura: 1,2062
-   Tipo de cambio de euros a dólares USD en la fecha de pago: 1,2277

### <a name="free-text-invoice-is-posted-and-a-tax-transaction-is-generated-in-fabrikam-east-for-customer-4000"></a>Se registra una factura de servicios y se genera una transacción de impuestos en Fabrikam Este para el cliente 4000

| Cuenta                             | Importe de débito            | Importe de crédito           |
|-------------------------------------|-------------------------|-------------------------|
| Clientes (Fabrikam Este) | 638,22 EUR / 769,82 dólares USD |                         |
| Ventas (Fabrikam Este)               |                         | 600,00 EUR / 723,72 dólares USD |
| Impuestos (Fabrikam Este)           |                         | 38,22 EUR / 46,10 dólares USD   |

### <a name="payment-is-received-and-posted-in-fabrikam-for-customer-4000"></a>Se recibe y registra el pago del cliente 4000 en Fabrikam

| Cuenta                        | Importe de débito            | Importe de crédito           |
|--------------------------------|-------------------------|-------------------------|
| Efectivo (Fabrikam)                | 626,22 EUR / 768,81 dólares USD |                         |
| Clientes (Fabrikam) |                         | 626,22 EUR / 768,81 dólares USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>Se liquida el pago de Fabrikam con una factura de Fabrikam Este

**Registro de Fabrikam**

| Cuenta                         | Importe de débito            | Importe de crédito           |
|---------------------------------|-------------------------|-------------------------|
| Clientes (Fabrikam)  | 626,22 EUR / 768,81 dólares USD |                         |
| Importe debido a Fabrikam Este (Fabrikam) |                         | 626,22 EUR / 768,81 dólares USD |
| Importe debido a Fabrikam Este (Fabrikam) | 0,00 EUR / 13,46 dólares USD    |                         |
| Ganancia realizada (Fabrikam)        |                         | 0,00 EUR / 13,46 dólares USD    |

**Registro de Fabrikam Este**

| Cuenta                             | Importe de débito            | Importe de crédito           |
|-------------------------------------|-------------------------|-------------------------|
| Importe debido de Fabrikam (Fabrikam Este)   | 626,22 EUR / 768,81 dólares USD |                         |
| Clientes (Fabrikam Este) |                         | 626,22 EUR / 768,81 dólares USD |
| Clientes (Fabrikam Este)  | 0,00 EUR / 13,46 dólares USD    |                         |
| Importe debido de Fabrikam (Fabrikam Este)   |                         | 0,00 EUR / 13,46 dólares USD    |
| Descuento por pronto pago (Fabrikam Este)       | 12,00 EUR / 14,47 dólares USD   |                         |
| Clientes (Fabrikam Este) |                         | 12,00 EUR / 14,47 dólares USD   |

## <a name="example-5-customer-credit-note-with-primary-payment"></a>Ejemplo 5: Nota de abono de cliente con pago principal
Fabrikam recibe un pago de 75,00 del cliente 4000, Northwind Traders. El pago se liquida con una factura abierta del cliente 10000 de Fabrikam Oeste y una nota de abono abierta del cliente 4000 de Fabrikam Este. Se selecciona el pago como pago principal en la página **Liquidar transacciones**.

### <a name="invoice-is-posted-to-fabrikam-west-for-customer-10000"></a>Se registra la factura del cliente 10000 en Fabrikam Oeste

| Cuenta                             | Importe de débito | Importe de crédito |
|-------------------------------------|--------------|---------------|
| Clientes (Fabrikam Oeste) | 100,00       |               |
| Ventas (Fabrikam Oeste)               |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-customer-4000"></a>Se registra la nota de abono del cliente 4000 en Fabrikam Este

| Cuenta                             | Importe de débito | Importe de crédito |
|-------------------------------------|--------------|---------------|
| Devolución de ventas (Fabrikam Este)       | 25,00        |               |
| Clientes (Fabrikam Este) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-customer-4000"></a>Se registra el pago del cliente 4000 en Fabrikam

| Cuenta                        | Importe de débito | Importe de crédito |
|--------------------------------|--------------|---------------|
| Efectivo (Fabrikam)                | 75,00        |               |
| Clientes (Fabrikam) |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Se liquida el pago de Fabrikam con la factura de Fabrikam Oeste y la nota de abono de Fabrikam Este

**Registro de Fabrikam**

| Cuenta                           | Importe de débito | Importe de crédito |
|-----------------------------------|--------------|---------------|
| Importe debido de Fabrikam Este (Fabrikam) | 25,00        |               |
| Clientes (Fabrikam)    |              | 25,00         |
| Clientes (Fabrikam)    | 100,00       |               |
| Importe debido a Fabrikam Oeste (Fabrikam)   |              | 100,00        |

**Registro de Fabrikam Este**

| Cuenta                             | Importe de débito | Importe de crédito |
|-------------------------------------|--------------|---------------|
| Clientes (Fabrikam Este) | 25,00        |               |
| Importe debido a Fabrikam (Fabrikam Este)     |              | 25,00         |

**Registro de Fabrikam Oeste**

| Cuenta                             | Importe de débito | Importe de crédito |
|-------------------------------------|--------------|---------------|
| Importe debido de Fabrikam (Fabrikam Oeste)   | 100,00       |               |
| Clientes (Fabrikam Oeste) |              | 100,00        |

## <a name="example-6-customer-credit-note-without-primary-payment"></a>Ejemplo 6: Nota de abono de cliente sin pago principal
Fabrikam recibe un pago de 75,00 del cliente 4000, Northwind Traders. El pago se liquida con una factura abierta del cliente 10000 de Fabrikam Oeste y una nota de abono abierta del cliente 4000 de Fabrikam Este. No se selecciona el pago como pago principal en la página **Liquidar transacciones**.

### <a name="invoice-is-posted-to-fabrikam-west-for-customer-10000"></a>Se registra la factura del cliente 10000 en Fabrikam Oeste

| Cuenta                             | Importe de débito | Importe de crédito |
|-------------------------------------|--------------|---------------|
| Clientes (Fabrikam Oeste) | 100,00       |               |
| Ventas (Fabrikam Oeste)               |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-customer-4000"></a>Se registra la nota de abono del cliente 4000 en Fabrikam Este

| Cuenta                             | Importe de débito | Importe de crédito |
|-------------------------------------|--------------|---------------|
| Devolución de ventas (Fabrikam Este)       | 25,00        |               |
| Clientes (Fabrikam Este) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-customer-4000"></a>Se registra el pago del cliente 4000 en Fabrikam

| Cuenta                        | Importe de débito | Importe de crédito |
|--------------------------------|--------------|---------------|
| Efectivo (Fabrikam)                | 75,00        |               |
| Clientes (Fabrikam) |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>Se liquida el pago de Fabrikam con la factura de Fabrikam Oeste y la nota de abono de Fabrikam Este

**Registro de Fabrikam**

| Cuenta                         | Importe de débito | Importe de crédito |
|---------------------------------|--------------|---------------|
| Clientes (Fabrikam)  | 75,00        |               |
| Importe debido a Fabrikam Oeste (Fabrikam) |              | 75,00         |

**Registro de Fabrikam Este**

| Cuenta                              | Importe de débito | Importe de crédito |
|--------------------------------------|--------------|---------------|
| Clientes (Fabrikam Este)  | 25,00        |               |
| Importe debido a Fabrikam Oeste (Fabrikam Este) |              | 25,00         |

**Registro de Fabrikam Oeste**

| Cuenta                                | Importe de débito | Importe de crédito |
|----------------------------------------|--------------|---------------|
| Importe debido de Fabrikam (Fabrikam Oeste)      | 75,00        |               |
| Clientes (Fabrikam Oeste)    |              | 75,00         |
| Importe debido de Fabrikam Este (Fabrikam Oeste) | 25,00        |               |
| Clientes (Fabrikam Oeste)    |              | 25,00         |
