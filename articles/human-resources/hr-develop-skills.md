---
title: Configurar aptitudes
description: Puede realizar un seguimiento de las aptitudes de su trabajador en Dynamics 365 Human Resources. También puede especificar las aptitudes necesarias para un puesto concreto.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 816822d1f3d365b4c5571c13e9f596e1c5d5e59c
ms.sourcegitcommit: 48528233e0f02dbd47e96e030254ef65f2bb899e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "6076568"
---
# <a name="configure-skills"></a><span data-ttu-id="f5343-104">Configurar aptitudes</span><span class="sxs-lookup"><span data-stu-id="f5343-104">Configure skills</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="f5343-105">Puede realizar un seguimiento de las aptitudes de su trabajador en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="f5343-105">You can track your worker's skills in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="f5343-106">También puede especificar las aptitudes necesarias para un puesto concreto.</span><span class="sxs-lookup"><span data-stu-id="f5343-106">You can also specify the skills that are required for a specific job.</span></span>

<span data-ttu-id="f5343-107">Estos son ejemplos de aptitudes de las que se puede hacer un seguimiento:</span><span class="sxs-lookup"><span data-stu-id="f5343-107">Examples of skills you can track include:</span></span>

- <span data-ttu-id="f5343-108">Supervisión: capacidad para supervisar el trabajo de los demás.</span><span class="sxs-lookup"><span data-stu-id="f5343-108">Supervisory – Ability to supervise the work of others.</span></span>
- <span data-ttu-id="f5343-109">Liderazgo: capacidad para dirigir empleados y dominios de empresa.</span><span class="sxs-lookup"><span data-stu-id="f5343-109">Leadership – Ability to lead employees and business domains.</span></span>
- <span data-ttu-id="f5343-110">Planificación: capacidad para anticipar las cosas, formar instrucciones de visiones de futuro y ponerlas en práctica.</span><span class="sxs-lookup"><span data-stu-id="f5343-110">Planning – Ability to look ahead, to form vision statements, and to see them through.</span></span>
- <span data-ttu-id="f5343-111">HTML: capacidad de escribir código HTML.</span><span class="sxs-lookup"><span data-stu-id="f5343-111">HTML – Ability to write HTML code.</span></span>

<span data-ttu-id="f5343-112">Si aún no ha configurado tipos de aptitudes y modelos de calificación, deberá agregar algunos antes de crear habilidades.</span><span class="sxs-lookup"><span data-stu-id="f5343-112">If you haven't already set up skill types and rating models, you'll need to add some before creating skills.</span></span>

<span data-ttu-id="f5343-113">Las siguientes personas pueden ingresar aptitudes para un trabajador:</span><span class="sxs-lookup"><span data-stu-id="f5343-113">The following people can enter skills for a worker:</span></span>

- <span data-ttu-id="f5343-114">Los trabajadores pueden introducir aptitudes por sí mismos en el autoservicio para empleados.</span><span class="sxs-lookup"><span data-stu-id="f5343-114">Workers can enter skills for themselves in Employee self-service.</span></span> <span data-ttu-id="f5343-115">Estas habilidades requieren la aprobación del gerente.</span><span class="sxs-lookup"><span data-stu-id="f5343-115">These skills require manager approval.</span></span>
- <span data-ttu-id="f5343-116">Los gerentes pueden introducir aptitudes para sus trabajadores.</span><span class="sxs-lookup"><span data-stu-id="f5343-116">Managers can enter skills for their workers.</span></span> <span data-ttu-id="f5343-117">Puede crear un flujo de trabajo que apruebe automáticamente estas aptitudes.</span><span class="sxs-lookup"><span data-stu-id="f5343-117">You can create a workflow that auto-approves these skills.</span></span>

## <a name="create-a-skill-type"></a><span data-ttu-id="f5343-118">Crear un tipo de aptitud</span><span class="sxs-lookup"><span data-stu-id="f5343-118">Create a skill type</span></span>

<span data-ttu-id="f5343-119">Los tipos de aptitudes son categorías a las que pertenecen las aptitudes individuales, como Administración o Ventas.</span><span class="sxs-lookup"><span data-stu-id="f5343-119">Skill types are categories that individual skills fall under, such as Administration or Sales.</span></span>

1. <span data-ttu-id="f5343-120">En el espacio de trabajo **Desarrollo de empleado** seleccione **Enlaces**.</span><span class="sxs-lookup"><span data-stu-id="f5343-120">In the **Employee development** workspace, select **Links**.</span></span>

2. <span data-ttu-id="f5343-121">En **Configuración de competencias**, seleccione **Tipos de aptitudes**.</span><span class="sxs-lookup"><span data-stu-id="f5343-121">Under **Competency setup**, select **Skill types**.</span></span>

3. <span data-ttu-id="f5343-122">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f5343-122">Select **New**.</span></span>

4. <span data-ttu-id="f5343-123">Complete los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="f5343-123">Complete the following fields:</span></span>

   - <span data-ttu-id="f5343-124">**Tipo de aptitud**: escriba un nombre para el tipo de aptitud.</span><span class="sxs-lookup"><span data-stu-id="f5343-124">**Skill type**: Enter a name for the skill type.</span></span>
   - <span data-ttu-id="f5343-125">**Descripción**: escriba una descripción para el tipo de aptitud.</span><span class="sxs-lookup"><span data-stu-id="f5343-125">**Description**: Enter a description for the skill type.</span></span>

5. <span data-ttu-id="f5343-126">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f5343-126">Select **Save**.</span></span>

## <a name="create-a-rating-model"></a><span data-ttu-id="f5343-127">Crear un modelo de evaluación</span><span class="sxs-lookup"><span data-stu-id="f5343-127">Create a rating model</span></span>

<span data-ttu-id="f5343-128">Los modelos de evaluación ayudan a evaluar el nivel de aptitud real de una persona, el nivel que deben trabajar para lograr o el nivel de aptitud necesario para un puesto.</span><span class="sxs-lookup"><span data-stu-id="f5343-128">Rating models help evaluate a person's actual level of skill, the level they should work to achieve, or the level of skill required for a job.</span></span> <span data-ttu-id="f5343-129">Cada nivel del modelo de clasificación tiene asignado un factor.</span><span class="sxs-lookup"><span data-stu-id="f5343-129">Each level in a rating model is assigned a factor.</span></span>

1. <span data-ttu-id="f5343-130">En el espacio de trabajo **Desarrollo de empleado** seleccione **Enlaces**.</span><span class="sxs-lookup"><span data-stu-id="f5343-130">In the **Employee development** workspace, select **Links**.</span></span>

2. <span data-ttu-id="f5343-131">En **Configuración de competencias**, seleccione **Modelos de clasificación**.</span><span class="sxs-lookup"><span data-stu-id="f5343-131">Under **Competency setup**, select **Rating models**.</span></span>

3. <span data-ttu-id="f5343-132">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f5343-132">Select **New**.</span></span>

4. <span data-ttu-id="f5343-133">Complete los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="f5343-133">Complete the following fields:</span></span>

   - <span data-ttu-id="f5343-134">**Clasificación**: introduzca un nombre para el modelo de clasificación, como **Aptitudes**.</span><span class="sxs-lookup"><span data-stu-id="f5343-134">**Rating**: Enter a name for the rating model, such as **Skills**.</span></span>
   - <span data-ttu-id="f5343-135">**Descripción**: introduzca una descripción para el modelo de calificación, como **Calificaciones de aptitud**.</span><span class="sxs-lookup"><span data-stu-id="f5343-135">**Description**: Enter a description for the rating model, such as **Skill ratings**.</span></span>

5. <span data-ttu-id="f5343-136">En la sección **Niveles** sección, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f5343-136">In the **Levels** section, select **New**.</span></span> <span data-ttu-id="f5343-137">Para cada nivel que desee agregar, complete los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="f5343-137">For each level you want to add, complete the following fields:</span></span>

   - <span data-ttu-id="f5343-138">**Nivel**: escriba un nombre para el nivel.</span><span class="sxs-lookup"><span data-stu-id="f5343-138">**Level**: Enter a name for the level.</span></span>
   - <span data-ttu-id="f5343-139">**Descripción**: escriba una descripción del nivel.</span><span class="sxs-lookup"><span data-stu-id="f5343-139">**Description**: Enter a description for the level.</span></span>
   - <span data-ttu-id="f5343-140">**Factor**: introduzca un valor de factor de 0 a 9.</span><span class="sxs-lookup"><span data-stu-id="f5343-140">**Factor**: Enter a factor value from 0-9.</span></span> <span data-ttu-id="f5343-141">Los factores le ayudan a normalizar las puntuaciones de aptitudes que utilizan distintos modelos de evaluación.</span><span class="sxs-lookup"><span data-stu-id="f5343-141">Factors help normalize the scores of skills that use different rating models.</span></span> <span data-ttu-id="f5343-142">Cada nivel debe tener un factor único.</span><span class="sxs-lookup"><span data-stu-id="f5343-142">Each level must have a unique factor.</span></span> <span data-ttu-id="f5343-143">Los niveles con valores más altos de factor conllevan más peso en un modelo de evaluación.</span><span class="sxs-lookup"><span data-stu-id="f5343-143">Levels with higher factor values carry more weight in a rating model.</span></span>

   <span data-ttu-id="f5343-144">Continúe agregando niveles según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f5343-144">Continue adding levels as necessary.</span></span> <span data-ttu-id="f5343-145">Puede escribir hasta 10 niveles para cada modelo de evaluación.</span><span class="sxs-lookup"><span data-stu-id="f5343-145">You can enter up to 10 levels for each rating model.</span></span>

6. <span data-ttu-id="f5343-146">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f5343-146">Select **Save**.</span></span>

## <a name="create-a-skill"></a><span data-ttu-id="f5343-147">Crear una aptitud</span><span class="sxs-lookup"><span data-stu-id="f5343-147">Create a skill</span></span>

<span data-ttu-id="f5343-148">Antes de poder asignar una aptitud, crear una búsqueda de asignación de aptitudes o un perfil de aptitudes, debe especificar información sobre las aptitudes en la página **Aptitudes**.</span><span class="sxs-lookup"><span data-stu-id="f5343-148">Before you can assign a skill, or create a skill-mapping search or skill profile, you must enter information about the skills on the **Skills** page.</span></span> <span data-ttu-id="f5343-149">Para cada aptitud, puede seleccionar un tipo de aptitud y un modelo de evaluación.</span><span class="sxs-lookup"><span data-stu-id="f5343-149">For each skill, you can select a skill type and a rating model.</span></span>

1. <span data-ttu-id="f5343-150">En el espacio de trabajo **Desarrollo de empleado** seleccione **Enlaces**.</span><span class="sxs-lookup"><span data-stu-id="f5343-150">In the **Employee development** workspace, select **Links**.</span></span>

2. <span data-ttu-id="f5343-151">En **Configuración de competencias**, seleccione **Aptitudes**.</span><span class="sxs-lookup"><span data-stu-id="f5343-151">Under **Competency setup**, select **Skills**.</span></span>

3. <span data-ttu-id="f5343-152">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="f5343-152">Select **New**.</span></span>

4. <span data-ttu-id="f5343-153">Complete los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="f5343-153">Complete the following fields:</span></span>

   - <span data-ttu-id="f5343-154">**Aptitud**: escriba un nombre para la aptitud.</span><span class="sxs-lookup"><span data-stu-id="f5343-154">**Skill**: Enter a name for the skill.</span></span>
   - <span data-ttu-id="f5343-155">**Descripción**: escriba una descripción para la aptitud.</span><span class="sxs-lookup"><span data-stu-id="f5343-155">**Description**: Enter a description for the skill.</span></span>
   - <span data-ttu-id="f5343-156">**Valoración**: seleccione el modelo de valoración que quiere usar para esta aptitud.</span><span class="sxs-lookup"><span data-stu-id="f5343-156">**Rating**: Select the rating model you want to use for this skill.</span></span>
   - <span data-ttu-id="f5343-157">**Tipo de aptitud**: seccione de la lista de tipos de aptitudes.</span><span class="sxs-lookup"><span data-stu-id="f5343-157">**Skill type**: Select from the list of skill types.</span></span>

5. <span data-ttu-id="f5343-158">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="f5343-158">Select **Save**.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5343-159">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f5343-159">See also</span></span>

[<span data-ttu-id="f5343-160">Introducir aptitudes</span><span class="sxs-lookup"><span data-stu-id="f5343-160">Enter skills</span></span>](hr-develop-enter-skills.md)<br>
[<span data-ttu-id="f5343-161">Asignar aptitudes</span><span class="sxs-lookup"><span data-stu-id="f5343-161">Map skills</span></span>](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]