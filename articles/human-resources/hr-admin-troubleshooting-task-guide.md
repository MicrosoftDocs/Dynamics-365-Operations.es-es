---
title: Guarda las guías de tareas en LCS y reproducirlas
description: El artículo explica cómo guardar guías de tareas para Microsoft Dynamics Lifecycle Services (LCS) y, después, reproducirlas.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c81c345932e0e3dce4b13104222ed9f668a3c460
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114214"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a>Guarda las guías de tareas en LCS y reproducirlas

**Detalles del entorno** 

Microsoft Dynamics 365 Human Resources, que se ha implementado mediante Microsoft Dynamics Lifecycle Services (LCS)

**Emisión**

El cliente desea guardar nuevas grabaciones de tareas a su proyecto de LCS y volver a reproducir las guías guardadas de la tarea.

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

    ![Guardar en Lifecycle Services](media/task-guides.png)

12. Seleccione la biblioteca y el nodo de BPM donde guardar la grabación de tareas.

Siga estos pasos para volver a consultar una guía de tareas desde LCS.

1. Inicie el grabador de tareas.
2. Seleccione **Abrir desde LCS**.
3. Seleccione la biblioteca y el nodo de BPM que tienen la guía de tareas guardada.
4. Abra la guía de tareas.


[!INCLUDE[footer-include](../includes/footer-banner.md)]