---
title: Cargas de trabajo de ejecución de fabricación para unidades de escalado en el perímetro y en la nube
description: Este tema describe cómo funcionan las cargas de trabajo de ejecución de fabricación con unidades de escala de borde y nube.
author: cabeln
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: SCM
ms.author: cabeln
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 9cd7dd8b9241171bdfdb3cc1379211a2fe99bbe1
ms.sourcegitcommit: 8d50c905a0c9d4347519549b587bdebab8ffc628
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2021
ms.locfileid: "6184005"
---
# <a name="manufacturing-execution-workloads-for-cloud-and-edge-scale-units"></a>Cargas de trabajo de ejecución de fabricación para unidades de escalado en el perímetro y en la nube

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> La carga de trabajo de ejecución de fabricación está disponible en versión preliminar en este momento.
> Algunas funciones comerciales no son totalmente compatibles en la versión preliminar pública cuando se utilizan unidades de escala de carga de trabajo.

En la ejecución de la fabricación, las unidades de escala ofrecen las siguientes capacidades:

- Los operadores de máquinas y los supervisores de planta pueden acceder al plan de producción operativo.
- Los operadores de máquinas pueden mantener el plan actualizado mediante la ejecución de trabajos de fabricación discretos y de proceso.
- El supervisor de planta puede ajustar el plan operativo.
- Los trabajadores pueden acceder al tiempo y la asistencia para el registro de entrada y salida en el borde, para garantizar el cálculo correcto del salario del trabajador.

Este tema describe cómo funcionan las cargas de trabajo de ejecución de fabricación con unidades de escala de borde y nube.

## <a name="the-manufacturing-lifecycle"></a>El ciclo de vida de fabricación

Como muestra la siguiente ilustración, el ciclo de vida de la fabricación se divide en tres fases: *Planear*, *Ejecutar* y *Finalizar*.

[![Fases de ejecución de fabricación cuando se utiliza un solo entorno](media/mes-phases.png "Fases de ejecución de fabricación cuando se utiliza un solo entorno")](media/mes-phases-large.png)

La fase _Planear_ incluye la definición del producto, la planificación, la creación y programación de pedidos y la liberación. El paso de liberación indica la transición desde la fase _Planear_ a la fase _Ejecutar_. Cuando se lanza una orden de producción, los trabajos de la orden de producción serán visibles en el piso de producción y estarán listos para su ejecución.

Cuando un trabajo de producción se marca como completado, se mueve desde la fase _Ejecutar_ a la fase _Finalizar_. En la fase _Finalizar_, los registros de la fase *Ejecutar* pasan por un flujo de trabajo de aprobación, donde se calculan, aprueban y transfieren. En ese momento, se completa la orden de producción. Por tanto, se genera la base para la remuneración de los trabajadores.

## <a name="splitting-the-execute-phase-into-a-separate-workload"></a>Dividir la fase de ejecución en una carga de trabajo separada

Como muestra la siguiente ilustración, cuando se utilizan unidades de escala, la fase _Ejecutar_ se divide como una carga de trabajo separada.

[![Fases de ejecución de fabricación cuando se utilizan unidades de escala](media/mes-phases-workloads.png "Fases de ejecución de fabricación cuando se utilizan unidades de escala")](media/mes-phases-workloads-large.png)

El modelo ahora pasa de una instalación de instancia única a un modelo que se basa en el concentrador y las unidades de escala. Las fases _Planear_ y _Finalizar_ se ejecutan como operaciones de back-office en el concentrador y la carga de trabajo de ejecución de fabricación se ejecuta en las unidades de escala. Los datos se transfieren de forma asincrónica entre el concentrador y las unidades de escala.

Cuando se libera una orden de producción en el concentrador, todos los datos necesarios para procesar los trabajos de producción se transfieren a la unidad de escala. Estos datos incluyen órdenes de producción, rutas de producción, listas de materiales y productos. Los datos que no están relacionados con una orden de producción (como actividades indirectas, códigos de ausencia y parámetros de producción) también se transfieren desde el centro a la unidad de escala. Como regla general, los datos que se originan en el concentrador y que se transfieren a la unidad de escala se pueden crear o actualizar solo en el concentrador. Por ejemplo, no se puede crear un nuevo código de ausencia o actividad indirecta en la unidad de escala&mdash;solo se pueden utilizar para el registro. Los registros que se realizan en la unidad de báscula durante la ejecución se transfieren al centro, donde se procesan la aprobación de tiempo y asistencia, el inventario y las actualizaciones financieras.

## <a name="manufacturing-execution-tasks-that-can-be-run-on-workloads"></a>Tareas de ejecución de fabricación que se pueden ejecutar en cargas de trabajo

Las siguientes tareas de ejecución de fabricación se pueden ejecutar actualmente en cargas de trabajo cuando se utilizan unidades de escala:

- Hora de entrada, inicio de sesión, salida y ausencia
- Iniciar trabajo
- Agrupar trabajos
- Informar progreso
- Notificar residuos
- Actividad indirecta
- Descanso
- Notificar como terminado y almacenado (requiere que también ejecute la carga de trabajo de ejecución del almacén en su unidad de escalado, consulte también [Notificar como terminado y almacenado en una unidad de escalado](#RAF))

## <a name="working-with-manufacturing-execution-workloads-on-the-hub"></a>Trabajar con cargas de trabajo de ejecución de fabricación en el hub

Por lo general, los procesos necesarios para ejecutar las cargas de trabajo de ejecución de fabricación se ejecutan automáticamente para mantener sincronizados el concentrador y todas las unidades de escala, según sea necesario. Sin embargo, si tiene problemas, puede activar manualmente el procesamiento de registros sin procesar que se reciben de cargas de trabajo y / o verificar el registro de procesamiento de registros.

### <a name="manually-process-raw-registrations"></a>Procesar manualmente registros sin procesar

Un trabajo por lotes en Supply Chain Management se ejecuta automáticamente para procesar todos los registros que se han recibido de las cargas de trabajo. Este trabajo crea los diarios de producción necesarios y las entradas del libro de registro cuando se procesa un registro para un trabajo completado en la carga de trabajo.

Aunque el trabajo generalmente se ejecuta automáticamente, puede ejecutarlo manualmente en cualquier momento iniciando sesión en el concentrador y yendo a **Control de producción \> Tareas periódicas \> Gestión de la carga de trabajo de backoffice \> Procesar registros sin procesar**.

### <a name="check-the-raw-registration-processing-log"></a>Comprobar el registro de procesamiento de registro sin procesar

Para revisar el registro de procesamiento de registro, inicie sesión en el hub y vaya a **Control de producción \> Tareas periódicas \> Gestión de la carga de trabajo de backoffice \> Registro de procesamiento de registro sin procesar**. La página **Registro de procesamiento de registro sin procesar** muestra una lista de registros sin procesar procesados y el estado de cada registro.

![Página Registro de procesamiento de registro sin procesar](media/mes-processing-log.png "Página Registro de procesamiento de registro sin procesar")

Puede trabajar en cualquier registro de la lista seleccionándolo y luego seleccionando uno de los siguientes botones en el Panel de acciones:

- **Proceso** - Procesar manualmente el registro seleccionado. Esta acción puede resultar útil si el trabajo _Procesar registros sin procesar_ no se ha ejecutado o ha fallado.
- **Cancelar** - Cancelar el registro seleccionado.

## <a name="working-with-manufacturing-execution-workloads-on-a-scale-unit"></a>Trabajar con cargas de trabajo de ejecución de fabricación en una unidad de escala

Por lo general, los procesos necesarios para ejecutar las cargas de trabajo de ejecución de fabricación se ejecutan automáticamente para mantener sincronizados el concentrador y todas las unidades de escala, según sea necesario. Sin embargo, si tiene problemas, puede verificar el historial de pedidos que se han procesado en una unidad de báscula o ejecutar manualmente el trabajo _Centro de fabricación para el procesador de mensajes de la unidad de escala_.

### <a name="view-the-history-of-manufacturing-jobs-that-have-been-processed-on-a-scale-unit"></a>Ver el historial de trabajos de fabricación que se han procesado en una unidad de escala

Para revisar el historial de trabajos de fabricación que se han procesado en una unidad de báscula, inicie sesión en la máquina de la unidad de báscula y vaya a **Control de producción \> Tareas periódicas \> Gestión de la carga de trabajo de backoffice \> Historial de procesamiento de trabajos de fabricación**. La página **Historial de procesamiento de trabajos de fabricación** muestra el historial de procesamiento de las órdenes de producción en la unidad de escalado. Puede trabajar en cualquier orden de producción de la lista seleccionándolo y luego seleccionando uno de los siguientes botones en el Panel de acciones:

- **Proceso** - Procesar manualmente la orden de producción seleccionada.
- **Cancelar** - Cancelar la orden de producción seleccionada.

### <a name="manufacturing-hub-to-scale-unit-message-processor-job"></a>Centro de fabricación para escalar el trabajo del procesador de mensajes de la unidad

El trabajo _Centro de fabricación para el procesador de mensajes de la unidad de escala_ procesa datos desde el centro hasta la unidad de escalado. Este trabajo se inicia automáticamente cuando se implementa la carga de trabajo de ejecución de fabricación. Sin embargo, puede ejecutarlo manualmente en cualquier momento yendo a **Control de producción \> Tareas periódicas \> Gestión de la carga de trabajo de backoffice \> Centro de fabricación para el procesador de mensajes de la unidad de escala**.

<a name="RAF"></a>

## <a name="report-as-finished-and-putaway-on-a-scale-unit"></a>Notificar como terminado y almacenado en una unidad de escalado

<!-- KFM: 
This section describes how to enable the abilities to report as finished and then putaway finished items when you are using to a scale unit.

### Enable and use report as finished and putaway on a scale unit -->

En la versión actual, las operaciones de notificación como terminadas y almacenadas (para productos terminados, coproductos y subproductos) son compatibles con la [carga de trabajo de ejecución de almacén](cloud-edge-workload-warehousing.md) (no con la carga de trabajo de ejecución de fabricación). Por lo tanto, para usar esta funcionalidad cuando está conectado a una unidad de escalado, debe hacer lo siguiente:

- Instale tanto la carga de trabajo de ejecución del almacén como la carga de trabajo de ejecución de fabricación en su unidad de escalado.
- Utilice la aplicación móvil Warehouse Management para notificar como terminado y procesar el trabajo de almacenamiento. Actualmente, la interfaz de ejecución de la planta de producción no admite estos procesos.

<!-- KFM: API details needed

### Customize report as finished and putaway functionality

 -->

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
