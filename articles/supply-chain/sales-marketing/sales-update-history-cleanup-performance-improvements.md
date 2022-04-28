---
title: Programar la limpieza de datos del historial de ventas
description: Este tema describe cómo puede ayudar a mejorar el rendimiento del sistema programando la tarea periódica de limpieza del historial de actualizaciones de ventas para que se ejecute a intervalos regulares.
author: myvakalo
ms.date: 03/21/2022
ms.topic: article
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: myvakalo
ms.search.validFrom: 2021-09-29
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6c6c1e08d45f2a7d1e1267010b286111bad01a6c
ms.sourcegitcommit: 197e6ddee84522fd587c6e4ee4f9089101e301c2
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2022
ms.locfileid: "8570405"
---
# <a name="schedule-sales-history-data-cleanup"></a>Programar la limpieza de datos del historial de ventas

[!include [banner](../includes/banner.md)]

Como parte de su operación estándar, Microsoft Dynamics 365 Supply Chain Management genera y almacena datos de actualización del historial de ventas de forma continua. Con el tiempo, es posible que se acumule en su sistema una gran cantidad de datos de historial de ventas desactualizados. Estos datos acumulados pueden causar problemas funcionales y de rendimiento cuando se registran documentos relacionados con pedidos de ventas. (Estos documentos incluyen confirmaciones de órdenes de venta, albaranes de ventas, listas de selección de ventas y facturas). Por lo tanto, debe configurar y programar la tarea periódica *Limpieza del historial de actualizaciones de ventas* para ejecutarla a intervalos regulares. Esta tarea eliminará todos los datos de actualización del historial de ventas que ya no sean necesarios.

Si usa la tarea periódica *Limpieza del historial de actualizaciones de ventas*, le recomendamos que habilite la característica *Mejoras en el rendimiento de la limpieza del historial de ventas*, lo que hace que la tarea se ejecute de manera más efectiva. (Sin embargo, también puede ejecutar la tarea sin habilitar esta característica).

## <a name="turn-on-the-sales-history-cleanup-features"></a>Activar las funciones de limpieza del historial de ventas

Para configurar y utilizar la tarea periódica *Limpieza del historial de actualizaciones de ventas* junto con todas las características que se describen en este tema, debe habilitar las características *Mejoras en el rendimiento de la limpieza del historial de ventas* y *Limpiar el historial de actualizaciones de ventas según la edad* en Administración de características, como se describe en las siguientes subsecciones.

### <a name="sales-history-cleanup-performance-improvements"></a>Mejoras de rendimiento de limpieza del historial de ventas

El trabajo por lotes periódico **Limpieza del historial de ventas** puede llevar mucho tiempo si se ejecuta con poca frecuencia en entornos con un gran volumen de actualizaciones de ventas. En estas situaciones, la característica *Mejoras en el rendimiento de la limpieza del historial de ventas* puede ayudar a reducir la duración de la ejecución y mejorar la fiabilidad.

La característica mejora el trabajo de limpieza existente de las siguientes formas:

- Divide la limpieza en lotes (puede cambiar el tamaño del lote mediante personalizaciones).
- Se ejecutará durante un máximo de 2 horas (puede cambiar la duración mediante personalizaciones).
- Siempre que sea posible, aprovechará las capacidades de la base de datos para minimizar el bloqueo y evitar unir tablas transaccionales durante la limpieza.

Después de habilitar la característica, el trabajo por lotes **Limpieza del historial de actualizaciones de ventas** (**Ventas y marketing \> Tareas periódicas \> Limpiar \> Limpieza del historial de actualizaciones de ventas**) funcionará como antes, pero con un mejor rendimiento y durante un máximo de 2 horas. Esto significa que es posible que deba ejecutarse varias veces para limpiar todos los datos durante un periodo de tiempo de retención específico.

Para poder usar esta característica, debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla. En el espacio de trabajo **Administración de características**, la función aparece de la siguiente forma:

- **Módulo:** *Ventas y marketing*
- **Nombre de la característica:** *Mejoras en el rendimiento de la limpieza del historial de ventas*

### <a name="clean-up-sales-update-history-based-on-age"></a>Eliminar historial de actualización de ventas según la antigüedad

La característica *Limpiar el historial de actualizaciones de ventas según la edad* le permite especificar la antigüedad máxima de los registros que se deben mantener al ejecutar la tarea periódica *Limpieza del historial de actualización de ventas*. Se eliminarán los registros más antiguos. Esta característica es útil al configurar la tarea para que se ejecute periódicamente porque la edad siempre se calcula en relación con la fecha en que se ejecuta la tarea. Si no usa esta característica, solo puede establecer una fecha específica para conservar los registros más antiguos.

Para poder usar esta característica, debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla. En el espacio de trabajo **Administración de características**, la función aparece de la siguiente forma:

- **Módulo:** *Ventas y marketing*
- **Nombre de característica:** *Eliminar historial de actualización de ventas según la edad*

## <a name="set-up-and-schedule-the-sales-history-cleanup-periodic-task"></a>Configurar y programar la tarea periódica de limpieza del historial de ventas

Para configurar y programar la tarea periódica *Limpieza del historial de ventas*, siga estos pasos.

1. Analice las necesidades de su negocio para determinar cuántos días de datos históricos de registro de órdenes de venta debe conservar. Por lo general, recomendamos que ejecute la tarea de limpieza cada tres meses y como máximo cada seis meses.
1. Vaya a **Ventas y marketing \> Tareas del período \> Limpiar \> Limpieza del historial de actualizaciones de ventas**.
1. En el cuadro de diálogo **Limpiar historial de actualizaciones de ventas**, en la ficha desplegable **Parámetros**, establezca los siguientes campos:

    - **Limpiar**: seleccione uno de los siguientes valores para especificar el tipo de registros a limpiar:

        - **Ejecutado**: eliminar solo los registros que se hayan procesado por completo. Debido a que es poco probable que tenga más uso de estos registros, esta opción es la más segura.
        - **Ejecutado y erróneo**: elimine tanto los registros totalmente procesados como los registros en los que se ha producido un error. Esta opción es la más utilizada. Es posible que desee inspeccionar e incluso corregir registros erróneos en lugar de limpiarlos automáticamente. Sin embargo, muchas empresas eligen limpiar estos registros también después de aproximadamente un mes, porque probablemente ya no sean relevantes en ese momento.
        - **Todos**: elimine registros ejecutados, erróneos y en espera. Los registros en espera son válidos pero aún no se han procesado por completo. En la mayoría de los casos, probablemente no desee que se eliminen automáticamente. Sin embargo, en algunas situaciones, puede elegir que se eliminen automáticamente después de que haya transcurrido un período de tiempo específico.

    - **Conservar registros según la edad**: especifique si desea limpiar los registros en función de su edad el día en que se ejecuta la tarea o eliminar los registros que se crearon antes de una fecha fija. Si está programando la limpieza como una tarea periódica, debe establecer esta opción en *Sí*, porque la edad siempre se calcula en relación con la fecha en que se ejecuta la tarea.

        - Establezca esta opción en *Sí* para habilitar el campo **Edad máxima**. Utilice este campo para especificar la edad máxima de los registros que se deben conservar cada vez que se ejecuta la tarea. El campo **Creado hasta** se ignora.
        - Establezca esta opción en *No* para habilitar el campo **Creado hasta**. Utilice este campo para especificar la fecha de creación más antigua de los registros que se deben conservar cada vez que se ejecuta la tarea. El campo **Edad máxima** se ignora.

    - **Creado hasta**: este ajuste se aplica solo cuando la opción **Conservar registros según la edad** está configurada en *No*. Especifique la fecha de creación más antigua de los registros que se deben conservar cada vez que se ejecuta la tarea. Los registros que se crearon antes de esta fecha se eliminarán.
    - **Edad máxima**: este ajuste se aplica solo cuando la opción **Conservar registros según la edad** está configurada en *Sí*. Especifique la edad máxima (en días) de los registros que se deben conservar cada vez que se ejecuta la tarea. Se eliminarán los registros más antiguos.

1. En la ficha desplegable **Ejecutar en segundo plano**, especifique cómo, cuándo y con qué frecuencia se ejecuta la tarea. Utilice esta configuración para implementar la programación que determinó en el paso 1. Los campos funcionan igual que o hacen para otros tipos de [trabajos por lotes](../../fin-ops-core/dev-itpro/sysadmin/batch-processing-overview.md) en Supply Chain Management.
1. Seleccione **Aceptar** para aplicar su configuración y cerrar el cuadro de diálogo.
