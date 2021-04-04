---
title: Programar la creación del trabajo durante la oleada
description: Este tema describe cómo configurar y utilizar el método de programación de procesamiento de oleada de creación de trabajos.
author: perlynne
manager: mirzaab
ms.date: 01/14/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSPostMethod, WHSWavePostMethodTaskConfig, WHSWaveTemplateTable, WHSParameters, WHSWaveTableListPage, WHSWorkTableListPage, WHSWorkTable, BatchJobEnhanced, WHSPlannedWorkOrder
audience: Application User
ms.reviewer: ''
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2021-01-14
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 36a450f78695f617056875f8d236fe46bc66aaaf
ms.sourcegitcommit: 2b4809e60974e72df9476ffd62706b1bfc8da4a7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/04/2021
ms.locfileid: "5501231"
---
# <a name="schedule-work-creation-during-wave"></a>Programar la creación del trabajo durante la oleada

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Use la característica *Programar creación de trabajo* como parte de su proceso de oleada para ayudar a aumentar el rendimiento del procesamiento de oleadas al hacer que el sistema cree trabajo utilizando el procesamiento paralelo.

Cuando la funcionalidad está habilitada, el trabajo planificado se creará automáticamente y el sistema lo procesará para crear el trabajo real. Si el número de líneas de carga de oleada alcanza un umbral predeterminado, el sistema creará trabajo real más rápidamente aplicando el procesamiento asincrónico paralelo.

## <a name="enable-the-schedule-work-creation-feature"></a>Habilitar la característica Programar creación de trabajo

### <a name="enable-the-feature-in-feature-management"></a>Habilitar la característica en la administración de características

Antes de poder usar la característica *Programar creación de trabajo* debe estar activada en su sistema. Los administradores pueden usar el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la característica y activarla si es necesario. Allí, la característica se enumera de la siguiente manera:

- **Módulo:** *Gestión de almacén*
- **Nombre de característica:** *Programar creación de trabajo*

> [!NOTE]
> La característica *Bloqueo de trabajo en toda la organización* debe estar habilitada antes de poder habilitar *Programar creación de trabajo*.

### <a name="manually-enable-batch-processing-of-waves"></a>Habilite manualmente el procesamiento por lotes de oleadas

Para aprovechar un método asincrónico paralelo para crear trabajo de almacén, su proceso de oleada debe ejecutarse por lotes. Para configurar:

1. Vaya a  **Gestión de almacenes \> Configurar \> Parámetros de gestión de inventario y almacenes**.

1. En la pestaña **General**, establezca **Procesar oleadas en lote** a *Sí*. Opcionalmente, también puede seleccionar **Grupo de lotes de procesamiento de oleadas** para evitar que el procesamiento de la cola por lotes se ejecute al mismo tiempo que otros procesos.

1. Elija la **hora de Esperar bloqueo (ms)**, que se aplica cuando el sistema está procesando varias oleadas al mismo tiempo. Para la mayoría de los procesos de creación de oleadas más grandes, recomendamos un valor de *60 000*.

### <a name="manually-enable-the-new-wave-step-method-for-existing-wave-templates"></a>Habilitar manualmente el nuevo método de paso de oleada para plantillas de oleada existentes

Comience creando el nuevo método de paso de oleada y habilitándolo para el procesamiento de tareas asincrónicas en paralelo.

1. Vaya a  **Gestión de almacenes \> Configuración \> Oleadas \> Métodos de proceso de oleadas**.

1. Seleccione  **Regenerar métodos** y vea que se ha agregado *WHSScheduleWorkCreationWaveStepMethod* a la lista de métodos de proceso de oleada que puede utilizar en sus plantillas de oleada de envío.

1. Seleccione el registro con el **Nombre del método** *WHSScheduleWorkCreationWaveStepMethod* y seleccione **Configuración de tareas**.

1. Para agregar una nueva fila a la cuadrícula, seleccione **Nuevo** en el panel de acciones y use los siguientes ajustes:

    - **Almacén**: seleccione el almacén que utilizará para programar el procesamiento de creación de trabajo.

    - **Número máximo de tareas por lotes**: especifique un número máximo de tareas por lotes. En la mayoría de los casos, este valor debe estar entre 8 y 16; sin embargo, le recomendamos que experimente con la configuración óptima según sus escenarios.

    - **Grupo de lotes de procesamiento de oleadas**: seleccione un grupo de lotes de procesamiento de oleadas dedicado para optimizar el procesamiento de la cola de lotes.

Ahora puede actualizar una plantilla de oleada existente (o crear una nueva) para usar el método de procesamiento de oleadas *Programar creación de trabajo*.

1. Vaya a  **Gestión de almacenes \> Configurar \> Oleadas \> Plantillas de oleada**.

1. En el panel Acciones, seleccione **Editar**.

1. En el panel de lista, seleccione la plantilla de oleada que le gustaría actualizar (si está probando con datos de demostración, entonces podría usar *Envío predeterminado 24*).

1. Amplíe la ficha desplegable **Métodos** y seleccione la fila con el **Nombre** *Programar creación de trabajo* en la cuadrícula **Métodos restantes**.

1. Seleccione la flecha que apunta a la columna **Métodos seleccionados** para mover la fila seleccionada a esa columna. (Solo puede seleccionar un método a la vez que utilice *WHSScheduleWorkCreationWaveStepMethod* o *createWork* y así la fila existente con **Nombre del método** *createWork* se mueve automáticamente a la cuadrícula **Métodos restantes**).

## <a name="set-wave-task-processing-threshold-data"></a>Establecer datos de umbral de procesamiento de tareas de oleadas

El sistema creará datos de umbral de procesamiento de tareas de oleada predeterminados la primera vez que se ejecute un proceso de oleada utilizando cualquier procesamiento basado en tareas. Los datos se utilizan para controlar cuándo el procesamiento de oleadas se ejecutará de forma asincrónica y se basará en tareas, lo que le permite procesar y crear trabajo en paralelo.

Los datos predeterminados utilizarán inicialmente un valor de umbral de 15 para el número mínimo de líneas de carga (MINIMUMWAVELOADLINES). Esto significa que cuando el sistema procesa una oleada con más de 15 líneas de carga, utilizará el procesamiento de tareas asincrónico. Puede insertar o actualizar manualmente estos datos en la tabla **WHSWaveTaskProcessingThresholdParameters** en sus entornos de prueba, pero si necesita cambiar esta configuración en un entorno de producción, debe comunicarse con el Soporte técnico de Microsoft para solicitar la actualización.

## <a name="work-with-the-feature"></a>Trabajar con la característica

Cuando la función *Programar creación de trabajo* está habilitada, el procesamiento de oleadas creará el trabajo planificado, que al final será utilizado por el proceso de creación de un nuevo trabajo. Durante la creación del trabajo, este se bloqueará mediante la característica *Bloqueo de trabajo en toda la organización*.

El siguiente diagrama de flujo muestra cómo se crea el trabajo planificado durante el procesamiento de oleadas.

![Programar la creación del trabajo](media/schedule-work-creation-process.png)

### <a name="planned-work"></a>Trabajo planificado

La página **Detalles del trabajo planificado** (**Gestión de almacenes \> Trabajo \> Detalles del trabajo planificado**) muestra información sobre el trabajo planificado, que se crea inicialmente durante el procesamiento de oleadas. Están disponibles los siguientes valores de **Estado de progreso**:

- **Puesto en cola**: El trabajo planificado está a la espera de ser utilizada para crear trabajo.
- **Completado**: el trabajo planificado se ha utilizado para crear trabajo.
- **Error**: el procesamiento de la oleada ha fallado. Tenga en cuenta que el trabajo planificado puede estar en estado de **Error** con o sin trabajo real relacionado. Cuando falla el proceso de creación del trabajo real, el trabajo real permanece en estado *Cancelado*.

### <a name="batch-job-for-the-work-creation-process"></a>Trabajo por lotes para el proceso de creación de trabajo

Para ver los trabajos por lotes para procesar oleadas, seleccione **Trabajos por lotes** en el panel de Acción en la página **Todas las oleadas**.

Desde aquí, puede ver todos los detalles de la tarea por lotes para cada uno de los Id. de trabajo por lotes.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]