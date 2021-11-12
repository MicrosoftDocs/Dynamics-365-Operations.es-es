---
title: Parámetros de fecha y hora utilizados por Optimización de planificación
description: Este tema proporciona información sobre los parámetros de fecha y hora que utiliza Optimización de la planificación durante su funcionamiento.
author: ChristianRytt
ms.date: 09/21/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-09-21
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: dc44778dba0a5b914c524ff2ad026ab2f8eb88aa
ms.sourcegitcommit: f8b597b09157d934b62bd5fb9a4d05b8f82b5a0e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/26/2021
ms.locfileid: "7700192"
---
# <a name="date-and-time-parameters-used-by-planning-optimization"></a>Parámetros de fecha y hora utilizados por Optimización de planificación

[!include [banner](../../includes/banner.md)]

Este tema proporciona información sobre los parámetros de fecha y hora que utiliza Optimización de la planificación durante su funcionamiento.

Mientras que el motor de planificación maestro integrado utiliza fechas de transacción en todos los cálculos, Optimización de planificación funciona con valores de fecha y hora que se convierten en fechas. Esta diferencia de comportamiento puede llevar a situaciones en las que, por ejemplo, las transacciones de pronóstico que se crean a la medianoche del día en que se ejecuta la planificación maestra no se incluyen porque Optimización de planificación considera que se crearon antes de la fecha actual.

## <a name="parameters-for-issue-and-demand-transactions"></a>Parámetros para transacciones de emisión y demanda

La siguiente tabla enumera los parámetros que utiliza Optimización de planificación cuando procesa transacciones de emisión y demanda.

| Parámetro | Nombre del parámetro en Optimización de planificación | Descripción | Campo equivalente en Microsoft Dynamics 365 Supply Chain Management (en la tabla ReqTrans) |
|---|---|---|---|
| Hora de emisión prevista | `PlannedIssueTime` | La fecha prevista actualmente para la emisión. | **Hasta la fecha** (`FuturesDate`) y **Retrasado a tiempo** (`FuturesTime`) |
| Hora de emisión solicitada | `RequestedIssueTime` | La fecha de emisión solicitada por el usuario y establecida en Supply Chain Management. Este parámetro es aplicable solo para pedidos planificados liberados o aprobados. Para los pedidos planificados, está en blanco de forma predeterminada. | **Fecha solicitada** (`ReqDateDlvOrig`) |
| Hora de emisión obligatoria | `RequiredIssueTime` | La fecha de emisión obligatoria que se ajusta mediante Optimización de planificación. Si la hora de emisión solicitada está en el pasado cuando se ejecuta Optimización de planificación, la hora de emisión requerida se ajustará al primer día abierto que no sea anterior a la fecha de hoy. Si la hora de emisión solicitada está marcada como bloqueada en el calendario, la hora de emisión requerida se ajustará al primer día abierto antes de esa fecha. | **Fecha de requisito** (`ReqDate`) y **Hora de requisito** (`ReqTime`) |
| Retraso de la hora de emisión | `IssueTimeDelay` | La diferencia de tiempo entre la hora de emisión planificada y la hora de emisión solicitada para los pedidos aprobados y liberados o la hora de emisión requerida. | **Retraso (en días)** (`FuturesDays`) |

## <a name="parameters-for-receipt-and-supply-transactions"></a>Parámetros para transacciones de recepción y suministro

La siguiente tabla enumera los parámetros que utiliza Optimización de planificación cuando procesa transacciones de recepción y suministro.

| Parámetro | Nombre del parámetro en Optimización de planificación | Descripción | Campo equivalente en Supply Chain Management (en la tabla ReqTrans o ReqPO) |
|---|---|---|---|
| Tiempo de disponibilidad planificado | `PlannedAvailabilityTime` | La fecha en que está previsto que el recibo esté disponible. | **Fecha de requisito** (`ReqDate`) y **Hora de requisito** (`ReqTime`) |
| Hora de recepción planificada | `PlannedReceiptTime` | La fecha en la que el recibo llegará a la ubicación. | **Hasta la fecha** (`FuturesDate`), **Retrasado a tiempo** (`FuturesTime`), y **Fecha de entrega** (`ReqDateDlv`) o **Fecha solicitada** (`ReqDateDlvOrig`) si el pedido aún no se ha emitido. |
| Tiempo de disponibilidad necesario | `RequiredAvailabilityTime` | La fecha de disponibilidad que se ajusta mediante Optimización de planificación. | **Fecha de requisito** (`ReqDate`) y **Hora de requisito** (`ReqTime`) |
| Hora de recepción prevista | `ExpectedReceiptTime` | La fecha de recepción prevista para un recibo emitido. El valor lo establece el usuario en Supply Chain Management y no se ajusta mediante Optimización de planificación. Este parámetro se aplica solo a los recibos emitidos. | **Fecha solicitada** (`ReqDateDlvOrig`) |
| Hora de recepción requerida | `RequiredReceiptTime` | La fecha de recibo requerida que se ajusta mediante Optimización de planificación. | **Fecha de requisito** (`ReqDate`) y **Hora de requisito** (`ReqTime`) |
| Hora de pedido prevista | `PlannedOrderingTime` | La fecha de pedido que se calcula mediante Optimización de planificación. | **Fecha de pedido** (`ReqDateOrder`) y **Hora de pedido** (`ReqTimeOrder`) |
| Hora de inicio de la actividad prevista | `PlannedActivityStartTime` | La fecha en la que debe comenzar la actividad de este recibo. | **Fecha de inicio** (`SchedFromDate`) |
| Retraso en el tiempo de recepción | `ReceiptTimeDelay` | La diferencia de tiempo entre la hora de recepción planificada y la hora de recepción requerida. | **Retraso (días)** (`FuturesDays`) y **Retrasado a tiempo** (`FuturesTime`) |

## <a name="examples-of-date-parameter-use-by-planning-optimization"></a>Ejemplos de parámetros de fecha utilizados por Optimización de planificación

Los planes en las siguientes ilustraciones son a nivel de día, pero Optimización de planificación se ejecuta a un nivel más detallado. Por ejemplo, dado que los márgenes pueden expresarse en horas, el tiempo de planificación para realizar el pedido puede ser el 22 de enero de 2021, a las 11:35 y así sucesivamente.

### <a name="example-1-simple-scenario"></a>Ejemplo 1: escenario simple

Un pedido de venta que tiene una fecha de emisión solicitada el 22 de enero está cubierto por un pedido de compra. Se usan los siguientes parámetros:

- Sin tiempo de espera
- Sin calendarios (todos los días están abiertos).
- Sin márgenes

En la ilustración siguiente se muestra este escenario. (Seleccione la ilustración para abrir una versión más grande).

[![Escenario simple.](media/planning-service-dates-1-small.png)](media/planning-service-dates-1.png)

### <a name="example-2-lead-time-scenario"></a>Ejemplo 2: escenario de plazo

Un pedido de venta que tiene una fecha de emisión solicitada el 22 de enero está cubierto por un pedido de compra. Se usan los siguientes parámetros:

- Tres días de plazo
- Sin calendarios (todos los días están abiertos).
- Sin márgenes

En la ilustración siguiente se muestra este escenario. (Seleccione la ilustración para abrir una versión más grande).

[![Escenario de plazo.](media/planning-service-dates-2-small.png)](media/planning-service-dates-2.png)

### <a name="example-3-margin-scenario"></a>Ejemplo 3: escenario de margen

Un pedido de venta que tiene una fecha de emisión solicitada el 22 de enero está cubierto por un pedido de compra. Se usan los siguientes parámetros:

- Tres días de plazo
- Margen de pedido de cuatro días
- Margen de disponibilidad de cinco días
- Sin calendarios (todos los días están abiertos).

En la ilustración siguiente se muestra este escenario. (Seleccione la ilustración para abrir una versión más grande).

[![Escenario de margen.](media/planning-service-dates-3-small.png)](media/planning-service-dates-3.png)

### <a name="example-4-delay-scenario"></a>Ejemplo 4: escenario de retraso

Un pedido de venta que tiene una fecha de emisión solicitada el 22 de enero está cubierto por un pedido de compra. Este ejemplo usa la misma configuración que el ejemplo 3, pero la fecha de planificación se ha movido al 15 de enero. La programación regresiva (marcadores rojos) falla porque el tiempo de pedido planificado debería ser anterior a la fecha de hoy. Por lo tanto, la planificación maestra debe programar con anticipación y se producirán retrasos.

En la ilustración siguiente se muestra este escenario. (Seleccione la ilustración para abrir una versión más grande).

[![Escenario de retraso.](media/planning-service-dates-4-small.png)](media/planning-service-dates-4.png)

### <a name="example-5-transfer-scenario"></a>Ejemplo 5: escenario de transferencia

Un pedido de venta del almacén 1 que tiene una hora de emisión solicitada el 22 de enero está cubierto por un pedido de transferencia del almacén 2 que está cubierto por un pedido de compra planificado. Se usan los siguientes parámetros:

- Tres días de plazo de transferencia (almacén 1)
- Dos días de plazo de compra (almacén 2)
- Sin calendarios (todos los días están abiertos).

En la ilustración siguiente se muestra este escenario. (Seleccione la ilustración para abrir una versión más grande).

[![Escenario de transferencia.](media/planning-service-dates-5-small.png)](media/planning-service-dates-5.png)

### <a name="example-6-lead-time-with-calendars-scenario"></a>Ejemplo 6: Plazo de ejecución con escenario de calendarios

Un pedido de venta que tiene una fecha de emisión solicitada el 22 de enero está cubierto por un pedido de compra. Se usan los siguientes parámetros:

- Tres días de plazo
- Calendario de emisión (cerrado los viernes)
- Calendario de disponibilidad (cerrado jueves y viernes)
- Calendario de recepción (cerrado los martes, miércoles y domingos)
- Calendario de plazo (cerrado jueves y viernes)
- Calendario de pedidos (abierto los lunes y sábados)

En la ilustración siguiente se muestra este escenario. (Seleccione la ilustración para abrir una versión más grande).

[![Plazo de ejecución con escenario de calendarios.](media/planning-service-dates-6-small.png)](media/planning-service-dates-6.png)

### <a name="example-7-delay-with-calendars-scenario"></a>Ejemplo 7: Retraso con escenario de calendarios

Un pedido de venta que tiene una fecha de emisión solicitada el 22 de enero está cubierto por un pedido de compra. Este ejemplo usa la misma configuración que el ejemplo 6, pero la fecha de planificación se ha movido al 13 de enero. La programación regresiva (marcadores rojos) falla porque el tiempo de pedido planificado debería ser anterior a la fecha de hoy. Por lo tanto, la planificación maestra debe programar con anticipación y se producirán retrasos.

En la ilustración siguiente se muestra este escenario. (Seleccione la ilustración para abrir una versión más grande).

[![Retraso con escenario de calendarios.](media/planning-service-dates-7-small.png)](media/planning-service-dates-7.png)
