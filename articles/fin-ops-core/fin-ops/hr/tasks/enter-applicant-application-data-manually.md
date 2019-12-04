---
title: Especificar los datos del candidato y de la solicitud manualmente
description: Este procedimiento muestra cómo mantener manualmente la información de los candidatos y sus solicitudes.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HcmApplicant, LogisticsContactInfoGrid, HRMApplication,  DirPartyTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ea61e3c1d76ade6e0d694b4b521e4be76fc8799d
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "2179882"
---
# <a name="enter-applicant-and-application-data-manually"></a><span data-ttu-id="2827a-103">Especificar los datos del candidato y de la solicitud manualmente</span><span class="sxs-lookup"><span data-stu-id="2827a-103">Enter applicant and application data manually</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2827a-104">Este procedimiento muestra cómo mantener manualmente la información de los candidatos y sus solicitudes.</span><span class="sxs-lookup"><span data-stu-id="2827a-104">This procedure shows how to manually maintain information about applicants and their application.</span></span>   <span data-ttu-id="2827a-105">Puede especificar y mantener información personal, fechas y horas de entrevistas, referencias, capacidades y los solicitudes de alojamiento de los candidatos.</span><span class="sxs-lookup"><span data-stu-id="2827a-105">You can enter and maintain personal information, interview dates and times, references, competencies, and accommodation requests for applicants.</span></span> <span data-ttu-id="2827a-106">También puede actualizar el estado de las solicitudes de empleo de los candidatos y crear cartas o mensajes de correo electrónico para comunicarse con ellos.</span><span class="sxs-lookup"><span data-stu-id="2827a-106">You can also update the status of applicants’ applications for employment and create letters or email messages to communicate with applicants.</span></span> <span data-ttu-id="2827a-107">Al crear un registro de candidato, se creará un registro de la persona para dicho candidato en la libreta de direcciones global.</span><span class="sxs-lookup"><span data-stu-id="2827a-107">When you create an applicant record, a person record for that applicant is created in the global address book.</span></span>       <span data-ttu-id="2827a-108">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="2827a-108">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-new-applicant-record"></a><span data-ttu-id="2827a-109">Creación de un nuevo registro de candidato nuevo</span><span class="sxs-lookup"><span data-stu-id="2827a-109">Create a new applicant record</span></span>
1. <span data-ttu-id="2827a-110">Vaya a Recursos humanos > Contratación > Candidatos > Candidatos.</span><span class="sxs-lookup"><span data-stu-id="2827a-110">Go to Human resources > Recruitment > Applicants > Applicants.</span></span>
2. <span data-ttu-id="2827a-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="2827a-111">Click New.</span></span>
3. <span data-ttu-id="2827a-112">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2827a-112">In the First name field, type a value.</span></span>
4. <span data-ttu-id="2827a-113">En el campo Apellidos, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2827a-113">In the Last name field, type a value.</span></span>
    * <span data-ttu-id="2827a-114">Puede especificar información adicional del candidato, si disponible de ella.</span><span class="sxs-lookup"><span data-stu-id="2827a-114">You can enter additional applicant information if it's available.</span></span> <span data-ttu-id="2827a-115">Por ejemplo, su cualificación más alta, su puesto actual de trabajo o su empleador anterior.</span><span class="sxs-lookup"><span data-stu-id="2827a-115">For example, information can include the applicant's highest degree, current job title, or previous employer.</span></span>  
5. <span data-ttu-id="2827a-116">Expanda la sección Información de contacto.</span><span class="sxs-lookup"><span data-stu-id="2827a-116">Toggle the expansion of the Contact information section.</span></span>
6. <span data-ttu-id="2827a-117">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="2827a-117">Click Add.</span></span>
7. <span data-ttu-id="2827a-118">En el campo Descripción, escriba "Correo electrónico de comunicación".</span><span class="sxs-lookup"><span data-stu-id="2827a-118">In the Description field, type 'Communications email'.</span></span>
8. <span data-ttu-id="2827a-119">En el campo Tipo, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="2827a-119">In the Type field, select an option.</span></span>
9. <span data-ttu-id="2827a-120">En el campo Dirección y número de contacto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2827a-120">In the Contact number/address field, type a value.</span></span>
    * <span data-ttu-id="2827a-121">Esta dirección de correo electrónico se usará para generar la comunicación por correo electrónico con el candidato.</span><span class="sxs-lookup"><span data-stu-id="2827a-121">This email address will be used to generate email communication with the applicant.</span></span>  
10. <span data-ttu-id="2827a-122">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="2827a-122">Click Add.</span></span>
11. <span data-ttu-id="2827a-123">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2827a-123">In the Description field, type a value.</span></span>
12. <span data-ttu-id="2827a-124">En el campo Dirección y número de contacto, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="2827a-124">In the Contact number/address field, type a value.</span></span>
    * <span data-ttu-id="2827a-125">Información personal del candidato.</span><span class="sxs-lookup"><span data-stu-id="2827a-125">Applicant personal information.</span></span>  
    * <span data-ttu-id="2827a-126">Puede especificar otra información personal para el candidato, si fuera necesario.</span><span class="sxs-lookup"><span data-stu-id="2827a-126">You can enter additional personal information for the applicant, if needed.</span></span> <span data-ttu-id="2827a-127">Por ejemplo, la fecha de nacimiento, el origen étnico, el sexo o el estado civil.</span><span class="sxs-lookup"><span data-stu-id="2827a-127">For example, this can include birth date, ethnic origin, gender, or marital status.</span></span>  
13. <span data-ttu-id="2827a-128">En el panel de acciones, haga clic en Competencias.</span><span class="sxs-lookup"><span data-stu-id="2827a-128">On the Action Pane, click Competencies.</span></span>
    * <span data-ttu-id="2827a-129">Puede especificar el perfil de competencia del candidato, como sus aptitudes, su experiencia profesional, su formación, exámenes o certificados.</span><span class="sxs-lookup"><span data-stu-id="2827a-129">You can enter the applicant's competency profile, including their skills, professional experiences, education, tests, or certificates.</span></span>  
    * <span data-ttu-id="2827a-130">Esta información se puede usar para asignar las aptitudes del candidato a las aptitudes asociadas con los trabajos definidos en los datos de su empresa.</span><span class="sxs-lookup"><span data-stu-id="2827a-130">This information can be used to map the applicant's skills to the skills associated with the jobs defined in your company's data.</span></span>   

## <a name="create-an-application-for-the-applicant"></a><span data-ttu-id="2827a-131">Creación de una solicitud para el candidato</span><span class="sxs-lookup"><span data-stu-id="2827a-131">Create an application for the applicant</span></span>
1. <span data-ttu-id="2827a-132">Haga clic en Solicitudes.</span><span class="sxs-lookup"><span data-stu-id="2827a-132">Click Applications.</span></span>
2. <span data-ttu-id="2827a-133">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="2827a-133">Click New.</span></span>
3. <span data-ttu-id="2827a-134">En el campo Proyecto de contratación, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="2827a-134">In the Recruitment project field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="2827a-135">Al seleccionar un proyecto de contratación, se asociará al candidato con una vacante específica incluida en dicho proyecto de contratación.</span><span class="sxs-lookup"><span data-stu-id="2827a-135">By selecting a recruitment project, the applicant will be associated with a specific opening included in that recruitment project.</span></span>  
4. <span data-ttu-id="2827a-136">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="2827a-136">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="2827a-137">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="2827a-137">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="2827a-138">De forma predeterminada, el trabajo y el departamento se basan en el proyecto de contratación seleccionado.</span><span class="sxs-lookup"><span data-stu-id="2827a-138">By default, the job and department are based on the selected recruitment project.</span></span>  
6. <span data-ttu-id="2827a-139">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="2827a-139">Click Save.</span></span>
    * <span data-ttu-id="2827a-140">Tras guardar la solicitud, puede adjuntarle documentos, incluida la experiencia del candidato, los títulos y una carta de presentación.</span><span class="sxs-lookup"><span data-stu-id="2827a-140">After saving the application, you can attach documents to it, including the applicant's experience, awards, and cover letter.</span></span>  
