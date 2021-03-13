---
title: Mantener la información de lesiones y enfermedades del empleado
description: Se recomienda completar primero la guía de tareas "Configuración de lesión o enfermedad", puesto que aquí se usa parte de la información de configuración.
author: andreabichsel
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMInjuryIncident, HcmWorkerLookUp, HcmPersonnelManagementWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2ae5a14879a9e182f6f4604204f1cd6dd12576a3
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "5130118"
---
# <a name="maintain-employee-injury-and-illness-information"></a><span data-ttu-id="7efff-103">Mantener la información de lesiones y enfermedades del empleado</span><span class="sxs-lookup"><span data-stu-id="7efff-103">Maintain employee injury and illness information</span></span>



<span data-ttu-id="7efff-104">Se recomienda completar primero la guía de tareas "Configuración de lesión o enfermedad", puesto que aquí se usa parte de la información de configuración.</span><span class="sxs-lookup"><span data-stu-id="7efff-104">It is recommended to complete the 'Setup injury and illness' task guide first, as some of the setup information is used here.</span></span> 



<span data-ttu-id="7efff-105">Esta grabación de tareas cubre los pasos básicos para crear un caso de lesión o enfermedad.</span><span class="sxs-lookup"><span data-stu-id="7efff-105">This task recording covers the basic steps to creating an injury or illness case.</span></span> <span data-ttu-id="7efff-106">Además de realizar un seguimiento de los detalles de la lesión o enfermedad, hay un estado de caso del que se realiza también un seguimiento.</span><span class="sxs-lookup"><span data-stu-id="7efff-106">Besides tracking the details of the injury or illness, there is a case status that is tracked as well.</span></span>  <span data-ttu-id="7efff-107">El caso toma como predeterminado un estado "abierto".</span><span class="sxs-lookup"><span data-stu-id="7efff-107">The case defaults with an 'open' status.</span></span>  <span data-ttu-id="7efff-108">Los estados se pueden administrar desde el elemento de menú "Estado del caso" en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="7efff-108">The statuses can be managed from the 'Case status' menu item at the top of the page.</span></span>

1. <span data-ttu-id="7efff-109">Vaya a Recursos humanos > Trabajadores > Lesiones y enfermedades > Incidentes de lesiones o enfermedad.</span><span class="sxs-lookup"><span data-stu-id="7efff-109">Go to Human resources > Workers > Injury and illness > Injury or illness incidents.</span></span>
2. <span data-ttu-id="7efff-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="7efff-110">Click New.</span></span>
3. <span data-ttu-id="7efff-111">En el campo Descripción del caso, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7efff-111">In the Case description field, type a value.</span></span>
    * <span data-ttu-id="7efff-112">Ejemplo: Lesión de muñeca</span><span class="sxs-lookup"><span data-stu-id="7efff-112">Example:  Wrist injury</span></span>  
4. <span data-ttu-id="7efff-113">En el campo Trabajador, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="7efff-113">In the Worker field, enter or select a value.</span></span>
    * <span data-ttu-id="7efff-114">Ejemplo: Ahmed Barnett</span><span class="sxs-lookup"><span data-stu-id="7efff-114">Example: Ahmed Barnett</span></span>  
5. <span data-ttu-id="7efff-115">En el campo Fecha y hora del incidente, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="7efff-115">In the Date and time of incident field, enter a date and time.</span></span>
    * <span data-ttu-id="7efff-116">Ejemplo: 20/1/2016 10:00 a.m.</span><span class="sxs-lookup"><span data-stu-id="7efff-116">Example:  1/20/2016 10:00 AM</span></span>  
6. <span data-ttu-id="7efff-117">En el campo Tipo de lesión o enfermedad, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="7efff-117">In the Injury or illness type field, enter or select a value.</span></span>
    * <span data-ttu-id="7efff-118">Ejemplo: Fractura</span><span class="sxs-lookup"><span data-stu-id="7efff-118">Example:  Fracture</span></span>  
7. <span data-ttu-id="7efff-119">En el campo Parte del cuerpo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="7efff-119">In the Body part field, enter or select a value.</span></span>
    * <span data-ttu-id="7efff-120">Ejemplo: Muñeca</span><span class="sxs-lookup"><span data-stu-id="7efff-120">Example:  Wrist</span></span>  
8. <span data-ttu-id="7efff-121">En el campo Tipo de resultado, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="7efff-121">In the Outcome type field, enter or select a value.</span></span>
    * <span data-ttu-id="7efff-122">Ejemplo: Terapia</span><span class="sxs-lookup"><span data-stu-id="7efff-122">Example:  Therapy</span></span>  
9. <span data-ttu-id="7efff-123">En el campo Fecha y hora informadas, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="7efff-123">In the Date and time reported field, enter a date and time.</span></span>
    * <span data-ttu-id="7efff-124">La fecha y hora notificadas deben ser posteriores a la fecha y hora del incidente.</span><span class="sxs-lookup"><span data-stu-id="7efff-124">The date and time reported must be later than the date and time of incident.</span></span>  
10. <span data-ttu-id="7efff-125">En el campo Persona que informó del caso, escriba o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="7efff-125">In the Person who reported case field, enter or select a value.</span></span>
    * <span data-ttu-id="7efff-126">Podría ser el empleado u otro testigo del incidente.</span><span class="sxs-lookup"><span data-stu-id="7efff-126">This could be the employee or another witness to the incident.</span></span>  <span data-ttu-id="7efff-127">Ejemplo: Ahmed Barnett</span><span class="sxs-lookup"><span data-stu-id="7efff-127">Example: Ahmed Barnett</span></span>  
11. <span data-ttu-id="7efff-128">Expanda la sección Incidente.</span><span class="sxs-lookup"><span data-stu-id="7efff-128">Expand the Incident section.</span></span>
12. <span data-ttu-id="7efff-129">En el campo Lugar donde ocurrió el incidente, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7efff-129">In the Where incident occurred field, type a value.</span></span>
    * <span data-ttu-id="7efff-130">Ejemplo: Almacén</span><span class="sxs-lookup"><span data-stu-id="7efff-130">Example:  Warehouse</span></span>  
13. <span data-ttu-id="7efff-131">Seleccione Sí en el campo En el sitio de trabajo.</span><span class="sxs-lookup"><span data-stu-id="7efff-131">Select Yes in the On work premises field.</span></span>
    * <span data-ttu-id="7efff-132">Si el incidente se produjo en las instalaciones del sitio de trabajo, seleccione sí.</span><span class="sxs-lookup"><span data-stu-id="7efff-132">If the incident occurred on work premises, select yes.</span></span>  
14. <span data-ttu-id="7efff-133">En el campo Fecha y hora de inicio laboral, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="7efff-133">In the Date and time began work field, enter a date and time.</span></span>
    * <span data-ttu-id="7efff-134">Escriba la fecha y la hora en que el individuo afectado empezó a trabajar, antes de que se produjera el incidente.</span><span class="sxs-lookup"><span data-stu-id="7efff-134">Enter the date and time that affected individual started working, prior to the incident occurring.</span></span>  
15. <span data-ttu-id="7efff-135">En el campo Trabajo o tarea del empleado, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7efff-135">In the Employee job or task field, type a value.</span></span>
    * <span data-ttu-id="7efff-136">Especifique el trabajo o la tarea que el trabajador estaba realizando cuando se produjo el incidente.</span><span class="sxs-lookup"><span data-stu-id="7efff-136">Enter the job or task the worker was performing when the incident occurred.</span></span>  <span data-ttu-id="7efff-137">Ejemplo: Cargar cajas</span><span class="sxs-lookup"><span data-stu-id="7efff-137">Example:  Loading boxes</span></span>  
16. <span data-ttu-id="7efff-138">En el campo Causa del incidente, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7efff-138">In the Cause of incident field, type a value.</span></span>
    * <span data-ttu-id="7efff-139">Especifique la causa del incidente.</span><span class="sxs-lookup"><span data-stu-id="7efff-139">Enter the cause of the incident.</span></span>  <span data-ttu-id="7efff-140">Ejemplo: Se resbaló en suelo mojado</span><span class="sxs-lookup"><span data-stu-id="7efff-140">Example:  Slipped on wet floor</span></span>  
17. <span data-ttu-id="7efff-141">En el campo Nivel de gravedad, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="7efff-141">In the Severity level field, enter or select a value.</span></span>
18. <span data-ttu-id="7efff-142">En el campo Acción que debe realizarse, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7efff-142">In the Action to be taken field, type a value.</span></span>
    * <span data-ttu-id="7efff-143">Ejemplo: Limpiar pronto vertidos</span><span class="sxs-lookup"><span data-stu-id="7efff-143">Example:  Clean up spills promptly</span></span>  
19. <span data-ttu-id="7efff-144">En el campo Días previstos de ausencia laboral, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="7efff-144">In the Expected days away from work field, enter a number.</span></span>
    * <span data-ttu-id="7efff-145">Especifique el número de días en que está previsto que el trabajador se ausente del trabajo.</span><span class="sxs-lookup"><span data-stu-id="7efff-145">Enter the number of days that the individual is expected to be away from work.</span></span>  <span data-ttu-id="7efff-146">Una vez que el individuo vuelva al trabajo, actualice el campo "Días de ausencia laboral" con el número real de días que ha estado ausente.</span><span class="sxs-lookup"><span data-stu-id="7efff-146">Once the individual returns to work, update the 'Days away from work' field with the actual number of days away.</span></span>  
20. <span data-ttu-id="7efff-147">Expanda la sección Costes por lesión o enfermedad.</span><span class="sxs-lookup"><span data-stu-id="7efff-147">Expand the Injury or illness costs section.</span></span>
21. <span data-ttu-id="7efff-148">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="7efff-148">Click Add.</span></span>
22. <span data-ttu-id="7efff-149">En el campo Fecha, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="7efff-149">In the Date field, enter a date.</span></span>
23. <span data-ttu-id="7efff-150">En el campo Tipo de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="7efff-150">In the Cost type field, enter or select a value.</span></span>
    * <span data-ttu-id="7efff-151">Ejemplo: Tratamiento También puede especificar un importe y adjuntar cualquier documentación justificativa como facturas o notas del médico al coste.</span><span class="sxs-lookup"><span data-stu-id="7efff-151">Example:  Therapy    You can also enter in an amount, and attach any supporting documentation such as invoices or doctor's notes to the cost.</span></span>  
24. <span data-ttu-id="7efff-152">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="7efff-152">Click Add.</span></span>
25. <span data-ttu-id="7efff-153">En el campo Fecha, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="7efff-153">In the Date field, enter a date.</span></span>
26. <span data-ttu-id="7efff-154">En el campo Tipo de coste, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="7efff-154">In the Cost type field, enter or select a value.</span></span>
    * <span data-ttu-id="7efff-155">Ejemplo: Médico</span><span class="sxs-lookup"><span data-stu-id="7efff-155">Example: Doctor</span></span>  
27. <span data-ttu-id="7efff-156">Expanda la sección Tratamiento de lesiones o enfermedades.</span><span class="sxs-lookup"><span data-stu-id="7efff-156">Expand the Injury or illness treatments section.</span></span>
28. <span data-ttu-id="7efff-157">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="7efff-157">Click Add.</span></span>
29. <span data-ttu-id="7efff-158">En el campo Fecha de tratamiento, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="7efff-158">In the Treatment date field, enter a date and time.</span></span>
30. <span data-ttu-id="7efff-159">En el campo Tipo de tratamiento, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="7efff-159">In the Treatment type field, enter or select a value.</span></span>
    * <span data-ttu-id="7efff-160">Ejemplo: Tablilla</span><span class="sxs-lookup"><span data-stu-id="7efff-160">Example:  Splint</span></span>  
31. <span data-ttu-id="7efff-161">De manera opcional, establezca la sección Traslado a unidad de emergencias en Sí.</span><span class="sxs-lookup"><span data-stu-id="7efff-161">Optionally, set the emergency room hospital visit section to Yes.</span></span>
32. <span data-ttu-id="7efff-162">En el campo Comentarios sobre el tratamiento, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7efff-162">In the Treatment comments field, type a value.</span></span>
    * <span data-ttu-id="7efff-163">Ejemplo: Tablilla durante 2 semanas</span><span class="sxs-lookup"><span data-stu-id="7efff-163">Example:  Splint for 2 weeks</span></span>  
33. <span data-ttu-id="7efff-164">En el campo Nombre del médico, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7efff-164">In the Physician name field, type a value.</span></span>
    * <span data-ttu-id="7efff-165">Ejemplo: Dr. Anderson</span><span class="sxs-lookup"><span data-stu-id="7efff-165">Example:  Dr. Anderson</span></span>  
34. <span data-ttu-id="7efff-166">En el campo Centro de salud en el que se realiza el tratamiento y ubicación, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7efff-166">In the Treatment facility and location field, type a value.</span></span>
    * <span data-ttu-id="7efff-167">Ejemplo: Elm St. Emergency</span><span class="sxs-lookup"><span data-stu-id="7efff-167">Example:  Elm St. Emergency</span></span>  
35. <span data-ttu-id="7efff-168">En el campo Detalles del tratamiento, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="7efff-168">In the Treatment details field, type a value.</span></span>
    * <span data-ttu-id="7efff-169">Ejemplo: La radiografía confirma la fractura, llevar tablilla</span><span class="sxs-lookup"><span data-stu-id="7efff-169">Example:  Xray confirms fracture, wear splint</span></span>  
36. <span data-ttu-id="7efff-170">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="7efff-170">Click Save.</span></span>
    * <span data-ttu-id="7efff-171">El estado del caso se puede actualizar en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="7efff-171">The case status can be updated at any time.</span></span>  <span data-ttu-id="7efff-172">Establezca el caso en curso, si el procesamiento de la lesión o enfermedad está en curso.</span><span class="sxs-lookup"><span data-stu-id="7efff-172">Set the case to in process, if the processing of the injury or illness is in process.</span></span>  <span data-ttu-id="7efff-173">Una vez cierre el incidente, solo podrá agregar o quitar costes, tratamientos o archivos relacionados con el incidente.</span><span class="sxs-lookup"><span data-stu-id="7efff-173">Once you close the incident you can only add or remove costs, treatments or filings related to the incident.</span></span>  <span data-ttu-id="7efff-174">Para modificar otra información, vuelva a abrir el caso.</span><span class="sxs-lookup"><span data-stu-id="7efff-174">To modify other information, reopen the case.</span></span>  

