---
title: Guarda las guías de tareas en LCS y reproducirlas
description: El artículo explica cómo guardar guías de tareas para Microsoft Dynamics Lifecycle Services (LCS) y, después, reproducirlas.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 2efe48a31db533c5f22d4174cc6897f4a590cf49
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8875811"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a>Guarda las guías de tareas en LCS y reproducirlas


[!INCLUDE [PEAP](../includes/peap-2.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

**Detalles del entorno** 

Microsoft Dynamics 365 Human Resources, que se ha implementado mediante Microsoft Dynamics Lifecycle Services (LCS)

**Emitir**

El cliente desea guardar nuevas grabaciones de tareas al proyecto de LCS y volver a reproducir las guías guardadas de la tarea.

**Resolución**

Siga estos pasos para guardar una grabación de tareas en LCS.

1. Inicie sesión en LCS y seleccione el proyecto.
2. Seleccione el mosaico **Modelador de procesos empresariales** .
3. Vea la página en la "experiencia actualizada de BPM".
4. Seleccione una biblioteca y seleccione **Copiar**.
5. Especifique un nombre para el modelo Modelador de procesos empresariales (BPM).
6. Inicie sesión en Recursos humanos desde LCS.
7. En el campo **Búsqueda**, especifique **ayuda**. Se abre la ayuda de Lifecycle Services.
8. Seleccione el botón **Actualización** para la configuración de la Ayuda de Lifecycle Services.

    Su nueva biblioteca de BPM debe aparecer, y debe estar activa.

9. Cierre la página.
10. Cree una grabación de tareas.
11. Cuando haya terminado, seleccione **Guardar en Lifecycle Services**.

    ![Guardar en Lifecycle Services.](media/task-guides.png)

12. Seleccione la biblioteca y el nodo de BPM donde guardar la grabación de tareas.

Siga estos pasos para volver a consultar una guía de tareas desde LCS.

1. Inicie el grabador de tareas.
2. Seleccione **Abrir desde LCS**.
3. Seleccione la biblioteca y el nodo de BPM que tienen la guía de tareas guardada.
4. Abra la guía de tareas.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
