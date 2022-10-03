---
title: Planificación y programación de la capacidad finita
description: La planificación y programación de la capacidad finita le ayuda a comprender cuánto trabajo se puede producir durante un período específico cuando se tienen en cuenta las limitaciones de los diferentes recursos.
author: t-benebo
ms.date: 09/19/2022
ms.topic: article
ms.search.form: ReqParameters, ReqPlanSched, WrkCtrTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2022-09-19
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: c5eebe9ef6258b43daa7c7007ee28b0278fe5b09
ms.sourcegitcommit: 1a7729a6ce4f3fcf68bdc4cfdad746a5553da3c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573142"
---
# <a name="finite-capacity-planning-and-scheduling"></a>Planificación y programación de la capacidad finita

[!include [banner](../../includes/banner.md)]

La capacidad finita es un enfoque que le ayuda a comprender cuánto trabajo se puede producir durante un período específico cuando se tienen en cuenta las limitaciones de los diferentes recursos. El propósito de la programación de capacidad finita es garantizar que el trabajo avance a un ritmo uniforme y eficiente en toda la planta.

La planificación y programación de la capacidad finita crea un programa más realista para los procesos de producción que el que crea el enfoque de carga infinita. Si no hay suficiente capacidad en los recursos, la fecha de entrega se retrasará y el trabajo se programará cuando haya suficiente capacidad.

## <a name="planning-optimization-support-for-finite-capacity-planning"></a>Compatibilidad de Optimización de planificación para planificación de la capacidad finita

La planificación y la programación de la capacidad finita funcionan casi de la misma manera, independientemente de si utiliza la optimización de la planificación o el motor de planificación incorporado. Sin embargo, la optimización de la planificación no utiliza el parámetro de límite temporal **Tiempo de cuello de botella**. Cuando utiliza la optimización de la planificación, los recursos de cuello de botella siempre se programan utilizando el mismo límite de tiempo que los recursos que no son de cuello de botella (como lo indica el límite de tiempo de capacidad finita).

## <a name="set-up-finite-capacity-functionality"></a>Configurar la funcionalidad de capacidad finita

Para usar la funcionalidad de capacidad finita, debe habilitar la planificación de capacidad globalmente y debe habilitar la planificación de capacidad finita tanto para el plan maestro donde desea usarla como para cada recurso donde se aplica. En el caso de los planes y recursos en los que se ha habilitado la capacidad finita, la programación de las órdenes de fabricación planificadas tendrá en cuenta la capacidad que ya se ha reservado. Los pedidos de producción planificados son programan desde la fecha de requisito. Si la capacidad no está disponible para cumplir con la programación óptima, el sistema intentará requerir los artículos de componentes en una fecha anterior. Si su capacidad puede cambiar a medida que cambian las necesidades (por ejemplo, cuando trabaja con turnos), no debe utilizar la funcionalidad de capacidad finita, porque los tiempos de procesamiento calculados no serán correctos. La programación solo tiene en cuenta la capacidad que ya está reservada para los recursos en los que la capacidad finita está habilitada. Al habilitar la capacidad finita para un recurso, es posible modificar el límite de tiempo de capacidad finita.

### <a name="activate-master-planning-parameters"></a>Activar parámetros de planificación maestra

Para usar la funcionalidad de capacidad finita, debe habilitar la planificación de capacidad en la página **Parámetros de planificación maestra**.

1. Vaya a **Planificación maestra \> Configuración \> Parámetros de planificación maestra**.
1. En la pestaña **Pedidos planificados** en la sección **Planificación de capacidad**, configure la opción **Producción** a *Sí*.

### <a name="activate-a-master-plan"></a>Activar un plan maestro

Debe habilitar la planificación y programación de capacidad finita para cada plan maestro donde desee utilizarlo.

1. Vaya a **Planificación maestra \> Configurar \> Planes \> Planes maestros**.
1. En el panel de lista, seleccione un plan maestro que desee configurar para usar planificación y programación de capacidad finita.
1. En la pestaña desplegable **General** en la sección **Pedidos de producción planificados**, configure la opción **Capacidad finita** a *Sí*.
1. Repita los pasos 2 y 3 para cada plan maestro adicional en el que desee configurar.

### <a name="activate-resources"></a>Activar recursos

Debe habilitar la planificación y programación de capacidad finita para cada recurso donde desee utilizarlo.

1. Vaya a **Control de producción \> Configuración \> Recursos \> Capacidades de recursos**.
1. En el panel de lista, seleccione un recurso que desee configurar para usar planificación y programación de capacidad finita.
1. En la ficha desplegable **Operación**, en la sección **Botón de capacidad**, establezca la opción **Capacidad finita** en *Sí*.
1. Repita los pasos 2 y 3 para cada recurso adicional en el que desee configurar.

## <a name="examples"></a>Ejemplo

Esta sección proporciona los siguientes ejemplos que muestran cómo trabajar con planificación y programación de capacidad infinita y finita:

- Ejemplo 1 – Planificación de capacidad infinita
- Ejemplo 2: planificación de capacidad finita con un límite de tiempo de un día
- Ejemplo 3: planificación de capacidad finita con un límite de tiempo de dos días

### <a name="preconditions"></a>Condiciones previas

Los tres ejemplos asumen las condiciones previas que se describen en esta sección.

El producto *Producto1* tiene una ruta que contiene las siguientes operaciones.

| N.º operación | Nombre de la operación | Recurso        | Tiempo de ejecución | Cantidad de proceso | Siguiente |
|---------------|----------------|-----------------|----------|--------------|------|
| 10            | Soldaduras        | Linea de soldadura    | 1        | 2            | 20   |
| 20            | Ensamblando     | Línea de ensamblaje | 1        | 4            |      |

Los trabajadores de su empresa trabajan en un turno durante ocho horas (8:00–16:00).

Hay un pedido de producción programada para *24 piezas* de *Producto1*. Tiene una fecha de entrega de *Hoy + 3 días*.

Como resultado de la planificación, el sistema carga los recursos de la siguiente manera:

- **Linea de soldadura:** Este recurso se carga desde *Hoy a las 8:00* hasta *Hoy + 1 a las 12:00*.
- **Línea de montaje:** Este recurso se carga desde *Hoy + 1 a las 12:00* hasta *Hoy + 2 a las 10:00*.

La siguiente ilustración muestra el diagrama de Gantt resultante (selecciónelo para una vista más grande).

[![Diagrama de Gantt que muestra las condiciones previas.](media/finite-examples-conditions-small.png "Diagrama de Gantt que muestra las condiciones previas")](media/finite-examples-conditions.png)

### <a name="example-1--infinite-capacity-planning"></a>Ejemplo 1 – Planificación de capacidad infinita

Este ejemplo muestra los resultados de la planificación cuando utiliza la planificación de capacidad infinita en lugar de la planificación de capacidad finita.

El plan maestro tiene la siguiente configuración relevante, que deshabilita la planificación de capacidad finita para el plan:

- **Capacidad finita:** *No*

La opción **Capacidad finita** también está configurada como *No* para ambos recursos relevantes para deshabilitar la planificación de capacidad finita para ellos:

- Linea de soldadura
- Línea de ensamblaje

Ahora agregue una nueva orden de venta para *8 piezas* de *Producto1* y ejecute el plan. Como resultado, el sistema carga la línea de soldadura desde *hoy a las 8:00* Hasta que *Hoy a las 12:00*. Una vez completadas las operaciones en la línea de soldadura, el sistema cargará la línea de ensamblaje desde *Hoy a las 12:00* hasta *Hoy a las 14:00*.

La siguiente ilustración muestra el diagrama de Gantt resultante (selecciónelo para una vista más grande).

[![Diagrama de Gantt que muestra un ejemplo de planificación de capacidad infinita.](media/finite-examples-example1-small.png "Diagrama de Gantt que muestra un ejemplo de planificación de capacidad infinita")](media/finite-examples-example1.png)

### <a name="example-2--finite-capacity-planning-with-a-time-fence-of-one-day"></a>Ejemplo 2: planificación de capacidad finita con un límite de tiempo de un día

Este ejemplo muestra los resultados de la planificación cuando utiliza la planificación de capacidad finita y un límite temporal de un día.

El plan maestro tiene los siguientes ajustes relevantes, que permiten la planificación de la capacidad finita y establecen un límite temporal para el plan:

- **Capacidad finita:** *Sí*
- **Límite temporal de capacidad finita:** *1*

La opción **Capacidad finita** también está configurada como *Sí* para ambos recursos relevantes para habilitar la planificación de capacidad finita para ellos:

- Linea de soldadura
- Línea de ensamblaje

Ahora agregue una nueva orden de venta para *8 piezas* de *Producto1* y ejecute el plan. Como resultado, el sistema carga la línea de soldadura desde *Hoy + 1 a las 8:00* hasta *Hoy +1 a las 12:00*. Una vez completadas las operaciones en la línea de soldadura, el sistema cargará la línea de ensamblaje desde *Hoy +1 a las 12:00* hasta *Hoy +1 a las 14:00*. El sistema considera la capacidad finita para un solo día.

La siguiente ilustración muestra el diagrama de Gantt resultante (selecciónelo para una vista más grande).

[![Gráfico de Gantt que muestra la planificación de capacidad finita con un límite de tiempo de un día.](media/finite-examples-example2-small.png "Gráfico de Gantt que muestra la planificación de capacidad finita con un límite de tiempo de un día")](media/finite-examples-example2.png)

### <a name="example-3--finite-capacity-planning-with-a-time-fence-of-two-days"></a>Ejemplo 3: planificación de capacidad finita con un límite de tiempo de dos días

Este ejemplo muestra los resultados de la planificación cuando utiliza la planificación de capacidad finita y un límite temporal de dos días.

El plan maestro tiene los siguientes ajustes relevantes, que permiten la planificación de la capacidad finita y establecen un límite temporal para el plan:

- **Capacidad finita:** *Sí*
- **Límite temporal de capacidad finita:** *2*

La opción **Capacidad finita** también está configurada como *Sí* para ambos recursos relevantes para habilitar la planificación de capacidad finita para ellos:

- Linea de soldadura
- Línea de ensamblaje

Ahora agregue una nueva orden de venta para *8 piezas* de *Producto1* y ejecute el plan. Como resultado, el sistema carga la línea de soldadura desde *Hoy + 1 a las 12:00* hasta *Hoy +1 a las 16:00*. Una vez completadas las operaciones en la línea de soldadura, el sistema cargará la línea de ensamblaje desde *Hoy +2 a las 8:00* hasta *Hoy +2 a las 10:00*. El sistema considera la capacidad finita para solo dos días.

La siguiente ilustración muestra el diagrama de Gantt resultante (selecciónelo para una vista más grande).

[![Gráfico de Gantt que muestra la planificación de capacidad finita con un límite de tiempo de dos días.](media/finite-examples-example3-small.png "Gráfico de Gantt que muestra la planificación de capacidad finita con un límite de tiempo de dos días")](media/finite-examples-example3.png)

> [!IMPORTANT]
> Siempre debe establecer el límite de tiempo de capacidad finita según sea necesario para satisfacer sus necesidades comerciales. Los ejemplos que se proporcionan en este artículo simplemente ilustran la funcionalidad. En realidad, un límite de tiempo de un solo día es probablemente demasiado bajo para la mayoría de los fabricantes que utilizan la planificación de capacidad finita.
