---
title: Configurar entidades virtuales de Common Data Service
description: Este tema muestra cómo configurar entidades virtuales para Dynamics 365 Human Resources. Generar y actualizar entidades virtuales existentes y analizar entidades generadas y disponibles.
author: andreabichsel
manager: tfehr
ms.date: 11/02/2020
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
ms.openlocfilehash: 2b590faeab600d04c9d5303693ec1e9ac682250d
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/25/2020
ms.locfileid: "4645610"
---
# <a name="configure-common-data-service-virtual-entities"></a><span data-ttu-id="7525e-104">Configurar entidades virtuales de Common Data Service</span><span class="sxs-lookup"><span data-stu-id="7525e-104">Configure Common Data Service virtual entities</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="7525e-105">Dynamics 365 Human Resources es una fuente de datos virtual en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="7525e-105">Dynamics 365 Human Resources is a virtual data source in Common Data Service.</span></span> <span data-ttu-id="7525e-106">Proporciona operaciones completas de creación, lectura, actualización y eliminación (CRUD) de Common Data Service y Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="7525e-106">It provides full create, read, update, and delete (CRUD) operations from Common Data Service and Microsoft Power Platform.</span></span> <span data-ttu-id="7525e-107">Los datos de las entidades virtuales no se almacenan en Common Data Service, pero en la base de datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7525e-107">The data for virtual entities isn't stored in Common Data Service, but in the application database.</span></span> 

<span data-ttu-id="7525e-108">Permitir operaciones CRUD en entidades de Human Resources desde Common Data Service, debe hacer que las entidades estén disponibles como entidades virtuales en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="7525e-108">To enable CRUD operations on Human Resources entities from Common Data Service, you must make the entities available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="7525e-109">Esto le permite realizar operaciones CRUD desde Common Data Service y Microsoft Power Platform en datos que se encuentran en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7525e-109">This lets you perform CRUD operations from Common Data Service and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="7525e-110">Las operaciones también respaldan las validaciones de la lógica empresarial completa de Human Resources para garantizar la integridad de los datos al escribir datos en las entidades.</span><span class="sxs-lookup"><span data-stu-id="7525e-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

## <a name="available-virtual-entities-for-human-resources"></a><span data-ttu-id="7525e-111">Entidades virtuales disponibles para Human Resources</span><span class="sxs-lookup"><span data-stu-id="7525e-111">Available virtual entities for Human Resources</span></span>

<span data-ttu-id="7525e-112">Todas las entidades de Protocolo de datos abiertos (OData) de Human Resources están disponibles como entidades virtuales en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="7525e-112">All Open Data Protocol (OData) entities in Human Resources are available as virtual entities in Common Data Service.</span></span> <span data-ttu-id="7525e-113">También están disponibles en Power Platform.</span><span class="sxs-lookup"><span data-stu-id="7525e-113">They're also available in Power Platform.</span></span> <span data-ttu-id="7525e-114">Ahora puede crear aplicaciones y experiencias con datos directamente de Human Resources con capacidad CRUD completa, sin copiar ni sincronizar datos en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="7525e-114">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Common Data Service.</span></span> <span data-ttu-id="7525e-115">Puede usar los portales de Power Apps para construir sitios web externos que habiliten escenarios de colaboración para procesos comerciales en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7525e-115">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="7525e-116">Puede ver la lista de entidades virtuales habilitadas en el entorno y comenzar a trabajar con las entidades en [Power Apps](https://make.powerapps.com), en la solución **Entidades virtuales de Dynamics 365 HR**.</span><span class="sxs-lookup"><span data-stu-id="7525e-116">You can view the list of virtual entities enabled in the environment, and begin working with the entities in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Entities** solution.</span></span>

![Entidades virtuales de Dynamics 365 HR en Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-entities-versus-natural-entities"></a><span data-ttu-id="7525e-118">Entidades virtuales versus entidades naturales</span><span class="sxs-lookup"><span data-stu-id="7525e-118">Virtual entities versus natural entities</span></span>

<span data-ttu-id="7525e-119">Las entidades virtuales de Human Resources no son lo mismo que las entidades naturales de Common Data Service creadas para Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7525e-119">Virtual entities for Human Resources aren't the same as the natural Common Data Service entities created for Human Resources.</span></span> <span data-ttu-id="7525e-120">Las entidades naturales para Human Resources se generan por separado y se mantienen en la solución HCM Common en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="7525e-120">The natural entities for Human Resources are generated separately and maintained in the HCM Common solution in Common Data Service.</span></span> <span data-ttu-id="7525e-121">Con entidades naturales, los datos se almacenan en Common Data Service y requiere la sincronización con la base de datos de la aplicación de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7525e-121">With natural entities, the data is stored in Common Data Service and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="7525e-122">Para obtener una lista de las entidades naturales de Common Data Service para Human Resources, vea[Entidades de Common Data Service](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="7525e-122">For a list of the natural Common Data Service entities for Human Resources, see [Common Data Service entities](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="7525e-123">Configurar</span><span class="sxs-lookup"><span data-stu-id="7525e-123">Setup</span></span>

<span data-ttu-id="7525e-124">Siga estos pasos de configuración para habilitar entidades virtuales en su entorno.</span><span class="sxs-lookup"><span data-stu-id="7525e-124">Follow these setup steps to enable virtual entities in your environment.</span></span>

### <a name="enable-virtual-entities-in-human-resources"></a><span data-ttu-id="7525e-125">Habilitar entidades virtuales en Human Resources</span><span class="sxs-lookup"><span data-stu-id="7525e-125">Enable virtual entities in Human Resources</span></span>

<span data-ttu-id="7525e-126">Primero, debe habilitar las entidades virtuales en el espacio de trabajo **Administración de características**.</span><span class="sxs-lookup"><span data-stu-id="7525e-126">First, you must enable virtual entities in the **Feature management** workspace.</span></span>

1. <span data-ttu-id="7525e-127">En Human Resources, seleccione **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="7525e-127">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="7525e-128">Seleccione la ventana **Gestión de funciones**.</span><span class="sxs-lookup"><span data-stu-id="7525e-128">Select the **Feature management** tile.</span></span>

3. <span data-ttu-id="7525e-129">Seleccione **Soporte de entidad virtual en HR/CDS** y, a continuación, **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="7525e-129">Select **Virtual Entity support in HR/CDS**, and then select **Enable**.</span></span>

<span data-ttu-id="7525e-130">Para obtener más información sobre cómo habilitar y deshabilitar características, consulte [Administrar características](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="7525e-130">For more information about enabling and disabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="7525e-131">Registrar la aplicación en Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="7525e-131">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="7525e-132">Debe registrar su instancia de Human Resources en Azure Portal para que la plataforma de identidad de Microsoft pueda proporcionar servicios de autenticación y autorización para la aplicación y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="7525e-132">You must register your Human Resources instance in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="7525e-133">Para obtener más información sobre cómo registrar aplicaciones en Azure, consulte [Inicio rápido: registre una aplicación con la plataforma de identidad de Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="7525e-133">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="7525e-134">Abra el [portal de Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="7525e-134">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="7525e-135">En la lista de servicios de Azure, seleccione **Registros de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="7525e-135">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="7525e-136">Seleccione **Nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="7525e-136">Select **New registration**.</span></span>

4. <span data-ttu-id="7525e-137">En el campo **Nombre**, especifique un nombre descriptivo para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7525e-137">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="7525e-138">Por ejemplo, **Entidades virtuales de Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="7525e-138">For example, **Dynamics 365 Human Resources Virtual Entities**.</span></span>

5. <span data-ttu-id="7525e-139">En el campo **Redirigir URI**, ingrese la URL del espacio de nombres de su instancia de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7525e-139">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="7525e-140">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="7525e-140">Select **Register**.</span></span>

7. <span data-ttu-id="7525e-141">Cuando se completa el registro, Azure Portal muestra el panel **Visión de conjunto** del registro de la aplicación, que incluye su **ID de aplicación (cliente)**.</span><span class="sxs-lookup"><span data-stu-id="7525e-141">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="7525e-142">Tome nota del **ID de aplicación (cliente)** en este momento.</span><span class="sxs-lookup"><span data-stu-id="7525e-142">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="7525e-143">Ingresará esta información al [Configurar la fuente de datos de la entidad virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="7525e-143">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

8. <span data-ttu-id="7525e-144">En el panel de navegación izquierdo, seleccione **Certificados y secretos**.</span><span class="sxs-lookup"><span data-stu-id="7525e-144">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="7525e-145">En la sección **Secretos del cliente** de la página, seleccione **Nuevo secreto de cliente**.</span><span class="sxs-lookup"><span data-stu-id="7525e-145">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="7525e-146">Proporcione una descripción, seleccione una duración y seleccione **Añadir**.</span><span class="sxs-lookup"><span data-stu-id="7525e-146">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="7525e-147">Registre el valor del secreto.</span><span class="sxs-lookup"><span data-stu-id="7525e-147">Record the secret's value.</span></span> <span data-ttu-id="7525e-148">Ingresará esta información al [Configurar la fuente de datos de la entidad virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span><span class="sxs-lookup"><span data-stu-id="7525e-148">You'll enter this information when you [Configure the virtual entity data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-entity-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7525e-149">Asegúrese de tomar nota del valor del secreto en este momento.</span><span class="sxs-lookup"><span data-stu-id="7525e-149">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="7525e-150">El secreto nunca se vuelve a mostrar después de salir de esta página.</span><span class="sxs-lookup"><span data-stu-id="7525e-150">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-entity-app"></a><span data-ttu-id="7525e-151">Instalar la aplicación Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="7525e-151">Install the Dynamics 365 HR Virtual Entity app</span></span>

<span data-ttu-id="7525e-152">Instale la aplicación Dynamics 365 HR Virtual Entity en su entorno de Power Apps para implementar el paquete de solución de entidad virtual para Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="7525e-152">Install the Dynamics 365 HR Virtual Entity app in your Power Apps environment to deploy the virtual entity solution package to Common Data Service.</span></span>

1. <span data-ttu-id="7525e-153">Abra el [centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="7525e-153">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="7525e-154">En la lista **Entornos**, seleccione el entorno de Power Apps asociado a su instancia de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7525e-154">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="7525e-155">En la sección **Recursos** de la página, seleccione **Aplicaciones de Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="7525e-155">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="7525e-156">Seleccione la acción **Instalar aplicación**.</span><span class="sxs-lookup"><span data-stu-id="7525e-156">Select the **Install app** action.</span></span>

5. <span data-ttu-id="7525e-157">Seleccione **Dynamics 365 HR Virtual Entity** y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="7525e-157">Select **Dynamics 365 HR Virtual Entity**, and select **Next**.</span></span>

6. <span data-ttu-id="7525e-158">Revise y marque para aceptar los términos de servicio.</span><span class="sxs-lookup"><span data-stu-id="7525e-158">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="7525e-159">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="7525e-159">Select **Install**.</span></span>

<span data-ttu-id="7525e-160">La instalación tarda unos minutos.</span><span class="sxs-lookup"><span data-stu-id="7525e-160">The install takes a few minutes.</span></span> <span data-ttu-id="7525e-161">Cuando se complete, continúe con los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="7525e-161">When it completes, continue to the next steps.</span></span>

![Instalar la aplicación Dynamics 365 HR Virtual Entity desde el centro de administración de Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-entity-data-source"></a><span data-ttu-id="7525e-163">Configurar la fuente de datos de la entidad virtual</span><span class="sxs-lookup"><span data-stu-id="7525e-163">Configure the virtual entity data source</span></span> 

<span data-ttu-id="7525e-164">El siguiente paso es configurar la fuente de datos de la entidad virtual en el entorno de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="7525e-164">The next step is to configure the virtual entity data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="7525e-165">Abra el [centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="7525e-165">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="7525e-166">En la lista **Entornos**, seleccione el entorno de Power Apps asociado a su instancia de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7525e-166">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="7525e-167">Seleccione la **URL del entorno** la sección **Detalles** de la página.</span><span class="sxs-lookup"><span data-stu-id="7525e-167">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="7525e-168">En el **Centro de estado de la solución**, selecciona el icono **Búsqueda avanzada** en la parte superior derecha de la página de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="7525e-168">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="7525e-169">En la página **Búsqueda avanzada**, en la lista desplegable **Buscar**, seleccione **Configuraciones de fuentes de datos virtuales de Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="7525e-169">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="7525e-170">Seleccione **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="7525e-170">Select **Results**.</span></span>

7. <span data-ttu-id="7525e-171">Seleccione el registro **Fuente de datos de recursos humanos de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="7525e-171">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="7525e-172">Introduzca la información requerida para la configuración del origen de datos:</span><span class="sxs-lookup"><span data-stu-id="7525e-172">Enter the required information for the data source configuration:</span></span>

   - <span data-ttu-id="7525e-173">**URL de destino**: la URL del espacio de nombres de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="7525e-173">**Target URL**: The URL of your Human Resources namespace.</span></span> <span data-ttu-id="7525e-174">El formato de la URL de destino es:</span><span class="sxs-lookup"><span data-stu-id="7525e-174">The format of the target URL is:</span></span>
     
     <span data-ttu-id="7525e-175">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span><span class="sxs-lookup"><span data-stu-id="7525e-175">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span></span>

     <span data-ttu-id="7525e-176">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="7525e-176">For example:</span></span>
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     ><span data-ttu-id="7525e-177">Asegúrese de incluir el carácter "**/**" al final de la URL para evitar recibir un error.</span><span class="sxs-lookup"><span data-stu-id="7525e-177">Be sure to include the "**/**" character at the end of the URL to avoid receiving an error.</span></span>

   - <span data-ttu-id="7525e-178">**ID de inquilino**: el ID de inquilino de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="7525e-178">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>

   - <span data-ttu-id="7525e-179">**ID de la aplicación de AAD**: id. de aplicación (cliente) creado para la aplicación registrada en el portal de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="7525e-179">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="7525e-180">Recibió esta información anteriormente durante el paso [Registrar la aplicación en Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="7525e-180">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   - <span data-ttu-id="7525e-181">**Secreto de aplicación de AAD**: secreto de aplicación creado para la aplicación registrada en el portal de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="7525e-181">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="7525e-182">Recibió esta información anteriormente durante el paso [Registrar la aplicación en Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="7525e-182">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   ![Fuente de datos de HR de Microsoft](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. <span data-ttu-id="7525e-184">Seleccione **Guardar y cerrar**.</span><span class="sxs-lookup"><span data-stu-id="7525e-184">Select **Save & Close**.</span></span>

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="7525e-185">Conceder permisos de aplicación en Human Resources</span><span class="sxs-lookup"><span data-stu-id="7525e-185">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="7525e-186">Otorgar permisos para los las dos aplicaciones de Azure AD en Human Resources:</span><span class="sxs-lookup"><span data-stu-id="7525e-186">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="7525e-187">La aplicación creada para su inquilino en el portal de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="7525e-187">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="7525e-188">La aplicación Dynamics 365 HR Virtual Entity instalada en el entorno de Power Apps</span><span class="sxs-lookup"><span data-stu-id="7525e-188">The Dynamics 365 HR Virtual Entity app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="7525e-189">En Human Resources, abra la página **Aplicaciones de Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="7525e-189">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="7525e-190">Seleccione **Nuevo** para crear un nuevo registro de aplicación.</span><span class="sxs-lookup"><span data-stu-id="7525e-190">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="7525e-191">En el campo **Id. de cliente**, ingrese el ID de cliente de la aplicación que registró en el portal de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="7525e-191">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="7525e-192">En el campo **Nombre**, ingrese el nombre de la aplicación que registró en el portal de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="7525e-192">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="7525e-193">En el campo **ID de usuario**, seleccione el ID de un usuario con permisos de administrador en Human Resources y el entorno de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="7525e-193">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="7525e-194">Seleccione **Nuevo** para crear un segundo registro de aplicación:</span><span class="sxs-lookup"><span data-stu-id="7525e-194">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="7525e-195">**Id. de cliente**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="7525e-195">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="7525e-196">**Nombre**: Dynamics 365 HR Virtual Entity</span><span class="sxs-lookup"><span data-stu-id="7525e-196">**Name**: Dynamics 365 HR Virtual Entity</span></span>
    - <span data-ttu-id="7525e-197">En el campo **ID de usuario**, seleccione el ID de un usuario con permisos de administrador en Human Resources y el entorno de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="7525e-197">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-entities"></a><span data-ttu-id="7525e-198">Generar entidades virtuales</span><span class="sxs-lookup"><span data-stu-id="7525e-198">Generate virtual entities</span></span>

<span data-ttu-id="7525e-199">Cuando se completa la configuración, puede seleccionar las entidades virtuales que desea generar y habilitar en su instancia de Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="7525e-199">When setup completes, you can select the virtual entities you want to generate and enable in your Common Data Service instance.</span></span>

1. <span data-ttu-id="7525e-200">En Human Resources, abra la página **Integración de Common Data Service (CDS)**.</span><span class="sxs-lookup"><span data-stu-id="7525e-200">In Human Resources, open the **Common Data Service (CDS) integration** page.</span></span>

2. <span data-ttu-id="7525e-201">Seleccione la pestaña **Entidades virtuales**.</span><span class="sxs-lookup"><span data-stu-id="7525e-201">Select the **Virtual entities** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="7525e-202">El botón de alternancia **Habilitar la entidad virtual** se establecerá en **Sí** automáticamente cuando se haya completado toda la configuración necesaria.</span><span class="sxs-lookup"><span data-stu-id="7525e-202">The **Enable the virtual entity** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="7525e-203">Si el botón de alternancia está configurado en **No**, revise los pasos de las secciones anteriores de este documento para asegurarse de completar toda la configuración los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="7525e-203">If the toggle is set to **No**, review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="7525e-204">Seleccione la entidad (o entidades) que desea generar en Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="7525e-204">Select the entity or entities you want to generate in Common Data Service.</span></span>

4. <span data-ttu-id="7525e-205">Seleccione **Generar/actualizar**.</span><span class="sxs-lookup"><span data-stu-id="7525e-205">Select **Generate/refresh**.</span></span>

![Integración de Common Data Service](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-entity-generation-status"></a><span data-ttu-id="7525e-207">Comprobar el estado de generación de la entidad</span><span class="sxs-lookup"><span data-stu-id="7525e-207">Check entity generation status</span></span>

<span data-ttu-id="7525e-208">Las entidades virtuales se generan en Common Data Service mediante un proceso asincrónico en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="7525e-208">Virtual entities are generated in Common Data Service through an asynchronous background process.</span></span> <span data-ttu-id="7525e-209">Actualizaciones de la visualización del proceso en el centro de actividades.</span><span class="sxs-lookup"><span data-stu-id="7525e-209">Updates on the process display in the action center.</span></span> <span data-ttu-id="7525e-210">Los detalles del proceso, incluidos los registros de errores, aparecen en la página **Automatizaciones de procesos**.</span><span class="sxs-lookup"><span data-stu-id="7525e-210">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="7525e-211">En Recursos humanos, abra la página **Automatizaciones de procesos**.</span><span class="sxs-lookup"><span data-stu-id="7525e-211">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="7525e-212">Seleccione la pestaña **Procesos en segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="7525e-212">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="7525e-213">Seleccione **Proceso en segundo plano de operación asincrónica de sondeo de entidad virtual**.</span><span class="sxs-lookup"><span data-stu-id="7525e-213">Select **Virtual entity poll async operation background process**.</span></span>

4. <span data-ttu-id="7525e-214">Seleccione **Ver los resultados más recientes**.</span><span class="sxs-lookup"><span data-stu-id="7525e-214">Select **View most recent results**.</span></span>

<span data-ttu-id="7525e-215">El panel deslizante muestra los resultados de ejecución más recientes del proceso.</span><span class="sxs-lookup"><span data-stu-id="7525e-215">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="7525e-216">Puede ver el registro del proceso, que incluye los errores devueltos por Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="7525e-216">You can view the log for the process, including any errors returned from Common Data Service.</span></span>

## <a name="see-also"></a><span data-ttu-id="7525e-217">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7525e-217">See also</span></span>

[<span data-ttu-id="7525e-218">¿Qué es Common Data Service?</span><span class="sxs-lookup"><span data-stu-id="7525e-218">What is Common Data Service?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="7525e-219">Información general sobre las entidades</span><span class="sxs-lookup"><span data-stu-id="7525e-219">Entity overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="7525e-220">Descripción general de las relaciones entre entidades</span><span class="sxs-lookup"><span data-stu-id="7525e-220">Entity relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="7525e-221">Crear y editar entidades virtuales que contienen datos de una fuente de datos externa</span><span class="sxs-lookup"><span data-stu-id="7525e-221">Create and edit virtual entities that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="7525e-222">¿Que son los portales de Power Apps?</span><span class="sxs-lookup"><span data-stu-id="7525e-222">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="7525e-223">Descripción general de la creación de aplicaciones en Power Apps</span><span class="sxs-lookup"><span data-stu-id="7525e-223">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)
