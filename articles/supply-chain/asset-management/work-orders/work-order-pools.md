---
title: Grupos de órdenes de trabajo
description: En este tema se describe cómo trabajar con grupos de órdenes de trabajo en administración de activos.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderTablePoolPart, EntAssetWorkOrderPoolReferenceInfoPart, EntAssetWorkOrderPool, EntAssetWorkOrderPoolPreviewPart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 3e95a4fdfaf4817867f3d2df7774df6a27ee6599
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437148"
---
# <a name="work-order-pools"></a>Grupos de órdenes de trabajo

[!include [banner](../../includes/banner.md)]


Puede usar conjuntos de órdenes de trabajo para agrupar órdenes de trabajo que tienen algo en común. A continuación se muestran algunos ejemplos para los que puede crear grupos de órdenes de trabajo:

- Equipos de trabajo; por ejemplo, equipo de mantenimiento A, equipo de mantenimiento B  

- Aptitudes profesionales, como electricistas o fontaneros  

- Ubicaciones físicas  

- Programaciones horarias, como semanas u otros períodos  

Según necesite, puede colocar una orden de trabajo en varios grupos de órdenes de trabajo.


## <a name="create-a-work-order-pool"></a>Crear un grupo de órdenes de trabajo

En la página de lista **Todos los grupos de órdenes de trabajo** o **Grupo de órdenes de trabajo activas**, puede obtener una visión general de los grupos de órdenes de trabajo y crear nuevos grupos.

1. Seleccione **Administración de activos** > **Común** > **Grupos de órdenes de trabajo** > **Todos los grupos de órdenes de trabajo** o **Grupos de órdenes de trabajo activas**.

2. Seleccione **Nuevo**.

3. En el campo **Conjunto**, especifique un id. para el grupo de órdenes de trabajo.

4. Escriba un nombre en el campo **Nombre**.

5. Establezca la opción **Activo** en **Sí** para indicar que el grupo de órdenes de trabajo está activo.

6. Establezca la opción **Eliminar relaciones de órdenes de trabajo** en **Sí** si desea que las órdenes de trabajo automáticamente se quiten del grupo de órdenes de trabajo.

7. En el campo **Eliminar estado de ciclo de vida**, seleccione el estado del ciclo de vida de la orden de trabajo. Por ejemplo, el estado del ciclo de vida de pedido de trabajo para completar un pedido de trabajo se puede establecer para eliminar automáticamente relaciones con grupos de órdenes de trabajo.

    Puede empezar a agregar órdenes de trabajo a su grupo de órdenes de trabajo inmediatamente.

8. En la ficha desplegable **Órdenes de trabajo**, seleccione **Agregar línea**.

9. Seleccione una orden de trabajo en el campo **Orden de trabajo**. Los campos relacionados se actualizarán automáticamente.

10. Repita los pasos del 8 al 9 para agregar más órdenes de trabajo.

11. Si las órdenes de trabajo que agregó deben realizarse en un orden específico, en el campo **Orden**, puede escribir los números **1**, **2**, **3**, etc., para especificar ese orden.

12. Para ver una lista de todas las órdenes de trabajo que se incluyen en el grupo de órdenes de trabajo, en el panel de acciones, en la pestaña **Grupo de órdenes de trabajo**, en el grupo de **ver grupo de órdenes de trabajo relacionado**, seleccione **Órdenes de trabajo** para abrir la página de lista **Todas las órdenes de trabajo** .

13. Para calcular y ver la carga de capacidad para el programa de mantenimiento, las órdenes de trabajo no programadas y las órdenes de trabajo programadas, en el panel de acciones, en la pestaña **Grupo de órdenes de trabajo**, en el grupo de **ver grupo de órdenes de trabajo relacionado**, seleccione **Carga de capacidad** para abrir el diálogo **Calcular carga de capacidad** .

14. Para calcular y ver las previsiones para artículos (piezas de repuesto y otros artículos requeridos) que son necesarios para el programa de mantenimiento, las órdenes de trabajo no programadas y las órdenes de trabajo programadas, en el panel de acciones, en la pestaña **Grupo de órdenes de trabajo**, en el grupo de **ver grupo de órdenes de trabajo relacionado**, seleccione **Previsión de artículos** para abrir el diálogo **Calcular previsión de artículo**.

15. Para ver una lista de las solicitudes de compra que están relacionadas con las órdenes de trabajo del grupo de órdenes de trabajo, en el panel de acciones, en la pestaña **Grupo de órdenes de trabajo**, en el grupo **Adquisición**, seleccione **Solicitud de compra de orden de trabajo** para abrir la página de lista **Solicitud de compra de orden de trabajo**.

16. Para ver una lista de las órdenes de compra que están relacionadas con las órdenes de trabajo del grupo de órdenes de trabajo, en el panel de acciones, en la pestaña **Grupo de órdenes de trabajo**, en el grupo **Adquisición**, seleccione **Compra de orden de trabajo** para abrir la página de lista **Compra de orden de trabajo**.

>[!NOTE]
>Cuando un conjunto de órdenes de trabajo ya no es relevante para la planificación de trabajo, establezca la opción **Activo** de dicho grupo en **No** en la vista de lista de la página **Grupo de órdenes de trabajo**.

Para eliminar todas las líneas de orden de trabajo, establezca la opción **Eliminar relaciones de órdenes de trabajo** en **Sí**. Esta opción resulta útil si, por ejemplo, desea crear un grupo vacío que pueda usar posteriormente en otras órdenes de trabajo. Cuando esté preparado para usar el grupo de órdenes de trabajo para crear relaciones de órdenes de trabajo nuevas posteriormente, recuerde establecer la opción **Eliminar relaciones de órdenes de trabajo** en **No**.

La ilustración siguiente muestra un ejemplo de la página de lista **Grupo de órdenes de trabajo**.

![Figura 1](media/22-work-orders.png)


## <a name="add-a-work-order-to-a-work-order-pool"></a>Agregar una orden de trabajo a un grupo de órdenes de trabajo

Como se describe en la sección anterior, puede agregar órdenes de trabajo a un grupo de órdenes de trabajo al crear ese grupo. También puede agregar órdenes de trabajo a un grupo de órdenes de trabajo en la página de lista **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

1. Seleccione la orden de trabajo y, a continuación, en el panel de acciones, en la pestaña **Orden de trabajo**, en el grupo **Mantener**, seleccione **Grupo de órdenes de trabajo**.

2. Seleccione la orden de trabajo en la lista y haga clic en **Grupo de órdenes de trabajo**.

3. En el diálogo **Mantener grupo de órdenes de trabajo**, en el campo **Agregar o quitar**, seleccione **Agregar**.

4. En el campo **Grupo**, seleccione el grupo de órdenes de trabajo.

5. Seleccione **Aceptar**.

6. Para poner la orden de trabajo que ha agregado en un orden determinado en el grupo de órdenes de trabajo, en la página de lista **Todos los conjuntos del pedido de trabajo** o **Conjuntos activo de pedidos de trabajo**, seleccione el grupo y, a continuación, seleccione **Editar**. A continuación, en la página **Grupo de órdenes de trabajo**, en la ficha desplegable **Órdenes de trabajo**, utilice el campo **Orden** para ajustar el orden de las órdenes de trabajo que se incluyen en el grupo.

Para eliminar una orden de trabajo de un grupo de órdenes de trabajo, repita estos pasos pero seleccione **Quitar** en el paso 3.

