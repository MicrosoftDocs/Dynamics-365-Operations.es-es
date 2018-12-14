---
title: "Guardar las guías de tarea al LCS y reproducirlas"
description: "Este tema explica cómo guardar las guías de la tarea en Microsoft Dynamics Lifecycle Services (LCS) y volver a reproducirlas."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: 40b4c3154a04a557b8a670e1f1ae3722c71122fe
ms.contentlocale: es-es
ms.lasthandoff: 12/04/2018

---

# <a name="save-task-guides-to-lcs-and-replay-them"></a>Guardar las guías de tarea al LCS y reproducirlas

[!include [banner](includes/banner.md)]

**Detalles del entorno** 

Microsoft Dynamics 365 for Talent, que se ha implementado mediante los Microsoft Dynamics Lifecycle Services (LCS)

**Emisión**

El cliente desea guardar nuevas grabaciones de tareas a su proyecto de LCS y volver a reproducir las guías guardadas de la tarea.

**Resolución**

Siga estos pasos para guardar una grabación de tareas en LCS.

1. Inicie sesión en LCS y seleccione el proyecto.
2. Seleccione el mosaico **Modelador de procesos empresariales** .
3. Vea la página en la "experiencia actualizada de BPM".
4. Seleccione una biblioteca y seleccione **Copiar**.
5. Especifique un nombre para el modelo Modelador de procesos empresariales (BPM).
6. Inicie sesión en Talent desde LCS.
7. En el campo **Búsqueda**, especifique **ayuda**. Se abre la ayuda de Lifecycle Services.
8. Seleccione el botón **Actualización** para la configuración de la Ayuda de Lifecycle Services.

    Su nueva biblioteca de BPM debe aparecer, y debe estar activa.

9. Cierre la página.
10. Cree una grabación de tareas.
11. Cuando haya terminado, seleccione **Guardar en Lifecycle Services**.

    ![Guardar en Lifecycle Services](media/task-guides.png)

12. Seleccione la biblioteca y el nodo de BPM donde guardar la grabación de tareas.

Siga estos pasos para volver a consultar una guía de tareas desde LCS.

1. Inicie el grabador de tareas.
2. Seleccione **Abrir desde LCS**.
3. Seleccione la biblioteca y el nodo de BPM que tienen la guía de tareas guardada.
4. Abra la guía de tareas.

