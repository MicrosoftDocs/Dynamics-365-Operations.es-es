---
title: Formalizar procesos empresariales
description: "La característica del proceso empresarial permite crear una plantilla del proceso empresarial para los procesos que necesiten completarse en la organización."
author: ShielaSogge
manager: AnnBe
ms.date: 01/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: PersonnelBusinessProcessGenericWorkspace, BusinessProcessGenericTemplateListpage, BusinessProcessGenericMyTemplates, BusinessProcessGroupAssignment
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: ShielaS
ms.search.validFrom: 2018-01-09
ms.dyn365.ops.version: AX 7.1.0, Talent October 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 1b50a97f5e2fc94255ff71702faf91ab36e68eb4
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---
# <a name="formalize-business-processes"></a><span data-ttu-id="ee879-103">Formalizar procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="ee879-103">Formalize business processes</span></span>
<span data-ttu-id="ee879-104">La característica del proceso empresarial permite crear una plantilla del proceso empresarial para los procesos que necesiten completarse en la organización.</span><span class="sxs-lookup"><span data-stu-id="ee879-104">The Business process feature allows you to create a business process template for processes that need to be completed within your organization.</span></span> <span data-ttu-id="ee879-105">Por ejemplo, la empresa puede completar una auditoría de RR. HH. de cada año.</span><span class="sxs-lookup"><span data-stu-id="ee879-105">For example, your company may complete an HR audit each year.</span></span> <span data-ttu-id="ee879-106">Una plantilla se puede crear para controlar todas las tareas que comprende la auditoría para ayudar a garantizar que todas las tareas se realizan cada vez que se completa el proceso y, si es necesario, para ayudar a garantizar que las tareas están efectuadas en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="ee879-106">A template can be created to track all the tasks that the audit comprises to help ensure that all the tasks are done each time the process is completed, and if necessary, to help ensure that tasks are performed in the correct order.</span></span> <span data-ttu-id="ee879-107">Las plantillas se pueden volver a utilizar para los procesos que se repiten o copiar para usarlas como punto de partida para crear nuevas tareas.</span><span class="sxs-lookup"><span data-stu-id="ee879-107">Templates can be re-used for recurring processes or copied to use as a starting point creating new ones.</span></span>

<span data-ttu-id="ee879-108">Una vez creada una plantilla, se puede iniciar un proceso y realizar un seguimiento en el espacio de trabajo del proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="ee879-108">After a template is created, a process can be started and tracked in the Business process workspace.</span></span>  <span data-ttu-id="ee879-109">Cuando se inicia un proceso empresarial, las tareas se asignan a las personas adecuadas e incluyen una fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="ee879-109">When a business process is started, the tasks will be assigned to the appropriate people and will include a due date.</span></span> <span data-ttu-id="ee879-110">Cubriremos estos componentes en detalle a continuación.</span><span class="sxs-lookup"><span data-stu-id="ee879-110">We will cover these components in detail below.</span></span>

## <a name="business-process-template"></a><span data-ttu-id="ee879-111">Plantilla de proceso empresarial</span><span class="sxs-lookup"><span data-stu-id="ee879-111">Business process template</span></span>
<span data-ttu-id="ee879-112">Una plantilla del proceso empresarial muestra un grupo de tareas que conforma un proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="ee879-112">A Business process template lists a group of tasks that make up a business process.</span></span> <span data-ttu-id="ee879-113">Los administradores de recursos humanos y los asistentes pueden crear procesos empresariales de forma predeterminada.</span><span class="sxs-lookup"><span data-stu-id="ee879-113">Human resource managers and assistants can create business processes by default.</span></span>  <span data-ttu-id="ee879-114">Sin embargo, esto se puede modificar en la configuración de seguridad editando el derecho Mantener los procesos empresariales genéricos.</span><span class="sxs-lookup"><span data-stu-id="ee879-114">However, this can be changed in the security configuration by editing the Maintain generic business processes duty.</span></span>

<span data-ttu-id="ee879-115">El propietario de proceso puede ser definido para cada proceso.</span><span class="sxs-lookup"><span data-stu-id="ee879-115">A Process owner can be defined for each process.</span></span> <span data-ttu-id="ee879-116">El propietario del proceso tendrá visibilidad en todas las tareas del proceso, y puede reasignar tareas o cambiar fechas de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="ee879-116">The process owner will have visibility into all the tasks for the process, and can re-assign tasks or change due dates.</span></span>  <span data-ttu-id="ee879-117">Por ejemplo, el director de RR. HH. ha podido crear una plantilla del proceso empresarial para una revisión de prestaciones.</span><span class="sxs-lookup"><span data-stu-id="ee879-117">For example, the HR director could create a Business process template for a benefits review.</span></span>  <span data-ttu-id="ee879-118">El administrador de COMP y de prestaciones se puede establecer como propietario de proceso, de modo que esta persona pueda tener penetración en las tareas que deben completarse como parte de la revisión.</span><span class="sxs-lookup"><span data-stu-id="ee879-118">The Comp and benefits manager can be set as the Process owner, so that he or she can have insight into the tasks that need to be completed as part of the review.</span></span>  <span data-ttu-id="ee879-119">El propietario de proceso no puede crear o eliminar los procesos empresariales activos o plantillas del proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="ee879-119">A Process owner cannot create or delete active Business processes or Business process templates.</span></span>

## <a name="task"></a><span data-ttu-id="ee879-120">Tarea</span><span class="sxs-lookup"><span data-stu-id="ee879-120">Task</span></span>
<span data-ttu-id="ee879-121">Un proceso empresarial comprende a menudo varias tareas.</span><span class="sxs-lookup"><span data-stu-id="ee879-121">A business process often comprises multiple tasks.</span></span> <span data-ttu-id="ee879-122">Algunas tareas se pueden completar en Dynamics 365 for Talent, por ejemplo revisar ofertas internas de curso.</span><span class="sxs-lookup"><span data-stu-id="ee879-122">Some tasks can be completed within Dynamics 365 for Talent, such as reviewing internal course offerings.</span></span> <span data-ttu-id="ee879-123">En esta instancia, se selecciona un elemento de menú en el campo de vínculo de la tarea.</span><span class="sxs-lookup"><span data-stu-id="ee879-123">In this instance, a Menu item is selected in the Task link field.</span></span> <span data-ttu-id="ee879-124">Otras tareas pueden implicar revisar o completar los formularios de un sitio web.</span><span class="sxs-lookup"><span data-stu-id="ee879-124">Other tasks might involve reviewing or completing forms on a web site.</span></span> <span data-ttu-id="ee879-125">La selección de dirección URL en el campo de vínculo de tarea permite especificar la dirección web.</span><span class="sxs-lookup"><span data-stu-id="ee879-125">Selecting URL in the Task link field enables the web address to be entered.</span></span> <span data-ttu-id="ee879-126">Puede especificar direcciones URL para sitios externos e internos en este campo.</span><span class="sxs-lookup"><span data-stu-id="ee879-126">You can enter URLs for both external and internal sites in this field.</span></span> <span data-ttu-id="ee879-127">También puede crear tareas para actividades que complete manualmente, por ejemplo revisar la accesibilidad de todas las estructuras.</span><span class="sxs-lookup"><span data-stu-id="ee879-127">You can also create tasks for activities that you complete manually, such as reviewing the accessibility of all structures.</span></span> <span data-ttu-id="ee879-128">En esta instancia no se requiere un vínculo de tarea.</span><span class="sxs-lookup"><span data-stu-id="ee879-128">In this instance a task link is not required.</span></span> <span data-ttu-id="ee879-129">Esta flexibilidad le permite realizar un seguimiento de varias clases de tareas en un proceso completo.</span><span class="sxs-lookup"><span data-stu-id="ee879-129">This flexibility lets you track multiple kinds of tasks in a comprehensive process.</span></span>

<span data-ttu-id="ee879-130">Las tareas se pueden asignar a un trabajador específico o a un puesto.</span><span class="sxs-lookup"><span data-stu-id="ee879-130">Tasks can be assigned to a specific worker or to a position.</span></span> <span data-ttu-id="ee879-131">Por ejemplo, el responsable de compensación y beneficios siempre será la persona que lleve a cabo una revisión de las primas de seguros.</span><span class="sxs-lookup"><span data-stu-id="ee879-131">For example, the Comp and benefits manager will always be the person that conducts a review of insurance premiums.</span></span>   <span data-ttu-id="ee879-132">Al realizar esta tarea, seleccione puesto para el tipo de asignación, y después seleccione el administrador de compensaciones y prestaciones en la lista del puesto.</span><span class="sxs-lookup"><span data-stu-id="ee879-132">When creating this task, select Position for the Assignment type, and then select Comp and benefit manager from the Position list.</span></span> <span data-ttu-id="ee879-133">Cuando se inicia el proceso, la tarea se asignará al trabajador que se encuentra en el puesto de administrador de compensaciones y prestaciones.</span><span class="sxs-lookup"><span data-stu-id="ee879-133">When the process starts, the task will be assigned to the worker who is in the Comp and benefits manager position.</span></span> <span data-ttu-id="ee879-134">También puede asignar una tarea a un trabajador específico seleccionando el trabajador en el campo de tipo de asignación, y a continuación, seleccionando a la persona adecuada.</span><span class="sxs-lookup"><span data-stu-id="ee879-134">You can also assign a task to a specific worker by selecting Worker in the Assignment type field, and then selecting the appropriate person.</span></span>

<span data-ttu-id="ee879-135">Las fechas de vencimiento de la tarea dependen de la fecha especificada fijada al comienzo del proceso.</span><span class="sxs-lookup"><span data-stu-id="ee879-135">Task due dates depend on the Target date entered at the start of the process.</span></span> <span data-ttu-id="ee879-136">Algunas tareas se deben terminar antes de la fecha fijada, y algunas podrían completarse después de la fecha fijada.</span><span class="sxs-lookup"><span data-stu-id="ee879-136">Some tasks must be completed before the target date, and some might be completed after the target date.</span></span>  <span data-ttu-id="ee879-137">Al definir una tarea, puede escribir una fecha de vencimiento que esté en relación con la fecha fijada en la contrapartida de la fecha de vencimiento del campo de la fecha fijada.</span><span class="sxs-lookup"><span data-stu-id="ee879-137">When defining a task, you will enter a due date that is relative to the target date in the Due date offset from target date field.</span></span> <span data-ttu-id="ee879-138">Por ejemplo, supongamos que responsable de compensación y beneficios debe realizar una revisión de las primas de seguros 10 días antes de que se complete la auditoría de RR. HH.</span><span class="sxs-lookup"><span data-stu-id="ee879-138">For example, assume that the Comp and benefits manager must perform a review of the insurance premiums 10 days before the HR audit is complete.</span></span> <span data-ttu-id="ee879-139">La tarea creada tendrá una fecha de vencimiento en relación con la fecha de vencimiento de -10.</span><span class="sxs-lookup"><span data-stu-id="ee879-139">The task created will have a due date relative to target date of -10.</span></span> <span data-ttu-id="ee879-140">Por lo tanto, si el proceso se inicia el 13 de mayo, la tarea vencerá el 3 de mayo.</span><span class="sxs-lookup"><span data-stu-id="ee879-140">Therefore, if the process is started on May 13th, the task will be due on May 3rd.</span></span> <span data-ttu-id="ee879-141">Nota: Las fechas de vencimiento también pueden ser ajustadas después de iniciarse el proceso.</span><span class="sxs-lookup"><span data-stu-id="ee879-141">Note: Due dates can also be adjusted after the process is started.</span></span>

<span data-ttu-id="ee879-142">Las tareas complejas pueden requerir varios pasos o necesitar que la persona que realiza las tareas proporcione información adicional.</span><span class="sxs-lookup"><span data-stu-id="ee879-142">Complex tasks might require multiple steps, or need the individual performing the tasks to provide additional information.</span></span> <span data-ttu-id="ee879-143">Puede agregar instrucciones a la tarea, e incruir formato de texto enriquecido para las instrucciones, también.</span><span class="sxs-lookup"><span data-stu-id="ee879-143">You can add Instructions to the task, and include rich text formatting for the instructions, as well.</span></span> <span data-ttu-id="ee879-144">Las directrices pueden proporcionar información adicional sobre cómo completar la tarea a la persona a la que se ha asignado su ejecución.</span><span class="sxs-lookup"><span data-stu-id="ee879-144">The instructions can provide additional information on how to complete the task to the person who is assigned to complete it.</span></span>

## <a name="starting-a-process"></a><span data-ttu-id="ee879-145">Iniciar un proceso</span><span class="sxs-lookup"><span data-stu-id="ee879-145">Starting a process</span></span>
<span data-ttu-id="ee879-146">Un proceso se puede iniciar dentro de una plantilla del proceso empresarial seleccionando Iniciar proceso.</span><span class="sxs-lookup"><span data-stu-id="ee879-146">A process can be started within a Business process template by selecting Start process.</span></span>  <span data-ttu-id="ee879-147">Cuando se inicia un proceso, se crearán tareas para los trabajadores y/o puestos seleccionados definidos en las tareas que se incluyen en la plantilla del proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="ee879-147">When a process is started, tasks will be created for the selected workers and/or positions defined in the tasks that are included in the Business process template.</span></span> <span data-ttu-id="ee879-148">Una fecha de vencimiento también se asignará a cada tarea agregando o restando los días compensados a partir de la fecha fijada (consulte la información relacionada con días compensados en la sección de la tarea).</span><span class="sxs-lookup"><span data-stu-id="ee879-148">A due date will also be assigned to each task by adding or subtracting the offset days from the target date (see the information regarding offset days in the task section).</span></span> <span data-ttu-id="ee879-149">Los procesos empresariales activos se pueden ver en el espacio de trabajo de los procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="ee879-149">The active Business processes can be viewed in the Business processes workspace.</span></span> 

## <a name="employee-self-service"></a><span data-ttu-id="ee879-150">Autoservicio para empleados</span><span class="sxs-lookup"><span data-stu-id="ee879-150">Employee self-service</span></span>
<span data-ttu-id="ee879-151">Cuando una tarea se asigna a un empleado, sus tareas asignadas se pueden ver en la página de autoservicio de empleado.</span><span class="sxs-lookup"><span data-stu-id="ee879-151">When a task is assigned to an employee, their assigned tasks can be viewed on the Employee self service page.</span></span> <span data-ttu-id="ee879-152">Los empleados que tienen asignada una tarea del proceso empresarial pueden consultar la tarea, su descripción, las instrucciones para completarla y el nombre de una persona de contacto y pueden abrir la página Dynamics365 o la página Web asociada desde su página de Autoservicio para empleados.</span><span class="sxs-lookup"><span data-stu-id="ee879-152">Employees who have a business process task assigned to them can see the task, its description, instructions for completing it, and the name of a contact person, and they can open the associated Dynamics365 page or web page, from their Employee self-service page.</span></span> <span data-ttu-id="ee879-153">Las tareas se pueden marcar como en curso, canceladas o completadas.</span><span class="sxs-lookup"><span data-stu-id="ee879-153">Tasks can be marked as in-progress, canceled or completed.</span></span>

## <a name="business-process-workspace"></a><span data-ttu-id="ee879-154">Espacio de trabajo de proceso empresarial</span><span class="sxs-lookup"><span data-stu-id="ee879-154">Business Process Workspace</span></span>
<span data-ttu-id="ee879-155">Los profesionales de RR. HH. pueden ver los procesos empresariales activos desde el espacio de trabajo de los procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="ee879-155">HR professionals can view the active business processes from the Business process workspace.</span></span> <span data-ttu-id="ee879-156">El espacio de trabajo muestra todos los procesos activos y las tareas asociados entre sí.</span><span class="sxs-lookup"><span data-stu-id="ee879-156">The workspace lists all active processes and the tasks that are associated with each one.</span></span> <span data-ttu-id="ee879-157">La lista de tareas completas se puede filtrar por fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="ee879-157">The comprehensive task list can be filtered by due date.</span></span> <span data-ttu-id="ee879-158">La página también muestra tareas vencidas, así como tareas asignadas específicamente al profesional de recursos humanos.</span><span class="sxs-lookup"><span data-stu-id="ee879-158">The page also lists overdue tasks, and tasks specifically assigned to the HR professional.</span></span> <span data-ttu-id="ee879-159">También pueden actualizar el estado de todas las tareas y en caso necesario, vuelve a asignar tareas para ayudar a que siga avanzando el proceso empresarial general.</span><span class="sxs-lookup"><span data-stu-id="ee879-159">They can also update the status of all tasks and if necessary, reassign tasks to help keep the overall business process moving forward.</span></span>

## <a name="my-business-processes-workspace"></a><span data-ttu-id="ee879-160">Espacio de trabajo de mis procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="ee879-160">My Business Processes Workspace</span></span>
<span data-ttu-id="ee879-161">Los propietarios del proceso pueden ver los procesos de negocio activos que se les asignan desde el espacio de trabajo de mi proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="ee879-161">Process owners can view the active business processes that are assigned to them from the My Business Process workspace.</span></span> <span data-ttu-id="ee879-162">El espacio de trabajo muestra todos los procesos activos y las tareas asociadas propiedad de dicho usuario.</span><span class="sxs-lookup"><span data-stu-id="ee879-162">The workspace lists all active processes and associated tasks that that user owns.</span></span>  <span data-ttu-id="ee879-163">La lista de tareas completas se puede filtrar por fecha de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="ee879-163">The comprehensive task list can be filtered by due date.</span></span> <span data-ttu-id="ee879-164">La página también muestra las tareas asignadas específicamente al propietario de proceso.</span><span class="sxs-lookup"><span data-stu-id="ee879-164">The page also lists tasks specifically assigned to process owner.</span></span> <span data-ttu-id="ee879-165">El propietario de proceso también puede actualizar el estado de todas las tareas, así como reasignar cualquier tarea.</span><span class="sxs-lookup"><span data-stu-id="ee879-165">The process owner can also update the status of all tasks, as well as reassign any tasks.</span></span>

## <a name="navigating-business-processes"></a><span data-ttu-id="ee879-166">Navegando por los procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="ee879-166">Navigating Business Processes</span></span>
1. <span data-ttu-id="ee879-167">Para agregar una plantilla del proceso empresarial, desplácese a los vínculos de los procesos empresariales – gestión de los procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="ee879-167">To add a Business process template, navigate to Business processes- links – Business processes administration.</span></span>
   - <span data-ttu-id="ee879-168">a.</span><span class="sxs-lookup"><span data-stu-id="ee879-168">a.</span></span>   <span data-ttu-id="ee879-169">Nuevo creará una nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="ee879-169">New will create a new template.</span></span>
   - <span data-ttu-id="ee879-170">b.</span><span class="sxs-lookup"><span data-stu-id="ee879-170">b.</span></span>   <span data-ttu-id="ee879-171">La copia desde plantilla copiará la plantilla seleccionada a una nueva.</span><span class="sxs-lookup"><span data-stu-id="ee879-171">Copy from template will copy the selected template to a new one.</span></span>
   - <span data-ttu-id="ee879-172">c.</span><span class="sxs-lookup"><span data-stu-id="ee879-172">c.</span></span>   <span data-ttu-id="ee879-173">Iniciar el proceso comenzará el proceso empresarial seleccionado, asignará tareas y calculará las fechas de vencimiento.</span><span class="sxs-lookup"><span data-stu-id="ee879-173">Start process will start the selected business process, assign tasks, and calculate due dates.</span></span>  
2. <span data-ttu-id="ee879-174">Para ver procesos activo y tareas asociadas desplácese al espacio de trabajo de los procesos empresariales.</span><span class="sxs-lookup"><span data-stu-id="ee879-174">To view active processes and associated tasks navigate to the Business processes workspace.</span></span>
