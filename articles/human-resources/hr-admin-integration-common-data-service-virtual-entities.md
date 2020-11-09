---
title: Configurar entidades virtuales de Common Data Service
description: Este tema muestra cómo configurar entidades virtuales para Dynamics 365 Human Resources. Generar y actualizar entidades virtuales existentes y analizar entidades generadas y disponibles.
author: andreabichsel
manager: tfehr
ms.date: 10/05/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: CDSIntegrationAdministration
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-10-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0d6f79ea569a7a9b0d25e73e8666bf9ba19095d0
ms.sourcegitcommit: a8665c47696028d371cdc4671db1fd8fcf9e1088
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2020
ms.locfileid: "4058163"
---
# <a name="configure-common-data-service-virtual-entities"></a><span data-ttu-id="89931-104">Configurar entidades virtuales de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="89931-104">Configure Common Data Service virtual entities</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="89931-105">Dynamics 365 Human Resources es una fuente de datos virtual en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="89931-105">Dynamics 365 Human Resources is a virtual data source in Common Data Service.</span></span> <span data-ttu-id="89931-106">Proporciona operaciones completas de creación, lectura, actualización y eliminación (CRUD) de Common Data Service y Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="89931-106">It provides full create, read, update, and delete (CRUD) operations from Common Data Service and Microsoft Power Platform.</span></span> <span data-ttu-id="89931-107">Los datos de las entidades virtuales no se almacenan en Common Data Service, pero en la base de datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="89931-107">The data for virtual entities isn't stored in Common Data Service, but in the application database.</span></span> 

<span data-ttu-id="89931-108">Permitir operaciones CRUD en entidades de Human Resources desde Common Data Service, debe hacer que las entidades estén disponibles como entidades virtuales en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="89931-108">To enable CRUD operations on Human Resources entities from Common Data Service, you must make the entities available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="89931-109">Esto le permite realizar operaciones CRUD desde Common Data Service y Microsoft Power Platform en datos que se encuentran en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="89931-109">This lets you perform CRUD operations from Common Data Service and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="89931-110">Las operaciones también respaldan las validaciones de la lógica empresarial completa de Human Resources para garantizar la integridad de los datos al escribir datos en las entidades.</span><span class="sxs-lookup"><span data-stu-id="89931-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

## <a name="available-virtual-entities-for-human-resources"></a><span data-ttu-id="89931-111">Entidades virtuales disponibles para Human Resources</span><span class="sxs-lookup"><span data-stu-id="89931-111">Available virtual entities for Human Resources</span></span>

<span data-ttu-id="89931-112">Todas las entidades de Protocolo de datos abiertos (OData) de Human Resources están disponibles como entidades virtuales en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="89931-112">All Open Data Protocol (OData) entities in Human Resources are available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="89931-113">También están disponibles en Power Platform.</span><span class="sxs-lookup"><span data-stu-id="89931-113">They're also available in Power Platform.</span></span> <span data-ttu-id="89931-114">Ahora puede crear aplicaciones y experiencias con datos directamente de Human Resources con capacidad CRUD completa, sin copiar ni sincronizar datos en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="89931-114">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Common Data Service.</span></span> <span data-ttu-id="89931-115">Puede usar los portales de Power Apps para construir sitios web externos que habiliten escenarios de colaboración para procesos comerciales en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="89931-115">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="89931-116">Puede ver la lista de entidades virtuales habilitadas en el entorno y comenzar a trabajar con las entidades en [Power Apps](https://make.powerapps.com), en la solución **Entidades virtuales de Dynamics 365 HR**.</span><span class="sxs-lookup"><span data-stu-id="89931-116">You can view the list of virtual entities enabled in the environment, and begin working with the entities in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Entities** solution.</span></span>

![Entidades virtuales de Dynamics 365 HR en Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a><span data-ttu-id="89931-118">Entidades virtuales versus entidades naturales</span><span class="sxs-lookup"><span data-stu-id="89931-118">Virtual entities versus natural entities</span></span>

<span data-ttu-id="89931-119">Las entidades virtuales de Human Resources no son lo mismo que las entidades naturales de Common Data Service creadas para Human Resources.</span><span class="sxs-lookup"><span data-stu-id="89931-119">Virtual entities for Human Resources aren't the same as the natural Common Data Service entities created for Human Resources.</span></span> <span data-ttu-id="89931-120">Las entidades naturales para Human Resources se generan por separado y se mantienen en la solución HCM Common en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="89931-120">The natural entities for Human Resources are generated separately and maintained in the HCM Common solution in Common Data Service.</span></span> <span data-ttu-id="89931-121">Con entidades naturales, los datos se almacenan en Common Data Service y requiere la sincronización con la base de datos de la aplicación de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="89931-121">With natural entities, the data is stored in Common Data Service and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="89931-122">Para obtener una lista de las entidades naturales de Common Data Service para Human Resources, vea[Entidades de Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="89931-122">For a list of the natural Common Data Service entities for Human Resources, see [Common Data Service entities](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="89931-123">Configurar</span><span class="sxs-lookup"><span data-stu-id="89931-123">Setup</span></span>

<span data-ttu-id="89931-124">Siga estos pasos de configuración para habilitar entidades virtuales en su entorno.</span><span class="sxs-lookup"><span data-stu-id="89931-124">Follow these setup steps to enable virtual entities in your environment.</span></span> 

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="89931-125">Registrar la aplicación en Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="89931-125">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="89931-126">En primer lugar, debe registrar la aplicación en Azure Portal para que la plataforma de identidad de Microsoft pueda proporcionar servicios de autenticación y autorización para la aplicación y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="89931-126">First, you need to register the app in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="89931-127">Para obtener más información sobre cómo registrar aplicaciones en Azure, consulte [Inicio rápido: registre una aplicación con la plataforma de identidad de Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="89931-127">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="89931-128">Abra el [portal de Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="89931-128">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="89931-129">En la lista de servicios de Azure, seleccione **Registros de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="89931-129">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="89931-130">Seleccione **Nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="89931-130">Select **New registration**.</span></span>

4. <span data-ttu-id="89931-131">En el campo **Nombre** , especifique un nombre descriptivo para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="89931-131">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="89931-132">Por ejemplo, **Entidades virtuales de Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="89931-132">For example, **Dynamics 365 Human Resources Virtual Entities**.</span></span>

5. <span data-ttu-id="89931-133">En el campo **Redirigir URI** , ingrese la URL del espacio de nombres de su instancia de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="89931-133">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="89931-134">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="89931-134">Select **Register**.</span></span>

7. <span data-ttu-id="89931-135">Cuando se completa el registro, Azure Portal muestra el panel **Visión de conjunto** del registro de la aplicación, que incluye su **ID de aplicación (cliente)**.</span><span class="sxs-lookup"><span data-stu-id="89931-135">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="89931-136">Tome nota del **ID de aplicación (cliente)** en este momento.</span><span class="sxs-lookup"><span data-stu-id="89931-136">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="89931-137">Ingresará esta información al [Configurar la fuente de datos de la entidad virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="89931-137">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

8. <span data-ttu-id="89931-138">En el panel de navegación izquierdo, seleccione **Certificados y secretos**.</span><span class="sxs-lookup"><span data-stu-id="89931-138">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="89931-139">En la sección **Secretos del cliente** de la página, seleccione **Nuevo secreto de cliente**.</span><span class="sxs-lookup"><span data-stu-id="89931-139">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="89931-140">Proporcione una descripción, seleccione una duración y seleccione **Añadir**.</span><span class="sxs-lookup"><span data-stu-id="89931-140">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="89931-141">Registre el valor del secreto.</span><span class="sxs-lookup"><span data-stu-id="89931-141">Record the secret's value.</span></span> <span data-ttu-id="89931-142">Ingresará esta información al [Configurar la fuente de datos de la entidad virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="89931-142">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="89931-143">Asegúrese de tomar nota del valor del secreto en este momento.</span><span class="sxs-lookup"><span data-stu-id="89931-143">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="89931-144">El secreto nunca se vuelve a mostrar después de salir de esta página.</span><span class="sxs-lookup"><span data-stu-id="89931-144">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a><span data-ttu-id="89931-145">Instalar la aplicación Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="89931-145">Install the Dynamics 365 HR Virtual Entity app</span></span>

<span data-ttu-id="89931-146">Instale la aplicación Dynamics 365 HR Virtual Entity en su entorno de Power Apps para implementar el paquete de solución de entidad virtual para Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="89931-146">Install the Dynamics 365 HR Virtual Entity app in your Power Apps environment to deploy the virtual entity solution package to Common Data Service.</span></span>

1. <span data-ttu-id="89931-147">Abra el [centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="89931-147">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="89931-148">En la lista **Entornos** , seleccione el entorno de Power Apps asociado a su instancia de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="89931-148">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="89931-149">En la sección **Recursos** de la página, seleccione **Aplicaciones de Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="89931-149">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="89931-150">Seleccione la acción **Instalar aplicación**.</span><span class="sxs-lookup"><span data-stu-id="89931-150">Select the **Install app** action.</span></span>

5. <span data-ttu-id="89931-151">Seleccione **Dynamics 365 HR Virtual Entity** y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="89931-151">Select **Dynamics 365 HR Virtual Entity** , and select **Next**.</span></span>

6. <span data-ttu-id="89931-152">Revise y marque para aceptar los términos de servicio.</span><span class="sxs-lookup"><span data-stu-id="89931-152">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="89931-153">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="89931-153">Select **Install**.</span></span>

<span data-ttu-id="89931-154">La instalación tarda unos minutos.</span><span class="sxs-lookup"><span data-stu-id="89931-154">The install takes a few minutes.</span></span> <span data-ttu-id="89931-155">Cuando se complete, continúe con los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="89931-155">When it completes, continue to the next steps.</span></span>

![Instalar la aplicación Dynamics 365 HR Virtual Entity desde el centro de administración de Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a><span data-ttu-id="89931-157">Configurar la fuente de datos de la entidad virtual</span><span class="sxs-lookup"><span data-stu-id="89931-157">Configure the virtual entity data source</span></span> 

<span data-ttu-id="89931-158">El siguiente paso es configurar la fuente de datos de la entidad virtual en el entorno de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="89931-158">The next step is to configure the virtual entity data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="89931-159">Abra el [centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="89931-159">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="89931-160">En la lista **Entornos** , seleccione el entorno de Power Apps asociado a su instancia de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="89931-160">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="89931-161">Seleccione la **URL del entorno** la sección **Detalles** de la página.</span><span class="sxs-lookup"><span data-stu-id="89931-161">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="89931-162">En el **Centro de estado de la solución** , selecciona el icono **Búsqueda avanzada** en la parte superior derecha de la página de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="89931-162">In the **Solution Health Hub** , select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="89931-163">En la página **Búsqueda avanzada** , en la lista desplegable **Buscar** , seleccione **Configuraciones de fuentes de datos virtuales de Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="89931-163">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="89931-164">Seleccione **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="89931-164">Select **Results**.</span></span>

7. <span data-ttu-id="89931-165">Seleccione el registro **Fuente de datos de recursos humanos de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="89931-165">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="89931-166">Ingrese la información requerida para la configuración de la fuente de datos.</span><span class="sxs-lookup"><span data-stu-id="89931-166">Enter the required information for the data source configuration.</span></span>

   - <span data-ttu-id="89931-167">**URL de destino** : la URL del espacio de nombres de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="89931-167">**Target URL** : The URL of your Human Resources namespace.</span></span>
   - <span data-ttu-id="89931-168">**ID de inquilino** : el ID de inquilino de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="89931-168">**Tenant ID** : The Azure Active Directory (Azure AD) tenant ID.</span></span>
   - <span data-ttu-id="89931-169">**ID de la aplicación de AAD** : id. de aplicación (cliente) creado para la aplicación registrada en el portal de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="89931-169">**AAD Application ID** : The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="89931-170">Recibió esta información anteriormente durante el paso [Registrar la aplicación en Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="89931-170">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>
   - <span data-ttu-id="89931-171">**Secreto de aplicación de AAD** : secreto de aplicación creado para la aplicación registrada en el portal de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="89931-171">**AAD Application Secret** : The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="89931-172">Recibió esta información anteriormente durante el paso [Registrar la aplicación en Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="89931-172">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

9. <span data-ttu-id="89931-173">Seleccione **Guardar y cerrar**.</span><span class="sxs-lookup"><span data-stu-id="89931-173">Select **Save & Close**.</span></span>

   ![Fuente de datos de HR de Microsoft](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="89931-175">Conceder permisos de aplicación en Human Resources</span><span class="sxs-lookup"><span data-stu-id="89931-175">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="89931-176">Otorgar permisos para los las dos aplicaciones de Azure AD en Human Resources:</span><span class="sxs-lookup"><span data-stu-id="89931-176">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="89931-177">La aplicación creada para su inquilino en el portal de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="89931-177">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="89931-178">La aplicación Dynamics 365 HR Virtual Entity instalada en el entorno de Power Apps</span><span class="sxs-lookup"><span data-stu-id="89931-178">The Dynamics 365 HR Virtual Entity app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="89931-179">En Human Resources, abra la página **Aplicaciones de Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="89931-179">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="89931-180">Seleccione **Nuevo** para crear un nuevo registro de aplicación.</span><span class="sxs-lookup"><span data-stu-id="89931-180">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="89931-181">En el campo **Id. de cliente** , ingrese el ID de cliente de la aplicación que registró en el portal de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="89931-181">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="89931-182">En el campo **Nombre** , ingrese el nombre de la aplicación que registró en el portal de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="89931-182">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="89931-183">En el campo **ID de usuario** , seleccione el ID de un usuario con permisos de administrador en Human Resources y el entorno de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="89931-183">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="89931-184">Seleccione **Nuevo** para crear un segundo registro de aplicación:</span><span class="sxs-lookup"><span data-stu-id="89931-184">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="89931-185">**Id. de cliente** : f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="89931-185">**Client Id** : f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="89931-186">**Nombre** : Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="89931-186">**Name** : Dynamics 365 HR Virtual Entity</span></span>
    - <span data-ttu-id="89931-187">En el campo **ID de usuario** , seleccione el ID de un usuario con permisos de administrador en Human Resources y el entorno de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="89931-187">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-entities"></a><span data-ttu-id="89931-188">Generar entidades virtuales</span><span class="sxs-lookup"><span data-stu-id="89931-188">Generate virtual entities</span></span>

<span data-ttu-id="89931-189">Cuando se completa la configuración, puede seleccionar las entidades virtuales que desea generar y habilitar en su instancia de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="89931-189">When setup completes, you can select the virtual entities you want to generate and enable in your Common Data Service instance.</span></span>

1. <span data-ttu-id="89931-190">En Human Resources, abra la página **Integración de Common Data Service (CDS)**.</span><span class="sxs-lookup"><span data-stu-id="89931-190">In Human Resources, open the **Common Data Service (CDS) integration** page.</span></span>

2. <span data-ttu-id="89931-191">Seleccione la pestaña **Entidades virtuales**.</span><span class="sxs-lookup"><span data-stu-id="89931-191">Select the **Virtual entities** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="89931-192">El botón de alternancia **Habilitar la entidad virtual** se establecerá en **Sí** automáticamente cuando se haya completado toda la configuración necesaria.</span><span class="sxs-lookup"><span data-stu-id="89931-192">The **Enable the virtual entity** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="89931-193">Si el botón de alternancia está configurado en **No** , revise los pasos de las secciones anteriores de este documento para asegurarse de completar toda la configuración los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="89931-193">If the toggle is set to **No** , review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="89931-194">Seleccione la entidad (o entidades) que desea generar en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="89931-194">Select the entity or entities you want to generate in Common Data Service.</span></span>

4. <span data-ttu-id="89931-195">Seleccione **Generar/actualizar**.</span><span class="sxs-lookup"><span data-stu-id="89931-195">Select **Generate/refresh**.</span></span>

![Integración de Common Data Service](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-entity-generation-status"></a><span data-ttu-id="89931-197">Comprobar el estado de generación de la entidad</span><span class="sxs-lookup"><span data-stu-id="89931-197">Check entity generation status</span></span>

<span data-ttu-id="89931-198">Las entidades virtuales se generan en Common Data Service mediante un proceso asincrónico en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="89931-198">Virtual entities are generated in Common Data Service through an asynchronous background process.</span></span> <span data-ttu-id="89931-199">Actualizaciones de la visualización del proceso en el centro de actividades.</span><span class="sxs-lookup"><span data-stu-id="89931-199">Updates on the process display in the action center.</span></span> <span data-ttu-id="89931-200">Los detalles del proceso, incluidos los registros de errores, aparecen en la página **Automatizaciones de procesos**.</span><span class="sxs-lookup"><span data-stu-id="89931-200">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="89931-201">En Recursos humanos, abra la página **Automatizaciones de procesos**.</span><span class="sxs-lookup"><span data-stu-id="89931-201">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="89931-202">Seleccione la pestaña **Procesos en segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="89931-202">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="89931-203">Seleccione **Proceso en segundo plano de operación asincrónica de sondeo de entidad virtual**.</span><span class="sxs-lookup"><span data-stu-id="89931-203">Select **Virtual entity poll async operation background process**.</span></span>

4. <span data-ttu-id="89931-204">Seleccione **Ver los resultados más recientes**.</span><span class="sxs-lookup"><span data-stu-id="89931-204">Select **View most recent results**.</span></span>

<span data-ttu-id="89931-205">El panel deslizante muestra los resultados de ejecución más recientes del proceso.</span><span class="sxs-lookup"><span data-stu-id="89931-205">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="89931-206">Puede ver el registro del proceso, que incluye los errores devueltos por Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="89931-206">You can view the log for the process, including any errors returned from Common Data Service.</span></span>

## <a name="see-also"></a><span data-ttu-id="89931-207">Consulte también</span><span class="sxs-lookup"><span data-stu-id="89931-207">See also</span></span>

[<span data-ttu-id="89931-208">¿Qué es Common Data Service?</span><span class="sxs-lookup"><span data-stu-id="89931-208">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="89931-209">Información general sobre las entidades</span><span class="sxs-lookup"><span data-stu-id="89931-209">Entity overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="89931-210">Descripción general de las relaciones entre entidades</span><span class="sxs-lookup"><span data-stu-id="89931-210">Entity relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="89931-211">Crear y editar entidades virtuales que contienen datos de una fuente de datos externa</span><span class="sxs-lookup"><span data-stu-id="89931-211">Create and edit virtual entities that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="89931-212">¿Que son los portales de Power Apps?</span><span class="sxs-lookup"><span data-stu-id="89931-212">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="89931-213">Descripción general de la creación de aplicaciones en Power Apps</span><span class="sxs-lookup"><span data-stu-id="89931-213">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)
