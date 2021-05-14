---
title: Procesamiento aplazado de trabajo de almacén
description: En este tema se describe la funcionalidad que crea el procesamiento diferido de las operaciones de colocación de trabajo de almacén disponibles en Dynamics 365 Supply Chain Management.
author: josaw1
ms.date: 11/18/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWorkProcessingPolicy, WHSWorkDeferredPutProcessingTask
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2019-6-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e2c9fced9091e851683c7dd7727aff693043c433
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956287"
---
# <a name="deferred-processing-of-warehouse-work"></a>Procesamiento aplazado de trabajo de almacén

[!include [banner](../includes/banner.md)]

En este tema se describe la funcionalidad que crea el procesamiento diferido de las operaciones de colocación para trabajo de almacén disponibles en Dynamics 365 Supply Chain Management.

La funcionalidad de procesamiento diferido permite a trabajadores de almacén seguir realizando otros trabajos mientras se procesa la operación de colocación en segundo plano. El procesamiento diferido es útil cuando hay que procesar muchas líneas de trabajo y el trabajador puede dejar que ese trabajo se procese de forma asincrónica. También resulta útil si puede haber aumentos ad hoc o imprevistos de tiempo de procesamiento en el servidor y ese aumento del tiempo de procesamiento puede afectar a la productividad del usuario.

El procesamiento en segundo plano se consigue con el marco de SysOperation. Para obtener más información, consulte [Información general sobre el marco SysOperation](/dynamicsax-2012/developer/sysoperation-framework-overview).

## <a name="configuring-the-work-processing-policies"></a>Configurar las directivas de procesamiento de trabajo

Para utilizar el procesamiento diferido debe configurar y utilizar una directiva de procesamiento de trabajo.

Las directivas se configuran en la página **Directivas de procesamiento de trabajo**. En la tabla siguiente se describen los campos de esa página.

| Campo                           | Descripción |
|---------------------------------|-------------|
| Nombre de directiva de procesamiento de trabajo     | El nombre de la directiva de procesamiento de trabajo. |
| Tipo de orden de trabajo                 | El tipo de orden de trabajo al que se aplica la directiva. |
| Operación                       | La operación que se procesa mediante la directiva. |
| Método de procesamiento de trabajo          | El método que se usa para procesar la línea de trabajo. Si el método está establecido en **Inmediato**, el comportamiento se parece al que se produce cuando no se usa ninguna directiva de procesamiento de trabajo para procesar la línea. Si el método está establecido **Aplazado**, se utiliza el procesamiento diferido que utiliza el marco por lotes. |
| Umbral de procesamiento diferido   | Un valor de **0** (cero) indica que no hay umbral. En este caso, se utiliza el procesamiento diferido si es posible. Si el cálculo de umbral específico está por debajo del umbral, se utiliza el método Inmediato. De lo contrario, se utiliza el método Aplazado si es posible. Para las ventas y el trabajo relacionado con transferencias, el umbral se calcula como el número de líneas de carga de origen asociadas que se están procesando para el trabajo. Para el trabajo de reabastecimiento, se calcula el umbral como el número de líneas de trabajo que se van a reabastecer por el trabajo. Si se establece un umbral de, por ejemplo, **5** para ventas, los trabajos más pequeños que tengan menos de cinco líneas de carga de origen iniciales no usarán el procesamiento diferido; solo lo usarán los trabajos más grandes. El umbral solo surte efecto si el método de procesamiento de trabajo se establece en **Aplazado**. |
| Grupo de lotes de procesamiento diferido |El grupo de lotes que se usa para el procesamiento. |

Para el procesamiento de colocación diferido, se admiten los siguientes tipos de pedido de trabajo: pedido de ventas, emisión de pedido de transferencia, y reabastecimiento.

## <a name="assigning-the-work-creation-policy"></a>Asignación de la directiva de creación de trabajo

La directiva de creación de trabajo se puede asignar en los parámetros de gestión de almacenes. También se puede asignar para almacenes individuales. Si la directiva está asignada a un almacén, solo se aplica a trabajo creado para ese almacén. Si no se ha asignado ninguna directiva en el nivel de almacén, se aplica la directiva especificada en los parámetros de gestión de almacenes.

## <a name="viewing-the-deferred-put-processing-tasks"></a>Ver las tareas de procesamiento de colocación diferidas

Puede ver las tareas de procesamiento de colocación diferidas en la página **Tareas de procesamiento de colocación diferidas**.

De forma predeterminada, se muestran las tareas **Completadas**.

| Campo            | Descripción |
|------------------|-------------|
| Estado           | Estado de la tarea. |
| Estado del trabajo por lotes | Estado del trabajo por lotes relacionado. Si se ha procesado el trabajo por lotes, el historial del lote contiene el registro y la información del trabajo por lotes. |

A continuación se ofrece una explicación de los estados posibles:

- **En espera**: el trabajo por lotes está esperando el procesamiento en el servidor de procesos por lotes.
- **Error**: error de procesamiento. La tarea se puede volver a procesar mediante la acción **Procesar colocación diferida** o se puede cancelar mediante la acción **Cancelar colocación diferida**.
- **Completado**: se ha completado el trabajo.

## <a name="impact-on-closed-work-dates"></a>Impacto en las fechas de cierre de trabajo

Cuando se usa el procesamiento de colocación diferida, la fecha del cierre del trabajo se establece como la fecha o la hora en que se crearon las tareas de procesamiento de colocación diferidas. Se usa la fecha del cierre del trabajo porque es la mejor estimación de cuándo se habrá completado la operación de colocación.

## <a name="reprocessing-a-failed-task"></a>Reprocesamiento de una tarea con error

Puede volver a procesar una tarea con error seleccionándola en la página y seleccionando a continuación **Procesar colocación diferida**. El reprocesamiento corresponde a una situación en la que el usuario completa la ubicación desde el dispositivo móvil si estaba establecida para procesamiento inmediato.

## <a name="canceling-failed-tasks"></a>Cancelar tareas con error

Solo se pueden cancelar las tareas con error. Al cancelar una tarea, puede asignársela a otro usuario. Como alternativa, la tarea puede permanecer asignada al usuario que procesó el trabajo. La cancelación corresponde a una situación en la que el trabajo se trae de vuelta al dispositivo móvil como si el último paso de selección acabara de completarse y hubiera que ubicar el trabajo. Sin embargo, el usuario podrá determinar que el trabajo es "diferente", ya que solo tendrá un paso de ubicación, y la ubicación corresponderá a aquella que el primer usuario que procesó el trabajo tenía como ubicación de colocación final.

Cuando se cancela una tarea, el trabajo deja de estar bloqueado por la razón de bloqueo de procesamiento de colocación diferida. Se puede volver a procesar mediante el dispositivo móvil.

El registro de la tarea se elimina cuando se cancela la tarea.

## <a name="configuring-the-mobile-device-menu-to-skip-the-deferred-processing-policy"></a>Configurar el menú del dispositivo móvil para omitir la directiva de procesamiento diferido

Puede configurar el elemento de menú del dispositivo móvil de forma que no se utilice la directiva de procesamiento diferido. El trabajo se procesa como si no se usara ninguna directiva de procesamiento diferido. Esta funcionalidad permite que un supervisor usar un elemento de menú específico en el que no se usa la colocación diferida. Para configurarlo, establezca el campo **Directiva de procesamiento de colocación diferida** en **Anular configuración y procesar colocación de forma sincrónica**. 

## <a name="restrictions-when-the-deferred-put-processing-isnt-applied"></a>Restricciones cuando no se aplica el procesamiento de colocación diferido

Hay varios escenarios en los que no se aplica el procesamiento de colocación diferido aunque la directiva esté configurada. A continuación se incluyen algunos ejemplos:

- Se usa la finalización del trabajo manual.
- El trabajo se completa mediante finalización automática.
- Se usan plantillas de auditoría.


## <a name="monitoring-the-deferred-processing-tasks-from-the-outbound-work-monitoring-workspace"></a>Supervisar las tareas de procesamiento diferido desde el espacio de trabajo de supervisión del trabajo de salida

El espacio de trabajo **Supervisión de trabajo de salida** tiene dos paneles que le ayuden a controlar las tareas de procesamiento de colocación diferidas:

- **Tareas de procesamiento de colocación con error diferidas**: en este panel se muestra el número de tareas con error. Si hubiera tareas con error, el responsable del almacén debe volver a procesarlas o cancelarlas, ya que no se volverán a procesar automáticamente.
- **Tareas de procesamiento de colocación diferidas en espera**: este panel muestra el número de tareas que han estado en el estado **En espera** durante más de 10 minutos. Si el panel muestra un número, puede indicar que se ha producido un problema durante el procesamiento por lotes. Puede procesar manualmente las tareas **En espera**. Si el trabajo por lotes para una tarea se va a procesar más tarde, se producirá un error, puesto que ya ha sido procesado. No habrá impacto.

## <a name="deleting-completed-tasks"></a>Eliminar tareas completadas

Puede eliminar tareas de procesamiento de colocación diferidas que ya se han completado. Para ello, debe seleccionarlas y eliminarlas en la página.

## <a name="additional-resources"></a>Recursos adicionales

- [Procesamiento diferido de la operación de movimiento de inventario manual](deferred-processing-manual-inventory-movement.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]