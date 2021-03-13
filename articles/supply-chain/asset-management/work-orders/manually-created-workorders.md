---
title: Órdenes de trabajo creadas manualmente
description: En este tema se explica cómo crear órdenes de trabajo manualmente en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderTableCreateRelated, EntAssetWorkOrderTableCreate, EntAssetWorkOrderTableCopy
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 8c787dbc9889139df76b9b102deb18fce567e382
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/16/2021
ms.locfileid: "5017877"
---
# <a name="manually-created-work-orders"></a>Órdenes de trabajo creadas manualmente

[!include [banner](../../includes/banner.md)]


Puede crear órdenes de trabajo de manera manual de dos formas:

- En **Todas las órdenes de trabajo** o la página **Órdenes de trabajo activas** 
- En **Todas las solicitudes de mantenimiento** o **Solicitudes de mantenimiento activas** o **Mis solicitudes de mantenimiento de la ubicación técnica**. 

## <a name="create-work-order"></a>Crear orden de trabajo

1. Seleccione **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

2. Seleccione **Nuevo**.

3. En el cuadro de diálogo **Crear orden de trabajo**, seleccione un tipo de orden del trabajo en el campo **Tipo de orden de trabajo**.

4. Si es necesario, seleccione una **Descripción**.

5. Seleccione el activo en el campo **Activo**.

>[!NOTE]
>Al seleccionar un activo, tres fichas pueden estar disponibles en el menú desplegable **Activo**: 

- **Activos activos**: esta ficha contiene una lista de todos los activos cuyo estado de ciclo de vida es "Activo". 
- **Vista de activos**: esta ficha muestra una vista de árbol de las ubicaciones técnicas y los activos instalados en ellas.
- **Mis activos**: esta ficha contiene los activos que están relacionados con las ubicaciones técnicas y que se le pueden asignar (al trabajador que ha iniciado sesión en el sistema). (Para obtener información sobre la configuración, consulte [Trabajadores de mantenimiento y grupos de trabajadores](../setup-for-objects/workers-and-worker-groups.md).) Si no se ha configurado ninguna ubicación técnica de un trabajador en [Trabajadores de mantenimiento y grupos de trabajadores](../setup-for-objects/workers-and-worker-groups.md), la ficha **Mis activos** no está disponible. 

6. Seleccione el tipo de trabajo de mantenimiento para la orden de trabajo en el campo **Tipo de trabajo de mantenimiento**.

7. Si es necesario, seleccione **Variante de tipo de trabajo de mantenimiento** y **Comercio**.

8. Si es necesario, puede cambiar el nivel de servicio de la orden de trabajo en el campo **Nivel de servicio**.

9. Seleccione las fechas **Inicio previsto** y **Final previsto** en los campos relacionados.

10. Haga clic en **Aceptar** para crear la orden de trabajo.

11. En la página de lista **Todas las órdenes de trabajo**, puede editar las órdenes de trabajo como sea necesario.

Tenga en cuenta los aspectos siguientes:

- En la vista de detalles de la página de lista **Todas las órdenes de trabajo**, puede agregar varios activos a una orden de trabajo agregando líneas en la ficha desplegable **Trabajos de mantenimiento de órdenes de trabajo**. En el activo, solo puede seleccionar los tipos de trabajo de mantenimiento que se definen en el tipo de activo seleccionando para el activo.  

- Si modifica el nivel de servicio de activos o una importancia de activo después de utilizar el activo en una orden de trabajo, el nivel de servicio o la importancia de la orden de trabajo no se actualiza como corresponde. Para obtener más información sobre los niveles de servicio y las importancias, consulte [Niveles del servicio de activos](../setup-for-objects/object-priorities.md) e [Tipos de importancia de activos](../setup-for-objects/object-criticalities.md).

- La importancia de una orden de trabajo se actualiza cada vez que se agrega o se elimina un trabajo de una orden de trabajo.

- En la vista de detalles **Todas las órdenes de trabajo** > ficha **Encabezado** > ficha desplegable **Programar**, puede seleccionar un trabajador o grupo de trabajadores responsable del mantenimiento en los campos **Grupo responsable** o **Responsable**. Estos valores se pueden cambiar mientras que la orden de trabajo está activa. Por ejemplo, se pueden cambiar cuando cambia el estado del ciclo de vida de la orden de trabajo. La selección automática realizada durante la creación de la orden de trabajo se basa en la configuración en la página **Trabajadores responsables del mantenimiento**. Si agrega o elimina tareas de una orden de trabajo después de haber creado una orden de trabajo, y los campos **Grupo responsable** y **Responsable** están en blanco cuando actualiza la orden de trabajo, la Administración de activos intenta buscar una posible coincidencia en la página de configuración para un trabajador o grupo de trabajadores responsable del mantenimiento. Si los campos **Grupo responsable** o **Responsable** ya están definidos cuando actualice la orden de trabajo, no se realiza ningún cambio. Para obtener más información sobre los trabajadores y grupos de trabajadores de mantenimiento responsables, consulte [Trabajadores de mantenimiento responsables](../setup-for-maintenance-requests/responsible-workers.md).

- En la página [Estado del mantenimiento](../controlling-and-reporting/maintenance-status.md), puede hacer un cálculo para obtener una visión general de la carga de trabajo relativa a las órdenes de trabajo entrantes y completadas.  

- En la vista detalles de la página **Todas las órdenes de trabajo**, en la ficha desplegable **Detalles de línea**, puede utilizar los campos **Latitud** y **Longitud** para agregar las coordenadas geográficas para el activo que se selecciona en la tarea de la orden de trabajo.  


## <a name="create-related-work-order"></a>Crear orden de trabajo relacionada

Puede crear una orden de trabajo relacionada con una orden de trabajo existente. Esta capacidad resulta útil, por ejemplo, si se desea trabajar con órdenes de trabajo principales y secundarios. Una nueva orden de trabajo se basa en una tarea de la orden de trabajo a partir de una orden de trabajo existente.

1. Seleccione **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

2. Seleccione la orden de trabajo para crear una orden de trabajo relacionada.

3. En el panel de acciones, en la ficha **Orden de trabajo**, en el grupo **Nuevo**, seleccione **Orden de trabajo relacionada**.

4. En el cuadro de diálogo desplegable **Crear orden de trabajo relacionada**, seleccione la orden de trabajo para la que desea crear una orden de trabajo relacionada en el campo **Tarea de orden de trabajo**.

5. En el campo **Tipo de trabajo de mantenimiento**, seleccione el tipo de trabajo de mantenimiento.

6. En los campos **Variante del tipo de trabajo de mantenimiento** y **Comercio**, seleccione la variante y el comercio relacionados con el tipo de trabajo de mantenimiento que sean necesarios.

7. Si esta orden de trabajo es la primera orden de trabajo relacionada que se ha creado para la orden de trabajo seleccionada, siga estos pasos:
    1. Seleccione la opción **Nueva orden de trabajo**.
    2. En el campo **Tipo de orden de trabajo**, seleccione un tipo de orden de trabajo.
    3. En **Descripción**, escriba una descripción.
    4. Si es necesario, cambie el nivel de servicio de la orden de trabajo en el campo **Nivel de servicio**.
    5. En los campos **Inicio previsto** y **Final previsto**, seleccione las fechas inicial y final previstas.
    6. Seleccione **Aceptar**. La nueva orden de trabajo relacionada se muestra en la página de lista **Todas las órdenes de trabajo**.  

8. Si la orden de trabajo para la que está creando esta orden de trabajo relacionada ya tiene órdenes de trabajo relacionadas, siga estos pasos para agregar una nueva tarea de orden de trabajo a una orden de trabajo relacionada existente:
    1. Seleccione la opción **Agregar a orden de trabajo relacionada**.
    2. A continuación, en el campo **Orden de trabajo** seleccione la orden de trabajo relacionada a la que desea agregar una nueva tarea de orden de trabajo.
    3. Si es necesario, cambie el nivel de servicio de la orden de trabajo en el campo **Nivel de servicio**.
    4. En los campos **Inicio previsto** y **Final previsto**, cambie las fechas inicial y final previstas en la medida en que sea necesario.
    5. Seleccione **Aceptar**. La orden de trabajo se agrega a la orden de trabajo relacionada que ya existe.

La ilustración muestra un ejemplo del cuadro de diálogo **Crear orden de trabajo relacionada**.

![Figura 1](media/03-work-orders.png)

>[!NOTE]
>Si ha configurado una máscara de orden de trabajo relacionada en la ficha **Parámetros de administración de activos** > **Órdenes de trabajo** > campo **Máscara de orden de trabajo relacionada**, los id. de orden de trabajo se crearán de acuerdo con la configuración de la máscara. Si no se ha configurado ninguna máscara de orden de trabajo relacionada, se utiliza el siguiente id. de orden de trabajo disponible para las órdenes de trabajo relacionadas.

## <a name="copy-a-work-order"></a>Copiar una orden de trabajo

Puede crear rápidamente una nueva orden de trabajo a partir de una orden de trabajo existente. Esta forma de trabajar con órdenes de trabajo es diferente a la de crear órdenes de trabajo basadas en [planes de mantenimiento](../preventive-and-reactive-maintenance/maintenance-plans.md). Resulta útil si, por ejemplo, tiene una orden de trabajo que contiene muchas tareas con distintas tareas en diferentes activos que se deben completar a intervalos periódicos.

1. Seleccione **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

2. Seleccione la orden de trabajo desde la que desea copiar el contenido.

3. En el panel de acciones, en la ficha **Orden de trabajo**, en el grupo **Nuevo**, seleccione **Copiar orden de trabajo**.

4. Se muestra la configuración de la orden de trabajo desde la orden de trabajo seleccionada. Si es necesario, puede editar algunos campos.

5. Seleccione **Aceptar** para crear la nueva orden de trabajo.

6. En la página de lista **Todas las órdenes de trabajo**, puede editar las órdenes de trabajo como sea necesario.

>[!NOTE]
>Cuando se crea la nueva orden de trabajo, alguna información se copia directamente desde la orden de trabajo existente. La información sobre las previsiones, herramientas, listas de comprobación de mantenimiento, la ubicación funcional, direcciones, y la programación no se copia. En su lugar, se inicializa de la configuración actual en Administración de activos. Por lo tanto, si la información se cambió entre el momento en que se creó la primera orden de trabajo y el momento en que hizo una copia de la orden de trabajo, los cambios se incluyen en la nueva orden de trabajo. Algunos ejemplos son los cambios en las previsiones y las actualizaciones de las listas de comprobación de mantenimiento.

La ilustración siguiente muestra un ejemplo del diálogo **Copiar orden de trabajo**.

![Figura 2](media/04-work-orders.png)


## <a name="create-a-work-order-based-on-a-maintenance-request"></a>Crear una orden de trabajo basada en una solicitud de mantenimiento

1. Seleccione **Administración de activos** > **Común** > **Solicitudes de mantenimiento** > **Todas las solicitudes de mantenimiento** o **Solicitudes de mantenimiento activas**.

2. Seleccione las solicitudes de mantenimiento para las que desea crear una orden de trabajo y haga clic en **Editar**.

3. En el panel de acciones, en la ficha **Solicitud de mantenimiento**, en el grupo **Nuevo**, seleccione **Orden de trabajo**.

4. En el cuadro de diálogo **Orden de trabajo**, establezca los campos. Si se ha seleccionado un tipo de trabajo de mantenimiento en la solicitud de mantenimiento, puede seleccionar otro tipo de trabajo de mantenimiento, si es necesario, al crear la orden de trabajo.

5. Seleccione **Aceptar**. Un mensaje informa de que se ha creado la orden de trabajo.

6. Para ver las órdenes de trabajo que están conectadas a una solicitud de mantenimiento, seleccione la solicitud de mantenimiento en la página de lista **Todas las solicitudes de mantenimiento** o **Solicitudes de mantenimiento activas**. A continuación, en el panel de acciones, en la ficha **Solicitud de mantenimiento**, en el grupo **Vista**, seleccione **Órdenes de trabajo**.


La ilustración siguiente muestra un ejemplo del diálogo **Crear orden de trabajo**.

![Figura 3](media/05-work-orders.png)


>[!NOTE]
>Si desea que las órdenes de trabajo se creen automáticamente, puede programar tareas del plan de mantenimiento, o bien configurar "Crear automáticamente" [planes de mantenimiento](../preventive-and-reactive-maintenance/maintenance-plans.md) o [rondas de mantenimiento](../preventive-and-reactive-maintenance/maintenance-rounds.md) en un activo. Las órdenes de trabajo creadas a partir de solicitudes de mantenimiento en la página de lista **Todo el programa de mantenimiento** tienen tipos de trabajo de mantenimiento seleccionados en las solicitudes de mantenimiento.

