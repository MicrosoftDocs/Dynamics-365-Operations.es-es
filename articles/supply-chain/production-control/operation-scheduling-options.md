---
title: Opciones de programación de las operaciones
description: Este tema describe las opciones de programación de las operaciones. Puede usar la programación de operaciones para proporcionar una estimación general del tiempo extra del proceso de producción.
author: ChristianRytt
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ProdSchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 198123
ms.assetid: d680d7be-da64-4132-89fe-ad2fa59afb77
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 32d15a4c2f2ec550d4a0b5436add2963b5636acf8f2b8ba8231ceeab16bb0929
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6776323"
---
# <a name="operations-scheduling-options"></a>Opciones de programación de las operaciones

[!include [banner](../includes/banner.md)]

Este tema describe las opciones de programación de las operaciones. Puede usar la programación de operaciones para proporcionar una estimación general del tiempo extra del proceso de producción.

La programación de operaciones calcula la siguiente información de un pedido de producción:

-   Se establecen fechas de inicio y fin para el pedido de producción y para cada operación.
-   Se asignan recursos a las operaciones.

Varias configuraciones determinan cómo se calculan los programas de producción. Puede definir estos valores en la página **Programación de operaciones**. La información siguiente describe las opciones de programación.

## <a name="operations-scheduling"></a>Programación de operaciones
### <a name="scheduling-direction"></a>Dirección de programación

La dirección de programación es indispensable en el proceso de programación. La producción se puede programar hacia adelante o hacia atrás a partir de cualquier fecha, en función de los requisitos de tiempo y programación.

-   **A partir de la fecha de programación:** puede programar la producción para que se inicie lo antes posible. La producción puede iniciarse hoy, mañana o en cualquier fecha concreta en el futuro. La producción está programada para comenzar lo antes posible y se planifica hacia adelante en el tiempo hasta la fecha final más próxima posible.
-   **Programación regresiva**: puede programar la producción para que se inicie lo más tarde posible. El programa se basa en la fecha en que debe completarse la producción y cuenta hacia atrás hasta la última fecha posible en que puede iniciarse la producción sin que supere la fecha límite objetivo.

Están disponibles las siguientes opciones:

-   **Remitir a partir de hoy**: se programa hacia adelante desde la fecha actual. (La fecha actual es la fecha del sistema.)
-   **Remitir a partir del inicio programado**: se programa a partir de una fecha de inicio más temprana. Si no hay una programación anterior, la dirección del programa es a partir de la fecha actual.
-   **A partir de la fecha de programación**: se programa a partir la fecha de programación especificada en el campo **Fecha de programación**. Si no especifica una fecha de programación, la dirección de la programación es a partir de la fecha actual.
-   **Regresivo desde la fecha de entrega**: se programa desde la fecha de entrega que se especifica para el pedido de producción. Si selecciona esta opción, pero no se ha especificado ninguna fecha de entrega, la fecha de entrega es la fecha actual.
-   **Regresivo desde el final programado**: la programación retrocede desde una fecha de finalización anteriormente calculada. Si no hay una programación anterior, la fecha final es la fecha actual.
-   **Regresivo desde la fecha de programación**: se programa desde la fecha de programación especificada en el campo **Fecha de programación**. Si no especifica una fecha de programación, se usa la fecha actual. La regresión desde la fecha de programación se calcula para el pedido de producción la última vez que se calcula un requisito. Si no se especifica una fecha para el pedido de producción, se usa la fecha actual del sistema.
-   **Regresivo desde fechas futuras**: se programa desde fechas futuras que se han calculado para el pedido de producción para el que se calculó por última vez un requisito. Si no se especifica una fecha futura para el pedido de producción, se usa la fecha actual del sistema.
-   **Como la última programación**: la dirección y la fecha de la programación seleccionada se guardan para programar operaciones y trabajos. Por lo tanto, puede seleccionar esta opción para posteriores programaciones. Si no existe una programación previa del pedido de producción, la programación es regresivo a partir de la fecha actual del sistema.
-   **Remitir a partir de mañana**: la programación se realiza a partir de la fecha actual más un día.
-   **Hacia delante a partir del trabajo anterior**: esta función solo es importante en la programación de trabajos. Si selecciona esta dirección de programación para programar operaciones, el pedido de producción se programa hacia delante a partir de la fecha actual. En la programación de trabajos, la programación se establece para un trabajo y todos los demás trabajos del pedido de producción se programan según ese trabajo.
-   **Regresivo desde el trabajo anterior**: esta función solo es importante en la programación de trabajos. Si selecciona esta dirección de programación para programar operaciones, los pedidos planificados se programan hacia atrás desde la fecha actual. En la programación de trabajos, la programación se establece para un trabajo y todos los demás trabajos del pedido de producción se programan según ese trabajo.

### <a name="scheduling-date"></a>Fecha de programación

Esta fecha se utiliza para las direcciones de programación **a partir de la fecha de programación** y desde las **regresivas desde la fecha de programación**. De este modo, la programación se realiza hacia delante o hacia atrás a partir de dicha fecha. Para obtener más información, vea la sección anterior, "Dirección de programación."

### <a name="recalculate-bom-levels"></a>Volver a calcular niveles de L. MAT.

Cuando selecciona **Recalcular niveles de la lista de materiales (BOM)**, los niveles de BOM seleccionados se calcularán de nuevo para ayudar a garantizar el orden correcto de la programación.

## <a name="limitations"></a>Limitaciones
### <a name="finite-capacity"></a>Capacidad limitada

La programación depende de la disponibilidad de los recursos requeridos para poder completar la producción. Si no hay capacidad suficiente, se pueden retrasar e incluso detener los pedidos de producción. Si se aplica la capacidad limitada a la programación de operaciones, se tendrán en cuenta las reservas de capacidad hechas en los recursos, y esa capacidad se considerará no disponible. El pedido de producción se programa según la disponibilidad de la capacidad de los recursos requeridos. La programación de operaciones usa una secuencia específica para determinar el orden de las operaciones de la ruta de producción. La programación de operaciones reserva capacidad en los grupos de recursos en función de los tiempos de operación definidos en la ruta de producción. La capacidad del grupo de recursos es el total de capacidad disponible entre todos los recursos.

### <a name="finite-material"></a>Material limitado

La programación también depende de la disponibilidad de los materiales necesarios para la producción. Si no hay componentes suficientes, también es posible que se retrase la producción. La programación también se puede basar en el uso de materiales. Simplemente especifique los materiales que deben estar disponibles para la producción en lugar de los materiales que no son críticos. Este tipo de programación se conoce como programación con material limitado. Al seleccionar materiales limitados, la producción se programa según si los materiales están disponibles o no. **Nota:** Si optimiza tanto la capacidad como los materiales, la producción se calcula para cumplir ambas restricciones. Se tiene en cuenta la disponibilidad de capacidad y materiales, y las operaciones del pedido de producción no pueden programarse para iniciarse hasta que la capacidad y los materiales estén disponibles al mismo tiempo y en las cantidades necesarias. Activar esta casilla de verificación si los materiales se deberían considerar limitados durante la programación. Si hay límites en los materiales, se tendrá en cuenta la cobertura del material para ese momento. Es decir, la programación tiene en cuenta las fechas futuras calculadas para los artículos. La programación reserva materias primas y expande la producción actual. Si la programación tiene lugar varias veces, la primera programación será la que ejecute una expansión y realice las reservas. Si realiza cambios en la lista de materiales de producción o en la ruta, la siguiente programación ejecutará una expansión. Para dicha expansión, se asume que los materiales se necesitan el mismo día. Dado que la producción no se programa en el momento de la expansión de la programación maestra, la fecha actual es la estimación más precisa del momento en que los artículos estarán disponibles. Luego, la expansión comprueba si los artículos están disponibles. Si los artículos están disponibles, es posible satisfacer el requisito de producción. Si los artículos no están disponibles para la fecha actual, se generará un pedido planificado y se realizará una selección de contrapartida para el mismo. Si la puesta en firme automática está establecida para el pedido planificado, el pedido planificado se pone en firme de manera automática para la compra o la producción. El estado de la producción cambiará automáticamente al estado especificado en el campo **Estado de producción solicitado** del cuadro de diálogo **Grupos de cobertura**. Si se desactiva la casilla, los materiales siempre se consideran disponibles. Por lo tanto, la programación no tiene en cuenta si los materiales están disponibles en el momento en el que se necesitan.

### <a name="finite-property"></a>Propiedad limitada

Activar esta casilla de verificación si la programación de trabajos debe incluir los requisitos de propiedad.

### <a name="keep-production-unit"></a>Conservar unidad de producción

Seleccionar si el motor de programación solo debe programar recursos que ya estén especificados en la unidad de producción.

### <a name="keep-warehouse-from-resource"></a>Conservar almacén del recurso

Seleccionar si el motor de programación solo debe programar recursos que estén asociados con el almacén de entrada especificado en el recurso.

## <a name="references"></a>Referencias
### <a name="schedule-references"></a>Programar referencias

Cuando las referencias dependen de las órdenes de producción, también se denominan subproducciones. Las subproducciones pueden programarse como parte de la programación de un pedido de producción. Seleccione esta casilla si la programación de subproducciones se basa en la programación de la producción principal. En relación con la producción principal, las producciones superpuestas se programan hacia delante y las subyacentes hacia atrás. Las referencias del pedido de producción se pueden ver en el campo del **Nivel de referencia** en la página **Pedidos de producción**.

### <a name="synchronize-references"></a>Sincronizar las referencias

También puede sincronizar las referencias con el pedido de producción. Si se selecciona esta opción, las fechas de las subproducciones se modificarán y alinearán cuando se efectúen cambios en la programación del pedido de producción. Si un pedido de producción tiene una o más subproducciones, se recomienda programar dichas subproducciones junto con la producción principal. En este caso, la producción principal no puede iniciarse hasta que se hayan terminado las subproducciones relacionadas. Por lo tanto, seleccione esta casilla si la programación de subproducciones se basa en los tiempos de inicio y fin de la producción seleccionada. Puede seleccionar esta casilla solo si la casilla de las **Referencias de la programación** también se ha seleccionado.

## <a name="cancellation"></a>Cancelación
### <a name="cancel-queue-time"></a>Cancelar el tiempo en cola

Active esta casilla de verificación para excluir el tiempo en la cola de la programación.

### <a name="cancel-setup"></a>Cancelar la configuración

Active esta casilla de verificación para excluir el tiempo de configuración de la programación.

### <a name="cancel-process"></a>Cancelar el proceso

Active esta casilla de verificación para excluir el tiempo de ejecución de la programación.

### <a name="cancel-overlap"></a>Cancelar la superposición

Active esta casilla de verificación para excluir el tiempo de superposición de la programación.

### <a name="cancel-transport"></a>Cancelar transporte

Active esta casilla de verificación para excluir el tiempo de tránsito de la programación.

## <a name="set-default"></a>Establecer predeterminado
Puede guardar los valores actuales como valores predeterminados. Existen dos opciones:

-   Establecer como mi valor predeterminado
-   Establecer como predeterminado para todos


## <a name="additional-resources"></a>Recursos adicionales

[Programación de operaciones](operations-scheduling.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]