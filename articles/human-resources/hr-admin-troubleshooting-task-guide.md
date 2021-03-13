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
# <a name="save-task-guides-to-lcs-and-replay-them"></a><span data-ttu-id="43c3e-103">Guarda las guías de tareas en LCS y reproducirlas</span><span class="sxs-lookup"><span data-stu-id="43c3e-103">Save task guides to LCS and replay them</span></span>

<span data-ttu-id="43c3e-104">**Detalles del entorno**</span><span class="sxs-lookup"><span data-stu-id="43c3e-104">**Environment details**</span></span> 

<span data-ttu-id="43c3e-105">Microsoft Dynamics 365 Human Resources, que se ha implementado mediante Microsoft Dynamics Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="43c3e-105">Microsoft Dynamics 365 Human Resources, which was deployed via Microsoft Dynamics Lifecycle Services (LCS)</span></span>

<span data-ttu-id="43c3e-106">**Emisión**</span><span class="sxs-lookup"><span data-stu-id="43c3e-106">**Issue**</span></span>

<span data-ttu-id="43c3e-107">El cliente desea guardar nuevas grabaciones de tareas a su proyecto de LCS y volver a reproducir las guías guardadas de la tarea.</span><span class="sxs-lookup"><span data-stu-id="43c3e-107">The customer wants to save new task recordings to his or her LCS project, and then replay the saved task guides.</span></span>

<span data-ttu-id="43c3e-108">**Resolución**</span><span class="sxs-lookup"><span data-stu-id="43c3e-108">**Resolution**</span></span>

<span data-ttu-id="43c3e-109">Siga estos pasos para guardar una grabación de tareas en LCS.</span><span class="sxs-lookup"><span data-stu-id="43c3e-109">Follow these steps to save a task recording to LCS.</span></span>

1. <span data-ttu-id="43c3e-110">Inicie sesión en LCS y seleccione el proyecto.</span><span class="sxs-lookup"><span data-stu-id="43c3e-110">Sign in to LCS, and select the project.</span></span>
2. <span data-ttu-id="43c3e-111">Seleccione el mosaico **Modelador de procesos empresariales** .</span><span class="sxs-lookup"><span data-stu-id="43c3e-111">Select the **Business process modeler** tile.</span></span>
3. <span data-ttu-id="43c3e-112">Vea la página en la "experiencia actualizada de BPM".</span><span class="sxs-lookup"><span data-stu-id="43c3e-112">View the page in the "Updated BPM experience."</span></span>
4. <span data-ttu-id="43c3e-113">Seleccione una biblioteca y seleccione **Copiar**.</span><span class="sxs-lookup"><span data-stu-id="43c3e-113">Select a library, and then select **Copy**.</span></span>
5. <span data-ttu-id="43c3e-114">Especifique un nombre para el modelo Modelador de procesos empresariales (BPM).</span><span class="sxs-lookup"><span data-stu-id="43c3e-114">Enter a name for the Business process modeler (BPM) model.</span></span>
6. <span data-ttu-id="43c3e-115">Inicie sesión en Recursos humanos desde LCS.</span><span class="sxs-lookup"><span data-stu-id="43c3e-115">Sign in to Human Resources from LCS.</span></span>
7. <span data-ttu-id="43c3e-116">En el campo **Búsqueda**, especifique **ayuda**.</span><span class="sxs-lookup"><span data-stu-id="43c3e-116">In the **Search** field, enter **help**.</span></span> <span data-ttu-id="43c3e-117">Se abre la ayuda de Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="43c3e-117">Lifecycle Services Help is opened.</span></span>
8. <span data-ttu-id="43c3e-118">Seleccione el botón **Actualización** para la configuración de la Ayuda de Lifecycle Services.</span><span class="sxs-lookup"><span data-stu-id="43c3e-118">Select the **Refresh** button for Lifecycle Services Help configuration.</span></span>

    <span data-ttu-id="43c3e-119">Su nueva biblioteca de BPM debe aparecer, y debe estar activa.</span><span class="sxs-lookup"><span data-stu-id="43c3e-119">Your new BPM library should appear, and it should be active.</span></span>

9. <span data-ttu-id="43c3e-120">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="43c3e-120">Close the page.</span></span>
10. <span data-ttu-id="43c3e-121">Cree una grabación de tareas.</span><span class="sxs-lookup"><span data-stu-id="43c3e-121">Create a task recording.</span></span>
11. <span data-ttu-id="43c3e-122">Cuando haya terminado, seleccione **Guardar en Lifecycle Services**.</span><span class="sxs-lookup"><span data-stu-id="43c3e-122">When you've finished, select **Save to Lifecycle Services**.</span></span>

    ![Guardar en Lifecycle Services](media/task-guides.png)

12. <span data-ttu-id="43c3e-124">Seleccione la biblioteca y el nodo de BPM donde guardar la grabación de tareas.</span><span class="sxs-lookup"><span data-stu-id="43c3e-124">Select the BPM library and node to save the task recording to.</span></span>

<span data-ttu-id="43c3e-125">Siga estos pasos para volver a consultar una guía de tareas desde LCS.</span><span class="sxs-lookup"><span data-stu-id="43c3e-125">Follow these steps to replay a task guide from LCS.</span></span>

1. <span data-ttu-id="43c3e-126">Inicie el grabador de tareas.</span><span class="sxs-lookup"><span data-stu-id="43c3e-126">Start Task recorder.</span></span>
2. <span data-ttu-id="43c3e-127">Seleccione **Abrir desde LCS**.</span><span class="sxs-lookup"><span data-stu-id="43c3e-127">Select **Open from LCS**.</span></span>
3. <span data-ttu-id="43c3e-128">Seleccione la biblioteca y el nodo de BPM que tienen la guía de tareas guardada.</span><span class="sxs-lookup"><span data-stu-id="43c3e-128">Select the library and the BPM node that have the saved task guide.</span></span>
4. <span data-ttu-id="43c3e-129">Abra la guía de tareas.</span><span class="sxs-lookup"><span data-stu-id="43c3e-129">Open the task guide.</span></span>
