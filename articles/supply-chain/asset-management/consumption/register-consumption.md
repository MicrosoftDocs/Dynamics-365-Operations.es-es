---
title: Registrar consumo
description: En este artículo se explica cómo registrar el consumo en Administración de activos.
author: johanhoffmann
ms.date: 08/21/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetWorkOrderJournal, EntAssetWorkOrderAddSparePart
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 729ef6aae228ad1e528945031567b92c44cdf256
ms.sourcegitcommit: 6781fc47606b266873385b901c302819ab211b82
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2022
ms.locfileid: "9111766"
---
# <a name="register-consumption"></a>Registrar consumo

[!include [banner](../../includes/banner.md)]

 

Cuando se haya completado un trabajo de mantenimiento en una orden de trabajo, el paso siguiente es hacer los registros de consumo y registrar los diarios. Puede hacer registros en los siguientes tipos de consumo: horas, artículos y gastos. Los distintos tipos de consumo se registran en la página **Diarios de órdenes de trabajo**. La configuración del diario en **Administración de activos** se utiliza para crear y registrar diarios independientes para horas, artículos y gastos en el módulo **Gestión y contabilidad de proyectos**.

En algunos casos, es posible que pueda agregar o eliminar líneas de previsión en una orden de trabajo. La configuración del estado de ciclo de vida de una orden de trabajo, el tipo de proyecto relacionado y las reglas de etapa relacionadas con el tipo de proyecto determinan si puede agregar o editar líneas del diario. Lea más información sobre estados del ciclo de vida de la orden de trabajo y fases del proyecto relacionadas en [Previsiones, órdenes de trabajo y proyectos](../integration-to-project-management-and-accounting/forecasts-work-orders-and-projects.md).

>[!NOTE]
>Es posible configurar un registro automático de diarios en el estado de ciclo de vida de una orden de trabajo. Consulte [Estados de ciclo de vida de orden de trabajo](../setup-for-work-orders/work-order-lifecycle-states.md) para obtener más información.

1. Haga clic en **Administración de activos** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

2. Seleccione la orden de trabajo y haga clic en **Diarios**.

3. Haga clic en **Copiar desde previsión** para transferir cualquier línea de previsión que pueda estar conectada con la orden de trabajo. Puede seleccionar los tipos de consumo que desea transferir.

4. Si es necesario, puede agregar más líneas de consumo en la ficha desplegable pertinente haciendo clic en **Agregar línea** y rellenando los datos de la línea.

5. Haga clic en **Validar diarios** para validar las líneas de diario antes de registrarlo.

6. Haga clic en **Registrar diarios** para registrar las líneas del diario.

7. Después de haber registrado los diarios de consumo, puede actualizar el estado del ciclo de vida del pedido de trabajo. Por ejemplo, para indicar que el pedido de trabajo se ha completado, puede actualizar al estado del ciclo de vida en “terminado”.

    - En el campo **Mostrar** situado en la parte superior de la página **Diarios de órdenes de trabajo**, seleccione las líneas del diario que desea ver: **Todas**, **No registradas** o **Registradas**. Los diarios registrados tienen una marca de verificación en la casilla **Registrado**.  
    - Cuando se crean líneas de artículos en el diario de orden de trabajo, las dimensiones del producto y las dimensiones de seguimiento relacionadas con el artículo se transfieren automáticamente a la línea del diario.  

La siguiente captura de pantalla muestra un ejemplo de los registros de horas y artículos en una orden de trabajo en **Diarios de órdenes de trabajo**.

![Figura 1.](media/01-consumption.png)


## <a name="split-hours-on-work-orders-with-several-work-order-jobs"></a>Horas divididas en órdenes de trabajo con varios trabajos de una orden trabajo

Si una orden de trabajo contiene varias tareas, puede registrar las horas de trabajo mediante la función **Horas divididas**, lo que significa que una línea de registro de horas se puede distribuir de forma equitativa en cada tarea de la orden de trabajo.

1. Haga clic en **Administración de activos** > **Órdenes de trabajo** > **Todas las órdenes de trabajo** u **Órdenes de trabajo activas**.

2. Seleccione la orden de trabajo y haga clic en **Diarios**.

3. Seleccione la línea de registro de horas que desea dividir y haga clic en **Horas divididas**.

4. En el diálogo **Horas divididas en trabajos de mantenimiento de órdenes de trabajo**, el nombre del trabajador que está registrado se muestra automáticamente en el campo **Trabajador**. Si es necesario, puede seleccionar otro trabajador.

5. Seleccione una categoría para el registro de horas en el campo **Categoría**.

6. Inserte el número de horas de trabajo que se van a dividir en el campo **Horas**.

    ![Figura 2.](media/02-consumption.png)

7. Haga clic en **Aceptar**.

*Ejemplo:* en la siguiente captura de pantalla se muestran las líneas de diario para una orden de trabajo que contiene tres tareas. La primera línea, que contiene tres horas de trabajo, se ha dividido, y una hora de trabajo se registra en cada tarea de la orden de trabajo. Una vez creadas las tres líneas de registro de horas, decida qué hacer con la línea de registro de horas original (la primera línea del ejemplo). Puede conservarla tal cual o eliminarla. 

![Figura 3.](media/03-consumption.png)

## <a name="financial-dimensions-on-consumption-registrations"></a>Dimensiones financieras en los registros de consumo

Al hacer registros de consumo, las dimensiones financieras relacionadas con los distintos tipos de registro se agregan a los registros en una secuencia específica. 

- *Registros de horas y gastos:* en primer lugar, se agregan las dimensiones financieras del encabezado del diario, si existen. A continuación, se agregan las dimensiones financieras del proyecto de orden de trabajo relacionado. Finalmente, se agregan las dimensiones financieras del recurso (trabajador).

- *Registros de artículos:* en primer lugar, se agregan las dimensiones financieras del encabezado del diario, si existen. Después, se agregan las dimensiones financieras del proyecto de orden de trabajo relacionado. A continuación, se agregan las dimensiones financieras del sitio. Finalmente, se agregan las dimensiones financieras del artículo.

>[!NOTE]
>Para los tres tipos de registro, se valida la combinación de dimensiones financieras y se dejan en blanco las combinaciones no válidas. Es configuración estándar con otras aplicaciones de finanzas y operaciones.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
