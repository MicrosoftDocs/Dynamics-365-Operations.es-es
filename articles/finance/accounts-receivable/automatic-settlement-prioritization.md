---
title: Liquidación y priorización automáticas
description: Este tema describe cómo se liquidan las transacciones si selecciona Liquidación automática en la página Parámetros de clientes. También explica cómo se puede usar la liquidación automática junto con la prioridad de pago.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 01/30/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustOpenTrans, CustParameters, LedgerJournalTransCustPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14531
ms.assetid: e7837cf6-ec69-44b4-8d47-eba38d5c7b1f
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b596557e80035e8d62d01f156a6678c75e4ae573
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447577"
---
# <a name="automatic-settlement-and-prioritization"></a>Liquidación y priorización automáticas

[!include [banner](../includes/banner.md)]

Este tema describe cómo se liquidan las transacciones si selecciona Liquidación automática en la página Parámetros de clientes. También explica cómo se puede usar la liquidación automática junto con la prioridad de pago.

Tiene dos opciones al liquidar pagos con facturas y otras transacciones. También puede seleccionar manualmente las transacciones para liquidar, o el sistema puede seleccionar las transacciones automáticamente mediante la funcionalidad de liquidación automática. También puede personalizar cómo se procesan las liquidaciones automáticas mediante la opción **Priorizar liquidación**. Todas estas opciones son parte de los parámetros de liquidación que se definen en la página **Parámetros de clientes**. La forma en que las transacciones se liquidan automáticamente puede variar en función del método que se usa para la liquidación automática. Están disponibles los siguientes métodos:

-   Prioridad de liquidación definida por el usuario
-   Liquidación automática predeterminada

Las siguientes secciones describen cómo se liquidan las transacciones con cada método.

## <a name="example-transactions"></a>Transacciones de ejemplo
Los ejemplos de liquidaciones que se proporcionan más adelante en este artículo se basan en las siguientes transacciones. Todas las transacciones son del cliente 2.050.

| Transacción   | Fecha        | Importe | Condiciones de descuento por pronto pago | Fecha del descuento por pronto pago | Comentarios                                                                                                                                                                                      |
|---------------|-------------|--------|---------------------|--------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Factura 1     | 15 de agosto   | 100,00 | 2%14, Neto 30        | 29 de agosto          |                                                                                                                                                                                               |
| Factura 2     | 1 de septiembre | 250,00 | 2%14, Neto 30        | 15 de septiembre       |                                                                                                                                                                                               |
| Factura 3     | Octubre de 15  | 500,00 | 2% 14/Net 30        | 29 de octubre         |                                                                                                                                                                                               |
| Nota de interés | 15 de octubre  | 7,00   |                     |                    | Esta nota de interés es para la factura 1 y la factura 2. El importe se calcula como un interés del 2 por ciento sobre importes que han vencido hace 30 días o más. Por ejemplo, 0,02 × (100,00 + 250,00) = 7,00. |

## <a name="user-defined-settlement-priority"></a>Prioridad de liquidación definida por el usuario
Si establece **Usar la prioridad para las liquidaciones automáticas** en **Sí** en la página **Parámetros de clientes**, se usa la prioridad de liquidación que defina en la página **Prioridad de liquidación** cuando las transacciones se seleccionan para la liquidación automática. En este ejemplo, se define la prioridad de liquidación siguiente:

1.  Tipo de transacción
    -   Cuotas de pago
    -   Cartas de cobro
    -   Notas de interés
    -   Facturas

2.  Fecha de transacción, Ascendente
3.  Comprobante

Si se registra un pago de 700,00 el 25 de octubre, el pago se liquida para las transacciones en el orden siguiente.

| Comprobante       | Fecha       | Factura | Importe en divisa de la transacción | Importe para liquidar | Saldo | Divisa |
|---------------|------------|---------|--------------------------------|------------------|---------|----------|
| Nota de interés | 15/10/2015 |         | 7,00                           | 7,00             | 0,00    | USD      |
| Factura 1     | 15/8/2015  | 10001   | 100,00                         | 100,00           | 0,00    | USD      |
| Factura 2     | 1/9/2015   | 10002   | 250,00                         | 250,00           | 0,00    | USD      |
| Factura 3     | 15/10/2015 |         | 500,00                         | 343,00           | 157,00  | USD      |

## <a name="default-automatic-settlement"></a>Liquidación automática predeterminada
Si no se ha especificado ninguna prioridad de liquidación definida por el usuario, las transacciones se seleccionarán automáticamente para la liquidación en función de la fecha de vencimiento. Las transacciones que se liquidan deben tener la misma divisa que la transacción con la que se liquidarán. Si se registra un pago de 700,00 el 25 de octubre, las siguientes transacciones se seleccionarán para la liquidación.

| Comprobante       | Fecha       | Factura | Importe en divisa de la transacción | Importe para liquidar | Saldo | Divisa |
|---------------|------------|---------|--------------------------------|------------------|---------|----------|
| Factura 1     | 15/8/2015  | 10001   | 100,00                         | 100,00           | 0,00    | USD      |
| Factura 2     | 1/9/2015   | 10002   | 250,00                         | 250,00           | 0,00    | USD      |
| Factura 3     | 15/10/2015 |         | 500.00                         | 350.00           | 150.00  | USD      |
| Nota de interés | 15/10/2015 |         | 7.00                           | 0,00             | 7.00    | USD      |







[!INCLUDE[footer-include](../../includes/footer-banner.md)]