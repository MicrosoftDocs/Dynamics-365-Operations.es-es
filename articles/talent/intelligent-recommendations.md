---
title: Recomendaciones inteligentes
description: "Este tema explica cómo se puede usar el aprendizaje automático para proporcionar recomendaciones para los trabajos y los candidatos de trabajo."
author: josaw
manager: AnnBe
ms.date: 10/15/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: b589a6ce02cdc02436e256f9e81346fe8b766687
ms.openlocfilehash: c6225a311f5ba0b65b45092a1f626b9d6aff3f5e
ms.contentlocale: es-es
ms.lasthandoff: 11/12/2018

---

# <a name="intelligent-recommendations"></a><span data-ttu-id="b13dc-103">Recomendaciones inteligentes</span><span class="sxs-lookup"><span data-stu-id="b13dc-103">Intelligent recommendations</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b13dc-104">El aprendizaje automático puede ayudar reclutadores y a los administradores de contratación a identificar rápidamente a los candidatos mejor situados para un puesto.</span><span class="sxs-lookup"><span data-stu-id="b13dc-104">Machine learning can help recruiters and hiring managers quickly identify top candidates for a position.</span></span> <span data-ttu-id="b13dc-105">También puede ayudar a los candidatos viables a encontrar el puesto que mejor se adapta a su perfil e intereses.</span><span class="sxs-lookup"><span data-stu-id="b13dc-105">It can also help prospects find the position that best suits their profile and interests.</span></span> <span data-ttu-id="b13dc-106">A medida que se usan estas características, y se proporcionan valoraciones, las recomendaciones mejorarán.</span><span class="sxs-lookup"><span data-stu-id="b13dc-106">As these features are used, and feedback is provided, recommendations will improve.</span></span>

> [!NOTE] 
> - <span data-ttu-id="b13dc-107">Las características de recomendación inteligente solo están disponibles con el complemento de contratación completa.</span><span class="sxs-lookup"><span data-stu-id="b13dc-107">The intelligent recommendation features are available only with the Comprehensive hiring add-on.</span></span>
> - <span data-ttu-id="b13dc-108">Para habilitar las características de recomendación del candidato y el trabajo, un administrador tiene que activar las opciones de vista previa para ellos.</span><span class="sxs-lookup"><span data-stu-id="b13dc-108">To enable the candidate and job recommendation features, an admin must turn on the preview options for them.</span></span> <span data-ttu-id="b13dc-109">En el centro de gestión, en la pestaña **Administración de la función**, asegúrese de que la opción **Funciones de vista previa** está configurada en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="b13dc-109">In the Admin center, on the **Feature management** tab, make sure that the **Preview features** option is set to **On**.</span></span> <span data-ttu-id="b13dc-110">A continuación asegúrese de que las opciones **Recomendación del candidato** y **Recomendación de trabajo** están configurados en **Activado**.</span><span class="sxs-lookup"><span data-stu-id="b13dc-110">Then make sure that the individual **Candidate recommendation** and **Job recommendation** options are set to **On**.</span></span>

## <a name="candidate-recommendations"></a><span data-ttu-id="b13dc-111">Recomendaciones de candidatos</span><span class="sxs-lookup"><span data-stu-id="b13dc-111">Candidate recommendations</span></span>

<span data-ttu-id="b13dc-112">Dado que las propuestas de empleo pueden atraer a cientos de candidatos, puede resultar difícil para que los reclutadores y los responsables de contratación encuentren candidatos cuyos aptitudes e historial son los requeridos para el puesto.</span><span class="sxs-lookup"><span data-stu-id="b13dc-112">Because job postings might attract hundreds of applicants, it can be difficult for recruiters and hiring managers to find the candidates whose skills and background best match the position.</span></span> <span data-ttu-id="b13dc-113">Al analizar la correlación entre la descripción del trabajo y los requisitos, y los datos de curriculums vitae y de los perfiles de los candidatos, se puede usar el aprendizaje automático para genearr recomendaciones del candidato.</span><span class="sxs-lookup"><span data-stu-id="b13dc-113">By analyzing the correlation between the job description and requirements, and data from the candidates' resumes and profiles, machine learning can be used to produce candidate recommendations.</span></span> <span data-ttu-id="b13dc-114">Las recomendaciones de candidatos pueden ayudar reclutadores y a los administradores de contratación a identificar los talentos mejor situados y a moverlos a la etapa de la entrevista con más rapidez.</span><span class="sxs-lookup"><span data-stu-id="b13dc-114">Candidate recommendations can help recruiters and hiring managers identify the top talent and move them to the interview stage faster.</span></span> <span data-ttu-id="b13dc-115">Para cualquier trabajo, si hay más de diez candidatos o candidatos potenciales que tienen curriculums vitae o perfiles completos, los candidatos o candidatos viables que mejor cumplan los requisitos de trabajo aparecen en la sección **Candidatos a tener en cuenta** en la página **Trabajo**.</span><span class="sxs-lookup"><span data-stu-id="b13dc-115">For any job, if there are more than ten candidates or prospects who have resumes or complete profiles, the candidates or prospects who most closely meet the job's requirements appear in the **Applicants to consider** section on the **Job** page.</span></span>

<span data-ttu-id="b13dc-116">Para cualquier candidato recomendado, puede seleccionar **Ver candidato** en la tarjeta del candidato para revisar el perfil del candidato y actuar en su solicitud.</span><span class="sxs-lookup"><span data-stu-id="b13dc-116">For any recommended candidate, you can select **View candidate** on the candidate card to review the candidate's profile and take action on his or her application.</span></span> <span data-ttu-id="b13dc-117">Puede usar el botón de puntos suspensivos (**...**) para abrir el perfil del candidato en una nueva ficha. Puede usar puntos suspensivos para proporcionar valoraciones acerca de la recomendación.</span><span class="sxs-lookup"><span data-stu-id="b13dc-117">You can use the ellipsis button (**...**) to open the candidate's profile on a new tab. You can also use the ellipsis button to provide feedback about the recommendation.</span></span> <span data-ttu-id="b13dc-118">De esta manera, puede ayudar a ajustar el motor de recomendación y a mejorar las recomendaciones futuras.</span><span class="sxs-lookup"><span data-stu-id="b13dc-118">In this way, you help fine-tune the recommendation engine and improve future recommendations.</span></span> <span data-ttu-id="b13dc-119">Cualquier recomendación que no le guste se eliminará de la sección **Candidatos a tener en cuenta** al actualizar la página **Trabajo**.</span><span class="sxs-lookup"><span data-stu-id="b13dc-119">Any recommendations that you don't like are removed from the **Applicants to consider** section when you refresh the **Job** page.</span></span> <span data-ttu-id="b13dc-120">Puede usar la tarjeta de valoración para indicar por qué no encontró la recomendación útil.</span><span class="sxs-lookup"><span data-stu-id="b13dc-120">You can use the feedback card to indicate why you didn't find the recommendation useful.</span></span>

## <a name="job-recommendations"></a><span data-ttu-id="b13dc-121">Recomendación de trabajos</span><span class="sxs-lookup"><span data-stu-id="b13dc-121">Job recommendations</span></span> 

<span data-ttu-id="b13dc-122">Cuando un empleado potencial utiliza el sitio de Proyectos profesionales para solicitar un trabajo, otros puestos vacantes en la organización se recomiendan.</span><span class="sxs-lookup"><span data-stu-id="b13dc-122">When a prospective employee uses the career site to apply to a job, other open positions at the organization are recommended.</span></span> <span data-ttu-id="b13dc-123">Estas recomendaciones se basan en las solicitudes anteriores del cliente viable y en su currículum o perfil de candidato.</span><span class="sxs-lookup"><span data-stu-id="b13dc-123">These recommendations are based on the prospect's past applications, and on his or her resume or candidate profile.</span></span> <span data-ttu-id="b13dc-124">Por lo tanto, las recomendaciones de trabajo ayudan a los candidatos viables a identificar rápidamente los trabajos que se ajusten mejor a ellos.</span><span class="sxs-lookup"><span data-stu-id="b13dc-124">Therefore, job recommendations help prospects quickly identify the jobs that are the best fit for them.</span></span> <span data-ttu-id="b13dc-125">Las recomendaciones de trabajo se ofrecen a los clientes viables si hay más de diez trabajos publicados en el sitio de Proyectos profesionales.</span><span class="sxs-lookup"><span data-stu-id="b13dc-125">Job recommendations are provided to prospects if more than ten jobs are posted on the career site.</span></span> <span data-ttu-id="b13dc-126">Los candidatos potenciales pueden abrir los detalles de una oferta de empleo desde la tarjeta de recomendación.</span><span class="sxs-lookup"><span data-stu-id="b13dc-126">Prospects can open the details of a job posting from the recommendation card.</span></span> <span data-ttu-id="b13dc-127">También pueden proporcionar comentarios sobre una recomendación para ayudar a mejorar las recomendaciones futuras.</span><span class="sxs-lookup"><span data-stu-id="b13dc-127">They can also provide feedback about a recommendation to help improve future recommendations.</span></span>
