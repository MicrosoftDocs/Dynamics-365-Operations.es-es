---
title: Programa de mantenimiento
description: En este tema se explica el programa de mantenimiento en Administración de activos.
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
ms.openlocfilehash: 780b633af04c38705f8321d19924f3802b2d5c67
ms.sourcegitcommit: f5bfa3212bc3ef7d944a358ef08fe8863fd93b91
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/16/2019
ms.locfileid: "1875882"
---
# <a name="maintenance-schedule"></a>Programa de mantenimiento

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

El programa de mantenimiento contiene una lista de todos los planes de mantenimiento preventivo, solicitudes de mantenimiento y rondas de mantenimiento que se van a realizar. Puede que algunas líneas de programación se hayan convertido en órdenes de trabajo.

Las cuatro vistas del programa de mantenimiento son ligeramente diferentes, según las líneas del programa de mantenimiento que desee ver.

| Elemento de menú                  | Descripción del contenido                                                                                                                                             |
|----------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Todo el programa de mantenimiento       | Se muestran todas las líneas del programa de mantenimiento.     |
| Mi programación de activos        | En esta lista se muestran todas las líneas del programa de mantenimiento que contienen activos instalados en ubicaciones técnicas con las que está relacionado como trabajador (configuradas en [Trabajadores y grupos de trabajadores de mantenimiento](../setup-for-objects/workers-and-worker-groups.md)). |
| Abrir líneas del programa de mantenimiento | En esta lista se muestran las líneas del programa de mantenimiento con el estado "Creado" (lo que significa que aún no se han convertido en una orden de trabajo o se han descartado).                                            |
| Abrir grupos de programas de mantenimiento | En esta lista se muestran las líneas del programa de mantenimiento relacionadas con un conjunto de órdenes de trabajo.                                                                                                                  |

>[!NOTE]
>Si una línea del programa de mantenimiento se incluye en varios grupos de órdenes de trabajo (consulte [Grupos de órdenes de trabajo](../work-orders/work-order-pools.md)), se muestra un registro para cada grupo en **Grupos del programa de mantenimiento abiertos**. Esto se hace para optimizar las opciones de filtrado en grupos de órdenes de trabajo.

Para abrir un programa de mantenimiento:

1. Haga clic en **Administración de activos** > **Común** > **Programa de mantenimiento** > **Todo el programa de mantenimiento** o **Líneas del programa de mantenimiento abiertas** o **Grupos del programa de mantenimiento abiertos**.

2. Para actualizar el programa de mantenimiento, haga clic en **Plan de mantenimiento** o **Rondas de mantenimiento**. 

3. Puede editar una línea del programa de mantenimiento seleccionándola y haciendo clic en **Editar**. Por ejemplo, puede actualizar fácilmente el nivel de servicio o el trabajador responsable del trabajo. Solo puede editar las líneas del programa de mantenimiento que aún no se han conectado a una orden de trabajo.

4. Puede eliminar una línea del programa de mantenimiento seleccionándola en la página de lista y haciendo clic en **Eliminar**.

5. Puede descartar una línea del programa de mantenimiento seleccionándola en la página de lista y haciendo clic en **Descartar**. Esta función resulta útil si, por ejemplo, un activo tiene un plan de mantenimiento de 2000 km y un plan de mantenimiento de 10 000 km. Después, es posible que desee descartar la línea creada del plan de mantenimiento de 2000 km cuando coincide con 10 000 km, 20 000 km, 30 000 km, etc. Si descarta una línea del programa de mantenimiento relacionada con un plan de mantenimiento, esa línea nunca volverá a aparecer cuando se programe ese plan de mantenimiento.

6. Si desea que todas las líneas seleccionadas se incluyan en el mismo conjunto de órdenes de trabajo, puede seleccionar una serie de líneas del programa de mantenimiento en **Todo el programa de mantenimiento** y hacer clic en **Conjunto de órdenes de trabajo**.

7. Puede seleccionar una serie de líneas del programa de mantenimiento en **Todo el programa de mantenimiento** o **Líneas del programa de mantenimiento abiertas** o **Grupos del programa de mantenimiento abiertos** y hacer clic en **Ajustar programa** si desea realizar los mismos ajustes en varias líneas. Puede cambiar las fechas previstas de inicio y finalización, el nivel de servicio y el trabajador o grupo de trabajadores responsable del mantenimiento relacionado con las líneas del programa de mantenimiento seleccionadas.

- Si una línea del programa de mantenimiento se ha relacionado con una orden de trabajo, el id. de la orden de trabajo se mostrará en el campo **Orden de trabajo**.  
- En la vista de detalles **Todos los activos** > ficha desplegable **Planes de mantenimiento del activo**, puede seleccionar los planes de mantenimiento para el activo. Más adelante, si elimina una línea del plan de mantenimiento relacionada con un activo en **Todos los activos**, también elimina automáticamente todas las líneas del programa de mantenimiento con el estado "Creado" que se crearon a partir del plan de mantenimiento. Consulte también [Crear un activo](../objects/create-an-object.md).

La ilustración siguiente muestra la página de lista **Todo el programa de mantenimiento**.

![Figura 1](media/16-preventive-maintenance.png)

