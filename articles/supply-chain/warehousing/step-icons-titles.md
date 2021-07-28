---
title: Asignar iconos y títulos de paso para la aplicación móvil Warehouse Management
description: Este tema describe cómo asignar títulos e iconos de paso para flujos de tareas nuevos o personalizados para la aplicación móvil Warehouse Management.
author: MarkusFogelberg
ms.date: 05/17/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2021-05-17
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: a74847b50512d2f712e5a9a5125e520afc732591
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6344504"
---
# <a name="assign-step-icons-and-titles-for-the-warehouse-management-mobile-app"></a>Asignar iconos y títulos de paso para la aplicación móvil Warehouse Management

[!include [banner](../includes/banner.md)]

Este tema describe cómo asignar títulos de paso e iconos de paso para flujos de tareas nuevos o personalizados para la aplicación móvil Warehouse Management.

Las siguientes ilustraciones muestran cómo aparecen los títulos e iconos de pasos en la aplicación móvil Warehouse Management.

![Ejemplo de un icono de paso y un título de paso en la aplicación móvil Warehouse Management.](media/step-icon-example.png "Ejemplo de un icono de paso y un título de paso en la aplicación móvil Warehouse Management")

## <a name="turn-on-this-feature-in-your-system"></a>Activar esta función en el sistema

Antes de poder usar esta característica debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de la función:** *Configuración de usuario, iconos y títulos de pasos para la nueva aplicación de almacén*

## <a name="standard-step-ids-classes-and-icons"></a>Íconos, clases e ID de pasos estándar

Cada paso en un flujo de tareas se identifica mediante un ID de paso, y cada ID de paso tiene una clase de paso correspondiente. El icono y el título del paso se especifican en cada clase de paso.

### <a name="step-ids-and-step-classes"></a><a name="step-ids-classes"></a>ID de pasos y clases de pasos

La siguiente tabla enumera cada ID de paso que está disponible actualmente y su clase de paso correspondiente. El nombre de control del campo de entrada principal se utiliza como ID de paso.

Para ver un ejemplo que muestra cómo se utilizan estas clases y ID de pasos, consulte la implementación del método `WHSMobileAppStepInfoBuilder.stepId()` en la sección [Ejemplo: asignar iconos y títulos de paso para un flujo personalizado](#example) más adelante en este tema.

| Id. del paso | Clase de paso |
|-|-|
| BatchDisposition | WHSMobileAppStepBatchDisposition |
| Transportista | WHSMobileAppStepCarrier |
| CatchWeight | WHSMobileAppStepCatchWeight |
| CatchWeightQtyOutboundWeight | WHSMobileAppStepCatchWeight |
| CatchWeightTag | WHSMobileAppStepCatchWeightTag |
| CatchWeightTagWeight | WHSMobileAppStepCatchWeightTagWeight |
| ChangeWarehouseSuccess | WHSMobileAppStepChangeWarehouseSuccess |
| CheckDigit | WHSMobileAppStepCheckDigit |
| ClusterId | WHSMobileAppStepClusterId |
| ClusterPickQtyVerification | WHSMobileAppStepQtyVerification |
| ClusterPosition | WHSMobileAppStepClusterPosition |
| ConfigId | WHSMobileAppStepConfigId |
| Confirmación | WHSMobileAppStepConfirmation |
| ConsolidateFromLicensePlateId | WHSMobileAppStepConsolidateFromLicensePlateId |
| ConsolidateLPConfirmation | WHSMobileAppStepConsolidateLPConfirmation |
| ConsolidateToLicensePlateId | WHSMobileAppStepConsolidateToLicensePlateId |
| ContainerType | WHSMobileAppStepContainerType |
| CountingReasonCode | WHSMobileAppStepCountingReasonCode |
| CycleCountingAddLPOrFinish | WHSMobileAppStepCycleCountingAddLPOrFinish |
| CycleCountQty1 | WHSMobileAppStepCycleCountQty |
| CycleCountQty2 | WHSMobileAppStepCycleCountQty |
| CycleCountQty3 | WHSMobileAppStepCycleCountQty |
| CycleCountQty4 | WHSMobileAppStepCycleCountQty |
| Disposición | WHSMobileAppStepDisposition |
| DriverCheckInConfirmation | WHSMobileAppStepDriverCheckInConfirmation |
| DriverCheckInId | WHSMobileAppStepDriverCheckInId |
| DriverCheckOutConfirmation | WHSMobileAppStepDriverCheckOutConfirmation |
| DriverCheckOutId | WHSMobileAppStepDriverCheckOutId |
| ExpDate | WHSMobileAppStepExpDate |
| FromBatchDisposition | WHSMobileAppStepFromBatchDisposition |
| FromInventoryStatus | WHSMobileAppStepInventoryStatusFrom |
| FullQty | WHSMobileAppStepFullQty |
| InboundPut | WHSMobileAppStepInboundPut |
| InventBatchId | WHSMobileAppStepBatch |
| InventColorId | WHSMobileAppStepInventColorId |
| InventLocation | WHSMobileAppStepInventLocation |
| InventLocationId | WHSMobileAppStepWarehouse |
| InventSerialId | WHSMobileAppStepInventSerialId |
| InventSizeId | WHSMobileAppStepInventSizeId |
| InventStatusId | WHSMobileAppStepInventStatus |
| InventStyleId | WHSMobileAppStepInventStyleId |
| InventVersionId | WHSMobileAppStepInventVersionId |
| ItemId | WHSMobileAppStepItem |
| ITMContainerID | ITMMobileAppStepContainerId |
| ITMShipmentID | ITMMobileAppStepShipmentId |
| KanbanCardId | WHSMobileAppStepKanbanCard |
| KanbanCardToEmpty | WHSMobileAppStepKanbanCardToEmpty |
| KanbanOrCardId | WHSMobileAppStepKanbanCard |
| LicensePlateId | WHSMobileAppStepLicensePlate |
| LoadId | WHSMobileAppStepLoadId |
| LocationLicensePlatePosition | WHSMobileAppStepLocationLicensePlatePosition |
| LocOrLP | WHSMobileAppStepLocOrLP |
| LocOrLP_From | WHSMobileAppStepLocOrLPFrom |
| LocOrLP_To | WHSMobileAppStepLocOrLPTo |
| LocOrLPCheck | WHSMobileAppStepLocOrLPCheck |
| LocVerification | WHSMobileAppStepLocVerification |
| LPAdjustIn | WHSMobileAppStepLPAdjustIn |
| LPBreakChildLP | WHSMobileAppStepLPBreakChildLP |
| LPBreakParentLP | WHSMobileAppStepLPBreakParentLP |
| LPBuildChildLP | WHSMobileAppStepLPBuildChildLP |
| LPBuildParentLP | WHSMobileAppStepLPBuildParentLP |
| LPVerification | WHSMobileAppStepLPVerification |
| MergeContainerId | WHSMobileAppStepMergeContainerId |
| MixedLPLineNum | WHSMobileAppStepMixedLPLineNum |
| MobileDeviceQueueMessageCollectionIdentifierId | WHSMobileAppStepSelectOrder |
| MovementConfirmCancel | WHSMobileAppStepMovementConfirmCancel |
| NewCaptureWeight | WHSMobileAppStepCatchWeight |
| NewQty | WHSMobileAppStepNewQty |
| OutboundCatchWeightTag | WHSMobileAppStepCatchWeightTag |
| OutboundPut | WHSMobileAppStepOutboundPut |
| OutboundWeight | WHSMobileAppStepCatchWeight |
| OverridePutNewLocation | WHSMobileAppStepOverridePutNewLocation |
| PieceByPieceConfirmation | WHSMobileAppStepQtyVerification |
| POLineNum | WHSMobileAppStepPOLineNum |
| NúmPC | WHSMobileAppStepPONum |
| PositionFull | WHSMobileAppStepPositionFull |
| PositionFullQty | WHSMobileAppStepPositionFullQty |
| Potencia | WHSMobileAppStepPotency |
| PrinterName | WHSMobileAppStepPrinterName |
| ProdId | WHSMobileAppStepProdId |
| ProdLastPalletConfirmation | WHSMobileAppStepProdLastPalletConfirmation |
| ProductConfirmation | WHSMobileAppStepProductConfirmation |
| ProductionScrapConfirmation | WHSMobileAppStepProductionScrapConfirmation |
| Colocar | WHSMobileAppStepPut |
| PutawayClusterId | WHSMobileAppStepPutawayClusterId |
| Cant. | WHSMobileAppStepQty |
| QtyAdjust | WHSMobileAppStepQtyAdjust |
| QtyShort | WHSMobileAppStepQtyShort |
| QtyToConsume | WHSMobileAppStepQtyToConsume |
| QtyToPick | WHSMobileAppStepQtyToPick |
| QtyToPut | WHSMobileAppStepQtyToPut |
| QtyToScrap | WHSMobileAppStepQtyToScrap |
| QtyVerification | WHSMobileAppStepQtyVerification |
| QtyWithScanningLimit | WHSMobileAppStepQtyAdjust |
| ReasonString | WHSMobileAppStepReasonString |
| RecvLocationId | WHSMobileAppStepRecvLocationId |
| RemoveContainerId | WHSMobileAppStepRemoveContainerId |
| ReprintLabelConfirmation | WHSMobileAppStepReprintLabelConfirmation |
| RMANum | WHSMobileAppStepRMANum |
| ShortPickReason | WHSMobileAppStepShortPickReason |
| SortConOrLP | WHSMobileAppStepSortConOrLP |
| SortLicensePlateId | WHSMobileAppStepSortLicensePlateId |
| SortPositionId | WHSMobileAppStepSortPositionId |
| SortVerification | WHSMobileAppStepSortVerification |
| StartLocationId | WHSMobileAppStepStartLocationId |
| StartProdOrderConfirmation | WHSMobileAppStepStartProdOrderConfirmation |
| TargetLicensePlateId | WHSMobileAppStepTargetLicensePlateId |
| TOLineNum | WHSMobileAppStepTOLineNum |
| ToLocation | WHSMobileAppStepToLocation |
| TONum | WHSMobileAppStepTONum |
| ToWarehouse | WHSMobileAppStepWarehouseTo |
| TransportLoadId | WHSMobileAppStepTransportLoadId |
| WaveLabelId | WHSMobileAppStepWaveLabelId |
| WaveLblQty | WHSMobileAppStepWaveLblQty |
| Importancia | WHSMobileAppStepWeight |
| WeightToConsume | WHSMobileAppStepWeightToConsume |
| WHSAdjustmentType | WHSMobileAppStepWHSAdjustmentType |
| WHSReceivingException | WHSMobileAppStepWHSReceivingException |
| WHSWorkException | WHSMobileAppStepWHSWorkException |
| WHSWorkLicensePlateId | WHSMobileAppStepWorkLicensePlateId |
| WMSLocationId | WHSMobileAppStepLocation |
| WorkId | WHSMobileAppStepWorkId |
| WorkIdToCancel | WHSMobileAppStepWorkIdToCancel |
| WorkLPIdPutawayCluster | WHSMobileAppStepWorkLPIdPutawayCluster |
| WorkPoolId | WHSMobileAppStepWorkPoolId |
| ZoneId | WHSMobileAppStepZoneId |

### <a name="available-step-icons"></a><a name="step-icons"></a>Iconos de pasos disponibles

El sistema incluye una colección de iconos de pasos estándar que también puede utilizar para sus pasos personalizados. Actualmente, no puede cargar iconos de pasos personalizados. Por lo tanto, siempre debe seleccionar uno de los iconos de pasos estándar.

La siguiente tabla muestra cada icono de paso estándar que está disponible actualmente y su nombre.

<table>
<tbody>
<tr>
<td><img src="media/step-icons-about.png" alt="About step icon" title="Acerca del icono de paso"><br>Acerca de</td>
<td><img src="media/step-icons-add-lp.png" alt="Add license plate or item step icon" title="Agregar matrícula de entidad o icono de paso de artículo"><br>AddLpOrItem</td>
<td><img src="media/step-icons-batch-disposition.png" alt="Batch disposition step icon" title="Icono de paso de disposición de lote"><br>BatchDisposition</td>
<td><img src="media/step-icons-carrier.png" alt="Carrier step icon" title="Icono de paso del operador"><br>Transportista</td>
</tr>
<tr>
<td><img src="media/step-icons-cw-tag.png" alt="Catch weight tag step icon" title="Icono de paso de etiqueta de peso de captura"><br>CatchWeightTag</td>
<td><img src="media/step-icons-cw-tag-weight.png" alt="Catch weight tag weight step icon" title="Icono de peso de paso de etiqueta de peso de captura"><br>CatchWeightTagWeight</td>
<td><img src="media/step-icons-check-digit.png" alt="Check digit step icon" title="Icono de comprobar dígito de paso"><br>CheckDigit</td>
<td><img src="media/step-icons-check-in-out.png" alt="Check in or out ID step icon" title="Icono de paso de identificación de entrada o salida"><br>CheckInOutId</td>
</tr>
<tr>
<td><img src="media/step-icons-child-lp.png" alt="Child license plate step icon" title="Icono de paso de matrícula infantil"><br>ChildLP</td>
<td><img src="media/step-icons-cluster-id.png" alt="Cluster ID step icon" title="Icono de paso de ID de clúster"><br>ClusterId</td>
<td><img src="media/step-icons-cluster-position.png" alt="Cluster position step icon" title="Icono de paso de posición de clúster"><br>ClusterPosition</td>
<td><img src="media/step-icons-config-id.png" alt="Config ID step icon" title="Icono de paso de ID de configuración"><br>ConfigId</td>
</tr>
<tr>
<td><img src="media/step-icons-configured-field.png" alt="Configured field step icon" title="Icono de paso de campo configurado"><br>ConfiguredField</td>
<td><img src="media/step-icons-con-lp.png" alt="Con or LP step icon" title="Icono de paso con o LP"><br>ConOrLP</td>
<td><img src="media/step-icons-consolidate-from-LP.png" alt="Consolidate from license plate ID step icon" title="Icono de paso consolidar desde identificador de matrícula de entidad"><br>ConsolidateFromLicensePlateID</td>
<td><img src="media/step-icons-consolidate-to-LP.png" alt="Consolidate to license plate ID step icon" title="Icono de paso consolidar a identificador de matrícula de entidad"><br>ConsolidateToLicensePlateID</td>
</tr>
<tr>
<td><img src="media/step-icons-container-type.png" alt="Container type step icon" title="Icono de paso de tipo de contenedor"><br>ContainerType</td>
<td><img src="media/step-icons-counting.png" alt="Counting step icon" title="Icono de paso contando"><br>Recuento</td>
<td><img src="media/step-icons-counting-reason.png" alt="Counting reason code step icon" title="Icono de paso contando código de razón"><br>CountingReasonCode</td>
<td><img src="media/step-icons-country-origin.png" alt="Country of origin code step icon" title="Icono de paso de código de país de origen"><br>CountryOfOrigin</td>
</tr>
<tr>
<td><img src="media/step-icons-disposition.png" alt="Disposition step icon" title="Icono de paso de disposición"><br>Disposición</td>
<td><img src="media/step-icons-done.png" alt="Done step icon" title="Icono de paso hecho"><br>Hecho</td>
<td><img src="media/step-icons-driver-check-in-confirmation.png" alt="Driver check in confirmation step icon" title="Icono de paso de confirmación de registro de conductor"><br>DriverCheckInConfirmation</td>
<td><img src="media/step-icons-driver-check-in-id.png" alt="Driver check in ID step icon" title="Icono de paso de identificación de registro de conductor"><br>DriverCheckInId</td>
</tr>
<tr>
<td><img src="media/step-icons-driver-check-out-id.png" alt="Driver check out ID step icon" title="Icono de paso de identificación de registro de salida de conductor"><br>DriverCheckOutId</td>
<td><img src="media/step-icons-exp-date.png" alt="Expiration date step icon" title="Icono de paso de fecha de vencimiento"><br>ExpDate</td>
<td><img src="media/step-icons-field.png" alt="Field step icon" title="Icono de paso de campo"><br>Campo</td>
<td><img src="media/step-icons-from-batch.png" alt="From batch disposition step icon" title="Icono de paso de desde disposición de lote"><br>FromBatchDisposition</td>
</tr>
<tr>
<td><img src="media/step-icons-from-inventory-status.png" alt="From inventory status step icon" title="Icono de paso desde estado de inventario"><br>FromInventoryStatus</td>
<td><img src="media/step-icons-id-attribute.png" alt="ID attribute step icon" title="Icono de paso de ID de atributo"><br>IdAttribute</td>
<td><img src="media/step-icons-invent-batch-id.png" alt="Inventory batch ID step icon" title="Icono de paso de ID de lote de inventario"><br>InventBatchID</td>
<td><img src="media/step-icons-invent-color-id.png" alt="Inventory color ID step icon" title="Icono de paso de ID de color de inventario"><br>InventColorID</td>
</tr>
<tr>
<td><img src="media/step-icons-invent-location.png" alt="Inventory location step icon" title="Icono de paso de ID de ubicación de inventario"><br>InventLocation</td>
<td><img src="media/step-icons-invent-serial-id.png" alt="Inventory serial ID step icon" title="Icono de paso de ID de serie de inventario"><br>InventSerialID</td>
<td><img src="media/step-icons-invent-size-id.png" alt="Inventory size ID step icon" title="Icono de paso de ID de tamaño de inventario"><br>InventSizeID</td>
<td><img src="media/step-icons-invent-status-id.png" alt="Inventory status ID step icon" title="Icono de paso de ID de estado de inventario"><br>InventStatusID</td>
</tr>
<tr>
<td><img src="media/step-icons-invent-style-id.png" alt="Inventory style ID step icon" title="Icono de paso de ID de estilo de inventario"><br>InventStyleID</td>
<td><img src="media/step-icons-invent-version-id.png" alt="Inventory version ID step icon" title="Icono de paso de ID de versión de inventario"><br>InventVersionID</td>
<td><img src="media/step-icons-item-id.png" alt="Item ID step icon" title="Icono de paso de ID de artículo"><br>ItemID</td>
<td><img src="media/step-icons-itm-contianer-id.png" alt="ITM container ID step icon" title="Icono de paso de ID de contenedor ITM"><br>ITMContainerID</td>
</tr>
<tr>
<td><img src="media/step-icons-itm-shipment-id.png" alt="ITM shipment ID step icon" title="Ícono de paso de ID de envío de ITM"><br>ITMShipmentID</td>
<td><img src="media/step-icons-kanban-card-id.png" alt="Kanban card ID step icon" title="Icono de paso de ID de tarjeta Kanban"><br>KanbanCardID</td>
<td><img src="media/step-icons-kanban-or-card-id.png" alt="Kanban or card ID step icon" title="Icono de paso de ID de tarjeta o Kanban"><br>KanbanOrCardID</td>
<td><img src="media/step-icons-license-plate-id.png" alt="License plate ID step icon" title="Icono de paso de matrícula de entidad"><br>LicensePlateID</td>
</tr>
<tr>
<td><img src="media/step-icons-load-id.png" alt="Load ID step icon" title="Icono de paso de ID de carga"><br>LoadId</td>
<td><img src="media/step-icons-location-lp-pos.png" alt="Location license plate position step icon" title="Icono de paso de posición de ubicación de matrícula de entidad"><br>LocationLicensePlatePosition</td>
<td><img src="media/step-icons-location-or-lp.png" alt="Location or license plate step icon" title="Icono de paso de ubicación o matrícula de entidad"><br>LocOrLP</td>
<td><img src="media/step-icons-location-or-lp-check.png" alt="Location or license plate check step icon" title="Icono de paso de comprobación de ubicación o matrícula de entidad"><br>LocOrLPCheck</td>
</tr>
<tr>
<td><img src="media/step-icons-location-or-lp-from.png" alt="Location or license plate from step icon" title="Icono de paso de desde ubicación o matrícula de entidad"><br>LocOrLPFrom</td>
<td><img src="media/step-icons-location-or-lp-to.png" alt="Location or license plate to step icon" title="Icono de paso de para ubicación o matrícula de entidad"><br>LocOrLPTo</td>
<td><img src="media/step-icons-long-process-complete.png" alt="Long process completed step icon" title="Icono de paso de proceso largo completado"><br>LongProcessCompleted</td>
<td><img src="media/step-icons-lp-break-parent.png" alt="LP break parent LP step icon" title="Icono de paso LP romper LP primario"><br>LPBreakParentLP</td>
</tr>
<tr>
<td><img src="media/step-icons-merge-container.png" alt="Merge container ID step icon" title="Icono de paso de ID de combinar contenedor"><br>MergeContainerId</td>
<td><img src="media/step-icons-mixed-lp-line.png" alt="Mixed license plate line number step icon" title="Icono de paso de línea de número de matrícula de entidad mixta"><br>MixedLPLineNum</td>
<td><img src="media/step-icons-outbound-weight.png" alt="Outbound weight step icon" title="Icono de paso de peso saliente"><br>OutboundWeight</td>
<td><img src="media/step-icons-owner.png" alt="Owner step icon" title="Icono de paso de propietario"><br>Propietario</td>
</tr>
<tr>
<td><img src="media/step-icons-parent-lp.png" alt="Parent license plate step icon" title="Icono de paso de matrícula primaria"><br>ParentLP</td>
<td><img src="media/step-icons-please-confirm.png" alt="Please confirm step icon" title="Icono de paso de por favor confirme"><br>PleaseConfirm</td>
<td><img src="media/step-icons-po-line-num.png" alt="Purchase order line number step icon" title="Icono de paso del número de línea de pedido de compra"><br>POLineNum</td>
<td><img src="media/step-icons-po-num.png" alt="Purchase order number step icon" title="Icono de paso del número de pedido de compra"><br>NúmPC</td>
</tr>
<tr>
<td><img src="media/step-icons-position-full.png" alt="Position full step icon" title="Icono de paso de posición completa"><br>PositionFull</td>
<td><img src="media/step-icons-potency.png" alt="Potency step icon" title="Icono de paso de potencia"><br>Potencia</td>
<td><img src="media/step-icons-printer-name.png" alt="Printer name step icon" title="Icono de paso del nombre de la impresora"><br>PrinterName</td>
<td><img src="media/step-icons-prod-id.png" alt="Prod ID step icon" title="Icono de paso de ID de prod"><br>ProdId</td>
</tr>
<tr>
<td><img src="media/step-icons-product-confirm.png" alt="Product confirmation step icon" title="Icono de paso de confirmación del producto"><br>ProductConfirmation</td>
<td><img src="media/step-icons-put.png" alt="Put step icon" title="Icono de paso de colocar"><br>Colocar</td>
<td><img src="media/step-icons-putaway-cluster-id.png" alt="Putaway cluster ID step icon" title="Icono de paso de ID de ubicación de clúster"><br>PutawayClusterId</td>
<td><img src="media/step-icons-qty.png" alt="Quantity step icon" title="Icono de paso de cantidad"><br>Cant.</td>
</tr>
<tr>
<td><img src="media/step-icons-qty-adjust-in.png" alt="Quantity adjust in step icon" title="Icono de paso de ajustar cantidad en"><br>QtyAdjustIn</td>
<td><img src="media/step-icons-qty-short.png" alt="Quantity short step icon" title="Icono de paso de cantidad corta"><br>QtyShort</td>
<td><img src="media/step-icons-qty-to-consume.png" alt="Quantity to consume step icon" title="Icono de paso de cantidad a consumir"><br>QtyToConsume</td>
<td><img src="media/step-icons-qty-to-put.png" alt="Quantity to put step icon" title="Icono de paso de cantidad a colocar"><br>QtyToPut</td>
</tr>
<tr>
<td><img src="media/step-icons-qty-to-scrap.png" alt="Quantity to scrap step icon" title="Icono de paso de cantidad para dar de baja"><br>QtyToScrap</td>
<td><img src="media/step-icons-qty-confirmation.png" alt="Quantity confirmation step icon" title="Icono de paso de confirmación de cantidad"><br>QuantityConfirmation</td>
<td><img src="media/step-icons-raf-end-job.png" alt="Report as finished end job step icon" title="Icono de paso Informar como trabajo finalizado"><br>RAFEndJob</td>
<td><img src="media/step-icons-recv-loc-id.png" alt="Receive location ID step icon" title="Icono de paso recibir ID de ubicación"><br>RecvLocationID</td>
</tr>
<tr>
<td><img src="media/step-icons-remove-container-id.png" alt="Remove container ID step icon" title="Icono de paso de eliminar ID de contenedor"><br>RemoveContainerID</td>
<td><img src="media/step-icons-rma-no.png" alt="RMA number step icon" title="Icono de paso de número de RMA"><br>RMANum</td>
<td><img src="media/step-icons-select-order.png" alt="Select order step icon" title="Icono de paso de seleccionar pedido"><br>SelectOrder</td>
<td><img src="media/step-icons-short-pick-reason.png" alt="Short pick reason step icon" title="Icono de paso de motivo de selección breve"><br>ShortPickReason</td>
</tr>
<tr>
<td><img src="media/step-icons-sort-position-id.png" alt="Sort position ID step icon" title="Icono de paso de ID de ordenar posición"><br>SortPositionId</td>
<td><img src="media/step-icons-target-lp-id.png" alt="Target license plate ID step icon" title="Icono de paso de matrícula de entidad de destino"><br>TargetLicensePlateId</td>
<td><img src="media/step-icons-to-line-no.png" alt="To line number step icon" title="Icono de paso al número de línea"><br>ToLineNum</td>
<td><img src="media/step-icons-to-location.png" alt="To location step icon" title="Icono de paso a ubicación"><br>ToLocation</td>
</tr>
<tr>
<td><img src="media/step-icons-to-number.png" alt="To number step icon" title="Icono de paso a número"><br>ToNum</td>
<td><img src="media/step-icons-to-warehouse.png" alt="To warehouse step icon" title="Icono de paso a almacén"><br>ToWarehouse</td>
<td><img src="media/step-icons-tranport-load-id.png" alt="Transport load ID step icon" title="Icono de paso de ID de transporte carga"><br>TransportLoadId</td>
<td><img src="media/step-icons-vendor-batch-id.png" alt="Vendor batch ID step icon" title="Icono de paso de ID de lote de proveedor"><br>VendBatchId</td>
</tr>
<tr>
<td><img src="media/step-icons-wave-label-id.png" alt="Wave label ID step icon" title="Icono de paso de ID de etiqueta de oleada"><br>WaveLabelId</td>
<td><img src="media/step-icons-wave-label-qty.png" alt="Wave label quantity step icon" title="Icono de paso de cantidad de etiqueta de oleada"><br>WaveLblQty</td>
<td><img src="media/step-icons-weight.png" alt="Weight step icon" title="Icono de paso de peso"><br>Importancia</td>
<td><img src="media/step-icons-weight-to-consume.png" alt="Weight to consume step icon" title="Icono de paso de peso a consumir"><br>WeightToConsume</td>
</tr>
<tr>
<td><img src="media/step-icons-whs-adjustment-type.png" alt="WHS adjustment type step icon" title="Icono de paso de tipo de ajuste WHS"><br>WHSAdjustmentType</td>
<td><img src="media/step-icons-whs-receiving-exception.png" alt="WHS receiving exception step icon" title="Icono de paso de excepción de recepción WHS"><br>WHSReceivingException</td>
<td><img src="media/step-icons-wms-location-id.png" alt="WMS location ID step icon" title="Icono de paso de ubicación WMS"><br>WMSLocationID</td>
<td><img src="media/step-icons-work-id.png" alt="Work ID step icon" title="Icono de paso de ID de trabajo"><br>WorkId</td>
</tr>
<tr>
<td><img src="media/step-icons-work-id-to-cancel.png" alt="Work ID to cancel step icon" title="Icono de paso de ID de trabajo a cancelar"><br>WorkIdToCancel</td>
<td><img src="media/step-icons-work-lp-id.png" alt="Work license plate ID step icon" title="Icono de paso de matrícula de entidad de trabajo"><br>WorkLicensePlateId</td>
<td><img src="media/step-icons-work-lp-putaway-cluster.png" alt="Work license plate ID putaway cluster step icon" title="Icono de paso de ID de matrícula de entidad de trabajo de ubicación de clúster"><br>WorkLPIDPutawayCluster</td>
<td><img src="media/step-icons-work-pool-id.png" alt="Work pool ID step icon" title="Icono de paso de ID de grupo de trabajo"><br>WorkPoolID</td>
</tr>
<tr>
<td><img src="media/step-icons-zone-pool-id.png" alt="Zone ID step icon" title="Icono de paso de ID de zona"><br>ZoneID</td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>

## <a name="example-assign-step-icons-and-titles-for-a-custom-flow"></a><a name="example"></a>Ejemplo: asignar iconos y títulos de paso para un flujo personalizado

Este ejemplo explica cómo configurar los iconos y los títulos de los pasos para un flujo de tareas personalizado. El escenario se basa en un ejemplo de un flujo de tareas personalizado que se presenta y explora con más detalle en la siguiente publicación del blog: [Personalización de la aplicación móvil de almacenamiento](https://cloudblogs.microsoft.com/dynamics365/it/2017/07/06/customizing-the-warehousing-mobile-app). El flujo de tareas funciona de la siguiente manera:

1. La aplicación muestra una página que solicita al trabajador que proporcione una identificación de contenedor (por ejemplo, escaneando un código de barras).
1. Si el ID del contenedor es válido, la aplicación abre una nueva página que solicita al trabajador el peso. (Si el ID del contenedor no es válido, el trabajador vuelve a la primera página).
1. Cuando el trabajador introduce un peso válido, el sistema almacena el peso y devuelve al trabajador a la primera página.

En la ilustración siguiente se muestra el flujo de la tarea.

![Diagrama de flujo de tarea.](media/step-icons-example-task-flow.png "Diagrama de flujo de tarea")

### <a name="create-a-step-class-for-the-container-input-page"></a>Cree una clase de paso para la página de entrada del contenedor

La página de entrada del contenedor permite al trabajador escanear o introducir una ID de contenedor.

![Página de entrada del contenedor.](media/step-icons-example-container-input.png "Página de entrada del contenedor")

En la página de entrada del contenedor, el nombre de control del campo de entrada es `ContainerId`. Debido a que este nombre de control no está en la [lista de ID de pasos](#step-ids-classes), no encontrará un paso existente que se base en él. Por lo tanto, debe crear una clase de paso que represente el paso. He aquí un ejemplo.

```xpp
[WHSMobileAppStepId('ContainerId')]
final internal class WHSMobileAppStepContainerId extends WHSMobileAppStep
{
    private const WHSMobileAppStepIcon PopulationIcon = 'InventBatchID';
    private const WHSMobileAppStepTitle InputNotFilledTitle = "@WAX:WHSMobileAppStepContainerID_InputNotFilled"; //Scan a container
    protected void initValues()
    {
        defaultStepIcon = PopulationIcon;
        defaultStepTitle = InputNotFilledTitle;
    }
}
```

El identificador del icono de paso se almacena en el miembro de la clase `defaultStepIcon` y el título del paso se almacena en el miembro de la clase `defaultStepTitle`.

Para asignar un icono de paso, configure `defaultStepIcon` a uno de los ID de icono que se enumeran en la sección [Iconos de pasos disponibles](#step-icons) anterior en este tema.

### <a name="use-a-standard-or-custom-step-icon-and-title-for-the-weight-input"></a>Use un icono de paso estándar o personalizado y un título para la entrada de peso

La página de entrada de peso le permite al trabajador introducir un peso.

![Página de entrada de peso.](media/step-icons-example-weight-input.png "Página de entrada de peso")

En la página de entrada de peso, el nombre de control del campo de entrada es `Weight`, que está en la [lista de ID de pasos](#step-ids-classes). Por lo tanto, si el icono de paso y el título que se definen en la clase `WHSMobileAppStepWeight` son aceptables para usted, no tiene que cambiar nada para este paso.

Sin embargo, si prefiere utilizar un icono o título diferente para este paso, puede anular el método `stepId()` o el método `stepInfo()` en la clase de constructor. Cada flujo de tareas tiene su propio generador de información de pasos.

#### <a name="override-the-stepid-method"></a>Anular el método stepId()

El siguiente ejemplo muestra una forma en la que puede modificar una clase de constructor anulando el método `stepId()`.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepId stepId()
    {
        WHSMobileAppStepId stepIdLocal = super();
        if (stepIdLocal == 'Weight')
        {
            return 'NewWeight';
        }
        return stepIdLocal;
    }
}
```

Luego cree una clase de pasos para el paso `NewWeight`. El código debe parecerse al código del ejemplo `ContainerId` que se mostró anteriormente en este tema.

#### <a name="override-the-stepinfo-method"></a>Anular el método stepInfo()

El siguiente ejemplo muestra una forma en la que puede modificar una clase de constructor anulando el método `stepInfo()`.

```xpp
[WHSWorkExecuteMode(WHSWorkExecuteMode:: WeighContainer)]
public class WHSMobileAppStepInfoBuilderWeighContainer extends WHSMobileAppStepInfoBuilder
{
    protected WHSMobileAppStepInfo stepInfo()
    {
        if (stepId != 'Weight')
        {
            return super();
        }
        WHSMobileAppStepInfo stepInfo = WHSMobileAppStepInfo::construct();
        stepInfo.parmStepIcon('NewIcon');
        stepInfo.parmStepTitle('NewTitle');
        return stepInfo;
    }
}
```

Luego construye un objeto `WHSMobileAppStepInfo` y establezca el icono y/o título directamente.

## <a name="additional-resources"></a>Recursos adicionales

- [Instalar y conectar la aplicación móvil Gestión de almacenes](install-configure-warehouse-management-app.md)
- [Configuración de usuario del dispositivo móvil](mobile-device-user-settings.md)
