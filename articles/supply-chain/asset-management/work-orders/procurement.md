---
title: Adquisición
description: Este tema explica el proceso de adquisición en Administración de activos.
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
ms.openlocfilehash: 1678dbe2432e4be46aebb40a12e73dfd695c3e77
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875880"
---
# <a name="procurement"></a>Adquisición


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

En Administración de activos, puede obtener una visión general de las solicitudes de compra y los pedidos de compra relacionados con órdenes de trabajo. También es posible crear un pedido de compra o una solicitud de compra a partir de una orden de trabajo.

En la lista **Solicitud de compra de orden de trabajo** (**Administración de activos** > **Común** > **Adquisición** > **Solicitud de compra de orden de trabajo**), verá una lista de solicitudes de compra relacionadas con órdenes de trabajo.

- Seleccione una tarea de una orden de trabajo en la lista **Solicitud de compra de orden de trabajo** y haga clic en el botón **Solicitud de compra** para abrir la solicitud de compra relacionada.  
- Seleccione una tarea de una orden de trabajo en la lista **Solicitud de compra de orden de trabajo** y haga clic en el botón **Orden de trabajo** para abrir la orden de trabajo relacionada.  
- Seleccione una tarea de una orden de trabajo en la lista **Solicitud de compra de orden de trabajo** y haga clic en el botón **Dónde se usa el artículo** si desea obtener una visión general de dónde se usa el artículo en la línea seleccionada en Administración de activos en relación con los activos, los valores predeterminados del tipo de trabajo de mantenimiento, los recambios y las órdenes de trabajo. 

![Figura 1](media/08-work-orders.png)


En la lista **Solicitud de compra de orden de trabajo** (**Administración de activos de la empresa** > **Común** > **Adquisición** > **Compra de orden de trabajo**), puede ver una lista de pedidos de compra relacionadas con órdenes de trabajo.

- Seleccione una tarea de una orden de trabajo en la lista **Compra de orden de trabajo** y haga clic en el botón **Pedido de compra** para abrir el pedido de compra relacionado.  
- Seleccione una tarea de una orden de trabajo en la lista **Solicitud de compra de orden de trabajo** y haga clic en el botón **Orden de trabajo** para abrir la orden de trabajo relacionada.  
- Seleccione una tarea de la orden de trabajo en la lista de compra **Orden de trabajo** y haga clic en el botón **Dónde se usa el artículo** si desea obtener una visión general de dónde se usa el artículo en la línea seleccionada en Administración de activos en relación con los activos, los valores predeterminados del tipo de trabajo de mantenimiento, los recambios y las órdenes de trabajo. 

![Figura 2](media/09-work-orders.png)


En las listas que se muestra anteriormente, a la derecha de cada línea se coloca un icono relativo al control de fecha de entrega. Si el icono muestra un signo de exclamación en un círculo rojo, significa que se puede retrasar la entrega en la solicitud de compra o el pedido de compra relacionado.

En una solicitud de compra, la fecha usada para calcular el posible retraso se encuentra en el formulario **Solicitudes de compra** > ficha desplegable **Encabezado de solicitud de compra** > campo **Fecha solicitada**. Esa fecha se compara con la fecha disponible en la orden de trabajo o la tarea de orden de trabajo de la misma manera que la fecha del pedido de compra.

En un pedido de compra, la fecha que se usa para calcular un posible retraso es la fecha relacionada con la línea del pedido de compra, que se muestra en el formulario **Pedido de compra** > seleccione la línea del pedido de compra > ficha desplegable **Detalles de línea** > pestaña **Configuración** > campo **Fecha de entrega confirmada**. Si ese campo no se rellena, se utiliza la fecha en el campo **Fecha de entrega** en la ficha desplegable **Encabezado del pedido de compra**. Una de esas fechas se compara con la fecha disponible en la orden de trabajo o la tarea de orden de trabajo en el orden siguiente:

- Fecha de inicio real en la orden de trabajo, o  

- Fecha de inicio programada en la tarea de orden de trabajo relacionada, o  

- Fecha de inicio programada en la orden de trabajo, o  

- Fecha de inicio prevista en la orden de trabajo  


## <a name="create-purchase-order-from-a-work-order"></a>Crear pedido de compra desde una orden de trabajo

En **Todas las órdenes de trabajo**, seleccione una tarea de la orden de trabajo y cree un pedido de compra o una solicitud de compra relacionada. Esto se hace para garantizar las relaciones de proyectos entre el pedido de compra o la solicitud de compra y la orden de trabajo.

1. Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

2. En la lista **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**, seleccione la orden de trabajo para la que desea crear un pedido de compra y haga clic en **Editar**.

3. En el formulario **Orden de trabajo** > ficha desplegable **Trabajos de mantenimiento de orden de trabajo**, seleccione la tarea de la orden de trabajo para la que desea crear el pedido de compra.

4. Haga clic en **Tareas del artículo** > **Pedido de compra de la tarea de la orden de trabajo**.

5. En la página de lista **Pedidos de compra del proyecto**, haga clic en **Nuevo**.

6. Cree el pedido de compra.

>[!NOTE]
>La creación de una solicitud de compra es casi idéntica a la creación de un pedido de compra. La única diferencia es que en el proceso anterior, hace clic en **Tareas del artículo** > **Solicitud de compra de la tarea de la orden de trabajo** en el paso 2.

## <a name="project-relation-between-work-order-and-purchase-order-or-purchase-requisition"></a>Relación de proyectos entre orden de trabajo y pedido de compra o solicitud de compra

Una línea de pedido de compra o de solicitud de compra se relaciona con una tarea de orden de trabajo a través del proyecto de la orden de trabajo y el número de la actividad del proyecto relacionado. Cuando cree un pedido de compra o una solicitud de compra desde una tarea de orden de trabajo, el número de la actividad del proyecto relacionado es obligatorio. El número de la actividad del proyecto se inserta automáticamente en un pedido de compra o una solicitud de compra si la orden de trabajo relacionada contiene tareas de la orden de trabajo que utilizan todas el mismo tipo de trabajo de mantenimiento. Si las tareas de la orden de trabajo contienen distintos tipos de trabajo de mantenimiento, el número de la actividad del proyecto se debe insertar manualmente.

Para ver o insertar el número de la actividad relacionada con una línea de pedido de compra, abra **Compra de orden de trabajo** > seleccione el registro del pedido de compra > haga clic en el pedido de compra en la columna **Pedido de compra** > ficha desplegable **Detalles de línea** > pestaña **Proyecto** > campo **Número de actividad**.


![Figura 3](media/10-work-orders.png)


Del mismo modo, para ver o insertar el número de la actividad relacionada con una línea de solicitud de compra de una orden de trabajo, abra **Solicitud de compra de orden de trabajo** > seleccione el registro de la solicitud de compra > haga clic en la solicitud de compra en la columna **Solicitud de compra** > ficha desplegable **Detalles de línea** > pestaña **Proyecto** > campo **Número de actividad**.

