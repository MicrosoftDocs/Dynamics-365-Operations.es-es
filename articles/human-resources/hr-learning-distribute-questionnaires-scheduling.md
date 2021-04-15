---
title: Distribuir cuestionarios mediante la programación
description: La programación del cuestionario le permite planear y distribuir los cuestionarios a múltiples encuestados.
author: andreabichsel
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: KMKnowledgeCollectorPlanningTable, KMKnowledgeCollectorPlanningMulti, SysQueryForm, HcmPersonLookup, KMKnowledgeCollectorPlanning, HcmLearningWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8ddad70792c4ebc1785698812fe12406142f07a2
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5790629"
---
# <a name="distribute-questionnaires-using-scheduling"></a><span data-ttu-id="6605c-103">Distribuir cuestionarios mediante la programación</span><span class="sxs-lookup"><span data-stu-id="6605c-103">Distribute questionnaires using scheduling</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="6605c-104">La programación del cuestionario le permite planear y distribuir los cuestionarios a múltiples encuestados.</span><span class="sxs-lookup"><span data-stu-id="6605c-104">Questionnaire scheduling allows you to plan and distribute questionnaires to multiple respondents.</span></span> <span data-ttu-id="6605c-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="6605c-105">The demo data company used to create this procedure is USMF.</span></span>

## <a name="create-a-questionnaire-schedule"></a><span data-ttu-id="6605c-106">Cree una programación del cuestionario</span><span class="sxs-lookup"><span data-stu-id="6605c-106">Create a questionnaire schedule</span></span>

1. <span data-ttu-id="6605c-107">Vaya a Cuestionario > Distribuir > Programaciones de cuestionarios.</span><span class="sxs-lookup"><span data-stu-id="6605c-107">Go to Questionnaire > Distribute > Questionnaire schedules.</span></span>

2. <span data-ttu-id="6605c-108">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="6605c-108">Click New.</span></span>

3. <span data-ttu-id="6605c-109">En el campo Programación, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6605c-109">In the Scheduling field, type a value.</span></span>

4. <span data-ttu-id="6605c-110">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6605c-110">In the Description field, type a value.</span></span>
    * <span data-ttu-id="6605c-111">Defina la programación en anónima si las respuestas se debe registrar sin nombres asociados a la respuesta.</span><span class="sxs-lookup"><span data-stu-id="6605c-111">Set the schedule to Anonymous if the responses should be recorded without names associated to the response.</span></span>  
    * <span data-ttu-id="6605c-112">Permitir resultados anónimos se debe configurar primero en los parámetros de RR. HH.</span><span class="sxs-lookup"><span data-stu-id="6605c-112">Allowing anonymous results must be set up in the HR parameters first.</span></span>  

5. <span data-ttu-id="6605c-113">En el campo Tipo, seleccione el tipo de planificación.</span><span class="sxs-lookup"><span data-stu-id="6605c-113">In the Type field, select the planning type.</span></span>  <span data-ttu-id="6605c-114">En este ejemplo utilizaremos el tipo de satisfacción.</span><span class="sxs-lookup"><span data-stu-id="6605c-114">In this example we will use the Satisfaction type.</span></span>

6. <span data-ttu-id="6605c-115">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="6605c-115">In the list, find and select the desired record.</span></span>

7. <span data-ttu-id="6605c-116">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="6605c-116">In the list, click the link in the selected row.</span></span>

8. <span data-ttu-id="6605c-117">En el campo Fecha, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="6605c-117">In the Date field, enter a date.</span></span>

9. <span data-ttu-id="6605c-118">Expanda la sección Correo electrónico para autoservicio de empleados.</span><span class="sxs-lookup"><span data-stu-id="6605c-118">Expand the Email for employee self service section.</span></span>

10. <span data-ttu-id="6605c-119">En el campo Asunto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="6605c-119">In the Subject field, type a value.</span></span>

    * <span data-ttu-id="6605c-120">Ejemplo: Cuestionario disponible</span><span class="sxs-lookup"><span data-stu-id="6605c-120">Example: Questionnaire available</span></span>  

11. <span data-ttu-id="6605c-121">Escriba el cuerpo de su mensaje de correo electrónico en el campo Texto.</span><span class="sxs-lookup"><span data-stu-id="6605c-121">In the Text field, type the body of your email message.</span></span> <span data-ttu-id="6605c-122">Tenga en cuenta que la variable se puede utilizar para sustituir los valores del sistema.</span><span class="sxs-lookup"><span data-stu-id="6605c-122">Note, the variable can be used to substitue values in the system.</span></span>

    * <span data-ttu-id="6605c-123">Ejemplo: Estimado/a %P%, inicie sesión en Autoservicio Empleado para completar el cuestionario Estados de salud de los trabajadores.</span><span class="sxs-lookup"><span data-stu-id="6605c-123">Example: Dear %P%, Please log in to Employee Self Service to complete the Workforce Health questionnaire.</span></span>  <span data-ttu-id="6605c-124">Contoso</span><span class="sxs-lookup"><span data-stu-id="6605c-124">Contoso</span></span>  

12. <span data-ttu-id="6605c-125">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="6605c-125">Click Save.</span></span>

## <a name="use-the-setup-details-to-select-the-questionnaires-to-be-answered-as-well-as-any-queries-to-use-to-select-respondents"></a><span data-ttu-id="6605c-126">Use los Detalles de configuración para seleccionar los cuestionarios que se responderán junto con cualquier consulta que se usará para seleccionar encuestados.</span><span class="sxs-lookup"><span data-stu-id="6605c-126">Use the Setup details to select the questionnaire(s) to be answered as well as any queries to use to select respondents.</span></span>

1. <span data-ttu-id="6605c-127">Haga clic en Detalles de configuración.</span><span class="sxs-lookup"><span data-stu-id="6605c-127">Click Setup details.</span></span>

2. <span data-ttu-id="6605c-128">En la lista, seleccione la consulta que desee usar para encontrar encuestados para el cuestionario en el sistema.</span><span class="sxs-lookup"><span data-stu-id="6605c-128">In the list, select a query to use to search the system for respondents for the questionnaire.</span></span>

    * <span data-ttu-id="6605c-129">Ejemplo: Trabajadores</span><span class="sxs-lookup"><span data-stu-id="6605c-129">Example: Workers</span></span>  

3. <span data-ttu-id="6605c-130">Haga clic en Ver o modificar consulta para seleccionar personas específicas o ajustar la consulta para buscar las personas que coinciden con criterios específicos.</span><span class="sxs-lookup"><span data-stu-id="6605c-130">Click View or modify query to select specific people or adjust the query to find people who match specific criteria.</span></span>

    * <span data-ttu-id="6605c-131">Tenga en cuenta que todos los encuestados también deben ser usuarios en el sistema.</span><span class="sxs-lookup"><span data-stu-id="6605c-131">Note that all respondents must also be users in the system.</span></span>  

4. <span data-ttu-id="6605c-132">En la lista, marque la fila por persona.</span><span class="sxs-lookup"><span data-stu-id="6605c-132">In the list, mark the row for Person</span></span>

5. <span data-ttu-id="6605c-133">En el campo Criterios, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="6605c-133">In the Criteria field, enter or select a value.</span></span>

    * <span data-ttu-id="6605c-134">Seleccione Julia Funderburk</span><span class="sxs-lookup"><span data-stu-id="6605c-134">Select Julia Funderburk</span></span>  

6. <span data-ttu-id="6605c-135">Seleccione Julia Funderburk en la lista.</span><span class="sxs-lookup"><span data-stu-id="6605c-135">In the list, select Julia Funderburk</span></span>

7. <span data-ttu-id="6605c-136">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="6605c-136">Click OK.</span></span>

8. <span data-ttu-id="6605c-137">Haga clic en la ficha Cuestionarios.</span><span class="sxs-lookup"><span data-stu-id="6605c-137">Click the Questionnaires tab.</span></span>

9. <span data-ttu-id="6605c-138">En el árbol, expanda "el nodo para el tipo de cuestionario de la encuesta de satisfacción".</span><span class="sxs-lookup"><span data-stu-id="6605c-138">In the tree, expand 'the node for the questionnaire type Satisfaction Survey'.</span></span>

10. <span data-ttu-id="6605c-139">En el árbol, compruebe "Evaluación del estado de salud de los trabajadores".</span><span class="sxs-lookup"><span data-stu-id="6605c-139">In the tree, check 'Workforce Health Assessment'.</span></span>

11. <span data-ttu-id="6605c-140">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="6605c-140">Click OK.</span></span>

12. <span data-ttu-id="6605c-141">Haga clic en Sesión de respuestas planificadas.</span><span class="sxs-lookup"><span data-stu-id="6605c-141">Click Planned answer session.</span></span>

    * <span data-ttu-id="6605c-142">Tenga en cuenta que se han creado sesiones de respuestas planificadas para cada usuario seleccionado o consultado.</span><span class="sxs-lookup"><span data-stu-id="6605c-142">Note that Planned answer sessions have been created for each selected/queried user.</span></span>  

13. <span data-ttu-id="6605c-143">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6605c-143">Close the page.</span></span>

## <a name="start-the-questionnaire-schedule-in-order-to-make-the-questionnaire-available-for-respondents-to-complete"></a><span data-ttu-id="6605c-144">Inicie la programación de cuestionario para que el cuestionario esté disponible para que lo completen los encuestados.</span><span class="sxs-lookup"><span data-stu-id="6605c-144">Start the questionnaire schedule in order to make the questionnaire available for respondents to complete.</span></span>

1. <span data-ttu-id="6605c-145">Haga clic en Funciones.</span><span class="sxs-lookup"><span data-stu-id="6605c-145">Click Functions.</span></span>

2. <span data-ttu-id="6605c-146">Haga clic en Inicio.</span><span class="sxs-lookup"><span data-stu-id="6605c-146">Click Start.</span></span>

3. <span data-ttu-id="6605c-147">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="6605c-147">Click OK.</span></span>

## <a name="send-the-email-to-inform-respondents-of-the-available-questionnaire"></a><span data-ttu-id="6605c-148">Envíe el mensaje de correo electrónico para informar a los encuestados del cuestionario disponible.</span><span class="sxs-lookup"><span data-stu-id="6605c-148">Send the email to inform respondents of the available questionnaire.</span></span>

1. <span data-ttu-id="6605c-149">Haga clic en Funciones.</span><span class="sxs-lookup"><span data-stu-id="6605c-149">Click Functions.</span></span>

2. <span data-ttu-id="6605c-150">Haga clic en Enviar correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6605c-150">Click Send email.</span></span>

3. <span data-ttu-id="6605c-151">Haga clic en Cancelar.</span><span class="sxs-lookup"><span data-stu-id="6605c-151">Click Cancel.</span></span>

## <a name="use-planned-answer-sessions-to-monitor-who-needs-to-complete-the-questionnaire"></a><span data-ttu-id="6605c-152">Use las sesiones de respuesta planificadas para supervisar quién debe completar el cuestionario.</span><span class="sxs-lookup"><span data-stu-id="6605c-152">Use Planned answer sessions to monitor who needs to complete the questionnaire.</span></span>

1. <span data-ttu-id="6605c-153">Haga clic en Sesión de respuestas planificadas.</span><span class="sxs-lookup"><span data-stu-id="6605c-153">Click Planned answer session.</span></span>

    * <span data-ttu-id="6605c-154">Elimine cualquier sesión de respuestas planificadas restante cuando esté listo para finalizar la sesión programada.</span><span class="sxs-lookup"><span data-stu-id="6605c-154">Delete any remaining planned answer session when you're ready to end the scheduled session.</span></span>  

2. <span data-ttu-id="6605c-155">Haga clic Eliminar.</span><span class="sxs-lookup"><span data-stu-id="6605c-155">Click Delete.</span></span>

3. <span data-ttu-id="6605c-156">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="6605c-156">Click Yes.</span></span>

4. <span data-ttu-id="6605c-157">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="6605c-157">Close the page.</span></span>

## <a name="end-the-schedule-when-all-respondents-have-completed-the-questionnaire-andor-all-remaining-planned-answer-sessions-have-been-deleted"></a><span data-ttu-id="6605c-158">Finalice la programación cuando todos los encuestados hayan completado el cuestionario y/o se hayan eliminado todas las sesiones de respuestas planificadas restantes.</span><span class="sxs-lookup"><span data-stu-id="6605c-158">End the schedule when all respondents have completed the questionnaire and/or all remaining Planned answer sessions have been deleted.</span></span>

1. <span data-ttu-id="6605c-159">Haga clic en Funciones.</span><span class="sxs-lookup"><span data-stu-id="6605c-159">Click Functions.</span></span>
2. <span data-ttu-id="6605c-160">Haga clic en Fin.</span><span class="sxs-lookup"><span data-stu-id="6605c-160">Click End.</span></span>
3. <span data-ttu-id="6605c-161">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="6605c-161">Click OK.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]