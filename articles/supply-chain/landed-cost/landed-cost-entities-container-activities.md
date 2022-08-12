---
title: Entidad de actividades de contenedor
description: Este artículo proporciona información sobre las actividades de los contenedores, que se utilizan para realizar un seguimiento del progreso de los contenedores de envío.
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
ms.openlocfilehash: 6a518003f8624ef05ac86be1b963c3f916420278
ms.sourcegitcommit: 5b34b41ae74269ba639e2876bc5862ef468da1cc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/15/2022
ms.locfileid: "9167585"
---
# <a name="container-activities-entity"></a>Entidad de actividades de contenedor

[!include [banner](../includes/banner.md)]

Las actividades de contenedores se utilizan para realizar un seguimiento del progreso de los contenedores de envío. Se crea un registro para cada tramo que se asigna a la plantilla de viaje que se selecciona en el momento de la creación del contenedor de envío. Los registros también se crean cuando el contenedor de envío se crea a través de una entidad de datos.

La información sobre el progreso de un contenedor de envío en tránsito a menudo se recibe de una fuente externa. La entidad de actividades del contenedor permite que una fuente externa, como un agente de carga, actualice directamente el registro. Por lo tanto, no se requiere una actualización manual de los datos.

## <a name="container-activities-itmcontaineractivityentity"></a>Actividades de contenedor (ITMContainerActivityEntity)

Puede utilizar la entidad de actividades del contenedor (`ITMContainerActivityEntity`) para crear registros de actividad adicionales. Alternativamente, un transitario puede pasar actualizaciones para un valor de **Fecha de finalización real** confirmado.

| Name | Asignación | Tipo de datos | Clave | Obligatoria |
|---|---|---|---|---|
| Fecha de finalización real | ITMContainerActivityTable.ActualEndDate | Fecha y hora | No | No |
| Modo de entrega | ITMContainerActivityTable.DlvModeId | Nvarchar(10) | No | No |
| Fecha final estimada | ITMContainerActivityTable.EsimatedDate | Fecha y hora | No | No |
| Número de línea | ITMContainerActivityTable.LineNum | Numeric(32, 16) | **Sí** | No |
| Notas | ITMContainerActivityTable.Notes | nvarchar(MAX) | No | No |
| Actividad | ITMContainerActivityTable.ShipActivityId | Nvarchar(10) | No | **Sí** |
| Contenedor de envío | ITMContainerActivityTable.ShipContainerId | Nvarchar(20) | **Sí** | **Sí** |
| Viaje | ITMContainerActivityTable.ShipId | Nvarchar(20) | **Sí** | **Sí** |
| Escala | ITMContainerActivityTable.ShipLegId | Nvarchar(20) | No | **Sí** |
| Proveedor de servicio | ITMContainerActivityTable.ShipServiceProvider | Nvarchar(20) | No | No |
| Temperatura | ITMContainerActivityTable.ShipTemperature | Numeric(32, 6) | No | No |
| Embarcación | ITMContainerActivityTable.ShipVesselId | Nvarchar(20) | No | No |
| Fecha inicial | ITMContainerActivityTable.StartDate | Fecha y hora | No | No |

## <a name="tracking-control"></a>Control de seguimiento

El centro de control de seguimiento permite que una actualización de un campo de origen específico se desencadene mediante una actualización de un campo de destino específico. Si tanto el valor del campo de origen como el valor del campo de destino se actualizan utilizando la entidad de actividades del contenedor, el campo de destino mostrará el valor de la entidad. Este comportamiento está relacionado con los registros de control de seguimiento que tienen un valor **Crear tipo** de *Tiempo de espera*.

Para las áreas de coste que tienen un valor **Crear tipo** de *Actualización de estado* o *Vacío* (que es un valor definido por el usuario), el sistema actualizará el estado del viaje o el campo de destino de acuerdo con la configuración del control de seguimiento.

## <a name="calculated-fields"></a>Campos calculados

Los valores de los siguientes campos en un registro de actividad de contenedor se calculan en función de los valores de otros campos. Aunque estos campos calculados no están incluidos en la entidad de datos, se establecerán si se proporcionan los campos en los que se basan los cálculos.

- **Días estimados** = **Fecha de finalización estimada** - **Fecha de inicio**
- **Días reales** = **Fecha de finalización real** - **Fecha de inicio**
