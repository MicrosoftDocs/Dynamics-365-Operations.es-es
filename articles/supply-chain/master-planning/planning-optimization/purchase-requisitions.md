---
title: Solicitudes de compra
description: Este tema describe cómo se admiten las solicitudes de compra en Planning Optimization.
author: t-benebo
ms.date: 01/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqPlanSched, ReqGroup
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2021-01-04
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 0328342fbe322225a5ecb095d3b0165caa6d18d3
ms.sourcegitcommit: ad1afc6893a8dc32d1363395666b0fe1d50e983a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/23/2022
ms.locfileid: "8469656"
---
# <a name="purchase-requisitions"></a>Solicitudes de compra

[!include [banner](../../includes/banner.md)]

La planificación maestra puede reponer las solicitudes de compra aprobadas. Por lo tanto, para cubrir las solicitudes de compra, los usuarios no tienen que usar un flujo de trabajo para crear pedidos de compra. En cambio, las solicitudes de compra se pueden cubrir mediante la planificación maestra. Debido a esta funcionalidad, una solicitud de compra puede producir un pedido de compra, un pedido de transferencia o un pedido de producción, según el valor del **Tipo de pedido planificado** que se establece para el producto relacionado.

## <a name="enable-master-plans-to-include-requisitions"></a>Habilitar planes maestros para incluir solicitudes

Para incluir solicitudes durante el cálculo de cobertura para un plan maestro, siga estos pasos.

1. Vaya a **Planificación maestra** \> **Configurar** \> **Planes** \> **Planes maestros**.
1. Seleccionar o crear un plan maestro.
1. En la ficha desplegable **General**, configure la opción **Incluir solicitudes** en *Sí*.
1. Repita los pasos 2 y 3 para cada plan maestro adicional en el que desee incluir solicitudes.

## <a name="approved-requisitions-time-fence"></a>Límite de tiempo de solicitudes aprobadas

El *Límite de tiempo de requisiciones aprobadas* establece cuánto tiempo atrás (en días) un plan maestro incluirá la demanda de las solicitudes de reabastecimiento aprobadas. Puede establecer un límite de tiempo para solicitudes aprobadas tanto a nivel de grupo de cobertura como a nivel de plan maestro.

### <a name="set-the-approved-requisitions-time-fence-for-a-coverage-group"></a>Establecer el límite de tiempo de solicitudes aprobadas para un grupo de cobertura

1. Vaya a **Planificación maestra** \> **Configurar** \> **Cobertura** \> **Grupos de cobertura**.
1. Cree o seleccione un grupo de cobertura.
1. En la ficha desplegable **Otro**, establezca el campo **Límite de tiempo de solicitudes aprobadas (días)** en el número de días que se incluirán en el límite de tiempo.
1. Repita los pasos 2 y 3 para cada grupo de cobertura adicional en el que desee establecer un límite de tiempo para solicitudes aprobadas.

### <a name="set-the-approved-requisitions-time-fence-for-individual-master-plans"></a>Establecer el límite de tiempo de solicitudes aprobadas para un plan maestro individual

Cuando establece un límite de tiempo de solicitudes aprobado para un plan maestro individual, la configuración anula la configuración de límite de tiempo para cualquier grupo de cobertura aplicable.

1. Vaya a **Planificación maestra** \> **Configurar** \> **Planes** \> **Planes maestros**.
1. Seleccionar o crear un plan maestro.
1. En la ficha desplegable **Límites de tiempo en días**, establezca el campo **Límite de tiempo de solicitudes aprobadas (días)** en el número de días que se incluirán en el límite de tiempo.
1. Repita los pasos 2 y 3 para cada plan maestro adicional en el que desee establecer un límite de tiempo para solicitudes aprobadas.

> [!IMPORTANT]
> **Próximamente:** Los límites de tiempo de solicitudes aprobadas aún no son compatibles con Planning Optimization. Hasta que sean compatibles, todos los valores que ingrese en el campo **Límite de tiempo de solicitudes aprobadas (días)** se ignorará.

## <a name="independent-supply-regardless-of-coverage-code"></a>Suministro independiente, independientemente del código de cobertura

Las solicitudes de compra siempre están cubiertas por pedidos planificados independientes, independientemente del código de cobertura. Este comportamiento asegura una trazabilidad clara y flujos de trabajo entre las solicitudes de compra y los pedidos de reabastecimiento.

### <a name="example-1"></a>Ejemplo 1

Un producto está configurado para que tenga un valor de **Código de cobertura** de *Mínimo/máximo*. Tiene los siguientes estados de inventario y solicitud:

- Cantidad de inventario disponible = 10.
- Cantidad de inventario mínima = 15.
- Cantidad de inventario máxima = 20.
- Existe una solicitud de compra para una pieza. Tiene una fecha solicitada de hoy.

Cuando se ejecuta la planificación maestra, se crean dos órdenes planificadas: una para 10 piezas para reabastecer el inventario hasta la cantidad máxima y otra para una pieza para reabastecer la solicitud de compra.

### <a name="example-2"></a>Ejemplo 2

Un producto está configurado para que tenga un valor de **Código de cobertura** de *Mínimo/máximo*. Tiene los siguientes estados de inventario y solicitud:

- Cantidad de inventario disponible = 17.
- Cantidad de inventario mínima = 15.
- Cantidad de inventario máxima = 20.
- Existe una solicitud de compra para una pieza. Tiene una fecha solicitada de hoy.

Cuando se ejecuta la planificación maestra, se crea un pedido planificado para una pieza para reponer la solicitud de compra.

### <a name="example-3"></a>Ejemplo 3

Un producto está configurado para que tenga un valor de **Código de cobertura** de *Período* y una duración del período de siete días. Tiene los siguientes estados de inventario, pedido de ventas y solicitud:

- Cantidad de inventario disponible = 0.
- Existe un pedido de venta de cinco piezas. Tiene una fecha de envío prevista de hoy más un día.
- Existe una solicitud de compra para tres piezas. Tiene una fecha solicitada de hoy más tres días.

Cuando se ejecuta la planificación maestra, se crean dos órdenes planificadas: una para tres piezas para reabastecer la solicitud de compra y una para cinco piezas para reabastecer la demanda del pedido de ventas.

> [!NOTE]
> Después de que se firme una orden planificada que está vinculada a una solicitud de compra, el motor de planificación mantiene el diagrama de árbol a la solicitud de compra. Si posteriormente se descubre que en el pedido firme falta alguna cantidad necesaria para cumplir con la solicitud de compra, el sistema creará un nuevo pedido planificado por la diferencia.

Para obtener más información sobre las solicitudes de compra, consulte [Descripción general de la solicitud de compra](../../procurement/purchase-requisitions-overview.md).


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]