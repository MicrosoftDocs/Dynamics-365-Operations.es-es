---
title: Integrar con LinkedIn Talent Hub
description: Este tema explica cómo configurar la integración entre Microsoft Dynamics 365 Human Resources y LinkedIn Talent Hub.
author: jaredha
manager: tfehr
ms.date: 10/20/2020
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
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4fda9d85b459d233e6239f3fcffbb48e596d4085
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114215"
---
# <a name="integrate-with-linkedin-talent-hub"></a><span data-ttu-id="8b3a1-103">Integrar con LinkedIn Talent Hub</span><span class="sxs-lookup"><span data-stu-id="8b3a1-103">Integrate with LinkedIn Talent Hub</span></span>

[!include [banner](includes/preview-feature.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="8b3a1-104">[LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub) es una plataforma de sistema de seguimiento de candidatos (ATS).</span><span class="sxs-lookup"><span data-stu-id="8b3a1-104">[LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub) is an applicant tracking system (ATS) platform.</span></span> <span data-ttu-id="8b3a1-105">Permite buscar, administrar y contratar empleados, todo en un solo lugar.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-105">It lets you source, manage, and hire employees all in one place.</span></span> <span data-ttu-id="8b3a1-106">Mediante la integración de Microsoft Dynamics 365 Human Resources con LinkedIn Talent Hub, puede crear fácilmente registros de empleados en Human Resources para los solicitantes contratados para un puesto.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-106">By integrating Microsoft Dynamics 365 Human Resources with LinkedIn Talent Hub, you can easily create employee records in Human Resources for applicants who have been hired for a position.</span></span>

## <a name="setup"></a><span data-ttu-id="8b3a1-107">Configurar</span><span class="sxs-lookup"><span data-stu-id="8b3a1-107">Setup</span></span>

<span data-ttu-id="8b3a1-108">Un administrador del sistema debe completar las tareas de configuración para permitir la integración con LinkedIn Talent Hub.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-108">A system administrator must complete setup tasks to enable integration with LinkedIn Talent Hub.</span></span> <span data-ttu-id="8b3a1-109">Primero, en el entorno de Power Apps, debe configurar un usuario y un rol de seguridad para otorgar a LinkedIn Talent Hub los permisos necesarios para escribir datos en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-109">First, in the Power Apps environment, you must set up a user and security role to grant LinkedIn Talent Hub the appropriate permissions to write data into Human Resources.</span></span>

### <a name="link-your-environment-to-linkedin-talent-hub"></a><span data-ttu-id="8b3a1-110">Vincular su entorno a LinkedIn Talent Hub</span><span class="sxs-lookup"><span data-stu-id="8b3a1-110">Link your environment to LinkedIn Talent Hub</span></span>

1. <span data-ttu-id="8b3a1-111">Abra [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub).</span><span class="sxs-lookup"><span data-stu-id="8b3a1-111">Open [LinkedIn Talent Hub](https://business.linkedin.com/talent-solutions/talent-hub).</span></span>

2. <span data-ttu-id="8b3a1-112">En el menú desplegable de usuarios, seleccione **Configuración del producto**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-112">On the user drop-down menu, select **Product Settings**.</span></span>

3. <span data-ttu-id="8b3a1-113">En el panel de navegación izquierdo, en la sección **Avanzado**, seleccione **Integraciones**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-113">In the left navigation pane, in the **Advanced** section, select **Integrations**.</span></span>

4. <span data-ttu-id="8b3a1-114">Seleccione **Autorizar** para la integración de Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-114">Select **Authorize** for the Microsoft Dynamics 365 Human Resources integration.</span></span>

5. <span data-ttu-id="8b3a1-115">En la página **Dynamics 365 Human Resources**, seleccione el entorno al que vincular LinkedIn Talent Hub y, a continuación, seleccione **Vincular**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-115">On the **Dynamics 365 Human Resources** page, select the environment to link LinkedIn Talent Hub to, and then select **Link**.</span></span>

    ![Incorporación a LinkedIn Talent Hub.](./media/hr-admin-integration-talent-hub-onboarding.jpg)

    > [!NOTE]
    > <span data-ttu-id="8b3a1-117">Puede vincular solo a entornos para los que su cuenta de usuario tenga acceso de administrador tanto al entorno de Human Resources como al entorno de Power Apps asociado.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-117">You can link only to environments where your user account has administrator access to both the Human Resources environment and the associated Power Apps environment.</span></span> <span data-ttu-id="8b3a1-118">Si no se muestra ningún entorno en la página de vínculo de Human Resources, asegúrese de que tiene entornos de Human Resources con licencia en el inquilino y que el usuario que inició sesión en la página de vínculo tiene permisos de administrador tanto para el entorno de Human Resources como para el entorno de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-118">If no environments are listed on the Human Resources link page, make sure that you have licensed Human Resources environments on the tenant, and that the user that you signed in to the link page as has administrator permissions to both the Human Resources environment and the Power Apps environment.</span></span>

### <a name="create-a-power-apps-security-role"></a><span data-ttu-id="8b3a1-119">Crear un rol de seguridad de Power Apps</span><span class="sxs-lookup"><span data-stu-id="8b3a1-119">Create a Power Apps security role</span></span>

1. <span data-ttu-id="8b3a1-120">Abra el [centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="8b3a1-120">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="8b3a1-121">En la lista **Entornos**, seleccione el entorno que está asociado al entorno de Human Resources al que desea vincular su instancia de LinkedIn Talent Hub.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-121">In the **Environments** list, select the environment that is associated with the Human Resources environment that you want to link your instance of LinkedIn Talent Hub to.</span></span>

3. <span data-ttu-id="8b3a1-122">Seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-122">Select **Settings**.</span></span>

4. <span data-ttu-id="8b3a1-123">Expanda el nodo **Usuarios + Permisos** y seleccione **Roles de seguridad**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-123">Expand the **Users + Permissions** node, and select **Security Roles**.</span></span>

5. <span data-ttu-id="8b3a1-124">En la página **Roles de seguridad**, en la barra de herramientas, seleccione **Nuevo rol**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-124">On the **Security Roles** page, on the toolbar, select **New role**.</span></span>

6. <span data-ttu-id="8b3a1-125">En la pestaña **Detalles**, escriba un nombre para el rol, como **Integración HRIS de LinkedIn Talent Hub**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-125">On the **Details** tab, enter a name for the role, such as **LinkedIn Talent Hub HRIS Integration**.</span></span>

7. <span data-ttu-id="8b3a1-126">En la pestaña **Personalización**, seleccione el permiso **Leer** de nivel de organización para las siguientes entidades:</span><span class="sxs-lookup"><span data-stu-id="8b3a1-126">On the **Customization** tab, select organization-level **Read** permission for the following entities:</span></span>

    - <span data-ttu-id="8b3a1-127">Entidad</span><span class="sxs-lookup"><span data-stu-id="8b3a1-127">Entity</span></span>
    - <span data-ttu-id="8b3a1-128">Campo</span><span class="sxs-lookup"><span data-stu-id="8b3a1-128">Field</span></span>
    - <span data-ttu-id="8b3a1-129">Relación</span><span class="sxs-lookup"><span data-stu-id="8b3a1-129">Relationship</span></span>

8. <span data-ttu-id="8b3a1-130">Guarde y cierre el rol de seguridad.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-130">Save and close the security role.</span></span>

### <a name="create-a-power-apps-application-user"></a><span data-ttu-id="8b3a1-131">Crear un usuario de aplicación de Power Apps</span><span class="sxs-lookup"><span data-stu-id="8b3a1-131">Create a Power Apps application user</span></span>

<span data-ttu-id="8b3a1-132">Hay que crear un usuario de aplicación para que el adaptador de LinkedIn Talent Hub otorgue permisos al adaptador para escribir registros de candidatos en el entorno de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-132">An application user must be created for the LinkedIn Talent Hub adapter to grant permissions to the adapter to write candidate records into the Power Apps environment.</span></span>

1. <span data-ttu-id="8b3a1-133">Abra el [centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="8b3a1-133">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="8b3a1-134">En la lista **Entornos**, seleccione el entorno que está asociado al entorno de Human Resources al que desea vincular su instancia de LinkedIn Talent Hub.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-134">In the **Environments** list, select the environment that is associated with the Human Resources environment that you want to link your instance of LinkedIn Talent Hub to.</span></span>

3. <span data-ttu-id="8b3a1-135">Seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-135">Select **Settings**.</span></span>

4. <span data-ttu-id="8b3a1-136">Expanda el nodo **Usuarios + Permisos** y seleccione **Usuarios**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-136">Expand the **Users + Permissions** node, and select **Users**.</span></span>

5. <span data-ttu-id="8b3a1-137">Seleccione **Administrar usuarios en Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-137">Select **Manage users in Dynamics 365**.</span></span>

6. <span data-ttu-id="8b3a1-138">Utilice el menú desplegable situado encima de la lista para pasar de la vista predeterminada **Usuarios habilitados** a **Usuarios de la aplicación**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-138">Use the drop-down menu above the list to change the view from the default **Enabled Users** view to **Application Users**.</span></span>

    ![Vista Usuarios de la aplicación](./media/hr-admin-integration-power-apps-application-users.jpg)

7. <span data-ttu-id="8b3a1-140">En la barra de herramientas, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-140">On the toolbar, select **New**.</span></span>

8. <span data-ttu-id="8b3a1-141">En la página **Nuevo usuario**, siga estos pasos:</span><span class="sxs-lookup"><span data-stu-id="8b3a1-141">On the **New user** page, follow these steps:</span></span>

    1. <span data-ttu-id="8b3a1-142">Cambie el valor del campo **Tipo de usuario** a **Usuario de la aplicación**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-142">Change the value of the **User type** field to **Application User**.</span></span>
    2. <span data-ttu-id="8b3a1-143">Establezca el campo **Nombre de usuario** en **Integración HRIS de LinkedIn y Dynamics365 HR**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-143">Set the **User Name** field to **Dynamics365 HR LinkedIn HRIS Integration**.</span></span>
    3. <span data-ttu-id="8b3a1-144">Establezca el campo **Id. de aplicación** en **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-144">Set the **Application ID** field to **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span></span>
    4. <span data-ttu-id="8b3a1-145">Escriba los valores que desee en los campos **Nombre**, **Apellidos** y **Correo electrónico principal**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-145">Enter any value in the **First Name**, **Last Name**, and **Primary Email** fields.</span></span>
    5. <span data-ttu-id="8b3a1-146">En la barra de herramientas, seleccione **Guardar \& Cerrar**</span><span class="sxs-lookup"><span data-stu-id="8b3a1-146">On the toolbar, select **Save \& Close**.</span></span>

### <a name="assign-a-security-role-to-the-new-user"></a><span data-ttu-id="8b3a1-147">Asignar un rol de seguridad al nuevo usuario</span><span class="sxs-lookup"><span data-stu-id="8b3a1-147">Assign a security role to the new user</span></span>

<span data-ttu-id="8b3a1-148">Después de guardar y cerrar el nuevo usuario de la aplicación en la sección anterior, volverá a la página **Lista de usuarios**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-148">After you save and close the new application user in the previous section, you're returned to the **Users list** page.</span></span>

1. <span data-ttu-id="8b3a1-149">En la página **Lista de usuarios**, cambie la vista a **Usuarios de la aplicación**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-149">On the **Users list** page, change the view to **Application Users**.</span></span>

2. <span data-ttu-id="8b3a1-150">Seleccione el usuario de la aplicación que ha creado en la sección anterior.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-150">Select the application user that you created in the previous section.</span></span>

3. <span data-ttu-id="8b3a1-151">En la barra de herramientas, seleccione **Administrar roles**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-151">On the toolbar, select **Manage Roles**.</span></span>

4. <span data-ttu-id="8b3a1-152">Seleccione el rol de seguridad que creó anteriormente para la integración.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-152">Select the security role that you created earlier for the integration.</span></span>

5. <span data-ttu-id="8b3a1-153">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-153">Select **OK**.</span></span>

### <a name="add-an-azure-active-directory-app-in-human-resources"></a><span data-ttu-id="8b3a1-154">Agregar una aplicación de Azure Active Directory a Human Resources</span><span class="sxs-lookup"><span data-stu-id="8b3a1-154">Add an Azure Active Directory app in Human Resources</span></span>

1. <span data-ttu-id="8b3a1-155">En Dynamics 365 Human Resources, abra la página **Aplicaciones de Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-155">In Dynamics 365 Human Resources, open the **Azure Active Directory applications** page.</span></span>
2. <span data-ttu-id="8b3a1-156">Agregue un registro nuevo a la lista y establezca los campos siguientes:</span><span class="sxs-lookup"><span data-stu-id="8b3a1-156">Add a new record to the list, and set the following fields:</span></span>

    - <span data-ttu-id="8b3a1-157">**Id. de cliente**: especifique **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-157">**Client ID**: Enter **3a225c96-d62a-44ce-b3ec-bd4e8e9befef**.</span></span>
    - <span data-ttu-id="8b3a1-158">**Nombre**: escriba el nombre del rol de seguridad de Power Apps que creó anteriormente, como **Integración HRIS de LinkedIn Talent Hub**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-158">**Name**: Enter the name of the Power Apps security role that you created earlier, such as **LinkedIn Talent Hub HRIS Integration**.</span></span>
    - <span data-ttu-id="8b3a1-159">**Id. de usuario**: seleccione un usuario que tenga permisos para escribir datos en Dirección de personal.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-159">**User ID**: Select a user who has permissions to write data in Personnel Management.</span></span>

### <a name="create-the-table-in-dataverse"></a><span data-ttu-id="8b3a1-160">Crear la tabla en Dataverse</span><span class="sxs-lookup"><span data-stu-id="8b3a1-160">Create the table in Dataverse</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b3a1-161">La integración con LinkedIn Talent Hub depende de tablas virtuales de Dataverse para Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-161">The integration with LinkedIn Talent Hub depends on virtual tables in Dataverse for Human Resources.</span></span> <span data-ttu-id="8b3a1-162">Como requisito previo para este paso de la configuración, debe configurar las tablas virtuales.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-162">As a prerequisite for this step in the setup, you must configure virtual tables.</span></span> <span data-ttu-id="8b3a1-163">Para obtener más información sobre cómo configurar tablas virtuales, consulte [Configurar tablas virtuales de Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span><span class="sxs-lookup"><span data-stu-id="8b3a1-163">For information about how to configure virtual tables, see [Configure Dataverse virtual tables](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).</span></span>

1. <span data-ttu-id="8b3a1-164">En Human Resources, abra la página **Integración de Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-164">In Human Resources, open the **Dataverse integration** page.</span></span>

2. <span data-ttu-id="8b3a1-165">Seleccione la pestaña **Tablas virtuales**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-165">Select the **Virtual tables** tab.</span></span>

3. <span data-ttu-id="8b3a1-166">Filtre la lista de entidades por etiqueta de entidad para encontrar **Candidato exportado de LinkedIn**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-166">Filter the entity list by entity label to find **LinkedIn exported candidate**.</span></span>

4. <span data-ttu-id="8b3a1-167">Seleccione la entidad jurídica y, a continuación, seleccione **Generar/actualizar**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-167">Select the entity, and then select **Generate/refresh**.</span></span>

## <a name="exporting-candidate-records"></a><span data-ttu-id="8b3a1-168">Exportar registros de candidatos</span><span class="sxs-lookup"><span data-stu-id="8b3a1-168">Exporting candidate records</span></span>

<span data-ttu-id="8b3a1-169">Una vez completada la configuración, los reclutadores y los profesionales de recursos humanos (RR. HH.) podrán utilizar la función **Exportar a HRIS** en LinkedIn Talent Hub para exportar registros de candidatos contratados desde LinkedIn Talent Hub a Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-169">After the setup is completed, recruiters and human resources (HR) professionals can use the **Export to HRIS** function in LinkedIn Talent Hub to export hired candidate records from LinkedIn Talent Hub to Human Resources.</span></span>

### <a name="export-records-from-linkedin-talent-hub"></a><span data-ttu-id="8b3a1-170">Exportar registros desde LinkedIn Talent Hub</span><span class="sxs-lookup"><span data-stu-id="8b3a1-170">Export records from LinkedIn Talent Hub</span></span>

<span data-ttu-id="8b3a1-171">Una vez que un candidato ha pasado por el proceso de contratación y ha sido contratado, puede exportar el registro de candidato desde LinkedIn Talent Hub a Human Resources.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-171">After a candidate has moved through the recruiting process and has been hired, you can export the candidate record from LinkedIn Talent Hub to Human Resources.</span></span>

1. <span data-ttu-id="8b3a1-172">En LinkedIn Talent Hub, abra el proyecto para el que se contrató al nuevo empleado.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-172">In LinkedIn Talent Hub, open the project that you hired the new employee for.</span></span>

2. <span data-ttu-id="8b3a1-173">Seleccione un registro de candidato.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-173">Select a candidate record.</span></span>

3. <span data-ttu-id="8b3a1-174">Seleccione **Cambiar etapa** y, a continuación, seleccione **Contratado**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-174">Select **Change stage**, and then select **Hired**.</span></span>

4. <span data-ttu-id="8b3a1-175">En el menú de puntos suspensivos (**...**) para el candidato, seleccione **Exportar a HRIS**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-175">On the ellipsis menu (**...**) for the candidate, select **Export to HRIS**.</span></span>

5. <span data-ttu-id="8b3a1-176">En el panel **Exportar a HRIS**, especifique la información que se debe exportar:</span><span class="sxs-lookup"><span data-stu-id="8b3a1-176">In the **Export to HRIS** pane, enter the information that must be exported:</span></span>

    - <span data-ttu-id="8b3a1-177">En el campo **Proveedor de HRIS**, seleccione **Microsoft Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-177">In the **HRIS provider** field, select **Microsoft Dynamics 365 Human Resources**.</span></span>
    - <span data-ttu-id="8b3a1-178">En el campo **Fecha de inicio** seleccione un valor para el nuevo empleado.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-178">In the **Start date** field, select a value for the new employee.</span></span>
    - <span data-ttu-id="8b3a1-179">En el campo **Cargo**, especifique un cargo para el trabajo del nuevo empleado.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-179">In the **Job title** field, enter a job title for the new employee's job.</span></span>
    - <span data-ttu-id="8b3a1-180">En el campo **Ubicación**, especifique la ubicación en la que estará basado el empleado.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-180">In the **Location** field, enter the location where the employee will be based.</span></span>
    - <span data-ttu-id="8b3a1-181">Escriba o compruebe la dirección de correo electrónico del empleado.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-181">Enter or verify the employee's email address.</span></span>

![Exportar al panel HRIS en LinkedIn Talent Hub](./media/hr-admin-integration-linkedin-talent-hub-export.jpg)

## <a name="complete-onboarding-in-human-resources"></a><span data-ttu-id="8b3a1-183">Completar la incorporación en Human Resources</span><span class="sxs-lookup"><span data-stu-id="8b3a1-183">Complete onboarding in Human Resources</span></span>

<span data-ttu-id="8b3a1-184">Los registros de candidatos que se exportan desde LinkedIn Talent Hub a Human Resources aparecen en la sección **Candidatos a contratar** de la página **Administración de personal**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-184">Candidate records that are exported from LinkedIn Talent Hub to Human Resources appear in the **Candidates to hire** section of the **Personnel management** page.</span></span>

1. <span data-ttu-id="8b3a1-185">En Human Resources, abra la página **Administración de personal**.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-185">In Human Resources, open the **Personnel management** page.</span></span>

2. <span data-ttu-id="8b3a1-186">En la sección **Candidatos a contratar**, seleccione **Contratar** para el candidato seleccionado.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-186">In the **Candidates to hire** section, select **Hire** for the selected candidate.</span></span>

3. <span data-ttu-id="8b3a1-187">En el cuadro de diálogo **Contratar trabajador nuevo**, revise el registro y agregue la información necesaria.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-187">In the **Hire new worker** dialog box, review the record, and add any required information.</span></span> <span data-ttu-id="8b3a1-188">También puede seleccionar el número de cargo para el que se ha contratado al candidato.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-188">You can also select the position number that the candidate has been hired for.</span></span>

<span data-ttu-id="8b3a1-189">Después de especificar la información necesaria, puede continuar con los procesos estándar para crear registros de empleados e incorporar empleados.</span><span class="sxs-lookup"><span data-stu-id="8b3a1-189">After the required information has been entered, you can continue with your standard processes for creating employee records and onboarding employees.</span></span>

<span data-ttu-id="8b3a1-190">Se importan los siguientes detalles y se incluyen en el nuevo registro de empleado:</span><span class="sxs-lookup"><span data-stu-id="8b3a1-190">The following details are imported and included on the new employee record:</span></span>

- <span data-ttu-id="8b3a1-191">Nombre</span><span class="sxs-lookup"><span data-stu-id="8b3a1-191">First name</span></span>
- <span data-ttu-id="8b3a1-192">Apellidos</span><span class="sxs-lookup"><span data-stu-id="8b3a1-192">Last name</span></span>
- <span data-ttu-id="8b3a1-193">Fecha inicial del empleo</span><span class="sxs-lookup"><span data-stu-id="8b3a1-193">Employment start date</span></span>
- <span data-ttu-id="8b3a1-194">Dirección de correo electrónico</span><span class="sxs-lookup"><span data-stu-id="8b3a1-194">Email address</span></span>
- <span data-ttu-id="8b3a1-195">Número de teléfono</span><span class="sxs-lookup"><span data-stu-id="8b3a1-195">Phone number</span></span>

## <a name="see-also"></a><span data-ttu-id="8b3a1-196">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8b3a1-196">See also</span></span>

[<span data-ttu-id="8b3a1-197">Configurar tablas virtuales de Dataverse</span><span class="sxs-lookup"><span data-stu-id="8b3a1-197">Configure Dataverse virtual tables</span></span>](./hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="8b3a1-198">¿Qué es Microsoft Dataverse?</span><span class="sxs-lookup"><span data-stu-id="8b3a1-198">What is Microsoft Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)
