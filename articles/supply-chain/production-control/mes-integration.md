---
title: Integración con sistemas de ejecución de fabricación de terceros
description: Este artículo explica cómo puede integrar Microsoft Dynamics 365 Supply Chain Management con un sistema de ejecución de fabricación de terceros (MES).
author: johanhoffmann
ms.date: 10/01/2021
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2021-10-01
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 208ed2d6c8b411d12888966d9c175730e828eb44
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8860649"
---
# <a name="integrate-with-third-party-manufacturing-execution-systems"></a>Integración con sistemas de ejecución de fabricación de terceros

[!include [banner](../includes/banner.md)]

Algunas organizaciones de fabricación que utilizan Microsoft Dynamics 365 Supply Chain Management utilizan la funcionalidad nativa de Dynamics 365 para controlar sus actividades de fabricación de máquinas, equipos y personal. Sin embargo, otras organizaciones de fabricación, especialmente aquellas que tienen requisitos de fabricación avanzados, utilizan en su lugar un sistema de ejecución de fabricación (MES) de terceros. Las organizaciones pueden elegir una solución MES de terceros porque, por ejemplo, se adapta específicamente a su industria vertical.

En la solución integrada, el intercambio de datos está completamente automatizado y ocurre casi en tiempo real. Por lo tanto, los datos se mantienen actualizados en ambos sistemas y no se requiere entrada de datos manual. Por ejemplo, cuando se registra el consumo de material en el MES, la integración garantiza que el mismo consumo también se registre en Dynamics 365. Por lo tanto, los registros de inventario actualizados están disponibles para otros procesos importantes, como la planificación y las ventas.

La solución hace que sea más rápido, más fácil y más económico para los usuarios de Supply Chain Management integrarse con MES de terceros. Ofrece las siguientes características:

- Eventos e interfaces empresariales que admiten [procesos clave de ejecución de fabricación](#processes-available-for-mes-integration)
- Un panel de control centralizado donde puede realizar un seguimiento del historial de procesamiento de eventos y solucionar problemas y corregir los procesos que fallan

La siguiente ilustración muestra una colección típica de eventos, procesos y mensajes comerciales que se intercambian en una solución integrada.

![Escenario de integración típico.](media/3p-mes-scenario.png "Escenario de integración típico.")

## <a name="turn-on-the-mes-integration-feature"></a>Activar la función de integración MES

Antes de poder usar esta característica, un administrador debe activarla en su sistema como se describe en el procedimiento siguiente.

1. Vaya a **Administración del sistema \> Configuración \> Configuración de licencias**.
1. Asegúrese de que la clave de licencia **Tiempo y asistencia** está habilitada (muestra una marca de verificación). Esta clave de licencia es necesaria porque controla la funcionalidad y los datos del sistema de ejecución de fabricación. Si no está habilitada, siga los siguientes pasos:
    1. Coloque su sistema en modo de mantenimiento como se describe en [Modo de mantenimiento](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md).
    1. En la página **Configuración de licencia**, seleccione la casilla de verificación **Tiempo y asistencia**.
    1. Desactive el modo de mantenimiento como se describe en [Modo de mantenimiento](../../fin-ops-core/dev-itpro/sysadmin/maintenance-mode.md)
1. Vaya a **Administración del sistema \> Espacios de trabajo \> Administración de características**.
1. Active la característica que aparece en la siguiente forma (ver también [Resumen general de gestión de característica](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)):
    - **Módulo:** *control de producción*
    - **Nombre de característica:** *Integración del sistema de ejecución de fabricación*

## <a name="processes-available-for-mes-integration"></a>Procesos disponibles para la integración de MES

Puede habilitar cualquiera o todos los siguientes procesos para la integración.

| Nombre del proceso | Description |
|---|---|
| Eventos de negocio de liberación de pedidos de producción y cambio del estado de pedidos de producción | Este proceso proporciona un evento de negocio que el MES puede escuchar para obtener información sobre los pedidos de producción que deben producirse. Se espera que los datos de referencia relacionados con el pedido de producción se compartan desde Supply Chain Management hasta el MES a través del protocolo de datos abiertos (OData) o entidades de datos. |
| Iniciar pedido de producción | Este proceso proporciona a Supply Chain Management información sobre los pedidos de producción que se están iniciando mediante el MES. Garantiza que ambos sistemas tengan una vista actualizada de todas las actividades de fabricación. |
| Informe de cantidad producida o convertida en residuos | Este proceso proporciona a Supply Chain Management información sobre las cantidades de productos y errores que se generan en un trabajo de producción mediante el MES. Garantiza que los supervisores de planta tengan una visión actualizada del progreso del plan de producción. |
| Informe de consumo de materias primas | Este proceso proporciona a Supply Chain Management información del MES sobre las cantidades de materias primas que se consumen. Pone registros de inventario actualizados a disposición de otros procesos importantes, como la planificación y las ventas. |
| Informe de tiempo consumido por la operación | Este proceso proporciona a Supply Chain Management información sobre el tiempo que se utiliza para una operación específica. |
| Finalizar pedido de producción | Este proceso informa a Supply Chain Management de que el MES ha actualizado un pedido de producción a su estado final de *Terminado*. Este estado indica que no se producirán más cantidades en el pedido de producción. |

## <a name="monitor-incoming-messages"></a>Supervisar mensajes entrantes

Para supervisar los mensajes entrantes al sistema, abra la página **Integración de sistemas de ejecución de fabricación**. Allí, puede ver, procesar y solucionar problemas.

Todos los mensajes para un pedido de producción específico se procesan en la secuencia en que se reciben. Sin embargo, es posible que los mensajes para diferentes pedidos de producción no se procesen en la secuencia recibida porque los trabajos por lotes se procesan en paralelo. En caso de error, el trabajo por lotes intentará procesar cada mensaje tres veces antes de establecerlo en el estado *Con errores*.

## <a name="call-the-api"></a>Llamar a la API

Para llamar a la API de integración de MES, envíe una solicitud `POST` a la siguiente URL de punto final:

`/api/services/SysMessageServices/SysMessageService/SendMessage`

El cuerpo de la solicitud que envíe debe parecerse al siguiente ejemplo. Reemplace los valores de `_companyId`, `_messageType` y `_messageContent` según sea necesario. Para obtener información sobre los distintos tipos de mensajes que admite la API y cómo diseñar su contenido, consulte la siguiente sección.

```json
{
    "_companyId": "USMF",
    "_messageQueue": "JmgMES3P",
    "_messageType": "ProdProductionOrderReportFinished",
    "_messageContent":
    "{\"ProductionOrderNumber\": \"P000123\", \"ReportFinishedLines\": [{\"ItemNumber\": \"A0001\", \"ReportedGoodQuantity\": 10, \"ReportAsFinishedDate\": \"2021-01-01\"}]}"
}
```

## <a name="api-message-types-and-content"></a>Tipos y contenido de mensajes de API

Esta sección describe cada tipo de mensaje que se puede intercambiar a través de la API de integración de MES.

### <a name="start-production-order-message"></a>Mensaje Iniciar pedido de producción

Para el mensaje *iniciar orden de producción*, el valor de `_messageType` es `ProdProductionOrderStart`. La siguiente tabla muestra los campos que admite este mensaje.

| Nombre de campo | Status | Tipo |
|---|---|---|
| `ProductionOrderNumber` | Obligatoria | Cadena |
| `StartedQuantity` | Opcional | Real |
| `StartedDate` | Opcional | Fecha |
| `AutomaticBOMConsumptionRule` | Opcional | Enum (FlushingPrincip \| Always \| Never) |

### <a name="report-as-finished-message"></a>Mensaje Notificar como terminado

Para el mensaje *notificar como terminado*, el valor de `_messageType` es `ProdProductionOrderReportFinished`. La siguiente tabla muestra los campos que admite este mensaje.

| Nombre de campo | Status | Tipo |
|---|---|---|
| `ProductionOrderNumber` | Obligatoria | Cadena |
| `ReportFinishedLines` | Obligatoria | Una lista de líneas (al menos una), cada una de las cuales contiene la carga útil que se describe en la siguiente tabla |

La siguiente tabla muestra los campos que admite cada línea de la sección `ReportFinishedLines` del mensaje `ProdProductionOrderReportFinished`.

| Nombre de campo | Status | Tipo |
|---|---|---|
| `LineNumber` | Opcional | Real |
| `ItemNumber` | Opcional | Cadena|
| `ProductionType` | Opcional | Enum (MainItem \| Formula \| BOM \| Co_Product \| By_Product \| None), extensible |
| `ReportedErrorQuantity` | Opcional | Real|
| `ReportedGoodQuantity` | Opcional | Real|
| `ReportedErrorCatchWeightQuantity` | Opcional | Real |
| `ReportedGoodCatchWeightQuantity` | Opcional | Real |
| `AcceptError` | Opcional | Enum (Sí \| No) |
| `ErrorCause` | Opcional | Enum (None \| Material \| Machine \| OperatingStaff), extensible |
| `ExecutedDateTime` | Opcional | Fecha y hora |
| `ReportAsFinishedDate` | Opcional | Fecha |
| `AutomaticBOMConsumptionRule` | Opcional | Enum (FlushingPrincip \| Always \| Never) |
| `AutomaticRouteConsumptionRule` | Opcional |Enum (RouteDependent \| Always \| Never) |
| `RespectFlushingPrincipleDuringOverproduction` | Opcional | Enum (Sí \| No) |
| `ProductionJournalNameId` | Opcional | Cadena |
| `PickingListProductionJournalNameId` | Opcional | Cadena|
| `RouteCardProductionJournalNameId` | Opcional | Cadena |
| `FromOperationNumber` | Opcional | Entero|
| `ToOperationNumber` | Opcional | Entero|
| `InventoryLotId` | Opcional | Cadena |
| `BaseValue` | Opcional | Cadena |
| `EndJob` | Opcional | Enum (Sí \| No) |
| `EndPickingList` | Opcional | Enum (Sí \| No) |
| `EndRouteCard` | Opcional | Enum (Sí \| No) |
| `PostNow` | Opcional | Enum (Sí \| No) |
| `AutoUpdate` | Opcional | Enum (Sí \| No) |
| `ProductColorId` | Opcional | Cadena|
| `ProductConfigurationId` | Opcional | Cadena |
| `ProductSizeId` | Opcional | Cadena |
| `ProductStyleId` | Opcional | Cadena |
| `ProductVersionId` | Opcional | Cadena |
| `ItemBatchNumber` | Opcional | Cadena |
| `ProductSerialNumber` | Opcional | Cadena |
| `LicensePlateNumber` | Opcional | Cadena |
| `InventoryStatusId` | Opcional | Cadena |
| `ProductionWarehouseId` | Opcional | Cadena |
| `ProductionSiteId` | Opcional | Cadena |
| `ProductionWarehouseLocationId` | Opcional | Cadena |
| `InventoryDimension1` a `InventoryDimension12` | Opcional | Cadena |

Las 12 dimensiones extensibles (de `InventoryDimension1` a `InventoryDimension12`) requieren personalización y no siempre se utilizan. Para obtener más información sobre ellas, consulte [Agregar nuevas dimensiones de inventario a través de la extensión](../../fin-ops-core/dev-itpro/extensibility/inventory-dimensions.md).

### <a name="material-consumption-picking-list-message"></a>Mensaje Consumo de material (lista de selección)

Para el mensje *consumo de material (lista de selección)*, el valor de `_messageType` es `ProdProductionOrderPickingList`. La siguiente tabla muestra los campos que admite este mensaje.

| Nombre de campo | Status | Tipo |
|---|---|---|
| `ProductionOrderNumber` | Obligatoria | Cadena |
| `JournalNameId` | Opcional | Cadena |
| `PickingListLines` | Obligatoria | Una lista de líneas (al menos una), cada una de las cuales contiene la carga útil que se describe en la siguiente tabla |

La siguiente tabla muestra los campos que admite cada línea de la sección `PickingListLines` del mensaje `ProdProductionOrderPickingList`.

| Nombre de campo | Status | Tipo |
|---|---|---|
| `ItemNumber` | Obligatoria | Cadena |
| `ConsumptionBOMQuantity` | Opcional | Real |
| `ProposalBOMQuantity` | Opcional | Real |
| `ScrapBOMQuantity` | Opcional | Real |
| `BOMUnitSymbol` | Opcional | Cadena |
| `ConsumptionInventoryQuantity` | Opcional | Real |
| `ProposalInventoryQuantity` | Opcional | Real |
| `ConsumptionCatchWeightQuantity` | Opcional | Real |
| `ProposalCatchWeightQuantity` | Opcional | Real |
| `ConsumptionDate` | Opcional | Fecha |
| `OperationNumber` | Opcional | Entero |
| `LineNumber` | Opcional | Real |
| `PositionNumber` | Opcional | Cadena |
| `IsConsumptionEnded` | Opcional | Enum (Sí \| No) |
| `ErrorCause` | Opcional | Enum (None \| Material \| Machine \| OperatingStaff), extensible |
| `InventoryLotId` | Opcional | Cadena |

### <a name="time-used-for-operation-route-card-message"></a>Mensaje Tiempo utilizado para la operación (tarjeta de ruta)

Para el mensaje *tiempo utilizado para la operación (tarjeta de ruta)*, el valor de `_messageType` es `ProdProductionOrderRouteCard`. La siguiente tabla muestra los campos que admite este mensaje.

| Nombre de campo | Status | Tipo |
|---|---|---|
| `ProductionOrderNumber` | Obligatoria | Cadena |
| `JournalNameId` | Opcional | Cadena |
| `RouteCardLines` | Obligatoria | Una lista de líneas (al menos una), cada una de las cuales contiene la carga útil que se describe en la siguiente tabla |

La siguiente tabla muestra los campos que admite cada línea de la sección `RouteCardLines` del mensaje `ProdProductionOrderRouteCard`.

| Nombre de campo | Status | Tipo |
|---|---|---|
| `OperationNumber` | Obligatoria | Entero |
| `OperationPriority` | Opcional | Enum (Primary \| Secondary1 \| Secondary2 \| ... \| Secondary20) |
| `OperationId` | Opcional | Cadena |
| `OperationsResourceId` | Opcional | Cadena |
| `Worker` | Opcional | Cadena |
| `HoursRouteCostCategoryId` | Opcional | Cadena |
| `QuantityRouteCostCategoryId` | Opcional | Cadena |
| `HourlyRate` | Opcional | Real |
| `Hours` | Opcional | Real |
| `GoodQuantity` | Opcional | Real |
| `ErrorQuantity` | Opcional | Real |
| `CatchWeightGoodQuantity` | Opcional | Real |
| `CatchWeightErrorQuantity` | Opcional | Real |
| `QuantityPrice` | Opcional | Real |
| `ProcessingPercentage` | Opcional | Real |
| `ConsumptionDate` | Opcional | Fecha |
| `TaskType` | Opcional | Enum (QueueBefore \| Setup \| Process \| Overlap \| Transport \| QueueAfter \| Burden) |
| `ErrorCause` | Opcional | Enum (None \| Material \| Machine \| OperatingStaff), extensible |
| `OperationCompleted` | Opcional | Enum (Sí \| No) |
| `BOMConsumption` | Opcional | Enum (Sí \| No) |
| `ReportAsFinished` | Opcional | Enum (Sí \| No) |

### <a name="end-production-order-message"></a>Mensaje Finalizar pedido de producción

Para el mensaje *finalziar pedido de producción*, el valor de `_messageType` es `ProdProductionOrderEnd`. La siguiente tabla muestra los campos que admite este mensaje.

| Nombre de campo | Status | Tipo |
|---|---|---|
| `ProductionOrderNumber` | Obligatoria | Cadena |
| `ExecutedDateTime` | Opcional | Fecha y hora |
| `EndedDate` | Opcional | Fecha |
| `UseTimeAndAttendanceCost` | Opcional | Enum (Sí \| No) |
| `AutoReportAsFinished` | Opcional | Enum (Sí \| No) |
| `AutoUpdate` | Opcional | Enum (Sí \| No) |

## <a name="other-production-information"></a>Otra información de producción

Los mensajes respaldan acciones o eventos que ocurren en la planta. Se procesan mediante el marco de integración MES descrito en este artículo. El diseño asume que otra información de referencia que se compartirá con el MES (como la información relacionada con el producto o la lista de materiales o la ruta (con sus tiempos de instalación y configuración específicos) utilizada en una orden de producción específica) se extraerá del sistema utilizando [entidades de datos](../../fin-ops-core/dev-itpro/data-entities/data-entities-data-packages.md#data-entities) mediante transferencia de archivos u OData.

## <a name="receive-feedback-about-the-state-of-a-message"></a>Recibir comentarios sobre el estado de un mensaje

Después de que el MES haya enviado un mensaje a Supply Chain Management, podría ser relevante para Supply Chain Management devolver comentarios sobre el estado del mensaje. A continuación se muestran algunos ejemplos de casos en los que este comportamiento podría ser relevante:

- No hay ninguna persona que se encargue de supervisar constantemente la integración de MES.
- La persona que se encarga de supervisar la integración de MES quiere que se le notifique por correo electrónico cuando falla un mensaje, para que sepa que tiene que actuar.
- El MES debe mostrar un mensaje de error para informar al operador de la planta o alguien del departamento de TI que deben tomar medidas.
- El MES debe volver a calcular la programación de la orden después de recibir un mensaje de falla (por ejemplo, porque una orden de producción no se inició).

En estos casos, puede aprovechar la función de alerta estándar en Supply Chain Management. Para obtener información sobre cómo funcionan las alertas estándar, consulte los siguientes recursos:

- Artículo de ayuda: [Resumen de alertas](../../fin-ops-core/fin-ops/get-started/alerts-overview.md)
- Vídeo: [Opciones de reglas de alertas en Dynamics 365 for Finance and Operations](https://www.youtube.com/watch?v=cpzimwOjicM&ab_channel=MicrosoftDynamics365)

Por ejemplo, puede configurar las siguientes alertas para proporcionar comentarios sobre el estado de un mensaje:

- Crear un evento empresarial ("Enviar externamente") que se utiliza cuando un mensaje es *Fallido*.
- Envíe una notificación y un correo electrónico al administrador de TI o al gerente de la planta de producción.
