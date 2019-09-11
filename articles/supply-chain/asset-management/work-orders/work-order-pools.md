---
title: Grupos de órdenes de trabajo
description: En este tema se describe cómo trabajar con grupos de órdenes de trabajo en administración de activos.
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
ms.openlocfilehash: 069fa02073808fd7bbaac9bc1603e49ce4d450eb
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875883"
---
# <a name="work-order-pools"></a>Grupos de órdenes de trabajo


[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Puede usar conjuntos de órdenes de trabajo para agrupar órdenes de trabajo que tienen algo en común. Por ejemplo, puede crear conjuntos de grupos de trabajo para

- equipos de trabajo; por ejemplo, equipo de mantenimiento A, equipo de mantenimiento B  

- aptitudes profesionales, por ejemplo, electricistas o fontaneros  

- ubicaciones físicas  

- calendarios; por ejemplo, semanas u otros períodos  


Si es necesario, un pedido de trabajo puede realizarse en varios conjuntos de órdenes de trabajo.


## <a name="create-work-order-pool"></a>Crear grupos de órdenes de trabajo

En **Todos los grupos de órdenes de trabajo** o **Grupo de órdenes de trabajo activas**, puede obtener una visión general de los grupos de órdenes de trabajo y crear nuevos grupos.

1. Haga clic en **Administración de activos** > **Común** > **Grupos de órdenes de trabajo** > **Todos los grupos de órdenes de trabajo** o **Grupos de órdenes de trabajo activas**.

2. Haga clic en **Nuevo**.

3. Inserte un identificador de grupo de órdenes de trabajo en el campo **Grupo** y un nombre en el campo **Nombre**.

4. Seleccione "Sí" en el botón de alternar **Activo** para indicar que el grupo de órdenes de trabajo está activo.

5. Seleccione "Sí" en el botón de alternar **Eliminar relaciones de órdenes de trabajo** si desea que las órdenes de trabajo automáticamente se quiten del grupo de órdenes de trabajo.

6. En el campo **Eliminar estado de ciclo de vida**, seleccione el estado del ciclo de vida de la orden de trabajo. Por ejemplo, el estado del ciclo de vida de pedido de trabajo para completar un pedido de trabajo se puede establecer para eliminar automáticamente relaciones con grupos de órdenes de trabajo.

7. Puede empezar a agregar órdenes de trabajo a su grupo de órdenes de trabajo inmediatamente. En la ficha desplegable **Órdenes de trabajo**, haga clic en **Agregar línea**.

8. Seleccione una orden de trabajo en el campo **orden de trabajo**. Los campos relacionados se actualizarán automáticamente.

9. Repita los pasos 7-8 si desea agregar más órdenes de trabajo.

10. En el campo **Orden**, puede indicar si las órdenes de trabajo se realizan siguiendo un orden determinado. Inserte los números 1, 2, 3, etc. para indicar una secuencia específica para las órdenes de trabajo seleccionadas.

11. Haga clic en el botón **Órdenes de trabajo** para ver una lista de todos las órdenes de trabajo incluidas en el grupo de órdenes de trabajo.

12. Haga clic en el botón **Carga de capacidad** para abrir **Carga de capacidad** para calcular y ver la carga de capacidad de la programación del mantenimiento, las órdenes de trabajo no programadas y las órdenes de trabajo programadas.

13. Haga clic en el botón **Previsión de artículos** para abrir **Previsión de artículos** para calcular y ver las previsiones para artículos (piezas de repuesto y otros elementos obligatorios) relacionados con la programación del mantenimiento, las órdenes de trabajo no programadas y las órdenes de trabajo programadas.

14. Haga clic en el botón **Solicitud de compra de orden de trabajo** para abrir la lista **Solicitud de compra de orden de trabajo** para abrir una lista de solicitudes de compra relacionadas con órdenes de compra del grupo de órdenes de trabajo.

15. Haga clic en el botón **Compra de orden de trabajo** para abrir la lista **Compra de orden de trabajo** para abrir una lista de órdenes de compra relacionadas con órdenes de trabajo del grupo de órdenes de trabajo.

>[!NOTE]
>Cuando un conjunto de órdenes de trabajo ya no es relevante para la planificación de trabajo, establezca la casilla de verificación **Activo** de dicho grupo en ”No” en la vista de lista **Grupo de órdenes de trabajo**.

Seleccione la casilla de verificación **Eliminar relaciones de órdenes de trabajo** si desea eliminar todas las líneas de pedido del trabajo, para por ejemplo, crear un conjunto vacío que pueda usar posteriormente para otros órdenes de trabajo. No se olvide de desactivar la casilla de verificación **Eliminar relaciones de órdenes de trabajo** si desea usar el conjunto de órdenes de trabajo para crear relaciones de órdenes de trabajo nuevas posteriormente.


![Figura 1](media/22-work-orders.png)


## <a name="add-work-order-to-a-work-order-pool"></a>Agregar un pedido de trabajo a un conjunto de órdenes de trabajo

Como se describe en la sección anterior, puede agregar órdenes de trabajo a un grupo de órdenes de trabajo al crear el grupo. También puede agregar un pedido de trabajo a un grupo de órdenes de trabajo desde una de las listas de **Todas las órdenes de trabajo**.

1. Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

2. Seleccione la orden de trabajo en la lista y haga clic en **Grupo de órdenes de trabajo**.

3. Seleccione “Agregar” en el campo **Agregar o quitar**.

4. En el campo **Grupo**, seleccione el grupo de órdenes de trabajo.

5. Haga clic en **Aceptar**.

6. Una vez agregado un pedido de trabajo a un conjunto de órdenes de trabajo, si desea poner la orden de trabajo en una secuencia específica del conjunto: Abra una de las páginas de lista de los conjuntos de órdenes de trabajo, seleccione el conjunto y haga clic en **Editar** y ajuste el orden de las órdenes de trabajo incluidas en el conjunto en el formulario **Grupo de órdenes de trabajo** > ficha desplegable **Órdenes de trabajo** > campo **Orden**.

Si desea eliminar la orden de trabajo seleccionado de un conjunto de órdenes de trabajo, seleccione “Quitar” en el paso 3.

