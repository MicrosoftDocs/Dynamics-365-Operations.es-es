---
title: Adquisición
description: Este tema explica el proceso de adquisición en Administración de activos.
author: johanhoffmann
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderPurchaseListPagePreviewPane, EntAssetWorkOrderPurchaseListPage, EntAssetWorkOrderPurchaseLineAmountInfoPart, EntAssetWorkOrderPurchReqListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: f3e01dd85cbe8e2b2c9095431f3e0aead817a5a5
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6352771"
---
# <a name="procurement"></a>Adquisición

[!include [banner](../../includes/banner.md)]

En Administración de activos, puede obtener una visión general de las solicitudes de compra y los pedidos de compra relacionados con órdenes de trabajo. También es posible crear un pedido de compra o una solicitud de compra a partir de una orden de trabajo.

En la página de lista **Solicitud de compra de orden de trabajo** (**Administración de activos** > **Común** > **Adquisición** > **Solicitud de compra de orden de trabajo**), se ve una lista de solicitudes de compra relacionadas con órdenes de trabajo. Cuando selecciona un trabajo de orden de trabajo en esta página, puede utilizar los botones del grupo **Mostrar** de la ficha del panel de acciones **Solicitud de compra del pedido de trabajo** para realizar distintas acciones:

- Para abrir la solicitud de compra relacionada, seleccione **solicitud de compra**. 
- Para abrir la orden de trabajo relacionada, seleccione **Orden de trabajo**.
- Para obtener una visión general de dónde se usa el artículo de la línea seleccionada en Administración de activos, en relación con los activos, los valores predeterminados de los tipos de trabajo de mantenimiento, las piezas de repuesto y las órdenes de trabajo en la administración de activos, seleccione **Dónde se usó el artículo**. Para obtener más información sobre esta información general, consulte [Dónde se usó el artículo](../controlling-and-reporting/item-where-used.md).

La ilustración siguiente muestra un ejemplo de la página de lista **Solicitud de compra de orden de trabajo**.

![Figura 1.](media/08-work-orders.png)


En la página de lista **Solicitud de compra de orden de trabajo** (**Administración de activos** > **Común** > **Adquisición** > **Solicitud de compra de orden de trabajo**), se ve una lista de órdenes de compra relacionadas con órdenes de trabajo. Cuando selecciona un trabajo de orden de trabajo en esta página, puede utilizar los botones del grupo **Mostrar** de la ficha del panel de acciones **Compra del pedido de trabajo** para realizar distintas acciones:

- Para abrir la orden de compra relacionada, seleccione **Orden de compra**. 
- Para abrir la orden de trabajo relacionada, seleccione **Orden de trabajo**.
- Para obtener una visión general de dónde se usa el artículo de la línea seleccionada en Administración de activos, en relación con los activos, los valores predeterminados de los tipos de trabajo de mantenimiento, las piezas de repuesto y las órdenes de trabajo en la administración de activos, seleccione **Dónde se usó el artículo**. Para obtener más información sobre esta información general, consulte [Dónde se usó el artículo](../controlling-and-reporting/item-where-used.md).

La ilustración siguiente muestra un ejemplo de la página de lista **Compra de orden de trabajo**.

![Figura 2.](media/09-work-orders.png)


En la página de lista **Compra de orden de trabajo** y la página de lista **Solicitud de compra del pedido de trabajo**, un símbolo relacionado con el control de fecha de entrega aparece a la derecha de cada línea. Si el símbolo muestra un signo de exclamación en un círculo rojo, significa que se puede retrasar la entrega de la solicitud de compra o el pedido de compra relacionado.

Para un pedido de compra, la fecha que está relacionada con la línea de pedido de compra se usa para calcular un retraso posible. Para ver esta fecha, en la página **Pedido de compra**, seleccione la línea de pedido de compra. La fecha se muestra en el campo **Fecha de entrega confirmada** en la pestaña **Configuración** de la ficha desplegable **Detalles de línea**. Si el campo **Fecha de entrega confirmada** no se establece, la fecha del campo **Fecha de entrega** en la ficha desplegable **Encabezado del pedido de compra** se usa para el cálculo. Una de esas fechas se compara con la fecha disponible en la orden de trabajo o la tarea de orden de trabajo en el orden siguiente:

1. Fecha de inicio real en la orden de trabajo  

2. Fecha de inicio programada en la tarea de orden de trabajo relacionada 

3. Fecha de inicio programada en la orden de trabajo 

4. Fecha de inicio prevista en la orden de trabajo 

En una solicitud de compra, la fecha usada en el campo **Fecha solicitada** en la ficha desplegable **Encabezado de solicitud de compra** de la página **Solicitudes de compra** se usa para calcular un posible retraso. La fecha de ese campo se compara con la fecha disponible en la orden de trabajo o la tarea de orden de trabajo en la mismo orden que se usa para una orden de trabajo.


## <a name="create-a-purchase-order-from-a-work-order"></a>Crear un pedido de compra desde una orden de trabajo

En la página de lista **Todas las órdenes de trabajo**, puede seleccionar una tarea de orden de trabajo y luego crear una orden de pedido de compra o una solicitud de compra relacionada. De esta forma, esto ayuda a garantizar que haya relaciones de proyectos entre el pedido de compra o la solicitud de compra y la orden de trabajo.

1. Seleccione **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

2. Seleccione el pedido de trabajo para crear para él una orden de compra y, a continuación, seleccione **Editar**.

3. En la ficha desplegable **Trabajos de mantenimiento de orden de trabajo**, seleccione la tarea de la orden de trabajo para la que desea crear el pedido de compra.

4. Haga clic en **Tareas del artículo** > **Pedido de compra de la tarea de la orden de trabajo**.

5. En la página de lista **Pedidos de compra del proyecto**, haga clic en **Nuevo**.

6. Cree el pedido de compra.

>[!NOTE]
>Para crear una solicitud de compra relacionada, siga los mismos pasos. Sin embargo, seleccione **Tareas de artículo** > **Solicitud de compra de trabajo del pedido de trabajo** en el paso 4.


## <a name="project-relation-between-work-order-and-purchase-order-or-purchase-requisition"></a>Relación de proyectos entre orden de trabajo y pedido de compra o solicitud de compra

Una línea de pedido de compra o de solicitud de compra se relaciona con una tarea de orden de trabajo a través del proyecto de la orden de trabajo y el número de la actividad del proyecto relacionado. Cuando cree un pedido de compra o una solicitud de compra desde una tarea de orden de trabajo, el número de la actividad del proyecto relacionado es obligatorio. Si todos los trabajos de órdenes de trabajo de la orden de trabajo relacionada tienen el mismo tipo de trabajo de mantenimiento, el número de actividad de proyecto se introduce automáticamente en la orden de trabajo o la solicitud de compra. Si los trabajos de órdenes de trabajo tienen tipos de trabajo de mantenimiento diferentes, tiene que introducir manualmente el número de actividad de proyecto en la orden de trabajo o la solicitud de compra.

Para ver o especificar el número de actividad relacionado con una línea de pedido de compra, en la página de lista **Compra de orden de trabajo**, seleccione el registro del pedido de compra y, a continuación, en la columna **Pedido de compra**, seleccione el vínculo para el pedido de compra. Puede encontrar el campo **Número de actividad** en la pestaña **Proyecto** de la ficha desplegable **Detalles de línea**.

La ilustración siguiente muestra un ejemplo de la página **Pedido de compra**, con enfoque en el **Número de actividad**.

![Figura 3.](media/10-work-orders.png)

Igualmente, para ver o especificar el número de actividad relacionado con una línea de solicitud de compra de orden de trabajo, en la página de lista **Solicitud de compra de orden de trabajo**, seleccione el registro de la solicitud de compra y, a continuación, en la columna **Solicitud de compra**, seleccione el vínculo para el pedido de compra. Puede encontrar el campo **Número de actividad** en la pestaña **Proyecto** de la ficha desplegable **Detalles de línea**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]