---
title: Conciliar el flete en la administración del transporte
description: En este tema se describe el proceso de conciliación de flete.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSFBDetailReconcile, TMSInvoiceTable,TMSInvoiceLineReconcile,TMSReconcileInvoice, TMSFreightBillDetail, TMSFreightBillTypeAssignment, TMSRejectInvoiceLine, TMSMiscellaneousCharge
audience: Application User
ms.reviewer: kamaybac
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: ac07155e4dde77689b1994abfb8b30f45d5a5a30
ms.sourcegitcommit: b6686265314499056690538eaa95ca51cff7c720
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5014517"
---
# <a name="reconcile-freight-in-transportation-management"></a>Conciliar el flete en la administración del transporte

[!include [banner](../includes/banner.md)]

En este tema se describe el proceso de conciliación de flete.

La conciliación de flete se puede realizar manualmente o se puede configurar para que se produzca automáticamente. Para usar la conciliación de flete automático, debe configurar un maestro de auditoría donde pueda definir los criterios que determinan qué albaranes de flete se concilian automáticamente.

## <a name="the-freight-reconciliation-process"></a>El proceso de conciliación de flete

Las tasas de flete se calculan por el motor de velocidad que está asociado al transportista de envío pertinente. Cuando se confirma una carga, se genera un albarán de flete y las tasas de flete se transfieren a él. Las tasas de flete se distribuyen como gastos varios al documento de origen pertinente (pedido de compra, pedido de ventas o pedido de transferencia), en función de la configuración que se utiliza para el proceso de facturación normal. El proceso de conciliación de flete (que también se conoce como el proceso de conciliación) puede iniciarse tan pronto como llega la factura de flete del transportista de envío. La factura se puede recibir de manera electrónica o en papel. Si la factura en papel se recibe, puede generar una factura electrónica mediante el albarán de flete como plantilla.

[![Proceso de conciliación de flete](./media/freight-reconcilation-process.jpg)](./media/freight-reconcilation-process.jpg)

## <a name="manual-reconciliation"></a>Conciliación manual

Si está conciliando el flete manualmente, deben conciliar cada línea de factura con la línea o líneas del albarán de flete para la carga que se factura. Esto se hace conciliando en la página **Conciliación de albaranes de flete y facturas**. Si el importe de la línea de factura no coincide con el importe del albarán de flete, debe seleccionar un motivo de conciliación para la diferencia. Si hay varios motivos para la conciliación, puede dividir el importe no conciliado entre ellos. El motivo de conciliación determina cómo se registran los importes de diferencia en la contabilidad general. Cuando se contabiliza la conciliación de todo el importe de la factura, se envía para aprobación y, a continuación, se registra el diario. En la ilustración siguiente se muestra cómo generar una factura de flete y realizar la conciliación de flete.

[![Tareas de conciliación de flete](./media/processflowforfreightreconciliation.jpg)](./media/processflowforfreightreconciliation.jpg)

## <a name="automatic-reconciliation"></a>Conciliación automática

Para utilizar la conciliación automática, debe especificar la programación de conciliación y las facturas y los transportistas de envío que se utilizarán. La conciliación de las líneas de factura y los albaranes de flete se realiza según la configuración del tipo de albarán de flete y el maestro de auditoría. Tras la ejecución de la conciliación automática, debe controlar todas las facturas que el sistema no puede conciliar. A continuación, debe procesar estas facturas manualmente para poder registrar todas las facturas para el pago.

## <a name="match-freight-bills-with-freight-invoices-using-automatic-or-manual-reconciliation"></a>Haga coincidir las facturas de flete con las facturas de flete mediante la conciliación automática o manual

*Matching* es el proceso de encontrar las facturas de flete que corresponden a cada factura de flete. Esto se puede hacer haciendo coincidir las líneas de la factura una por una (comparación manual) o haciendo coincidir todas las facturas disponibles a la vez (coincidencia automática).

### <a name="auto-matching"></a>Coincidencia automática

Al hacer coincidir varias facturas de flete con la misma factura de flete, el proceso de coincidencia automática funciona de la siguiente manera:

1. Todas las facturas de flete no igualadas se clasifican por monto, con el monto mayor primero.
1. Las facturas de flete se comparan una por una, hasta que la factura de flete no tenga un monto positivo restante.
1. Según la configuración del maestro de auditoría y el monto restante en las facturas de flete, se establece el monto restante.

### <a name="manual-matching"></a>Conciliación manual

Todas las facturas de flete con montos positivos estarán disponibles para coincidir. De forma similar a la comparación automática, el usuario solo podrá hacer coincidir las facturas de flete con montos negativos con las facturas de flete que no coincidan completamente.

### <a name="example"></a>Ejemplo

Suponga que tiene una factura de flete (FB) por un monto de 1500 y ha creado tres facturas de flete para la factura de flete con una línea de factura para cada factura con las siguientes configuraciones:

- Factura de flete original (FB): Monto 1500
- Factura 1 (Inv1): Importe 1000
- Factura 2 (Inv2): Importe 600
- Factura 3 (Inv3): Importe -100

#### <a name="automatic-matching-result"></a>Resultado de coincidencia automático

La coincidencia automática se ejecutará en el siguiente orden:

1. Ordene todas las facturas de flete descendiendo por monto: Inv1 -> Inv2 -> Inv3.
1. Haga coincidir Inv1 con FB. Inv1 tiene 1000 coincidente y FB tiene 500 como importe restante, por lo que el estado se establece en *Parcialmente emparejado*.
1. Haga coincidir Inv2 con FB. Inv2 tiene 500 coincidente y FB tiene 0 como importe restante, por lo que el estado se establece en *Completamente emparejado*.
1. Debido a que FB ahora está completamente emparejado, Inv3 no se procesará.

#### <a name="manual-matching-result"></a>Resultado de coincidencia manual

Para la coincidencia manual, los resultados varían según el orden de la coincidencia, como se ilustra en los siguientes casos de ejemplo.

##### <a name="manual-matching-case-1"></a>Caso de correspondencia manual 1

Una forma de hacer la coincidencia manual para este ejemplo es proceder de la siguiente manera:

1. Haga coincidir FB con Inv1. FB tiene un importe de 500 restante, por lo que el estado se establece en *Parcialmente emparejado*.
1. Haga coincidir Inv2 con FB. Inv2 tiene 500 coincidente y FB tiene 0 como importe restante, por lo que el estado se establece en *Completamente emparejado*.
1. Cuando haga coincidir Inv3 manualmente, no encontrará facturas de flete incomparables.

Este caso es esencialmente el mismo que la coincidencia automática

##### <a name="manual-matching-case-2"></a>Caso de correspondencia manual 2

Otra forma de hacer la coincidencia manual para este ejemplo es proceder de la siguiente manera:

1. Haga coincidir Inv3 con FB. Ahora FB tiene una cantidad restante de 1600, que es lo mismo que restar 100 negativo sobre 1500. Tanto FB como Inv3 tienen una cantidad equivalente de -100.
1. Haga coincidir Inv1 e Inv 2 con FB uno tras otro. FB está completamente coincidente.

Como muestra este ejemplo, las facturas de flete coincidentes con importes negativos solo deben realizarse manualmente. Esto garantizará que siempre sea posible hacer coincidir las facturas de flete con importes negativos con una factura de flete que no coincida completamente porque eso le permite controlar la secuencia de coincidencia.
