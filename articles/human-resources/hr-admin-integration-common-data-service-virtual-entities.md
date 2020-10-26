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
ms.openlocfilehash: 0848b7556100fba38fcab0aa2a1a109e2e055fc9
ms.sourcegitcommit: b89baab13e530b5b1f079231619c628309a4742d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2020
ms.locfileid: "3959584"
---
# <a name="configure-common-data-service-virtual-entities"></a><span data-ttu-id="076eb-104">Configurar entidades virtuales de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="076eb-104">Configure Common Data Service virtual entities</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="076eb-105">Dynamics 365 Human Resources es una fuente de datos virtual en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="076eb-105">Dynamics 365 Human Resources is a virtual data source in Common Data Service.</span></span> <span data-ttu-id="076eb-106">Proporciona operaciones completas de creación, lectura, actualización y eliminación (CRUD) de Common Data Service y Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="076eb-106">It provides full create, read, update, and delete (CRUD) operations from Common Data Service and Microsoft Power Platform.</span></span> <span data-ttu-id="076eb-107">Los datos de las entidades virtuales no se almacenan en Common Data Service, pero en la base de datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="076eb-107">The data for virtual entities isn't stored in Common Data Service, but in the application database.</span></span> 

<span data-ttu-id="076eb-108">Permitir operaciones CRUD en entidades de Human Resources desde Common Data Service, debe hacer que las entidades estén disponibles como entidades virtuales en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="076eb-108">To enable CRUD operations on Human Resources entities from Common Data Service, you must make the entities available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="076eb-109">Esto le permite realizar operaciones CRUD desde Common Data Service y Microsoft Power Platform en datos que se encuentran en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="076eb-109">This lets you perform CRUD operations from Common Data Service and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="076eb-110">Las operaciones también respaldan las validaciones de la lógica empresarial completa de Human Resources para garantizar la integridad de los datos al escribir datos en las entidades.</span><span class="sxs-lookup"><span data-stu-id="076eb-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

## <a name="available-virtual-entities-for-human-resources"></a><span data-ttu-id="076eb-111">Entidades virtuales disponibles para Human Resources</span><span class="sxs-lookup"><span data-stu-id="076eb-111">Available virtual entities for Human Resources</span></span>

<span data-ttu-id="076eb-112">Todas las entidades de Protocolo de datos abiertos (OData) de Human Resources están disponibles como entidades virtuales en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="076eb-112">All Open Data Protocol (OData) entities in Human Resources are available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="076eb-113">También están disponibles en Power Platform.</span><span class="sxs-lookup"><span data-stu-id="076eb-113">They're also available in Power Platform.</span></span> <span data-ttu-id="076eb-114">Ahora puede crear aplicaciones y experiencias con datos directamente de Human Resources con capacidad CRUD completa, sin copiar ni sincronizar datos en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="076eb-114">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Common Data Service.</span></span> <span data-ttu-id="076eb-115">Puede usar los portales de Power Apps para construir sitios web externos que habiliten escenarios de colaboración para procesos comerciales en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="076eb-115">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="076eb-116">Puede ver la lista de entidades virtuales habilitadas en el entorno y comenzar a trabajar con las entidades en [Power Apps](https://make.powerapps.com), en la solución **Entidades virtuales de Dynamics 365 HR**.</span><span class="sxs-lookup"><span data-stu-id="076eb-116">You can view the list of virtual entities enabled in the environment, and begin working with the entities in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Entities** solution.</span></span>

![Entidades virtuales de Dynamics 365 HR en Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a><span data-ttu-id="076eb-118">Entidades virtuales versus entidades naturales</span><span class="sxs-lookup"><span data-stu-id="076eb-118">Virtual entities versus natural entities</span></span>

<span data-ttu-id="076eb-119">Las entidades virtuales de Human Resources no son lo mismo que las entidades naturales de Common Data Service creadas para Human Resources.</span><span class="sxs-lookup"><span data-stu-id="076eb-119">Virtual entities for Human Resources aren't the same as the natural Common Data Service entities created for Human Resources.</span></span> <span data-ttu-id="076eb-120">Las entidades naturales para Human Resources se generan por separado y se mantienen en la solución HCM Common en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="076eb-120">The natural entities for Human Resources are generated separately and maintained in the HCM Common solution in Common Data Service.</span></span> <span data-ttu-id="076eb-121">Con entidades naturales, los datos se almacenan en Common Data Service y requiere la sincronización con la base de datos de la aplicación de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="076eb-121">With natural entities, the data is stored in Common Data Service and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="076eb-122">Para obtener una lista de las entidades naturales de Common Data Service para Human Resources, vea[Entidades de Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="076eb-122">For a list of the natural Common Data Service entities for Human Resources, see [Common Data Service entities](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="076eb-123">Configurar</span><span class="sxs-lookup"><span data-stu-id="076eb-123">Setup</span></span>

<span data-ttu-id="076eb-124">Siga estos pasos de configuración para habilitar entidades virtuales en su entorno.</span><span class="sxs-lookup"><span data-stu-id="076eb-124">Follow these setup steps to enable virtual entities in your environment.</span></span> 

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="076eb-125">Registrar la aplicación en Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="076eb-125">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="076eb-126">En primer lugar, debe registrar la aplicación en Azure Portal para que la plataforma de identidad de Microsoft pueda proporcionar servicios de autenticación y autorización para la aplicación y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="076eb-126">First, you need to register the app in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="076eb-127">Para obtener más información sobre cómo registrar aplicaciones en Azure, consulte [Inicio rápido: registre una aplicación con la plataforma de identidad de Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="076eb-127">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="076eb-128">Abra el [portal de Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="076eb-128">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="076eb-129">En la lista de servicios de Azure, seleccione **Registros de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="076eb-129">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="076eb-130">Seleccione **Nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="076eb-130">Select **New registration**.</span></span>

4. <span data-ttu-id="076eb-131">En el campo **Nombre**, especifique un nombre descriptivo para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="076eb-131">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="076eb-132">Por ejemplo, **Entidades virtuales de Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="076eb-132">For example, **Dynamics 365 Human Resources Virtual Entities**.</span></span>

5. <span data-ttu-id="076eb-133">En el campo **Redirigir URI**, ingrese la URL del espacio de nombres de su instancia de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="076eb-133">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="076eb-134">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="076eb-134">Select **Register**.</span></span>

7. <span data-ttu-id="076eb-135">Cuando se completa el registro, Azure Portal muestra el panel **Visión de conjunto** del registro de la aplicación, que incluye su **ID de aplicación (cliente)**.</span><span class="sxs-lookup"><span data-stu-id="076eb-135">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="076eb-136">Tome nota del **ID de aplicación (cliente)** en este momento.</span><span class="sxs-lookup"><span data-stu-id="076eb-136">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="076eb-137">Ingresará esta información al [Configurar la fuente de datos de la entidad virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="076eb-137">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

8. <span data-ttu-id="076eb-138">En el panel de navegación izquierdo, seleccione **Certificados y secretos**.</span><span class="sxs-lookup"><span data-stu-id="076eb-138">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="076eb-139">En la sección **Secretos del cliente** de la página, seleccione **Nuevo secreto de cliente**.</span><span class="sxs-lookup"><span data-stu-id="076eb-139">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="076eb-140">Proporcione una descripción, seleccione una duración y seleccione **Añadir**.</span><span class="sxs-lookup"><span data-stu-id="076eb-140">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="076eb-141">Registre el valor del secreto.</span><span class="sxs-lookup"><span data-stu-id="076eb-141">Record the secret's value.</span></span> <span data-ttu-id="076eb-142">Ingresará esta información al [Configurar la fuente de datos de la entidad virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="076eb-142">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="076eb-143">Asegúrese de tomar nota del valor del secreto en este momento.</span><span class="sxs-lookup"><span data-stu-id="076eb-143">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="076eb-144">El secreto nunca se vuelve a mostrar después de salir de esta página.</span><span class="sxs-lookup"><span data-stu-id="076eb-144">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a><span data-ttu-id="076eb-145">Instalar la aplicación Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="076eb-145">Install the Dynamics 365 HR Virtual Entity app</span></span>

<span data-ttu-id="076eb-146">Instale la aplicación Dynamics 365 HR Virtual Entity en su entorno de Power Apps para implementar el paquete de solución de entidad virtual para Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="076eb-146">Install the Dynamics 365 HR Virtual Entity app in your Power Apps environment to deploy the virtual entity solution package to Common Data Service.</span></span>

1. <span data-ttu-id="076eb-147">Abra el [centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="076eb-147">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="076eb-148">En la lista **Entornos**, seleccione el entorno de Power Apps asociado a su instancia de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="076eb-148">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="076eb-149">En la sección **Recursos** de la página, seleccione **Aplicaciones de Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="076eb-149">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="076eb-150">Seleccione la acción **Instalar aplicación**.</span><span class="sxs-lookup"><span data-stu-id="076eb-150">Select the **Install app** action.</span></span>

5. <span data-ttu-id="076eb-151">Seleccione **Dynamics 365 HR Virtual Entity** y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="076eb-151">Select **Dynamics 365 HR Virtual Entity**, and select **Next**.</span></span>

6. <span data-ttu-id="076eb-152">Revise y marque para aceptar los términos de servicio.</span><span class="sxs-lookup"><span data-stu-id="076eb-152">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="076eb-153">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="076eb-153">Select **Install**.</span></span>

<span data-ttu-id="076eb-154">La instalación tarda unos minutos.</span><span class="sxs-lookup"><span data-stu-id="076eb-154">The install takes a few minutes.</span></span> <span data-ttu-id="076eb-155">Cuando se complete, continúe con los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="076eb-155">When it completes, continue to the next steps.</span></span>

![Instalar la aplicación Dynamics 365 HR Virtual Entity desde el centro de administración de Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a><span data-ttu-id="076eb-157">Configurar la fuente de datos de la entidad virtual</span><span class="sxs-lookup"><span data-stu-id="076eb-157">Configure the virtual entity data source</span></span> 

<span data-ttu-id="076eb-158">El siguiente paso es configurar la fuente de datos de la entidad virtual en el entorno de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="076eb-158">The next step is to configure the virtual entity data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="076eb-159">Abra el [centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="076eb-159">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="076eb-160">En la lista **Entornos**, seleccione el entorno de Power Apps asociado a su instancia de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="076eb-160">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="076eb-161">Seleccione la **URL del entorno** la sección **Detalles** de la página.</span><span class="sxs-lookup"><span data-stu-id="076eb-161">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="076eb-162">En el **Centro de estado de la solución**, selecciona el icono **Búsqueda avanzada** en la parte superior derecha de la página de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="076eb-162">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="076eb-163">En la página **Búsqueda avanzada**, en la lista desplegable **Buscar**, seleccione **Configuraciones de fuentes de datos virtuales de Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="076eb-163">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="076eb-164">Seleccione **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="076eb-164">Select **Results**.</span></span>

7. <span data-ttu-id="076eb-165">Seleccione el registro **Fuente de datos de recursos humanos de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="076eb-165">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="076eb-166">Ingrese la información requerida para la configuración de la fuente de datos.</span><span class="sxs-lookup"><span data-stu-id="076eb-166">Enter the required information for the data source configuration.</span></span>

   - <span data-ttu-id="076eb-167">**URL de destino**: la URL del espacio de nombres de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="076eb-167">**Target URL**: The URL of your Human Resources namespace.</span></span>
   - <span data-ttu-id="076eb-168">**ID de inquilino**: el ID de inquilino de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="076eb-168">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>
   - <span data-ttu-id="076eb-169">**ID de la aplicación de AAD**: id. de aplicación (cliente) creado para la aplicación registrada en el portal de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="076eb-169">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="076eb-170">Recibió esta información anteriormente durante el paso [Registrar la aplicación en Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="076eb-170">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>
   - <span data-ttu-id="076eb-171">**Secreto de aplicación de AAD**: secreto de aplicación creado para la aplicación registrada en el portal de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="076eb-171">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="076eb-172">Recibió esta información anteriormente durante el paso [Registrar la aplicación en Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="076eb-172">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

9. <span data-ttu-id="076eb-173">Seleccione **Guardar y cerrar**.</span><span class="sxs-lookup"><span data-stu-id="076eb-173">Select **Save & Close**.</span></span>

   ![Fuente de datos de HR de Microsoft](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="076eb-175">Conceder permisos de aplicación en Human Resources</span><span class="sxs-lookup"><span data-stu-id="076eb-175">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="076eb-176">Otorgar permisos para los las dos aplicaciones de Azure AD en Human Resources:</span><span class="sxs-lookup"><span data-stu-id="076eb-176">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="076eb-177">La aplicación creada para su inquilino en el portal de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="076eb-177">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="076eb-178">La aplicación Dynamics 365 HR Virtual Entity instalada en el entorno de Power Apps</span><span class="sxs-lookup"><span data-stu-id="076eb-178">The Dynamics 365 HR Virtual Entity app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="076eb-179">En Human Resources, abra la página **Aplicaciones de Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="076eb-179">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="076eb-180">Seleccione **Nuevo** para crear un nuevo registro de aplicación.</span><span class="sxs-lookup"><span data-stu-id="076eb-180">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="076eb-181">En el campo **Id. de cliente**, ingrese el ID de cliente de la aplicación que registró en el portal de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="076eb-181">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="076eb-182">En el campo **Nombre**, ingrese el nombre de la aplicación que registró en el portal de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="076eb-182">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="076eb-183">En el campo **ID de usuario**, seleccione el ID de un usuario con permisos de administrador en Human Resources y el entorno de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="076eb-183">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="076eb-184">Seleccione **Nuevo** para crear un segundo registro de aplicación:</span><span class="sxs-lookup"><span data-stu-id="076eb-184">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="076eb-185">**Id. de cliente**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="076eb-185">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="076eb-186">**Nombre**: Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="076eb-186">**Name**: Dynamics 365 HR Virtual Entity</span></span>
    - <span data-ttu-id="076eb-187">En el campo **ID de usuario**, seleccione el ID de un usuario con permisos de administrador en Human Resources y el entorno de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="076eb-187">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-entities"></a><span data-ttu-id="076eb-188">Generar entidades virtuales</span><span class="sxs-lookup"><span data-stu-id="076eb-188">Generate virtual entities</span></span>

<span data-ttu-id="076eb-189">Cuando se completa la configuración, puede seleccionar las entidades virtuales que desea generar y habilitar en su instancia de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="076eb-189">When setup completes, you can select the virtual entities you want to generate and enable in your Common Data Service instance.</span></span>

1. <span data-ttu-id="076eb-190">Abra el [centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="076eb-190">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="076eb-191">En la lista **Entornos**, seleccione el entorno de Power Apps asociado a su instancia de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="076eb-191">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="076eb-192">Seleccione la **URL del entorno** la sección **Detalles** de la página.</span><span class="sxs-lookup"><span data-stu-id="076eb-192">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="076eb-193">En el **Centro de estado de la solución**, selecciona el icono **Búsqueda avanzada** en la parte superior derecha de la página.</span><span class="sxs-lookup"><span data-stu-id="076eb-193">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the page.</span></span>

5. <span data-ttu-id="076eb-194">En la página **Búsqueda avanzada**, en la lista desplegable **Buscar**, seleccione **Entidades de HR disponibles**.</span><span class="sxs-lookup"><span data-stu-id="076eb-194">On the **Advanced Find** page, in the **Look for** dropdown list, select **Available HR Entities**.</span></span>

6. <span data-ttu-id="076eb-195">Utilice las opciones de filtro para encontrar la entidad o entidades que desea habilitar.</span><span class="sxs-lookup"><span data-stu-id="076eb-195">Use the filter options to find the entity or entities you want to enable.</span></span>

7. <span data-ttu-id="076eb-196">Seleccione una entidad en la lista.</span><span class="sxs-lookup"><span data-stu-id="076eb-196">Select an entity from the list.</span></span>

8. <span data-ttu-id="076eb-197">En la página de la entidad, cambie la propiedad **Ha sido generado** a **Sí** para la entidad.</span><span class="sxs-lookup"><span data-stu-id="076eb-197">On the entity page, change the **Has Been Generated** property to **Yes** for the entity.</span></span>

9. <span data-ttu-id="076eb-198">Guarde y cierre la página de entidad.</span><span class="sxs-lookup"><span data-stu-id="076eb-198">Save and close the entity page.</span></span>

> [!NOTE]
> <span data-ttu-id="076eb-199">Puede generar varias entidades virtuales a la vez utilizando la página **Cambiar varios registros**.</span><span class="sxs-lookup"><span data-stu-id="076eb-199">You can generate multiple virtual entities at once by using the **Change Multiple Records** page.</span></span> <span data-ttu-id="076eb-200">Seleccione varios registros en la página y seleccione **Editar** en la cinta.</span><span class="sxs-lookup"><span data-stu-id="076eb-200">Select multiple records on the page, and select **Edit** on the ribbon.</span></span> <span data-ttu-id="076eb-201">A continuación, puede cambiar la propiedad **Ha sido generado** para todos los registros seleccionados.</span><span class="sxs-lookup"><span data-stu-id="076eb-201">You can then change the **Has Been Generated** property for all selected records.</span></span>

![Entidades de HR disponibles](./media/hr-admin-integration-virtual-entities-available.jpg)

> [!NOTE]
> <span data-ttu-id="076eb-203">Para agilizar el proceso de generación de entidades virtuales en futuras versiones, el proceso ocurrirá en una página en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="076eb-203">To streamline the process of generating virtual entities in future releases, the process will occur in a page in Human Resources.</span></span>

## <a name="see-also"></a><span data-ttu-id="076eb-204">Consulte también</span><span class="sxs-lookup"><span data-stu-id="076eb-204">See also</span></span>

[<span data-ttu-id="076eb-205">¿Qué es Common Data Service?</span><span class="sxs-lookup"><span data-stu-id="076eb-205">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="076eb-206">Información general sobre las entidades</span><span class="sxs-lookup"><span data-stu-id="076eb-206">Entity overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="076eb-207">Descripción general de las relaciones entre entidades</span><span class="sxs-lookup"><span data-stu-id="076eb-207">Entity relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="076eb-208">Crear y editar entidades virtuales que contienen datos de una fuente de datos externa</span><span class="sxs-lookup"><span data-stu-id="076eb-208">Create and edit virtual entities that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="076eb-209">¿Que son los portales de Power Apps?</span><span class="sxs-lookup"><span data-stu-id="076eb-209">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="076eb-210">Descripción general de la creación de aplicaciones en Power Apps</span><span class="sxs-lookup"><span data-stu-id="076eb-210">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)
