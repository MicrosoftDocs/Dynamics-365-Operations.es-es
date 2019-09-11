---
title: Órdenes de trabajo creadas manualmente
description: En este tema se explica cómo crear órdenes de trabajo manualmente en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-15
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 261448a134a7c1aacfbb4ea6f954ce03a63c23e2
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875881"
---
# <a name="manually-created-work-orders"></a>Órdenes de trabajo creadas manualmente

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Puede crear órdenes de trabajo de manera manual de dos formas:

- en **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**  
- en **Todas las solicitudes de mantenimiento** o **Solicitudes de mantenimiento activas** o **Mis solicitudes de mantenimiento de la ubicación técnica**.  

## <a name="create-work-order"></a>Crear orden de trabajo

1. Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

2. Haga clic en el botón **Nuevo**.

3. En el desplegable **Crear orden de trabajo**, seleccione un tipo de orden de trabajo.

4. Si es necesario, seleccione una descripción.

5. Seleccione el activo para la orden de trabajo junto con un tipo de trabajo de mantenimiento.

>[!NOTE]
>Al seleccionar un activo, puede que estén disponibles tres pestañas: la pestaña **Mis activos** contiene los activos relacionados con las ubicaciones técnicas a las que usted (el trabajador conectado al sistema) puede ser asignado (se configura en [Trabajadores y grupos de trabajadores de mantenimiento](../setup-for-objects/workers-and-worker-groups.md)). Si no se ha configurado ninguna ubicación técnica para un trabajador en [Trabajadores y grupos de trabajadores de mantenimiento](../setup-for-objects/workers-and-worker-groups.md), la pestaña **Mis activos** no estará visible. La pestaña **Activos activos** contiene una lista de todos los activos cuyo estado de ciclo de vida es "Activo". La pestaña **Vista de activos** muestra una vista de árbol de las ubicaciones técnicas y los activos instalados en esas ubicaciones.

6. Si es necesario, seleccione **Variante de tipo de trabajo de mantenimiento** y **Comercio**.

7. Si es necesario, puede cambiar el nivel de servicio de la orden de trabajo en el campo **Nivel de servicio**.

8. Seleccione las fechas iniciales y finales previstas en los campos relacionados.

9. Haga clic en **Aceptar** para crear una nueva orden de trabajo.

10. Si es necesario, edite la orden de trabajo en **Todas las órdenes de trabajo**.

- En **Todas las órdenes de trabajo**, puede agregar varios activos a una orden de trabajo en la vista de detalles agregando líneas en la ficha desplegable **Trabajos de mantenimiento de órdenes de trabajo**. En el activo, solo puede seleccionar los tipos de trabajo de mantenimiento que se definen en el tipo de activo seleccionando para el activo.  
- Si ha cambiado el nivel de servicio o la importancia de un activo después de que lo haya utilizado en una orden de trabajo (consulte [Niveles de servicio de activos](../setup-for-objects/object-priorities.md) e [Importancias de activos](../setup-for-objects/object-criticalities.md)), el nivel de servicio o la importancia en la orden de trabajo no se actualiza.
- La importancia de una orden de trabajo se vuelve a calcular cada vez que se agrega o se elimina una línea de la orden de trabajo.
- En la vista de detalles **Todas las órdenes de trabajo** > vista **Encabezado** > ficha desplegable **Programar**, puede seleccionar un trabajador o grupo de trabajadores responsable del mantenimiento en los campos **Grupo responsable** o **Responsable**. Esta configuración se puede cambiar siempre que la orden de trabajo esté activa, por ejemplo, cuando cambia el estado del ciclo de vida de la orden de trabajo. La selección automática realizada durante la creación de la orden de trabajo se basa en la configuración en **Trabajadores responsables del mantenimiento**. Si agrega o elimina tareas de una orden de trabajo después de haber creado una orden de trabajo, y los campos **Grupo responsable** y **Responsable** están en blanco cuando actualiza la orden de trabajo, la Administración de activos busca una posible coincidencia en el formulario de configuración para un trabajador o grupo de trabajadores responsable del mantenimiento. Si los campos **Grupo responsable** o **Responsable** ya están rellenados cuando actualice la orden de trabajo, no se realiza ningún cambio. 

- En **Estado del mantenimiento**, puede hacer un cálculo para obtener una visión general de la carga de trabajo relativa a las órdenes de trabajo entrantes y completadas.  

- En la ficha desplegable **Detalles de línea**, utilice los campos **Latitud** y **Longitud** para agregar coordenadas geográficas para el activo seleccionado en la tarea de la orden de trabajo.  

## <a name="create-related-work-order"></a>Crear orden de trabajo relacionada

Puede crear una orden de trabajo relacionada con una orden de trabajo existente si, por ejemplo, desea trabajar con órdenes de trabajo principales y secundarias. Una nueva orden de trabajo se basa en una tarea de la orden de trabajo a partir de una orden de trabajo existente.

1. Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

2. Seleccione la orden de trabajo para la que desea crear una orden de trabajo relacionada.

3. Haga clic en **Orden de trabajo relacionada**.

4. En el cuadro de diálogo desplegable **Crear orden de trabajo relacionada**, seleccione la orden de trabajo para la que desea crear una orden de trabajo relacionada en el campo **Tarea de orden de trabajo**.

5. Seleccione un tipo de trabajo de mantenimiento en el campo **Tipo de trabajo de mantenimiento** y, si es necesario, una variante de tipo de trabajo de mantenimiento relacionada y un comercio en los campos **Variante de tipo de trabajo de mantenimiento** y **Comercio**.

6. Si se trata de la primera orden de trabajo relacionada que crea, haga clic en el botón de opción **Nueva orden de trabajado**.

7. Seleccione una **Tipo de orden de trabajo** y una **Descripción** en los campos relacionados.

8. Si es necesario, cambie el nivel de servicio de la orden de trabajo en el campo **Nivel de servicio**.

9. Inserte las fechas iniciales y finales previstas en los campos relacionados.

10. Haga clic en **Aceptar**. La nueva orden de trabajo relacionada se muestra en la lista **Todas las órdenes de trabajo**.

11. Si crea una orden de trabajo relacionada en una orden de trabajo que ya tiene órdenes de trabajo relacionadas, puede agregar una tarea de orden de trabajo a una orden de trabajo ya relacionada. Para ello, haga clic en el botón de opción **Agregar a orden de trabajo relacionada** en el paso 6. A continuación, seleccione la orden de trabajo relacionada a la que desea agregar una nueva tarea de orden de trabajo. Edite los campos **Nivel de servicio**, **Inicio previsto** y **Finalización prevista**, según sea necesario, y haga clic en **Aceptar**. La orden de trabajo se agrega a la orden de trabajo relacionada que ya existe.


![Figura 1](media/03-work-orders.png)

**Nota**: si ha configurado una máscara de orden de trabajo relacionada en el vínculo **Parámetros de administración de activos** > **Órdenes de trabajo** > campo **Máscara de orden de trabajo relacionada**, los id. de orden de trabajo se crearán de acuerdo con la configuración de la máscara. Si no se ha configurado ninguna máscara de orden de trabajo relacionada, se utilizará el siguiente id. de orden de trabajo disponible para las órdenes de trabajo relacionadas.

## <a name="copy-work-order"></a>Copiar orden de trabajo

Es posible crear rápidamente una nueva orden de trabajo a partir de una orden de trabajo existente. Esta forma de trabajar con órdenes de trabajo es diferente a la de crear órdenes de trabajo basadas en planes de mantenimiento. Resulta útil si, por ejemplo, tiene una orden de trabajo que contiene muchas tareas con distintas tareas en diferentes activos que se deben completar a intervalos periódicos.

1. Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

2. Seleccione la orden de trabajo desde la que desea copiar el contenido.

3. Haga clic en **Copiar orden de trabajo**. Se muestra la configuración de la orden de trabajo desde la orden de trabajo seleccionada. Si es necesario, puede editar algunos campos.

4. Haga clic en **Aceptar** para crear la nueva orden de trabajo.

5. Si es necesario, edite la orden de trabajo en **Todas las órdenes de trabajo**.

>[!NOTE]
>Cuando se crea la nueva orden de trabajo, alguna información se copia directamente desde la orden de trabajo existente. La información acerca de previsiones, herramientas, listas de comprobación de mantenimiento, ubicación técnica, direcciones y programación no se copia, pero se inicializa desde la configuración actual en Administración de activos. Esto significa que si se hicieron cambios en esos datos desde el momento de la creación de la primera orden de trabajo hasta el momento en que hizo una copia de la orden de trabajo, esos cambios se incluyen en la nueva orden de trabajo que ha creado. Los ejemplos son cambios en las previsiones o listas de comprobación de mantenimiento actualizadas.


![Figura 2](media/04-work-orders.png)


## <a name="create-work-order-based-on-a-maintenance-request"></a>Crear una orden de trabajo basada en una solicitud de mantenimiento

1. Haga clic en **Administración de activos** > **Común** > **Solicitudes de mantenimiento** > **Todas las solicitudes de mantenimiento** o **Solicitudes de mantenimiento activas**.

2. Seleccione las solicitudes de mantenimiento para las que desea crear una orden de trabajo y haga clic en **Editar**.

3. En **Todas las solicitudes**, haga clic en **Orden de trabajo**.

4. Rellene el desplegable **Orden de trabajo**. Si se ha seleccionado un tipo de trabajo de mantenimiento en la solicitud de mantenimiento, puede seleccionar otro tipo de trabajo de mantenimiento, si es necesario, al crear la orden de trabajo.

5. Haga clic en **Aceptar**. Verá un mensaje que le informa de que se ha creado la orden de trabajo.

6. Si desea ver las órdenes de trabajo que están conectadas a una solicitud de mantenimiento, seleccione la solicitud de mantenimiento en las listas **Todas las solicitudes de mantenimiento** o **Solicitudes de mantenimiento activa** y haga clic en el botón **Órdenes de trabajo**.


![Figura 3](media/05-work-orders.png)


>[!NOTE]
>Las órdenes de trabajo también se pueden crear automáticamente programando tareas del plan de mantenimiento, o bien configurando "Crear automáticamente" planes de mantenimiento o rondas de mantenimiento en un activo. Las órdenes de trabajo creadas a partir de solicitudes de mantenimiento en **Programa de mantenimiento** se crean con los tipos de trabajo de mantenimiento seleccionados en las solicitudes de mantenimiento.

