---
title: Mejorar el rendimiento del motor de programación
description: Este tema proporciona información sobre el motor de programación y cómo mejorar el rendimiento.
author: ChristianRytt
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: ''
ms.author: kamaybac
ms.search.validFrom: 2020-09-03
ms.dyn365.ops.version: ''
ms.openlocfilehash: d1378ae652ea70cba941316f4667052dcb05f717
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5812920"
---
# <a name="improve-scheduling-engine-performance"></a>Mejorar el rendimiento del motor de programación

[!include [banner](../includes/banner.md)]

El motor de programación de recursos se utiliza al programar rutas para órdenes de producción planificadas y liberadas. El motor se lanzó originalmente como parte de Dynamics AX 2012 y ha pasado por varias mejoras desde su lanzamiento.

El [problema de programación del taller de trabajo](https://en.wikipedia.org/wiki/Job_shop_scheduling) es un problema combinatorio extremadamente complejo donde el tiempo de solución crece exponencialmente con el número de variables de decisión. A menudo, los clientes configuran rutas de producción y datos relacionados de una manera que da como resultado un problema de programación que no se puede resolver en un tiempo razonable, incluso en el hardware más moderno. Este tema lo ayudará a comprender el motor de programación y cómo una configuración específica puede influir en el rendimiento.

Cuando se trata de mejorar el rendimiento de la programación, las pautas generales recomiendan reducir la complejidad del problema que el motor debe resolver. Algunos de los principales factores que pueden afectar el rendimiento incluyen:

- Rutas con muchas operaciones
- Rutas con operaciones en paralelo
- Operaciones con cantidad de recursos superior a uno
- Operaciones con muchos recursos aplicables
- Uso de enlaces físicos
- Uso de la capacidad limitada
- La cantidad de calendarios diferentes utilizados
- El número de franjas horarias de trabajo por día en el calendario.
- Duración total de la ruta
- Ejecución de varios motores de programación en paralelo

## <a name="overview-of-basic-scheduling-flow"></a>Descripción general del flujo de programación básico

Para comprender cómo una configuración determinada puede afectar el rendimiento, es importante comprender algo sobre cómo fluye el proceso, tanto dentro del motor como en el código X ++ que lo rodea.

El proceso básico de programación de un pedido consta de tres pasos principales:

- **Cargando datos** - Aquí, los modelos de datos X ++ se transforman en el modelo de datos interno del motor en forma de trabajos y restricciones.
- **Planificación** - Esta es la fuente principal de programación que procesa el modelo y las restricciones dados y genera un resultado. Durante este proceso, el motor solicitará información sobre el tiempo de trabajo y las reservas de capacidad existentes de X ++ según sea necesario.
- **Guardar datos** - El resultado del motor en forma de espacios de reserva de capacidad de trabajo es procesado por el código X ++ para guardar reservas de capacidad y actualizar las horas de inicio y finalización de los trabajos / operación / orden.

## <a name="load-data-into-the-engine"></a>Cargar datos en el motor

El motor de programación tiene un modelo de datos más abstracto que la base de datos de Supply Chain Management porque se ha construido como un motor genérico que puede manejar diferentes fuentes de datos. Los conceptos de ruta, operaciones secundarias y tiempo de ejecución deben "traducirse" al modelo genérico de trabajo y restricción que expone el motor. La lógica para construir el modelo tiene una cantidad significativa de lógica empresarial y es diferente según los datos de origen. La clase responsable de X++ es `WrkCtrScheduler` y tiene clases derivadas para órdenes de producción planificadas, órdenes de producción liberadas y previsiones de proyectos.

Como ejemplo, considere una ruta que se muestra en la siguiente tabla e imagen, que parece relativamente simple.

| Oper. Nº | Prioridad | Tiempo de preparación | Tiempo de ejecución | Tiempo en cola posterior | Cantidad de recursos | Siguiente |
| --- | --- | --- | --- | --- | --- | --- |
| 10 | Principal | 1.00 | 2.00 | | 1 | 20 |
| 10 | Secundario&nbsp;1 | | | | 1 | 20 |
| 20 | Principal | | 3.00 | 1.00 | 3 | 0 |

![Diagrama de ruta de ejemplo](media/scheduling-engine-route.png "Diagrama de ruta de ejemplo")

Al enviar esto al motor, se divide en ocho trabajos, como se muestra en la siguiente ilustración (seleccione la imagen para ampliarla).

[![Programación de trabajos del motor](media/scheduling-engine-jobs.png "Programación de trabajos del motor")](media/scheduling-engine-jobs-large.png)

El vínculo estándar entre dos trabajos es `FinishStart`, lo que significa que la hora de finalización de un trabajo debe ser anterior a la hora de inicio de otro trabajo. Debido a que la configuración debe ser realizada por el mismo recurso que luego realizará el proceso, hay restricciones `OnSameResource` entre ellos. Entre los trabajos para operación primaria y secundaria para 10, hay enlaces `StartStart` y `FinishFinish` enlaces, lo que significa que los trabajos deben comenzar y terminar al mismo tiempo, y hay restricciones `NotOnSameResource`, lo que impedirá el mismo recurso para primaria y secundaria.

Para la operación 20, donde la cantidad de recursos se ha establecido en 3, el trabajo de proceso se ha dividido en tres trabajos distintos donde todos los trabajos deben ejecutarse exactamente al mismo tiempo.
En este caso, el grupo de rutas se ha configurado para no reservar capacidad para la cola después de horas, por lo que solo hay un trabajo para la cola posterior.

El motor de programación solo comprende los conceptos de trabajos y no tiene noción de operaciones. Esto significa que al realizar la programación de operaciones, las operaciones también se dividen en trabajos, aunque estos no se conservarán en la base de datos.

Para cada trabajo, también definiremos cuál es el requisito de capacidad del trabajo (la cantidad de segundos requeridos). Dependiendo de cómo se hayan definido los requisitos de recursos, también podemos, para cada trabajo, enviar una lista de todos los recursos aplicables potenciales en los que podría ejecutarse el trabajo y cuál es el requisito de capacidad para ese recurso específico. Aunque la lista de recursos aplicables se envía al crear el modelo, el motor aún deberá asegurarse de que la asignación de recursos sea realmente válida durante toda la duración del trabajo.

## <a name="scheduling-engine-internals"></a>Programación de componentes internos del motor

### <a name="scheduling-engine-interface"></a>Programación de la interfaz del motor

Para tener una idea de cómo funciona el motor internamente, lo mejor es mirar la funcionalidad que expone externamente. En X++, la interfaz principal es `WrkCtrSchedulerEngineInterface`. Tiene los métodos descritos en las siguientes subsecciones.

#### <a name="general-engine"></a>Motor general

| **Método** | **Propósito** |
| --- | --- |
| `run` | Programa todos los trabajos cargados y devuelve el código de error. |
| `getJobSchedulingSequenceResult` | Obtiene el resultado de la programación y el primer trabajo de error para la secuencia identificada por un trabajo específico. |
| `validateJobCapacityReservations` | Valida las reservas de capacidad para todos los trabajos almacenados por el motor. |
| `setReservationsTimeStamp` | Envía una marca de tiempo al motor configurado en todas las nuevas reservas de capacidad para los trabajos programados en la memoria caché del motor. |
| `addPropertyToGroupAggregation` | Agrega un prefijo de propiedad al conjunto de propiedades que se utilizan cuando se agrega capacidad. |
| `addResource` | Agrega un recurso al grupo de recursos del motor de programación. |
| `addResourceGroup` | Agrega un grupo de recursos al grupo de recursos del motor de programación. |
| `addResourceGroupMembership` | Agrega un recurso como miembro de un grupo de recursos. |
| `addOptimizationGoal` | Agrega un objetivo de optimización de programación (duración o prioridad). |

#### <a name="individual-jobs"></a>Trabajos individuales

| **Método** | **Propósito** |
| --- | --- |
| `addJobInfo` | Agrega un registro de información del trabajo que informa al motor sobre un trabajo que debe programarse. |
| `addConstraintJobEndsAt` | Agrega una restricción de que un trabajo debe finalizar en una fecha y hora específicas. |
| `addConstraintJobStartsAt` | Agrega una restricción de que un trabajo debe comenzar en una fecha y hora específicas. |
| `addConstraintMaxJobDays` | Define la restricción que un trabajo puede abarcar durante un número máximo de días especificado. |
| `addConstraintResourceRequirement` | Agrega la restricción de que el trabajo debe programarse en un recurso específico. |
| `addJobBindPriority` | Agrega una prioridad de enlace de trabajo para un par (trabajo, nivel de restricción). Un valor de prioridad más alto significa que las variables de trabajo se vincularán antes. El trabajo se procesará antes que los trabajos con un valor de prioridad más bajo en la misma secuencia. |
| `addJobCapacity` | Agrega información de carga de capacidad para un trabajo (como el tiempo de ejecución del trabajo requerido) independientemente del recurso en el que se ejecuta el trabajo. |
| `addJobResourceCapacity` | Agrega un recurso al conjunto de recursos que se pueden usar para realizar un trabajo y establece la capacidad requerida cuando se ejecuta en ese recurso. |
| `addJobGoal` | Agrega información sobre el objetivo del trabajo para un nivel de restricción específico (hora de finalización más temprana o hora de inicio más tardía). |
| `addJobResourcePriority` | Agrega la prioridad que se utilizará cuando se programe un trabajo en un recurso. |
| `addJobResourceRuntime` | Especifica un tiempo de trabajo que depende del recurso en el que se programará el trabajo. |
| `addJobRuntime` | Especifica un tiempo de trabajo que es independiente del recurso en el que se programará el trabajo. |
| `scheduleJobOnResourceGroup` | Marca un trabajo para programarlo en el nivel del grupo de recursos. |
| `setJobResourcePreemptionAllowed` | Establece si se permite la preferencia para un trabajo en un recurso (si el motor puede programar el trabajo en ranuras de capacidad no contiguas). |
| `setRequiredNumberOfResources` | Establece la cantidad de recursos necesarios para programar un trabajo (solo para la programación de operaciones). |

#### <a name="constraints-between-jobs"></a>Restricciones entre trabajos

| **Método** | **Propósito** |
| --- | --- |
| `addJobLink` | Agrega un enlace (como final\>inicio) entre dos trabajos. |
| `addConstraintEndsDelayed` | Define la restricción de que un trabajo no puede finalizar antes de que finalicen otros trabajos más algún tiempo de retraso. |
| `addConstraintJobListWorkingTimeIntersect` | Agrega una restricción de que las ranuras de capacidad reservadas para los trabajos deben estar en los horarios de trabajo que se cruzan para los dos recursos utilizados por los trabajos. |
| `addConstraintJobOverlap` | Agregue una restricción que defina cómo se secuencian los trabajos cuando una cantidad determinada de un artículo se puede mover entre dos recursos mientras el primer recurso aún no ha terminado de procesarse, de modo que el segundo recurso pueda comenzar a procesarse. |
| `addConstraintNotOnSameResource` | Agrega una restricción de que no se deben programar dos trabajos en el mismo recurso. |
| `addConstraintOnSameResource` | Agrega una restricción de que dos trabajos no deben usar el mismo recurso. |
| `addJobSameReservations` | Agrega una restricción de que un trabajo debe terminar teniendo reservas de capacidad para los mismos intervalos de tiempo que el trabajo principal. |
| `setPrimaryParallelJob` | Agrega información sobre qué trabajo es el trabajo principal en un conjunto de trabajos paralelos. |

### <a name="solver"></a>Solucionador

El motor en sí es esencialmente un solucionador de restricciones especializado con heurísticas personalizadas agregadas. El solucionador se basa en dos elementos principales: variables y restricciones.

#### <a name="variable"></a>Variable

Una variable representa un dominio de valores posibles. El motor de programación tiene dos tipos de variables:

- **Variable DateTime** - Tiene un dominio de todas las fechas y horas, y el dominio se puede restringir moviendo el límite inferior y superior para el tiempo de la variable más cerca uno del otro.
- **Variable de recurso** - Tiene un dominio de recursos aplicables y el dominio se puede restringir eliminando recursos de la lista.

#### <a name="constraint"></a>Restricción

Una restricción actúa sobre las variables restringiendo sus dominios, pero también depende de las variables, por lo que se activa cuando las variables cambian. El proceso de "propagación de restricciones" es cuando una restricción realiza su función principal e informa a la lógica principal si tiene éxito.

Una variable se considera vinculada cuando no se puede restringir más, lo que para la variable DateTime significa que el límite superior e inferior es el mismo, y para la variable Resource, que solo tiene un único recurso aplicable. Cuando todas las variables están vinculadas, se encuentra una solución.

### <a name="constraint-levels"></a>Niveles de restricción

Cuando la programación se ejecuta como parte de la fase de cobertura de la planificación de necesidades de material (MRP), los pedidos se programarán hacia atrás desde la fecha de necesidad. Sin embargo, si no es posible encontrar una programación que comience hoy o más tarde y finalice antes de la fecha de requisito, entonces la dirección de programación cambiará para avanzar desde hoy.

Esta regla comercial principal se maneja organizando las restricciones en niveles. Si no se encuentra una solución al usar las restricciones en el nivel más alto, entonces todas las restricciones en ese nivel se eliminan y se prueba el nivel inferior. En la práctica, esto significa que para la programación hacia atrás, el modelo contendrá un nivel 1 con objetivos de trabajo de la última hora de inicio dada una restricción de tiempo de finalización máxima (la fecha de requisito), y un nivel 0 con objetivos de trabajo de la hora de finalización más temprana y dado un mínimo Restricción de tiempo de inicio de hoy.

### <a name="algorithm"></a>Algoritmo

Los pasos principales del algoritmo del motor son:

1. Encuentre secuencias (cadenas de trabajo) que se puedan resolver por separado.
1. Intente encontrar una solución inicial para la secuencia del nivel de restricción más alto.
    1. Ordene los trabajos en la secuencia según el objetivo y las prioridades del trabajo, de modo que se pueda encontrar un trabajo inicial.
    1. Repita los trabajos en la siguiente secuencia:
        1. Encuentre todas las restricciones que deben propagarse y ejecute la propagación.
        1. Si se han vinculado todas las variables del trabajo, se ha encontrado una solución para ese trabajo.
        1. Si una de las variables no se pudo vincular sin violar las restricciones, deshaga la vinculación de la variable, pruebe con un valor diferente en el dominio (para la variable de recurso) y vuelva a ejecutar la propagación de la restricción.
1. Si no se encontró una solución, entonces se eliminan todas las restricciones en el nivel de restricción actual, se reduce el nivel de restricción (si hay niveles inferiores disponibles) y se reintenta la búsqueda de soluciones con el nuevo conjunto de restricciones.
1. Si se encontró una solución factible, entonces se inicia la fase de optimización, que intentará encontrar una mejor solución hasta que se alcance el tiempo de espera de optimización o se hayan agotado todas las combinaciones de recursos.

El solucionador de restricciones no conoce los detalles del algoritmo de programación. Es en la definición y combinación de las diversas limitaciones donde ocurre la "magia".

### <a name="determining-working-times"></a>Determinación de los tiempos de trabajo

Una gran parte de las limitaciones (internas) del motor controla el tiempo de trabajo y la capacidad de un recurso. Básicamente, la tarea consiste en recorrer las franjas horarias de trabajo de un recurso desde un punto determinado en una dirección determinada, y encontrar un intervalo suficientemente largo en el que la capacidad (tiempo) requerida de los trabajos pueda caber.

Para hacer esto, el motor necesita conocer los tiempos de trabajo de un recurso. Frente a los datos del modelo principal, los tiempos de trabajo son de *carga diferida*, lo que significa que se cargan en el motor según sea necesario. La razón de este enfoque es que a menudo hay tiempos de trabajo en Supply Chain Management para un calendario durante un período muy largo y, por lo general, existen muchos calendarios, por lo que los datos serían bastante grandes para precargarlos.

El motor solicita la información del calendario en fragmentos, invocando el método de clase X++ `WrkCtrSchedulingInteropDataProvider.getWorkingTimes`. La solicitud es para un ID de calendario específico en un intervalo de tiempo específico. Dependiendo del estado de la caché del servidor en Supply Chain Management, cada una de estas solicitudes podría terminar en varias llamadas a la base de datos, lo que lleva mucho tiempo (en relación con el tiempo computacional puro). Además, si el calendario contiene definiciones de tiempo de trabajo muy elaboradas con muchos intervalos de tiempo de trabajo por día, esto se suma al tiempo de carga.

Cuando los datos del tiempo de trabajo se cargan en el motor de programación, se retienen en su caché interna para el calendario específico, lo que significa que si otros trabajos o recursos están usando el mismo calendario, las próximas búsquedas se pueden realizar rápidamente desde la memoria. Una causa común de mal rendimiento es si se usa un ID de calendario diferente para cada recurso, porque entonces será necesario solicitar datos para cada calendario, aunque el contenido de los calendarios sea el mismo.

### <a name="finite-capacity"></a>Capacidad limitada

Cuando se utiliza la capacidad finita, las franjas horarias de trabajo del calendario se dividen y reducen en función de las reservas de capacidad existentes. Estas reservas también se obtienen a través de la misma clase `WrkCtrSchedulingInteropDataProvider` que los calendarios, pero en su lugar utilice el método `getCapacityReservations`. Al programar durante la planificación maestra, se consideran las reservas para el plan maestro específico y si están habilitadas en la página **Parámetros de planificación maestra**, también se incluyen las reservas de pedidos de producción firmes. De manera similar, al programar una orden de producción, también es una opción incluir reservas de órdenes planificadas existentes, aunque esto no es tan común como al revés.

El uso de capacidad finita hará que la programación tarde más debido a varias razones:

- Obtener la información de capacidad de la base de datos es una operación lenta y el almacenamiento en caché del lado del servidor de la información de capacidad generalmente no es tan bueno como para los horarios de trabajo porque no se comparten entre recursos como los calendarios.
- El número de franjas horarias de trabajo para atravesar aumenta debido a las divisiones, y las franjas horarias para un período de tiempo más largo normalmente deben investigarse antes de encontrar una solución.
- Una vez completada la programación, se debe realizar una verificación de reservas conflictivas (consulte la sección "Ejecución de motores de programación en paralelo" para obtener más detalles).

### <a name="examining-the-resource-combinations"></a>Examinando las combinaciones de recursos

Si la secuencia de trabajo solo contiene los enlaces estándar `FinishStart`, lo que significa que forma una cadena simple sin ramificaciones, se puede lograr un resultado óptimo (visto desde el pedido único, no entre pedidos) encontrando la mejor solución para el primer trabajo y luego avanzando para encontrar la mejor solución para el siguiente trabajo. La mejor solución para un trabajo significa encontrar el recurso que puede obtener la fecha de inicio y finalización del trabajo más cercano al objetivo del trabajo (en la programación anticipada, esto significa obtener la fecha de finalización del trabajo lo antes posible) sin dejar de respetar las restricciones.

Cuando hay trabajos paralelos, encontrar una solución puede implicar examinar diferentes combinaciones de recursos. El número de posibles combinaciones de recursos es el producto del número de recursos aplicables para los trabajos en paralelo conectados. Especialmente cuando se programa un pedido hacia atrás desde una fecha de requisito, la lógica puede tardar bastante en darse cuenta de que no hay una solución al problema que hará que los trabajos paralelos encajen antes de la fecha de hoy, ya que deberá verificar todas las combinaciones. porque podría haber algunos recursos que tuvieran una mayor eficiencia o un calendario diferente que podría dar un resultado. Esto significa que si no se ha establecido un límite de tiempo de espera, se ejecutará durante mucho tiempo antes de cambiar la dirección para avanzar.

Esta lógica combinatoria también significa que agregar más recursos aplicables puede hacer que el motor funcione más lento. Si se producen problemas de rendimiento al tener operaciones paralelas y programación con capacidad infinita, se puede solucionar en parte haciendo que el diseñador de ruta tome una decisión sobre qué recurso debe usarse y luego asigne el recurso directamente en la operación (porque el motor en la mayoría de los casos lo hará). siempre terminan eligiendo el mismo recurso, por lo que el resultado final será el mismo.

### <a name="hard-links"></a>Enlaces duros

Establecer el tipo de vínculo entre dos trabajos en duro garantiza que no haya ningún intervalo de tiempo entre el final de un trabajo y el inicio del siguiente. Esto puede ser muy útil en escenarios como cuando el metal se calienta en un trabajo y luego se procesa en el siguiente trabajo, donde no es deseable que el metal se enfríe en el medio.

Con enlaces suaves estándar y programación hacia adelante, si la ruta forma una cadena simple sin ramificaciones, se puede lograr un resultado al encontrar una solución para el primer trabajo que satisfaga sus propias restricciones y luego avanzar a través de la cadena propagando el tiempo de finalización desde el trabajo anterior al siguiente trabajo. Si el trabajo actual no puede encontrar ninguna capacidad, la hora de inicio se trasladará más lejos, sin ninguna consecuencia para los trabajos anteriores que podrían crear brechas entre los trabajos. Sin embargo, con enlaces duros (especialmente en relación con la capacidad finita) para el mismo escenario, el hecho de que un trabajo posterior en la cadena no pueda encontrar capacidad, significará que todos los trabajos programados anteriores tendrán que ser "arrastrados" uno por uno y, por lo tanto, reprogramado varias veces. Especialmente en escenarios con alta carga para múltiples recursos, los enlaces duros pueden causar una reacción en cadena donde los trabajos se afectarán entre sí y se deberán realizar varias iteraciones antes de que el resultado se estabilice en un programa factible.

## <a name="running-scheduling-engines-in-parallel"></a>Ejecución de motores de programación en paralelo

Al realizar la programación como parte de una ejecución de planificación maestra en la que se utilizan ayudantes, cada uno de los subprocesos auxiliares de planificación maestra también puede recoger las tareas de programación de órdenes de producción. Esto significa que se pueden ejecutar varios motores de programación al mismo tiempo. Si bien el subproceso múltiple en general es un beneficio de rendimiento muy significativo, también existen algunas desventajas funcionales cuando se trata de la programación.

En MRP, todos los pedidos de producción para un nivel de lista de materiales (BOM) determinado se programan en una secuencia de fecha de requisito, lo que significa que los pedidos con la fecha de requisito más temprana deben programarse primero y, por lo tanto, tienen la mayor probabilidad de obtener la capacidad de recursos disponible. Sin embargo, con varios motores seleccionando de la lista de pedidos no programados, la secuencia ya no está asegurada, ya que uno podría completarse más rápido que el otro.

Además, al programar con capacidad finita y cuando varias instancias de motor intentan programar pedidos que potencialmente usan los mismos recursos en el mismo intervalo de tiempo, puede ocurrir una condición de carrera. El número de tales condiciones de carrera se registra en el campo **Conflictos de programación** en la página del historial de planes maestros. La lógica de resolución de conflictos es la siguiente:

- Programe un pedido (sin candados) y obtenga reservas de capacidad.
- Tome el bloqueo.
- Compruebe si existen reservas de capacidad más nuevas para los recursos programados en el intervalo de tiempo.
  - Si no, escriba la capacidad y suelte el bloqueo.
  - Si es así, suelte el candado y reprograme el pedido desde el principio.

Por lo tanto, al programar con varias instancias de motor, el resultado no es completamente determinista porque dependerá de la sincronización exacta de cada uno de los subprocesos.

## <a name="operation-scheduling-performance"></a>Rendimiento de programación de operaciones

Aunque la programación de operaciones también se conoce como planificación de capacidad aproximada, vista desde el punto de vista del motor, puede ser un problema más difícil de resolver si se utiliza capacidad finita, ya que se necesitan más datos para determinar la viabilidad.

La capacidad de un grupo de recursos depende de cuáles y cuántos recursos son miembros del grupo de recursos. Un grupo de recursos en sí mismo no tiene ninguna capacidad &mdash;solo cuando los recursos sean miembros del grupo tendrá capacidad. Dado que la pertenencia al grupo de recursos puede variar con el tiempo, la capacidad debe evaluarse por día.

En la programación de operaciones, el calendario del grupo de recursos se utiliza para determinar las horas de inicio y finalización de cada operación. Esto significa que el calendario del grupo de recursos establece un límite sobre la cantidad de tiempo que se pueden programar las operaciones para una operación en un día en un grupo de recursos. Frente al calendario para los recursos específicos, los datos de eficiencia del calendario se ignoran para el grupo de recursos ya que simplemente denota horas de apertura y no capacidad real.

Por ejemplo, si el tiempo de trabajo para un grupo de recursos en una fecha específica es de 8:00 a 16:00, una operación no puede poner más carga en el grupo de recursos de lo que cabe en 8 horas, sin importar cuánto capacidad que el grupo de recursos tiene disponible en total ese día. Sin embargo, la capacidad disponible puede limitar aún más la carga.

La carga de la programación de trabajos en todos los recursos incluidos en el grupo de recursos en un día determinado se considera cuando se calcula la capacidad disponible para el grupo de recursos en el mismo día. Para cada fecha, el cálculo es:

*Capacidad disponible del grupo de recursos = Capacidad para los recursos del grupo según su calendario &ndash; Carga programada del trabajo en los recursos del grupo &ndash; Carga programada de operaciones en los recursos del grupo &ndash; Carga programada de operaciones en el grupo de recursos*

En la pestaña **Requerimientos de recursos** en la operación de ruta, los requisitos de recursos se pueden especificar usando un recurso específico (en cuyo caso la operación se programará usando ese recurso), para un grupo de recursos, para un tipo de recurso, o para una o más capacidades, habilidades, curso o certificado. Si bien el uso de todas estas opciones brinda una gran flexibilidad en el diseño de la ruta, también complica la programación del motor, ya que la capacidad debe tenerse en cuenta por "propiedad" (el nombre abstracto que se usa en el motor para la capacidad, habilidades, etc. ).

La capacidad del grupo de recursos para una capacidad es la suma de la capacidad de todos los recursos en el grupo de recursos que tiene la capacidad en cuestión. Si un recurso del grupo tiene una capacidad, se considerará sin importar el nivel de capacidad que se requiera.

En la programación de operaciones, la capacidad disponible para una cierta capacidad para un grupo de recursos se reducirá cuando se carga con una operación que requiere la capacidad en cuestión. Si la operación requiere más de una capacidad, la capacidad se reducirá para todas las capacidades requeridas.

Para cada fecha, el cálculo necesario es:

*Capacidad disponible para una funcionalidad = Capacidad para la funcionalidad &ndash; Carga programada del trabajo en los recursos con la funcionalidad específica, incluida en el grupo de recursos &ndash; Carga programada de operaciones en los recursos con la funcionalidad específica, incluida en el grupo de recursos &ndash; Carga programada de operaciones en el propio grupo de recursos que requieren la funcionalidad específica*

Esto significa que si hay carga en un recurso específico, la carga se considera en el cálculo de la capacidad disponible del grupo de recursos por capacidad, porque la carga en un recurso específico reduce su contribución a la capacidad del grupo de recursos para una capacidad sin importar si el carga en el recurso específico es para esa capacidad específica. Si hay carga en el nivel del grupo de recursos, se considera en el cálculo de la capacidad disponible del grupo de recursos por capacidad solo si la carga es de una operación que requiere la capacidad específica.

La lógica anterior es complicada, ya que es la misma para cada tipo de "propiedad", por lo que el uso de la programación de operaciones con capacidad finita requiere que se cargue una cantidad significativa de datos.

## <a name="viewing-scheduling-engine-input-and-output"></a>Visualización de la entrada y salida del motor de programación

Para obtener detalles específicos de la entrada y salida del proceso de programación, habilite el registro yendo a **Administración de la organización \> Preparar \> Planificación \> Programación de cabina de seguimiento**.

En esta página, primero seleccione **Habilitar el registro** en el Panel de acciones. A continuación, ejecute la programación para la orden de producción. Cuando termine, regrese a la página **Programación de cabina de seguimiento** y seleccione **Deshabilitar el registro** en el Panel de acciones. Actualice la página y aparecerá una nueva línea en la cuadrícula. Seleccione la línea nueva y seleccione **Descargar** en el panel de acciones. Esto le dará una carpeta comprimida .zip que contiene los siguientes archivos:

- **Log.txt** - Este es el archivo de registro que describe los pasos por los que pasa el motor. Es muy elaborado y puede ser un poco abrumador, pero cuando se usa como parte de la experimentación con la configuración de la ruta para resolver problemas de rendimiento, lo primero que debe buscar es la diferencia de tiempo entre la primera y la última línea, ya que esto le dará el tiempo exacto que ha pasado el planificador.
- **XmlModel.xml** - Contiene el modelo que está construido en X ++ y con el que opera el motor. El `JobId` utilizado en el archivo se correlaciona con el `RecId` de la tabla de origen que contiene los trabajos (`ReqRouteJob` o `ProdRouteJob`). Lo típico a buscar en este archivo es que las fechas dadas en `ConstraintJobStartsAt` y `ConstraintJobEndsAt` son las esperadas, que la propiedad `JobGoal` esté configurada correctamente y que los trabajos estén relacionados entre sí a través de las restricciones de `JobLink`.
- **XmlSlots.xml** - Contiene todos los tiempos de trabajo y reservas de capacidad que ha solicitado el motor. El motor solo solicitará los horarios de trabajo del calendario y las reservas para los períodos de tiempo en los que intente colocar los trabajos (y un búfer adicional), por lo que si el archivo contiene tiempos muy lejanos en el futuro, podría ser una indicación de problema con la configuración. Los nodos de `ResourceProperty` mostrarán para cada recurso con qué grupo de recursos y capacidades está asociado para qué períodos.
- **Result.xml** - Contiene el resultado de la ejecución de programación.

Tenga en cuenta que la función de seguimiento puede agregar una sobrecarga de rendimiento significativa, por lo que solo úsela para investigar la programación de pedidos específicos de manera controlada. Si se enciende durante una ejecución de planificación maestra, alcanzará rápidamente su límite de tamaño y se detendrá.

## <a name="troubleshooting-performance"></a>Resolución de problemas de rendimiento

Como se puede entender en todas las secciones anteriores, existen algunas dificultades en lo que respecta a la configuración y el uso del motor de programación, que pueden provocar problemas de rendimiento. La siguiente lista de verificación se puede utilizar para solucionar estos problemas. Es importante tener en cuenta todos los puntos, ya que la mayoría de las veces es una combinación de múltiples factores lo que genera problemas.

### <a name="performing-scheduling-as-part-of-mrp-when-it-is-not-needed"></a>Realización de la programación como parte de MRP cuando no es necesario

Aunque las rutas se utilizan para fines de control de producción, como el cálculo de costos y la generación de informes, es posible que no sea necesario considerarlas durante la planificación de necesidades. En algunos casos, tener un tiempo de producción estándar especificado para el artículo será suficiente para la planificación. Para desactivar la programación de rutas, establezca el límite de tiempo de capacidad en cero. Si se debe realizar la programación, entonces el límite de tiempo de capacidad debe establecerse con cuidado porque podría no ser necesario considerar rutas para la extensión total del límite de tiempo de cobertura del MRP.

Tenga en cuenta que si el pedido no está programado durante la planificación de necesidades, será necesario programarlo cuando se firme el pedido planificado. Esto significa que el proceso de reafirmación tomará más tiempo, por lo que dependiendo de cuántos de los pedidos planificados sugeridos se reafirmen, la ganancia de rendimiento durante la MRP podría perderse al reafirmar.

### <a name="route-with-unnecessary-operations"></a>Ruta con operaciones innecesarias

Al diseñar la ruta, es tentador intentar modelar el mundo real exactamente con todos los pasos por los que pasa la producción. Si bien esto puede ser útil en algunos casos, no es bueno para el rendimiento, ya que el modelo en el que el motor necesita trabajar se hace más grande (tanto en términos de trabajos como de restricciones) y se ejecutarán más sentencias SQL para la inserción y actualización de los trabajos. y reservas de capacidad. Además, existe el efecto posterior de tener que informar eventualmente el progreso de los trabajos, que se puede mitigar con publicaciones automáticas. Si los datos no se utilizan para nada, crea una carga innecesaria.

Recomendamos que solo cree operaciones que sean estrictamente necesarias para la programación (que normalmente serán los recursos de cuello de botella) y / o para fines de cálculo de costos. Alternativamente, debe agrupar muchas operaciones distintas más pequeñas en una operación más grande que represente una parte mayor del proceso.

### <a name="many-applicable-resources-for-an-operation"></a>Muchos recursos aplicables para una operación

El número de recursos aplicables para una operación está determinado por los requisitos de recursos establecidos en la relación de operación. El requisito puede ser para un recurso específico (individual) o puede basarse en la pertenencia del recurso a un grupo o capacidad de recursos.

Si la programación no se realiza utilizando una capacidad finita y todos los recursos aplicables tienen el mismo calendario y eficiencia, entonces el motor de programación siempre terminará seleccionando el mismo recurso para una operación, pero solo después de probar todos los recursos aplicables para verificar si hay uno. que es "mejor" que los demás. En este caso, la carga de la programación se puede reducir en gran medida simplemente asignando siempre un recurso específico a la operación en el momento del diseño de la ruta.

### <a name="route-with-parallel-operations"></a>Ruta con operaciones en paralelo

Si bien las operaciones paralelas (primarias / secundarias) son una herramienta poderosa para modelar escenarios como cuando se necesita una máquina y un operador para realizar una tarea específica, también es la fuente de muchos problemas de rendimiento. Si se asigna un requisito para un recurso individual específico tanto a la operación primaria como a la secundaria, normalmente no es un problema. Pero si hay muchos recursos posibles para cada una de las operaciones, entonces agrega una complejidad computacional significativa a la programación.

Una alternativa al uso de operaciones paralelas es modelar los pares como recursos "virtuales" (que luego representarán al equipo que siempre va unido para la operación) o simplemente no modelar una de las operaciones si no representa un cuello de botella.

### <a name="route-with-quantity-of-resources-higher-than-1"></a>Ruta con cantidad de recursos superior a 1

Si establece la cantidad de recursos necesarios para una operación superior a uno, el resultado es efectivamente lo mismo que usar operaciones primarias / secundarias porque se envían múltiples trabajos paralelos al motor. Sin embargo, para este caso no existe la opción de utilizar asignaciones de recursos específicos, porque una cantidad mayor que uno requiere que más de un recurso sea aplicable para la operación.

### <a name="excessive-use-of-finite-capacity"></a>Uso excesivo de la capacidad limitada

El uso de capacidad finita requiere que el motor cargue la información de capacidad desde una base de datos y puede tener una sobrecarga computacional porque será más difícil encontrar una solución, especialmente en entornos donde los recursos se reservan cerca de su capacidad máxima. Como resultado, es importante evaluar cuidadosamente si un recurso realmente necesita usar una capacidad finita o si puede tener overbooking. Debido a que puede haber una diferencia entre los recursos de capacidad finita en cuanto a la importancia que tienen para no realizar overbooking, recomendamos usar la opción de cuello de botella en un recurso en combinación con un valor separado en el plan en "Límite de tiempo de capacidad para recursos de cuello de botella". El uso del concepto de cuello de botella puede permitir que se reduzca el límite de tiempo de capacidad finita general.

### <a name="setting-hard-links"></a>Establecer enlaces duros

El tipo de enlace estándar de la ruta es *suave*, lo que significa que se permite un intervalo de tiempo entre el tiempo de finalización de una operación y el inicio de la siguiente. Permitir esto puede tener el desafortunado efecto de que, si los materiales o la capacidad no están disponibles para una de las operaciones durante mucho tiempo, la producción podría estar inactiva durante bastante tiempo, lo que significa un posible aumento del trabajo en curso. Esto no sucederá con enlaces duros porque la meta y la salida deben alinearse perfectamente. Pero el establecimiento de vínculos físicos hace que el problema de programación sea más difícil porque el tiempo de trabajo y las intersecciones de capacidad deben calcularse para los dos recursos de las operaciones. Si también hay operaciones paralelas involucradas, esto agrega un tiempo computacional significativo. Si los recursos de las dos operaciones tienen calendarios diferentes que no se superponen en absoluto, el problema no tiene solución.

Recomendamos utilizar enlaces duros solo cuando sea estrictamente necesario, y considerar cuidadosamente si es necesario para cada operación de la ruta.

Para reducir el trabajo en progreso sin aplicar enlaces duros, un truco consiste en programar el orden dos veces cambiando a la dirección opuesta para la segunda pasada. Si la primera programación se realizó hacia atrás desde la fecha de entrega, la segunda debe realizarse hacia adelante desde la fecha de inicio programada. Esto hará que los trabajos se compriman tanto como sea posible para minimizar el trabajo en progreso.

### <a name="separate-calendar-for-each-resource"></a>Calendario separado para cada recurso

Una de las principales fuentes de datos del motor de programación es la información del calendario, que puede resultar costosa de cargar desde la base de datos. Debido a que los calendarios se generan en base a plantillas, sería tentador generar un calendario para cada recurso y luego ajustar la información en este calendario cuando el recurso tenga tiempo de inactividad y otros problemas. Sin embargo, hacer esto limitará severamente la capacidad de los motores para almacenar en caché los datos del calendario, ya que necesitaría solicitar nuevos datos para cada recurso y puede ser una gran fuente de problemas de rendimiento. En su lugar, le recomendamos que reutilice los calendarios tanto como sea posible entre los recursos y luego controle los cambios en el tiempo de inactividad asignando un ID de calendario diferente para un período.

### <a name="high-number-of-working-time-slots-per-calendar-day"></a>Alto número de franjas horarias de trabajo por día de calendario

Debido a que el motor funciona examinando los intervalos de tiempo uno por uno para determinar la capacidad, es beneficioso minimizar el número de intervalos de tiempo por día calendario. Esto podría hacerse, por ejemplo, considerando si es importante que el horario resultante refleje que los trabajadores tienen un descanso de 5 minutos cada hora.

### <a name="large-or-none-scheduling-timeouts"></a>Tiempos de espera de programación grandes (o ninguno)

El rendimiento del motor de programación se puede optimizar utilizando los parámetros que se encuentran en la página **Parámetros de programación**. Las opciones **Programación de tiempo de espera habilitado** y **Programación de tiempo de espera de optimización habilitado** siempre deben establecerse en **Sí**. Si se establecen en **No**, la programación puede potencialmente ejecutarse infinitamente si se ha creado una ruta inviable con muchas opciones.

El valor de **Tiempo máximo de programación por secuencia** controla cuántos segundos se pueden dedicar, como máximo, a tratar de encontrar una solución para una sola secuencia (en la mayoría de los casos, una secuencia corresponde a un solo orden). El valor a utilizar aquí depende en gran medida de la complejidad de la ruta y configuraciones como la capacidad finita, pero un máximo de unos 30 segundos es un buen punto de partida.

El valor de **Tiempo de espera de los intentos de optimización** controla cuántos segundos como máximo se pueden utilizar para encontrar una solución mejor que la que se encontró originalmente. Esto solo influirá en las rutas que utilizan operaciones en paralelo, ya que hacen necesario probar diferentes combinaciones.

> [!NOTE]
> Los valores establecidos para los tiempos de espera se aplicarán tanto para la programación de las órdenes de producción liberadas como para las órdenes planificadas como parte de MRP. Como resultado, establecer valores muy altos podría aumentar significativamente el tiempo de ejecución de MRP cuando se ejecuta para un plan con muchas órdenes de producción planificadas.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]