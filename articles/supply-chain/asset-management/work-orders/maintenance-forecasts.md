---
title: Previsiones de mantenimiento
description: En este tema se explican las previsiones de mantenimiento en Administración de activos.
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
ms.openlocfilehash: 383c910b40199f2da863144c6dc85a579d0091e9
ms.sourcegitcommit: f87de0f949b5d60993b19e0f61297f02d42b5bef
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2019
ms.locfileid: "2024508"
---
# <a name="maintenance-forecasts"></a>Previsiones de mantenimiento

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]


Cuando cree una orden de trabajo, cree tareas de la orden de trabajo con activos y tipos de trabajo de mantenimiento relacionados. Cuando seleccione un tipo de trabajo de mantenimiento que contenga previsiones de mantenimiento, las previsiones se copian automáticamente en la orden de trabajo.

Es posible que pueda agregar o eliminar líneas de previsión en una orden de trabajo. La configuración del estado de ciclo de vida de una orden de trabajo, el tipo de proyecto relacionado y las reglas de etapa relacionadas con el tipo de proyecto determinan si puede agregar o editar líneas de previsión. 

1. Haga clic en **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

2. Seleccione la orden de trabajo en la lista y haga clic en **Previsión**. En **Previsión de mantenimiento de orden de trabajo** se muestran las líneas de previsión del tipo de trabajo de mantenimiento seleccionado en la tarea de la orden de trabajo.


## <a name="add-hours-forecast-to-a-work-order"></a>Agregar previsión de horas a una orden de trabajo

1. Seleccione la tarea de la orden de trabajo a la que desea agregar una previsión.

2. En la ficha desplegable **Horas**, haga clic en **Agregar** para crear una línea nueva.

3. Seleccione una categoría en el campo **Categoría**.

4. Inserte el número de horas previstas en el campo **Horas**.

5. En el campo **Propiedad de la línea**, seleccione el tipo de cargo que se usará en la línea.


## <a name="add-items-forecast-to-a-work-order"></a>Agregar previsión de artículos a una orden de trabajo

Hay tres formas de agregar artículos a una previsión de mantenimiento de orden de trabajo: puede crear líneas para artículos (recambios) que no se incluyen en la lista de recambios o L. MAT de activos, puede seleccionar recambios de la lista de recambios aprobadas, y puede seleccionar artículos de la L. MAT de activos.

1. Seleccione la tarea de la orden de trabajo a la que desea agregar una previsión.

2. Seleccione la ficha desplegable **Artículos**.

3. Haga clic en **Agregar** para crear una nueva línea para un recambio que no está en la lista de recambios o en la lista de L. MAT de activos.

4. Seleccione el elemento el campo **Número de artículo**.

5. Inserte la cantidad en el campo **Cantidad de ventas** y seleccione una unidad de cantidad en el campo **Unidad**.

6. Inserte el precio de coste y la divisa en los campos pertinentes y seleccione **Propiedad de línea**.

7. Si desea cambiar la lista de dimensiones que se muestran en las líneas de artículos, haga clic en **Inventario** > **Mostrar dimensiones**, seleccione "Sí" en el botón de alternancia **Guardar configuración**.

8. Si desea agregar un recambio aprobado a la previsión de mantenimiento, haga clic en **Agregar recambios**, seleccione el recambio, edite la información relacionada si es necesario y haga clic en **Aceptar**.

9. Si desea agregar artículos de la L. MAT de activos a la previsión, haga clic en **Agregar artículos de L. MAT**, seleccione el artículo, edite la información relacionada si es necesario y haga clic en **Aceptar**.

10. Haga clic en **Dónde se usa el artículo** si desea obtener una visión general de dónde se usa el artículo de la línea seleccionada en Administración de activos, en relación con los activos, los valores predeterminados de tipo de trabajo de mantenimiento, lo recambios y las órdenes de trabajo. 



## <a name="add-expense-forecast-to-a-work-order"></a>Agregar previsión de gastos a una orden de trabajo

1. En este tema se explica cómo agregar una previsión de gastos a una orden de trabajo. En el lado izquierdo del formulario, seleccione la tarea de la orden de trabajo a la que desea agregar una previsión.

2. Seleccione la ficha desplegable **Gasto**.

3. Haga clic en **Agregar** para crear una línea nueva.

4. Seleccione una categoría en el campo **Categoría**.

5. Inserte la cantidad en el campo **Cantidad**.

6. Inserte el precio de coste, la divisa de ventas y el precio de venta en los campos correspondientes.

7. En el campo **Propiedad de la línea**, seleccione el tipo de cargo que se usará en la línea.

>[!NOTE]
>En la ficha desplegable **Totales de previsión de mantenimiento** puede obtener una visión general del número de líneas creadas en cada pestaña, para la tarea de la orden de trabajo seleccionada y para la orden de trabajo. Además, puede ver una suma de las horas de trabajo previstas para la tarea de la orden de trabajo y para la orden de trabajo.

![Figura 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a>Actualización automática de previsiones de orden de trabajo

En Administración de activos, puede actualizar automáticamente cualquier cambio en las previsiones de orden de trabajo en lo que respecta a costes por hora, costes de artículo y gastos, que se han actualizado en otros módulos. Esto se hace para garantizar que los últimos precios de coste se utilizan siempre en sus previsiones de orden de trabajo. También es posible realizar actualizaciones similares para [previsiones de tipo de trabajo de mantenimiento](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).

1. Haga clic en **Administración de activos** > **Periódico** > **Previsión** > **Actualizar previsión de orden de trabajo**.

2. En el cuadro de diálogo desplegable **Actualizar previsión de orden de trabajo**, puede agregar selecciones relativas a determinadas órdenes de trabajo o tareas de orden de trabajo, si es necesario. Haga clic en **Filtrar** para hacer esas selecciones.

3. Si es necesario, puede configurar la actualización automática como un trabajo por lotes en la ficha desplegable **Ejecutar en segundo plano**.

4. Haga clic en **Aceptar** para iniciar la actualización de la previsión.


![Figura 2](media/07-work-orders.png)

