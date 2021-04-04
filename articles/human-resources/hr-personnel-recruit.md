---
title: Contratar candidatos de trabajo
description: Este tema muestra cómo contratar candidatos en Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6aca285133495dfe023dfd18bdeb050aabcafee6
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478293"
---
# <a name="recruit-job-candidates"></a><span data-ttu-id="0e2f3-103">Contratar candidatos de trabajo</span><span class="sxs-lookup"><span data-stu-id="0e2f3-103">Recruit job candidates</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="0e2f3-104">Dynamics 365 Human Resources le ayuda a administrar las solicitudes de contratación.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-104">Dynamics 365 Human Resources helps you to manage recruiting requests.</span></span> <span data-ttu-id="0e2f3-105">También le ayuda a realizar una transición sin problemas de candidatos de puestos de trabajo a empleados.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-105">It also helps you seamlessly transition job candidates to employees.</span></span> <span data-ttu-id="0e2f3-106">Si su organización usa una aplicación de contratación independiente, su proceso de contratación puede incluir los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="0e2f3-106">If your organization uses a separate recruiting application, your recruiting process might include the following steps:</span></span>

- <span data-ttu-id="0e2f3-107">Introduzca su solicitud de contratación en Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-107">Enter your recruiting request in Human Resources.</span></span>
- <span data-ttu-id="0e2f3-108">Reciba referencias de candidatos en Human Resources desde la aplicación de contratación.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-108">Receive candidate referrals in Human Resources from the recruiting application.</span></span>
- <span data-ttu-id="0e2f3-109">Completa el proceso de aprobación de candidatos en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-109">Complete the candidate approval process in Human Resources.</span></span>

<span data-ttu-id="0e2f3-110">Si no está usando una aplicación de contratación independiente, también puede administrar candidatos manualmente en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-110">If you aren't using a separate recruiting application, you can also manually manage candidates in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="0e2f3-111">Si es administrador o desarrollador, y desea integrar Human Resources con una aplicación de contratación de terceros, consulte [Configurar la integración de Dataverse](hr-admin-integration-common-data-service.md) y [Configurar las tablas virtuales de Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)</span><span class="sxs-lookup"><span data-stu-id="0e2f3-111">If you're an admin or developer and want to integrate Human Resources with a third-party recruiting application, see [Configure Dataverse integration](hr-admin-integration-common-data-service.md) and [Configure Dataverse virtual tables](hr-admin-integration-common-data-service-virtual-entities.md)</span></span>
>
> <span data-ttu-id="0e2f3-112">También puede encontrar aplicaciones de integración de contratación en [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).</span><span class="sxs-lookup"><span data-stu-id="0e2f3-112">You can also find recruiting integration apps on [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).</span></span>
>
> <span data-ttu-id="0e2f3-113">Para probar nuestra característica en vista previa para la integración con LinkedIn Talent Hub, consulte [Integrar con LinkedIn Talent Hub](hr-admin-integration-linkedin.md).</span><span class="sxs-lookup"><span data-stu-id="0e2f3-113">To try out our preview feature for integrating with LinkedIn Talent Hub, see [Integrate with LinkedIn Talent Hub](hr-admin-integration-linkedin.md).</span></span>

## <a name="enable-recruiting-requests"></a><span data-ttu-id="0e2f3-114">Habilitar solicitudes de contratación</span><span class="sxs-lookup"><span data-stu-id="0e2f3-114">Enable recruiting requests</span></span>

<span data-ttu-id="0e2f3-115">Si desea enviar solicitudes de contratación en Human Resources, debe habilitar primero la funcionalidad en **Parámetros compartidos de recursos humanos**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-115">If you want to submit recruiting requests in Human Resources, you must first enable the functionality in **Human resources shared parameters**.</span></span>

1. <span data-ttu-id="0e2f3-116">En el espacio de trabajo **Administración de personal**, seleccione **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-116">In the **Personnel management** workspace, select **Links**.</span></span>

2. <span data-ttu-id="0e2f3-117">En **Configuración**, seleccione **Parámetros compartidos de Recursos Humanos**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-117">Under **Setup**, select **Human resources shared parameters**.</span></span>

3. <span data-ttu-id="0e2f3-118">En la pestaña **Contratación**, en **CONTRATACIÓN**, establezca **Habilitar solicitudes de contratación** en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-118">On the **Recruitment** tab, under **RECRUITING**, set **Enable recruiting requests** to **Yes**.</span></span>

## <a name="add-a-recruiting-request-location"></a><span data-ttu-id="0e2f3-119">Agregar una ubicación de solicitud de contratación</span><span class="sxs-lookup"><span data-stu-id="0e2f3-119">Add a recruiting request location</span></span>

<span data-ttu-id="0e2f3-120">Si su organización tiene varias ubicaciones, puede agregarlas para que los solicitantes puedan seleccionar una ubicación donde trabajará el nuevo empleado.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-120">If your organization has multiple locations, you can add them so requestors can select a location where the new recruit will be working.</span></span> <span data-ttu-id="0e2f3-121">La ubicación se incluirá en la publicación del trabajo.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-121">The location will be included in the job posting.</span></span>

1. <span data-ttu-id="0e2f3-122">En la barra de búsqueda, introduzca **ubicación de la solicitud de contratación**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-122">In the search bar, enter **recruiting request location**.</span></span>

2. <span data-ttu-id="0e2f3-123">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-123">Select **New**.</span></span>

3. <span data-ttu-id="0e2f3-124">En el campo **Ubicación de la solicitud de contratación**, introduzca el nombre de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-124">In the **Recruiting request location** field, enter the location name.</span></span>

   ![Agregar una ubicación de solicitud de contratación](./media/hr-recruit-0a-add-location.png)

4. <span data-ttu-id="0e2f3-126">En la **Descripción**, escriba una descripción para la ubicación.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-126">In the **Description**, enter a description for the location.</span></span>

5. <span data-ttu-id="0e2f3-127">En **Ubicación**, seleccione **Agregar**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-127">Under **Location**, select **Add**.</span></span> <span data-ttu-id="0e2f3-128">Si aparece la ventana emergente **Nueva dirección**, introduzca la dirección de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-128">If the **New address** popout appears, enter the address for the location.</span></span>

   ![Especificar dirección](./media/hr-recruit-0b-address.png)

6. <span data-ttu-id="0e2f3-130">En **Información del contacto**, introduzca la información del contacto de la ubicación.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-130">Under **Contact information**, enter the information for the location's contact.</span></span>

7. <span data-ttu-id="0e2f3-131">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-131">Select **Save**.</span></span>

## <a name="add-a-recruiting-request"></a><span data-ttu-id="0e2f3-132">Agregar una solicitud de contratación</span><span class="sxs-lookup"><span data-stu-id="0e2f3-132">Add a recruiting request</span></span>

<span data-ttu-id="0e2f3-133">Los responsables pueden enviar solicitudes de contratación en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-133">Managers can submit recruiting requests in Human Resources.</span></span> <span data-ttu-id="0e2f3-134">Si usa una solicitud de contratación independiente, al completar estos pasos se enviará una solicitud de contratación e iniciará el proceso de contratación en esa aplicación.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-134">If you use a separate recruiting application, completing these steps will send a recruiting request and start the recruiting process in that application.</span></span> <span data-ttu-id="0e2f3-135">De lo contrario, complete este procedimiento para comenzar el flujo de trabajo para su propio proceso de contratación interno.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-135">Otherwise, complete this procedure to begin the workflow for your own internal recruiting process.</span></span>

1. <span data-ttu-id="0e2f3-136">Seleccione **Autoservicio para empleados**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-136">Select **Employee self service**.</span></span>

2. <span data-ttu-id="0e2f3-137">Seleccione la pestaña **Mi equipo**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-137">Select the **My team** tab.</span></span>

3. <span data-ttu-id="0e2f3-138">Seleccione **Solicitud de contratación**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-138">Select  **Request to recruit**.</span></span>

   ![Iniciar una solicitud de contratación](./media/hr-recruit-1-request-to-recruit.png)

4. <span data-ttu-id="0e2f3-140">Complete los campos **Descripción**, **Trabajo** y **Fecha de inicio estimada**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-140">Complete the **Description**, **Job**, and **Estimated start date** fields.</span></span>

   ![Completar la solicitud de contratación](./media/hr-recruit-2-request-to-recruit.png)

5. <span data-ttu-id="0e2f3-142">Seleccione **Continuar**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-142">Select **Continue**.</span></span> <span data-ttu-id="0e2f3-143">Aparece la solicitud de contratación para su puesto.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-143">The recruiting request for your position appears.</span></span>

6. <span data-ttu-id="0e2f3-144">En **General**, seleccione un contratante el menú desplegable **Contratante** y, a continuación, seleccione una ubicación en el menú desplegable **Ubicación de la solicitud de contratación**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-144">Under **General**, select a recruiter from the **Recruiter** dropdown, and then select a location from the **Recruiting request location** dropdown.</span></span>

7. <span data-ttu-id="0e2f3-145">En **Trabajo**, cambie cualquier información según sea necesario y, a continuación, seleccione **Crear detalles a partir del trabajo**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-145">Under **Job**, change any information as needed, and then select **Create details from job**.</span></span>

   ![Crear detalles desde el trabajo](./media/hr-recruit-3-create-details-from-job.png)

   <span data-ttu-id="0e2f3-147">El resto de la solicitud de contratación se completará con la información predeterminada para el trabajo que ha introducido.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-147">The rest of the recruiting request will populate with the default information for the job you entered.</span></span>

8. <span data-ttu-id="0e2f3-148">En **Descripción externa**, introduzca una descripción de trabajo externa.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-148">Under **External description**, enter an external-facing job description.</span></span>

9. <span data-ttu-id="0e2f3-149">En **Puestos**, seleccione **Agregar** y, a continuación, un puesto para esta solicitud de contratación.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-149">Under **Positions**, select **Add**, and then select a position for this recruiting request.</span></span>

   ![Agregar un puesto](./media/hr-recruit-4-select-position.png)

10. <span data-ttu-id="0e2f3-151">En **Aptitudes**, seleccione **Agregar** y, a continuación, una aptitud.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-151">Under **Skills**, select **Add**, and then select a skill.</span></span>

11. <span data-ttu-id="0e2f3-152">En **Requisitos educativos**, seleccione **Agregar** y, a continuación, seleccione valores en los menús desplegables **Aptitudes** y **Nivel de formación**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-152">Under **Educational requirements**, select **Add**, and then select values from the **Education** and **Level of education** dropdowns.</span></span>

   ![Agregar requisitos educativos](./media/hr-recruit-5-select-educational-requirements.png)

12. <span data-ttu-id="0e2f3-154">En **Comentario**, agregue comentarios según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-154">Under **Comment**, add comments as necessary.</span></span>

13. <span data-ttu-id="0e2f3-155">En **Compensación**, seleccione un nivel en el menú desplegable **Nivel** y luego ajuste **Umbral inferior**, **Punto de control** y **Umbral superior** según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-155">Under **Compensation**, select a level from the **Level** dropdown, and then adjust **Low threshold**, **Control point**, and **High threshold** as necessary.</span></span>

14. <span data-ttu-id="0e2f3-156">Cuando se complete su solicitud de contratación y esté listo para iniciar el proceso de contratación, seleccione **Activar** en la barra de menús.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-156">When your recruiting request is complete and you're ready to start the recruiting process, select **Activate** in the menu bar.</span></span>

   ![Activar solicitud de contratación](./media/hr-recruit-6-activate-recruit-request.png)

15. <span data-ttu-id="0e2f3-158">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-158">Select **Save**.</span></span>

## <a name="view-and-edit-your-recruiting-requests"></a><span data-ttu-id="0e2f3-159">Ver y editar sus solicitudes de contratación</span><span class="sxs-lookup"><span data-stu-id="0e2f3-159">View and edit your recruiting requests</span></span>

<span data-ttu-id="0e2f3-160">Si es un responsable y desea ver sus propias solicitudes:</span><span class="sxs-lookup"><span data-stu-id="0e2f3-160">If you're a manager and want to view your own requests:</span></span>

1. <span data-ttu-id="0e2f3-161">Seleccione **Autoservicio para empleados**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-161">Select **Employee self service**.</span></span>

2. <span data-ttu-id="0e2f3-162">Seleccione la pestaña **Mi equipo**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-162">Select the **My team** tab.</span></span>

3. <span data-ttu-id="0e2f3-163">En **Información de mi equipo**, seleccione la pestaña **Solicitudes de contratación**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-163">Under **My team information**, select the **Recruiting requests** tab.</span></span>

   ![Seleccionar la pestaña Solicitudes de contratación](./media/hr-recruit-7-recruiting-requests.png)

4. <span data-ttu-id="0e2f3-165">Para ver o editar una solicitud de contratación, selecciónela en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-165">To view or edit a recruiting request, select it in the grid.</span></span>

<span data-ttu-id="0e2f3-166">Si es un profesional de recursos humanos y desea ver todas las solicitudes de contratación:</span><span class="sxs-lookup"><span data-stu-id="0e2f3-166">If you're an HR pro and want to view all recruiting requests:</span></span>

1. <span data-ttu-id="0e2f3-167">Seleccione **Administración de personal**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-167">Select **Personnel management**.</span></span>

2. <span data-ttu-id="0e2f3-168">Seleccione **Solicitudes de contratación**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-168">Select **Recruiting requests**.</span></span>

   ![Ver solicitudes de contratación en Administración de personal](./media/hr-recruit-8-recruiting-requests-personnel-management.png)

3. <span data-ttu-id="0e2f3-170">Para ver o editar una solicitud de contratación, selecciónela en la cuadrícula.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-170">To view or edit a recruiting request, select it in the grid.</span></span>

## <a name="add-or-edit-a-candidate-profile"></a><span data-ttu-id="0e2f3-171">Agregar o editar un perfil de candidato</span><span class="sxs-lookup"><span data-stu-id="0e2f3-171">Add or edit a candidate profile</span></span>

<span data-ttu-id="0e2f3-172">Si su organización se ha integrado con otra aplicación para administrar las solicitudes de contratación, las solicitudes de contratación se reenvían a esa aplicación.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-172">If your organization has integrated with another application to manage recruiting requests, recruiting requests are forwarded to that application.</span></span> <span data-ttu-id="0e2f3-173">Luego, la aplicación de contratación devuelve la información del candidato a Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-173">The recruiting application then sends candidate information back to Human Resources.</span></span> <span data-ttu-id="0e2f3-174">De lo contrario, puede seguir sus propios procesos de contratación internos e introducir la información del candidato manualmente.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-174">Otherwise, you can follow your own internal recruiting processes and enter candidate information manually.</span></span>

1. <span data-ttu-id="0e2f3-175">Seleccione **Administración de personal**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-175">Select **Personnel management**.</span></span>

2. <span data-ttu-id="0e2f3-176">Seleccione **Vínculos**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-176">Select **Links**.</span></span>

3. <span data-ttu-id="0e2f3-177">En **Contratación**, seleccione **Candidatos**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-177">Under **Recruiting**, select **Candidates**.</span></span>

   ![Ver candidatos](./media/hr-recruit-9-candidates.png)

4. <span data-ttu-id="0e2f3-179">Para agregar un candidato, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-179">To add a candidate, select **New**.</span></span> <span data-ttu-id="0e2f3-180">Para editar un candidato existente, selecciónelo en la lista y después seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-180">To edit an existing candidate, select the candidate from the list and then select **Edit**.</span></span> <span data-ttu-id="0e2f3-181">Aparece el perfil del candidato.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-181">The candidate profile appears.</span></span>

5. <span data-ttu-id="0e2f3-182">En **Resumen del candidato**, introduzca o edite la información del candidato según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-182">Under **Candidate summary**, enter or edit the candidate information as necessary.</span></span>

6. <span data-ttu-id="0e2f3-183">En **Solicitud de reclutamiento**, seleccione una solicitud de contratación a la que vincular al candidato.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-183">Under **Recruiting request**, select a recruiting request to link the candidate to.</span></span> <span data-ttu-id="0e2f3-184">A continuación, complete los campos **Fecha de inicio estimada**, **Responsable de contratación**, **Puesto** y **Descripción** según sea apropiado.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-184">Then complete the **Estimated start date**, **Hiring manager**, **Position**, and **Description fields** as appropriate.</span></span>

   ![Vincular a la solicitud de contratación](./media/hr-recruit-10-link-to-recruiting-request.png)

7. <span data-ttu-id="0e2f3-186">Complete toda la información en las siguientes áreas que desea incluir en el registro del candidato:</span><span class="sxs-lookup"><span data-stu-id="0e2f3-186">Complete all the information in the following areas that you want to include in the candidate's record:</span></span>
   - <span data-ttu-id="0e2f3-187">**Comentarios**</span><span class="sxs-lookup"><span data-stu-id="0e2f3-187">**Comments**</span></span>
   - <span data-ttu-id="0e2f3-188">**Experiencia profesional**</span><span class="sxs-lookup"><span data-stu-id="0e2f3-188">**Professional experience**</span></span>
   - <span data-ttu-id="0e2f3-189">**Información de contacto**</span><span class="sxs-lookup"><span data-stu-id="0e2f3-189">**Contact information**</span></span>
   - <span data-ttu-id="0e2f3-190">**Formación**</span><span class="sxs-lookup"><span data-stu-id="0e2f3-190">**Education**</span></span>
   - <span data-ttu-id="0e2f3-191">**Aptitudes**</span><span class="sxs-lookup"><span data-stu-id="0e2f3-191">**Skills**</span></span>
   - <span data-ttu-id="0e2f3-192">**Certificados**</span><span class="sxs-lookup"><span data-stu-id="0e2f3-192">**Certificates**</span></span>
   - <span data-ttu-id="0e2f3-193">**Filtrados**</span><span class="sxs-lookup"><span data-stu-id="0e2f3-193">**Screenings**</span></span>

8. <span data-ttu-id="0e2f3-194">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-194">Select **Save**.</span></span>

## <a name="hire-a-candidate"></a><span data-ttu-id="0e2f3-195">Contratar un candidato</span><span class="sxs-lookup"><span data-stu-id="0e2f3-195">Hire a candidate</span></span>

<span data-ttu-id="0e2f3-196">Cuando esté listo para contratar a un candidato, siga este procedimiento para hacer la transición del candidato a empleado.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-196">When you're ready to hire a candidate, follow this procedure to transition the candidate to an employee.</span></span>

1. <span data-ttu-id="0e2f3-197">En el formulario del candidato, seleccione **Contratar**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-197">On the candidate form, select **Hire**.</span></span>

   ![Contratar un candidato](./media/hr-recruit-11-hire.png)

2. <span data-ttu-id="0e2f3-199">En el formulario **Contratar nuevo trabajador**, en **Detalles**, complete todos los campos.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-199">On the **Hire new worker** form, under **Details**, complete all the fields.</span></span>

   ![Introducir los detalles de la nueva contratación](./media/hr-recruit-12-hire-new-worker.png)

3. <span data-ttu-id="0e2f3-201">En **Detalles del puesto**, compruebe y cambie la información según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-201">Under **Position details**, verify and change information as necessary.</span></span>

4. <span data-ttu-id="0e2f3-202">En **Listas de comprobación de incorporación**, seleccione las listas de comprobación de incorporación relevantes para este empleado.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-202">Under **Onboarding checklists**, select the relevant onboarding checklists for this employee.</span></span>

5. <span data-ttu-id="0e2f3-203">Seleccione **Continuar** para crear el registro de empleado.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-203">Select **Continue** to create the employee record.</span></span>

   >[!NOTE]
   ><span data-ttu-id="0e2f3-204">Dependiendo de los flujos de trabajo de su organización, el registro de candidato puede pasar por pasos de aprobación adicionales antes de convertirse en un registro de empleado.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-204">Depending on your organization's workflows, the candidate record may go through additional approval steps before becoming an employee record.</span></span>

## <a name="decide-not-to-hire-a-candidate"></a><span data-ttu-id="0e2f3-205">Decide no contratar a un candidato</span><span class="sxs-lookup"><span data-stu-id="0e2f3-205">Decide not to hire a candidate</span></span>

<span data-ttu-id="0e2f3-206">Si decide no contratar a un candidato, siga este procedimiento para eliminarlo del proceso de examen.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-206">If you decide not to hire a candidate, follow this procedure to remove them from the vetting process.</span></span> 

1. <span data-ttu-id="0e2f3-207">En el formulario del candidato, seleccione **No contratar**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-207">On the candidate form, select **Do not hire**.</span></span>

   ![No contratar candidato](./media/hr-recruit-13-do-not-hire.png)

2. <span data-ttu-id="0e2f3-209">Seleccione un **Código de motivo** e incluya cualquier comentario.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-209">Select a **Reason code** and include any comments.</span></span>

3. <span data-ttu-id="0e2f3-210">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-210">Select **OK**.</span></span>

## <a name="dismiss-a-candidate"></a><span data-ttu-id="0e2f3-211">Descartar un candidato</span><span class="sxs-lookup"><span data-stu-id="0e2f3-211">Dismiss a candidate</span></span>

<span data-ttu-id="0e2f3-212">Si es necesario, puede despedir a un candidato después de contratarlo.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-212">If needed, you can dismiss a candidate after hiring them.</span></span> <span data-ttu-id="0e2f3-213">Por ejemplo, un candidato puede rechazar su oferta o no presentarse el primer día.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-213">For example, a candidate might reject your offer or not show up on their first day.</span></span>

- <span data-ttu-id="0e2f3-214">En el formulario del candidato, seleccione **Despedir candidato**.</span><span class="sxs-lookup"><span data-stu-id="0e2f3-214">On the candidate form, select **Dismiss candidate**.</span></span>

  ![Descartar candidato](./media/hr-recruit-14-dismiss-candidate.png)

## <a name="see-also"></a><span data-ttu-id="0e2f3-216">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0e2f3-216">See also</span></span>

[<span data-ttu-id="0e2f3-217">Configurar tablas virtuales de Dataverse</span><span class="sxs-lookup"><span data-stu-id="0e2f3-217">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="0e2f3-218">Organizar los recursos</span><span class="sxs-lookup"><span data-stu-id="0e2f3-218">Organize your workforce</span></span>](hr-personnel-departments-jobs-positions.md)<br>
[<span data-ttu-id="0e2f3-219">Configurar los componentes de un trabajo</span><span class="sxs-lookup"><span data-stu-id="0e2f3-219">Set up the components of a job</span></span>](hr-personnel-jobs.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
