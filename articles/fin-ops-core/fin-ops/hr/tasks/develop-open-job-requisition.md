---
title: Desarrollar y abrir solicitudes de trabajo
description: Los proyectos de contratación ayudan a gestionar el proceso de contratación.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMRecruitingTable, HcmWorkerLookUp, HcmJobLookup, HRMRecruitingMedia, HRMRecruitingJobAd
audience: Application User
ms.reviewer: anbichse
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d23f180c1afcfa6d24c0b44f69fba9b40c114e1b
ms.sourcegitcommit: 6cb174d1ec8b55946dca4db03d6a3c3f4c6fa2df
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/09/2021
ms.locfileid: "5564660"
---
# <a name="develop-and-open-job-requisition"></a><span data-ttu-id="d25ed-103">Desarrollar y abrir solicitudes de trabajo</span><span class="sxs-lookup"><span data-stu-id="d25ed-103">Develop and open job requisition</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d25ed-104">Los proyectos de contratación ayudan a gestionar el proceso de contratación.</span><span class="sxs-lookup"><span data-stu-id="d25ed-104">Recruitment projects help manage the recruiting process.</span></span> <span data-ttu-id="d25ed-105">Se puede configurar la información de cada proyecto de contratación, como el trabajo para el que se está contratando personal, el nombre de la persona a cargo de la contratación, el estado del proyecto y el departamento en el cual se realizará el trabajo en cuestión.</span><span class="sxs-lookup"><span data-stu-id="d25ed-105">For each recruitment project, you can set up information, such as the job that recruiting is for, the name of the recruiter, the status of the project and the department that the job will be located in.</span></span> <span data-ttu-id="d25ed-106">Tras crear un proyecto de contratación, puede escribir un anuncio de trabajo para el proyecto, publicarlo en las páginas de autoservicio del empleado, asociar solicitudes de empleo con el proyecto y realizar un seguimiento de las actividades del proyecto.</span><span class="sxs-lookup"><span data-stu-id="d25ed-106">After creating a recruitment project, you can write a job advertisement for the project, publish the ad on Employee self-service pages, associate applications for employment with the project, and track activities for that project.</span></span> <span data-ttu-id="d25ed-107">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="d25ed-107">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="d25ed-108">Para iniciar el procedimiento, vaya a Recursos humanos > Contratación > Proyectos de contratación > Proyectos de contratación</span><span class="sxs-lookup"><span data-stu-id="d25ed-108">To begin the procedure, go to Human resources > Recruitment > Recruitment projects > Recruitment projects</span></span>

1. <span data-ttu-id="d25ed-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d25ed-109">Click New.</span></span>
2. <span data-ttu-id="d25ed-110">En el campo Proyecto de contratación, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d25ed-110">In the Recruitment project field, type a value.</span></span>
3. <span data-ttu-id="d25ed-111">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="d25ed-111">In the Description field, type a value.</span></span>
4. <span data-ttu-id="d25ed-112">En el campo Contratante, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d25ed-112">In the Recruiter field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="d25ed-113">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d25ed-113">In the list, find and select the desired record.</span></span>
6. <span data-ttu-id="d25ed-114">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d25ed-114">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="d25ed-115">Haga clic en Seleccionar.</span><span class="sxs-lookup"><span data-stu-id="d25ed-115">Click Select.</span></span>
8. <span data-ttu-id="d25ed-116">En el campo Departamento, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d25ed-116">In the Department field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="d25ed-117">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d25ed-117">In the list, click the link in the selected row.</span></span>
10. <span data-ttu-id="d25ed-118">En el campo Trabajo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d25ed-118">In the Job field, click the drop-down button to open the lookup.</span></span>
11. <span data-ttu-id="d25ed-119">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d25ed-119">In the list, find and select the desired record.</span></span>
12. <span data-ttu-id="d25ed-120">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d25ed-120">In the list, click the link in the selected row.</span></span>
13. <span data-ttu-id="d25ed-121">En el campo Número de vacantes, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="d25ed-121">In the Number of openings field, enter a number.</span></span>
14. <span data-ttu-id="d25ed-122">En el campo Jefe de contratación, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d25ed-122">In the Hiring manager field, click the drop-down button to open the lookup.</span></span>
15. <span data-ttu-id="d25ed-123">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d25ed-123">In the list, find and select the desired record.</span></span>
16. <span data-ttu-id="d25ed-124">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d25ed-124">In the list, click the link in the selected row.</span></span>
17. <span data-ttu-id="d25ed-125">Haga clic en Seleccionar.</span><span class="sxs-lookup"><span data-stu-id="d25ed-125">Click Select.</span></span>
18. <span data-ttu-id="d25ed-126">En el campo Fecha límite de la solicitud, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="d25ed-126">In the Application deadline field, enter a date.</span></span>
19. <span data-ttu-id="d25ed-127">Haga clic en Medios.</span><span class="sxs-lookup"><span data-stu-id="d25ed-127">Click Media.</span></span>
    * <span data-ttu-id="d25ed-128">Los proyectos de contratación incluyen la opción de especificar los mercados de medios que se usarán para realizar publicidad de vacantes.</span><span class="sxs-lookup"><span data-stu-id="d25ed-128">Recruitment projects include the option to specify media outlets to use to advertise open positions.</span></span>  
20. <span data-ttu-id="d25ed-129">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="d25ed-129">Click New.</span></span>
21. <span data-ttu-id="d25ed-130">En el campo Medios, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d25ed-130">In the Media field, click the drop-down button to open the lookup.</span></span>
22. <span data-ttu-id="d25ed-131">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="d25ed-131">In the list, click the link in the selected row.</span></span>
23. <span data-ttu-id="d25ed-132">En el campo Fecha inicial, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="d25ed-132">In the Start date field, enter a date.</span></span>
24. <span data-ttu-id="d25ed-133">En el campo Fecha final, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="d25ed-133">In the End date field, enter a date.</span></span>
25. <span data-ttu-id="d25ed-134">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d25ed-134">Click Save.</span></span>
26. <span data-ttu-id="d25ed-135">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d25ed-135">Close the page.</span></span>
27. <span data-ttu-id="d25ed-136">Haga clic en Anuncios de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d25ed-136">Click Job ads.</span></span>
28. <span data-ttu-id="d25ed-137">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="d25ed-137">Click Save.</span></span>
29. <span data-ttu-id="d25ed-138">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d25ed-138">Close the page.</span></span>
30. <span data-ttu-id="d25ed-139">Active o desactive la casilla Mostrar en autoservicio para empleados.</span><span class="sxs-lookup"><span data-stu-id="d25ed-139">Check or uncheck the Display on employee self service checkbox.</span></span>
    * <span data-ttu-id="d25ed-140">Seleccione la casilla Mostrar en autoservicio para empleados para que el proyecto de contratación sea visible a los empleados en las páginas de autoservicio del empleado.</span><span class="sxs-lookup"><span data-stu-id="d25ed-140">Select the Display on employee self service check box to make the recruitment project visible to employees on their Employee self-service pages.</span></span>  
31. <span data-ttu-id="d25ed-141">Haga clic en Estado de proyecto de contratación.</span><span class="sxs-lookup"><span data-stu-id="d25ed-141">Click Recruitment project status.</span></span>
32. <span data-ttu-id="d25ed-142">Haga clic en Inicio.</span><span class="sxs-lookup"><span data-stu-id="d25ed-142">Click Start.</span></span>
    * <span data-ttu-id="d25ed-143">El estado Iniciado significa que el proyecto está listo para recibir las solicitudes.</span><span class="sxs-lookup"><span data-stu-id="d25ed-143">The Started status means that the project is ready to receive applications.</span></span>  
33. <span data-ttu-id="d25ed-144">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="d25ed-144">Click OK.</span></span>



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]