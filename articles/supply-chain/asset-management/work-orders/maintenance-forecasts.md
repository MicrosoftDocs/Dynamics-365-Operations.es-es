---
title: Previsiones de mantenimiento
description: En este tema se explican las previsiones de mantenimiento en Administración de activos.
author: josaw1
manager: tfehr
ms.date: 10/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetWorkOrderForecastToJournals, EntAssetWorkOrderForecast
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 2686dd6db032239e2a3aac03f3998cee055302f6
ms.sourcegitcommit: 5f21cfde36c43887ec209bba4a12b830a1746fcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/29/2020
ms.locfileid: "4437303"
---
# <a name="maintenance-forecasts"></a>Previsiones de mantenimiento

[!include [banner](../../includes/banner.md)]



Cuando cree una orden de trabajo, cree tareas de la orden de trabajo con activos y tipos de trabajo de mantenimiento relacionados. Cuando seleccione un tipo de trabajo de mantenimiento que contenga previsiones de mantenimiento, las previsiones se copian automáticamente en la orden de trabajo.

Es posible que pueda agregar líneas de previsión a una orden de trabajo o eliminarlas de una orden de trabajo. La configuración del estado de ciclo de vida de una orden de trabajo, el tipo de proyecto relacionado y las reglas de etapa relacionadas con el tipo de proyecto determinan si puede agregar o editar líneas de previsión. Para obtener más información sobre estados y etapas de proyecto del ciclo de vida de la orden de trabajo, consulte [Previsiones, órdenes de trabajo y proyectos](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).

1. Seleccione **Administración de activos** > **Común** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

2. Seleccione la orden de trabajo de la lista y, a continuación, en el panel de acciones, en la pestaña **Orden de trabajo**, en el grupo **Proyecto**, seleccione **Previsión**. En la página **Previsión de mantenimiento de orden de trabajo** se muestran las líneas de previsión del tipo de trabajo de mantenimiento seleccionado en la tarea de la orden de trabajo.


## <a name="add-an-hours-forecast-to-a-work-order"></a>Agregar una previsión de horas a una orden de trabajo

1. En la página **Pronóstico de mantenimiento de órdenes de trabajo** , seleccione el trabajo de una orden de trabajo al que se va a agregar una previsión.

2. En la ficha desplegable **Horas**, seleccione **Agregar** para crear una línea nueva.

3. Seleccione una categoría en el campo **Categoría**.

4. Inserte el número de horas previstas en el campo **Horas**.

5. En el campo **Propiedad de la línea**, seleccione el tipo de cargo que se deberá usar en la línea.


## <a name="add-an-items-forecast-to-a-work-order"></a>Agregar una previsión de artículos a una orden de trabajo

Hay tres formas de agregar artículos a una previsión de mantenimiento de pedidos de trabajo. Puede crear líneas para artículos (recambios) que no se incluyen en la lista de recambios o lista de materiales (BOM) del activo, puede seleccionar recambios de la lista de recambios aprobadas o puede seleccionar artículos de la lista de materiales (BOM) del activo.

- En la página **Pronóstico de mantenimiento de órdenes de trabajo** , seleccione el trabajo de una orden de trabajo al que se va a agregar una previsión.

- En el ficha desplegable **Artículos**, agregue los artículos a la previsión de mantenimiento mediante el método adecuado.

Para crear una nueva línea para un recambio que no está en la lista de recambios o en la lista de materiales de activos, siga estos pasos:

1. Seleccione **Agregar**.
2. Seleccione el artículo en el campo **Número de artículo**.
3. Introduzca la cantidad en el campo **Cantidad de ventas**.
4. En el campo **Unidad**, seleccione la unidad de medida para la cantidad.
5. En los campos **Precio de coste** y **Divisa**, introduzca los valores adecuados.
6. En el campo **Propiedad de línea** , seleccione una propiedad de línea.
7. Si desea cambiar la lista de dimensiones que se muestran en las líneas de artículos, haga clic en **Inventario** > **Mostrar dimensiones**, seleccione las dimensiones y defina la opción **Guardar configuración** en **Sí**.

Para agregar un repuesto de una lista de recambios aprobada, siga estos pasos:

1. Seleccione **Agregar recambios**.
2. Seleccione el recambio, y edite la información relacionada como sea necesario.
3. Seleccione **Aceptar**.

Para agregar un artículo de lista de materiales de activos, siga estos pasos:

1. Seleccione **Agregar artículos de L. MAT**.
2. Seleccione el artículo, y edite la información relacionada como sea necesario.
3. Seleccione **Aceptar**.

Para obtener una visión general de dónde se usa el artículo de la línea seleccionada en Administración de activos, en relación con los activos, los valores predeterminados de los tipos de trabajo de mantenimiento, las piezas de repuesto y las órdenes de trabajo en la administración de activos, seleccione **Dónde se usó el artículo**. Para obtener más información sobre esta información general, consulte [Dónde se usó el artículo](../controlling-and-reporting/item-where-used.md).


## <a name="add-an-expense-forecast-to-a-work-order"></a>Agregar una previsión de gastos a una orden de trabajo

1. En la página **Pronóstico de mantenimiento de órdenes de trabajo** , seleccione el trabajo de una orden de trabajo al que se va a agregar una previsión.

2. En la ficha desplegable **Gasto**, seleccione **Agregar** para crear una línea.

3. Seleccione una categoría en el campo **Categoría**.

4. En el campo **Cantidad**, escriba la cantidad.

5. En los campos **Precio de coste**, **Divisa de ventas** y **Precio de venta**, introduzca los valores adecuados.

6. En el campo **Propiedad de la línea**, seleccione el tipo de cargo que se deberá usar en la línea.

>[!NOTE]
>En la ficha desplegable **Totales de previsión de mantenimiento** se muestra una visión general del número de líneas creadas para la tarea de la orden de trabajo seleccionada y para la orden de trabajo, en cada ficha desplegable. Además, muestra la suma de las horas de trabajo previstas para la tarea de la orden de trabajo y para la orden de trabajo.

La ilustración muestra un ejemplo de la página **Previsión de mantenimiento de orden de trabajo**.

![Figura 1](media/06-work-orders.png)


## <a name="automatic-update-of-work-order-forecasts"></a>Actualización automática de previsiones de orden de trabajo

En Administración de activos, puede actualizar automáticamente cualquier cambio en las previsiones de orden de trabajo en lo que respecta a costes por hora, costes de artículo y gastos, que se han actualizado en otros módulos de Microsoft Dynamics 365 for Finance and Operations. Esta capacidad ayuda a garantizar que los últimos precios de coste se utilizan siempre en sus previsiones de orden de trabajo. También es posible realizar actualizaciones similares para [previsiones de tipo de trabajo de mantenimiento](../setup-for-work-orders/job-groups-and-job-types-variants-trades-and-checklists.md).

1. Seleccione **Administración de activos** > **Periódico** > **Previsión** > **Actualizar previsión de orden de trabajo**.

2. En el cuadro de diálogo **Actualizar previsión de orden de trabajo**, en la ficha desplegable **Registros que incluir** puede agregar selecciones relativas a determinadas órdenes de trabajo o tareas de orden de trabajo, si es necesario. Haga clic en **Filtrar** para hacer las selecciones relevantes.

3. En la pestaña desplegable **Ejecutar en segundo plano**, puede configurar la actualización automática como un trabajo por lotes según sea necesario.

4. Seleccione **Aceptar** para iniciar la actualización de la previsión.


La ilustración muestra un ejemplo del cuadro de diálogo **Actualizar previsión de orden de trabajo**.

![Figura 2](media/07-work-orders.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]