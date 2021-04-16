---
title: Asignación de oleadas
description: Este tema describe cómo configurar el paso de asignación de oleadas, incluido cómo habilitar el procesamiento en paralelo.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: feee33a7d4ea3f0d9c4d671210293a28aac14f61
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823176"
---
# <a name="wave-allocation"></a>Asignación de oleadas

[!include [banner](../includes/banner.md)]

El procesamiento de oleadas puede llevar mucho tiempo y la mayor parte del tiempo de procesamiento se emplea en el paso de asignación y en el paso de creación del trabajo.

Ahora es posible ejecutar cada uno de estos pasos en paralelo, lo que puede mejorar el rendimiento del procesamiento de oleadas y permitir un mayor rendimiento de oleadas en el mismo almacén. Este tema explica cómo configurar el método de asignación de oleadas para que se ejecute en paralelo. Para obtener más información sobre cómo configurar la creación de trabajos para que se ejecute en paralelo, consulte [Programar la creación del trabajo durante la oleada](configure-wave-schedule-work-creation.md).

Anteriormente, solo era posible asignar una oleada a un almacén a la vez. Esta restricción ha sido eliminada y reemplazada por una nueva restricción que solo bloquea el elemento y las dimensiones que están por encima de la ubicación en la jerarquía de reservas. Las dimensiones por encima de la ubicación siempre incluyen las dimensiones del producto. Por ejemplo, si un artículo se configura mediante *Color*, luego variantes para *Rojo*, *Azul*, y *Amarillo* cada uno podría procesarse en paralelo.

Esto significa que si el mismo artículo con las mismas dimensiones por encima de la ubicación está siendo asignado por una oleada, otras oleadas tendrán que esperar para adquirir un candado en el mismo artículo y dimensiones. Si el bloqueo no se puede adquirir de manera oportuna, se producirá un error y el procesamiento de la onda fallará.

Para utilizar el procesamiento en paralelo, la oleada debe ejecutarse por lotes.

## <a name="performance-improvements"></a>Mejoras del rendimiento

Los beneficios de rendimiento del procesamiento en paralelo se dividen en dos categorías:

- **Rendimiento mejorado**: el rendimiento de las oleadas normalmente mejorará incluso si el procesamiento en paralelo no está configurado, especialmente para escenarios donde no hay superposición de elementos dentro de las oleadas.
- **Mejora de la asignación para una sola oleada**: las pruebas en los datos de los clientes han mostrado una mejora de rendimiento cercana al 50 % después de cambiar a la asignación en paralelo. El procesamiento paralelo se realiza por elementos y dimensiones por encima de la ubicación, por lo que las mejoras dependen de cuántos elementos diferentes contenga una oleada, la infraestructura disponible y la duración de la asignación frente a la duración de la creación del trabajo.

## <a name="configure-parallel-allocation"></a>Configuración de una asignación paralela

### <a name="warehouse-management-parameters"></a>Parámetros de gestión de almacenes

Para utilizar el procesamiento de asignación en paralelo, vaya a **Gestión de almacenes > Configuración > Parámetros de gestión de almacenes**, abra la pestaña **Procesamiento de oleadas** y realice los siguientes ajustes:

- **Grupo de lotes de procesamiento de oleadas**: seleccione el grupo de lotes que debe utilizar el procesamiento inicial de las oleadas. El procesamiento posterior de la asignación se puede realizar utilizando diferentes grupos de lotes.
- **Procesar oleadas en lote**: establezca esto en *Sí* para utilizar el procesamiento paralelo.
- **Esperar al bloqueo (ms)**: especifique el tiempo, en milisegundos, que un paso de asignación esperará a un recurso del sistema bloqueado por otro paso de la asignación. Cuando se supere este tiempo, la oleada no se procesará y se mostrará un mensaje de error. Le recomendamos que deje al menos unos segundos para permitir que finalice la asignación de una unidad lógica.

Para obtener información sobre estas y otras opciones de procesamiento de oleadas en la página **Parámetros de gestión de almacén**, consulte [Parámetros de almacén para procesamiento de oleadas](wave-warehouse-parameters.md).

## <a name="wave-process-methods"></a>Métodos de procesamiento de oleada

Para configurar el procesamiento en paralelo:

1. Vaya a **Gestión de almacenes > Configuración > Oleadas > Métodos de proceso de oleadas**.
1. Seleccione el método `allocateWave` en la cuadrícula.
1. En el panel de acciones, seleccione **Configurar tarea**.
1. Se abrirá la página **Configuración de la tarea del método de publicación de oleadas**. Esta cuadrícula enumera cada almacén en el que ha configurado el método `allocateWave`. El procesamiento paralelo solo se utilizará para los almacenes que se enumeran. Utilice los botones del Panel de acciones para agregar o eliminar almacenes de la cuadrícula según sea necesario. 
1. Para cada almacén, realice los siguientes ajustes:
    - **Número máximo de tareas por lotes**: especifique el número de tareas por lotes que se deben utilizar para la asignación del almacén seleccionado. El número óptimo de tareas por lotes depende de la infraestructura disponible y de qué otros trabajos por lotes se procesan en el servidor. Las pruebas realizadas en un entorno de cuatro núcleos dedicado al procesamiento de ondas mostraron que el uso de ocho tareas producía buenos resultados.
    - **Grupo de lotes de procesamiento de oleadas**: se pueden usar grupos de lotes específicos para diferentes almacenes para permitir que el proceso de asignación se amplíe por almacén.

## <a name="enable-or-disable-parallelization-across-all-legal-entities"></a>Habilitar o deshabilitar la paralelización en todas las entidades jurídicas

Le recomendamos que configure el método `allocateWave` para ejecutarse en paralelo en todas las entidades legales porque esto ayuda a mejorar el rendimiento del procesamiento de oleadas. A partir de la versión 10.0.17 de Supply Chain Management, la función *Paralelización de oleadas para el método Asignar oleada* está habilitada de forma predeterminada para todas las instalaciones nuevas y actualizadas y no se puede volver a desactivar. Después de habilitar esta función, ocurre lo siguiente:

- El método `allocateWave` se actualiza para incluir un ajuste de configuración de tareas que le permite usar la página **Métodos de proceso de oleadas** para definir el número de tareas que se ejecutarán simultáneamente, equivalente al número de procesos paralelos. Como resultado, el tiempo utilizado en el paso de asignación de oleada (que suele ser del 30% al 60% del tiempo total de procesamiento) se reduce en un factor aproximadamente equivalente al número de tareas. También es posible seleccionar qué lote se asignará para procesar estas tareas. Es importante tener en cuenta que todas sus entidades legales estarán configuradas para procesar oleadas por lotes. Para los almacenes que ya están configurados para procesar oleadas en lote y para los almacenes que ya están configurados para usar el método `allocateWave` en paralelo, se mantendrá la configuración existente.
- De forma predeterminada, todas las nuevas entidades legales están configuradas para procesar oleadas por lotes. Todos los almacenes nuevos con la opción **Procesos de gestión de almacenes** habilitada tendrán el método `allocateWave` configurado para ejecutarse en paralelo de forma predeterminada.
- En la página **Parámetros de gestión de almacén**, **El proceso se guarda en lote** se establece en *Sí* y **Espere el bloqueo (ms)** establecido en un valor predeterminado de 15 segundos. Esto significa que todas las oleadas se ejecutarán por lotes. Cuando se ejecuta una ola, adquiere un bloqueo del elemento y las dimensiones por encima de la asignación durante el paso de asignación. Cuando otra tarea de procesamiento de oleada intenta adquirir el mismo bloqueo para el registro idéntico, se bloquea hasta que el proceso actual termina. La configuración **Espere el bloqueo (ms)** establece el tiempo máximo que el sistema esperará antes de que se libere el bloqueo.

El procesamiento de la asignación en paralelo requiere que el procesado de oleada se ejecute en lotes. Por lo tanto, reducirá el rendimiento del procesamiento de oleadas si desactiva la configuración **El proceso se guarda en lote**, especialmente si el procesamiento de oleadas está utilizando un proceso paralelo según lo definido por la configuración de tareas para los métodos de oleadas relevantes.

Si es necesario, puede deshacer cada uno de los ajustes realizados de forma predeterminada cuando la función *Paralelización de oleadas para el método Asignar oleada* se habilita automáticamente para su instancia. Acción:

- Vaya a **Gestión de almacenes \> Configurar \> Parámetros de gestión de almacenes**. En la pestaña **Procesamiento de oleadas**, aplique sus valores preferidos para **Procesar oleadas en lote** y **Esperar el bloqueo (ms)**.
- Vaya a **Gestión de almacenes \> Configuración \> Oleadas \> Métodos de proceso de oleadas**. Seleccione el método `allocateWave`. En el panel de acciones, seleccione **Configuración de tareas** para abrir una página que enumera cada almacén donde el método está configurado para ejecutarse en paralelo. Modifique o elimine la cantidad de tareas por lotes y el grupo de oleadas asignado para cada almacén listado según sea necesario.

## <a name="troubleshooting"></a>Solución de problemas

### <a name="troubleshoot-using-the-infolog"></a>Solucionar problemas con el Registro de información

Debido a que se utiliza el marco de trabajo por lotes, los errores que ocurren durante el procesamiento de oleadas se capturarán como parte de los informes de los trabajos por lotes. Para leer los trabajos por lotes relacionados con una oleada:

1. Vaya a **Gestión de almacenes \> Oleadas de salida \> Oleadas de envío \> Todas las oleadas**.
1. Seleccione la oleada que desea inspeccionar.
1. En el panel Acción, abra la pestaña **Oleada** y, desde el grupo **Oleada**, seleccione **Trabajos por lotes**.

El procesamiento de ondas se autocorrige, por lo que cualquier error detectado durante el procesamiento debe informarse mediante el Registro de información.

Un error típico relacionado con el procesamiento en paralelo podría ser que dos oleadas intentan asignar el mismo elemento al mismo tiempo y una no se completa, por lo que la otra oleada no puede adquirir un bloqueo dentro del tiempo especificado. Si se produce esta situación, el registro de trabajos por lotes contendrá información que indique que no se pudo adquirir el bloqueo del artículo, en cuyo caso la oleada que falló debe procesarse nuevamente.

Debido a que el procesamiento ocurre en paralelo, los datos deben mantenerse en diferentes tablas para rastrear el estado del procesamiento. Esto significa que los registros de los trabajos por lotes pueden contener errores, como errores de clave duplicada.

Los errores de las tareas por lotes también forman parte del registro de trabajos por lotes. La información más importante suele estar en la parte inferior.

En casos excepcionales, por ejemplo, si finalizó la conexión SQL, es posible que el procesamiento de la oleada termine en un estado incoherente en el que el trabajo por lotes parece estar ejecutándose pero el procesamiento está detenido. La oleada no puede gestionar errores como este, por lo que se realiza un intento de limpiar las oleadas fallidas cuando se ejecuta la siguiente oleada. Alternativamente, si la onda actual está en un estado inconsistente, realice los siguientes pasos:

1. Vaya a **Gestión de almacenes \> Oleadas de salida \> Oleadas de envío \> Todas las oleadas**.
1. Seleccione la oleada que necesita limpiar.
1. En el panel Acción, abra la pestaña **Oleada** y, desde el grupo **Oleada**, seleccione **Limpiar datos de oleada**.

### <a name="troubleshoot-using-the-wave-progress-log"></a>Solucionar problemas utilizando el registro de progreso de oleadas

Si la opción **Crear registro de progreso de oleadas** está habilitada en la página **Parámetros de gestión de almacén**, se crea un registro cada vez que comienza y termina la asignación de un artículo y sus dimensiones. Solo debe habilitar este registro cuando lo necesite, por ejemplo, durante la prueba inicial o para la resolución de problemas. Cuando esta opción está habilitada, puede ver el registro siguiendo los siguientes pasos:

1. Vaya a **Gestión de almacenes \> Oleadas de salida \> Oleadas de envío \> Todas las oleadas**.
1. Seleccione la oleada que desea inspeccionar.
1. En el panel de acciones, abra la pestaña **Oleada**, en el grupo **Oleada**, seleccione **Progreso**.
