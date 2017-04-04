---
title: "Conciliar el flete en la administración del transporte"
description: "En este artículo se describe el proceso de conciliación de flete."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: TMSAuditMaster, TMSFreightBillInvoiceReconcile, TMSFreightBillSummary, TMSFreightBillType, TMSFreightMatchReason, TMSInvoiceTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 89983
ms.assetid: bc34a9b1-0c11-4797-b463-25409cf98ca8
ms.search.region: Global
ms.search.industry: Distribution
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: c85806132efb65c2d4bc85ef1921c003c5c7453b
ms.lasthandoff: 03/31/2017


---

# <a name="reconcile-freight-in-transportation-management"></a>Conciliar el flete en la administración del transporte

En este artículo se describe el proceso de conciliación de flete.

La conciliación de flete se puede realizar manualmente o se puede configurar para que se produzca automáticamente. Para usar la conciliación de flete automático, debe configurar un maestro de auditoría donde pueda definir los criterios que determinan qué albaranes de flete se concilian automáticamente.

## <a name="the-freight-reconciliation-process"></a>El proceso de conciliación de flete
Las tasas de flete se calculan por el motor de velocidad que está asociado al transportista de envío pertinente. Cuando se confirma una carga, se genera un albarán de flete y las tasas de flete se transfieren a él. Las tasas de flete se distribuyen como gastos varios al documento de origen pertinente (pedido de compra, pedido de ventas o pedido de transferencia), en función de la configuración que se utiliza para el proceso de facturación normal. El proceso de conciliación de flete (que también se conoce como el proceso de conciliación) puede iniciarse tan pronto como llega la factura de flete del transportista de envío. La factura se puede recibir de manera electrónica o en papel. Si la factura en papel se recibe, puede generar una factura electrónica mediante el albarán de flete como plantilla. 

[proceso de conciliación![la carga![] (. /media/freight-reconcilation-process.jpg])(. /media/freight-reconcilation-process.jpg)

## <a name="manual-reconciliation"></a>Conciliación manual
Si está conciliando el flete manualmente, deben conciliar cada línea de factura con la línea o líneas del albarán de flete para la carga que se factura. Esto se hace conciliando en la página **Conciliación de albaranes de flete y facturas**. Si el importe de la línea de factura no coincide con el importe del albarán de flete, debe seleccionar un motivo de conciliación para la diferencia. Si hay varios motivos para la conciliación, puede dividir el importe no conciliado entre ellos. El motivo de conciliación determina cómo se registran los importes de diferencia en la contabilidad general. Cuando se contabiliza la conciliación de todo el importe de la factura, se envía para aprobación y, a continuación, se registra el diario. En la ilustración siguiente se muestra cómo generar una factura de transporte y realizar la conciliación de transporte en Microsoft Dynamics 365 for Operations. 
[tareas de conciliación![la carga![de Dynamics AX (]. /media/processflowforfreightreconciliation.jpg])(. /media/processflowforfreightreconciliation.jpg)
## <a name="automatic-reconciliation"></a>Conciliación automática
Para utilizar la conciliación automática, debe especificar la programación de conciliación y las facturas y los transportistas de envío que se utilizarán. La conciliación de las líneas de factura y los albaranes de flete se realiza según la configuración del tipo de albarán de flete y el maestro de auditoría. Tras la ejecución de la conciliación automática, debe controlar todas las facturas que el sistema no puede conciliar. A continuación, debe procesar estas facturas manualmente para poder registrar todas las facturas para el pago.


