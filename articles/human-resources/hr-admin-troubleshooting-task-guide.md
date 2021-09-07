---
title: Guarda las guías de tareas en LCS y reproducirlas
description: Este tema explica cómo guardar las guías de la tarea en Microsoft Dynamics Lifecycle Services (LCS) y volver a reproducirlas.
author: twheeloc
ms.date: 08/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 42fad014590abebf159b71227a44eb8df60bf05e
ms.sourcegitcommit: 259ba130450d8a6d93a65685c22c7eb411982c92
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/24/2021
ms.locfileid: "7416890"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a>Guarda las guías de tareas en LCS y reproducirlas

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
