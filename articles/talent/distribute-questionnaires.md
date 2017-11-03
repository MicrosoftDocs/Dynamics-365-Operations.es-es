---
title: Distribuir y completar un cuestionario
description: "En este tema se explica cómo distribuir los cuestionarios que diseña, de modo que estén disponibles para la persona o el grupo de personas que lo van a completar."
author: kherr75
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KMConnectionType, KMKnowledgeCollectorPlanningTabel, SysEmailParameters
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations, Core
ms.custom: 17424
ms.assetid: fd8d867a-2446-400a-b91f-ad4085427470
ms.search.region: Global
ms.author: kherr75
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 97003c6e90db1fe1335deff65efe6b5ef07ae24b
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="distribute-and-complete-a-questionnaire"></a><span data-ttu-id="399d3-103">Distribuir y completar un cuestionario</span><span class="sxs-lookup"><span data-stu-id="399d3-103">Distribute and complete a questionnaire</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="399d3-104">En este tema se explica cómo distribuir los cuestionarios que diseña, de modo que estén disponibles para la persona o el grupo de personas que lo van a completar.</span><span class="sxs-lookup"><span data-stu-id="399d3-104">This topic explains how distribute the questionnaires that you design, so that they are available to the person or group of people who will complete them.</span></span> 

<span data-ttu-id="399d3-105">Hay varias manera de distribuir un cuestionario:</span><span class="sxs-lookup"><span data-stu-id="399d3-105">There are multiple ways to distribute a questionnaire:</span></span>

-   <span data-ttu-id="399d3-106">Marcar el cuestionario como activo.</span><span class="sxs-lookup"><span data-stu-id="399d3-106">Mark the questionnaire as active.</span></span> <span data-ttu-id="399d3-107">El cuestionario estará entonces disponible para todos los empleados, a menos que se configure un grupo de cuestionarios para restringir el acceso al mismo.</span><span class="sxs-lookup"><span data-stu-id="399d3-107">The questionnaire is then available to all employees, unless a questionnaire group is set up to restrict access to it.</span></span>
-   <span data-ttu-id="399d3-108">Asigne derechos a un grupo de cuestionarios.</span><span class="sxs-lookup"><span data-stu-id="399d3-108">Assign rights to a questionnaire group.</span></span> <span data-ttu-id="399d3-109">El cuestionario estará entonces disponible para todos los miembros del grupo seleccionado.</span><span class="sxs-lookup"><span data-stu-id="399d3-109">The questionnaire is then available to all members of the selected group.</span></span>
-   <span data-ttu-id="399d3-110">Crear sesiones de respuestas planificadas.</span><span class="sxs-lookup"><span data-stu-id="399d3-110">Create planned answer sessions.</span></span> <span data-ttu-id="399d3-111">El cuestionario está entonces disponible solo para una persona concreta.</span><span class="sxs-lookup"><span data-stu-id="399d3-111">The questionnaire is then available only to a particular person.</span></span>
-   <span data-ttu-id="399d3-112">Crear una programación.</span><span class="sxs-lookup"><span data-stu-id="399d3-112">Create a schedule.</span></span> <span data-ttu-id="399d3-113">El cuestionario estará entonces disponibles para varias personas.</span><span class="sxs-lookup"><span data-stu-id="399d3-113">The questionnaire can then be available to multiple people.</span></span>

## <a name="marking-a-questionnaire-as-active"></a><span data-ttu-id="399d3-114">Marcar un cuestionario como activo</span><span class="sxs-lookup"><span data-stu-id="399d3-114">Marking a questionnaire as active</span></span>
<span data-ttu-id="399d3-115">Al establecer el campo **Activo** en **Sí** en la página **Cuestionarios**, pone el cuestionario a disposición de todos los empleados para que lo completen.</span><span class="sxs-lookup"><span data-stu-id="399d3-115">By setting the **Active** field to **Yes** on the **Questionnaires** page, you make the questionnaire available for all employees to complete.</span></span> <span data-ttu-id="399d3-116">Los encuestados pueden completar el cuestionario varias veces.</span><span class="sxs-lookup"><span data-stu-id="399d3-116">Respondents can complete the questionnaire multiple times.</span></span> <span data-ttu-id="399d3-117">Esta función resulta útil si desea recopilar comentarios continuos a lo largo del año.</span><span class="sxs-lookup"><span data-stu-id="399d3-117">This functionality is useful if you want to gather continual feedback throughout the year.</span></span> <span data-ttu-id="399d3-118">Por ejemplo, puede crear un cuestionario que los empleados usen para dar comentario sobre el servicio de almuerzo en la cafetería.</span><span class="sxs-lookup"><span data-stu-id="399d3-118">For example, you can make a questionnaire that employees use to give feedback about the lunch service in the cafeteria.</span></span>

## <a name="questionnaire-groups"></a><span data-ttu-id="399d3-119">Grupos de cuestionarios</span><span class="sxs-lookup"><span data-stu-id="399d3-119">Questionnaire groups</span></span>
<span data-ttu-id="399d3-120">Puede configurar los grupos de cuestionarios e incluir a continuación a los encuestados a los que se debe distribuir un cuestionario.</span><span class="sxs-lookup"><span data-stu-id="399d3-120">You can set up questionnaire groups and then include the respondents that a questionnaire should be distributed to.</span></span> 

<span data-ttu-id="399d3-121">Puede crear grupos de cuestionarios a partir de las páginas siguientes:</span><span class="sxs-lookup"><span data-stu-id="399d3-121">You can create questionnaire groups from the following pages:</span></span>

-   <span data-ttu-id="399d3-122">**Grupos de cuestionarios**: solo las personas de un grupo de cuestionarios pueden completar un cuestionario seleccionado.</span><span class="sxs-lookup"><span data-stu-id="399d3-122">**Questionnaire groups** – Only individuals in a questionnaire group can complete a selected questionnaire.</span></span> <span data-ttu-id="399d3-123">Por ejemplo, su público de destino son contratistas, por lo que crea un grupo de cuestionarios que sea específico para dichos encuestados.</span><span class="sxs-lookup"><span data-stu-id="399d3-123">For example, your intended audience is contractors, so you create a questionnaire group that is specific to those respondents.</span></span>
-   <span data-ttu-id="399d3-124">**Miembros del grupo de cuestionarios**: puede agregar personas a grupos de cuestionarios.</span><span class="sxs-lookup"><span data-stu-id="399d3-124">**Questionnaire group members** – You can add people to the questionnaire groups.</span></span>

<span data-ttu-id="399d3-125">Para asignar un grupo de cuestionarios a un cuestionario, en la página **Cuestionarios**, haga clic en **Derechos del usuario**.</span><span class="sxs-lookup"><span data-stu-id="399d3-125">To assign a questionnaire group to a questionnaire, on the **Questionnaires** page, click **User rights**.</span></span> <span data-ttu-id="399d3-126">Una vez que se guarda el cuestionario como activo, los miembros del grupo de cuestionarios pueden completar el cuestionario.</span><span class="sxs-lookup"><span data-stu-id="399d3-126">After the questionnaire is saved as active, the members of the questionnaire group can complete the questionnaire.</span></span> <span data-ttu-id="399d3-127">Esta función resulta de utilidad si desea probar un cuestionario en un grupo seleccionado de personas antes de extenderlo a un grupo mayor, o si desea que el público de un cuestionario sea muy específico.</span><span class="sxs-lookup"><span data-stu-id="399d3-127">This functionality is helpful if you want to test a questionnaire on a select group of people before you roll it out to a larger group, or if you want to target a questionnaire to a very specific audience.</span></span>

## <a name="planned-answer-sessions-in-a-questionnaire"></a><span data-ttu-id="399d3-128">Sesión de respuestas planificadas en un cuestionario</span><span class="sxs-lookup"><span data-stu-id="399d3-128">Planned answer sessions in a questionnaire</span></span>
<span data-ttu-id="399d3-129">Las sesiones de respuesta planificadas son cuestionarios diseñados por usted y para las que ha seleccionado los encuestados.</span><span class="sxs-lookup"><span data-stu-id="399d3-129">Planned answer sessions are questionnaires that you've designed and selected the respondents for.</span></span> 

> <span data-ttu-id="399d3-130">**Nota:** Para poder configurar sesiones de respuesta planificadas, debe diseñar un cuestionario.</span><span class="sxs-lookup"><span data-stu-id="399d3-130">**Note** Before you can set up planned answer sessions, you must design a questionnaire.</span></span> 

<span data-ttu-id="399d3-131">En la página **Sesión de respuestas planificadas**, puede crear una sesión de respuestas planificadas para un empleado.</span><span class="sxs-lookup"><span data-stu-id="399d3-131">On the **Planned answer session** page, you can create a planned answer session for an individual employee.</span></span> <span data-ttu-id="399d3-132">La lista de la página muestra todos los cuestionarios planificados.</span><span class="sxs-lookup"><span data-stu-id="399d3-132">The list on the page displays all planned questionnaires.</span></span> 

<span data-ttu-id="399d3-133">Las sesiones de respuestas planificadas también se utilizan en la página **Programaciones de cuestionarios**, donde puede planificar cuestionarios para varias personas:</span><span class="sxs-lookup"><span data-stu-id="399d3-133">Planned answer sessions are also used on the **Questionnaire schedules** page, where you can plan questionnaires for multiple people:</span></span>

-   <span data-ttu-id="399d3-134">Empleados</span><span class="sxs-lookup"><span data-stu-id="399d3-134">Employees</span></span>
-   <span data-ttu-id="399d3-135">Participantes en el curso</span><span class="sxs-lookup"><span data-stu-id="399d3-135">Course participants</span></span>
-   <span data-ttu-id="399d3-136">Unidades organizativas</span><span class="sxs-lookup"><span data-stu-id="399d3-136">Organizational units</span></span>

<span data-ttu-id="399d3-137">Cada persona puede responder al cuestionario solo una vez.</span><span class="sxs-lookup"><span data-stu-id="399d3-137">Each person can answer the questionnaire only one time.</span></span>

## <a name="scheduling-a-questionnaire"></a><span data-ttu-id="399d3-138">Programación de un cuestionario</span><span class="sxs-lookup"><span data-stu-id="399d3-138">Scheduling a questionnaire</span></span>
<span data-ttu-id="399d3-139">Puede programar opcionalmente un cuestionario para varios encuestados.</span><span class="sxs-lookup"><span data-stu-id="399d3-139">You can optionally schedule a questionnaire for multiple respondents.</span></span>

### <a name="planning-types"></a><span data-ttu-id="399d3-140">Tipos de planificación</span><span class="sxs-lookup"><span data-stu-id="399d3-140">Planning types</span></span>

<span data-ttu-id="399d3-141">Los tipos de planificación son obligatorios si desea programar sesiones de respuesta planificadas para varios encuestados.</span><span class="sxs-lookup"><span data-stu-id="399d3-141">Planning types are required if you want to schedule planned answer sessions for multiple respondents.</span></span> <span data-ttu-id="399d3-142">Los tipos de planificación se usan para clasificar las programaciones de cuestionarios.</span><span class="sxs-lookup"><span data-stu-id="399d3-142">Planning types are used to classify questionnaire schedules.</span></span> <span data-ttu-id="399d3-143">Por ejemplo, puede programar cuestionarios para los fines siguientes:</span><span class="sxs-lookup"><span data-stu-id="399d3-143">For example, you can schedule questionnaires for the following purposes:</span></span>

-   <span data-ttu-id="399d3-144">Evaluación</span><span class="sxs-lookup"><span data-stu-id="399d3-144">Evaluation</span></span>
-   <span data-ttu-id="399d3-145">Encuesta</span><span class="sxs-lookup"><span data-stu-id="399d3-145">Survey</span></span>
-   <span data-ttu-id="399d3-146">Pruebas</span><span class="sxs-lookup"><span data-stu-id="399d3-146">Testing</span></span>

<span data-ttu-id="399d3-147">Puede especificar los tipos de planificación para una programación de cuestionarios en la página **Programaciones de cuestionarios**.</span><span class="sxs-lookup"><span data-stu-id="399d3-147">You can specify planning types for a questionnaire schedule on the **Questionnaire schedules** page.</span></span>

### <a name="reference-types-for-questionnaire"></a><span data-ttu-id="399d3-148">Tipos de referencia para cuestionario</span><span class="sxs-lookup"><span data-stu-id="399d3-148">Reference types for questionnaire</span></span>

<span data-ttu-id="399d3-149">Puede utilizar tipos de referencia para especificar los criterios para los encuestados que podría seleccionar al programar un cuestionario.</span><span class="sxs-lookup"><span data-stu-id="399d3-149">You can use reference types to enter criteria for the respondents that you might select when you schedule a questionnaire.</span></span> 

<span data-ttu-id="399d3-150">Use la página **Tipos de referencia** para configurar tipos de referencia para un cuestionario.</span><span class="sxs-lookup"><span data-stu-id="399d3-150">Use the **Reference types** page to set up reference types for a questionnaire.</span></span> <span data-ttu-id="399d3-151">Cada tipo de referencia se corresponde con una tabla de Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="399d3-151">Each reference type corresponds to a table in Microsoft Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="399d3-152">Al crear programaciones de cuestionarios, puede especificar los registros individuales en la tabla o un intervalo de registros con los que el cuestionario esté asociado.</span><span class="sxs-lookup"><span data-stu-id="399d3-152">When you create questionnaire schedules, you can specify individual records in the table or a range of records that the questionnaire will be associated with.</span></span> 

<span data-ttu-id="399d3-153">Por ejemplo, si selecciona la tabla Cursos, puede decidir para qué curso específico será el cuestionario.</span><span class="sxs-lookup"><span data-stu-id="399d3-153">For example, if you select the Courses table, you can decide which specific course the questionnaire will be for.</span></span> <span data-ttu-id="399d3-154">Al configurar un tipo de referencia para la tabla Cursos, algunos campos y botones de la página **Cursos** pueden hacerse disponibles.</span><span class="sxs-lookup"><span data-stu-id="399d3-154">When you set up a reference for the Courses table, some fields and buttons on the **Courses** page become available.</span></span>

### <a name="questionnaire-schedules"></a><span data-ttu-id="399d3-155">Programaciones de cuestionarios</span><span class="sxs-lookup"><span data-stu-id="399d3-155">Questionnaire schedules</span></span>

<span data-ttu-id="399d3-156">Puede usar programaciones del cuestionario para generar varias sesiones de respuesta planificadas para un grupo de usuarios, en función de un tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="399d3-156">You can use questionnaire schedules to generate multiple planned answer sessions for a group of users, based on a reference type.</span></span> <span data-ttu-id="399d3-157">Cree una programación en la página **Programaciones de cuestionarios**.</span><span class="sxs-lookup"><span data-stu-id="399d3-157">Create a schedule on the **Questionnaire schedules** page.</span></span> <span data-ttu-id="399d3-158">Seleccione el tipo de planificación para clasificar la programación, y también seleccionar el tipo de referencia que se debe usar para consultar el sistema para usuarios específicos.</span><span class="sxs-lookup"><span data-stu-id="399d3-158">Select the planning type to categorize the schedule, and also select the reference type that should be used to query the system for specific users.</span></span> <span data-ttu-id="399d3-159">Por ejemplo, si establece el tipo de referencia en la tabla Cursos, puede seleccionar un curso específico en el campo **Referencia**.</span><span class="sxs-lookup"><span data-stu-id="399d3-159">For example, if you set the reference type to the Courses table, you can select a specific course in the **Reference** field.</span></span> 

<span data-ttu-id="399d3-160">Haga clic en **Detalles de configuración** para seleccionar el cuestionario y otros criterios.</span><span class="sxs-lookup"><span data-stu-id="399d3-160">Click **Setup details** to select the questionnaire and other criteria.</span></span> <span data-ttu-id="399d3-161">Por ejemplo, especifique el nombre del instructor como criterio si el cuestionario es una evaluación del instructor.</span><span class="sxs-lookup"><span data-stu-id="399d3-161">For example, specify the instructor's name as a criterion if the questionnaire is an evaluation of the instructor.</span></span> <span data-ttu-id="399d3-162">Una vez que haya terminado de especificar los detalles de la configuración, el sistema genera sesiones de respuestas planificadas para los usuarios que se incluyen en la consulta.</span><span class="sxs-lookup"><span data-stu-id="399d3-162">After you've finished entering the setup details, the system generates planned answer sessions for the users that are included in the query.</span></span> 

<span data-ttu-id="399d3-163">Haga clic en **Sesiones de respuestas planificadas** para ver las sesiones de respuesta para la programación.</span><span class="sxs-lookup"><span data-stu-id="399d3-163">Click **Planned answer sessions** to view the answer sessions for the schedule.</span></span> <span data-ttu-id="399d3-164">A continuación, puede crear manualmente sesiones de respuestas planificadas adicionales o eliminar sesiones de respuestas planificadas que no se han respondido.</span><span class="sxs-lookup"><span data-stu-id="399d3-164">You can then manually create additional planned answer sessions or delete planned answer sessions that haven't been answered.</span></span> 

<span data-ttu-id="399d3-165">Haga clic en **Funciones** &gt; **Iniciar** para que el cuestionario esté disponible para los usuarios en sesiones de respuestas planificadas relacionadas.</span><span class="sxs-lookup"><span data-stu-id="399d3-165">Click **Functions** &gt; **Start** to make the questionnaire available to the users in related planned answer sessions.</span></span> <span data-ttu-id="399d3-166">Haga clic en **Respuestas** para ver las respuestas completadas para el cuestionario.</span><span class="sxs-lookup"><span data-stu-id="399d3-166">Click **Answers** to view the completed responses to the questionnaire.</span></span> <span data-ttu-id="399d3-167">Puede copiar opcionalmente la configuración de la programación de cuestionarios, las sesiones de respuestas planificadas y las respuestas a una nueva programación de cuestionarios.</span><span class="sxs-lookup"><span data-stu-id="399d3-167">You can optionally copy the questionnaire schedule settings, planned answer sessions, and answers to a new questionnaire schedule.</span></span>

## <a name="notifying-respondents-about-questionnaires-that-are-available-to-them"></a><span data-ttu-id="399d3-168">Notificación de los encuestados sobre los cuestionarios que tienen a su disposición</span><span class="sxs-lookup"><span data-stu-id="399d3-168">Notifying respondents about questionnaires that are available to them</span></span>
<span data-ttu-id="399d3-169">Al distribuir un cuestionario, debe notificar a los encuestados que tienen los cuestionarios a su disposición.</span><span class="sxs-lookup"><span data-stu-id="399d3-169">When you distribute a questionnaire, you must notify respondents that questionnaires are available to them.</span></span> 

### <a name="notifying-respondents-about-a-planned-answer-session"></a><span data-ttu-id="399d3-170">Notificación de los encuestados acerca de una sesión de respuestas planificadas</span><span class="sxs-lookup"><span data-stu-id="399d3-170">Notifying respondents about a planned answer session</span></span>

<span data-ttu-id="399d3-171">Si usa una sesión de respuestas planificadas, debe notificar a la persona directamente, por ejemplo, por teléfono o correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="399d3-171">If you use a planned answer session, you must notify the person directly, such as by telephone or email.</span></span>

### <a name="notifying-respondents-about-a-scheduling"></a><span data-ttu-id="399d3-172">Notificación de los encuestados acerca de una programación</span><span class="sxs-lookup"><span data-stu-id="399d3-172">Notifying respondents about a scheduling</span></span>

<span data-ttu-id="399d3-173">Use la página **Programaciones de cuestionarios** para preparar y enviar correo electrónico a todos los encuestados asignados al cuestionario.</span><span class="sxs-lookup"><span data-stu-id="399d3-173">Use the **Questionnaire schedules** page to prepare and send email to all respondents who are assigned to the questionnaire.</span></span> <span data-ttu-id="399d3-174">Escriba el texto del correo electrónico en la pestaña **Correo electrónico del autoservicio del empleado**. Una vez iniciada la programación, haga clic en **Funciones** &gt; **Enviar correo electrónico** para generar y enviar mensajes de correo electrónico a los encuestados.</span><span class="sxs-lookup"><span data-stu-id="399d3-174">Enter the email text on the **E-mail for employee self service** tab. After the schedule has been started, click **Functions** &gt; **Send e-mail** to generate and send the email to the respondents.</span></span> <span data-ttu-id="399d3-175">A continuación, los encuestados pueden iniciar sesión en el sitio Web y completar el cuestionario.</span><span class="sxs-lookup"><span data-stu-id="399d3-175">Respondents can then sign in to the website and complete the questionnaire.</span></span> 

> <span data-ttu-id="399d3-176">**Nota:** Para poder usar la función de correo electrónico, el administrador de TI debe especificar la configuración de correo electrónico en la página **Parámetros del correo electrónico**.</span><span class="sxs-lookup"><span data-stu-id="399d3-176">**Note** Before you can use the email functionality, your IT administrator must enter the email settings on the **E-mail parameters** page.</span></span>

## <a name="ending-a-scheduled-questionnaire"></a><span data-ttu-id="399d3-177">Finalización de un cuestionario programado</span><span class="sxs-lookup"><span data-stu-id="399d3-177">Ending a scheduled questionnaire</span></span>
<span data-ttu-id="399d3-178">Puede finalizar un cuestionario programado una vez que todas las personas que respondan al mismo hayan completado las sesiones de preguntas que les hayan sido asignadas.</span><span class="sxs-lookup"><span data-stu-id="399d3-178">You can end a scheduled questionnaire after all respondents have completed their assigned answer sessions.</span></span> <span data-ttu-id="399d3-179">Cuando finaliza un cuestionario programado, no puede copiar su configuración en una programación nueva.</span><span class="sxs-lookup"><span data-stu-id="399d3-179">After a scheduled questionnaire is ended, you can't copy its settings to a new schedule.</span></span> 

> <span data-ttu-id="399d3-180">**Note:** Si uno o varios de los encuestados no han completado el cuestionario, pero aun así desea finalizar la programación, antes deberá eliminar a esos encuestados de la lista en la página **Sesión de respuestas planificadas**.</span><span class="sxs-lookup"><span data-stu-id="399d3-180">**Note** If one or more respondents haven't completed the questionnaire, but you still want to end the scheduling, you must first delete those respondents from the list on the **Planned answer session** page.</span></span> <span data-ttu-id="399d3-181">A continuación, puede finalizar la programación.</span><span class="sxs-lookup"><span data-stu-id="399d3-181">You can then end the schedule.</span></span>

## <a name="completing-questionnaires"></a><span data-ttu-id="399d3-182">Completando cuestionarios</span><span class="sxs-lookup"><span data-stu-id="399d3-182">Completing questionnaires</span></span>
<span data-ttu-id="399d3-183">Una vez que haya diseñado y haya distribuido un cuestionario, los encuestados seleccionados lo pueden completar.</span><span class="sxs-lookup"><span data-stu-id="399d3-183">After you've designed and distributed a questionnaire, the questionnaire can be completed by selected respondents.</span></span> <span data-ttu-id="399d3-184">Puede completar los cuestionarios a su disposición desde dos ubicaciones:</span><span class="sxs-lookup"><span data-stu-id="399d3-184">You can complete the questionnaires that are available to you from two locations:</span></span>

-   <span data-ttu-id="399d3-185">En el panel de navegación, haga clic en **Cuestionarios** &gt; **Distribuir** &gt; **Completar un cuestionario**.</span><span class="sxs-lookup"><span data-stu-id="399d3-185">In the navigation pane, click **Questionnaires** &gt; **Distribute** &gt; **Complete a questionnaire**.</span></span>
-   <span data-ttu-id="399d3-186">En Autoservicio para empleados, haga clic en **Cuestionarios que deben completarse**.</span><span class="sxs-lookup"><span data-stu-id="399d3-186">In Employee self-service, click **Questionnaires to complete**.</span></span>

<span data-ttu-id="399d3-187">Los cuestionarios se pueden poner a disposición de usuarios o grupos de usuarios específicos, o de todos los usuarios conectados a una red.</span><span class="sxs-lookup"><span data-stu-id="399d3-187">Questionnaires can made be available to specific users or groups of users, or to all users in a network.</span></span>

<a name="see-also"></a><span data-ttu-id="399d3-188">Consulte también</span><span class="sxs-lookup"><span data-stu-id="399d3-188">See also</span></span>
--------

[<span data-ttu-id="399d3-189">Diseñar cuestionarios</span><span class="sxs-lookup"><span data-stu-id="399d3-189">Designing questionnaires</span></span>](design-questionnaires.md)

[<span data-ttu-id="399d3-190">Uso de cuestionarios</span><span class="sxs-lookup"><span data-stu-id="399d3-190">Using questionnaires</span></span>](questionnaires.md)

[<span data-ttu-id="399d3-191">Visualización y evaluación de los resultados de cuestionarios</span><span class="sxs-lookup"><span data-stu-id="399d3-191">Viewing and evaluating the results of questionnaires</span></span>](evaluate-questionnaire-results.md)



