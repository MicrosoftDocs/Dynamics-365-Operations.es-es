---
title: "Configuración de una actividad paralela en un flujo de trabajo"
description: Para configurar una actividad paralela, realice los siguientes procedimientos en el editor de flujo de trabajo.
author: sericks007
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: donaldc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 818fb054742b935d002a7341e54a37eca0bb4761
ms.lasthandoff: 03/31/2017


---

# <a name="configure-a-parallel-activity-in-a-workflow"></a>Configuración de una actividad paralela en un flujo de trabajo

Para configurar una actividad paralela, realice los siguientes procedimientos en el editor de flujo de trabajo.

Una actividad paralela está formada por dos o más ramas de flujo de trabajo que se ejecutan al mismo tiempo.

## <a name="name-a-parallel-activity"></a>Asignación de un nombre a una actividad paralela
Siga estos pasos para asignar un nombre a una actividad paralela.
1.  Haga clic con el botón secundario en la actividad paralela y, a continuación haga clic en ** las propiedades ** para abrir ** las propiedades ** el formulario.
2.  En el panel izquierdo, haga clic en **Configuración básica**.
3.  En el campo **Nombre**, escriba un nombre único para la actividad paralela.
4.  Haga clic en **Cerrar**.

## <a name="configure-the-branches-of-a-parallel-activity"></a>Configuración de las secciones de una actividad paralela
Siga estos pasos para agregar y configurar las ramas de la actividad paralela.
1.  Haga doble clic en la actividad paralela para que se muestren sus ramas.
2.  Para agregar una sección, arrastre el elemento **Sección** del área **Elementos de flujo de trabajo** a un punto de inserción del lienzo. En la siguiente ilustración se muestra un punto de inserción.![Insertion point](./media/workflow_insertionpoint.gif)
    | **Nota **                                                                                                         |
    |------------------------------------------------------------------------------------------------------------------|
    | El orden de las ramas no es importante, pues todas las ramas de una actividad paralela se ejecutan al mismo tiempo. |

3.  Para configurar cada sección, vea [Configuración de una sección paralela](http://axhelp.dynamics.com/en/wiki/configure-a-parallel-branch/).




