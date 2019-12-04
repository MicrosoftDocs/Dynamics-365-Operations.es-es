---
title: Identificar e implementar herramientas de selección de candidatos
description: Encontrar un grupo calificado de candidatos para cubrir vacantes puede ser difícil, especialmente cuando un puesto requiere un conjunto único de aptitudes.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmSkillMapping, HcmJobLookup, HcmSkillMappingLine, HcmPersonCertificate, CCHTMLPrintPreview
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 51200a67a51097c438370866cb9d0ccbebe8392c
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2190382"
---
# <a name="identify-and-deploy-candidate-selection-tools"></a><span data-ttu-id="105ca-103">Identificar e implementar herramientas de selección de candidatos</span><span class="sxs-lookup"><span data-stu-id="105ca-103">Identify and deploy candidate selection tools</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="105ca-104">Encontrar un grupo calificado de candidatos para cubrir vacantes puede ser difícil, especialmente cuando un puesto requiere un conjunto único de aptitudes.</span><span class="sxs-lookup"><span data-stu-id="105ca-104">Finding a qualified pool of candidates to fill vacancies can be difficult, especially when a position requires a unique set of skills.</span></span>  <span data-ttu-id="105ca-105">Sin embargo, los candidatos con las aptitudes que necesita podrían ser ya empleados de su organización.</span><span class="sxs-lookup"><span data-stu-id="105ca-105">However, candidates with the skills you need might already be employed in your organization.</span></span> <span data-ttu-id="105ca-106">Puede buscar un conjunto de aptitudes específico entre los empleados existentes o los nuevos candidatos.</span><span class="sxs-lookup"><span data-stu-id="105ca-106">You can search for a specific skill set among existing employees, or new applicants.</span></span> <span data-ttu-id="105ca-107">Esto permite a un reclutador reunir y filtrar rápidamente a los candidatos que han solicitado la vacante ahora o en el pasado, o encontrar a los candidatos potenciales del grupo existente de empleados.</span><span class="sxs-lookup"><span data-stu-id="105ca-107">This allows a recruiter to quickly gather and screen applicants who have applied for open position now or in the past, or to find potential candidates from their existing pool of employees.</span></span> <span data-ttu-id="105ca-108">Utilice este registro de tareas para saber cómo la funcionalidad de distribución de perfiles puede ayudarle a encontrar a la persona adecuada para una vacante.</span><span class="sxs-lookup"><span data-stu-id="105ca-108">Use this task recording to learn how the skill mapping functionality can help you find the right person for an open position.</span></span> <span data-ttu-id="105ca-109">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="105ca-109">The demo data company used to create this procedure is USMF.</span></span>

1. <span data-ttu-id="105ca-110">Vaya a Recursos humanos > Competencias > Análisis de aptitudes > Perfiles de distribución de perfiles.</span><span class="sxs-lookup"><span data-stu-id="105ca-110">Go to Human resources > Competencies > Skill analysis > Skill mapping profiles.</span></span>
2. <span data-ttu-id="105ca-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="105ca-111">Click New.</span></span>
3. <span data-ttu-id="105ca-112">En el campo Distribución de perfiles, especifique un nombre para la distribución de perfiles.</span><span class="sxs-lookup"><span data-stu-id="105ca-112">In the Skill mapping field, enter a name for your skill mapping.</span></span>  <span data-ttu-id="105ca-113">Ejemplo: Contable.</span><span class="sxs-lookup"><span data-stu-id="105ca-113">Example: Accountant.</span></span>
4. <span data-ttu-id="105ca-114">En el campo Descripción, escriba una descripción de la distribución de perfiles.</span><span class="sxs-lookup"><span data-stu-id="105ca-114">In the Description field, enter a description of the skill mapping..</span></span>
5. <span data-ttu-id="105ca-115">En el campo Fecha, escriba una fecha.</span><span class="sxs-lookup"><span data-stu-id="105ca-115">In the Date field, enter a date.</span></span>
6. <span data-ttu-id="105ca-116">Haga clic en Recuperar perfil.</span><span class="sxs-lookup"><span data-stu-id="105ca-116">Click Retrieve profile.</span></span>
    * <span data-ttu-id="105ca-117">Utilice Recuperar perfil para extraer los datos de certificado, aptitud y formación de una persona, trabajo o curso seleccionado como base para la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="105ca-117">Use Retrieve profile to pull in the Certificate, Skill, and Education data from a selected Person, Job or Course as the basis for your search.</span></span>   <span data-ttu-id="105ca-118">Puede agregar o quitar los criterios, indicar si los criterios son opcionales y clasificar la importancia de los criterios.</span><span class="sxs-lookup"><span data-stu-id="105ca-118">You can then add or remove criteria, state if the criteria is optional and rank the importance of the criteria.</span></span>  
7. <span data-ttu-id="105ca-119">Haga clic en Trabajo.</span><span class="sxs-lookup"><span data-stu-id="105ca-119">Click Job.</span></span>
8. <span data-ttu-id="105ca-120">En el campo Trabajo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="105ca-120">In the Job field, enter or select a value.</span></span>
9. <span data-ttu-id="105ca-121">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="105ca-121">Click OK.</span></span>
10. <span data-ttu-id="105ca-122">Expanda la ficha desplegable Intervalo y agregue información adicional, como el departamento.</span><span class="sxs-lookup"><span data-stu-id="105ca-122">Expand the range fast tab, and add any additional information, such as department.</span></span>
11. <span data-ttu-id="105ca-123">Expanda la ficha rápida Certificados para ver o editar los certificados.</span><span class="sxs-lookup"><span data-stu-id="105ca-123">Expand the certificates fast tab to view or edit the certificates.</span></span>
12. <span data-ttu-id="105ca-124">Expanda la ficha rápida Aptitudes para ver o editar las aptitudes.</span><span class="sxs-lookup"><span data-stu-id="105ca-124">Expand the Skills fast tab to view or edit the skills.</span></span>
13. <span data-ttu-id="105ca-125">Expanda la ficha rápida Formación para ver o editar los criterios de formación.</span><span class="sxs-lookup"><span data-stu-id="105ca-125">Expand the Education fast tab to view or edit the education criteria.</span></span>
14. <span data-ttu-id="105ca-126">Haga clic en Ejecutar.</span><span class="sxs-lookup"><span data-stu-id="105ca-126">Click Execute.</span></span>
15. <span data-ttu-id="105ca-127">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="105ca-127">Click OK.</span></span>
16. <span data-ttu-id="105ca-128">Haga clic en Resultado.</span><span class="sxs-lookup"><span data-stu-id="105ca-128">Click Result.</span></span>
17. <span data-ttu-id="105ca-129">Haga clic en Resultado.</span><span class="sxs-lookup"><span data-stu-id="105ca-129">Click Result.</span></span>
18. <span data-ttu-id="105ca-130">Haga clic en Reanudar.</span><span class="sxs-lookup"><span data-stu-id="105ca-130">Click Resume.</span></span>
19. <span data-ttu-id="105ca-131">Haga clic en Certificados.</span><span class="sxs-lookup"><span data-stu-id="105ca-131">Click Certificates.</span></span>
    * <span data-ttu-id="105ca-132">Puede explorar más exhaustivamente cada persona enumerada y ver los detalles relativos a sus estudios, aptitudes, experiencia profesional, etc.</span><span class="sxs-lookup"><span data-stu-id="105ca-132">You can drill further into each person listed and see details regarding their education, skills, professional experience etc.</span></span>  
20. <span data-ttu-id="105ca-133">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="105ca-133">Close the page.</span></span>
21. <span data-ttu-id="105ca-134">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="105ca-134">Close the page.</span></span>
22. <span data-ttu-id="105ca-135">Seleccione el resultado de nuevo.</span><span class="sxs-lookup"><span data-stu-id="105ca-135">Select result again.</span></span>
23. <span data-ttu-id="105ca-136">Haga clic en Informe.</span><span class="sxs-lookup"><span data-stu-id="105ca-136">Click Report.</span></span>
    * <span data-ttu-id="105ca-137">El informe enumerará las mejores coincidencias en la parte superior del informe.</span><span class="sxs-lookup"><span data-stu-id="105ca-137">The report will list the best matches at the top of the report.</span></span>  <span data-ttu-id="105ca-138">Puede ver que hay un hueco en los elementos enumerados.</span><span class="sxs-lookup"><span data-stu-id="105ca-138">You can see that there is a gap element listed.</span></span>  <span data-ttu-id="105ca-139">Esta es la diferencia entre el nivel que se muestra en la distribución de perfiles y el nivel de la aptitud que está asignado a la persona.</span><span class="sxs-lookup"><span data-stu-id="105ca-139">This is the difference between the level that was listed on the skill mapping, and the level of the skill that is assigned to the person.</span></span>  
24. <span data-ttu-id="105ca-140">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="105ca-140">Close the page.</span></span>
25. <span data-ttu-id="105ca-141">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="105ca-141">Click Save.</span></span>
