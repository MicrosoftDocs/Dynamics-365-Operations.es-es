---
title: "Configuración de una actividad paralela en un flujo de trabajo"
description: Para configurar una actividad paralela, realice los siguientes procedimientos en el editor de flujo de trabajo.
author: sericks007
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: ec1c1d8abc49deb8ef16322370c59d40b01d344c
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="configure-a-parallel-activity-in-a-workflow"></a>Configuración de una actividad paralela en un flujo de trabajo

[!INCLUDE [banner](../includes/banner.md)]

Para configurar una actividad paralela, realice los siguientes procedimientos en el editor de flujo de trabajo.

Una actividad paralela está formada por dos o más ramas de flujo de trabajo que se ejecutan al mismo tiempo.

## <a name="name-a-parallel-activity"></a>Asignación de un nombre a una actividad paralela
Siga estos pasos para asignar un nombre a una actividad paralela.
1.  Haga clic con el botón secundario en la actividad paralela y, a continuación, haga clic en **Propiedades** para abrir el formulario **Propiedades**.
2.  En el panel izquierdo, haga clic en **Configuración básica**.
3.  En el campo **Nombre**, escriba un nombre único para la actividad paralela.
4.  Haga clic en **Cerrar**.

## <a name="configure-the-branches-of-a-parallel-activity"></a>Configuración de las secciones de una actividad paralela
Siga estos pasos para agregar y configurar las ramas de la actividad paralela.
1. Haga doble clic en la actividad paralela para que se muestren sus ramas.
2. Para agregar una sección, arrastre el elemento **Sección** del área **Elementos de flujo de trabajo** a un punto de inserción del lienzo. En la siguiente ilustración se muestra un punto de inserción.![Insertion point](./media/workflow_insertionpoint.gif)

   |                                              <strong>Nota</strong>                                               |
   |------------------------------------------------------------------------------------------------------------------|
   | El orden de las ramas no es importante, pues todas las ramas de una actividad paralela se ejecutan al mismo tiempo. |


3. Para configurar cada sección, vea [Configuración de una sección paralela](configure-parallel-branch-workflow.md).






