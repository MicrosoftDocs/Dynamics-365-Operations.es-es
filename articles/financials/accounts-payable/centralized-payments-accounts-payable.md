---
title: Pagos centralizados para Proveedores
description: "Las organizaciones que constan de diversas entidades jurídicas pueden crear y administrar pagos con una entidad jurídica única que controle todos los pagos. Por lo tanto, los mismos pagos no tienen que se especificarse en varias entidades jurídicas. Este artículo proporciona ejemplos que muestran cómo el registro para pagos centralizados se gestiona en distintos escenarios."
author: ShivamPandey-msft
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerJournalTransVendPaym, VendOpenTrans
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14341
ms.assetid: 7bd02e32-2416-4ac6-8a60-85525267fdb7
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 54329582abd36a8ca896ce731ce06ca4de58bbb0
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="centralized-payments-for-accounts-payable"></a>Pagos centralizados para Proveedores

[!INCLUDE [banner](../includes/banner.md)]

Las organizaciones que constan de diversas entidades jurídicas pueden crear y administrar pagos con una entidad jurídica única que controle todos los pagos. Por lo tanto, los mismos pagos no tienen que se especificarse en varias entidades jurídicas. Este artículo proporciona ejemplos que muestran cómo el registro para pagos centralizados se gestiona en distintos escenarios.

Las organizaciones que constan de diversas entidades jurídicas pueden crear y administrar pagos con una entidad jurídica que controle todos los pagos. Por lo tanto, los mismos pagos no tienen que se especificarse en varias entidades jurídicas. Además, la organización ahorra tiempo, ya que se simplifica el proceso de pago.

En una organización de pagos centralizados, existen muchas entidades jurídicas para realizar las operaciones, y cada entidad jurídica operativa administra sus propias facturas de proveedores. Los pagos de las entidades jurídicas operativas se generan desde una única entidad jurídica conocida como la entidad jurídica del pago. Durante el proceso de liquidación, se generan las transacciones vencidas en el intervalo de fechas aplicable. Puede especificar la entidad jurídica de la organización que recibirá las transacciones de pérdidas o de beneficios realizados, y cómo se administrarán las transacciones de descuento por pronto pago relacionadas con los pagos entre empresas. 

En los siguientes ejemplos se muestra cómo se gestionan los registros en distintas situaciones. Se usa la siguiente configuración en todos los ejemplos:

-   Las entidades jurídicas son Fabrikam, Fabrikam Este y Fabrikam Oeste. Los pagos se realizan desde Fabrikam.
-   El campo **Registrar descuento por pronto pago** en la página **Contabilidad de empresas vinculadas** está establecido en **Entidad jurídica de la factura**.
-   El campo **Registrar pérdida o ganancia por cambio de divisa** en la página **Contabilidad de empresas vinculadas** está establecido en **Entidad jurídica del pago**.
-   El proveedor Fourth Coffee se ha configurado como proveedor en cada entidad jurídica. Los proveedores de las distintas entidades jurídicas se identifican como el mismo proveedor, ya que comparten el mismo identificador de libreta de direcciones global.

| Id. de directorio | Cuenta de proveedor | Nombre          | Entidad jurídica  |
|--------------|----------------|---------------|---------------|
| 1050         | 3004           | Fourth Coffee | Fabrikam      |
| 1050         | 100            | Fourth Coffee | Fabrikam Este |
| 1050         | 3004           | Fourth Coffee | Fabrikam Oeste |

## <a name="example-1-vendor-payment-of-invoice-from-another-legal-entity"></a>Ejemplo 1: pago de proveedor de una factura de otra entidad jurídica
Fabrikam Este tiene una factura abierta para la cuenta de proveedor 100, Fourth Coffee. Fabrikam entra y registra un pago a la cuenta de proveedor de Fabrikam 3004, Fourth Coffee. El pago se liquida con la factura abierta.

### <a name="invoice-is-posted-in-fabrikam-east-for-vendor-100"></a>La factura se registra en Fabrikam Este para el proveedor 100

| Cuenta                          | Importe de débito | Importe de crédito |
|----------------------------------|--------------|---------------|
| Gasto (Fabrikam Este)          | 600,00       |               |
| Proveedores (Fabrikam Este) |              | 600,00        |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-vendor-3004"></a>El pago se genera y registra en Fabrikam para el proveedor 3004

| Cuenta                     | Importe de débito | Importe de crédito |
|-----------------------------|--------------|---------------|
| Proveedores (Fabrikam) | 600,00       |               |
| Efectivo (Fabrikam)             |              | 600,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>El pago de Fabrikam se liquida con la factura de Fabrikam Este

**Registro de Fabrikam**

| Cuenta                           | Importe de débito | Importe de crédito |
|-----------------------------------|--------------|---------------|
| Debido de Fabrikam Este (Fabrikam) | 600,00       |               |
| Proveedores (Fabrikam)       |              | 600,00        |

**Registro de Fabrikam Este**

| Cuenta                          | Importe de débito | Importe de crédito |
|----------------------------------|--------------|---------------|
| Proveedores (Fabrikam Este) | 600,00       |               |
| Importe debido a Fabrikam (Fabrikam Este)  |              | 600,00        |

## <a name="example-2-vendor-payment-of-invoice-from-another-legal-entity-with-cash-discount"></a>Ejemplo 2: pago de proveedor de una factura de otra entidad jurídica con descuento por pronto pago
Fabrikam Este tiene una factura abierta para el proveedor 100, Fourth Coffee. La factura tiene disponible un descuento por pronto pago de 20,00. Fabrikam entra y registra un pago de 580,00 al proveedor de Fabrikam 3004, Fourth Coffee. El pago se liquida con las facturas abiertas de Fabrikam Este. El descuento por pronto pago se registra en la entidad jurídica de la factura: Fabrikam Este.

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-vendor-100"></a>La factura se registra en Fabrikam Este para el proveedor 100 de Fabrikam Este

| Cuenta                          | Importe de débito | Importe de crédito |
|----------------------------------|--------------|---------------|
| Gasto (Fabrikam Este)          | 600,00       |               |
| Proveedores (Fabrikam Este) |              | 600,00        |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-fabrikam-vendor-3004"></a>El pago se genera y registra en Fabrikam para el proveedor 3004 de Fabrikam

| Cuenta                     | Importe de débito | Importe de crédito |
|-----------------------------|--------------|---------------|
| Proveedores (Fabrikam) | 580,00       |               |
| Efectivo (Fabrikam)             |              | 580,00        |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>El pago de Fabrikam se liquida con la factura de Fabrikam Este

**Registro de Fabrikam**

| Cuenta                           | Importe de débito | Importe de crédito |
|-----------------------------------|--------------|---------------|
| Debido de Fabrikam Este (Fabrikam) | 580,00       |               |
| Proveedores (Fabrikam)       |              | 580,00        |

**Registro de Fabrikam Este**

| Cuenta                          | Importe de débito | Importe de crédito |
|----------------------------------|--------------|---------------|
| Proveedores (Fabrikam Este) | 580,00       |               |
| Debido a Fabrikam (Fabrikam Este)  |              | 580,00        |
| Proveedores (Fabrikam Este) | 20,00        |               |
| Descuento por pronto pago (Fabrikam Este)    |              | 20,00         |

## <a name="example-3-vendor-payment-of-invoice-from-another-legal-entity-with-realized-exchange-rate-loss"></a>Ejemplo 3: pago de proveedor de una factura de otra entidad jurídica con una pérdida realizada por tipo de cambio
Fabrikam Este tiene una factura abierta para el proveedor 100, Fourth Coffee. Fabrikam entra y registra un pago para el proveedor de Fabrikam 3004, Fourth Coffee. El pago se liquida con la factura de Fabrikam Este abierta. Se genera una transacción de pérdida por cambio de divisa durante el proceso de liquidación.

-   Tipo de cambio de euros (EUR) a dólares estadounidenses (USD) en la fecha de factura: 1.2062
-   Tipo de cambio de euros a dólares USD en la fecha de pago: 1,2277

### <a name="invoice-is-posted-in-fabrikam-east-for-fabrikam-east-vendor-100"></a>La factura se registra en Fabrikam Este para el proveedor 100 de Fabrikam Este

| Cuenta                          | Importe de débito            | Importe de crédito           |
|----------------------------------|-------------------------|-------------------------|
| Gasto (Fabrikam Este)          | 600,00 EUR / 723,72 USD |                         |
| Proveedores (Fabrikam Este) |                         | 600,00 EUR / 723,72 USD |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-fabrikam-vendor-3004"></a>El pago se genera y registra en Fabrikam para el proveedor 3004 de Fabrikam

| Cuenta                     | Importe de débito            | Importe de crédito           |
|-----------------------------|-------------------------|-------------------------|
| Proveedores (Fabrikam) | 600,00 EUR / 736,62 USD |                         |
| Efectivo (Fabrikam)             |                         | 600,00 EUR / 736,62 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>El pago de Fabrikam se liquida con la factura de Fabrikam Este

**Registro de Fabrikam**

| Cuenta                           | Importe de débito            | Importe de crédito           |
|-----------------------------------|-------------------------|-------------------------|
| Debido de Fabrikam Este (Fabrikam) | 600,00 EUR / 736,62 USD |                         |
| Proveedores (Fabrikam)       |                         | 600,00 EUR / 736,62 USD |
| Pérdida realizada (Fabrikam)          | 0,00 EUR / 12,90 USD    |                         |
| Debido de Fabrikam Este (Fabrikam) |                         | 0,00 EUR / 12,90 USD    |

**Registro de Fabrikam Este**

| Cuenta                          | Importe de débito            | Importe de crédito           |
|----------------------------------|-------------------------|-------------------------|
| Proveedores (Fabrikam Este) | 600,00 EUR / 736,62 USD |                         |
| Debido a Fabrikam (Fabrikam Este)  |                         | 600,00 EUR / 736,62 USD |
| Debido a Fabrikam (Fabrikam Este)  | 0,00 EUR / 12,90 USD    |                         |
| Proveedores (Fabrikam Este) |                         | 0,00 EUR / 12,90 dólares USD    |

## <a name="example-4-vendor-payment-of-invoice-from-another-legal-entity-with-cash-discount-and-realized-exchange-rate-loss"></a>Ejemplo 4: pago de proveedor de una factura de otra entidad jurídica con un descuento por pronto pago y una pérdida realizada por tipo de cambio
Fabrikam Este tiene una factura abierta para el proveedor 100, Fourth Coffee. La factura tiene un descuento por pronto pago y se genera una transacción de impuestos. Fabrikam registra un pago para el proveedor 3004 de Fabrikam, Fourth Coffee. El pago se liquida con la factura de Fabrikam Este abierta. Se genera una transacción de pérdida por cambio de divisa durante el proceso de liquidación. El descuento por pronto pago se registra en la entidad jurídica de la factura (Fabrikam Este) y la pérdida por cambio de divisa se registra en la entidad jurídica del pago (Fabrikam).

-   Tipo de cambio de euros a dólares USD en la fecha de factura: 1,2062
-   Tipo de cambio de euros a dólares USD en la fecha de pago: 1,2277

### <a name="invoice-is-posted-and-a-tax-transaction-is-generated-in-fabrikam-east-for-vendor-100"></a>La factura se registra y se genera una transacción de impuestos en Fabrikam Este para el proveedor 100

| Cuenta                          | Importe de débito            | Importe de crédito           |
|----------------------------------|-------------------------|-------------------------|
| Gasto (Fabrikam Este)          | 564,07 EUR / 680,38 USD |                         |
| Impuestos (Fabrikam Este)        | 35,93 EUR / 43,34 USD   |                         |
| Proveedores (Fabrikam Este) |                         | 600,00 EUR / 723,72 USD |

### <a name="payment-is-generated-and-posted-in-fabrikam-for-vendor-3004"></a>El pago se genera y registra en Fabrikam para el proveedor 3004

| Cuenta                     | Importe de débito            | Importe de crédito           |
|-----------------------------|-------------------------|-------------------------|
| Proveedores (Fabrikam) | 588,72 EUR / 722,77 USD |                         |
| Efectivo (Fabrikam Este)        |                         | 588,72 EUR / 722,77 USD |

### <a name="fabrikam-payment-is-settled-with-fabrikam-east-invoice"></a>El pago de Fabrikam se liquida con la factura de Fabrikam Este

**Registro de Fabrikam**

| Cuenta                           | Importe de débito            | Importe de crédito           |
|-----------------------------------|-------------------------|-------------------------|
| Debido de Fabrikam Este (Fabrikam) | 588,72 EUR / 722,77 USD |                         |
| Proveedores (Fabrikam)       |                         | 588,72 EUR / 722,77 USD |
| Pérdida realizada (Fabrikam)          | 0,00 EUR / 12,66 USD    |                         |
| Debido de Fabrikam Este (Fabrikam) |                         | 0,00 EUR / 12,66 USD    |

**Registro de Fabrikam Este**

| Cuenta                          | Importe de débito            | Importe de crédito           |
|----------------------------------|-------------------------|-------------------------|
| Proveedores (Fabrikam Este) | 588,72 EUR / 722,77 USD |                         |
| Debido a Fabrikam (Fabrikam Este)  |                         | 588,72 EUR / 722,77 USD |
| Debido a Fabrikam (Fabrikam Este)   | 0,00 EUR / 12,66 USD    |                         |
| Proveedores (Fabrikam Este) |                         | 0,00 EUR / 12,66 USD    |
| Proveedores (Fabrikam Este) | 11,28 EUR / 13,61 USD   |                         |
| Descuento por pronto pago (Fabrikam Este)    |                         | 11,28 EUR / 13,61 USD   |

## <a name="example-5-vendor-credit-note-with-primary-payment"></a>Ejemplo 5: Nota de abono de proveedor con pago principal
Fabrikam genera un pago de 75,00 para el proveedor 3004, Fourth Coffee. El pago se liquida con una factura abierta para el proveedor 3004 de Fabrikam Oeste y una nota de abono abierta para el proveedor 100 de Fabrikam Este. Se selecciona el pago como pago principal en la página **Liquidar transacciones**.

### <a name="invoice-is-posted-to-fabrikam-west-for-vendor-3004"></a>La factura se registra en Fabrikam Oeste para el proveedor 3004

| Cuenta                          | Importe de débito | Importe de crédito |
|----------------------------------|--------------|---------------|
| Gasto (Fabrikam Oeste)          | 100,00       |               |
| Proveedores (Fabrikam Oeste) |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-vendor-100"></a>La nota de abono se registra en Fabrikam Este para el proveedor 100

| Cuenta                          | Importe de débito | Importe de crédito |
|----------------------------------|--------------|---------------|
| Proveedores (Fabrikam Este) | 25,00        |               |
| Devoluciones de compras (Fabrikam Este) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-vendor-3004"></a>El pago se registra en Fabrikam para el proveedor 3004

| Cuenta                     | Importe de débito | Importe de crédito |
|-----------------------------|--------------|---------------|
| Proveedores (Fabrikam) | 75,00        |               |
| Efectivo (Fabrikam)             |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>El pago de Fabrikam se liquida con la factura de Fabrikam Oeste y la nota de abono de Fabrikam Este

**Registro de Fabrikam**

| Cuenta                           | Importe de débito | Importe de crédito |
|-----------------------------------|--------------|---------------|
| Proveedores (Fabrikam)       | 25,00        |               |
| Debido a Fabrikam Este (Fabrikam)   |              | 25,00         |
| Debido de Fabrikam Oeste (Fabrikam) | 100,00       |               |
| Proveedores (Fabrikam)       |              | 100,00        |

**Registro de Fabrikam Este**

| Cuenta                           | Importe de débito | Importe de crédito |
|-----------------------------------|--------------|---------------|
| Debido de Fabrikam Este (Fabrikam) | 25,00        |               |
| Proveedores (Fabrikam Este)  |              | 25,00         |

**Registro de Fabrikam Oeste**

| Cuenta                          | Importe de débito | Importe de crédito |
|----------------------------------|--------------|---------------|
| Proveedores (Fabrikam Oeste) | 100,00       |               |
| Debido a Fabrikam (Fabrikam Oeste)  |              | 100,00        |

## <a name="example-6-vendor-credit-note-without-primary-payment"></a>Ejemplo 6: Nota de abono de proveedor sin pago principal
Fabrikam genera un pago de 75,00 para el proveedor 3004, Fourth Coffee. El pago se liquida con una factura abierta para el proveedor 3004 de Fabrikam Oeste y una nota de abono abierta para el proveedor 100 de Fabrikam Este. No se selecciona el pago como pago principal en la página **Liquidar transacciones**.

### <a name="invoice-is-posted-to-fabrikam-west-for-vendor-3004"></a>La factura se registra en Fabrikam Oeste para el proveedor 3004

| Cuenta                          | Importe de débito | Importe de crédito |
|----------------------------------|--------------|---------------|
| Gasto (Fabrikam Oeste)          | 100,00       |               |
| Proveedores (Fabrikam Oeste) |              | 100,00        |

### <a name="credit-note-is-posted-to-fabrikam-east-for-vendor-100"></a>La nota de abono se registra en Fabrikam Este para el proveedor 100

| Cuenta                          | Importe de débito | Importe de crédito |
|----------------------------------|--------------|---------------|
| Proveedores (Fabrikam Este) | 25,00        |               |
| Devoluciones de compras (Fabrikam Este) |              | 25,00         |

### <a name="payment-is-posted-to-fabrikam-for-vendor-3004"></a>El pago se registra en Fabrikam para el proveedor 3004

| Cuenta                     | Importe de débito | Importe de crédito |
|-----------------------------|--------------|---------------|
| Proveedores (Fabrikam) | 75,00        |               |
| Efectivo (Fabrikam)             |              | 75,00         |

### <a name="fabrikam-payment-is-settled-with-fabrikam-west-invoice-and-fabrikam-east-credit-note"></a>El pago de Fabrikam se liquida con la factura de Fabrikam Oeste y la nota de abono de Fabrikam Este

**Registro de Fabrikam**

| Cuenta                           | Importe de débito | Importe de crédito |
|-----------------------------------|--------------|---------------|
| Debido de Fabrikam Oeste (Fabrikam) | 75,00        |               |
| Proveedores (Fabrikam)       |              | 75,00         |

**Registro de Fabrikam Este**

| Cuenta                                | Importe de débito | Importe de crédito |
|----------------------------------------|--------------|---------------|
| Debido de Fabrikam Este (Fabrikam Este) | 25,00        |               |
| Proveedores (Fabrikam Este)       |              | 25,00         |

**Registro de Fabrikam Oeste**

| Cuenta                              | Importe de débito | Importe de crédito |
|--------------------------------------|--------------|---------------|
| Proveedores (Fabrikam Oeste)     | 75,00        |               |
| Debido a Fabrikam (Fabrikam Oeste)      |              | 75,00         |
| Proveedores (Fabrikam Oeste)     | 25,00        |               |
| Debido a Fabrikam (Fabrikam Oeste) |              | 25,00         |






