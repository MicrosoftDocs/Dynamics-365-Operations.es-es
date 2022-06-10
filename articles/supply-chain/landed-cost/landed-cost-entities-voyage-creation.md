---
title: Entidades de creación de viajes
description: Este tema proporciona información sobre las entidades de datos de creación de viajes, que agrupan las entidades de datos necesarias para crear un viaje de trabajo.
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
ms.openlocfilehash: 17f63af3ce1f858ed3e2086fc81c5e17c5e76be0
ms.sourcegitcommit: 611202adaa080250636efabb3b3b32b850d92d04
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2022
ms.locfileid: "8813132"
---
# <a name="voyage-creation-entities"></a>Entidades de creación de viajes

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]
<!-- KFM: Preview until GA with 10.0.28 -->

Las entidades de datos de creación de viajes agrupan las entidades de datos necesarias para crear un viaje de trabajo. Usted o su transitario pueden usar estas entidades de datos para crear registros de viaje, contenedor de envío, folio y línea de viaje que hagan referencia a órdenes de compra existentes o líneas de órdenes de transferencia.

## <a name="voyages-itmtableentity"></a>Viajes (ITMTableEntity)

El viaje representa el viaje de las mercancías entrantes y sirve como el área de costo de nivel más alto en el costo de destino. Contiene información a nivel de encabezado relacionada con la embarcación, el puerto de origen y el puerto de destino. Esta función es soportada por la entidad `ITMTableEntity`. La siguiente tabla enumera los campos y las asignaciones que componen esta entidad.

| Name | Asignación | Tipo de datos | Clave | Obligatoria |
|---|---|---|---|---|
| Modo de entrega | ITMTable.DlvModeId | Nvarchar(10) | No | No |
| Con recomendación del agente | ITMTable.ITMBrokerAdvised | Fecha y hora | No | No |
| Cita del cliente | ITMTable.ITMCustomerAppointment | Fecha y hora | No | No |
| Entregado en almacén | ITMTable.ITMDelAtWarehouse | Fecha y hora | No | No |
| Instrucciones de entrega | ITMTable.ITMDeliveryInstructions | Fecha y hora | No | No |
| Fecha de salida | ITMTable.ITMDepartureDate | Fecha y hora | No | No |
| Mercancías liberadas | ITMTable.ITMGoodsReleased | Fecha y hora | No | No |
| Fecha de transporte local | ITMTable.ITMLocalTransportDate | Fecha y hora | No | No |
| Hora de transporte local | ITMTable.ITMLocalTransportTime | Int | No | No |
| Estado de desembarque original enviado | ITMTable.ITMOriginalBOLSebt | Fecha y hora | No | No |
| Documentos originales recibidos | ITMTable.ITMOriginalDocsReceived | Fecha y hora | No | No |
| Estado de pedido de compra | ITMTable.ITMPurchStatus | Int | No | No |
| Fecha de verificación | ITMTable.ITMVerificationDate | Fecha y hora | No | No |
| Identificador de entrada de aduanas | ITMTable.ShipCustomsEntryId | Nvarchar(20) | No | No |
| Fecha de envío | ITMTable.ShipDate | Fecha y hora | No | No |
| Description | ITMTable.ShipDescription | Nvarchar(60) | No | No |
| Documentos recibidos | ITMTable.ShipDocReceived | Int | No | No |
| Fecha de entrega estimada | ITMTable.ShipEstDlvDate | Fecha y hora | No | No |
| Hora de llegada estimada en puerto de envío | ITMTable.ShipEstPortDate | Fecha y hora | No | No |
| Puerto de origen | ITMTable.ShipFromPort | Nvarchar(20) | No | No |
| Hoja de ruta aérea/Conocimiento de embarque | ITMTable.ShipHAWB | Nvarchar(20) | No | No |
| Viaje | ITMTable.ShipId | Nvarchar(20) | **Sí** | **Sí** |
| Referencia de reserva | ITMTable.ShipIdExternal | Nvarchar(20) | No | No |
| Plantilla de recorrido | ITMTable.ShipJourneyId | Nvarchar(20) | No | No |
| Transitario local | ITMTable.ShipLocalForwarder | Nvarchar(20) | No | No |
| Hoja de ruta aérea/Conocimiento de embarque | ITMTable.ShipMAWB | Nvarchar(20) | No | No |
| Medida | ITMTable.ShipMeasurement | Numeric(32, 6) | No | No |
| Unidad de medida | ITMTable.ShipMeasurementUnit | Int | No | No |
| Número de pallets | ITMTable.ShipNoOfPallets | Int | No | No |
| Viaje pendiente | ITMTable.ShipPending | Int | No | No |
| Comentarios | ITMTable.ShipRemarks | Nvarchar(MAX) | No | No |
| Alquiler | ITMTable.ShipRental | Int | No | No |
| Estado de viaje | ITMTable.ShipStatusId | Nvarchar(20) | No | No |
| Recuento en número | ITMTable.ShipTallyInNumber | Nvarchar(20) | No | No |
| Puerto de destino | ITMTable.ShipToPort | Nvarchar(20) | No | No |
| Fecha de valorización | ITMTable.ShipValuationDate | Fecha y hora | No | No |
| Empresa de transporte | ITMTable.ShipVendAccount | Nvarchar(20) | No | No |
| Embarcación | ITMTable.ShipVesselId | Nvarchar(20) | No | **Sí** |
| Id. de viaje externo | ITMTable.ShipVoyage | Nvarchar(20) | No | No |

### <a name="number-sequences-for-voyages"></a>Secuencias numéricas para viajes

La secuencia de números compartidos para viajes controla la asignación de ID de viaje.

El valor que se pasa a la entidad de datos como el **Identificador de viaje** (`ShipId`) se utiliza para identificar un registro existente para su actualización. Si ese registro no existe, el comportamiento depende de si la secuencia numérica asignada está configurada para permitir la entrada manual:

- Si la entrada manual está habilitada, se crea un nuevo registro que usa el valor pasado.
- Si la entrada manual no está habilitada, se usa el siguiente número en la secuencia numérica asignada en lugar del valor pasado.

Durante la sesión de importación, se conserva el valor de marcador de posición que se importa como identificador de viaje. Este comportamiento garantiza que el contenedor de envío y las líneas de viaje que hacen referencia al marcador de posición se incluyan en el viaje y que se actualicen para reflejar el valor asignado de la secuencia numérica.

### <a name="automatic-cost-transactions"></a>Transacciones de costes automáticos

Los costes automáticos se pueden añadir a un viaje desde la página **Costes automáticos** en Microsoft Dynamics 365 Supply Chain Management (**Coste descargado \> Configuración de costes \> Costes automáticos**). Los registros de costes automáticos también se pueden crear mediante el uso de entidades de datos de transacciones de costes para cada área de costo que admita el coste adicional.

Los costes automáticos que se configuran en Supply Chain Management se aplican al viaje cuando se crea una línea de viaje. Ningún costo será visible en el registro hasta que el registro de encabezado esté asociado con la información de la línea.

## <a name="shipping-containers-itmcontainersentity"></a>Contenedores de envío (ITMContainersEntity)

Un contenedor de envío representa un contenedor físico en el que se transportan mercancías. Este contenedor físico puede ser un contenedor de carga para transporte marítimo o un palé individual para transporte aéreo. El contenedor de envío incluye información a nivel de encabezado relacionada con el identificador del contenedor de envío, el número de sello y el tipo de contenedor de envío. (El tipo de contenedor de envío proporciona información sobre las dimensiones). Esta funcionalidad es compatible con la entidad `ITMContainersEntity`. La siguiente tabla enumera los campos y las asignaciones que componen esta entidad.

| Name | Asignación | Tipo de datos | Clave | Obligatoria |
|---|---|---|---|---|
| Fecha de salida | ITMContainers.ITMDepartureDate | Fecha y hora | No | No |
| Fecha de transporte local | ITMContainers.ITMLocalTransportDate | Fecha y hora | No | No |
| Hora de transporte local | ITMContainers.ITMLocalTransportTime | Int | No | No |
| Viaje original | ITMContainers.OrigShipId | Nvarchar(20) | No | No |
| Peso real | ITMContainers.ShipActualWeight | Numeric(32, 6) | No | No |
| Con recomendación del agente | ITMContainers.ShipBrokerAdvised | Fecha y hora | No | No |
| Contenedor de envío | ITMContainers.ShipContainerId | Nvarchar(20) | **Sí** | **Sí** |
| Tipo de contenedor de envío | ITMContainers.ShipContainerTypeId | Nvarchar(20) | No | No |
| Tipo de unidad | ITMContainers.ShipContainerUnitTypeId | Nvarchar(10) | No | No |
| Convertido en alquiler | ITMContainers.ShipConvertedToRental | Int | No | No |
| Cita del cliente | ITMContainers.ShipCustomerAppointment | Fecha y hora | No | No |
| Fecha de envío | ITMContainers.ShipDate | Fecha y hora | No | No |
| Entregado en almacén | ITMContainers.ShipDelAtWarehouse | Fecha y hora | No | No |
| Instrucciones de entrega | ITMContainers.ShipDeliveryInstructions | Fecha y hora | No | No |
| Fecha de aplicación de certificado de examen | ITMContainers.ShipECAppliedDate | Fecha y hora | No | No |
| Fecha de vencimiento de certificado de examen | ITMContainers.ShipECExpiryDate | Fecha y hora | No | No |
| Número de certificado de examen | ITMContainers.ShipECNum | Nvarchar(20) | No | No |
| Fecha de recepción del certificado de examen | ITMContainers.ShipECReceivedDate | Fecha y hora | No | No |
| Fecha de entrega estimada | ITMContainers.ShipEstDlvDate | Fecha y hora | No | No |
| Hora de llegada estimada en puerto de envío | ITMContainers.ShipEstPortDate | Fecha y hora | No | No |
| Fecha de carga esperada | ITMContainers.ShipExpectedLoadingDate | Fecha y hora | No | No |
| Puerto de origen | ITMContainers.ShipFromPort | Nvarchar(20) | No | No |
| Descripción de los bienes | ITMContainers.ShipGoodsDesc | Nvarchar(60) | No | No |
| Mercancías liberadas | ITMContainers.ShipGoodsReleased | Fecha y hora | No | No |
| Unidad de seguimiento GPS | ITMContainers.ShipGPSUnit | Nvarchar(30) | No | No |
| Hoja de ruta aérea/Conocimiento de embarque | ITMContainers.ShipHAWB | Nvarchar(20) | No | No |
| Viaje | ITMContainers.ShipId | Nvarchar(20) | **Sí** | **Sí** |
| Plantilla de recorrido | ITMContainers.ShipJourneyId | Nvarchar(20) | No | No |
| Transitario local | ITMContainers.ShipLocalForwarder | Nvarchar(20) | No | No |
| Medida | ITMContainers.ShipMeasurement | Numeric(32, 6) | No | No |
| Unidad de medida | ITMContainers.ShipMeasurementUnit | Int | No | No |
| Número de cajas | ITMContainers.ShipNoOfCartons | Numeric(32, 6) | No | No |
| Estado de desembarque original enviado | ITMContainers.ShipOriginalBOLSebt | Fecha y hora | No | No |
| Documentos originales recibidos | ITMContainers.ShipOriginalDocsReceived | Fecha y hora | No | No |
| Nuestro número de sello | ITMContainers.ShipOurSealNum | Nvarchar(20) | No | No |
| Utilizado | ITMContainers.ShipPendingUsed | Int | No | No |
| Estado de pedido de compra | ITMContainers.ShipPurchStatus | Int | No | No |
| Tipo de refrigeración | ITMContainers.ShipRefrigerationTypeId | Nvarchar(10) | No | No |
| Comentarios | ITMContainers.ShipRemarks | Nvarchar(MAX) | No | No |
| Alquiler | ITMContainers.ShipRental | Int | No | No |
| Retornable | ITMContainers.ShipReturnable | Int | No | No |
| Estado de viaje | ITMContainers.ShipStatusId | Nvarchar(20) | No | No |
| Número de sello de la empresa de transporte | ITMContainers.ShipTheirSealNum | Nvarchar(20) | No | No |
| Puerto de destino | ITMContainers.ShipToPort | Nvarchar(20) | No | No |
| Fecha de verificación | ITMContainers.ShipVerificationDate | Fecha y hora | No | No |
| Embarcación | ITMContainers.ShipVesselId | Nvarchar(20) | No | **Sí** |

### <a name="voyage-id-validation"></a>Validación de Id. de viaje

La identificación del contenedor de envío no está controlada por una secuencia numérica. Es único solo en el contexto del viaje en el que se usa.

Si la entidad del contenedor de envío (`ITMContainersEntity`) se utiliza independientemente de la entidad del viaje (`ITMTableEntity`), el valor del **Id. de viaje** (`ShipId`) debe coincidir con un registro existente en la tabla de viajes. De lo contrario, la importación fallará.

Si la entidad del contenedor de envío (`ITMContainersEntity`) y la entidad de viaje (`ITMTableEntity`) se utilizan como parte de la misma sesión de importación, la entidad de viaje debe preceder a la creación de un contenedor de envío. De lo contrario, el valor del **Id. de viaje** (`ShipId`) no se puede validar correctamente. Si se utiliza un valor de marcador de posición para el valor del **Id. de viaje** (`ShipId`), la asociación solo se puede crear si se utiliza el mismo marcador de posición que el valor del **Id. de viaje** (`ShipId`) en la entidad del contenedor de envío.

### <a name="other-field-validations"></a>Otras validaciones de campos

La siguiente tabla muestra los campos en la tabla de contenedores de envío (`ITMContainers`) que se validan con las tablas de configuración de costos de envío. También muestra las entidades de datos de costos de destino que un transitario puede usar para leer los valores existentes y garantizar que se reciban valores válidos en su entorno.

| Campo en la tabla ITMCointainers | Entidad de datos de costos descargados |
|---|---|
| Tipo de contenedor de envío | ITMShippingContainerTypeEntity |
| Descripción de los bienes | ITMGoodsDescriptionEntity |
| Tipo de refrigeración | ITMShippingContainerRefrigerationTypeEntity |

## <a name="folios-itmfolioentity"></a>Folios (ITMFolioEntity)

Un folio representa una agrupación de artículos en un contenedor de envío a efectos de las declaraciones de aduana. El folio incluye información a nivel de encabezado que está relacionada con el agente de aduanas y una descripción de las mercancías. Esta función es soportada por la entidad `ITMFolioEntity`. La siguiente tabla enumera los campos y las asignaciones que componen esta entidad.

| Name | Asignación | Tipo de datos | Clave | Obligatoria |
|---|---|---|---|---|
| Con recomendación del agente | ITMFolioTable.ShipBrokerAdvised | Fecha y hora | No | No |
| Número de control de carga | ITMFolioTable.ShipCargoControlNumber | Nvarchar(20) | No | No |
| Cita del cliente | ITMFolioTable.ShipCustomerAppointment | Fecha y hora | No | No |
| Agente de aduanas | ITMFolioTable.ShipCustomsBroker | Nvarchar(20) | No | No |
| Id. de aduanas | ITMFolioTable.ShipCustomsId | Nvarchar(60) | No | No |
| Empresa | ITMFolioTable.ShipDataArea | Nvarchar(4) | No | **Sí** |
| Entregado en almacén | ITMFolioTable.ShipDelAtWarehouse | Fecha y hora | No | No |
| Instrucciones de entrega | ITMFolioTable.ShipDeliveryInstructions | Fecha y hora | No | No |
| Documentos recibidos | ITMFolioTable.ShipDocReceived | Int | No | No |
| Fecha de entrega estimada | ITMFolioTable.ShipEstDlvDate | Fecha y hora | No | No |
| Hora de llegada estimada en puerto de envío | ITMFolioTable.ShipEstPortDate | Fecha y hora | No | No |
| Exportador | ITMFolioTable.ShipExporterId | Nvarchar(20) | No | No |
| Name | ITMFolioTable.ShipExporterName | Nvarchar(60) | No | No |
| Fecha de folio | ITMFolioTable.ShipFolioDate | Fecha y hora | No | No |
| Folio | ITMFolioTable.ShipFolioId | Nvarchar(20) | **Sí** | **Sí** |
| Puerto de origen | ITMFolioTable.ShipFromPort | Nvarchar(20) | No | No |
| Descripción de los bienes | ITMFolioTable.ShipGoodsDesc | Nvarchar(60) | No | No |
| Mercancías liberadas | ITMFolioTable.ShipGoodsReleased | Fecha y hora | No | No |
| Hoja de ruta aérea/Conocimiento de embarque | ITMFolioTable.ShipHAWB | Nvarchar(20) | No | No |
| Viaje | ITMFolioTable.ShipId | Nvarchar(20) | No | **Sí** |
| Medida | ITMFolioTable.ShipMeasurement | Numeric(32, 6) | No | No |
| Unidad de medida | ITMFolioTable.ShipMeasurementUnit | Int | No | No |
| Número de cajas | ITMFolioTable.ShipNoOfCartons | Numeric(32, 6) | No | No |
| Estado de desembarque original enviado | ITMFolioTable.ShipOriginalBOLSebt | Fecha y hora | No | No |
| Documentos originales recibidos | ITMFolioTable.ShipOriginalDocsReceived | Fecha y hora | No | No |
| Estado de pedido de compra | ITMFolioTable.ShipPurchStatus | Int | No | No |
| Comentarios | ITMFolioTable.ShipRemarks | Nvarchar(MAX) | No | No |
| Estado de viaje | ITMFolioTable.ShipStatusId | Nvarchar(20) | No | No |
| Código de tarifa | ITMFolioTable.ShipTariffCode | Nvarchar(10) | No | No |
| Puerto de destino | ITMFolioTable.ShipToPort | Nvarchar(20) | No | No |
| Fecha de valorización | ITMFolioTable.ShipValuationDate | Fecha y hora | No | No |
| Fecha de verificación | ITMFolioTable.ShipVerificationDate | Fecha y hora | No | No |
| Cuenta del proveedor | ITMFolioTable.VendAccount | Nvarchar(20) | No | No |

### <a name="number-sequences-for-folios"></a>Secuencias numéricas para folios

La secuencia de números para folios controla la asignación de identificadores de folio.

El valor que se pasa a la entidad de datos como el **Identificador de Folio** (`FolioId`) se utiliza para identificar un registro existente para su actualización. Si ese registro no existe, el comportamiento depende de si la secuencia numérica asignada está configurada para permitir la entrada manual:

- Si la entrada manual está habilitada, se crea un nuevo registro que usa el valor pasado.
- Si la entrada manual no está habilitada, se usa el siguiente número en la secuencia numérica asignada en lugar del valor pasado.

Durante la sesión de importación, se conserva el valor de marcador de posición que se importa como identificador de folio. Este comportamiento garantiza que las líneas de viaje que hacen referencia al marcador de posición se asocien correctamente y que se actualicen para reflejar el valor asignado de la secuencia numérica.

### <a name="field-validations"></a>Validaciones de campos

El campo **Descripción de los bienes** en la tabla de folio (`ITMFolioTable`) se valida con la tabla de configuración de costos de entrega del mismo nombre. Un transitario puede usar la entidad de datos de costes recibidos `ITMGoodsDescriptionEntity` para leer los valores existentes y garantizar que se reciban valores válidos en su entorno.

## <a name="voyage-lines-for-purchase-orders-itmpurchaselineentity"></a>Líneas de viaje para pedidos de compra (ITMPurchaseLineEntity)

La línea de viaje representa una sola línea de orden de compra que se incluye en el viaje. Esta relación se establece a través de los campos **Número de orden de compra** y **Número de línea de compra**. La línea de viaje hace referencia a cada registro anterior que se creó para el viaje, el contenedor de envío y el folio. Esta función es soportada por la entidad `ITMPurchaseLineEntity`. La siguiente tabla enumera los campos y las asignaciones que componen esta entidad.

| Name | Asignación | Tipo de datos | Clave | Obligatoria |
|---|---|---|---|---|
| Divisa | ITMLine.CurrencyCode | Nvarchar(3) | No | No |
| Importe neto | ITMLine.LineAmountMST | Numeric(32, 6) | No | No |
| Número de línea de compra | ITMLine.RefRecId | Numeric(32, 6) | **Sí** | No |
| Contenedor de envío | ITMLine.ShipContainerId | Int | No | No |
| Empresa | ITMLine.ShipDataArea | Nvarchar(20) | **Sí** | No |
| Cantidad declarada | ITMLine.ShipDeclaredQty | Nvarchar(4) | No | No |
| Folio | ITMLine.ShipFolioId | Numeric(32, 6) | No | No |
| Viaje | ITMLine.ShipId | Nvarchar(20) | **Sí** | No |
| Número de artículo | ITMLine.ShipItemId | Nvarchar(20) | No | No |
| Medida | ITMLine.ShipMeasurement | Nvarchar(20) | No | No |
| Unidad de medida | ITMLine.ShipMeasurementUnit | Numeric(32, 6) | No | No |
| Número de cajas | ITMLine.ShipNoOfCartons | Int | No | No |
| Trabajo | ITMLine.ShipPosition | Numeric(32, 6) | No | No |
| Quantity | ITMLine.ShipQty | Int | No | No |
| Número de pedido de compra | ITMLine.TransRefId | Numeric(32, 6) | **Sí** | No |
| Unidad | ITMLine.UnitId | Int | No | No |
| Volumen | ITMLine.Volume | Nvarchar(10) | No | No |
| Importancia | ITMLine.Weight | Numeric(32, 6) | No | No |

## <a name="voyage-lines-for-transfer-orders-itmtransferlineentity"></a>Líneas de viaje para órdenes de transferencia (ITMTransferLineEntity)

La línea de viaje representa una sola línea de orden de transferencia que se incluye en el viaje. Esta relación se establece a través de los campos **Número de orden de transferencia** y **Número de línea de transferencia**. La línea de viaje hace referencia a cada registro anterior que se creó para el viaje, el contenedor de envío y el folio. Esta función es soportada por la entidad `ITMTransferLineEntity`. La siguiente tabla enumera los campos y las asignaciones que componen esta entidad.

| Name | Asignación | Tipo de datos | Clave | Obligatoria |
|---|---|---|---|---|
| Divisa | ITMLine.CurrencyCode | Nvarchar(3) | No | No |
| Importe neto | ITMLine.LineAmountMST | Numeric(32, 6) | No | No |
| Contenedor de envío | ITMLine.ShipContainerId | Int | No | No |
| Empresa | ITMLine.ShipDataArea | Nvarchar(20) | **Sí** | No |
| Cantidad declarada | ITMLine.ShipDeclaredQty | Nvarchar(4) | No | No |
| Folio | ITMLine.ShipFolioId | Numeric(32, 6) | No | No |
| Viaje | ITMLine.ShipId | Nvarchar(20) | **Sí** | No |
| Número de artículo | ITMLine.ShipItemId | Nvarchar(20) | No | No |
| Medida | ITMLine.ShipMeasurement | Nvarchar(20) | No | No |
| Unidad de medida | ITMLine.ShipMeasurementUnit | Numeric(32, 6) | No | No |
| Número de cajas | ITMLine.ShipNoOfCartons | Int | No | No |
| Trabajo | ITMLine.ShipPosition | Numeric(32, 6) | No | No |
| Quantity | ITMLine.ShipQty | Int | No | No |
| Número de línea de transferencia | ITMLine.TransferLineNumber | Numeric(32, 6) | **Sí** | No |
| Número de pedido de transferencia | ITMLine.TransRefId | Numeric(32, 6) | **Sí** | No |
| Unidad | ITMLine.UnitId | Int | No | No |
| Volumen | ITMLine.Volume | Nvarchar(10) | No | No |
| Importancia | ITMLine.Weight | Numeric(32, 6) | No | No |

### <a name="reference-table"></a>Tabla de referencia

Las líneas de viaje se crean a través de una asociación con una línea de orden de entrada abierta. Esta línea puede estar en una orden de compra o puede ser la transacción de recepción en una orden de transferencia. El campo `RefTableId` en la tabla de líneas de viaje (`ITMLine`) especifica con qué tipo de orden está relacionada la línea haciendo referencia al número de tabla. Si se hace referencia a números de tabla específicos en la tabla donde se crean los datos, las entidades se dividen en función de esos valores.

Los valores de la tabla de referencia (`RefTableId`) y el tipo de transacción (`TransType`) están implícitos en la selección de la entidad de línea de compra de costo descargado o la entidad de línea de transferencia de costo descargado.

### <a name="validation"></a>Validación

Una línea de viaje hace referencia directa a un registro de viaje, un registro de contenedor de envío y un registro de folio. Si la entidad de línea de compra (`ITMPurchaseLinesEntity`) o entidad de línea de transferencia (`ITMPurchaseLinesEntity`) se usa independientemente de las entidades que se usan para crear estos registros de referencia, los valores del **Id. de viaje** (`ShipId`), **Contenedor de envío** (`ShipContainerId`), y **Folio** (`ShipFolioId`) deben coincidir con un registro existente en las tablas correspondientes. De lo contrario, la importación fallará.

Si cualquiera de las entidades de línea se utiliza como parte de la misma sesión de importación, esas otras entidades deben preceder a la creación de una línea de viaje. De lo contrario, los valores no se pueden validar correctamente. Si se utiliza un valor de marcador de posición para el número de viaje o folio, la asociación solo se puede crear si se utiliza el mismo marcador de posición para el viaje o número de folio en la entidad de línea del viaje.

Si la orden de compra o la línea de orden de transferencia ya está asignada a una línea de viaje existente, no se creará la nueva línea de viaje. Antes de que la línea de pedido pueda asignarse a un nuevo viaje, debe eliminarse de su viaje actual.

### <a name="order-line-identification"></a>Identificación de línea de pedido

Las líneas de viaje hacen referencia directa a la referencia de los valores **Identificación de registro** (`RefRecId`), **Identificador de dimensión de inventario** (`InventDimId`), e **Identificador de transacción de inventario** (`InventTransId`). Estos valores ya no tienen que incluirse cuando se utiliza la entidad de datos. En su lugar, ahora se debe incluir el número de línea del pedido. Juntos, el número de línea de pedido y el número de pedido permiten identificar cada uno de esos valores de referencia.

### <a name="voyage-line-quantity"></a>Cantidad de línea de viaje

Debido a que una línea de viaje está directamente asociada con una línea de orden, el valor **Cantidad** (`ShipQty`) que se ingresa usando la entidad requiere que los valores coincidan. La validación se ejecuta contra la cantidad en la línea de pedido de compra o en la línea de transferencia. Si la validación falla, el registro no se procesará.

### <a name="calculated-fields"></a>Campos calculados

Los campos calculados **Peso** y **Volumen** aceptan los valores que se reciben a través de la entidad de datos. Si no se proporcionan valores, los valores del sistema se utilizan para actualizar estos campos, si los valores del sistema están disponibles. Para el coste descargado, los valores se calculan de la siguiente manera:

- *Peso* = *Cantidad* × *Peso bruto del artículo*
- *Volumen* = *Cantidad* × (*Profundidad bruta del artículo* × *Altura bruta del artículo* × *Anchura bruta del artículo*)

## <a name="sequencing"></a>Secuenciación

Debido a las dependencias entre las tablas, primero se debe crear el registro de viaje. La línea de viaje solo se puede crear después de que se hayan creado el viaje, el contenedor de envío y los folios.

Para crear un viaje sin advertencias de validación, el sistema debe procesar las entidades en el siguiente orden:

1. Viajes (`ITMTableEntity`)
1. Contenedores de envío (`ITMContainersEntity`)
1. Folios (`ITMFolioTableEntity`)
1. Líneas de viaje (`ITMPurchaseLinesEntity` o `ITMTransferLinesEntity`)
