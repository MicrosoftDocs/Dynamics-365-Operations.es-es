---
title: Calcular carga de capacidad
description: En este tema se explica cómo calcular la carca de capacidad Administración de activos.
author: josaw1
manager: AnnBe
ms.date: 08/16/2019
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
ms.openlocfilehash: c6d15861492a46ddb1222db2210f8c751ed38cb3
ms.sourcegitcommit: 109a6ef2d20758dc4a25c51b11e22dd2214a1cc4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1886802"
---
# <a name="calculate-capacity-load"></a>Calcular carga de capacidad

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

En Administración de activos, puede calcular la carga de capacidad en

- líneas del programa de mantenimiento  
- órdenes de trabajo que aún no se han programado  
- órdenes de trabajo programadas

Esto resulta útil si desea obtener una visión general de la carga de capacidad esperada para un período específico. El cálculo de la carga de capacidad se puede realizar en todos los activos o los activos seleccionados. También puede crear un cálculo de los conjuntos de las actividades del tiempo de inactividad o los grupos de órdenes de trabajo.

1. Haga clic en **Administración de activos** > **Consultas** > **Carga de capacidad** o **Administración de activos** > **Común** > **Grupos de órdenes de trabajo** > **Todos los grupos de órdenes de trabajo** / **Grupos de órdenes de trabajo activas** > seleccionar el grupo de órdenes de trabajo en la lista > botón **Carga de capacidad** o **Administración de activos** > **Común**  > **Actividades de tiempo de inactividad por mantenimiento** > **Todas las actividades de tiempo de inactividad por mantenimiento** / **Actividades de tiempo de inactividad por mantenimiento activas** > seleccione actividad de mantenimiento en la lista > botón **Carga de capacidad**.

2. En el diálogo **Calcular la carga de capacidad**, seleccione un período para el cálculo en los campos **Fecha y hora de inicio** y los campos **Fecha y hora final**.

3. Seleccione "Sí" en el botón de alternar **Incluir programación de mantenimiento** si desea incluir líneas de mantenimiento en el cálculo.

4. Seleccione "Sí" en el botón de alternar **Incluir orden de trabajo** si desea incluir trabajos de orden de trabajo en el cálculo.

5. Puede usar el campo **Nivel** para indicar el nivel de detalle que desea para las líneas de carga de capacidad con respecto a las ubicaciones técnicas. Por ejemplo, si especifica el número "1" en el campo, y tiene una estructura de ubicación técnica de varios niveles, todas líneas del programa de mantenimiento y órdenes de trabajo para una ubicación técnica se mostrarán en el nivel superior, y por tanto, las horas en una línea se pueden agregar desde las ubicaciones técnicas ubicadas en un nivel inferior. Si especifica el número "0" en el campo **Nivel**, verá un resultado detallado que muestra todas las líneas del programa de mantenimiento y todas las órdenes de trabajo en todos los niveles de la ubicación técnica con el que están relacionadas.

6. Haga clic en **Aceptar** para iniciar el cálculo.

7. En los grupos del panel de acciones **Agrupar por...**, haga clic en los botones relevantes para mostrar el nivel de detalle necesario del cálculo. Se resaltarán en color azul los botones del grupo del panel de acciones seleccionados. Haga clic en un botón para activarlo o desactivarlo.

La ilustración siguiente muestra un ejemplo de interfaz.

![Figura 1](media/01-capacity-planning.png)

>[!NOTE]
>Si desea centrarse únicamente en el diseño de la capacidad en relación a las órdenes de trabajo programadas, consulte [Calcular la carga de capacidad en órdenes de trabajo programadas](../work-order-scheduling/calculate-capacity-load-on-scheduled-work-orders.md).

