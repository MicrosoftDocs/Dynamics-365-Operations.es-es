---
title: "Configuración de cursos de formación."
description: "Los administradores y directores de Recursos humanos pueden usar las características de los cursos para mantener información sobre la formación que se ofrece a los trabajadores."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: HcmCourseType, HcmCourseTypeGroup, HRMCourseTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 7532
ms.assetid: a6950c29-8b3e-45b2-9084-ddfb1317ffaa
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Talent July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 20d28e22e4e89d0d864a0cbeaadeb568e73e223e
ms.openlocfilehash: 0ab79e85872c19e30f24e182ea483687ecc0bc09
ms.contentlocale: es-es
ms.lasthandoff: 06/29/2017


---

# <a name="set-up-training-courses"></a><span data-ttu-id="a6107-103">Configuración de cursos de formación.</span><span class="sxs-lookup"><span data-stu-id="a6107-103">Set up training courses</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="a6107-104">Los administradores y directores de Recursos humanos pueden usar las características de los cursos para mantener información sobre la formación que se ofrece a los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="a6107-104">Human resources administrators and managers can use the courses features to maintain information about the training that's offered to workers.</span></span>

 <a name="set-up-prerequisites"></a><span data-ttu-id="a6107-105"> Requisitos previos de configuración</span><span class="sxs-lookup"><span data-stu-id="a6107-105">Set up prerequisites</span></span>
---------------------

<span data-ttu-id="a6107-106">La siguiente información es necesaria y debe estar configurada antes de crear cursos.</span><span class="sxs-lookup"><span data-stu-id="a6107-106">The following information is required and must be set up before you create courses.</span></span>
-   <span data-ttu-id="a6107-107">**Tipos de curso**</span><span class="sxs-lookup"><span data-stu-id="a6107-107">**Course types**</span></span>

<span data-ttu-id="a6107-108">La siguiente información es opcional que puede especificar para los cursos.</span><span class="sxs-lookup"><span data-stu-id="a6107-108">The following information is optional information that you can specify for courses.</span></span> <span data-ttu-id="a6107-109">Si sabe que se especificarán esta información para los cursos, debería configurar esta información antes de crear los registros del curso.</span><span class="sxs-lookup"><span data-stu-id="a6107-109">If you know that you will be entering this information for courses, you should set up this information before you create course records.</span></span>
-   <span data-ttu-id="a6107-110">**Grupos de aulas**</span><span class="sxs-lookup"><span data-stu-id="a6107-110">**Classroom groups**</span></span>
-   <span data-ttu-id="a6107-111">**Grupos del curso**</span><span class="sxs-lookup"><span data-stu-id="a6107-111">**Course groups**</span></span>
-   <span data-ttu-id="a6107-112">**Ubicaciones de los cursos**</span><span class="sxs-lookup"><span data-stu-id="a6107-112">**Course locations**</span></span>
-   <span data-ttu-id="a6107-113">**Aulas**</span><span class="sxs-lookup"><span data-stu-id="a6107-113">**Classrooms**</span></span>
-   <span data-ttu-id="a6107-114">**Instructores**</span><span class="sxs-lookup"><span data-stu-id="a6107-114">**Instructors**</span></span>

## <a name="course-types"></a><span data-ttu-id="a6107-115">Tipos de curso</span><span class="sxs-lookup"><span data-stu-id="a6107-115">Course types</span></span>
<span data-ttu-id="a6107-116">Puede usar tipos de curso para clasificar los cursos en función de su tipo, estructura o contenido.</span><span class="sxs-lookup"><span data-stu-id="a6107-116">You can use course types to categorize courses according to the structure or content of the course.</span></span> <span data-ttu-id="a6107-117">Puede crear tipos de cursos en la página **Tipos de curso**.</span><span class="sxs-lookup"><span data-stu-id="a6107-117">You can create course types on the **Course types** page.</span></span> <span data-ttu-id="a6107-118">Debe seleccionar un tipo de curso al crear el registro de un curso.</span><span class="sxs-lookup"><span data-stu-id="a6107-118">You must select a course type when you create a course record.</span></span>

## <a name="course-setup-type"></a><span data-ttu-id="a6107-119">Tipo de configuración del curso</span><span class="sxs-lookup"><span data-stu-id="a6107-119">Course setup type</span></span>
<span data-ttu-id="a6107-120">En la tabla siguiente se muestran los tres tipos de configuración para los cursos.</span><span class="sxs-lookup"><span data-stu-id="a6107-120">The following table lists the three setup types for courses.</span></span> <span data-ttu-id="a6107-121">Los tipos de configuración determinan la estructura del curso.</span><span class="sxs-lookup"><span data-stu-id="a6107-121">Setup types determine the structure of the course.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="a6107-122">Tipo de configuración</span><span class="sxs-lookup"><span data-stu-id="a6107-122">Setup type</span></span></th>
<th><span data-ttu-id="a6107-123">Descripción</span><span class="sxs-lookup"><span data-stu-id="a6107-123">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a6107-124"><strong>Estándar</strong></span><span class="sxs-lookup"><span data-stu-id="a6107-124"><strong>Standard</strong></span></span></td>
<td><span data-ttu-id="a6107-125">Seleccione este tipo para los cursos que no tendrán un programa diario.</span><span class="sxs-lookup"><span data-stu-id="a6107-125">Select this type for courses that will not have a daily agenda.</span></span> <span data-ttu-id="a6107-126">Este es el tipo de configuración predeterminado al crear un nuevo curso.</span><span class="sxs-lookup"><span data-stu-id="a6107-126">This is the default setup type when you create a new course.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a6107-127"><strong>Programa</strong></span><span class="sxs-lookup"><span data-stu-id="a6107-127"><strong>Agenda</strong></span></span></td>
<td><span data-ttu-id="a6107-128">Seleccione este tipo para planificar los detalles de cada día de un curso que tenga lugar durante varios días.</span><span class="sxs-lookup"><span data-stu-id="a6107-128">Select this type to plan the details of each day of a course that takes place over multiple days.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a6107-129"><strong>Agenda + sesión</strong></span><span class="sxs-lookup"><span data-stu-id="a6107-129"><strong>Agenda + session</strong></span></span></td>
<td><span data-ttu-id="a6107-130">Seleccione este tipo para los cursos más complejos.</span><span class="sxs-lookup"><span data-stu-id="a6107-130">Select this type for the more complex courses.</span></span> <span data-ttu-id="a6107-131">Por ejemplo, puede dividir el programa del curso en trayectorias y sesiones.</span><span class="sxs-lookup"><span data-stu-id="a6107-131">For example, you can divide the agenda for the course into tracks and sessions.</span></span>
<ul>
<li><span data-ttu-id="a6107-132"><strong>Trayectoria</strong>: las trayectorias son áreas temáticas específicas para un curso.</span><span class="sxs-lookup"><span data-stu-id="a6107-132"><strong>Track</strong> – Tracks are specific subject areas for a course.</span></span></li>
<li><span data-ttu-id="a6107-133"><strong>Sesiones</strong>: las sesiones dividen las trayectorias y ayudan a identificar procesos o técnicas específicos pertinentes para la trayectoria.</span><span class="sxs-lookup"><span data-stu-id="a6107-133"><strong>Sessions</strong> – Sessions divide up tracks and help identify specific processes or techniques that are relevant to the track.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="course-tasks"></a><span data-ttu-id="a6107-134">Tareas del curso</span><span class="sxs-lookup"><span data-stu-id="a6107-134">Course tasks</span></span>
<span data-ttu-id="a6107-135">Para cada curso, puede realizar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="a6107-135">For each course, you can complete the following tasks.</span></span>
-   <span data-ttu-id="a6107-136">Registrar participantes.</span><span class="sxs-lookup"><span data-stu-id="a6107-136">Register participants</span></span>
-   <span data-ttu-id="a6107-137">Especificar una fecha límite del registro.</span><span class="sxs-lookup"><span data-stu-id="a6107-137">Specify a registration deadline</span></span>
-   <span data-ttu-id="a6107-138">Definir el número mínimo y máximo de participantes.</span><span class="sxs-lookup"><span data-stu-id="a6107-138">Define the minimum and maximum number of participants</span></span>
-   <span data-ttu-id="a6107-139">Asignar una ubicación y un aula para el curso.</span><span class="sxs-lookup"><span data-stu-id="a6107-139">Assign a course location and classroom</span></span>
-   <span data-ttu-id="a6107-140">Recomendar hoteles a los participantes en el curso.</span><span class="sxs-lookup"><span data-stu-id="a6107-140">Recommend hotels to course participants</span></span>
-   <span data-ttu-id="a6107-141">Crear una descripción del curso que puede anunciar en Autoservicio para empleados.</span><span class="sxs-lookup"><span data-stu-id="a6107-141">Create a course description, which you can then advertise on Employee self service</span></span>

  ><span data-ttu-id="a6107-142">**Nota** Solo puede eliminar un curso solo si nadie se ha registrado.</span><span class="sxs-lookup"><span data-stu-id="a6107-142">**Note** You can delete a course only if no one has registered for it.</span></span> 
    
## <a name="course-statuses"></a><span data-ttu-id="a6107-143">Estados del curso</span><span class="sxs-lookup"><span data-stu-id="a6107-143">Course statuses</span></span>
<span data-ttu-id="a6107-144">En la tabla siguiente se muestran los estados posibles del curso y las acciones que puede realizar cuando el curso tiene un estado concreto.</span><span class="sxs-lookup"><span data-stu-id="a6107-144">The following table lists the possible course statuses and the actions that you can complete when the course has a specific status.</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="a6107-145">Estado</span><span class="sxs-lookup"><span data-stu-id="a6107-145">Status</span></span></th>
<th><span data-ttu-id="a6107-146">Acciones</span><span class="sxs-lookup"><span data-stu-id="a6107-146">Actions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a6107-147"><strong>Creado</strong></span><span class="sxs-lookup"><span data-stu-id="a6107-147"><strong>Created</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="a6107-148">Especificar y modificar la información del curso.</span><span class="sxs-lookup"><span data-stu-id="a6107-148">Enter and modify course information.</span></span></li>
<li><span data-ttu-id="a6107-149">Cambie el estado del curso a <strong>Abierto</strong> de modo que los trabajadores puedan registrarse en él.</span><span class="sxs-lookup"><span data-stu-id="a6107-149">Change the course status to <strong>Open</strong> so that workers can register for the course.</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a6107-150"><strong>Abrir</strong></span><span class="sxs-lookup"><span data-stu-id="a6107-150"><strong>Open</strong></span></span></td>
<td><ul>
<li><span data-ttu-id="a6107-151">Registrar participantes en el curso.</span><span class="sxs-lookup"><span data-stu-id="a6107-151">Register participants for the course.</span></span></li>
<li><span data-ttu-id="a6107-152">Quitar participantes del curso.</span><span class="sxs-lookup"><span data-stu-id="a6107-152">Remove participants from the course.</span></span></li>
<li><span data-ttu-id="a6107-153">Confirmar participantes en el curso.</span><span class="sxs-lookup"><span data-stu-id="a6107-153">Confirm participants for the course.</span></span></li>
<li><span data-ttu-id="a6107-154">Cambiar el estado del curso a<strong> Cerrado</strong> o <strong>Cancelado</strong>.</span><span class="sxs-lookup"><span data-stu-id="a6107-154">Change the course status to <strong>Closed</strong> or <strong>Canceled</strong>.</span></span></li>
<li><span data-ttu-id="a6107-155">Planificar cuestionarios para participantes cuyo estado sea <strong>Confirmado</strong>.</span><span class="sxs-lookup"><span data-stu-id="a6107-155">Plan questionnaires for participants whose status is <strong>Confirmed</strong>.</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="a6107-156"><strong>Cerrado</strong></span><span class="sxs-lookup"><span data-stu-id="a6107-156"><strong>Closed</strong></span></span></td>
<td><span data-ttu-id="a6107-157">Puede volver a abrir el curso.</span><span class="sxs-lookup"><span data-stu-id="a6107-157">You can reopen the course.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="a6107-158"><strong>Cancelado</strong></span><span class="sxs-lookup"><span data-stu-id="a6107-158"><strong>Canceled</strong></span></span></td>
<td><span data-ttu-id="a6107-159">Puede volver a abrir el curso.</span><span class="sxs-lookup"><span data-stu-id="a6107-159">You can reopen the course.</span></span></td>
</tr>
</tbody>
</table>

## <a name="course-participants"></a><span data-ttu-id="a6107-160">Participantes en el curso</span><span class="sxs-lookup"><span data-stu-id="a6107-160">Course participants</span></span>
<span data-ttu-id="a6107-161">Los participantes del curso son trabajadores, solicitantes o personas de contacto que participan en un evento o curso de aprendizaje.</span><span class="sxs-lookup"><span data-stu-id="a6107-161">Course participants are workers, applicants, or contact persons who participate in a training course or event.</span></span> <span data-ttu-id="a6107-162">Solo es posible registrar participantes para cursos abiertos.</span><span class="sxs-lookup"><span data-stu-id="a6107-162">You can only register participants for open courses.</span></span> <span data-ttu-id="a6107-163">El número mínimo y máximo de participantes que se pueden registrar para un curso se define en la ficha desplegable **General** en la página **Cursos**.</span><span class="sxs-lookup"><span data-stu-id="a6107-163">The minimum and maximum number of participants that you can register for a course is defined on the **General** FastTab on the **Courses** page.</span></span>

<a name="workflow"></a><span data-ttu-id="a6107-164">Flujo de trabajo</span><span class="sxs-lookup"><span data-stu-id="a6107-164">Workflow</span></span>
--------

<span data-ttu-id="a6107-165">Los empleados que se registran para un curso por medio de la página **Autoservicio del empleado** pueden dirigir su registro a través del flujo de trabajo para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="a6107-165">Employees who register for a course through the **Employee self service** page can have their registration routed through workflow for approval.</span></span>  <span data-ttu-id="a6107-166">Se puede asignar un flujo de trabajo a un curso en la ficha desplegable **General** de la página **Cursos**.</span><span class="sxs-lookup"><span data-stu-id="a6107-166">A workflow can be assigned to a course on the **General** FastTab on the **Courses** page.</span></span>






