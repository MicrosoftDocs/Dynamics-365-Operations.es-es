---
title: Guarda las guías de tareas en LCS y reproducirlas
description: Este tema explica cómo guardar las guías de la tarea en Microsoft Dynamics Lifecycle Services (LCS) y volver a reproducirlas.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: e84f0c18cfb52de2c6c8c40af9a08a88c947e38c
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010577"
---
# <a name="save-task-guides-to-lcs-and-replay-them"></a><span data-ttu-id="3e2f4-103">Guarda las guías de tareas en LCS y reproducirlas</span><span class="sxs-lookup"><span data-stu-id="3e2f4-103">Save task guides to LCS and replay them</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3e2f4-104">**Detalles del entorno**</span><span class="sxs-lookup"><span data-stu-id="3e2f4-104">**Environment details**</span></span> 

<span data-ttu-id="3e2f4-105">Microsoft Dynamics 365 Talent, que se ha implementado mediante Microsoft Dynamics Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="3e2f4-105">Microsoft Dynamics 365 Talent, which was deployed via Microsoft Dynamics Lifecycle Services (LCS)</span></span>

<span data-ttu-id="3e2f4-106">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="3e2f4-106">**Issue**</span></span>

<span data-ttu-id="3e2f4-107">El cliente desea guardar nuevas grabaciones de tareas a su proyecto de LCS y volver a reproducir las guías guardadas de la tarea.</span><span class="sxs-lookup"><span data-stu-id="3e2f4-107">The customer wants to save new task recordings to his or her LCS project, and then replay the saved task guides.</span></span>

<span data-ttu-id="3e2f4-108">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="3e2f4-108">**Resolution**</span></span>

<span data-ttu-id="3e2f4-109">Siga estos pasos para guardar una grabación de tareas en LCS.</span><span class="sxs-lookup"><span data-stu-id="3e2f4-109">Follow these steps to save a task recording to LCS.</span></span>

1. <span data-ttu-id="3e2f4-110">Inicie sesión en LCS y seleccione el proyecto.</span><span class="sxs-lookup"><span data-stu-id="3e2f4-110">Sign in to LCS, and select the project.</span></span>
2. <span data-ttu-id="3e2f4-111">Seleccione el mosaico **Modelador de procesos empresariales** .</span><span class="sxs-lookup"><span data-stu-id="3e2f4-111">Select the **Business process modeler** tile.</span></span>
3. <span data-ttu-id="3e2f4-112">Vea la página en la "experiencia actualizada de BPM".</span><span class="sxs-lookup"><span data-stu-id="3e2f4-112">View the page in the "Updated BPM experience."</span></span>
4. <span data-ttu-id="3e2f4-113">Seleccione una biblioteca y seleccione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="3e2f4-113">Select a library, and then select **Copy**.</span></span>
5. <span data-ttu-id="3e2f4-114">Especifique un nombre para el modelo Modelador de procesos empresariales (BPM).</span><span class="sxs-lookup"><span data-stu-id="3e2f4-114">Enter a name for the Business process modeler (BPM) model.</span></span>
6. <span data-ttu-id="3e2f4-115">Inicie sesión en Talent desde LCS.</span><span class="sxs-lookup"><span data-stu-id="3e2f4-115">Sign in to Talent from LCS.</span></span>
7. <span data-ttu-id="3e2f4-116">En el campo **Búsqueda**, especifique **ayuda**.</span><span class="sxs-lookup"><span data-stu-id="3e2f4-116">In the **Search** field, enter **help**.</span></span> <span data-ttu-id="3e2f4-117">Se abre la ayuda de Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="3e2f4-117">Lifecycle Services Help is opened.</span></span>
8. <span data-ttu-id="3e2f4-118">Seleccione el botón **Actualización** para la configuración de la Ayuda de Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="3e2f4-118">Select the **Refresh** button for Lifecycle Services Help configuration.</span></span>

    <span data-ttu-id="3e2f4-119">Su nueva biblioteca de BPM debe aparecer, y debe estar activa.</span><span class="sxs-lookup"><span data-stu-id="3e2f4-119">Your new BPM library should appear, and it should be active.</span></span>

9. <span data-ttu-id="3e2f4-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="3e2f4-120">Close the page.</span></span>
10. <span data-ttu-id="3e2f4-121">Cree una grabación de tareas.</span><span class="sxs-lookup"><span data-stu-id="3e2f4-121">Create a task recording.</span></span>
11. <span data-ttu-id="3e2f4-122">Cuando haya terminado, seleccione **Guardar en Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="3e2f4-122">When you've finished, select **Save to Lifecycle Services**.</span></span>

    ![Guardar en Lifecycle Services](media/task-guides.png)

12. <span data-ttu-id="3e2f4-124">Seleccione la biblioteca y el nodo de BPM donde guardar la grabación de tareas.</span><span class="sxs-lookup"><span data-stu-id="3e2f4-124">Select the BPM library and node to save the task recording to.</span></span>

<span data-ttu-id="3e2f4-125">Siga estos pasos para volver a consultar una guía de tareas desde LCS.</span><span class="sxs-lookup"><span data-stu-id="3e2f4-125">Follow these steps to replay a task guide from LCS.</span></span>

1. <span data-ttu-id="3e2f4-126">Inicie el grabador de tareas.</span><span class="sxs-lookup"><span data-stu-id="3e2f4-126">Start Task recorder.</span></span>
2. <span data-ttu-id="3e2f4-127">Seleccione **Abrir desde LCS**.</span><span class="sxs-lookup"><span data-stu-id="3e2f4-127">Select **Open from LCS**.</span></span>
3. <span data-ttu-id="3e2f4-128">Seleccione la biblioteca y el nodo de BPM que tienen la guía de tareas guardada.</span><span class="sxs-lookup"><span data-stu-id="3e2f4-128">Select the library and the BPM node that have the saved task guide.</span></span>
4. <span data-ttu-id="3e2f4-129">Abra la guía de tareas.</span><span class="sxs-lookup"><span data-stu-id="3e2f4-129">Open the task guide.</span></span>
