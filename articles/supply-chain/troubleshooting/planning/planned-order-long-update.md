---
title: Los pedidos planificados tardan mucho en actualizarse
description: Al actualizar la cantidad requerida y / o la fecha de entrega en un pedido planificado, generalmente se necesitan al menos 30 segundos por pedido para guardar la actualización
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: ccf3305cc18ea0ccf2ac3e9ca0dd507fd12a9da7
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477537"
---
# <a name="planned-orders-take-a-long-time-to-update"></a>Los pedidos planificados tardan mucho en actualizarse

## <a name="symptoms"></a>Síntomas

Al actualizar la cantidad requerida y / o la fecha de entrega en un pedido planificado, generalmente se necesitan al menos 30 segundos por pedido para guardar la actualización.

## <a name="resolution"></a>Resolución

Este es un problema conocido con el motor de planificación maestro integrado. Se debe a la explosión automática subyacente a través de la estructura de la lista de materiales durante las ediciones. Este problema se aborda en la Optimización de la planificación, donde un planificador puede actualizar y aprobar los pedidos relevantes y, cuando lo desee, activar una ejecución de planificación para actualizar los pedidos planificados para la estructura BOM subyacente.

Una forma de mejorar el rendimiento con el motor de planificación maestro integrado es hacer los pasos siguientes:

1. Vaya a **Planificación maestra \> Configurar \> Planes \> Planes maestros**.
1. Seleccione un tipo de plan.
1. Expanda la ficha desplegable **Límites de tiempo en días**.
1. Establezca **Explosión** en *Sí* y establezca el campo debajo de esta configuración en 0 (cero).

> [!NOTE]
> Esto limitará el período de explosiones realizadas para este plan maestro a un solo día.
