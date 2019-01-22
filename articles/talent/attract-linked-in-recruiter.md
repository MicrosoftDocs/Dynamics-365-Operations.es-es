---
title: Abastecimiento con LinkedIn Recruiter
description: "Este tema proporciona información sobre el uso del aprendizaje automático para obtener recomendaciones del trabajo y del candidato de trabajo."
author: josaw
manager: AnnBe
ms.date: 12/07/2018
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
ms.search.industry: 
ms.author: josaw
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: be66d9f95551066bb8bc25445c652d4fa59066d4
ms.openlocfilehash: 9bb323728923ff3b09ff0bfba3849f3c5d84eb34
ms.contentlocale: es-es
ms.lasthandoff: 12/07/2018

---

# <a name="sourcing-with-linkedin-recruiter"></a><span data-ttu-id="756a9-103">Abastecimiento con LinkedIn Recruiter</span><span class="sxs-lookup"><span data-stu-id="756a9-103">Sourcing with LinkedIn Recruiter</span></span>
[!include[banner](../includes/banner.md)]

<span data-ttu-id="756a9-104">LinkedIn es la base de datos más grande del mundo y a menudo el principal sistema que los reclutadores utilizan para buscar candidatos, comunicarse con ellos y conseguir candidatos para trabajos que los reclutadores quieren cubrir.</span><span class="sxs-lookup"><span data-stu-id="756a9-104">LinkedIn is the world’s largest talent database and often the primary system that recruiters use to find, communicate with, and source candidates for the jobs that recruiters are looking to fill.</span></span> <span data-ttu-id="756a9-105">La integración de LinkedIn Recruiter con Dynamics 365 for Talent: Attract facilita que los usuarios empleen, y conserven los datos en sincronización entre los dos sistemas.</span><span class="sxs-lookup"><span data-stu-id="756a9-105">LinkedIn Recruiter integration with Dynamics 365 for Talent: Attract makes it easier for users to hire, and to keep the data in sync between the two systems.</span></span>

> [!NOTE]
> <span data-ttu-id="756a9-106">Necesita el complemento de contratación completa y usuarios de Linkedin Recruiter para poder usar la integración de LinkedIn Recruiter con Attract.</span><span class="sxs-lookup"><span data-stu-id="756a9-106">You need the Comprehensive hiring add-on and LinkedIn Recruiter seats to be able to use LinkedIn Recruiter integration with Attract.</span></span>

## <a name="set-up-linkedin-recruiter-with-attract"></a><span data-ttu-id="756a9-107">Configuración de LinkedIn Recruiter con Attract</span><span class="sxs-lookup"><span data-stu-id="756a9-107">Set up LinkedIn Recruiter with Attract</span></span> 

<span data-ttu-id="756a9-108">Para poder usar las capacidades de LinkedIn Recruiter, debe configurar el acceso de nivel de contrato o de nivel de emrpesa con su instancia de Attract.</span><span class="sxs-lookup"><span data-stu-id="756a9-108">Before you can use the LinkedIn Recruiter capabilities, you must configure contract-level or company-level access with your Attract instance.</span></span> <span data-ttu-id="756a9-109">Para completar el proceso de configuración, debe trabajar con el usuario que es un administrador en su contrato de LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="756a9-109">To complete the configuration process, you must work with the user who is an Admin on your LinkedIn Recruiter contract.</span></span> <span data-ttu-id="756a9-110">Realice los pasos siguientes para configurar LinkedIn Recruiter con Attract.</span><span class="sxs-lookup"><span data-stu-id="756a9-110">Complete the following steps to configure LinkedIn Recruiter with Attract.</span></span>

1.  <span data-ttu-id="756a9-111">Inicie sesión en Attract como administrador y vaya a **Configuración de administrador**.</span><span class="sxs-lookup"><span data-stu-id="756a9-111">Sign in to Attract as an Admin and go to **Admin Settings**.</span></span>

2.  <span data-ttu-id="756a9-112">En el panel izquierdo, haga clic en la pestaña **Integración de LinkedIn**.</span><span class="sxs-lookup"><span data-stu-id="756a9-112">On the left pane, click the **LinkedIn Integration** tab.</span></span>

<span data-ttu-id="756a9-113">[![Vista de administrador de Attract para iniciar la integración de LinkedIn Recruiter](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)</span><span class="sxs-lookup"><span data-stu-id="756a9-113">[![Attract Admin view to start LinkedIn Recruiter integration](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)</span></span>

3.  <span data-ttu-id="756a9-114">Haga clic en **Conectar** para iniciar la configuración y obtener orientación durante el proceso de inicio de sesión en LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="756a9-114">Click **Connect** to start the setup and be guided through the LinkedIn sign-in process.</span></span>

4.  <span data-ttu-id="756a9-115">Si tiene usuarios en varios contratos de LinkedIn, seleccione el contrato que desea conectar al sistema de Attract.</span><span class="sxs-lookup"><span data-stu-id="756a9-115">If you have seats on multiple LinkedIn contracts, select the contract that you would like to connect to the Attract system.</span></span> <span data-ttu-id="756a9-116">Si tiene un usuario solo en un contrato de LinkedIn, este paso no será necesario.</span><span class="sxs-lookup"><span data-stu-id="756a9-116">If you have a seat on only one LinkedIn contract, this step will not be needed.</span></span>

5.  <span data-ttu-id="756a9-117">El widget de LinkedIn ahora se cargará en la configuración de administrado con la lista de integraciones mostrada.</span><span class="sxs-lookup"><span data-stu-id="756a9-117">The LinkedIn widget will now load in your Admin settings with the list of integrations shown.</span></span> <span data-ttu-id="756a9-118">En **Sistema de reclutador conectar**, haga clic en **Solicitar**.</span><span class="sxs-lookup"><span data-stu-id="756a9-118">Under **Recruiter System connect**, click **Request**.</span></span>

<span data-ttu-id="756a9-119">[![Vista de administrador de Attract para solicitar la integración de LinkedIn Recruiter](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)</span><span class="sxs-lookup"><span data-stu-id="756a9-119">[![Attract Admin view to Request LinkedIn Recruiter integration](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)</span></span>

6.  <span data-ttu-id="756a9-120">Después de que se solicite la integración desde Attract, se mostrará como **Listo para socios** y estará listo para activarse desde **Configuración de gestión de reclutador**.</span><span class="sxs-lookup"><span data-stu-id="756a9-120">After the integration is requested from Attract, it will show as **Partner ready** and is ready to be turned on from **Recruiter Admin settings**.</span></span> <span data-ttu-id="756a9-121">Si ve **Notificar al socio** en esta página, espere unos segundos, haga clic en **Notificar al socio**, y actualice la página.</span><span class="sxs-lookup"><span data-stu-id="756a9-121">If you see **Notify partner** on this page, wait a few seconds, click **Notify partner**, and then refresh the page.</span></span> <span data-ttu-id="756a9-122">Debe ahora mostrarse como **Listo para socios**.</span><span class="sxs-lookup"><span data-stu-id="756a9-122">It should now show as **Partner ready**.</span></span>

<span data-ttu-id="756a9-123">[![Vista de gestión de Attract para indicar que el lado de Attract de las solicitudes se ha realizado](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)</span><span class="sxs-lookup"><span data-stu-id="756a9-123">[![Attract Admin view to indicate Attract side of requests have been completed](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)</span></span>

<span data-ttu-id="756a9-124">Para completar el paso siguiente, debe tener un privilegio de administración en su contrato de LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="756a9-124">To complete the next step, you need to have an Admin privilege on your LinkedIn Recruiter Contract.</span></span>

7.  <span data-ttu-id="756a9-125">Inicie sesión en LinkedIn mediante la cuenta de administración y vaya al LinkedIn Recruiter en la parte superior derecha.</span><span class="sxs-lookup"><span data-stu-id="756a9-125">Sign in to LinkedIn using the Admin account and go to LinkedIn Recruiter on the top right.</span></span> 

8. <span data-ttu-id="756a9-126">En el menú **Más** en la parte superior de la pantalla, haga clic en **Valores de administración**, y haga clic en la pestaña **ATS** .</span><span class="sxs-lookup"><span data-stu-id="756a9-126">On the **More** menu at the top of the screen, click **Admin Settings**, and then click the **ATS** Tab.</span></span>

<span data-ttu-id="756a9-127">El sistema de Attract se mostrará con un par de opciones que se pueden activar.</span><span class="sxs-lookup"><span data-stu-id="756a9-127">The Attract system will be listed with a couple of options that can be turned on.</span></span>

9. <span data-ttu-id="756a9-128">Si desea permitir solo una exportación en 1 clic para el **Indicador en ATS** y el **Widget del perfil En ATS**, seleccione **Acceso de nivel de empresa**.</span><span class="sxs-lookup"><span data-stu-id="756a9-128">If you want to enable only 1-Click export for the **In-ATS indicator** and the **In-ATS Profile Widget**, select **Company-level access**.</span></span> <span data-ttu-id="756a9-129">Si desea habilitar todas las funciones de acceso de nivel de empresa más el historial de InMail, el historial de notas y el acceso de perfil del comprobante de InMail, seleccione **Acceso de nivel de contrato**.</span><span class="sxs-lookup"><span data-stu-id="756a9-129">If you want to enable all of Company-level access features plus InMail history, Notes history, and the InMail stub profile access, select **Contract-level access**.</span></span>

10. <span data-ttu-id="756a9-130">Conecte el nivel de acceso deseado desde su configuración **Admin-ATS** de LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="756a9-130">Turn on the desired access level from your LinkedIn Recruiter **Admin-ATS** settings.</span></span>

<span data-ttu-id="756a9-131">[![Activar la integración de Attract desde la vista de administración de LinkedIn Recruiter](./media/EnableRSC.png)](./media/EnableRSC.png)</span><span class="sxs-lookup"><span data-stu-id="756a9-131">[![Turn on Attract integration from LinkedIn Recruiter Admin view](./media/EnableRSC.png)](./media/EnableRSC.png)</span></span>

12. <span data-ttu-id="756a9-132">Vuelva a la configuración de gestión de Attract como AttractAdmin y seleccione la pestaña **Integración de LinkedIn**. Ahora debe ver la carga del widget de LinkedIn mostrando **Habilitado** con el nivel de acceso seleccionado activado.</span><span class="sxs-lookup"><span data-stu-id="756a9-132">Go back to Attract Admin Settings as an AttractAdmin and select the **LinkedIn integration** tab. You should now see the LinkedIn widget load showing **Enabled** with the selected access level turned on.</span></span>

<span data-ttu-id="756a9-133">[![Integración de LinkedIn Recruiter completa](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)</span><span class="sxs-lookup"><span data-stu-id="756a9-133">[![LinkedIn Recruiter integration complete](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)</span></span>

## <a name="using-linkedin-recruiter-capabilities"></a><span data-ttu-id="756a9-134">Uso de las capacidades de LinkedIn Recruiter</span><span class="sxs-lookup"><span data-stu-id="756a9-134">Using LinkedIn Recruiter capabilities</span></span>

<span data-ttu-id="756a9-135">Después de que las capacidades de LinkedIn Recruiter hayan sido habilitadas por el administrador de Attract, están disponibles para que los administradores y los reclutadores de contratación puedan acceder a ellas.</span><span class="sxs-lookup"><span data-stu-id="756a9-135">After LinkedIn Recruiter capabilities has been enabled by the Attract Admin it is available for hiring managers and recruiters to access.</span></span> <span data-ttu-id="756a9-136">Para usar estas capacidades, conecte su cuenta de LinkedIn en **Configuración del usuario**.</span><span class="sxs-lookup"><span data-stu-id="756a9-136">To use these capabilities, connect your LinkedIn account under **User Settings**.</span></span> <span data-ttu-id="756a9-137">Varias capacidades estarán disponibles después de que se hayan conectado la configuración de gestión y de usuario.</span><span class="sxs-lookup"><span data-stu-id="756a9-137">Several capabilities will be available after both the Admin and User settings have been connected.</span></span>

### <a name="in-ats-profile-widget"></a><span data-ttu-id="756a9-138">Widget del perfil En ATS</span><span class="sxs-lookup"><span data-stu-id="756a9-138">In-ATS profile widget</span></span>

<span data-ttu-id="756a9-139">Puede ver el perfil de LinkedIn del candidato en Attract.</span><span class="sxs-lookup"><span data-stu-id="756a9-139">You can view the candidate’s LinkedIn profile in Attract.</span></span> <span data-ttu-id="756a9-140">El widget de LinkedIn mostrará el perfil del candidato cuando la información de ATS coincida con la información de LinkedIn de sus usuarios.</span><span class="sxs-lookup"><span data-stu-id="756a9-140">The LinkedIn widget will display the candidate profile when the ATS information matches the LinkedIn information of its users.</span></span>

<span data-ttu-id="756a9-141">Para ver un perfil, vaya el perfil del candidato desde un trabajo o un grupo de talentos.</span><span class="sxs-lookup"><span data-stu-id="756a9-141">To view a profile, go the candidate profile either from a job or talent pool.</span></span> <span data-ttu-id="756a9-142">En el perfil del candidato, seleccione la pestaña **LinkedIn** y el widget del perfil se cargará.</span><span class="sxs-lookup"><span data-stu-id="756a9-142">In the candidate profile, select the **LinkedIn** tab and the profile widget will load.</span></span> <span data-ttu-id="756a9-143">También puede guardar el candidato en sus proyectos de LinkedIn Recruiter en esta página.</span><span class="sxs-lookup"><span data-stu-id="756a9-143">You can also save the candidate to your LinkedIn Recruiter projects from this page.</span></span>
1. <span data-ttu-id="756a9-144">Si LinkedIn ha encontrado la coincidencia basándose en el correo electrónico y el ID de miembro de LinkedIn (coincidencia exacta), el perfil del candidato se mostrará.</span><span class="sxs-lookup"><span data-stu-id="756a9-144">If LinkedIn found the match based on email and LinkedIn member ID (exact match), the candidate's profile will be shown.</span></span> <span data-ttu-id="756a9-145">El usuario aún le queda una opción para vincular/desvincular el perfil.</span><span class="sxs-lookup"><span data-stu-id="756a9-145">The user still has an option to link/unlink the profile.</span></span>

2. <span data-ttu-id="756a9-146">Si LinkedIn no puede encontrar el candidato basándose en su correo electrónico o el Id de miembro, se mostrará una lista de coincidencias de posibles de candidatos basadas en el nombre del candidato y el usuario puede elegir a uno de ellos y vincular el perfil.</span><span class="sxs-lookup"><span data-stu-id="756a9-146">If LinkedIn cannot find the candidate based on their email or member ID, it will show a list of possible candidate matches based on candidate name and the user can choose one of them and link the profile.</span></span>  

3. <span data-ttu-id="756a9-147">Si LinkedIn no puede encontrar ningún candidato basándose en el nombre, indicará que no se han encontrado ninguna coincidencia.</span><span class="sxs-lookup"><span data-stu-id="756a9-147">If LinkedIn cannot find any candidate based on the name, it will return that no match was found.</span></span>

### <a name="1-click-export"></a><span data-ttu-id="756a9-148">Exportación en 1 clic</span><span class="sxs-lookup"><span data-stu-id="756a9-148">1-click export</span></span> 

<span data-ttu-id="756a9-149">Mientras busca candidatos en LinkedIn, puede exportar el candidato en 1 clic a los trabajos que tiene ahora vacantes.</span><span class="sxs-lookup"><span data-stu-id="756a9-149">While sourcing candidates in LinkedIn, you can 1-click export the candidate to the jobs that you currently have open.</span></span> <span data-ttu-id="756a9-150">Realice los pasos siguientes para una exportación en 1 clic.</span><span class="sxs-lookup"><span data-stu-id="756a9-150">Complete the following steps for a 1-click export.</span></span> <span data-ttu-id="756a9-151">Para completar estos pasos, compruebe que se le asigne el rol de administrador de contratación o de reclutador para el trabajo y que el trabajo esté en la etapa **cliente potencial**.</span><span class="sxs-lookup"><span data-stu-id="756a9-151">Before you complete these steps, verify that you are a assigned the role of Hiring manager or Recruiter for the job and that the job has a **Prospect** stage.</span></span>

1.  <span data-ttu-id="756a9-152">Cree el trabajo, asigne los roles adecuados, y active el trabajo.</span><span class="sxs-lookup"><span data-stu-id="756a9-152">Create the job, assign the appropriate roles, and activate the job.</span></span>

2.  <span data-ttu-id="756a9-153">Cuando se activa el trabajo, desplácese hasta LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="756a9-153">When the job is activated, navigate to LinkedIn Recruiter.</span></span>

3.  <span data-ttu-id="756a9-154">Encuentre el candidato que está buscando y vaya a su perfil.</span><span class="sxs-lookup"><span data-stu-id="756a9-154">Find the candidate that you are looking for and go to their profile.</span></span>

4.  <span data-ttu-id="756a9-155">Usando el cuadro de búsqueda de la tarjeta de contacto, busque el trabajo mediante el título o el identificador de trabajo que se ha activado en Attract.</span><span class="sxs-lookup"><span data-stu-id="756a9-155">Using the job search box in the contact card, find the job using the title or the Job ID that was activated in Attract.</span></span> <span data-ttu-id="756a9-156">Si no encuentra el trabajo, haga clic en **Cambiar ATS** para encontrar la instancia de Attract correcta.</span><span class="sxs-lookup"><span data-stu-id="756a9-156">If you don’t find the job, click **Change ATS** to find the correct Attract instance.</span></span>

5. <span data-ttu-id="756a9-157">Tras seleccionar el trabajo, haga clic en **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="756a9-157">After the job is selected, click **Export**.</span></span> <span data-ttu-id="756a9-158">Ahora Attract obtiene al candidato.</span><span class="sxs-lookup"><span data-stu-id="756a9-158">The candidate is now fetched by Attract.</span></span>

6.  <span data-ttu-id="756a9-159">Vaya a Attract y abra el trabajo respectivo.</span><span class="sxs-lookup"><span data-stu-id="756a9-159">Go to Attract and open the respective job.</span></span> <span data-ttu-id="756a9-160">Puede encontrar el candidato que acaba de exportar en la etapa **cliente potencial** del trabajo.</span><span class="sxs-lookup"><span data-stu-id="756a9-160">You will find the candidate that you just exported in the **Prospect** stage of the job.</span></span>

### <a name="in-ats-indicator"></a><span data-ttu-id="756a9-161">Indicador en la solicitud de presupuesto</span><span class="sxs-lookup"><span data-stu-id="756a9-161">In-ATS indicator</span></span> 

<span data-ttu-id="756a9-162">Usando LinkedIn Recruiter, puede saber si un candidato ha solicitado otros trabajos en su organización, ver en qué etapa están de la solicitud de trabajo y consultar comentarios de Attract en LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="756a9-162">Using LinkedIn recruiter, you can track whether a candidate has applied to other jobs in your organization, look at where they are in different stages of job applications, and view the feedback and comments from Attract in LinkedIn Recruiter.</span></span>

1.  <span data-ttu-id="756a9-163">Abra LinkedIn Recruiter y encuentre el perfil del candidato que busca.</span><span class="sxs-lookup"><span data-stu-id="756a9-163">Open LinkedIn Recruiter and locate the candidate profile that you are looking for.</span></span>

2.  <span data-ttu-id="756a9-164">Trasládese hacia abajo para ver la sección **En-ATS** en el perfil del candidato.</span><span class="sxs-lookup"><span data-stu-id="756a9-164">Scroll down to view the **In-ATS** section on the candidate’s profile.</span></span>

3.  <span data-ttu-id="756a9-165">Puede usar este widget para ver toda la información sobre el candidato que se encuentra en Attract desde la vista de LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="756a9-165">You can use this widget to view all of the information about the candidate that’s present in Attract from within the LinkedIn Recruiter view.</span></span>

4.  <span data-ttu-id="756a9-166">Seleccione la pestaña **Trabajos y estados** para ver los trabajos de los que forman parte, el último estado, y cómo han avanzado en cada trabajo.</span><span class="sxs-lookup"><span data-stu-id="756a9-166">Select the **Jobs & Statuses** tab to see jobs they are part of, the latest status, and how they have been moving against each job.</span></span>

5.  <span data-ttu-id="756a9-167">Seleccione la pestaña **Comentarios sobre la entrevista** para consultar los comentarios que los entrevistadores han registrado en Attract.</span><span class="sxs-lookup"><span data-stu-id="756a9-167">Select the **Interview Feedback** tab to see feedback that the interviewers have submitted in Attract.</span></span>

6.  <span data-ttu-id="756a9-168">Seleccione la pestaña **Notas** para ver las notas que se han capturado para este candidato en Attract.</span><span class="sxs-lookup"><span data-stu-id="756a9-168">Select the **Notes** tab to see notes that have been captured for this applicant in Attract.</span></span>

> [!NOTE]
> <span data-ttu-id="756a9-169">El candidato y los datos de la aplicación no se sincronizarán con el reclutador de LinkedIn si el candidato no ha pasado de la etapa de cliente potencial.</span><span class="sxs-lookup"><span data-stu-id="756a9-169">Candidate and application data will not be synced to LinkedIn Recruiter if the candidate hasn't moved past the prospect stage.</span></span>

### <a name="inmail-history"></a><span data-ttu-id="756a9-170">Historial de InMail</span><span class="sxs-lookup"><span data-stu-id="756a9-170">InMail history</span></span>

<span data-ttu-id="756a9-171">El historial de LinkedIn InMail está disponible con acceso de nivel de contrato con LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="756a9-171">The LinkedIn InMail history is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="756a9-172">Cuando se habilita, puede ver el historial completo de InMail con el candidato.</span><span class="sxs-lookup"><span data-stu-id="756a9-172">When it is enabled, you can view your entire InMail history with the candidate.</span></span> <span data-ttu-id="756a9-173">También puede ver quién más de su organización ha intercambiado InMail con el candidato, aunque no puede ver los mensajes intercambiados entre ellos.</span><span class="sxs-lookup"><span data-stu-id="756a9-173">You can also see who else from your organization has exchanged InMail with the candidate, however you can't view the messages between them.</span></span>

<span data-ttu-id="756a9-174">Para ver el historial de InMail, vaya al perfil de un candidato, vaya a la ficha **LinkedIn** y desplácese a la parte inferior de la página para ver el historial.</span><span class="sxs-lookup"><span data-stu-id="756a9-174">To view InMail history, go to a candidate’s profile, go to the **LinkedIn** tab and scroll to the bottom of the page to view the history.</span></span> <span data-ttu-id="756a9-175">Puede ver el historial de InMail si ha tenido una conversación con el candidato.</span><span class="sxs-lookup"><span data-stu-id="756a9-175">You can view InMail history if you have had a discussion with the candidate.</span></span> <span data-ttu-id="756a9-176">Los mensajes de InMail se sincronizarán con Attract cada par de horas.</span><span class="sxs-lookup"><span data-stu-id="756a9-176">The messages from InMail will sync with Attract every couple of hours.</span></span>

### <a name="notes-history"></a><span data-ttu-id="756a9-177">Historial de notas</span><span class="sxs-lookup"><span data-stu-id="756a9-177">Notes history</span></span> 

<span data-ttu-id="756a9-178">El notas de LinkedIn están disponibles con acceso de nivel de contrato con LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="756a9-178">The LinkedIn notes history is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="756a9-179">Cuando se habilitan, puede ver las notas sobre el candidato que han sido capturadas por varios reclutadores de su organización.</span><span class="sxs-lookup"><span data-stu-id="756a9-179">When it is enabled, you can view the notes that have been captured about the candidate by different recruiters from your organization.</span></span>

<span data-ttu-id="756a9-180">Para ver el historial de notas, vaya al perfil de un candidato, vaya a la ficha **LinkedIn** y desplácese a la parte inferior de la página para ver el historial.</span><span class="sxs-lookup"><span data-stu-id="756a9-180">To view Notes history, go to a candidate’s profile, go to the **LinkedIn** tab and scroll to the bottom of the page to view the history.</span></span> <span data-ttu-id="756a9-181">Puede ver todas las notas sobre el candidato desde LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="756a9-181">You can view all the notes about the candidate from LinkedIn Recruiter.</span></span>

### <a name="inmail-stub-profile"></a><span data-ttu-id="756a9-182">Perfil del comprobante de InMail</span><span class="sxs-lookup"><span data-stu-id="756a9-182">InMail stub profile</span></span>

<span data-ttu-id="756a9-183">El perfil del comprobante de InMail está disponible con acceso de nivel de contrato con LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="756a9-183">The InMail stub profile is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="756a9-184">Si los candidatos aceptan compartir sus perfiles de LinkedIn con cualquier usuario de su organización, puede realizar el seguimiento de los candidatos en Attract y se creará un registro de candidato nuevo para cada candidato.</span><span class="sxs-lookup"><span data-stu-id="756a9-184">If candidates agree to share their LinkedIn profiles with any user in your organization, you can track the candidates in Attract and a new candidate record will be created for each candidate.</span></span> <span data-ttu-id="756a9-185">Puede ver la dirección de correo electrónico del candidato si el candidato ya existe en el sistema con una dirección de correo electrónico o ha elegido compartir la dirección con el reclutador.</span><span class="sxs-lookup"><span data-stu-id="756a9-185">You can view candidate's email address if the candidate already exists in the system with an email address or has chosen to share their address with the recruiter.</span></span>

<span data-ttu-id="756a9-186">Para ver la lista de candidatos, vaya a **Grupos de talentos** para ver un grupo de talentos de LinkedIn creado por el sistema.</span><span class="sxs-lookup"><span data-stu-id="756a9-186">To view the list of candidates, go to **Talent pools** to see a system-created LinkedIn talent pool.</span></span> <span data-ttu-id="756a9-187">Este grupo de talentos contiene la lista de candidatos y sus perfiles de comprobante tal y como se recibieron de LinkedIn, donde se muestra el nombre del candidato y sus apellidos.</span><span class="sxs-lookup"><span data-stu-id="756a9-187">This talent pool contains the list candidates and their stub profiles as received from LinkedIn, showing the candidate's first name and last name.</span></span> <span data-ttu-id="756a9-188">El identificador de correo electrónico del candidato se mostrará si el candidato había elegido compartir su dirección de correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="756a9-188">The candidate’s email ID will be displayed if the candidate had chosen to share their email address.</span></span>
