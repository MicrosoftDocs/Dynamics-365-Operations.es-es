---
title: Mejorar el rendimiento de la planificación maestra
description: En este tema se explican las distintas opciones que pueden ayudarle a mejorar el rendimiento de la planificación maestra y a resolver problemas.
author: t-benebo
manager: tfehr
ms.date: 12/18/2019
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
ms.openlocfilehash: fa8426c3a1f19f8607f45e9ac4d57300abddb161
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437071"
---
# <a name="improve-master-planning-performance"></a>Mejorar el rendimiento de la planificación maestra

[!include [banner](../includes/banner.md)]

En este tema se explican las distintas opciones que pueden ayudarle a mejorar el rendimiento de la planificación maestra y a resolver problemas. Incluye información sobre parámetros y ajustes, y sobre configuraciones y acciones recomendadas. También se incluye un resumen de todos los parámetros importantes que debe tener en cuenta cuando tenga trabajos de planificación maestra de larga ejecución.

Este tema está dirigido a los administradores de sistemas o usuarios de TI que tienen la capacidad de solucionar problemas. También está dirigido a planificadores de producción o de suministro, ya que incluye información sobre parámetros relacionados con los requisitos de la planificación empresarial. 

## <a name="parameters-related-to-master-planning-performance"></a>Parámetros relacionados con el rendimiento de la planificación maestra

Los distintos parámetros influyen en el tiempo de ejecución de la planificación maestra y deben tenerse en cuenta.

### <a name="number-of-threads"></a>Número de subprocesos

El parámetro **Número de subprocesos** le permite ajustar el proceso de programación maestra para ayudarle a mejorar el rendimiento en el conjunto de datos específico. Este parámetro especifica el número total de subprocesos que se utilizarán para ejecutar una planificación maestra. Produce la paralelización de la ejecución de la planificación maestra, que ayuda a reducir el tiempo de ejecución. 

Puede establecer el parámetro **Número de subprocesos** en el cuadro de diálogo **Ejecución de la planificación maestra**. Para abrir este cuadro de diálogo, vaya a **Planificación maestra \> Planificación maestra \> Ejecutar \> Planificación maestra**, o seleccione **Ejecutar** en el espacio de trabajo **Planificación maestra**. Para determinar el mejor valor para este parámetro, tendrá que confiar en un proceso de prueba y error. Sin embargo, puede usar las siguientes fórmulas para calcular un valor inicial:

- **Si su sector es la fabricación:** (Número de subprocesos) = (Número de pedidos planificados ÷ 1000)
- **De lo contrario:** (Número de subprocesos) = (Número de artículos ÷ 1000)

El número de ayudantes que se utilizan durante la planificación maestra debe ser inferior o igual al número máximo de subprocesos permitidos en el servidor de procesos por lotes. Si el número de ayudantes supera el número de subprocesos en el servidor de procesos por lotes, los subprocesos adicionales no realizarán ningún trabajo.

> [!NOTE]
> Establecer el parámetro **Número de subprocesos** en **0** (cero) aumenta el tiempo de ejecución de la planificación maestra. Por lo tanto, recomendamos que siempre establezca un valor que sea superior a 0.

### <a name="number-of-tasks-in-helper-task-bundle"></a>Número de tareas en la agrupación de trabajos de asistente

Al cambiar la configuración **Número de tareas en agrupación de tareas** (es decir, el tamaño de la agrupación de trabajos), quizás pueda reducir el tiempo de ejecución. Esta configuración controla el número de artículos planificados conjuntamente por un único ayudante.

Puede establecer el parámetro **Número de tareas en agrupación de tareas** en la sección **Rendimiento** en la pestaña **General** de la página **Parámetros de planificación maestra** (**Planificación maestra \> Configuración \> Parámetros de planificación maestra**). El mejor valor para este parámetro depende de sus datos. Por tanto, recomendamos que empiece con un valor de **1** y después utilice un proceso de prueba y error para determinar el mejor valor para su configuración.

En general, recomendamos que aumentará el número de tareas cuando el número de artículos sea muy grande (en los cientos de miles). De lo contrario, debería reducir el número de tareas. Para los siguientes sectores, considere estas recomendaciones:

- En los sectores minoristas y de distribución, donde hay muchos artículos independientes, utilice muchos ayudantes, ya que no hay dependencia entre los artículos. 
- En el sector de la fabricación, donde hay muchas listas de materiales (L. MAT) y subcomponentes compartidos, utilice menos ayudantes, ya que las dependencias entre artículos podrían provocar tiempos de espera.

> [!TIP]
> Si tiene problemas de rendimiento, le recomendamos que reduzca la configuración **Número de ayudantes en agrupación de tareas** a **1**. A continuación, puede iniciar el proceso de prueba y error para encontrar el mejor valor para su configuración. En general, los problemas de rendimiento se producen cuando un artículos tarda más largo en procesar que los artículos restantes. En este caso, verá que dos tareas posteriores que tienen un estado de **Cobertura** en la ejecución de la planificación maestra requieren un tiempo de ejecución considerablemente diferente. En casos extremos, esta diferencia podría ser de hasta 30 minutos. Puede deducir la cantidad de tiempo que tardan en ejecutarse las tareas mirando la duración de cada tarea.

### <a name="use-of-cache"></a>Uso de la memoria caché

El parámetro **Uso de la memoria caché** le permite ajustar el proceso de programación maestra para ayudarle a realizar mejor en el conjunto de datos específico. Por ejemplo, puede ajustarlo para lograr los siguientes resultados:

- Si se realiza más memoria caché, se recopilan más datos en la memoria de datos. La expectativa es que los datos se utilizarán de nuevo más adelante. Si los datos se encuentra en la memoria, puede guardar algunas solicitudes de base de datos. Sin embargo, si se realiza más memoria caché, los requisitos de memoria aumentan.
- Si se realiza menos memoria caché, puede que los mismos datos tengan que obtenerse más a menudo de la base de datos. Además, el Application Object Server (AOS) almacena pocos datos en la memoria durante el proceso.

Es difícil predecir qué opción será mejor, ya que cada caso no solo depende de los datos sino también del hardware. Por ejemplo, puesto que una menor memoria caché provoca una carga adicional en el servidor de base de datos, probablemente no sea una buena idea usar dicha opción si el servidor de base de datos ya está sobrecargado.

Puede establecer el parámetro **Uso de memoria caché** en la sección **Rendimiento** en la pestaña **General** de la página **Parámetros de planificación maestra** (**Planificación maestra \> Configuración \> Parámetros de planificación maestra**). La eficacia de almacenar en memoria caché depende mucho de los datos del cliente. Por ejemplo, si los datos en memoria caché nunca son necesarios, solo pierde memoria si almacena los datos hasta el final del proceso de programación. En este caso, si configura menos memoria en caché, el rendimiento puede aumentar, ya que Microsoft Dynamics AX Application Object Server (AOS) requiere menos memoria y se liberan recursos de servidor para otras tareas.

> [!TIP]
> En general, recomendamos que establezca el parámetro **Uso de memoria caché** en **Máximo**, ya que el parámetro está destinado como una característica que mejora el rendimiento. Recomendamos que establezca el parámetro **Mínimo** si se ejecuta en instalaciones y tiene una memoria limitada (aproximadamente 2 gigabytes \[GB\]).

### <a name="number-of-orders-in-firming-bundle"></a>Número de pedidos de agrupación de puesta en firme

El parámetro **Número de pedidos de agrupación de puesta en firme** especifica el número total de pedidos que serán procesados al mismo tiempo por cada subproceso/lote. Provoca la paralelización del proceso de puesta en firme automática.

Puede establecer el parámetro **Número de pedidos de agrupación de puesta en firme** en la sección **Rendimiento** en la pestaña **General** de la página **Parámetros de planificación maestra** (**Planificación maestra \> Configuración \> Parámetros de planificación maestra**). La paralelización del proceso de puesta en firme automática se basa en los pedidos que se deben procesar juntos. Por ejemplo, si este parámetro se establece en **50**, cada subproceso o tarea por lotes recogerá 50 pedidos al mismo tiempo y los procesará en conjunto. Recomendamos que utilice un proceso de prueba y error para encontrar el mejor valor. Sin embargo, puede usar la siguiente fórmula para calcular un valor inicial:

(Número de pedidos por agrupación de trabajos) = (Número de artículos con demanda ÷ Número de subprocesos)

> [!NOTE]
> Si establece el parámetro **Número de pedidos de agrupación de puesta en firme** en **0** (cero), no se producirá ninguna paralelización del proceso de puesta en firme automática. La totalidad del proceso se ejecutará en una única tarea por lote y tendrá un tiempo de ejecución acumulativo. Por lo tanto, el tiempo de ejecución de su planificación maestra aumentará. Por este motivo, recomendamos que establezca este parámetro en un valor superior a **0** (cero).

### <a name="time-fences"></a>Límites de tiempo

Los límites de tiempo especifican hasta qué punto en el futuro la planificación maestra debe calcular los cálculos y otros requisitos. Cuanto mayor sea el límite de tiempo, más tardará en ejecutarse la planificación maestra. Por lo tanto, establezca los límites de tiempo de acuerdo con sus requisitos empresariales. Para obtener más información acerca de los límites de tiempo, consulte [Configurar planificación maestra](master-planning-setup.md).

### <a name="actions"></a>Acciones

Entre los límites de tiempo, también puede encontrar el parámetro **Mensaje de acción**. El cálculo de mensajes de acción provoca un mayor tiempo de ejecución para la planificación maestra. Si los mensajes de acción no se analizan y aplican de forma periódica (a diario, cada semana, etc.), considere desactivar el cálculo durante la ejecución de la planificación maestra. Para desactivar el cálculo, en la página **Planes maestros**, (**Planificación maestra \> Configuración \> Planes \> Planes maestros**), establezca el límite de tiempo **Mensaje de acción** en **0** (cero). Asegúrese también de que la configuración **Mensaje de acción** está desactivada para todos los grupos de cobertura.

### <a name="futures"></a>Futuros

El cálculo de futuros provoca un mayor tiempo de ejecución para la planificación maestra. Si no planifica las L. MAT, o si los retrasos no tienen que propagarse del suministro a la demanda durante la planificación, considere desactivar cálculos de futuros durante la planificación maestra. Para desactivar los cálculos, establezca el límite de tiempo **Futuros** en **0** (cero) para el plan maestro que se está ejecutando. Asegúrese también de que la configuración **Futuros** está desactivada para todos los grupos de cobertura.

## <a name="one-heavy-routine-at-a-time"></a>Una rutina intensa al mismo tiempo

Cuando programe una planificación maestra, no programe ningún otro trabajo por lotes al mismo tiempo. Tenga especial cuidado de no programar al mismo tiempo ninguna otra rutina intensa, como el cierre de inventario.

## <a name="review-the-session-log"></a>Revisar el registro de sesiones

El sistema puede recopilar información adicional acerca de las tareas que se ejecutan durante la planificación maestra. Para que el sistema recopile esta información, active la configuración **Realizar seguimiento de tiempo procesamiento** en el cuadro de diálogo **Ejecución de la planificación maestra** . La información que se obtiene puede ayudarle a buscar cuellos de botella en la ejecución. Por ejemplo, cuando el parámetro **Número de tareas en la agrupación de trabajos de asistente** se establece en **1**, puede identificar el artículo con el mayor tiempo de ejecución. También puede comparar los tiempos de ejecución para los distintos subprocesos que tengan un estado de **Cobertura** y comparar la duración para cada tarea.

Para revisar las ejecuciones de la planificación maestra de su sistema, siga uno de estos pasos.

- En el espacio de trabajo **Planificación maestra**, seleccione un plan maestro en el campo desplegable y, a continuación, en el icono **Planificación maestra**, seleccione **Historial**. Seleccione un trabajo, seleccionan **Consultas** en la ficha desplegable y, a continuación, seleccione **Duración de la tarea de proceso**.
- En la página **Planes maestros**, seleccione un plan en el panel izquierdo y, a continuación, seleccione **Historial** en la ficha desplegable. Seleccione un trabajo, seleccionan **Consultas** en la ficha desplegable y, a continuación, seleccione **Duración de la tarea de proceso**.

Cuando revise el registro de la sesión, tenga en cuenta lo siguiente:

- **Actualizar** no debe tardar mucho tiempo (en general, debería tardar hasta 30 minutos), sin embargo, se trata de un solo subproceso.
- **Copiar plan** no debería tardar mucho tiempo (debería tardar cerca de un minuto).
- La **Puesta en firme automática** tarda normalmente unos 30 minutos. Sin embargo, puede tardar hasta varias horas, según el número de pedidos y la complejidad de los artículos.
- La **Puesta en firme automática** debe tardar menos tiempo que la **Cobertura**.
- **Cobertura** debe tardar el tiempo más largo en relación con el resto.
- **Acción** y **Mensaje de futuros** pueden llevar mucho tiempo, según los datos y el número de L. MAT.

## <a name="filtering-of-items"></a>Filtrado de artículos

Los filtros que se aplican en el cuadro de diálogo **Ejecución de la planificación maestra** afectan a la duración de la ejecución de la planificación maestra. Vaya a **Planificación maestra \> Planificación maestra \> Ejecutar \> Planificación maestra**, o seleccione **Ejecutar** en el espacio de trabajo **Planificación maestra**. Para excluir artículos de la ejecución, le recomendamos que filtre por el estado del ciclo de vida del artículo (no por los códigos de artículo). Cuando filtre por estado del ciclo de vida, el proceso de actualización tardará menos tiempo que cuando filtre por números de artículo.

## <a name="automatically-filter-by-items-with-direct-demand"></a>Filtrar automáticamente por artículos con demanda directa

Para mejorar el tiempo de ejecución de la planificación maestra, puede elegir incluir solo artículos con demanda directa. Este filtro solo se puede utilizar para una ejecución de planificación maestra completa, sin otros filtros aplicados en el campo **Registros que incluir**. Una ejecución de planificación maestra con filtros no tendrá en cuenta el valor de la opción de configuración **Filtrar automáticamente por artículos con demanda directa**.

El campo **Filtrar automáticamente por artículos con demanda directa** se encuentra en la página **Parámetros de planificación maestra** y se puede usar con configuraciones de preprocesamiento y postprocesamiento.

### <a name="pre-processing"></a>En procesamiento previo
El parámetro **Preprocesamiento: Filtrar automáticamente por artículos con demanda directa** garantiza que la fase de preprocesamiento de la planificación maestra solo incluya elementos que cumplan al menos una de las siguientes condiciones:
  - El artículo tiene un recibo o problema esperado, como un pedido de compra, un pedido de venta, un presupuesto, una orden de transferencia o un pedido de producción. 
  - El artículo tiene cobertura de artículos con existencias de seguridad (inventario mínimo disponible).
  - Existe la previsión de demanda después de hoy para el artículo.
  - Existe la previsión de suministro después de hoy para el artículo.
  - El artículo incluye las líneas de continuidad del módulo del centro de llamadas pendiente de creación.

> [!NOTE]
> Un artículo que tiene un inventario disponible físicamente no mostrará una transacción de requisito porque no hay demanda para el artículo.

### <a name="post-processing"></a>Posprocesamiento
La opción **Postprocesamiento: Filtra automáticamente por artículos con demanda directa** solo es relevante si configura **Requisito de versión de L. MAT** en sus grupos de cobertura. De lo contrario, no tiene que habilitar el parámetro. 

Antes de que comience el paso de cobertura, hay un paso de precobertura durante el cual se volverán a procesar los elementos que tengan la configuración de cobertura **Requisito de versión de L. MAT** habilitada. Esto se hace para garantizar que se planifiquen los artículos de la versión de lista de materiales requerida. Los artículos para los que se consideran que hay demanda durante el preprocesamiento ya no tienen demanda y, por lo tanto, deben excluirse de la ejecución de la planificación.

## <a name="performance-checklist-summary"></a>Resumen de la lista de comprobación del rendimiento

- **Número de subprocesos**: establezca un valor superior a **0** (cero).
- **Número de tareas en agrupación de trabajos del ayudante**: establezca un valor superior **0** (cero). (Utilice las fórmulas que se indican anteriormente en este tema.)
- **Uso de memoria caché**: establezca **Máximo** a menos que su sistema tenga poca memoria.
- **Número de pedidos en agrupación de puesta en firme**: establezca un valor superior **0** (cero). (Utilice la fórmula que se indica anteriormente en este tema.)
- **Límites de tiempo**: ajústelos a sus necesidades empresariales.
- **Acciones y futuros**: deshabilite las accciones y futuros si no las utiliza.
- **Una rutina intensa al mismo tiempo**: no ejecute la planificación maestra junto con ninguna otra rutina intensa.
- **Revisar el registro de sesiones.**
- **Filtrado de artículos**: utilice el estado del ciclo vida para excluir artículos de la ejecución de la planificación maestra. (No utilice los códigos de artículo.)
