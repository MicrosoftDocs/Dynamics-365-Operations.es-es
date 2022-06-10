---
title: Entidades de factura de proveedor
description: Este tema proporciona información sobre entidades de factura de proveedor, que permiten configurar códigos de tipo de coste para costes internos o costes derivados externamente.
author: yufeihuang
ms.date: 05/27/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yufeihuang
ms.search.validFrom: 2022-05-27
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: 4bbe0fdbf95050ebfa707224f602e5e71ddb3a8f
ms.sourcegitcommit: 611202adaa080250636efabb3b3b32b850d92d04
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2022
ms.locfileid: "8813139"
---
# <a name="vendor-invoice-entities"></a>Entidades de factura de proveedor

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

El módulo **Coste descargado** permite que los códigos de tipo de coste se configuren para costes internos o costes derivados externamente. Si un coste es externo a un negocio, se espera una factura del proveedor de servicios. Esta factura se procesa como un diario de facturas que se puede asociar con un viaje, y el valor de la factura se puede distribuir entre uno o más costes del viaje.

Las entidades de factura de proveedor permiten que el valor de una línea de diario se asigne a uno o más costes de un viaje que comparten el mismo código de tipo de costo.

Solo se puede asignar un coste si existen el encabezado del diario de facturas y las líneas del diario de facturas.

## <a name="vendor-voyage-cost-allocations-itmledgerjournalcostlinesvoyagesentity"></a>Asignaciones de costes de viaje del proveedor (ITMLedgerJournalCostLinesVoyagesEntity)

La entidad de datos de asignaciones de costes de viaje del proveedor permite asignar una línea de factura de proveedor a uno o más costos que se aplican al área de costos de viaje. Esta función es soportada por la entidad `ITMLedgerJournalCostLinesVoyagesEntity`. La siguiente tabla enumera los campos y las asignaciones que componen esta entidad.

| Name | Asignación | Tipo de datos | Clave | Obligatoria |
|---|---|---|---|---|
| Importe asignado | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | No | No |
| Número de línea de transacción de costes | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sí** | No |
| Número de línea del diario | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Sí** | No |
| Número de diario | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Sí** | No |
| Viaje | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Sí** | No |

## <a name="vendor-shipping-container-cost-allocations-itmledgerjournalcostlinescontainersentity"></a>Asignaciones de costos de contenedores de envío de proveedores (ITMLedgerJournalCostLinesContainersEntity)

La entidad de datos de asignaciones de costes de contenedor de envío del proveedor permite asignar una línea de factura de proveedor a uno o más costos que se aplican al área de costos del contenedor de envío. Esta función es soportada por la entidad `ITMLedgerJournalCostLinesContainersEntity`. La siguiente tabla enumera los campos y las asignaciones que componen esta entidad.

| Name | Asignación | Tipo de datos | Clave | Obligatoria |
|---|---|---|---|---|
| Importe asignado | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | No | No |
| Contenedor de envío | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Sí** | No |
| Número de línea de transacción de costes | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sí** | No |
| Número de línea del diario | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Sí** | No |
| Número de diario | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Sí** | No |
| Viaje | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Sí** | No |

## <a name="vendor-folio-cost-allocations-itmledgerjournalcostlinesfoliosentity"></a>Asignaciones de costes de folio del proveedor (ITMLedgerJournalCostLinesFoliosEntity)

La entidad de datos de asignaciones de costes de folio del proveedor permite asignar una línea de factura de proveedor a uno o más costos que se aplican al área de costos de folio. Esta función es soportada por la entidad `ITMLedgerJournalCostLinesFoliosEntity`. La siguiente tabla enumera los campos y las asignaciones que componen esta entidad.

| Name | Asignación | Tipo de datos | Clave | Obligatoria |
|---|---|---|---|---|
| Importe asignado | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | No | No |
| Número de línea de transacción de costes | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sí** | No |
| Folio | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Sí** | No |
| Número de línea del diario | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Sí** | No |
| Número de diario | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Sí** | No |

## <a name="vendor-purchase-order-cost-allocations-itmledgerjournalcostlinespurchtableentity"></a>Asignaciones de costes de pedidos de compra de proveedores (ITMLedgerJournalCostLinesPurchTableEntity)

La entidad de datos de asignaciones de costes de pedido de compra del proveedor permite asignar una línea de factura de proveedor a uno o más costos que se aplican al área de costos del pedido de compra. Esta función es soportada por la entidad `ITMLedgerJournalCostLinesPurchTableEntity`. La siguiente tabla enumera los campos y las asignaciones que componen esta entidad.

| Name | Asignación | Tipo de datos | Clave | Obligatoria |
|---|---|---|---|---|
| Importe asignado | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | No | No |
| Número de línea de transacción de costes | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sí** | No |
| Número de línea del diario | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Sí** | No |
| Número de diario | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Sí** | No |
| Pedido de compra | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Sí** | No |

## <a name="vendor-item-cost-allocations-itmledgerjournalcostlinespurchlineentity"></a>Asignaciones de costes de artículo del proveedor (ITMLedgerJournalCostLinesPurchLineEntity)

La entidad de datos de asignaciones de costes de artículo del proveedor permite asignar una línea de factura de proveedor a uno o más costos que se aplican al área de costes de artículo. El área de coste del artículo cubre los costos en la línea de la orden de compra. Esta función es soportada por la entidad `ITMLedgerJournalCostLinesPurchLineEntity`. La siguiente tabla enumera los campos y las asignaciones que componen esta entidad.

| Name | Asignación | Tipo de datos | Clave | Obligatoria |
|---|---|---|---|---|
| Importe asignado | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | No | No |
| Número de línea de transacción de costes | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sí** | No |
| Número de línea del diario | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Sí** | No |
| Número de diario | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Sí** | No |
| Pedido de compra | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Sí** | No |
| Número de línea de pedido de compra | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sí** | No |

## <a name="vendor-transfer-order-line-cost-allocations-itmledgerjournalcostlinestransferlineentity"></a>Asignaciones de costes de línea de pedido de transferencia de proveedor (ITMLedgerJournalCostLinesTransferLineEntity)

La entidad de datos de asignaciones de costes de línea de pedido de transferencia del proveedor permite asignar una línea de factura de proveedor a uno o más costos que se aplican al área de costos de la línea de transferencia. Esta función es soportada por la entidad `ITMLedgerJournalCostLinesTransferLineEntity`. La siguiente tabla enumera los campos y las asignaciones que componen esta entidad.

| Name | Asignación | Tipo de datos | Clave | Obligatoria |
|---|---|---|---|---|
| Importe asignado | ITMLedgerJournalCostLines.Amount | Numeric(32, 6) | No | No |
| Número de línea de transacción de costes | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sí** | No |
| Número de línea del diario | ITMLedgerJournalCostLines.RefRecId | Numeric(32, 16) | **Sí** | No |
| Número de diario | ITMLedgerJournalCostLines.RefRecId | Nvarchar(20) | **Sí** | No |
| Pedido de transferencia | ITMLedgerJournalCostLines.CostTransRefRecId | Nvarchar(20) | **Sí** | No |
| Número de línea de pedido de transferencia | ITMLedgerJournalCostLines.CostTransRefRecId | Numeric(32, 16) | **Sí** | No |

### <a name="reference-table"></a>Tabla de referencia

Las líneas de coste de viaje tienen una asociación directa con un registro de transacción de coste. Este registro incluye el valor del **Identificador de la tabla de referencia**. Este valor es único para cada área de costo (viaje, contenedor de envío, etc.). Cuando se hace referencia a números de tabla específicos para datos que se crean mediante el uso de entidades de datos, las entidades se dividen en función de valores de **Identificación de la tabla de referencia**.

Los valores de la tabla de referencia (`RefTableId`) y el tipo de transacción (`TransType`) están implícitos en la selección de la línea de compra de costo descargado o la entidad de línea de transferencia de costo descargado.

## <a name="vendor-invoice-journal-lines-vendorinvoicejournallineentity"></a>Líneas de diario de factura de proveedor (VendorInvoiceJournalLineEntity)

Antes de que se pueda asignar un valor de línea de diario a uno o más costes en el módulo **Coste descargado**, la línea de diario debe estar asociada con un área de coste. Para soportar esta funcionalidad, el módulo **Coste descargado** agrega algunos campos nuevos a la tabla de líneas de diario (`LedgerJournalTrans`).

### <a name="fields-added-to-the-vendor-invoice-journal-line-entity"></a>Campos agregados a la entidad de línea de diario de factura de proveedor

La siguiente tabla enumera los campos que el módulo **Coste descargado** agrega a la entidad de línea de diario de factura de proveedor (`VendorInvoiceJournalLineEntity`). Estos campos permiten que el sistema cree líneas de diario y asigne costes contra ellas.

| Name | Asignación | Tipo de datos | Clave | Obligatoria |
|---|---|---|---|---|
| Área de coste | LedgerJournalTrans.ITMCostArea | Int | No | No |
| Código de tipo de coste | LedgerJournalTrans.ITMCostTypeId | Nvarchar(20) | No | No |

### <a name="mainoffset-account"></a>Cuenta principal/de contrapartida

La cuenta principal/de contrapartida para una línea del diario de facturas que está asociada con un viaje de costo descargado está determinada por el código de tipo de costo. Cuando el código de tipo de coste se incluye en la línea del diario de facturas, la cuenta de compensación para el código se utilizará como cuenta principal o como cuenta de contrapartida, según el escenario:

- **Diario de una sola línea** – Si se define una cuenta principal (en otras palabras, la cuenta de proveedor) y se proporciona un código de tipo de coste, el valor de la cuenta de compensación para ese código de tipo de costo se ingresará en la cuenta de contrapartida.
- **Diario de varías líneas** – Si no se define una cuenta principal, pero se proporciona un código de tipo de coste, el valor de la cuenta de compensación para ese código de tipo de costo se ingresará en la cuenta principal. La línea de diario que acredita al proveedor no hará referencia a un código de tipo de coste.

## <a name="sequencing"></a>Secuenciación

Debido a las dependencias entre las tablas de diario y líneas de diario, primero se debe crear el registro de viaje. Las líneas de viaje solo se puede crear después de que se hayan creado el viaje, el contenedor de envío y los folios.

Para asignar una factura de viaje, el sistema debe procesar las entidades en el siguiente orden:

1. Encabezado de diario de factura (`VendInvoiceJournalHeaderEntity`)
1. Línea de diario de facturas (`VendInvoiceJournalLineEntity`)
1. Ver asignaciones de costes (`ITMLedgerJournalEntities`)
