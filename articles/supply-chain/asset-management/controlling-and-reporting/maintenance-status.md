---
title: Estado de mantenimiento
description: En este tema se explica cómo calcular un estado de mantenimiento en Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/23/2019
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
ms.search.validFrom: 2019-08-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 516607c056125a16e075c33f3c2ad069efb396d9
ms.sourcegitcommit: 2292b54e2da96f71b59ec9ccf17cd32d3d1d8b21
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/23/2019
ms.locfileid: "1918358"
---
# <a name="maintenance-status"></a>Estado de mantenimiento

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

En Administración de activos, puede realizar un cálculo para obtener una visión general de solicitudes de mantenimiento, órdenes de trabajo y actividades del tiempo de inactividad por mantenimiento nuevas, activas y completadas para un periodo determinado. También puede ver el número de evaluaciones de estado completadas para el mismo periodo. Use este cálculo para obtener una visión general de la carga de trabajo relativa a solicitudes de mantenimiento y órdenes de trabajo entrantes y completadas.

## <a name="make-a-maintenance-status-calculation"></a>Realizar un cálculo del estado de mantenimiento

1. Haga clic en **Administración de activos** > **Consultas** > **Estado de mantenimiento**.

2. En el diálogo **Calcular estado**, seleccione el período para el que desea crear el cálculo en los campos **Fecha inicial** y **Fecha final**.

3. Puede usar el campo **Nivel** para indicar el nivel de detalle que desea para las líneas de mantenimiento con respecto a las ubicaciones técnicas. Por ejemplo, si especifica el número "1" en el campo y tiene una estructura de ubicación técnica de varios niveles, todas líneas de mantenimiento para una ubicación técnica se mostrarán en el nivel superior. De este modo, el estado en una línea se puede agregar desde las ubicaciones técnicas ubicadas en un nivel inferior. Si especifica el número "0" en el campo **Nivel**, verá un resultado detallado que muestra todas las líneas de mantenimiento en todos los niveles de la ubicación técnica con los que están relacionados.

4. Haga clic en **Aceptar** para iniciar el cálculo.

5. En los grupos del panel de acciones **Agrupar por...**, haga clic en los botones relevantes para mostrar el nivel de detalle necesario del cálculo. Se resaltarán los botones del panel de acciones seleccionados. Haga clic en un botón para activarlo o desactivarlo.

6. Recuerde hacer clic en el botón **Actualizar** para actualizar el cálculo cada vez que haga cambios activando o desactivando los botones **Agrupar por…** o bien haciendo un cálculo para un nuevo periodo.

7. Haga clic en **Estado** si desea crear un nuevo cálculo del estado de mantenimiento.

>[!NOTE]
>Los resultados que se muestran en **Estado de mantenimiento** solo incluyen solicitudes de mantenimiento y órdenes de trabajo que tienen una fecha y hora de inicio real. La fecha y hora de finalización pueden estar en blanco.

*Ejemplo 1:*

En la ilustración siguiente, se han activado los botones **Año** y **Mes**. Aquí obtiene una visión general de la carga de trabajo y el rendimiento mensual relacionado con solicitudes de mantenimiento y órdenes de trabajo. 

![Figura 1](media/13-controlling-and-reporting.png)

*Ejemplo 2:*

En la siguiente ilustración se ha agregado información sobre ubicaciones técnicas. Ahora es posible comparar la carga de trabajo y el rendimiento a través de ubicaciones técnicas, lo que puede representar ubicaciones geográficas, fábricas o áreas de trabajo. 

![Figura 2](media/14-controlling-and-reporting.png)

