---
title: Configurar tablas virtuales de Dataverse
description: Este tema muestra cómo configurar tablas virtuales para Dynamics 365 Human Resources. Genere y actualice tablas virtuales existentes, y analice las tablas generadas y disponibles.
author: andreabichsel
manager: tfehr
ms.date: 01/25/2021
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
ms.openlocfilehash: cd299b51e38cc30c3e18f3ef9de1f43fa817b840
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114195"
---
# <a name="configure-dataverse-virtual-tables"></a><span data-ttu-id="96cc8-104">Configurar tablas virtuales de Dataverse</span><span class="sxs-lookup"><span data-stu-id="96cc8-104">Configure Dataverse virtual tables</span></span>

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="96cc8-105">Dynamics 365 Human Resources es una fuente de datos virtual en Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="96cc8-105">Dynamics 365 Human Resources is a virtual data source in Microsoft Dataverse.</span></span> <span data-ttu-id="96cc8-106">Proporciona operaciones completas de creación, lectura, actualización y eliminación (CRUD) de Dataverse y Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="96cc8-106">It provides full create, read, update, and delete (CRUD) operations from Dataverse and Microsoft Power Platform.</span></span> <span data-ttu-id="96cc8-107">Los datos de las tablas virtuales no se almacenan en Dataverse, sino en la base de datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="96cc8-107">The data for virtual tables isn't stored in Dataverse, but in the application database.</span></span>

<span data-ttu-id="96cc8-108">Para habilitar las operaciones CRUD en entidades de Human Resources desde Dataverse, debe hacer que las entidades estén disponibles como tablas virtuales en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="96cc8-108">To enable CRUD operations on Human Resources entities from Dataverse, you must make the entities available as virtual tables in Dataverse.</span></span> <span data-ttu-id="96cc8-109">Esto le permite realizar operaciones CRUD desde Dataverse y Microsoft Power Platform en datos que se encuentran en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="96cc8-109">This lets you perform CRUD operations from Dataverse and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="96cc8-110">Las operaciones también respaldan las validaciones de la lógica empresarial completa de Human Resources para garantizar la integridad de los datos al escribir datos en las entidades.</span><span class="sxs-lookup"><span data-stu-id="96cc8-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

> [!NOTE]
> <span data-ttu-id="96cc8-111">Las entidades de Human Resources se corresponden con tablas de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="96cc8-111">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="96cc8-112">Para obtener más información sobre Dataverse (antes denominado Common Data Service) y actualizaciones de terminología, consulte [¿Qué es Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="96cc8-112">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro)</span></span>

## <a name="available-virtual-tables-for-human-resources"></a><span data-ttu-id="96cc8-113">Tablas virtuales disponibles para Human Resources</span><span class="sxs-lookup"><span data-stu-id="96cc8-113">Available virtual tables for Human Resources</span></span>

<span data-ttu-id="96cc8-114">Todas las entidades de Protocolo de datos abiertos (OData) de Human Resources están disponibles como tablas virtuales en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="96cc8-114">All Open Data Protocol (OData) entities in Human Resources are available as virtual tables in Dataverse.</span></span> <span data-ttu-id="96cc8-115">También están disponibles en Power Platform.</span><span class="sxs-lookup"><span data-stu-id="96cc8-115">They're also available in Power Platform.</span></span> <span data-ttu-id="96cc8-116">Ahora puede crear aplicaciones y experiencias con datos directamente de Human Resources con capacidad CRUD completa, sin copiar ni sincronizar datos en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="96cc8-116">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Dataverse.</span></span> <span data-ttu-id="96cc8-117">Puede usar los portales de Power Apps para construir sitios web externos que habiliten escenarios de colaboración para procesos comerciales en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="96cc8-117">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="96cc8-118">Puede ver la lista de tablas virtuales habilitadas en el entorno y comenzar a trabajar con las tablas en [Power Apps](https://make.powerapps.com), en la solución **Tablas virtuales de Dynamics 365 HR**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-118">You can view the list of virtual tables enabled in the environment, and begin working with the tables in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Tables** solution.</span></span>

![Tablas virtuales de Dynamics 365 HR en Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a><span data-ttu-id="96cc8-120">Tablas virtuales versus tablas nativas</span><span class="sxs-lookup"><span data-stu-id="96cc8-120">Virtual tables versus native tables</span></span>

<span data-ttu-id="96cc8-121">Las tablas virtuales de Human Resources no son lo mismo que las tablas de Dataverse nativas creadas para Human Resources.</span><span class="sxs-lookup"><span data-stu-id="96cc8-121">Virtual tables for Human Resources aren't the same as the native Dataverse tables created for Human Resources.</span></span> 

<span data-ttu-id="96cc8-122">Las tablas nativas para Human Resources se generan por separado y se mantienen en la solución HCM Common en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="96cc8-122">The native tables for Human Resources are generated separately and maintained in the HCM Common solution in Dataverse.</span></span> <span data-ttu-id="96cc8-123">Con tablas nativas, los datos se almacenan en Dataverse y esto requiere la sincronización con la base de datos de la aplicación Human Resources.</span><span class="sxs-lookup"><span data-stu-id="96cc8-123">With native tables, the data is stored in Dataverse and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="96cc8-124">Para obtener una lista de las tablas de Dataverse nativas para Human Resources, vea [Tablas de Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span><span class="sxs-lookup"><span data-stu-id="96cc8-124">For a list of the native Dataverse tables for Human Resources, see [Dataverse tables](https://docs.microsoft.com/dynamics365/human-resources/hr-developer-entities).</span></span>

## <a name="setup"></a><span data-ttu-id="96cc8-125">Configurar</span><span class="sxs-lookup"><span data-stu-id="96cc8-125">Setup</span></span>

<span data-ttu-id="96cc8-126">Siga estos pasos de configuración para habilitar tablas virtuales en su entorno.</span><span class="sxs-lookup"><span data-stu-id="96cc8-126">Follow these setup steps to enable virtual tables in your environment.</span></span>

### <a name="enable-virtual-tables-in-human-resources"></a><span data-ttu-id="96cc8-127">Habilitar tablas virtuales en Human Resources</span><span class="sxs-lookup"><span data-stu-id="96cc8-127">Enable virtual tables in Human Resources</span></span>

<span data-ttu-id="96cc8-128">Primero, debe habilitar las tablas virtuales en el espacio de trabajo **Administración de características**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-128">First, you must enable virtual tables in the **Feature management** workspace.</span></span>

1. <span data-ttu-id="96cc8-129">En Human Resources, seleccione **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-129">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="96cc8-130">Seleccione la ventana **Gestión de funciones**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-130">Select the **Feature management** tile.</span></span>

3. <span data-ttu-id="96cc8-131">Seleccione **Compatibilidad con tablas virtuales para HR en Dataverse** y, a continuación, seleccione **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-131">Select **Virtual table support for HR in Dataverse**, and then select **Enable**.</span></span>

<span data-ttu-id="96cc8-132">Para obtener más información sobre cómo habilitar y deshabilitar características, consulte [Administrar características](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="96cc8-132">For more information about enabling and disabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="96cc8-133">Registrar la aplicación en Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="96cc8-133">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="96cc8-134">Debe registrar su instancia de Human Resources en Azure Portal para que la plataforma de identidad de Microsoft pueda proporcionar servicios de autenticación y autorización para la aplicación y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="96cc8-134">You must register your Human Resources instance in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="96cc8-135">Para obtener más información sobre cómo registrar aplicaciones en Azure, consulte [Inicio rápido: registre una aplicación con la plataforma de identidad de Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="96cc8-135">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="96cc8-136">Abra el [portal de Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="96cc8-136">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="96cc8-137">En la lista de servicios de Azure, seleccione **Registros de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-137">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="96cc8-138">Seleccione **Nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-138">Select **New registration**.</span></span>

4. <span data-ttu-id="96cc8-139">En el campo **Nombre**, especifique un nombre descriptivo para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="96cc8-139">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="96cc8-140">Por ejemplo, **Tablas virtuales de Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-140">For example, **Dynamics 365 Human Resources Virtual Tables**.</span></span>

5. <span data-ttu-id="96cc8-141">En el campo **Redirigir URI**, ingrese la URL del espacio de nombres de su instancia de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="96cc8-141">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="96cc8-142">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-142">Select **Register**.</span></span>

7. <span data-ttu-id="96cc8-143">Cuando se completa el registro, Azure Portal muestra el panel **Visión de conjunto** del registro de la aplicación, que incluye su **ID de aplicación (cliente)**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-143">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="96cc8-144">Tome nota del **ID de aplicación (cliente)** en este momento.</span><span class="sxs-lookup"><span data-stu-id="96cc8-144">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="96cc8-145">Debe introducir esta información al [Configurar el origen de datos de la tabla virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="96cc8-145">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

8. <span data-ttu-id="96cc8-146">En el panel de navegación izquierdo, seleccione **Certificados y secretos**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-146">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="96cc8-147">En la sección **Secretos del cliente** de la página, seleccione **Nuevo secreto de cliente**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-147">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="96cc8-148">Proporcione una descripción, seleccione una duración y seleccione **Añadir**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-148">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="96cc8-149">Registre el valor del secreto.</span><span class="sxs-lookup"><span data-stu-id="96cc8-149">Record the secret's value.</span></span> <span data-ttu-id="96cc8-150">Debe introducir esta información al [Configurar el origen de datos de la tabla virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="96cc8-150">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="96cc8-151">Asegúrese de tomar nota del valor del secreto en este momento.</span><span class="sxs-lookup"><span data-stu-id="96cc8-151">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="96cc8-152">El secreto nunca se vuelve a mostrar después de salir de esta página.</span><span class="sxs-lookup"><span data-stu-id="96cc8-152">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a><span data-ttu-id="96cc8-153">Instalar la aplicación Dynamics 365 HR Virtual Tabla</span><span class="sxs-lookup"><span data-stu-id="96cc8-153">Install the Dynamics 365 HR Virtual Table app</span></span>

<span data-ttu-id="96cc8-154">Instale la aplicación Dynamics 365 HR Virtual Tabla en su entorno de Power Apps para implementar el paquete de solución de tabla virtual para Dataverse.</span><span class="sxs-lookup"><span data-stu-id="96cc8-154">Install the Dynamics 365 HR Virtual Table app in your Power Apps environment to deploy the virtual table solution package to Dataverse.</span></span>

1. <span data-ttu-id="96cc8-155">Abra el [centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="96cc8-155">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="96cc8-156">En la lista **Entornos**, seleccione el entorno de Power Apps asociado a su instancia de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="96cc8-156">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="96cc8-157">En la sección **Recursos** de la página, seleccione **Aplicaciones de Dynamics 365**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-157">In the **Resources** section of the page, select **Dynamics 365 apps**.</span></span>

4. <span data-ttu-id="96cc8-158">Seleccione la acción **Instalar aplicación**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-158">Select the **Install app** action.</span></span>

5. <span data-ttu-id="96cc8-159">Seleccione **Dynamics 365 HR Virtual Table** y seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-159">Select **Dynamics 365 HR Virtual Table**, and select **Next**.</span></span>

6. <span data-ttu-id="96cc8-160">Revise y marque para aceptar los términos de servicio.</span><span class="sxs-lookup"><span data-stu-id="96cc8-160">Review and mark to agree to the terms of service.</span></span>

7. <span data-ttu-id="96cc8-161">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-161">Select **Install**.</span></span>

<span data-ttu-id="96cc8-162">La instalación tarda unos minutos.</span><span class="sxs-lookup"><span data-stu-id="96cc8-162">The install takes a few minutes.</span></span> <span data-ttu-id="96cc8-163">Cuando se complete, continúe con los siguientes pasos.</span><span class="sxs-lookup"><span data-stu-id="96cc8-163">When it completes, continue to the next steps.</span></span>

![Instalar la aplicación Dynamics 365 HR Virtual Table desde el centro de administración de Power Platform](./media/hr-admin-integration-virtual-entities-power-platform-install.jpg)

### <a name="configure-the-virtual-table-data-source"></a><span data-ttu-id="96cc8-165">Configurar el origen de datos de la tabla virtual</span><span class="sxs-lookup"><span data-stu-id="96cc8-165">Configure the virtual table data source</span></span> 

<span data-ttu-id="96cc8-166">El siguiente paso es configurar el origen de datos de la tabla virtual en el entorno de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="96cc8-166">The next step is to configure the virtual table data source in the Power Apps environment.</span></span> 

1. <span data-ttu-id="96cc8-167">Abra el [centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="96cc8-167">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="96cc8-168">En la lista **Entornos**, seleccione el entorno de Power Apps asociado a su instancia de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="96cc8-168">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="96cc8-169">Seleccione la **URL del entorno** la sección **Detalles** de la página.</span><span class="sxs-lookup"><span data-stu-id="96cc8-169">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="96cc8-170">En el **Centro de estado de la solución**, selecciona el icono **Búsqueda avanzada** en la parte superior derecha de la página de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="96cc8-170">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="96cc8-171">En la página **Búsqueda avanzada**, en la lista desplegable **Buscar**, seleccione **Configuraciones de fuentes de datos virtuales de Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-171">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

6. <span data-ttu-id="96cc8-172">Seleccione **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-172">Select **Results**.</span></span>

7. <span data-ttu-id="96cc8-173">Seleccione el registro **Fuente de datos de recursos humanos de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-173">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="96cc8-174">Introduzca la información requerida para la configuración del origen de datos:</span><span class="sxs-lookup"><span data-stu-id="96cc8-174">Enter the required information for the data source configuration:</span></span>

   - <span data-ttu-id="96cc8-175">**URL de destino**: la URL del espacio de nombres de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="96cc8-175">**Target URL**: The URL of your Human Resources namespace.</span></span> <span data-ttu-id="96cc8-176">El formato de la URL de destino es:</span><span class="sxs-lookup"><span data-stu-id="96cc8-176">The format of the target URL is:</span></span>
     
     <span data-ttu-id="96cc8-177">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span><span class="sxs-lookup"><span data-stu-id="96cc8-177">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span></span>

     <span data-ttu-id="96cc8-178">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="96cc8-178">For example:</span></span>
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     ><span data-ttu-id="96cc8-179">Asegúrese de incluir el carácter "**/**" al final de la URL para evitar recibir un error.</span><span class="sxs-lookup"><span data-stu-id="96cc8-179">Be sure to include the "**/**" character at the end of the URL to avoid receiving an error.</span></span>

   - <span data-ttu-id="96cc8-180">**ID de inquilino**: el ID de inquilino de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="96cc8-180">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>

   - <span data-ttu-id="96cc8-181">**ID de la aplicación de AAD**: id. de aplicación (cliente) creado para la aplicación registrada en el portal de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="96cc8-181">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="96cc8-182">Recibió esta información anteriormente durante el paso [Registrar la aplicación en Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="96cc8-182">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   - <span data-ttu-id="96cc8-183">**Secreto de aplicación de AAD**: secreto de aplicación creado para la aplicación registrada en el portal de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="96cc8-183">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="96cc8-184">Recibió esta información anteriormente durante el paso [Registrar la aplicación en Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="96cc8-184">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   ![Fuente de datos de HR de Microsoft](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. <span data-ttu-id="96cc8-186">Seleccione **Guardar y cerrar**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-186">Select **Save & Close**.</span></span>

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="96cc8-187">Conceder permisos de aplicación en Human Resources</span><span class="sxs-lookup"><span data-stu-id="96cc8-187">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="96cc8-188">Otorgar permisos para los las dos aplicaciones de Azure AD en Human Resources:</span><span class="sxs-lookup"><span data-stu-id="96cc8-188">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="96cc8-189">La aplicación creada para su inquilino en el portal de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="96cc8-189">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="96cc8-190">La aplicación Dynamics 365 HR Virtual Tabla instalada en el entorno de Power Apps</span><span class="sxs-lookup"><span data-stu-id="96cc8-190">The Dynamics 365 HR Virtual Table app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="96cc8-191">En Human Resources, abra la página **Aplicaciones de Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-191">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="96cc8-192">Seleccione **Nuevo** para crear un nuevo registro de aplicación.</span><span class="sxs-lookup"><span data-stu-id="96cc8-192">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="96cc8-193">En el campo **Id. de cliente**, ingrese el ID de cliente de la aplicación que registró en el portal de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="96cc8-193">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="96cc8-194">En el campo **Nombre**, ingrese el nombre de la aplicación que registró en el portal de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="96cc8-194">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="96cc8-195">En el campo **ID de usuario**, seleccione el ID de un usuario con permisos de administrador en Human Resources y el entorno de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="96cc8-195">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="96cc8-196">Seleccione **Nuevo** para crear un segundo registro de aplicación:</span><span class="sxs-lookup"><span data-stu-id="96cc8-196">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="96cc8-197">**Id. de cliente**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="96cc8-197">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="96cc8-198">**Nombre**: Dynamics 365 HR Virtual Table</span><span class="sxs-lookup"><span data-stu-id="96cc8-198">**Name**: Dynamics 365 HR Virtual Table</span></span>
    - <span data-ttu-id="96cc8-199">En el campo **ID de usuario**, seleccione el ID de un usuario con permisos de administrador en Human Resources y el entorno de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="96cc8-199">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-tables"></a><span data-ttu-id="96cc8-200">Generar tablas virtuales</span><span class="sxs-lookup"><span data-stu-id="96cc8-200">Generate virtual tables</span></span>

<span data-ttu-id="96cc8-201">Cuando se haya completado la configuración, puede seleccionar las tablas virtuales que desea generar y habilitar en su instancia de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="96cc8-201">When setup completes, you can select the virtual tables you want to generate and enable in your Dataverse instance.</span></span>

1. <span data-ttu-id="96cc8-202">En Human Resources, abra la página **Integración de Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-202">In Human Resources, open the **Dataverse integration** page.</span></span>

2. <span data-ttu-id="96cc8-203">Seleccione la pestaña **Tablas virtuales**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-203">Select the **Virtual tables** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="96cc8-204">El botón de alternancia **Habilitar tablas virtuales** se establecerá en **Sí** automáticamente cuando se haya completado toda la configuración necesaria.</span><span class="sxs-lookup"><span data-stu-id="96cc8-204">The **Enable virtual tables** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="96cc8-205">Si el botón de alternancia está configurado en **No**, revise los pasos de las secciones anteriores de este documento para asegurarse de completar toda la configuración los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="96cc8-205">If the toggle is set to **No**, review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="96cc8-206">Seleccione la tabla (o tablas) que desea generar en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="96cc8-206">Select the table or tables you want to generate in Dataverse.</span></span>

4. <span data-ttu-id="96cc8-207">Seleccione **Generar/actualizar**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-207">Select **Generate/refresh**.</span></span>

![Integración de Dataverse](./media/hr-admin-integration-common-data-service-integration.jpg)

## <a name="check-table-generation-status"></a><span data-ttu-id="96cc8-209">Comprobar el estado de generación de tablas</span><span class="sxs-lookup"><span data-stu-id="96cc8-209">Check table generation status</span></span>

<span data-ttu-id="96cc8-210">Las tablas virtuales se generan en Dataverse mediante un proceso asincrónico en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="96cc8-210">Virtual tables are generated in Dataverse through an asynchronous background process.</span></span> <span data-ttu-id="96cc8-211">Actualizaciones de la visualización del proceso en el centro de actividades.</span><span class="sxs-lookup"><span data-stu-id="96cc8-211">Updates on the process display in the action center.</span></span> <span data-ttu-id="96cc8-212">Los detalles del proceso, incluidos los registros de errores, aparecen en la página **Automatizaciones de procesos**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-212">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="96cc8-213">En Recursos humanos, abra la página **Automatizaciones de procesos**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-213">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="96cc8-214">Seleccione la pestaña **Procesos en segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-214">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="96cc8-215">Seleccione **Proceso en segundo plano de operación asincrónica de sondeo de tabla virtual**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-215">Select **Virtual table poll async operation background process**.</span></span>

4. <span data-ttu-id="96cc8-216">Seleccione **Ver los resultados más recientes**.</span><span class="sxs-lookup"><span data-stu-id="96cc8-216">Select **View most recent results**.</span></span>

<span data-ttu-id="96cc8-217">El panel deslizante muestra los resultados de ejecución más recientes del proceso.</span><span class="sxs-lookup"><span data-stu-id="96cc8-217">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="96cc8-218">Puede ver el registro del proceso, que incluye los errores devueltos por Dataverse.</span><span class="sxs-lookup"><span data-stu-id="96cc8-218">You can view the log for the process, including any errors returned from Dataverse.</span></span>

## <a name="see-also"></a><span data-ttu-id="96cc8-219">Consulte también</span><span class="sxs-lookup"><span data-stu-id="96cc8-219">See also</span></span>

[<span data-ttu-id="96cc8-220">¿Qué es Dataverse?</span><span class="sxs-lookup"><span data-stu-id="96cc8-220">What is Dataverse?</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="96cc8-221">Tablas en Dataverse</span><span class="sxs-lookup"><span data-stu-id="96cc8-221">Tables in Dataverse</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="96cc8-222">Visión general de las relaciones entre tablas</span><span class="sxs-lookup"><span data-stu-id="96cc8-222">Table relationships overview</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="96cc8-223">Crear y editar tablas virtuales que contienen datos de un origen de datos externo</span><span class="sxs-lookup"><span data-stu-id="96cc8-223">Create and edit virtual tables that contain data from an external data source</span></span>](https://docs.microsoft.com/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="96cc8-224">¿Que son los portales de Power Apps?</span><span class="sxs-lookup"><span data-stu-id="96cc8-224">What is Power Apps portals?</span></span>](https://docs.microsoft.com/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="96cc8-225">Descripción general de la creación de aplicaciones en Power Apps</span><span class="sxs-lookup"><span data-stu-id="96cc8-225">Overview of creating apps in Power Apps</span></span>](https://docs.microsoft.com/powerapps/maker/)
