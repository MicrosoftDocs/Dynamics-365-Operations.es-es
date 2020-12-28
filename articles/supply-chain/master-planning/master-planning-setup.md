---
title: Configurar planificación maestra
description: En este tema se describen distintas estrategias y parámetros importantes que se utilizan para configurar una planificación maestra.
author: t-benebo
manager: tfehr
ms.date: 07/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-05-31
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: a74d2987eac7409b5f576a52eccc37cf29566c7b
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436667"
---
# <a name="set-up-master-planning"></a>Configurar planificación maestra

[!include [banner](../includes/banner.md)]

En este tema se describen distintas estrategias y parámetros importantes que se utilizan para configurar una planificación maestra. Incluye una visión general de los tipos de planes que utiliza una planificación maestra y explica qué estrategia del plan debe utilizar, según sus requisitos empresariales. También describe los principales parámetros que afectan al plan y explica cómo afectan esos parámetros a los pedidos planificados que se sugieren.

## <a name="types-of-master-plans"></a>Tipos de planes maestros

La planificación maestra tiene dos tipos de planes: estático y dinámico. Cada tipo está diseñado para un uso diferente. Para lograr el mayor rendimiento, le recomendamos que utilice el plan adecuado para su escenario.

### <a name="static-plan"></a>Plan estático

El plan estático permanece sin modificar, independientemente de cualquier cambio en el suministro y la demanda, hasta la próxima vez que se ejecute esa planificación maestra.

El plan estático se utiliza para aprobar y poner en firme los pedidos sugeridos. Se trata de un plan operativo que varios miembros del personal de la empresa (como el comprador o el encargado de la planificación de producción) pueden utilizar para basar sus decisiones en él y realizar sus actividades y tareas diarias.

El plan estático también admite la regeneración. Se calcula un plan nuevo y totalmente optimizado cada vez que se ejecute esa planificación maestra, y se eliminan los pedidos existentes que no se han aprobado.

### <a name="dynamic-plan"></a>Plan dinámico

El plan dinámico suele iniciarse como una copia del plan estático, pero se puede actualizar cada vez que cambian los datos maestros. Por ejemplo, si los datos cambian, se crea un nuevo pedido de ventas.

El plan dinámico se utiliza para una planificación ad hoc. Permite a la empresa supervisar la red de pedido de cambio y la disponibilidad de artículos sin alterar el plan estático que otras personas utilizan para sus procesos de trabajo. Se utiliza especialmente para el tipo capaz de comprometer (CTP). El plan dinámico es el plan predeterminado cuando los requisitos netos se abren desde las páginas del pedido (como páginas de pedido de ventas, pedido de compra o pedido de producción).

El plan dinámico utiliza el cambio neto. Por lo tanto, ayuda a garantizar un tiempo de ejecución más rápido.

## <a name="strategies-for-using-master-plans"></a>Estrategias para utilizar planes maestros

En la planificación maestra puede usar uno o dos planes. La estrategia que utilice depende de sus requisitos empresariales.

### <a name="one-plan-strategy"></a>Estrategia de un plan

Para la estrategia de un plan, utilice el mismo plan maestro para el plan estático y el plan dinámico. Esta estrategia se emplea para escenarios de existencias, en los que normalmente no tiene que simular un plan que satisfaga un pedido.

La estrategia de un plan suele utilizarse en sectores minoristas y de distribución, o en los que se confirman las fechas de entrega de ventas basadas en contratos de nivel de servicio (SLA) o en plazos. Para el plan, el control de la fecha de entrega se puede utilizar sin CTP.

Si debe hacer una simulación, el plan se puede volver a ejecutar para los artículos que requieren la simulación. Los pedidos planificados que producen simulaciones de pedidos suelen estar en firme.

### <a name="two-plan-strategy"></a>Estrategia de dos planes

Para la estrategia de dos planes, utilice un plan estático y un plan dinámico diferente. La estrategia de dos planes se suele emplearse para escenarios tipo configuración a pedido y fabricación sobre pedido, donde debe hacer simulaciones de pedidos de ventas y calcular las fechas de entrega exactas para dichos pedidos, pero los cálculos no deben afectar a las operaciones diarias. Estas simulaciones se realizan siempre en el plan dinámico. Por ejemplo, la estrategia de dos planes es útil en los sectores automotriz y de fabricantes de equipo original (OEM).

Para la estrategia de dos planes, se puede utilizar el control de fecha de entrega de tipo CTP. Cuando se usa CTP, se activa automáticamente la ejecución en el plan dinámico.

### <a name="setting-up-the-plans"></a>Configuración de los planes

Puede crear planes en la página **Planes maestros** (**Planificación maestra \> Configuración \> Planes \> Planes maestros**).

Puede especificar qué planes se utilizarán para el plan estático y el plan dinámico estableciendo los campos **Plan maestro estático actual** y **Plan maestro dinámico actual** en la página **Parámetros de planificación maestra** (**Planificación maestra \> Configuración \> Parámetros de planificación maestra**). Para usar una estrategia de un plan, seleccione el mismo plan en los campos **Plan maestro estático actual** y **Plan maestro dinámico actual** .

## <a name="types-of-planning-methods"></a>Tipos de métodos de planificación

Se pueden usar tres métodos de cálculo para ejecutar la planificación maestra: regeneración y cambio neto. Cada método produce un plan diferente cuando se ejecuta.

Especifique el método de planificación en el cuadro de diálogo **Ejecución de la planificación maestra**. Para abrir este cuadro de diálogo, vaya a **Planificación maestra \> Planificación maestra \> Ejecutar \> Planificación maestra**, o seleccione **Ejecutar** en el espacio de trabajo **Planificación maestra**.

### <a name="regeneration"></a>Regeneración

El método de planificación de regeneración elimina los pedidos planificados existentes, a menos que esteń en firme. Genera nuevos pedidos planificados, en función de todos los requisitos. La regeneración es el único método de planificación que está disponible para los planes estáticos.

- Se tienen en cuenta los cambios en el suministro. Estos cambios incluyen cambios en la previsión.
- Este método respeta el código de cobertura **Período**.
- Este método admite la funcionalidad de sustitución de productos (PI).

### <a name="net-change"></a>Cambio neto

El método de planificación de cambio neto genera pedidos planificados para cubrir los requisitos que se han creado o cambiado desde la última ejecución de la planificación maestra. Los cambios en el suministro no se tienen en cuenta cuando se ejecuta este método. El sistema no considera los nuevos suministros, y los pedidos planificados que se crearon anteriormente no se eliminan si ya no se necesitan. El método de planificación de cambio neto se ejecuta más rápido que el método de regeneración. Solo está disponible para planes dinámicos.

- Las fechas de acción y las fechas futuras se actualizan para todos los requisitos.
- Este método no respeta el código de cobertura **Período**.
- Este método no satisface la previsión, incluso si se selecciona en el plan.
- Este método no admite la funcionalidad de sustitución de productos (PI).

### <a name="net-change-minimized"></a>Cambio neto minimizado

El método de planificación de cambio neto minimizado genera pedidos planificados para cubrir solo los requisitos que se han creado o cambiado desde la última ejecución de la programación de la planificación maestra. Para este método, a diferencia del método de cambio neto, las fechas de acción y las fechas futuras se actualizan solo para los requisitos nuevos o cambiados. Este método de planificación solo está disponible para los planes dinámicos.

## <a name="types-of-scheduling-methods"></a>Tipos de métodos de programación

Para cada plan, en la ficha desplegable **General** de la página **Planes maestros** (**Planificación maestra \> Configuración \> Planes \> Planes maestros**), debe seleccionar el método de programación que se utiliza para los pedidos de producción. Puede programar la producción en el nivel de operación y en el nivel de trabajo.

### <a name="operations-scheduling"></a>Programación de operaciones

Puede usar la programación de operaciones para proporcionar una estimación general del tiempo extra del proceso de producción. La programación de operaciones no expande las operaciones de la ruta de producción en trabajos. Para obtener más información sobre la programación de operaciones, consulte [Programación de operaciones](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/operations-scheduling).

### <a name="job-scheduling"></a>Programación de trabajos

La programación de trabajos es un método de programación más detallado, en el que cada operación se divide en sus tareas o trabajos individuales. La programación de trabajos incluye información acerca de capacidad. Se utiliza normalmente para programar trabajos individuales en la planta para un período de tiempo inmediato o a corto plazo. Para obtener más información sobre la programación de trabajos, consulte [Programación de trabajos](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/job-scheduling).

## <a name="time-fences-in-days"></a>Límites de tiempo en días

Para cada plan, puede seleccionar hasta qué punto la planificación maestra debe calcular los distintos requisitos y otras consideraciones. El período se conoce como *límite de tiempo*. Para obtener el mayor rendimiento en la planificación maestra, le recomendamos que ajuste los distintos límites de tiempo para cumplir los requisitos empresariales. Para cada plan, puede encontrar los límites de tiempo en la ficha desplegable **Límites de tiempo en días** de la página **Planes maestros** (**Planificación maestra \> Configuración \> Planes \> Planes maestros**).

> [!NOTE]
> Los límites de tiempo indican hasta qué punto en el futuro la planificación maestra calcula los distintos requisitos y otras consideraciones. Los límites de tiempo seleccionados en esta página anularán los límites de tiempo definidos en el grupo de cobertura. Esto significa que si establece una opción del límite de tiempo en Sí y define los días se anulará el límite de tiempo definido en el grupo de cobertura. Cuando se establece en No, el límite de tiempo se definirá en el grupo de cobertura. Finalmente, si no desea o necesita utilizar una opción (por ejemplo, no desea usar mensajes de acción), establézcalo en **Sí** y, seguidamente, establezca el límite de tiempo en **0** (cero) días.

### <a name="coverage"></a>Cobertura

El límite de tiempo de cobertura representa el período de programación, o bien hasta dónde debe incluirse la demanda. Es decir, indica el horizonte de su planificación.

Al establecer la opción **Cobertura** en **Sí**, puede anular el límite de tiempo de cobertura definido para el artículo durante la programación maestra. En este caso, especifique el número de días durante los que el cálculo de la programación maestra debe cubrir los requisitos. El límite de tiempo de cobertura se calcula en adelante desde la fecha actual. Los requisitos que se produzcan antes de la fecha actual siempre se procesan.

> [!NOTE]
> Para obtener el mayor rendimiento en la planificación maestra, le recomendamos que ajuste el límite de tiempo de cobertura al horizonte de su planificación.

### <a name="freeze"></a>Congelar

El límite de tiempo congelado representa el período en el que los pedidos planificados existentes no se cambian cuando se ejecuta una nueva programación maestra. Los pedidos planificados están congelados y no se sugerirán nuevos pedidos planificados.

Al establecer la opción **Congelar** en **Sí**, puede anular el límite de tiempo congelado que se define para el artículo durante la programación maestra. En este caso, especifique el número de días durante los que se debe congelar la actividad de planificación. No olvide que, durante este período, no se generan pedidos planificados nuevos y los pedidos planificados existentes no se pueden cambiar.

### <a name="firming"></a>Puesta en firme

El límite de tiempo de puesta en firme indica el horizonte de tiempo en el que los pedidos planificados se convierten automáticamente en pedidos de producción y de compra. Este proceso también se conoce como *puesta en firme automática de pedidos planificados*.

Al establecer la opción **Puesta en firme** en **Sí**, puede anular el límite de tiempo de puesta en firme que se define para el artículo durante la programación maestra. En este caso, especifique el número de días durante los que los pedidos de producción y de compra planificados deben ponerse en firme automáticamente. El límite de tiempo de puesta en firme se calcula en adelante desde la fecha de programación maestra. La puesta en firme automática de un pedido de compra planificado solo puede producirse si el artículo se asocia a un proveedor.

### <a name="forecast-plan"></a>Plan de previsión

El límite de tiempo del plan de previsión indica hasta qué punto en el futuro la planificación maestra crea pedidos planificados para artículos que tienen una demanda prevista.

Al establecer la opción **Plan de previsión** en **Sí**, puede anular el límite de tiempo del plan de previsión definido para el artículo durante la programación maestra. En este caso, especifique el número de días durante los que debe incluirse la previsión de ventas desde el plan de previsión en la planificación maestra.

### <a name="capacity"></a>Capacidad

El límite de tiempo de capacidad indica hasta qué punto en el futuro el sistema tiene en cuenta la capacidad máxima de sus recursos al programar pedidos. Es decir, el plan programa los pedidos de producción mediante la ruta de producción para los artículos, y considera los recursos de la ruta de producción y la capacidad máxima de cada recurso.

Al establecer la opción **Capacidad** en **Sí**, puede anular el límite de tiempo de capacidad definido para el artículo durante la programación maestra. En este caso, especifique el número de días durante el que la capacidad debe planificarse para los pedidos de producción planificados. La programación maestra utiliza la ruta de producción activa del artículo y programa hacia atrás desde la fecha de requisito. Si la fecha de requisito de un pedido de producción planificado está fuera del límite de tiempo de capacidad, el plazo se determina en función de la hora de entrega del artículo. El límite de tiempo de capacidad se calcula en adelante desde la fecha actual.

### <a name="action-message"></a>Mensaje de acción

Los mensajes de acción sugieren cambios que se pueden hacer en el pedido de suministro existente para ayudar a optimizar el plan de suministro. Por ejemplo, es posible que recomienden que adelante o posponga pedidos, o que aumente o reduzca las cantidades de pedido.

Al establecer la opción **Mensaje de acción** en **Sí**, puede anular el límite de tiempo del mensaje de acción definido para el artículo durante la programación maestra. En este caso, especifique el número de días durante los que la programación maestra debe generar mensajes de acción para los requisitos. El límite de tiempo de mensajes de acción se calcula en adelante desde la fecha actual.

Para obtener más información acerca de los mensajes de acción, consulte [Mensajes de acción](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/master-planning/action-messages).

> [!NOTE]
> El cálculo de mensajes de acción provoca un mayor tiempo de ejecución para la planificación maestra. Si los mensajes de acción no se analizan y aplican de forma periódica (a diario, cada semana, etc.), considere desactivar el cálculo durante la ejecución de la planificación maestra. Para desactivar el cálculo, en la página **Planes maestros**, establezca el límite de tiempo **Mensaje de acción** en **0** (cero) para el plan maestro que está ejecutando. Asegúrese también de que la configuración **Mensaje de acción** está desactivada para todos los grupos de cobertura.

### <a name="calculated-delays"></a>Retrasos calculados

Puede especificar hasta qué punto en el futuro se detectan y notifican los posibles retrasos en pedidos planificados. De esta manera, puede programar posibles fechas de entrega (retrasadas).

Si un pedido planificado no se puede cumplir para la fecha solicitada, se planifica para la fecha de cumplimiento más temprana para una transacción, en función de los plazos y la disponibilidad de capacidad y material.

### <a name="approved-requisitions-time-fence"></a>Límite de tiempo de solicitudes aprobadas

Puede configurar la planificación maestra para crear pedidos planificados para la demanda de solicitud. Establezca la opción **Incluir solicitudes** en **Sí** en la ficha desplegable **General** de la página **Planes maestros**. A continuación, cuando el propósito de una solicitud aprobada es el reabastecimiento, la planificación maestra crea automáticamente un pedido planificado correspondiente para satisfacerlo. El método de reabastecimiento se determina según las directivas de suministro configuradas para los artículos en su organización. Después de crear y aprobar la solicitud de reabastecimiento, no se requiere ninguna acción adicional del usuario.

Al establecer la opción **Límite de tiempo de solicitudes aprobadas** en **Sí** en la ficha desplegable **Límites de tiempo en días**, puede anular el límite de tiempo de solicitudes aprobadas definido para el artículo durante la programación maestra. En este caso, especifique el número de días en el pasado que debería incluirse la demanda de solicitudes aprobadas con fines de reabastecimiento en la programación maestra. Por ejemplo, puede especificar que solo deben considerarse y planificarse las demandas incumplidas o vencidas de solicitudes aprobadas que se han creado durante los últimos 10 días.

### <a name="sequencing"></a>Secuenciación

La secuenciación permite organizar los pedidos planificados en función de los atributos de secuenciación asociados al producto terminado. Con frecuencia se utiliza preparar pedidos de producción para su embalaje. Por ejemplo, se puede usar para empaquetar cajas en una secuencia determinada, según el color y el tamaño.

Al establecer la opción **Secuenciación** en **Sí**, puede especificar hasta qué punto en el futuro se debe establecer la secuencia de las operaciones o los trabajos. Tenga presente que cuanto mayor sea el límite de tiempo, más tardará en ejecutarse la planificación maestra.

### <a name="calculated-delays"></a>Retrasos calculados

La opciones de retraso ayudan a garantizar que los pedidos tengan fechas planificadas viables. Las siguientes opciones están disponibles en la ficha desplegable **Retrasos calculados** de la página **Planes maestros**:

- **Asegurarse de que los pedidos planificados no se crean antes de la fecha de ejecución de la planificación maestra**: establezca esta opción **Sí** para ayudar a garantizar que los pedidos no se pueden programar para fechas en el pasado.
- **Agregar el retraso calculado a la fecha de requisito** (en **Pedidos de compra planificados**): establezca esta opción en **Sí** para agregar el retraso calculado para los requisitos.
- **Agregar el retraso calculado a la fecha de requisito** (en **Pedidos de producción planificados**): establezca esta opción en **Sí** para agregar el retraso calculado para los requisitos.
- **Agregar el retraso calculado a la fecha de requisito** (en **Transferencia planificada**): establezca esta opción en **Sí** para agregar el retraso calculado para los requisitos.
- **Agregar el retraso calculado a la fecha de requisito** (en **Kanban planificado**): establezca esta opción en **Sí** para agregar el retraso calculado para los requisitos.

Al establecer las opciones **Agregar el retraso calculado a la fecha de requisito** en **Sí** para agregar los retrasos en los requisitos, el sistema tiene en cuenta la capacidad de los recursos y crea pedidos planificados y viables. El recálculo de las fechas del pedido planificado aumenta el tiempo de ejecución para la planificación maestra. Por lo tanto, si no necesita utilizar los retrasos, establezca las opciones en **No**.

## <a name="positive-and-negative-days"></a>Días positivos y negativos

Los días positivos y negativos afectan a cómo la planificación maestra sugiere pedidos y acciones planificadas. Los días positivos y negativos se establecen en el grupo de cobertura del artículo. Puede definir los diversos grupos de cobertura y establecer sus parámetros en la página **Grupos de cobertura** (**Planificación maestra \> Configuración \> Cobertura \> Grupos de cobertura**).

### <a name="positive-days"></a>Días positivos

Los días positivos indican hasta qué punto en el futuro la planificación maestra tiene en cuenta el inventario o las recepciones actuales para satisfacer una demanda futura. Por ejemplo, si los días positivos se establecen en **100**, el inventario actual se puede utilizar para satisfacer la demanda en los próximos 100 días. Si hay un pedido 150 días después de la fecha actual, la planificación maestra creará un pedido planificado para satisfacer esa demanda, aunque el inventario disponible para el artículo puede satisfacer el pedido. Para los artículos de alta rotación que tienen un plazo corto, es posible que no desee usar el inventario disponible para un pedido que es lejano en el futuro. En este caso de alta rotación, el inventario disponible actual se agotará rápidamente, y se pueden pedir más pedidos en el futuro para satisfacer una demanda futura en el tiempo, que sería posible gracias al plazo corto del artículo.

Los días positivos también afectan a los mensajes de acción. Por ejemplo, puede que el sistema le recomiende que aumente un pedido de compra planificado para que incluya una demanda que se encuentre dentro del número de días positivos en el futuro. Si los días positivos se establecen en **100**, y si hay demanda de un artículo en 30 días a partir de la fecha actual, el sistema creará un pedido planificado para satisfacer esa demanda. Si hay demanda para el mismo artículo en 90 días a partir de la fecha actual, el sistema recomendará que aumente la cantidad del pedido en 30 días a partir de la fecha actual, de modo que el pedido también cubra la demanda en 90 días. Sin embargo, si hay demanda para el artículo en 150 días a partir de la fecha actual, el sistema no recomendará que aumente la cantidad del pedido que ya se planificó. En su lugar, se creará un nuevo pedido planificado.

Como norma, los días positivos se establecen en un número que se encuentre entre el plazo más largo de los artículos y el límite de tiempo de cobertura. Le recomendamos que asigne los artículos que se adquieren o producen con frecuencia a un grupo de cobertura en el que los días positivos sean equivalentes al plazo del artículo.

### <a name="negative-days"></a>Días negativos

Los días negativos indican el límite de tiempo que se permitirán las recepciones de artículos. Representan el número de días que está dispuesto a esperar antes de que pida un nuevo reabastecimiento cuando tenga un inventario negativo o no tenga suficiente inventario. Los días negativos responden la pregunta, ¿debemos crear un nuevo pedido de compra para el artículo, o debemos usar una compra existente incluso si sabemos que el artículo se retrasará?

Por ejemplo, tiene un pedido de ventas para un artículo 15 días a partir de la fecha actual. También tiene un pedido de compra para el mismo artículo. Este pedido de compra se recibirá en 20 días a partir de la fecha actual. ¿Desea que el sistema cree un pedido de compra para dicho pedido de ventas, o desea usar el pedido existente incluso si no puede cumplir el pedido de ventas a tiempo? Si los días negativos se establecen en menos de **5** para indicar que el artículo se puede retrasar un máximo de cinco días, el sistema crea un nuevo pedido de compra planificado para satisfacer el pedido de ventas. Si los días negativos se establecen en más de **5**, el sistema utiliza el pedido existente para el artículo.

Los días negativos también afectan al rendimiento de la planificación maestra. Si los días negativos se establecen en un número elevado, se generarán muchos mensajes de acción.

Le recomendamos que establezca los días negativos en un número inferior al plazo del artículo.

### <a name="dynamic-negative-days"></a>Días negativos dinámicos

Los días negativos dinámicos tienen en cuenta el plazo y los días negativos del artículo que especificó. El sistema creará un nuevo pedido de compra planificado, según el límite de tiempo de días negativos que se calcula mediante la siguiente fórmula:

Plazo + Días negativos + Fecha actual – Fecha de requisito

El sistema utiliza solo los pedidos de suministro planificados que se encuentran dentro del límite de tiempo, y crea un nuevo pedido planificado fuera de este. La ventaja de los días negativos dinámicos es que incluirá el plazo del producto individual, para volver a utilizar los pedidos existentes e impedir la creación de nuevos pedidos planificados que terminarán con un día posterior, debido a los retrasos causados por el plazo. 

Para obtener más información, consulte [Días negativos y días negativos dinámicos](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/master-planning/more-about-dynamic-negative-days).
