---
title: La funcionalidad del sitio de Proyectos profesionales en Attract
description: "Este artículo proporciona una visión general de la funcionalidad del sitio de Proyectos profesionales de candidatos en Microsoft Dynamics 365 for Talent - Attract. También se explica cómo configurar esta funcionalidad."
author: josaw
manager: AnnBe
ms.date: 10/18/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: rschloma
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e890e32049e930b70c2d0aac8aa8206ab999418a
ms.openlocfilehash: 452e3e92ea32ab5f1e3720ab81ff2f7ea18b2a06
ms.contentlocale: es-es
ms.lasthandoff: 10/22/2018

---
# <a name="career-site-functionality-in-attract"></a><span data-ttu-id="d5101-104">La funcionalidad del sitio de Proyectos profesionales en Attract</span><span class="sxs-lookup"><span data-stu-id="d5101-104">Career site functionality in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="d5101-105">Este artículo proporciona una visión general de la funcionalidad del sitio de Proyectos profesionales de candidatos en Microsoft Dynamics 365 for Talent: Attract.</span><span class="sxs-lookup"><span data-stu-id="d5101-105">This article provides an overview of the candidate-facing career site functionality in Microsoft Dynamics 365 for Talent: Attract.</span></span> <span data-ttu-id="d5101-106">También se explica cómo configurar esta funcionalidad.</span><span class="sxs-lookup"><span data-stu-id="d5101-106">It also explains how to set up this functionality.</span></span>

## <a name="overview"></a><span data-ttu-id="d5101-107">Información general</span><span class="sxs-lookup"><span data-stu-id="d5101-107">Overview</span></span>

<span data-ttu-id="d5101-108">Attract ofrece un sitio de Proyectos profesionales para cada entorno de inquilino.</span><span class="sxs-lookup"><span data-stu-id="d5101-108">Attract provides one career site for each environment in a tenant.</span></span> <span data-ttu-id="d5101-109">Por ejemplo, si una organización tiene un entorno de desarrollo y un entorno de prueba, un sitio de Proyectos profesionales se aprovisiona para el entorno de desarrollo, y otro sitio de Proyectos profesionales se aprovisiona para el entorno de prueba.</span><span class="sxs-lookup"><span data-stu-id="d5101-109">For example, if an organization has a development environment and a test environment, one career site is provisioned for the development environment, and another career site is provisioned for the test environment.</span></span> <span data-ttu-id="d5101-110">Cada sitio de Proyectos profesionales es **aislado completamente** y tiene su propio mecanismo de autenticación.</span><span class="sxs-lookup"><span data-stu-id="d5101-110">Each career site is **completely isolated** and has its own authentication mechanism.</span></span> <span data-ttu-id="d5101-111">Los trabajos y los perfiles del candidato no se comparten entre los sitios de la Proyectos profesionales.</span><span class="sxs-lookup"><span data-stu-id="d5101-111">Jobs and candidate profiles aren't shared between career sites.</span></span>

<span data-ttu-id="d5101-112">De forma predeterminada, el sitio de la Proyectos profesionales es público.</span><span class="sxs-lookup"><span data-stu-id="d5101-112">By default, the career site is public.</span></span> <span data-ttu-id="d5101-113">Por lo tanto, los candidatos pueden ver todos los trabajos que están marcados como externos sin tener que iniciar sesión.</span><span class="sxs-lookup"><span data-stu-id="d5101-113">Therefore, candidates can view all jobs that are marked as external without having to sign in.</span></span> <span data-ttu-id="d5101-114">Sin embargo, el resto de las acciones requieren que los candidatos inicien sesión.</span><span class="sxs-lookup"><span data-stu-id="d5101-114">However, all other actions require that candidates sign in.</span></span>

## <a name="career-site-management"></a><span data-ttu-id="d5101-115">Gestión del sitio de desarrollo profesional</span><span class="sxs-lookup"><span data-stu-id="d5101-115">Career site management</span></span>

<span data-ttu-id="d5101-116">Los siguientes elementos en el sitio de la Proyectos profesionales son controlados mediante la configuración:</span><span class="sxs-lookup"><span data-stu-id="d5101-116">The following items on the career site are controlled by settings:</span></span>

- <span data-ttu-id="d5101-117">**Nombre de la organización:** El nombre de la organización aparece en la barra de navegación en la parte superior del sitio de Proyectos profesionales.</span><span class="sxs-lookup"><span data-stu-id="d5101-117">**Organization name:** The organization name appears on the navigation bar at the top of the career site.</span></span> <span data-ttu-id="d5101-118">Mediante la selección del nombre de la organización, los candidatos van a una página que enumera las vacantes.</span><span class="sxs-lookup"><span data-stu-id="d5101-118">By selecting the organization name, candidates go to a page that lists all open jobs.</span></span>
- <span data-ttu-id="d5101-119">**Logotipo de la organización:** Una imagen del logotipo de la organización aparece en la parte superior izquierda del sitio de Proyectos profesionales.</span><span class="sxs-lookup"><span data-stu-id="d5101-119">**Organization logo:** An image of the organization's logo appears in the upper left of the career site.</span></span> <span data-ttu-id="d5101-120">Mediante la selección de la imagen del logotipo, los candidatos van a una página que enumera las vacantes.</span><span class="sxs-lookup"><span data-stu-id="d5101-120">By selecting the logo image, candidates go to a page that lists all open jobs.</span></span>

<span data-ttu-id="d5101-121">Para establecer los valores para el nombre y el logotipo de la organización, inicie sesión en Attract como administrador, seleccione **Centro de administración** en el menú **Parámetros** (el símbolo de engranaje), y seleccione la pestaña **Información de la empresa**.</span><span class="sxs-lookup"><span data-stu-id="d5101-121">To set the values for the organization name and logo, sign in to Attract as an administrator, select **Admin center** on the **Settings** menu (the gear symbol), and then select the **Company information** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="d5101-122">La imagen del logotipo que aparece en el sitio de Proyectos profesionales tiene un altitud fija de 20 píxeles (px).</span><span class="sxs-lookup"><span data-stu-id="d5101-122">The logo image that appears on the career site has a fixed height of 20 pixels (px).</span></span> <span data-ttu-id="d5101-123">La imagen que agrega en el centro de gestión se escala para caber.</span><span class="sxs-lookup"><span data-stu-id="d5101-123">The image that you add in the Admin center is scaled to fit.</span></span> <span data-ttu-id="d5101-124">Por lo tanto, en función de la imagen, el ancho puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="d5101-124">Therefore, depending on the image, the width might change.</span></span>

## <a name="career-site-url"></a><span data-ttu-id="d5101-125">URL del sitio de desarrollo profesional</span><span class="sxs-lookup"><span data-stu-id="d5101-125">Career site URL</span></span>

<span data-ttu-id="d5101-126">Al [registrar un trabajo externo](./Creating-jobs-Attract.md#postings) por primera vez, puede copiar el vínculo **Solicitar** de la aplicación Attract.</span><span class="sxs-lookup"><span data-stu-id="d5101-126">When you [post an external job](./Creating-jobs-Attract.md#postings) for the first time, you can copy the **Apply** link from the Attract application.</span></span> <span data-ttu-id="d5101-127">La dirección URL para este vínculo estará en el formato siguiente: `https://jobs.talent.dynamics.com/jobs/<company_name>/<environment_number>/<job_number>/apply`</span><span class="sxs-lookup"><span data-stu-id="d5101-127">The URL for this link will be in the following format: `https://jobs.talent.dynamics.com/jobs/<company_name>/<environment_number>/<job_number>/apply`</span></span>

<span data-ttu-id="d5101-128">La dirección URL del sitio de Proyectos profesionales es una subcadena de la dirección URL **Solicitar**.</span><span class="sxs-lookup"><span data-stu-id="d5101-128">The URL of the career site is a substring of the **Apply** URL.</span></span> <span data-ttu-id="d5101-129">Incluye todo hasta el nombre de la empresa.</span><span class="sxs-lookup"><span data-stu-id="d5101-129">It consists of everything up through the company name.</span></span> <span data-ttu-id="d5101-130">Por lo tanto, para la dirección URL **Solicitar** anterior, la dirección URL del sitio de Proyectos profesionales is `https://jobs.talent.dynamics.com/jobs/<company_name>/`.</span><span class="sxs-lookup"><span data-stu-id="d5101-130">Therefore, for the preceding **Apply** URL, the career site URL is `https://jobs.talent.dynamics.com/jobs/<company_name>/`.</span></span>

## <a name="authentication-options"></a><span data-ttu-id="d5101-131">Opciones de autenticación</span><span class="sxs-lookup"><span data-stu-id="d5101-131">Authentication options</span></span>

<span data-ttu-id="d5101-132">Los candidatos tienen las siguientes opciones de inicio de sesión para un sitio de Proyectos profesionales de Attract:</span><span class="sxs-lookup"><span data-stu-id="d5101-132">Candidates have the following sign-in options for an Attract career site:</span></span>

- <span data-ttu-id="d5101-133">Cuenta personal:</span><span class="sxs-lookup"><span data-stu-id="d5101-133">Personal account:</span></span>

    - <span data-ttu-id="d5101-134">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="d5101-134">LinkedIn</span></span>
    - <span data-ttu-id="d5101-135">Microsoft</span><span class="sxs-lookup"><span data-stu-id="d5101-135">Microsoft</span></span>
    - <span data-ttu-id="d5101-136">Google</span><span class="sxs-lookup"><span data-stu-id="d5101-136">Google</span></span>
    - <span data-ttu-id="d5101-137">Facebook</span><span class="sxs-lookup"><span data-stu-id="d5101-137">Facebook</span></span>

- <span data-ttu-id="d5101-138">Cuenta del trabajo o del centro educativo:</span><span class="sxs-lookup"><span data-stu-id="d5101-138">Work or school account:</span></span>

    - <span data-ttu-id="d5101-139">Microsoft Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="d5101-139">Microsoft Azure Active Directory (Azure AD)</span></span>

<span data-ttu-id="d5101-140">El inicio de sesión de Azure AD es solo para candidatos internos.</span><span class="sxs-lookup"><span data-stu-id="d5101-140">Azure AD sign-in is intended only for internal candidates.</span></span> <span data-ttu-id="d5101-141">Por lo tanto, solo funciona para candidatos internos que usan las credenciales de Azure AD de la empresa.</span><span class="sxs-lookup"><span data-stu-id="d5101-141">Therefore, it works only for internal candidates who use their company Azure AD credentials.</span></span> <span data-ttu-id="d5101-142">Por ejemplo, un candidato que está actualmente empleado en Contoso Ltd quiere solicitar un trabajo en una empresa sin relación con la suya, Alpine Ski House.</span><span class="sxs-lookup"><span data-stu-id="d5101-142">For example, a candidate who is currently an employee of Contoso Ltd wants to apply for a job in an unrelated company, Alpine Ski House.</span></span> <span data-ttu-id="d5101-143">En este caso, el inicio de sesión no tendrá éxito si el empleado intenta usar sus credenciales de Azure AD de Contoso Ltd.</span><span class="sxs-lookup"><span data-stu-id="d5101-143">In this case, the sign-in will be unsuccessful if the employee tries to use his or her Azure AD credentials from Contoso Ltd.</span></span>

## <a name="create-and-maintain-a-profile"></a><span data-ttu-id="d5101-144">Creación y mantenimiento de un perfil</span><span class="sxs-lookup"><span data-stu-id="d5101-144">Create and maintain a profile</span></span>

<span data-ttu-id="d5101-145">Una vez que los candidatos inicien sesión en el sitio de Proyectos profesionales, pueden seleccionar **Mi perfil** en la barra de navegación en la parte superior de la página para crear y mantener su perfil.</span><span class="sxs-lookup"><span data-stu-id="d5101-145">After candidates sign in to the career site, they can select **My profile** on the navigation bar at the top of the page to create and maintain their profile.</span></span> <span data-ttu-id="d5101-146">El perfil incluye información personal, información sobre la experiencia profesional, detalles de formación, documentos, vínculos, e información acerca habilidades.</span><span class="sxs-lookup"><span data-stu-id="d5101-146">The profile includes personal information, information about work experience, education details, documents, links, and information about skill sets.</span></span> <span data-ttu-id="d5101-147">Una vez que se cree un perfil, se puede usar para solicitar trabajos en los que el candidato está interesado.</span><span class="sxs-lookup"><span data-stu-id="d5101-147">After a profile is created, it can be used to apply for jobs that the candidate is interested in.</span></span> <span data-ttu-id="d5101-148">Los perfiles también ayudan a Attract a recomendar los trabajos correctos para los candidatos.</span><span class="sxs-lookup"><span data-stu-id="d5101-148">Profiles also help Attract recommend the right jobs to candidates.</span></span>

## <a name="find-the-right-job"></a><span data-ttu-id="d5101-149">Encuentre el trabajo correcto</span><span class="sxs-lookup"><span data-stu-id="d5101-149">Find the right job</span></span>

<span data-ttu-id="d5101-150">En la página de la lista de trabajos, los candidatos pueden buscar un trabajo específico especificando términos de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="d5101-150">On the job list page, candidates can search for a specific job by entering search terms.</span></span> <span data-ttu-id="d5101-151">La funcionalidad de búsqueda busca los términos de búsqueda en los puestos y descripciones de trabajos, y muestra los trabajos apropiados como resultados.</span><span class="sxs-lookup"><span data-stu-id="d5101-151">The search functionality looks for the search terms in job titles and job descriptions, and shows relevant jobs as results.</span></span> <span data-ttu-id="d5101-152">Los candidatos pueden filtrar los resultados en cualquier momento, en función de la ubicación del trabajo o la función de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d5101-152">Candidates can filter the results at any time, based on the job location or job function.</span></span>

<span data-ttu-id="d5101-153">Los candidatos también pueden ver un conjunto de trabajos que se recomiendan en el sitio de Proyectos profesionales.</span><span class="sxs-lookup"><span data-stu-id="d5101-153">Candidates can also view a set of recommended jobs on the career site.</span></span> <span data-ttu-id="d5101-154">Los trabajos que se recomiendan a un candidato se basan en las solicitudes, perfil, y curriculums vitae anteriores del candidato.</span><span class="sxs-lookup"><span data-stu-id="d5101-154">The jobs that are recommended to a candidate are based on the candidate's past applications, profile, and resumes.</span></span>

> [!NOTE]
> <span data-ttu-id="d5101-155">Se muestran las recomendaciones de trabajo si al menos hay 10 trabajos publicados en el sitio de Proyectos profesionales, y si el candidato ha completado su perfil.</span><span class="sxs-lookup"><span data-stu-id="d5101-155">Job recommendations are shown only if at least 10 jobs are posted on the career site, and if the candidate has completed his or her profile.</span></span>

## <a name="apply-for-jobs"></a><span data-ttu-id="d5101-156">Solicitud de trabajos</span><span class="sxs-lookup"><span data-stu-id="d5101-156">Apply for jobs</span></span>

<span data-ttu-id="d5101-157">Una vez que los candidatos encuentren el trabajo correcto, pueden solicitar el trabajo mediante el botón **Solicitar** en la página de detalles del trabajo.</span><span class="sxs-lookup"><span data-stu-id="d5101-157">After candidates find the right job, they can apply by using the **Apply** button on the job details page.</span></span> <span data-ttu-id="d5101-158">En este punto, los candidatos pueden crear un perfil nuevo o revisar la información en su perfil existente.</span><span class="sxs-lookup"><span data-stu-id="d5101-158">At this point, candidates can either create a brand-new profile or review the information in their existing profile.</span></span> <span data-ttu-id="d5101-159">Los candidatos también pueden cargar un currículum, según convenga, y después enviar la solicitud de trabajo.</span><span class="sxs-lookup"><span data-stu-id="d5101-159">Candidates can also upload a resume, as required, and then submit the job application.</span></span>

## <a name="check-application-status"></a><span data-ttu-id="d5101-160">Comprobar el estado de la solicitud</span><span class="sxs-lookup"><span data-stu-id="d5101-160">Check application status</span></span>

<span data-ttu-id="d5101-161">Una vez que los candidatos hayan solicitado uno o más trabajos, pueden seleccionar **Solicitudes** en la barra de navegación en la parte superior de la página para ver sus solicitudes abiertas y cerradas.</span><span class="sxs-lookup"><span data-stu-id="d5101-161">After candidates apply for one or more jobs, they can select **Applications** on the navigation bar at the top of the page to view their open and closed applications.</span></span> <span data-ttu-id="d5101-162">Cuando los candidatos abren una de sus solicitudes, ven la etapa actual y acciones pendientes que deben completar.</span><span class="sxs-lookup"><span data-stu-id="d5101-162">When candidates open one of their applications, they see the current stage and any pending action items that they must complete.</span></span> <span data-ttu-id="d5101-163">Por ejemplo, si un candidato debe proporcionar fechas potenciales para entrevistas personales, la página muestra sus opciones.</span><span class="sxs-lookup"><span data-stu-id="d5101-163">For example, if a candidate must provide potential dates for an in-person interview, the page shows his or her options.</span></span>

## <a name="internal-jobs"></a><span data-ttu-id="d5101-164">Trabajos internos</span><span class="sxs-lookup"><span data-stu-id="d5101-164">Internal jobs</span></span>

<span data-ttu-id="d5101-165">Actualmente, los trabajos marcados como internos y enviados al sitio de Proyectos profesionales de Attract no aparecen en el sitio de Proyectos profesionales.</span><span class="sxs-lookup"><span data-stu-id="d5101-165">Currently, jobs that are marked as internal and posted to the Attract career site don't appear on the career site.</span></span> <span data-ttu-id="d5101-166">Son accesibles solo a través de la dirección URL **Solicitar** directa que puede ser copiada de la aplicación Attract.</span><span class="sxs-lookup"><span data-stu-id="d5101-166">They are accessible only via the direct **Apply** URL that can be copied from the Attract application.</span></span>

