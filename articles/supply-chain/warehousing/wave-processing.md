---
title: Creación y procesamiento de oleadas
description: En este tema se describe cómo crear, procesar y liberar una oleada para crear un trabajo de picking para una carga, un envío, un pedido de producción o un pedido del kanban.
author: Mirzaab
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSWaveTemplateTable, WHSParameters, whswavetablecreatenew, WHSWaveTable, WHSWaveAttributes, WHSKanbanWaveTable, WHSWaveTableListPage, WHSKanbanWaveTableListPage, WHSProdWaveTable
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Release 10.0.18
ms.openlocfilehash: 76b11eaec0f22393e877c2837e2533a176018f2b
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6355491"
---
# <a name="wave-creation-and-processing"></a>Creación y procesamiento de oleadas

[!include [banner](../includes/banner.md)]

En este tema se describe cómo crear, procesar y liberar una oleada para crear un trabajo de picking para una carga, un envío, un pedido de producción o un pedido del kanban. Puede crear oleadas para los siguientes tipos de pedidos:

- **Pedidos de ventas**: use oleadas de envío para incluir líneas de pedidos de ventas. Cuando un pedido de ventas se libera al almacén, las líneas de pedido de ventas se pueden incluir en la oleada.
- **Pedidos de producción**: use oleadas de producción para incluir líneas a partir de la lista de materiales (L. MAT) para un producto.
- **Pedidos kanban**: las oleadas de kanban incluyen líneas de la lista de selección de pedidos kanban.

Para los pedidos de ventas y las órdenes de kanban, el inventario se debe reservar antes de que el pedido se libere al almacén. Si no, los artículos o las líneas de asignación no se pueden procesar en una oleada. Sin embargo, los pedidos de producción son ligeramente más flexibles. Para pedidos de producción, puede elegir cualquiera de las siguientes opciones:

- Requerir que todos los materiales se reserven antes de poder liberar el pedido al almacén.
- Permitir que los pedidos de producción se liberen al almacén aunque no todos los materiales se puedan reservar. Si selecciona esta opción, debe repetir manualmente el proceso de liberación al almacén cuando los materiales adicionales estén disponibles. Por ejemplo, esto resulta útil si tiene los materiales que necesita para iniciar una producción y puede esperar hasta que los materiales adicionales estén disponibles.

Puede especificar cuál de estas opciones de orden de producción utilizar de forma predeterminada mediante el campo **Requisito de reserva de material** en la página **Parámetros de control de producción**. Sin embargo, puede cambiar la opción de configuración para cada pedido de producción específico según sea necesario. Para más información, consulte [Parámetros de almacén para procesamiento de oleadas](wave-warehouse-parameters.md).

## <a name="create-and-process-a-wave"></a>Crear y procesar una oleada

El siguiente diagrama muestra el flujo de cómo se crean, procesan y liberan las oleadas de envío. Los números se corresponden con las secciones descritos más adelante en esta sección.

![Proceso para crear una oleada.](media/wave-processing-diagram.png "Proceso para crear una oleada")

### <a name="prerequisites"></a>Requisitos previos

Antes de comenzar, debe haber disponible una plantilla de oleada para el tipo de oleada que desea crear (envío, producción o kanban). La plantilla de oleada establece muchas configuraciones sobre cómo se generará y procesará la oleada, incluidos los pasos que se deben realizar manualmente y los que se realizan automáticamente. Para obtener más información, vea [Plantillas de oleada](wave-templates.md).

### <a name="create-a-wave"></a>Crear una oleada

#### <a name="automatically-create-waves-based-on-warehouse-and-order-type"></a>Cree oleadas automáticamente según el almacén y el tipo de pedido

Para crear oleadas automáticamente, configure [Plantillas de oleada](wave-templates.md) que se aplican a cada tipo de pedido y almacén relevante. Asegúrese de que cada plantilla tenga la opción **Automatizar la creación de oleadas** establecida en *Sí*.

#### <a name="manually-create-waves"></a>Crear oleadas manualmente

Para crear una oleada manualmente, siga estos pasos:

1. Asegúrese de que las [Plantillas de oleada](wave-templates.md) relevantes no están configuradas para crear automáticamente una oleada para el almacén y los tipos de pedido en los que desea hacerlo manualmente.
1. En función del tipo de oleada que quiera a crear, use una de las siguientes opciones:

    - Vaya a **Gestión de almacenes** \> **Común** \> **Oleadas** \> **Oleadas de envío** \> **Todas las oleadas**. En el panel Acciones, seleccione **Oleada**.
    - Vaya a **Gestión de almacenes** \> **Común** \> **Oleadas** \> **Oleadas de producción** \> **Todas las oleadas de producción**. En el panel Acciones, seleccione **Oleada de producción**.
    - Vaya a **Gestión de almacenes** \> **Común** \> **Oleadas** \> **Oleadas kanban** \> **Todas las oleadas kanban**. En el panel Acciones, seleccione **Crear oleada**.

1. En el campo **Descripción**, especifique una descripción breve de la oleada. Esta debe indicar lo que va a procesar en la oleada.

1. En el campo **Nombre de plantilla de oleada**, seleccione la plantilla de oleada del tipo de oleada que desee crear. La plantilla de oleada contiene los métodos de oleada que realizarán acciones como la creación de trabajo para la oleada. Por ejemplo, la plantilla de oleada para oleadas de envío puede contener métodos para crear cargas, asignar líneas a las oleadas, reabastecer y crear trabajo de picking para la oleada.

1. Si desea usar atributos de oleada como criterios de consulta adicionales para la oleada, seleccione los atributos de los campos **Atributos de oleada**.

### <a name="specify-what-to-include-in-a-wave"></a>Especifique qué incluir en una oleada

Una vez que se ha creado una oleada, está listo para comenzar a agregarle contenido.

> [!NOTE]
> Si es necesario, puede agregar líneas a una oleada incluso después de que se haya procesado, siempre que no se haya liberado.

#### <a name="automatically-specify-what-to-include-in-a-wave"></a>Especifique automáticamente qué incluir en una oleada

Para crear oleadas automáticamente, configure [Plantillas de oleada](wave-templates.md) que se aplican a cada tipo de pedido y almacén relevante. Asegúrese de que cada plantilla tenga la opción **Automatizar la creación de oleadas** establecida en *Sí*. Alternativamente, su plantilla podría asignar líneas automáticamente a cualquier oleada abierta calificada si la opción **Asignar a oleadas abiertas** está configurada en *Sí*.

#### <a name="manually-specify-what-to-include-in-a-wave"></a>Especifique manualmente qué incluir en una oleada

Cuando se ha creado una oleada pero aún no se ha publicado, puede especificar manualmente qué incluir en ella. Para agregar líneas a una oleada manualmente:

1. En función del tipo de oleada al que desee agregar líneas, use uno de estos métodos:

    - Vaya a **Gestión de almacenes** \> **Común** \> **Oleadas** \> **Oleadas de envío** \> **Todas las oleadas**. En el panel Acciones, seleccione **Oleada**.
    - Vaya a **Gestión de almacenes** \> **Común** \> **Oleadas** \> **Oleadas de producción** \> **Todas las oleadas de producción**. En el panel Acciones, seleccione **Oleada de producción**.
    - Vaya a **Gestión de almacenes** \> **Común** \> **Oleadas** \> **Oleadas kanban** \> **Todas las oleadas kanban**. En el panel Acciones, seleccione **Crear oleada**.

1. Seleccione la oleada. En el panel de acciones, seleccione una de las opciones siguientes:

      - **Mantener envíos**
      - **Mantener producciones**
      - **Mantener listas de selección de trabajos kanban**

1. En la parte superior de la ventana, seleccione la línea que desee agregar a la oleada y, a continuación, seleccione **Agregar a oleada**. La línea se mueve a la ficha desplegable **Líneas de oleada**.

    Repita este paso para cada línea que desee agregar. Para agregar todas las líneas, seleccione **Agregar todo**.

    > [!TIP]
    > Para las oleadas de envío, puede encontrar rápidamente un pedido determinado seleccionando un filtro personalizado en el campo **Filtrar oleada por código**. Los códigos de filtro de la oleada contienen criterios de consulta para los envíos, que se crean en el formulario **Filtros de oleada**. Este campo no está disponible para las oleadas de producción ni de kanban.
    > Una marca de verificación verde en la columna **En oleada** indica que el envío se ha agregado a la oleada.

### <a name="process-the-wave-to-create-the-picking-work"></a>Procesar la oleada para crear el trabajo de picking

Una vez que se ha creado una oleada y contiene todas sus líneas requeridas, está listo para procesarla para crear el trabajo de picking correspondiente.

#### <a name="automatically-process-a-wave"></a>Procesar automáticamente una oleada

Para procesar automáticamente una oleada, configure [Plantillas de oleada](wave-templates.md) con las opciones de procesamiento automático requeridas.

#### <a name="manually-process-a-wave"></a>Procesar manualmente una oleada

Solo puede procesar una oleada cuando el **Estado de oleada** es *Creada*. Después de procesar una oleada, el **Estado de la oleada** será cambiado a *Retenida*.

Para procesar manualmente una oleada que tiene todo su contenido requerido, siga estos pasos:

1. En función del tipo de oleada que desee procesar, haga una de las siguientes cosas:

    - Seleccione **Gestión de almacenes** \> **Común** \> **Oleadas** \> **Oleadas de envío** \> **Todas las oleadas**. En el panel Acciones, seleccione **Oleada**.
    - Seleccione **Gestión de almacenes** \> **Común** \> **Oleadas** \> **Oleadas de producción** \> **Todas las oleadas de producción**. En el panel Acciones, seleccione **Oleada de producción**.
    - Seleccione **Gestión de almacenes** \> **Común** \> **Oleadas** \> **Oleadas kanban** \> **Todas las oleadas kanban**. En el panel Acciones, seleccione **Crear oleada**.

1. Seleccione la oleada que desee procesar. En el panel de acciones, seleccione **Proceso**.

### <a name="release-the-wave-to-the-warehouse-to-start-picking-and-packing"></a>Liberar la oleada en el almacén para iniciar el picking y el embalaje

Para poder liberar una ola antes debe procesarla. Al liberar la oleada, el trabajo que picking se encuentra disponible en el almacén. Puede cancelar una oleada una vez liberada y agregar más líneas, pero no puede modificar las líneas.

#### <a name="automatically-release-a-wave"></a>Liberar automáticamente una oleada

Para procesar automáticamente una oleada, configure [Plantillas de oleada](wave-templates.md) con las opciones de procesamiento automático requeridas.

#### <a name="manually-release-a-wave"></a>Liberar manualmente una oleada

Para liberar una oleada manualmente, siga estos pasos:

1. En función del tipo de oleada que desee liberar, haga una de las siguientes cosas:

      - Seleccione **Gestión de almacenes** \> **Común** \> **Oleadas** \> **Oleadas de envío** \> **Todas las oleadas**. En el panel Acciones, seleccione **Oleada**.
      - Seleccione **Gestión de almacenes** \> **Común** \> **Oleadas** \> **Oleadas de producción** \> **Todas las oleadas de producción**. En el panel Acciones, seleccione **Oleada de producción**.
      - Seleccione **Gestión de almacenes** \> **Común** \> **Oleadas** \> **Oleadas kanban** \> **Todas las oleadas kanban**. En el panel Acciones, seleccione **Crear oleada**.

1. Seleccione la oleada que desee liberar. En el panel Acciones, seleccione **Liberar oleada**.

## <a name="containerize-a-wave"></a>Containerizar una oleada

La creación de contenedores automatizada crea contenedores y el trabajo de picking para los envíos cuando se procesa una oleada. Para obtener detalles sobre cómo configurarlo, consulte [Creación de contenedores](wave-containerization.md).

## <a name="work-with-the-scheduled-work-creation"></a>Trabajar con la creación de trabajo programada

Cuando la función *Programar creación de trabajo* está habilitada, el procesamiento de oleadas creará el trabajo planificado, que al final será utilizado por el proceso de creación de un nuevo trabajo. Durante la creación del trabajo, este se bloqueará mediante la característica *Bloqueo de trabajo en toda la organización*. Para más información, consulte [Programar la creación del trabajo durante la oleada](configure-wave-schedule-work-creation.md).

El siguiente diagrama de flujo muestra cómo se crea el trabajo planificado durante el procesamiento de oleadas.

![Programar la creación del trabajo.](media/schedule-work-creation-process.png)

### <a name="planned-work"></a>Trabajo planificado

La página **Detalles del trabajo planificado** (**Gestión de almacenes \> Trabajo \> Detalles del trabajo planificado**) muestra información sobre el trabajo planificado, que se crea inicialmente durante el procesamiento de oleadas. Están disponibles los siguientes valores de **Estado de progreso**:

- **Puesto en cola**: El trabajo planificado está a la espera de ser utilizada para crear trabajo.
- **Completado**: el trabajo planificado se ha utilizado para crear trabajo.
- **Error**: el procesamiento de la oleada ha fallado. Tenga en cuenta que el trabajo planificado puede estar en estado de **Error** con o sin trabajo real relacionado. Cuando falla el proceso de creación del trabajo real, el trabajo real permanece en estado *Cancelado*.

### <a name="batch-job-for-the-work-creation-process"></a>Trabajo por lotes para el proceso de creación de trabajo

Para ver los trabajos por lotes para procesar oleadas, seleccione **Trabajos por lotes** en el panel de Acción en la página **Todas las oleadas**.

Desde aquí, puede ver todos los detalles de la tarea por lotes para cada uno de los Id. de trabajo por lotes.

## <a name="cancel-a-wave"></a>Cancelar una oleada

Si es necesario, puede cancelar una oleada que ya se ha procesado. Para cancelar una oleada y el trabajo de picking que se ha creado, siga estos pasos:

1. En función del tipo de oleada que desee cancelar, haga una de las siguientes cosas:

      - Vaya a **Gestión de almacenes** \> **Común** \> **Oleadas** \> **Oleadas de envío** \> **Todas las oleadas**.
      - Vaya a **Gestión de almacenes** \> **Común** \> **Oleadas** \> **Oleadas de producción** \> **Todas las oleadas de producción**.
      - Vaya a **Gestión de almacenes** \> **Común** \> **Oleadas** \> **Oleadas kanban** \> **Todas las oleadas kanban**.

1. Seleccione la oleada que desea cancelar. En el panel de acciones, en la pestaña **Trabajo**, seleccione **Cancelar**.

## <a name="review-wave-batch-job-details"></a>Revisar los detalles del trabajo por lotes de oleadas

Use la página **Detalles del trabajo por lotes de oleada** para inspeccionar los trabajos por lotes y las tareas relacionadas asociadas con cualquier oleada. Esto es especialmente útil para solucionar problemas de una oleada que ha fallado. Sin esta función, solo los administradores suelen tener acceso a los detalles del trabajo por lotes. La página **Detalles del trabajo por lotes de oleada** puede estar disponible para usuarios que no son administradores y proporciona una vista de solo lectura de los trabajos por lotes y las tareas relacionadas.

### <a name="enable-the-wave-batch-job-details-page"></a>Habilite la página de detalles del trabajo por lotes de oleada

Si su sistema aún no incluye la página **Detalles del trabajo por lotes de oleada**, vaya a [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y active la función *Detalles del trabajo por lotes de oleada*.

### <a name="use-the-wave-batch-job-details-page"></a>Use la página de detalles del trabajo por lotes de oleada

La página **Detalles del trabajo por lotes de oleada** combina trabajos por lotes y tareas de trabajo por lotes, lo que le permite investigar todos los pasos de la oleada sin necesidad de navegar entre un solo trabajo por lotes y la lista de tareas por lotes. La página también proporciona acceso al registro de lotes y, si tiene los permisos necesarios, proporciona un enlace a la página **Trabajos por lotes**.

Para abrir esta página, seleccione una oleada en cualquiera de las distintas páginas de oleadas y luego seleccione **Detalles del trabajo por lotes de oleada** desde el Panel de acciones.

## <a name="review-load-validation-and-error-messages"></a>Revisar la validación de carga y mensajes de error

Durante el procesamiento de la oleada, el sistema valida y muestra el estado de cada línea de carga en la oleada. Si no se producen advertencias, continúa con el siguiente paso de la oleada. Si se producen advertencias, en su lugar muestra el siguiente error una vez que ha terminado de validar toda la oleada:

> Se encontraron líneas de carga no válidas en la oleada. Elimine las líneas de carga no válidas.

Luego, puede revisar el estado final de cada línea de carga en la oleada y corregir todas las advertencias antes de volver a intentarlo. Esto le permite abordar todas las advertencias a la vez antes de reprocesar la oleada. (En versiones anteriores, el sistema dejaba de procesar la oleada después de la primera advertencia, por lo que solo podía corregir las advertencias una a la vez).

La forma en que el sistema muestra los mensajes de estado de procesamiento de oleadas depende de cómo haya configurado la opción **Crear un registro del historial de procesamiento de oleadas** en la página **Parámetros de gestión de almacén**.

- Cuándo **Crear un registro del historial de procesamiento de oleadas** se establece en *No*, los mensajes de estado de la línea de carga se muestran en el **Registro de información**.
- Cuándo **Crear un registro del historial de procesamiento de oleadas** se establece en *Sí*, los mensajes de estado de la línea de carga se muestran en la página **Registro de información de procesado de oleada**. Para ver el registro, vaya a **Gestión de almacenes \> Oleadas salientes \> Registro de historial de procesamiento de oleadas**.

## <a name="additional-resources"></a>Recursos adicionales

- [Ejemplo de configuración de procesamiento de oleadas](tasks/configure-wave-processing.md)
- [Plantillas de oleada](wave-templates.md)
- [Creación de contenedores](wave-containerization.md)