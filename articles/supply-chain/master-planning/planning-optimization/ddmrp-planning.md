---
title: Planificación basada en la demanda
description: El artículo describe cómo generar pedidos planificados para artículos que se configuran como puntos de desacoplo.
author: t-benebo
ms.date: 06/30/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-06-30
ms.dyn365.ops.version: 10.0.28
ms.openlocfilehash: f1e2cfca47d507c8de7f9323bb8e4262a0e90949
ms.sourcegitcommit: 3e04f7e4bc0c29c936dc177d5fa11761a58e9a02
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2022
ms.locfileid: "9689214"
---
# <a name="demand-driven-planning"></a>Planificación basada en la demanda

[!include [banner](../../includes/banner.md)]
[!INCLUDE [preview-banner](../../includes/preview-banner.md)]
<!-- KFM: Preview until further notice -->

El artículo describe cómo generar pedidos planificados para artículos que se configuran como puntos de desacoplo.

## <a name="net-flow-and-qualified-demand"></a>Flujo neto y demanda calificada

Durante la planificación maestra, el sistema aplica el concepto de *flujo neto* para establecer la cantidad disponible efectiva basada en el inventario disponible real, más el inventario que está en pedido (pedidos de suministro existentes que aún no se han recibido), menos lo que se conoce como *demanda calificada* (próximas ventas calificadas), como se muestra en la siguiente ilustración. Cuando el sistema determina a qué zona de búfer pertenece un artículo y cuál debe ser la cantidad pedida, evalúa el flujo neto, no el inventario disponible real.

![Ejemplo de gráfico de cálculo de flujo neto.](media/ddmrp-net-flow-example.png "Ejemplo de gráfico de cálculo de flujo neto")

Cuando se desencadena un pedido planificado durante una ejecución de planificación, la cantidad pedida será el nivel máximo menos el flujo neto. Para asignar una prioridad de pedidos, el sistema utiliza la funcionalidad [planificación basada en prioridades](priority-based-planning.md) en lugar de fechas de requisitos. La planificación de requisitos de materiales basada en la demanda (DDMRP) asigna la prioridad de un pedido planificado en función de la cantidad pedida como porcentaje del inventario máximo. En la ilustración anterior, la cantidad pedida es el 53 por ciento de la cantidad máxima. Por tanto, la prioridad de pedido para el reabastecimiento será 53. (Para dar contexto, 0 es la prioridad más alta y 100 es la prioridad más baja).

*Demanda calificada* es la demanda vencida, más la demanda actual, más los picos de pedidos calificados en el futuro. La siguiente ilustración muestra un ejemplo de los niveles de demanda para hoy (12 de junio) y los próximos tres días. DDMRP le permite establecer un umbral de pico de pedidos para identificar la demanda que supera las expectativas normales. Si el umbral se establece en 25 piezas, dos de las fechas futuras que se muestran en la ilustración calificarán como picos de pedidos. Debe asignar un umbral de aumento de pedidos para cada producto de forma individual utilizando su página **Cobertura de artículos**, como se describe en [Configurar búferes para un elemento de punto de desacoplo](ddmrp-buffer-profile-and-levels.md#set-up-buffers).

![Ejemplo de gráfico de cálculo de demanda calificada.](media/ddmrp-net-qualified-demand-example.png "Ejemplo de gráfico de cálculo de demanda calificada")

Siempre que no haya demanda vencida, ahora puede agregar la demanda de hoy (18) a las cantidades de los dos picos de pedidos (29 y 26) para obtener una demanda calificada de 73. Aunque hay demanda para el 23 de junio, tenga en cuenta que no se incluye en el cálculo del flujo neto, porque DDMRP desencadena el pedido planificado de forma diferente a los grupos de cobertura de planificación tradicionales.

## <a name="generating-planned-orders-with-ddmrp"></a>Generación de pedidos planificados con DDMRP

Durante una ejecución de planificación, el sistema creará un nuevo pedido planificado si el flujo neto de un artículo cae por debajo del punto de realización de nuevo pedido. Cuando utilice DDMRP, normalmente realizará una ejecución de planificación todos los días. Por tanto, básicamente está revisando sus niveles de inventario una vez al día para determinar qué artículos deben reabastecerse.

La siguiente ilustración muestra un ejemplo de situación en la que tiene un pedido de 18 piezas el 20 de junio, 29 piezas el 21 de junio, 26 piezas el 22 de junio y 20 piezas el 23 de junio. Dado que el umbral de pico se establece en 25 piezas, dos de estos pedidos se marcan como picos. Hay 220 piezas de este artículo disponibles.

![Ejemplo de planificación 1.](media/ddmrp-planning-example-1.png "Ejemplo de planificación 1")

Si ejecuta la planificación maestra ahora, generará un pedido planificado si se encuentra que el flujo neto cae por debajo del punto de realización de nuevo pedido (219 piezas en este ejemplo).

![Ejemplo de planificación 2.](media/ddmrp-planning-example-2.png "Ejemplo de planificación 2")

Este ejemplo genera un pedido de compra planificado para una cantidad de 130, que equivale al nivel máximo menos el flujo neto. Al pedido planificado se le asigna una prioridad de 53,07, en función de su porcentaje de la cantidad máxima. Dado que estos valores se encontraron el 20 de junio, el sistema crea un pedido planificado con fecha del 20 de junio más el plazo de entrega desacoplado del artículo (cinco días hábiles en este ejemplo). Por tanto, dado que cinco días hábiles son una semana a partir de hoy, la orden planificada tiene la fecha del 27 de junio.

> [!NOTE]
> Optimización de planificación calcula solo los elementos desacoplados mediante DDMRP. Todos los demás artículos se calculan utilizando la planificación estándar de requisitos de material (MRP).
