---
title: Entidades de transacción de costes
description: Este artículo proporciona información sobre las entidades de transacción de costes, que permiten dividir el valor de un coste entre los contenidos de un área de costos mediante la selección de un método de prorrateo.
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
ms.openlocfilehash: 3aabc1356eba27de797fa696dd928cb401d8501b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860823"
---
# <a name="cost-transaction-entities"></a>Entidades de transacción de coste

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

## <a name="apportionment"></a>Reparto

El costo descargado permite que el valor de un costo se divida entre los contenidos de un área de costo (viaje, contenedor de envío, etc.) a través de la selección de un método de prorrateo. El método de prorrateo se establece como parte de la configuración de costes automáticos que se basa en reglas de negocio. Se extrae como parte del costo cuando se crea una línea de viaje.

### <a name="configure-the-apportionment-mapping-for-use-with-data-entities"></a>Configurar la asignación de prorrateo para su uso con entidades de datos

Cuando se crea un costo a partir de una fuente externa, como un transitario, esa fuente externa no puede especificar el método preferido para prorratear el valor del costo. La asignación de prorrateo define el método de prorrateo predeterminado para cada código de tipo de costo. Se accede a la tabla de asignación de prorrateo desde la página **Asignación de prorrateo** en Microsoft Dynamics 365 Supply Chain Management (**Coste de descarga \> Configuración de costes \> Asignación de prorrateo**).

Si se ha definido una combinación de asignación y se crea un coste que coincide con el código de tipo de costo mediante el uso de una entidad de transacción de costo, se utilizará el método de prorrateo asignado en lugar de cualquier valor que se haya proporcionado a la entidad.

Si no hay ningún valor presente en la tabla de asignación, pero se ha proporcionado un valor a la entidad, se utilizará el valor proporcionado.

Si no existe ningún valor en la tabla de asignación o en el registro que se envió a la entidad, la creación fallará.

### <a name="apportionment-mapping-itmapportionmentmapping"></a>Asignación de reparto (ITMApportionmentMapping)

La entidad de asignación de reparto (`ITMApportionmentMapping`) crea relaciones de asignación de reparto y permite a los usuarios crear o actualizar registros.

| Name | Asignación | Tipo de datos | Clave | Obligatoria |
|---|---|---|---|---|
| Método de reparto | ITMApportionmentMapping.ApportionmentMethod | Int | No | No |
| Código de tipo de coste | ITMApportionmentMapping.ShipCostTypeId | Nvarchar(20) | **Sí** | No |

## <a name="voyage-costs-itmcosttransvoyageentity"></a>Costes de viaje (ITMCostTransVoyageEntity)

La entidad de costes de viaje (`ITMCostTransVoyageEntity`) crea transacciones de costes de viaje que se aplican a nivel de viaje. Durante el proceso de importación, el sistema utiliza los valores **Categoría** y **Método de reparto** que se incluyen en la entidad para determinar cómo se distribuye el valor del coste entre los contenidos del viaje.

| Name | Asignación | Tipo de datos | Clave | Obligatoria |
|---|---|---|---|---|
| Método de reparto | ITMCostTrans.ApportionmentMethod | Int | No | No |
| Valor de coste | ITMCostTrans.CostValue | Numeric(32, 6) | No | No |
| Divisa | ITMCostTrans.CurrencyCode | Nvarchar(3) | No | **Sí** |
| Número de línea | ITMCostTrans.LineNum | Numeric(32, 16) | **Sí** | No |
| Tipo de coste vinculado | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | No | No |
| Coste mínimo | ITMCostTrans.MinCostAmount | Numeric(32, 6) | No | No |
| Categoría | ITMCostTrans.ShipCostCategory | Int | No | No |
| Código de tipo de coste | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | No | No |
| Empresa | ITMCostTrans.ShipDataArea | Nvarchar(4) | No | **Sí** |
| Viaje | ITMCostTrans.TransRecId | Nvarchar(20) | **Sí** | No |
| Grupo de impuestos de artículos | ITMCostTrans.TaxItemGroup | Nvarchar(10) | No | No |

## <a name="shipping-container-costs-itmcosttransshippingcontainerentity"></a>Costes del contenedor de envío (ITMCostTransShippingContainerEntity)

La entidad de coste del contenedor de envío (`ITMCostTransShippingContainerEntity`) crea costes de contenedor de envío que se aplican en el nivel de contenedor de envío. Durante el proceso de importación, el sistema utiliza los valores **Categoría** y **Método de reparto** que se incluyen en la entidad para determinar cómo se distribuye el valor del coste entre los contenidos del contenedor de envío.

Los campos **Agregado**, **Sección**, y **Sección enlazada** son específicos de los registros en los que el valor del **Área de coste** el valor es *Contenedor de envío*. Por lo tanto, no están presentes en entidades de datos para otras áreas de costes.

| Name | Asignación | Tipo de datos | Clave | Obligatoria |
|---|---|---|---|---|
| Agregado | ITMCostTrans.AggregatedCost | Int | No | No |
| Método de reparto | ITMCostTrans.ApportionmentMethod | Int | No | No |
| Valor de coste | ITMCostTrans.CostValue | Numeric(32, 6) | No | No |
| Divisa | ITMCostTrans.CurrencyCode | Nvarchar(3) | No | **Sí** |
| Número de línea | ITMCostTrans.LineNum | Numeric(32, 16) | **Sí** | No |
| Tipo de coste vinculado | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | No | No |
| Escala vinculada | ITMCostTrans.LinkLegId | Nvarchar(20) | No | No |
| Coste mínimo | ITMCostTrans.MinCostAmount | Numeric(32, 6) | No | No |
| Contenedor de envío | ITMCostTrans.TransRecId | Nvarchar(20) | **Sí** | No |
| Categoría | ITMCostTrans.ShipCostCategory | Int | No | No |
| Código de tipo de coste | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | No | No |
| Empresa | ITMCostTrans.ShipDataArea | Nvarchar(4) | No | **Sí** |
| Viaje | ITMCostTrans.TransRecId | Nvarchar(20) | **Sí** | No |
| Escala | ITMCostTrans.ShipLegId | Nvarchar(20) | No | No |
| Grupo de impuestos de artículos | ITMCostTrans.TaxItemGroup | Nvarchar(10) | No | No |

## <a name="folio-costs-itmcosttransfolioentity"></a>Costes de folio (ITMCostTransFolioEntity)

La entidad de coste del folio (`ITMCostTransFolioEntity`) crea registros de transacciones de costos que se aplican al nivel de folio. Durante el proceso de importación, el sistema utiliza los valores **Categoría** y **Método de reparto** que se incluyen en la entidad para determinar cómo se distribuye el valor del coste entre los contenidos de cada folio.

| Name | Asignación | Tipo de datos | Clave | Obligatoria |
|---|---|---|---|---|
| Método de reparto | ITMCostTrans.ApportionmentMethod | Int | No | No |
| Valor de coste | ITMCostTrans.CostValue | Numeric(32, 6) | No | No |
| Divisa | ITMCostTrans.CurrencyCode | Nvarchar(3) | No | **Sí** |
| Número de línea | ITMCostTrans.LineNum | Numeric(32, 16) | **Sí** | No |
| Tipo de coste vinculado | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | No | No |
| Coste mínimo | ITMCostTrans.MinCostAmount | Numeric(32, 6) | No | No |
| Categoría | ITMCostTrans.ShipCostCategory | Int | No | No |
| Código de tipo de coste | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | No | No |
| Empresa | ITMCostTrans.ShipDataArea | Nvarchar(4) | No | **Sí** |
| Folio | ITMCostTrans.TransRecId | Nvarchar(20) | **Sí** | No |
| Grupo de impuestos de artículos | ITMCostTrans.TaxItemGroup | Nvarchar(10) | No | No |

## <a name="purchase-order-costs-itmcosttranspurchaseentity"></a>Costes de pedido de compra (ITMCostTransPurchaseEntity)

La entidad de costo del pedido de compra (`ITMCostTransPurchaseEntity`) crea transacciones de costes que se aplican al encabezado de la orden de compra. Durante el proceso de importación, el sistema utiliza los valores **Categoría** y **Método de reparto** que se incluyen en la entidad para determinar cómo se distribuye el valor del coste entre los contenidos de cada folio.

| Name | Asignación | Tipo de datos | Clave | Obligatoria |
|---|---|---|---|---|
| Método de reparto | ITMCostTrans.ApportionmentMethod | Int | No | No |
| Valor de coste | ITMCostTrans.CostValue | Numeric(32, 6) | No | No |
| Divisa | ITMCostTrans.CurrencyCode | Nvarchar(3) | No | **Sí** |
| Número de línea | ITMCostTrans.LineNum | Numeric(32, 16) | **Sí** | No |
| Tipo de coste vinculado | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | No | No |
| Coste mínimo | ITMCostTrans.MinCostAmount | Numeric(32, 6) | No | No |
| Pedido de compra | ITMCostTrans.TransRecId | Nvarchar(20) | **Sí** | No |
| Categoría | ITMCostTrans.ShipCostCategory | Int | No | No |
| Código de tipo de coste | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | No | No |
| Empresa | ITMCostTrans.ShipDataArea | Nvarchar(4) | No | **Sí** |
| Grupo de impuestos de artículos | ITMCostTrans.TaxItemGroup | Nvarchar(10) | No | No |

## <a name="item-costs-itmcosttransitementity"></a>Costes de artículos (ITMCostTransItemEntity)

La entidad de coste del artículo (`ITMCostTransItemEntity`) crea costes de transacciones de costos que se aplican al nivel de artículo. Esta entidad es específica para artículos en líneas de pedido de compra. El valor del costo se aplica en su totalidad a la línea.

Los campos **Cantidad de ajuste** y **Ajuste de valor** son específicos de las áreas de coste de nivel de línea. Por lo tanto, no están presentes en entidades de datos para otras áreas de costes.

| Name | Asignación | Tipo de datos | Clave | Obligatoria |
|---|---|---|---|---|
| Importe del ajuste | ITMCostTrans.AdjustmentAmount | Numeric(32, 6) | No | No |
| Valor de coste | ITMCostTrans.CostValue | Numeric(32, 6) | No | No |
| Divisa | ITMCostTrans.CurrencyCode | Nvarchar(3) | No | **Sí** |
| Número de línea | ITMCostTrans.LineNum | Numeric(32, 16) | **Sí** | No |
| Tipo de coste vinculado | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | No | No |
| Coste mínimo | ITMCostTrans.MinCostAmount | Numeric(32, 6) | No | No |
| Pedido de compra | ITMCostTrans.TransRecId | Nvarchar(20) | **Sí** | No |
| Número de línea de pedido de compra | ITMCostTrans.TransRecId | Nvarchar(20) | **Sí** | No |
| Categoría | ITMCostTrans.ShipCostCategory | Int | No | No |
| Código de tipo de coste | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | No | No |
| Empresa | ITMCostTrans.ShipDataArea | Nvarchar(4) | No | **Sí** |
| Grupo de impuestos de artículos | ITMCostTrans.TaxItemGroup | Nvarchar(10) | No | No |
| Ajuste de valor | ITMCostTrans.ValueAdjustmentMethod | Int | No | No |

## <a name="transfer-line-costs-itmcosttranstransferlineentity"></a>Costes de línea de transferencia (ITMCostTransTransferLineEntity)

La entidad de coste de la línea de transferencia (`ITMCostTransTransferLineEntity`) crea transacciones de coste que se aplican al nivel de línea de orden de transferencia. El valor de estos costes se aplica en su totalidad a la línea de transferencia de pedido.

Los campos **Cantidad de ajuste** y **Ajuste de valor** son específicos de las áreas de coste de nivel de línea. Por lo tanto, no están presentes en entidades de datos para otras áreas de costes.

| Name | Asignación | Tipo de datos | Clave | Obligatoria |
|---|---|---|---|---|
| Importe del ajuste | ITMCostTrans.AdjustmentAmount | Numeric(32, 6) | No | No |
| Valor de coste | ITMCostTrans.CostValue | Numeric(32, 6) | No | No |
| Divisa | ITMCostTrans.CurrencyCode | Nvarchar(3) | No | **Sí** |
| Número de línea | ITMCostTrans.LineNum | Numeric(32, 16) | **Sí** | No |
| Tipo de coste vinculado | ITMCostTrans.LinkCostTypeId | Nvarchar(20) | No | No |
| Coste mínimo | ITMCostTrans.MinCostAmount | Numeric(32, 6) | No | No |
| Categoría | ITMCostTrans.ShipCostCategory | Int | No | No |
| Código de tipo de coste | ITMCostTrans.ShipCostTypeId | Nvarchar(20) | No | No |
| Empresa | ITMCostTrans.ShipDataArea | Nvarchar(4) | No | **Sí** |
| Pedido de transferencia | ITMCostTrans.TransRecId | Nvarchar(20) | **Sí** | No |
| Número de línea de pedido de transferencia | ITMCostTrans.TransRecId | Nvarchar(20) | **Sí** | No |
| Grupo de impuestos de artículos | ITMCostTrans.TaxItemGroup | Nvarchar(10) | No | No |
| Ajuste de valor | ITMCostTrans.ValueAdjustmentMethod | Int | No | No |

### <a name="transaction-table"></a>Tabla de transacciones

Un registro de transacción de costes se asocia con un área de costes a través de la asignación de un número de tabla de transacciones (`TransTableId`). Cuando se requieren números de identificación de tabla específicos, las entidades se dividen en función de estos valores, de modo que exista una entidad para cada área de costos.

El valor de la tabla de transacciones (`TransTableId`) está implícito en la selección de la entidad de transacción de coste.

### <a name="calculated-fields"></a>Campos calculados

Los siguientes campos no están disponibles para insertar o actualizar cuando se usa una entidad de transacción de coste, porque estos campos se configuran solo cuando se toman acciones específicas en el registro de viaje:

- **Coste estimado** – Este campo se establece cuando se contabiliza una factura por el viaje (pedido de compra) o se recibe una transferencia.
- **Coste estimado en moneda** – Este campo se establece cuando se contabiliza una factura por el viaje (pedido de compra) o se recibe una transferencia.
- **Coste real** – Este campo se establece cuando se contabiliza una factura de proveedor. Está asociado con el coste.

### <a name="find-auto-costs"></a>Buscar costes automáticos

Un botón **Encontrar costes automáticos** está disponible para cada área de costes (viaje, contenedor de envío, etc.) ofrece una forma de actualizar las transacciones de costes para esa área de costos a partir de la información en las tablas de configuración. Cuando selecciona el botón para un área de costes, el sistema borra los costes existentes para esa área de costos y crea nuevos registros, según la configuración actual de las tablas de configuración automática de costos.

Los registros de transacciones de costes que se crean mediante el uso de una entidad de datos se marcan como importados. Estos registros no se eliminan cuando selecciona **Encuentre costos de automóviles**, porque no se volverán a crear a partir de las tablas de configuración automática de costos. Sin embargo, aún se puede eliminar un registro de transacción de coste que está marcado como importado.

### <a name="linked-fields"></a>Campos vinculados

Cada transacción de coste se puede asociar con otro registro en la misma área de coste. Esta asociación se constituye a través del campo **Tipo de coste vinculado**. Permite calcular el valor de un coste como un porcentaje de otro coste.

El campo **Tipo de coste vinculado** se puede validar solo si el registro al que se hace referencia se procesa primero o si ya existe en la tabla. El mismo requisito se aplica al campo **Sección enlazada** que se utiliza para los costos en el área de costos del contenedor de envío solamente.
