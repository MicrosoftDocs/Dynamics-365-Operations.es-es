---
title: Programar la creación del trabajo durante la oleada
description: Este tema describe cómo configurar y utilizar el método de programación de procesamiento de oleada de creación de trabajos.
author: perlynne
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 5b1e798ac0558e7c5b0bbe4b6a732cbdcf5729a1
ms.sourcegitcommit: 008779c530798f563fe216810d34b2d56f2c8d3c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/14/2021
ms.locfileid: "7920133"
---
# <a name="schedule-work-creation-during-wave"></a>Programar la creación del trabajo durante la oleada

[!include [banner](../../includes/banner.md)]

Use la característica *Programar creación de trabajo* como parte de su proceso de oleada para ayudar a aumentar el rendimiento del procesamiento de oleadas al hacer que el sistema cree trabajo utilizando el procesamiento paralelo.

Cuando la funcionalidad está habilitada, el trabajo planificado se creará automáticamente y el sistema lo procesará para crear el trabajo real. Si el número de líneas de carga de oleada alcanza un umbral predeterminado, el sistema creará trabajo real más rápidamente aplicando el procesamiento asincrónico paralelo.

## <a name="turn-on-the-scheduled-work-creation-features-in-feature-management"></a>Activar las funciones de creación de trabajos programados en la gestión de funciones

Para utilizar las funciones descritas en este tema, deben estar activadas en su sistema. Use el espacio de trabajo [Administración de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md), para activar las siguientes funciones en este orden:

1. **Bloqueo de trabajo en toda la organización**: requerido para la configuración manual y automática de la creación de trabajos programados. (A partir de la versión 10.0.21 de Supply Chain Management, esta función es obligatoria, por lo que está activada de forma predeterminada y no se puede volver a desactivar).
1. **Creación de trabajo programado**: requerido para la configuración manual y automática de la creación de trabajos programados.
1. **Método de oleada "Creación de trabajo programado" en toda la organización**: requerido para la configuración automática de la creación de trabajos programados. No necesita esta función si solo va a utilizar la configuración manual.

<a name="Auto-enable-schedule-work-creation"></a>

## <a name="automatically-configure-scheduled-work-creation"></a>Configurar automáticamente la creación de trabajos programados

Si habilita la función *Método de oleada de "creación de trabajos programados" para toda la organización*, lo siguiente ocurre automáticamente en su sistema:

- El método de oleada *Programar creación de trabajo* (`WHSScheduleWorkCreationWaveStepMethod`) se agrega y configura para ejecutarse en paralelo en todas las entidades legales.
- Las plantillas de oleada de todas las entidades jurídicas que tienen **Tipo de plantilla de oleada** ajustado a *Transporte* y **Estado de la plantilla** ajustado a *Válido* tendrán el método *Creación de trabajo* reemplazado por el método *Programar creación de trabajo*. Sin embargo, las plantillas de oleada de entidades jurídicas donde el método *Crear trabajo* se permite que se pueda repetir no se modificará.
- Configuraciones de tareas para el método *Programar creación de trabajo* se crearán para todos los almacenes de todas las entidades jurídicas que tienen **Utilizar procesos de gestión de almacenes** activado. Esto significa que el método *Programar creación de trabajo* ahora se ejecutará en paralelo de forma predeterminada. Almacenes existentes en los que cambia **Utilizar procesos de gestión de almacenes** desde *No* a *Sí* también ejecutarán este método en paralelo de forma predeterminada.
- Todas las entidades jurídicas procesarán oleadas en lotes y **Esperar el bloqueo (ms)** se establecerá en un valor predeterminado de *60 000* ms si se configuró previamente en *0* ms.
- Todas las nuevas plantillas de oleadas que cree tendrán el método *Programar creación de trabajo* de oleada en lugar del método *Crear trabajo*.

Las configuraciones de procesamiento de oleadas y tareas existentes también se mantendrán para todas las entidades jurídicas que ya están configuradas para procesar oleadas en lotes, y para todos los almacenes que ya están configurados para usar el método *Programar creación de trabajo* en paralelo.

Si es necesario, puede revertir manualmente cualquiera o todos los ajustes realizados automáticamente cuando habilitó la característica *Método de oleada de creación de trabajo programado para toda la organización* haciendo lo siguiente:

- Para plantillas de oleada vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**. Reemplace el método *Programar creación de trabajo* con *Crear trabajo*.
- Para los parámetros de almacén, vaya a **Gestión de almacenes \> Configurar \> Parámetros de gestión de almacenes**. En la pestaña **Procesamiento de oleadas**, aplique sus valores preferidos para **Procesar oleadas en lote** y **Esperar el bloqueo (ms)**.
- Para los métodos de oleada, vaya a **Gestión de almacenes \> Configuración \> Oleadas \> Métodos de proceso de oleadas**. Seleccione `WHSScheduleWorkCreationWaveStepMethod` y en el panel de acciones seleccione **Configurar tarea**. Modifique o elimine la cantidad de tareas por lotes y el grupo de oleadas asignado para cada almacén listado según sea necesario.

## <a name="manually-configure-scheduled-work-creation"></a>Configurar manualmente la creación de trabajos programados

Si no habilitó la [función *Método de oleada de "creación de trabajos programados" para toda la organización*](#Auto-enable-schedule-work-creation), puede utilizar los procedimientos proporcionados en esta sección para configurar manualmente la creación de trabajos programados según sea necesario.

### <a name="manually-enable-batch-processing-of-waves"></a>Habilite manualmente el procesamiento por lotes de oleadas

Para aprovechar un método asincrónico paralelo para crear trabajo de almacén, su proceso de oleada debe ejecutarse por lotes. Para configurar:

1. Vaya a **Gestión de almacenes \> Configuración \> Parámetros de gestión de almacenes**.
1. En la pestaña **General**, establezca **Procesar oleadas en lote** a *Sí*. Opcionalmente, también puede seleccionar **Grupo de lotes de procesamiento de oleadas** para evitar que el procesamiento de la cola por lotes se ejecute al mismo tiempo que otros procesos.
1. Elija la **hora de Esperar bloqueo (ms)**, que se aplica cuando el sistema está procesando varias oleadas al mismo tiempo. Para la mayoría de los procesos de creación de oleadas más grandes, recomendamos un valor de *60 000*.

### <a name="manually-enable-the-new-wave-step-method-for-existing-wave-templates"></a>Habilitar manualmente el nuevo método de paso de oleada para plantillas de oleada existentes

Comience creando el nuevo método de paso de oleada y habilitándolo para el procesamiento de tareas asincrónicas en paralelo.

1. Vaya a **Gestión de almacenes \> Configuración \> Oleadas \> Métodos de proceso de oleadas**.
1. Seleccione **Regenerar métodos** y vea que se ha agregado *WHSScheduleWorkCreationWaveStepMethod* a la lista de métodos de proceso de oleada que puede utilizar en sus plantillas de oleada de envío.
1. Seleccione el registro con el **Nombre del método** *WHSScheduleWorkCreationWaveStepMethod* y seleccione **Configuración de tareas**.
1. Para agregar una nueva fila a la cuadrícula, seleccione **Nuevo** en el panel de acciones y use los siguientes ajustes:

    - **Almacén**: seleccione el almacén que utilizará para programar el procesamiento de creación de trabajo.
    - **Número máximo de tareas por lotes**: especifique un número máximo de tareas por lotes. En la mayoría de los casos, este valor debe estar entre 8 y 16; sin embargo, le recomendamos que experimente con la configuración óptima según sus escenarios.
    - **Grupo de lotes de procesamiento de oleadas**: seleccione un grupo de lotes de procesamiento de oleadas dedicado para optimizar el procesamiento de la cola de lotes.

Ahora puede actualizar una plantilla de oleada existente (o crear una nueva) para usar el método de procesamiento de oleadas *Programar creación de trabajo*.

1. Vaya a **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.
1. En el panel Acciones, seleccione **Editar**.
1. En el panel de lista, seleccione la plantilla de oleada que le gustaría actualizar (si está probando con datos de demostración, entonces podría usar *Envío predeterminado 24*).
1. Amplíe la ficha desplegable **Métodos** y seleccione la fila con el **Nombre** *Programar creación de trabajo* en la cuadrícula **Métodos restantes**.
1. Seleccione la flecha que apunta a la columna **Métodos seleccionados** para mover la fila seleccionada a esa columna. (Solo puede seleccionar un método a la vez que utilice `WHSScheduleWorkCreationWaveStepMethod` o `createWork` y así la fila existente con **Nombre del método** `createWork` se mueve automáticamente a la cuadrícula **Métodos restantes**).

## <a name="set-wave-task-processing-threshold-data"></a>Establecer datos de umbral de procesamiento de tareas de oleadas

El sistema creará datos de umbral de procesamiento de tareas de oleada predeterminados la primera vez que se ejecute un proceso de oleada utilizando cualquier procesamiento basado en tareas. Los datos se utilizan para controlar cuándo el procesamiento de oleadas se ejecutará de forma asincrónica y se basará en tareas, lo que le permite procesar y crear trabajo en paralelo.

Los datos predeterminados utilizarán inicialmente un valor de umbral de 15 para el número mínimo de líneas de carga (`MINIMUMWAVELOADLINES`). Esto significa que cuando el sistema procesa una oleada con más de 15 líneas de carga, utilizará el procesamiento de tareas asincrónico. Puede insertar / actualizar manualmente estos datos en la tabla `WHSWaveTaskProcessingThresholdParameters` en sus entornos de prueba. Si necesita cambiar esta configuración en un entorno de producción, debe contactar con el Soporte de Microsoft para solicitar la actualización.

## <a name="work-with-the-scheduled-work-creation"></a>Trabajar con la creación de trabajo programada

Para obtener detalles sobre cómo trabajar con la creación de trabajos programados, consulte [Creación y procesamiento de oleadas](wave-processing.md). 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
