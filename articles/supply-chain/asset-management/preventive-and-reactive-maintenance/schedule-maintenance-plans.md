---
title: Programar planes de mantenimiento
description: En este tema se explica la programación de planes de mantenimiento en Administración de activos.
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
ms.openlocfilehash: 6b6e5bde83474fe8971e482af518f7cee23a2220
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875878"
---
# <a name="schedule-maintenance-plans"></a>Programar planes de mantenimiento

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

La programación del mantenimiento preventivo genera entradas de calendario en los activos, en función de los planes de mantenimiento configurados en los activos. Puede programar entradas de calendario basadas en los planes de mantenimiento, los tipos de activos y los activos seleccionados.

1. Haga clic en **Administración de activos** > **Periódico** > **Mantenimiento preventivo** > **Programar planes de mantenimiento**.

2. Puede seleccionar un intervalo de tiempo en los campos **Período** y **Frecuencia de períodos**.

>[!NOTE]
>Los campos **Período** y **Frecuencia de períodos** indican con cuánta antelación desea que se creen las líneas del programa de mantenimiento, en función de los planes de mantenimiento que ha creado (basados en tiempo o basados en contador). En la siguiente ilustración, las líneas del programa de mantenimiento (= propuestas de órdenes de trabajo) se crean a partir de la fecha actual y de tres meses en adelante.

3. Seleccione "Sí" en el botón de alternancia **Crear automáticamente si se especifica en la línea** si las órdenes de trabajo deben crearse automáticamente según la línea del plan de mantenimiento.

>[!NOTE]
>Si este botón de alternancia se establece en "Sí" *y* se selecciona también la casilla **Crear automáticamente** en las líneas del plan de mantenimiento en **Planes de mantenimiento**, se crean órdenes de trabajo en función de las líneas del plan de mantenimiento, así como líneas del programa de mantenimiento con el estado "Orden de trabajo creada". Si solo se selecciona una opción (botón de alternancia**Crear automáticamente si se especifica en la línea** en este diálogo o la casilla **Crear automáticamente** en el formulario **Planes de mantenimiento**), solo se crean líneas del programa de mantenimiento con el estado "Creada". En ese caso, no se crean órdenes de trabajo.

4. Es posible generar entradas de calendario basadas en planes de mantenimiento (tiempo o contador), activos, tipos de activos, ubicaciones técnicas y tipos de ubicaciones técnicas. Haga clic en el botón **Filtrar** y haga sus selecciones, si es necesario.

- En cuanto a la programación de planes de mantenimiento en ubicaciones técnicas: si actualiza la configuración de los tipos de activos, los fabricantes y los modelos en los planes de mantenimiento de la ficha desplegable **Todas las ubicaciones técnicas** > **Planes de mantenimiento** después de haber programado planes de mantenimiento, las entradas actuales del programa de mantenimiento relacionadas con esa ubicación técnica se eliminarán automáticamente. Para crear nuevas entradas de calendario que se correspondan con la configuración del plan de mantenimiento actualizado en la ubicación técnica, debe ejecutar una nueva programación del plan de mantenimiento para dicha ubicación técnica. Obtenga más información acerca de la configuración de los tipos de activos, los fabricantes y los modelos en ubicaciones técnicas en [Crear ubicaciones técnicas](../functional-locations/create-functional-locations.md).

>*Ejemplo:* desea crear un plan de mantenimiento para una determinada ubicación técnica, lo que significa que todos los activos configurados en esa ubicación técnica en un momento dado se incluirán cuando programe el plan de mantenimiento. En ese caso, cree un plan de mantenimiento y seleccione la ubicación técnica específica, pero NO agregue ningún objeto en el plan de mantenimiento. El resultado es que cuando programa ese plan de mantenimiento, las líneas del programa de mantenimiento se crearán para todos los activos relacionados con la ubicación técnica en ese momento.

- Si realiza cambios en los tipos de activos, los fabricantes y los modelos en **Tipos de activo**, estos cambios afectan únicamente a los nuevos activos que usan el tipo de activo actualizado. Obtenga más información sobre la configuración de tipos de activos en [Tipos de activos](../setup-for-objects/object-types.md).  

5. Haga clic en **Aceptar** para iniciar la generación de entradas del programa de mantenimiento en los activos. Las entradas generadas se mostrarán en la página de lista **Todo el programa de mantenimiento**.

![Figura 1](media/09-preventive-maintenance.png)

- En el diálogo **Programar planes de mantenimiento**, puede configurar trabajos por lotes en la ficha desplegable **Ejecutar en segundo plano** para generar automáticamente entradas de calendario a intervalos periódicos.  
- Cuando programe un mantenimiento preventivo, no se crearán líneas del programa de mantenimiento con fecha y hora de inicio prevista anterior a la fecha y hora del sistema.  

La imagen siguiente proporciona una ilustración gráfica del cálculo de un plan de mantenimiento basado en la hora.  

![Figura 2](media/10-preventive-maintenance.jpg)

En cuanto a los planes de mantenimiento basados en contador: en las ilustraciones siguientes aparecen dos ciclos de registro del contador diferentes. Se basan en un plan de mantenimiento configurado para el activo "V0001", que espera que el activo (un vehículo) ejecute aproximadamente 2000 km cada mes.

En el primer ejemplo, no se alcanzan los 2000 km previstos cada mes. Según el plan de mantenimiento basado en contador, el umbral es 2000 km, lo que significa que cuando ejecuta una programación del plan de mantenimiento, debe crearse una línea del programa de mantenimiento cada vez que se alcanza al umbral de 2000 km. En el ejemplo 1, hay 4 líneas de registro, pero el umbral de 2000 km solo se alcanza una vez. Esto significa que cuando ejecute los planes de mantenimiento del programa de este activo, por ejemplo para un período de tres meses, solo se creará una línea del programa de mantenimiento.

En la siguiente ilustración se registran 2000 km o más cada mes. Por lo tanto, se crearían tres líneas de mantenimiento si programa planes de mantenimiento para este activo durante un período de tres meses. 

Los ejemplos que se describen aquí indican que todos los registros de contador realizados en un activo muestran una tendencia que describe el desgaste de un activo. Esa tendencia se utiliza como base de cálculo en el momento de la programación del plan de mantenimiento.

![Figura 3](media/11-preventive-maintenance.png)

![Figura 4](media/12-preventive-maintenance.png)
