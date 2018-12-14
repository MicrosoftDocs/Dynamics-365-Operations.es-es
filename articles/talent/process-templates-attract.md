---
title: Crear una plantilla de proceso en Attract
description: "Este tema proporciona información sobre cómo crear una plantilla de proceso en Attract."
author: hasrivas
manager: AnnBe
ms.date: 10/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: hasrivas
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: AX 8.1
ms.translationtype: HT
ms.sourcegitcommit: b589a6ce02cdc02436e256f9e81346fe8b766687
ms.openlocfilehash: 2b9cac68093be65584192757229c20b1a1546342
ms.contentlocale: es-es
ms.lasthandoff: 12/04/2018

---

# <a name="create-a-process-template-in-attract"></a><span data-ttu-id="05bcb-103">Crear una plantilla de proceso en Attract</span><span class="sxs-lookup"><span data-stu-id="05bcb-103">Create a process template in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="05bcb-104">Una *plantilla de proceso de contratación* contiene todas las actividades que deben incluirse como parte del proceso de contratación para un trabajo.</span><span class="sxs-lookup"><span data-stu-id="05bcb-104">A *hiring process template* contains all the activities that should be included as part of the hiring process for a job.</span></span> <span data-ttu-id="05bcb-105">Este tema describe los elementos de un proceso de contratación en Microsoft Dynamics 365 for Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="05bcb-105">This topic describes the elements of a process template in Microsoft Dynamics 365 for Talent: Attract.</span></span> <span data-ttu-id="05bcb-106">También se explica cómo crear una plantilla.</span><span class="sxs-lookup"><span data-stu-id="05bcb-106">It also explains how to create a template.</span></span>

> [!NOTE]
> <span data-ttu-id="05bcb-107">La creación de plantillas es parte del complemento de contratación completo de Attract.</span><span class="sxs-lookup"><span data-stu-id="05bcb-107">Template creation is part of the Comprehensive Hiring Add-on for Attract.</span></span>

## <a name="template-management"></a><span data-ttu-id="05bcb-108">Administración de plantillas</span><span class="sxs-lookup"><span data-stu-id="05bcb-108">Template management</span></span>

<span data-ttu-id="05bcb-109">Las organizaciones pueden decidir si los miembros del equipo o solo los administradores pueden crear plantillas de proceso en Attract.</span><span class="sxs-lookup"><span data-stu-id="05bcb-109">Organizations can decide whether team members or only admins can create process templates in Attract.</span></span> <span data-ttu-id="05bcb-110">Para configurar la gestión de plantillas, vaya **Centro de administración** \> **Administración de plantillas**.</span><span class="sxs-lookup"><span data-stu-id="05bcb-110">To configure template management, go to **Admin Center** \> **Template management**.</span></span> <span data-ttu-id="05bcb-111">Para permitir que los miembros del equipo creen sus propias plantillas, active la administración de plantillas.</span><span class="sxs-lookup"><span data-stu-id="05bcb-111">To let team members create their own templates, turn on template management.</span></span> <span data-ttu-id="05bcb-112">Si no activa la administración de plantillas, solo los administradores pueden crear plantillas.</span><span class="sxs-lookup"><span data-stu-id="05bcb-112">If you don't turn on template management, only admins can create templates.</span></span>

## <a name="default-template"></a><span data-ttu-id="05bcb-113">Plantilla predeterminada</span><span class="sxs-lookup"><span data-stu-id="05bcb-113">Default template</span></span>

<span data-ttu-id="05bcb-114">Solo los administradores pueden establecer la plantilla predeterminada.</span><span class="sxs-lookup"><span data-stu-id="05bcb-114">Only admins can set the default template.</span></span> <span data-ttu-id="05bcb-115">Se usa la plantilla predeterminada si una plantilla no se selecciona cuando se crea un trabajo.</span><span class="sxs-lookup"><span data-stu-id="05bcb-115">The default template is used if a template isn't selected when a job is created.</span></span> <span data-ttu-id="05bcb-116">Para configurar la plantilla predeterminada, vaya a **Centro de administración** \> **Administración de plantillas**.</span><span class="sxs-lookup"><span data-stu-id="05bcb-116">To set the default template, go to **Admin Center** \> **Template management**.</span></span> <span data-ttu-id="05bcb-117">En la tarjeta para la plantilla que debe ser la plantilla predeterminada, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Establecer como predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="05bcb-117">On the card for the template that should be the default template, select the ellipsis button (**...**), and then select **Set as default**.</span></span>

## <a name="create-a-process-template"></a><span data-ttu-id="05bcb-118">Crear una plantilla de proceso</span><span class="sxs-lookup"><span data-stu-id="05bcb-118">Create a process template</span></span>

<span data-ttu-id="05bcb-119">Las administraciones, los reclutadores, y los administradores de contratación pueden crear plantillas de proceso.</span><span class="sxs-lookup"><span data-stu-id="05bcb-119">Admins, recruiters, and hiring managers can create process templates.</span></span> <span data-ttu-id="05bcb-120">Una plantilla de proceso consiste en *etapas* y *actividades*.</span><span class="sxs-lookup"><span data-stu-id="05bcb-120">A process template consists of *stages* and *activities*.</span></span> <span data-ttu-id="05bcb-121">Las etapas agrupan conjuntamente una o varias actividades.</span><span class="sxs-lookup"><span data-stu-id="05bcb-121">Stages group together one or more activities.</span></span> <span data-ttu-id="05bcb-122">De forma predeterminada, cada plantilla de proceso tiene actividades de candidato viable, solicitud y propuesta.</span><span class="sxs-lookup"><span data-stu-id="05bcb-122">By default, every process template has Prospect, Application, and Offer activities.</span></span> <span data-ttu-id="05bcb-123">Las etapas que contienen estas actividades pueden ser retituladas.</span><span class="sxs-lookup"><span data-stu-id="05bcb-123">The stages that contain these activities can be renamed.</span></span> <span data-ttu-id="05bcb-124">Puede agregar más etapas seleccionando **+ Nueva etapa**.</span><span class="sxs-lookup"><span data-stu-id="05bcb-124">You can add more stages by selecting **+ New Stage**.</span></span> <span data-ttu-id="05bcb-125">Puede agregar actividades a una etapa arrastrándolas a la etapa apropiada o haciendo doble clic en ellas en la lista de actividades.</span><span class="sxs-lookup"><span data-stu-id="05bcb-125">You can activities to a stage either by dragging them to the appropriate stage or by double-clicking them in the activity list.</span></span>

> [!NOTE]
> <span data-ttu-id="05bcb-126">Los nombres de etapas están visibles para los candidatos en la página **Estado de la solicitud**.</span><span class="sxs-lookup"><span data-stu-id="05bcb-126">Stage names are visible to candidates on the **Application status** page.</span></span> <span data-ttu-id="05bcb-127">Deberá considerar este hecho cuando elija los nombres para las etapas.</span><span class="sxs-lookup"><span data-stu-id="05bcb-127">You should consider this fact when you choose names for stages.</span></span>

<span data-ttu-id="05bcb-128">Para obtener más información acerca de actividades, consulte [Actividades de proceso de contratación en Attract](./activities-attract.md).</span><span class="sxs-lookup"><span data-stu-id="05bcb-128">To learn more about activities, see [Hiring process activities in Attract](./activities-attract.md).</span></span>

<span data-ttu-id="05bcb-129">Siga estos pasos para crear una plantilla de proceso de contratación.</span><span class="sxs-lookup"><span data-stu-id="05bcb-129">Follow these steps to create a hiring process template.</span></span>

1. <span data-ttu-id="05bcb-130">Vaya a **Plantillas**.</span><span class="sxs-lookup"><span data-stu-id="05bcb-130">Go to **Templates**.</span></span>
2. <span data-ttu-id="05bcb-131">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="05bcb-131">Select **New**.</span></span>
3. <span data-ttu-id="05bcb-132">En el campo **Nombre de plantilla**, escriba un nombre para la plantilla y, a continuación seleccione **Crear**.</span><span class="sxs-lookup"><span data-stu-id="05bcb-132">In the **Template name** field, enter a name for the template, and then select **Create**.</span></span>
4. <span data-ttu-id="05bcb-133">En el lista **Elegir el proceso de aprobación**, seleccione **Predeterminado** para requerir la aprobación para un trabajo.</span><span class="sxs-lookup"><span data-stu-id="05bcb-133">In the **Choose the approval process** list, select **Default** to require approval for a job.</span></span>
5. <span data-ttu-id="05bcb-134">Seleccione habilitar o deshabilitar los candidatos viables.</span><span class="sxs-lookup"><span data-stu-id="05bcb-134">Select to enable or disable prospects.</span></span>
6. <span data-ttu-id="05bcb-135">Opcional: agregar o quitar etapas.</span><span class="sxs-lookup"><span data-stu-id="05bcb-135">Optional: Add or remove stages.</span></span>

    - <span data-ttu-id="05bcb-136">Para agregar una etapa, seleccione **+ Nueva etapa**.</span><span class="sxs-lookup"><span data-stu-id="05bcb-136">To add a stage, select **+ New Stage**.</span></span>
    - <span data-ttu-id="05bcb-137">Para quitar una etapa, mantenga el puntero del mouse sobre la etapa, y seleccione el botón de papelera que aparece.</span><span class="sxs-lookup"><span data-stu-id="05bcb-137">To remove a stage, hover the pointer over the stage, and then select the trash can button that appears.</span></span>

        > [!NOTE]
        > <span data-ttu-id="05bcb-138">Las etapas de candidatos potenciales, solicitud u oferta no se pueden eliminar, pero sí se puede cambiar su nombre.</span><span class="sxs-lookup"><span data-stu-id="05bcb-138">Prospect, Application, and Offer stages can't be removed, but they can be renamed.</span></span>

7. <span data-ttu-id="05bcb-139">Opcional: agregar o quitar actividades.</span><span class="sxs-lookup"><span data-stu-id="05bcb-139">Optional: Add or remove activities.</span></span>

    - <span data-ttu-id="05bcb-140">Para agregar una actividad, arrástrela desde la lista de actividades de la derecha a la etapa adecuada.</span><span class="sxs-lookup"><span data-stu-id="05bcb-140">To add an activity, drag it from the activity list on the right to the appropriate stage.</span></span> <span data-ttu-id="05bcb-141">De forma alternativa, haga doble clic en la actividad, y luego seleccione la etapa a la que la agregará.</span><span class="sxs-lookup"><span data-stu-id="05bcb-141">Alternatively, double-click the activity, and then select the stage to add it to.</span></span>
    - <span data-ttu-id="05bcb-142">Para quitar una actividad, expándala y seleccione el botón de papelera en el encabezado de la actividad.</span><span class="sxs-lookup"><span data-stu-id="05bcb-142">To remove an activity, expand it, and then select the trash can button on the activity header.</span></span>

8. <span data-ttu-id="05bcb-143">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="05bcb-143">Select **Save**.</span></span>

