---
title: Configurar actividades paralelas en un flujo de trabajo
description: Para configurar una actividad paralela, realice los siguientes procedimientos en el editor de flujo de trabajo.
author: ChrisGarty
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 195753
ms.assetid: 6d0656df-b5af-4001-96e6-6f0fcc44d022
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a1a47857cbe65c00ad678b2b0372c642abf01b41
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747840"
---
# <a name="configure-parallel-activities-in-a-workflow"></a><span data-ttu-id="5523a-103">Configurar actividades paralelas en un flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="5523a-103">Configure parallel activities in a workflow</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="5523a-104">Para configurar una actividad paralela, realice los siguientes procedimientos en el editor de flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="5523a-104">To configure a parallel activity, complete the following procedures in the workflow editor.</span></span>

<span data-ttu-id="5523a-105">Una actividad paralela está formada por dos o más ramas de flujo de trabajo que se ejecutan al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="5523a-105">A parallel activity consists of workflow branches that run at the same time.</span></span>

## <a name="name-a-parallel-activity"></a><span data-ttu-id="5523a-106">Asignación de un nombre a una actividad paralela</span><span class="sxs-lookup"><span data-stu-id="5523a-106">Name a parallel activity</span></span>

<span data-ttu-id="5523a-107">Siga estos pasos para asignar un nombre a una actividad paralela.</span><span class="sxs-lookup"><span data-stu-id="5523a-107">Follow these steps to enter a name for a parallel activity.</span></span>

1. <span data-ttu-id="5523a-108">Haga clic con el botón secundario en la actividad paralela y, a continuación, haga clic en **Propiedades** para abrir el formulario **Propiedades**.</span><span class="sxs-lookup"><span data-stu-id="5523a-108">Right-click the parallel activity, and then click **Properties** to open the **Properties** form.</span></span>
2. <span data-ttu-id="5523a-109">En el panel izquierdo, haga clic en **Configuración básica**.</span><span class="sxs-lookup"><span data-stu-id="5523a-109">In the left pane, click **Basic Settings**.</span></span>
3. <span data-ttu-id="5523a-110">En el campo **Nombre**, escriba un nombre único para la actividad paralela.</span><span class="sxs-lookup"><span data-stu-id="5523a-110">In the **Name** field, enter a unique name for the parallel activity.</span></span>
4. <span data-ttu-id="5523a-111">Haga clic en **Cerrar**.</span><span class="sxs-lookup"><span data-stu-id="5523a-111">Click **Close**.</span></span>

## <a name="configure-the-branches-of-a-parallel-activity"></a><span data-ttu-id="5523a-112">Configuración de las secciones de una actividad paralela</span><span class="sxs-lookup"><span data-stu-id="5523a-112">Configure the branches of a parallel activity</span></span>

<span data-ttu-id="5523a-113">Siga estos pasos para agregar y configurar las ramas de la actividad paralela.</span><span class="sxs-lookup"><span data-stu-id="5523a-113">Follow these steps to add and configure the branches of this parallel activity.</span></span>

1. <span data-ttu-id="5523a-114">Haga doble clic en la actividad paralela para que se muestren sus ramas.</span><span class="sxs-lookup"><span data-stu-id="5523a-114">Double-click the parallel activity to display the branches of the parallel activity.</span></span>
2. <span data-ttu-id="5523a-115">Para agregar una sección, arrastre el elemento **Sección** del área **Elementos de flujo de trabajo** a un punto de inserción del lienzo.</span><span class="sxs-lookup"><span data-stu-id="5523a-115">To add a branch, drag the **Branch** element from the **Workflow elements** area to an insertion point on the canvas.</span></span> <span data-ttu-id="5523a-116">En la siguiente ilustración, se muestra un punto de inserción.</span><span class="sxs-lookup"><span data-stu-id="5523a-116">The following figure shows an insertion point.</span></span>

    ![Punto de inserción](./media/workflow_insertionpoint.gif)

    > [!NOTE]
    > <span data-ttu-id="5523a-118">El orden de las ramas no es importante, pues todas las ramas de una actividad paralela se ejecutan al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="5523a-118">The order of the branches is not important because all the branches of a parallel activity run at the same time.</span></span>

3. <span data-ttu-id="5523a-119">Para configurar cada sección, vea [Configurar ramas paralelas en un flujo de trabajo](configure-parallel-branch-workflow.md).</span><span class="sxs-lookup"><span data-stu-id="5523a-119">To configure each branch, see [Configure parallel branches in a workflow](configure-parallel-branch-workflow.md).</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]