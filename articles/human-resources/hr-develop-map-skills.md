---
title: Asignar aptitudes
description: Puede crear una búsqueda de asignación de aptitudes para encontrar una persona calificada en Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 03b7860fbde89097141cfe48f2c240dc127aa9c3
ms.sourcegitcommit: 48528233e0f02dbd47e96e030254ef65f2bb899e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2021
ms.locfileid: "6076613"
---
# <a name="map-skills"></a><span data-ttu-id="da52e-103">Asignar aptitudes</span><span class="sxs-lookup"><span data-stu-id="da52e-103">Map skills</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="da52e-104">Puede crear una búsqueda de asignación de aptitudes para encontrar una persona calificada en Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="da52e-104">You can create a skill-mapping search to find a qualified person in Dynamics 365 Human Resources.</span></span> <span data-ttu-id="da52e-105">Las búsquedas de asignación de aptitudes devuelven resultados para los criterios que ingresa al revisar la siguiente información:</span><span class="sxs-lookup"><span data-stu-id="da52e-105">Skill-mapping searches return results for criteria you enter by looking through the following information:</span></span>

- <span data-ttu-id="da52e-106">Aptitudes</span><span class="sxs-lookup"><span data-stu-id="da52e-106">Skills</span></span>
- <span data-ttu-id="da52e-107">Formación</span><span class="sxs-lookup"><span data-stu-id="da52e-107">Education</span></span>
- <span data-ttu-id="da52e-108">Certificados</span><span class="sxs-lookup"><span data-stu-id="da52e-108">Certificates</span></span>
- <span data-ttu-id="da52e-109">Puestos</span><span class="sxs-lookup"><span data-stu-id="da52e-109">Positions</span></span>
- <span data-ttu-id="da52e-110">Experiencia en proyectos</span><span class="sxs-lookup"><span data-stu-id="da52e-110">Project experience</span></span>

<span data-ttu-id="da52e-111">Por ejemplo, puede encontrar personas en su organización que hayan obtenido su CPA.</span><span class="sxs-lookup"><span data-stu-id="da52e-111">For example, you can find people in your organization who have earned their CPA.</span></span>

<span data-ttu-id="da52e-112">Los perfiles de distribución de aptitudes le permiten buscar empleados o candidatos actuales con cualificaciones que se correspondan directamente con sus necesidades empresariales.</span><span class="sxs-lookup"><span data-stu-id="da52e-112">Skill-mapping profiles allow you to find current employees or candidates with qualifications that directly correspond to business needs.</span></span>

> [!NOTE]
> <span data-ttu-id="da52e-113">Solo los trabajadores, los candidatos y las personas de contacto que se seleccionan para incluirse en las búsquedas de distribución de aptitudes se pueden mostrar en una lista de los resultados correspondiente o incluirse en un perfil de aptitudes.</span><span class="sxs-lookup"><span data-stu-id="da52e-113">Only workers, applicants, and contact persons who are selected to be included in skill-mapping searches will display in a skill-mapping results list, or be included in a skill profile.</span></span> <span data-ttu-id="da52e-114">Para incluir un persona en búsquedas de distribución de perfiles, establezca **Incluir en distribución de habilidades** en **Sí** en las siguientes páginas:</span><span class="sxs-lookup"><span data-stu-id="da52e-114">To include a person in skill mapping searches, set the **Include in skill mapping** selection to **Yes** in the following pages:</span></span><br>
> - <span data-ttu-id="da52e-115">Trabajador</span><span class="sxs-lookup"><span data-stu-id="da52e-115">Worker</span></span><br>
> - <span data-ttu-id="da52e-116">Empleado</span><span class="sxs-lookup"><span data-stu-id="da52e-116">Employee</span></span><br>
> - <span data-ttu-id="da52e-117">Candidato</span><span class="sxs-lookup"><span data-stu-id="da52e-117">Applicant</span></span><br>
> - <span data-ttu-id="da52e-118">Contactos</span><span class="sxs-lookup"><span data-stu-id="da52e-118">Contacts</span></span><br>

<span data-ttu-id="da52e-119">Para crear una asignación de aptitudes, vaya a **Desarrollo de empleados > Enlaces > Asignación de aptitudes**.</span><span class="sxs-lookup"><span data-stu-id="da52e-119">To create a skill mapping, go to **Employee development > Links > Skill mapping**.</span></span> <span data-ttu-id="da52e-120">Para crear un perfil de asignación de aptitudes, vaya a **Desarrollo de empleados > Enlaces > Perfiles de asignación de aptitudes**.</span><span class="sxs-lookup"><span data-stu-id="da52e-120">To create a skill-mapping profile, go to **Employee development > Links > Skill mapping profiles**.</span></span>

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a><span data-ttu-id="da52e-121">Análisis de lagunas de aptitudes y análisis de perfiles de aptitudes</span><span class="sxs-lookup"><span data-stu-id="da52e-121">Skill gap analysis and skill profile analysis</span></span>

<span data-ttu-id="da52e-122">Puede crear un análisis de perfil de aptitudes para ver una lista de las competencias de una persona.</span><span class="sxs-lookup"><span data-stu-id="da52e-122">You can create a skill profile analysis to view a list of a person's competencies.</span></span> <span data-ttu-id="da52e-123">Puede crear un análisis de lagunas de aptitudes para comparar las aptitudes de una persona con las aptitudes necesarias para un puesto.</span><span class="sxs-lookup"><span data-stu-id="da52e-123">You can create a skill gap analysis to compare a person’s skills and the skills required for a job.</span></span>

<span data-ttu-id="da52e-124">Para crear un análisis de lagunas, vaya a **Desarrollo de empleados > Enlaces > Trabajo de análisis de lagunas de aptitudes - persona**.</span><span class="sxs-lookup"><span data-stu-id="da52e-124">To create a gap analysis, go to **Employee development > Links > Skill gap analysis job - person**.</span></span> <span data-ttu-id="da52e-125">Para crear un perfil de análisis de aptitudes, vaya a **Desarrollo de empleados > Enlaces > Perfiles de análisis de aptitudes**.</span><span class="sxs-lookup"><span data-stu-id="da52e-125">To create a skill profile analysis, go to **Employee development > Links > Skill profile analysis**.</span></span>

## <a name="see-also"></a><span data-ttu-id="da52e-126">Consulte también</span><span class="sxs-lookup"><span data-stu-id="da52e-126">See also</span></span>

[<span data-ttu-id="da52e-127">Configurar aptitudes</span><span class="sxs-lookup"><span data-stu-id="da52e-127">Configure skills</span></span>](hr-develop-skills.md)<br>
[<span data-ttu-id="da52e-128">Introducir aptitudes</span><span class="sxs-lookup"><span data-stu-id="da52e-128">Enter skills</span></span>](hr-develop-enter-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]