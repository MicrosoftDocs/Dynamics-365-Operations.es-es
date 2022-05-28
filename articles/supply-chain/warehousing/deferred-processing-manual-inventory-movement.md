---
title: Procesamiento diferido del movimiento manual de inventario
description: Este tema describe cómo utilizar el procesamiento diferido del movimiento de inventario manual en Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 04/27/2021
ms.topic: article
ms.search.form: WHSWorkProcessingPolicy, WHSWorkDeferredPutProcessingTask
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-04-27
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: c2e7296d77332b665e5d618d39804216f4347ca2
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8670479"
---
# <a name="deferred-processing-of-manual-inventory-movement"></a>Procesamiento diferido del movimiento manual de inventario

[!include [banner](../includes/banner.md)]

Este tema describe cómo utilizar el procesamiento diferido del movimiento de inventario manual en Microsoft Dynamics 365 Supply Chain Management.

El procesamiento diferido permite a trabajadores de almacén seguir realizando otros trabajos mientras se procesa una operación de colocación en segundo plano. El procesamiento diferido también resulta útil si puede haber aumentos ocasionales o imprevistos de tiempo de procesamiento en el servidor y ese aumento del tiempo de procesamiento puede afectar a la productividad de los trabajadores. El tipo de trabajo *Movimiento de inventario* ahora se ha agregado al conjunto de tipos de trabajo que admite esta función.

El procesamiento en segundo plano se logra utilizando la [Función de eventos de aplicaciones de almacén de procesos](warehouse-app-events.md).

## <a name="turn-on-this-feature-for-your-system"></a>Activar esta función para su sistema

Para que esta característica esté disponible, active las siguientes características en la [administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md). Debe activarlos en este orden:

1. *Bloqueo de trabajo en toda la organización*<br>(A partir de la versión 10.0.21 de Supply Chain Management, esta función es obligatoria, por lo que está activada de forma predeterminada y no se puede volver a desactivar).
1. *Procesar eventos de la aplicación de almacén*<br>(A partir de la versión 10.0.25 de Supply Chain Management, esta función está activada de forma predeterminada).
1. *Operaciones de colocación diferidas*
1. *Procesamiento diferido de la operación de movimiento de inventario manual*<br>(A partir de la versión 10.0.25 de Supply Chain Management, esta función es obligatoria, por lo que está activada de forma predeterminada y no se puede volver a desactivar).

## <a name="configure-the-work-processing-policies"></a>Configurar las directivas de procesamiento de trabajos

Para utilizar el procesamiento diferido debe configurar y utilizar una directiva de procesamiento de trabajo. Para el procesamiento de venta diferida, el [Procesamiento diferido de la función de trabajo de almacén](deferred-put.md) admite los siguientes tipos de trabajo: *Pedido de ventas*, *Problema de pedido de transferencia* y *Reabastecimiento*. Las características *Procesamiento diferido de la operación de movimiento de inventario manual* agrega un nuevo tipo de trabajo: *Movimiento de inventario*.

Para configurar una directiva de procesamiento de trabajos, siga estos pasos.

1. Vaya a **Gestión de almacenes \> Configuración \> Trabajo \> Directivas de procesamiento de trabajos**.
1. Seleccione una directiva existente de la lista o cree una nueva directiva seleccionando **Nuevo** en el panel de acciones. El encabezado de cada directiva tiene los siguientes campos:

    - **Nombre de la directiva de procesamiento de trabajo**: el nombre de la directiva de procesamiento de trabajo.
    - **Descripción**: una descripción de la directiva de procesamiento de trabajo.

1. En la ficha desplegable **Reglas de procesamiento**, configure la colección de reglas que aplicará la directiva. Utilice los botones de la barra de herramientas para agregar o eliminar reglas según sea necesario. Para cada regla, establezca los siguientes campos:

    - **Tipo de orden de trabajo**: seleccione el tipo de trabajo al que se aplica la directiva.
    - **Operación**: seleccione la operación que se utiliza para procesar la directiva. Si seleccionó *Movimiento de inventario* en el campo **Tipo de orden de trabajo**, no es necesario que establezca este campo, ya que tanto las operaciones de selección como las operaciones de colocación se procesan como un solo evento.
    - **Método de procesamiento del trabajo**: seleccione el método que se utiliza para procesar la línea de trabajo. Si selecciona *Inmediato*, el comportamiento se parece al que se produce cuando no se usa ninguna directiva de procesamiento de trabajo para procesar la línea. Si selecciona *Diferido*, el sistema aplicará el procesamiento diferido que utiliza el marco por lotes.
    - **Umbral de procesamiento diferido**: si configura este campo en *0* (cero), no hay umbral. En este caso, se utiliza el método de procesamiento *Diferido* si es posible. Si el cálculo de umbral específico está por debajo del umbral, se utiliza el método *Inmediato*. De lo contrario, se utiliza el método *Aplazado* si es posible. Para las ventas y el trabajo relacionado con transferencias, el umbral se calcula como el número de líneas de carga de origen asociadas que se están procesando para el trabajo. Para el trabajo de reabastecimiento, se calcula el umbral como el número de líneas de trabajo que se van a reabastecer por el trabajo. Si se establece un umbral de, por ejemplo, *5* para ventas, se asegura que los trabajos más pequeños que tengan menos de cinco líneas de carga de origen iniciales no usarán el procesamiento diferido, pero sí que lo usarán los trabajos más grandes. El umbral solo surte efecto si el campo **Método de procesamiento de trabajo** se establece en *Aplazado*.
    - **Grupo de lotes de procesamiento diferido**: especifique el grupo de lotes que se utiliza para el procesamiento. Si seleccionó *Movimiento de inventario* en el campo **Tipo de orden de trabajo**, no tiene que configurar este campo, porque el grupo de lotes está seleccionado en el cuadro de diálogo **Procesar eventos de aplicaciones de almacén**.

## <a name="assign-the-work-creation-policy"></a>Asignar la directiva de creación de trabajos

Para obtener detalles sobre cómo asignar una política de creación de trabajo, consulte [Procesamiento diferido de trabajos de almacén](deferred-put.md).

## <a name="set-up-a-batch-job-to-process-warehouse-app-events"></a>Configurar un trabajo por lotes para procesar eventos de aplicaciones de almacén

Para usar el proceso *Procesamiento diferido de la operación de movimiento de inventario manual*, configure un trabajo por lotes programado.

1. Vaya a **Gestión de almacenes \> Tareas periódicas \> Procesar eventos de aplicación de almacén**.
1. En el cuadro de diálogo **Procesar eventos de apicaciones de almacén**, en la ficha desplegable **Ejecutar en segundo plano**, configure la opción **Procesamiento por lotes** como *Sí*.
1. Seleccione **Periodicidad** y configure una programación de ejecución que cumpla con los requisitos de su empresa.
1. Seleccione **Aceptar** en cada cuadro de diálogo.

## <a name="inquire-about-the-warehouse-app-events"></a>Consultar sobre los eventos de la aplicación de almacén

Puede ver la cola de eventos y los mensajes de eventos que genera la aplicación del almacén yendo a **Gestión de almacenes \> Consultas e informes \> Registros de dispositivos móviles \> Eventos de la aplicación de almacén**.

Los mensajes de eventos de *Movimiento de inventario* tendrán un estado de *Puesto en cola* cuando se crean por primera vez. Este estado indica que el trabajo por lotes de **Procesar eventos de aplicación de almacén** recogerá y procesará los mensajes de eventos. Cuando el estado se actualiza a *Completado*, todos los eventos relacionados se eliminan de la cola.

Todos los eventos *Movimiento de inventario* se acumulan en una colección por tipo de evento y almacén.

El trabajo por lotes procesará los eventos de la aplicación de almacén de acuerdo con la periodicidad configurada en el cuadro de diálogo **Procesar eventos de aplicaciones de almacén**. Por lo tanto, hasta que se procese un mensaje, puede encontrar el id. de almacén buscando en el campo **Identificador**.

Los detalles del mensaje contienen los detalles del movimiento (por ejemplo, las ubicaciones "desde" y "hasta").

Para más información, vea [Procesamiento de eventos de la aplicación de almacén](warehouse-app-events.md).

## <a name="configure-the-mobile-device-menu-to-skip-the-deferred-processing-policy"></a>Configurar el menú del dispositivo móvil para omitir la directiva de procesamiento diferido

Para obtener detalles sobre cómo configurar el menú del dispositivo móvil para omitir la política de procesamiento diferido, consulte [Procesamiento diferido de trabajos de almacén](deferred-put.md).

## <a name="impact-on-closed-work-dates"></a>Impacto en las fechas de cierre de trabajo

Para obtener detalles sobre el impacto en las fechas de trabajo cerradas, consulte [Procesamiento diferido de trabajos de almacén](deferred-put.md).

## <a name="additional-resources"></a>Recursos adicionales

- [Procesamiento aplazado de trabajo de almacén](deferred-put.md)
- [Procesamiento de eventos de la aplicación de almacén](warehouse-app-events.md)
- [Configurar dispositivos móviles para el trabajo de almacén](configure-mobile-devices-warehouse.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
