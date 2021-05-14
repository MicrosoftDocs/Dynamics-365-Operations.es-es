---
title: Configurar tablas virtuales de Dataverse
description: Este tema muestra cómo configurar tablas virtuales para Dynamics 365 Human Resources. Genere y actualice tablas virtuales existentes, y analice las tablas generadas y disponibles.
author: andreabichsel
ms.date: 01/25/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 04997aba427ae6013c8154593b09ae1a45a580c3
ms.sourcegitcommit: 9283caad2d0636f98579c995784abec19fda2e3f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "5935762"
---
# <a name="configure-dataverse-virtual-tables"></a><span data-ttu-id="0adab-104">Configurar tablas virtuales de Dataverse</span><span class="sxs-lookup"><span data-stu-id="0adab-104">Configure Dataverse virtual tables</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="0adab-105">Dynamics 365 Human Resources es una fuente de datos virtual en Microsoft Dataverse.</span><span class="sxs-lookup"><span data-stu-id="0adab-105">Dynamics 365 Human Resources is a virtual data source in Microsoft Dataverse.</span></span> <span data-ttu-id="0adab-106">Proporciona operaciones completas de creación, lectura, actualización y eliminación (CRUD) de Dataverse y Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="0adab-106">It provides full create, read, update, and delete (CRUD) operations from Dataverse and Microsoft Power Platform.</span></span> <span data-ttu-id="0adab-107">Los datos de las tablas virtuales no se almacenan en Dataverse, sino en la base de datos de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0adab-107">The data for virtual tables isn't stored in Dataverse, but in the application database.</span></span>

<span data-ttu-id="0adab-108">Para habilitar las operaciones CRUD en entidades de Human Resources desde Dataverse, debe hacer que las entidades estén disponibles como tablas virtuales en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="0adab-108">To enable CRUD operations on Human Resources entities from Dataverse, you must make the entities available as virtual tables in Dataverse.</span></span> <span data-ttu-id="0adab-109">Esto le permite realizar operaciones CRUD desde Dataverse y Microsoft Power Platform en datos que se encuentran en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0adab-109">This lets you perform CRUD operations from Dataverse and Microsoft Power Platform on data that's in Human Resources.</span></span> <span data-ttu-id="0adab-110">Las operaciones también respaldan las validaciones de la lógica empresarial completa de Human Resources para garantizar la integridad de los datos al escribir datos en las entidades.</span><span class="sxs-lookup"><span data-stu-id="0adab-110">The operations also support the full business logic validations of Human Resources to ensure data integrity when writing data to the entities.</span></span>

> [!NOTE]
> <span data-ttu-id="0adab-111">Las entidades de Human Resources se corresponden con tablas de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="0adab-111">Human Resources entities correspond to Dataverse tables.</span></span> <span data-ttu-id="0adab-112">Para obtener más información sobre Dataverse (antes denominado Common Data Service) y actualizaciones de terminología, consulte [¿Qué es Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span><span class="sxs-lookup"><span data-stu-id="0adab-112">For more information about Dataverse (formerly Common Data Service) and terminology updates, see [What is Microsoft Dataverse?](/powerapps/maker/data-platform/data-platform-intro)</span></span>

## <a name="available-virtual-tables-for-human-resources"></a><span data-ttu-id="0adab-113">Tablas virtuales disponibles para Human Resources</span><span class="sxs-lookup"><span data-stu-id="0adab-113">Available virtual tables for Human Resources</span></span>

<span data-ttu-id="0adab-114">Todas las entidades de Protocolo de datos abiertos (OData) de Human Resources están disponibles como tablas virtuales en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="0adab-114">All Open Data Protocol (OData) entities in Human Resources are available as virtual tables in Dataverse.</span></span> <span data-ttu-id="0adab-115">También están disponibles en Power Platform.</span><span class="sxs-lookup"><span data-stu-id="0adab-115">They're also available in Power Platform.</span></span> <span data-ttu-id="0adab-116">Ahora puede crear aplicaciones y experiencias con datos directamente de Human Resources con capacidad CRUD completa, sin copiar ni sincronizar datos en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="0adab-116">You can now build apps and experiences with data directly from Human Resources with full CRUD capability, without copying or synchronizing data to Dataverse.</span></span> <span data-ttu-id="0adab-117">Puede usar los portales de Power Apps para construir sitios web externos que habiliten escenarios de colaboración para procesos comerciales en Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0adab-117">You can use Power Apps portals to build external-facing websites that enable collaboration scenarios for business processes in Human Resources.</span></span>

<span data-ttu-id="0adab-118">Puede ver la lista de tablas virtuales habilitadas en el entorno y comenzar a trabajar con las tablas en [Power Apps](https://make.powerapps.com), en la solución **Tablas virtuales de Dynamics 365 HR**.</span><span class="sxs-lookup"><span data-stu-id="0adab-118">You can view the list of virtual tables enabled in the environment, and begin working with the tables in [Power Apps](https://make.powerapps.com), in the **Dynamics 365 HR Virtual Tables** solution.</span></span>

![Tablas virtuales de Dynamics 365 HR en Power Apps](./media/hr-admin-integration-virtual-entities-power-apps.jpg)

## <a name="virtual-tables-versus-native-tables"></a><span data-ttu-id="0adab-120">Tablas virtuales versus tablas nativas</span><span class="sxs-lookup"><span data-stu-id="0adab-120">Virtual tables versus native tables</span></span>

<span data-ttu-id="0adab-121">Las tablas virtuales de Human Resources no son lo mismo que las tablas de Dataverse nativas creadas para Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0adab-121">Virtual tables for Human Resources aren't the same as the native Dataverse tables created for Human Resources.</span></span> 

<span data-ttu-id="0adab-122">Las tablas nativas para Human Resources se generan por separado y se mantienen en la solución HCM Common en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="0adab-122">The native tables for Human Resources are generated separately and maintained in the HCM Common solution in Dataverse.</span></span> <span data-ttu-id="0adab-123">Con tablas nativas, los datos se almacenan en Dataverse y esto requiere la sincronización con la base de datos de la aplicación Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0adab-123">With native tables, the data is stored in Dataverse and requires synchronization with the Human Resources application database.</span></span>

> [!NOTE]
> <span data-ttu-id="0adab-124">Para obtener una lista de las tablas de Dataverse nativas para Human Resources, vea [Tablas de Dataverse](./hr-developer-entities.md).</span><span class="sxs-lookup"><span data-stu-id="0adab-124">For a list of the native Dataverse tables for Human Resources, see [Dataverse tables](./hr-developer-entities.md).</span></span>

## <a name="setup"></a><span data-ttu-id="0adab-125">Configurar</span><span class="sxs-lookup"><span data-stu-id="0adab-125">Setup</span></span>

<span data-ttu-id="0adab-126">Siga estos pasos de configuración para habilitar tablas virtuales en su entorno.</span><span class="sxs-lookup"><span data-stu-id="0adab-126">Follow these setup steps to enable virtual tables in your environment.</span></span>

### <a name="enable-virtual-tables-in-human-resources"></a><span data-ttu-id="0adab-127">Habilitar tablas virtuales en Human Resources</span><span class="sxs-lookup"><span data-stu-id="0adab-127">Enable virtual tables in Human Resources</span></span>

<span data-ttu-id="0adab-128">Primero, debe habilitar las tablas virtuales en el espacio de trabajo **Administración de características**.</span><span class="sxs-lookup"><span data-stu-id="0adab-128">First, you must enable virtual tables in the **Feature management** workspace.</span></span>

1. <span data-ttu-id="0adab-129">En Human Resources, seleccione **Administración del sistema**.</span><span class="sxs-lookup"><span data-stu-id="0adab-129">In Human Resources, select **System administration**.</span></span>

2. <span data-ttu-id="0adab-130">Seleccione la ventana **Gestión de funciones**.</span><span class="sxs-lookup"><span data-stu-id="0adab-130">Select the **Feature management** tile.</span></span>

3. <span data-ttu-id="0adab-131">Seleccione **Compatibilidad con tablas virtuales para HR en Dataverse** y, a continuación, seleccione **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="0adab-131">Select **Virtual table support for HR in Dataverse**, and then select **Enable**.</span></span>

<span data-ttu-id="0adab-132">Para obtener más información sobre cómo habilitar y deshabilitar características, consulte [Administrar características](hr-admin-manage-features.md).</span><span class="sxs-lookup"><span data-stu-id="0adab-132">For more information about enabling and disabling features, see [Manage features](hr-admin-manage-features.md).</span></span>

### <a name="register-the-app-in-microsoft-azure"></a><span data-ttu-id="0adab-133">Registrar la aplicación en Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="0adab-133">Register the app in Microsoft Azure</span></span>

<span data-ttu-id="0adab-134">Debe registrar su instancia de Human Resources en Azure Portal para que la plataforma de identidad de Microsoft pueda proporcionar servicios de autenticación y autorización para la aplicación y los usuarios.</span><span class="sxs-lookup"><span data-stu-id="0adab-134">You must register your Human Resources instance in the Azure portal so the Microsoft identity platform can provide authentication and authorization services for the app and users.</span></span> <span data-ttu-id="0adab-135">Para obtener más información sobre cómo registrar aplicaciones en Azure, consulte [Inicio rápido: registre una aplicación con la plataforma de identidad de Microsoft](/azure/active-directory/develop/quickstart-register-app).</span><span class="sxs-lookup"><span data-stu-id="0adab-135">For more information about registering apps in Azure, see [Quickstart: Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).</span></span>

1. <span data-ttu-id="0adab-136">Abra el [portal de Microsoft Azure](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="0adab-136">Open the [Microsoft Azure portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="0adab-137">En la lista de servicios de Azure, seleccione **Registros de aplicación**.</span><span class="sxs-lookup"><span data-stu-id="0adab-137">In the Azure services list, select **App registrations**.</span></span>

3. <span data-ttu-id="0adab-138">Seleccione **Nuevo registro**.</span><span class="sxs-lookup"><span data-stu-id="0adab-138">Select **New registration**.</span></span>

4. <span data-ttu-id="0adab-139">En el campo **Nombre**, especifique un nombre descriptivo para la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0adab-139">In the **Name** field, enter a descriptive name for the app.</span></span> <span data-ttu-id="0adab-140">Por ejemplo, **Tablas virtuales de Dynamics 365 Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="0adab-140">For example, **Dynamics 365 Human Resources Virtual Tables**.</span></span>

5. <span data-ttu-id="0adab-141">En el campo **Redirigir URI**, ingrese la URL del espacio de nombres de su instancia de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0adab-141">In the **Redirect URI** field, enter the namespace URL of your instance of Human Resources.</span></span>

6. <span data-ttu-id="0adab-142">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="0adab-142">Select **Register**.</span></span>

7. <span data-ttu-id="0adab-143">Cuando se completa el registro, Azure Portal muestra el panel **Visión de conjunto** del registro de la aplicación, que incluye su **ID de aplicación (cliente)**.</span><span class="sxs-lookup"><span data-stu-id="0adab-143">When registration completes, the Azure portal displays the app registration's **Overview** pane, which includes its **Application (client) ID**.</span></span> <span data-ttu-id="0adab-144">Tome nota del **ID de aplicación (cliente)** en este momento.</span><span class="sxs-lookup"><span data-stu-id="0adab-144">Take note of the **Application (client) ID** at this time.</span></span> <span data-ttu-id="0adab-145">Debe introducir esta información al [Configurar el origen de datos de la tabla virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="0adab-145">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

8. <span data-ttu-id="0adab-146">En el panel de navegación izquierdo, seleccione **Certificados y secretos**.</span><span class="sxs-lookup"><span data-stu-id="0adab-146">In the left navigation pane, select **Certificates and secrets**.</span></span>

9. <span data-ttu-id="0adab-147">En la sección **Secretos del cliente** de la página, seleccione **Nuevo secreto de cliente**.</span><span class="sxs-lookup"><span data-stu-id="0adab-147">In the **Client secrets** section of the page, select **New client secret**.</span></span>

10. <span data-ttu-id="0adab-148">Proporcione una descripción, seleccione una duración y seleccione **Añadir**.</span><span class="sxs-lookup"><span data-stu-id="0adab-148">Provide a description, select a duration, and select **Add**.</span></span>

11. <span data-ttu-id="0adab-149">Registre el valor del secreto de la propiedad de la tabla **Valor**.</span><span class="sxs-lookup"><span data-stu-id="0adab-149">Record the secret's value from the **Value** property of the table.</span></span> <span data-ttu-id="0adab-150">Debe introducir esta información al [Configurar el origen de datos de la tabla virtual](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span><span class="sxs-lookup"><span data-stu-id="0adab-150">You'll enter this information when you [Configure the virtual table data source](hr-admin-integration-common-data-service-virtual-entities.md#configure-the-virtual-table-data-source).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0adab-151">Asegúrese de tomar nota del valor del secreto en este momento.</span><span class="sxs-lookup"><span data-stu-id="0adab-151">Be sure to take note of the secret's value at this time.</span></span> <span data-ttu-id="0adab-152">El secreto nunca se vuelve a mostrar después de salir de esta página.</span><span class="sxs-lookup"><span data-stu-id="0adab-152">The secret is never displayed again after you leave this page.</span></span>

### <a name="install-the-dynamics-365-hr-virtual-table-app"></a><span data-ttu-id="0adab-153">Instalar la aplicación Dynamics 365 HR Virtual Tabla</span><span class="sxs-lookup"><span data-stu-id="0adab-153">Install the Dynamics 365 HR Virtual Table app</span></span>

<span data-ttu-id="0adab-154">Instale la aplicación Dynamics 365 HR Virtual Tabla en su entorno de Power Apps para implementar el paquete de solución de tabla virtual para Dataverse.</span><span class="sxs-lookup"><span data-stu-id="0adab-154">Install the Dynamics 365 HR Virtual Table app in your Power Apps environment to deploy the virtual table solution package to Dataverse.</span></span>

1. <span data-ttu-id="0adab-155">En Human Resources, abra la página **Integración de Microsoft Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="0adab-155">In Human Resources, open the **Microsoft Dataverse integration** page.</span></span>

2. <span data-ttu-id="0adab-156">Seleccione la pestaña **Tablas virtuales**.</span><span class="sxs-lookup"><span data-stu-id="0adab-156">Select the **Virtual tables** tab.</span></span>

3. <span data-ttu-id="0adab-157">Seleccione **Instalar aplicación de tablas virtuales**.</span><span class="sxs-lookup"><span data-stu-id="0adab-157">Select **Install virtual table app**.</span></span>

### <a name="configure-the-virtual-table-data-source"></a><span data-ttu-id="0adab-158">Configurar el origen de datos de la tabla virtual</span><span class="sxs-lookup"><span data-stu-id="0adab-158">Configure the virtual table data source</span></span>

<span data-ttu-id="0adab-159">El siguiente paso es configurar el origen de datos de la tabla virtual en el entorno de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="0adab-159">The next step is to configure the virtual table data source in the Power Apps environment.</span></span>

1. <span data-ttu-id="0adab-160">Abra el [centro de administración de Power Platform](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="0adab-160">Open the [Power Platform admin center](https://admin.powerplatform.microsoft.com).</span></span>

2. <span data-ttu-id="0adab-161">En la lista **Entornos**, seleccione el entorno de Power Apps asociado a su instancia de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0adab-161">In the **Environments** list, select the Power Apps environment associated with your Human Resources instance.</span></span>

3. <span data-ttu-id="0adab-162">Seleccione la **URL del entorno** la sección **Detalles** de la página.</span><span class="sxs-lookup"><span data-stu-id="0adab-162">Select the **Environment URL** in the **Details** section of the page.</span></span>

4. <span data-ttu-id="0adab-163">En el **Centro de estado de la solución**, selecciona el icono **Búsqueda avanzada** en la parte superior derecha de la página de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="0adab-163">In the **Solution Health Hub**, select the **Advanced Find** icon in the top right of the application page.</span></span>

5. <span data-ttu-id="0adab-164">En la página **Búsqueda avanzada**, en la lista desplegable **Buscar**, seleccione **Configuraciones de fuentes de datos virtuales de Finance and Operations**.</span><span class="sxs-lookup"><span data-stu-id="0adab-164">On the **Advanced Find** page, in the **Look for** dropdown list, select **Finance and Operations Virtual Data Source Configurations**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="0adab-165">La instalación de la aplicación de tablas virtuales desde el paso de configuración anterior puede tardar unos minutos.</span><span class="sxs-lookup"><span data-stu-id="0adab-165">The installation of the virtual table app from the previous setup step can take a few minutes.</span></span> <span data-ttu-id="0adab-166">Si las **Configuraciones de datos de origen virtuales de Finance and Operations** no están disponibles en la lista, espere un minuto y actualice la lista.</span><span class="sxs-lookup"><span data-stu-id="0adab-166">If **Finance and Operations Virtual Data Source Configurations** isn't available in the list, wait for a minute and refresh the list.</span></span>

6. <span data-ttu-id="0adab-167">Seleccione **Resultados**.</span><span class="sxs-lookup"><span data-stu-id="0adab-167">Select **Results**.</span></span>

7. <span data-ttu-id="0adab-168">Seleccione el registro **Fuente de datos de recursos humanos de Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="0adab-168">Select the **Microsoft HR Data Source** record.</span></span>

8. <span data-ttu-id="0adab-169">Introduzca la información requerida para la configuración del origen de datos:</span><span class="sxs-lookup"><span data-stu-id="0adab-169">Enter the required information for the data source configuration:</span></span>

   - <span data-ttu-id="0adab-170">**URL de destino**: la URL del espacio de nombres de Human Resources.</span><span class="sxs-lookup"><span data-stu-id="0adab-170">**Target URL**: The URL of your Human Resources namespace.</span></span> <span data-ttu-id="0adab-171">El formato de la URL de destino es:</span><span class="sxs-lookup"><span data-stu-id="0adab-171">The format of the target URL is:</span></span>
     
     <span data-ttu-id="0adab-172">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span><span class="sxs-lookup"><span data-stu-id="0adab-172">https://\<hostname\>.hr.talent.dynamics.com/namespaces/\<namespaceID\>/</span></span>

     <span data-ttu-id="0adab-173">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="0adab-173">For example:</span></span>
     
     `https://aos.rts-sf-5ea54e35c68-westus2.hr.talent.dynamics.com/namespaces/49d24c565-8f4d-4891-b174-bf83d948ed0c/`

     >[!NOTE]
     ><span data-ttu-id="0adab-174">Asegúrese de incluir el carácter "**/**" al final de la URL para evitar recibir un error.</span><span class="sxs-lookup"><span data-stu-id="0adab-174">Be sure to include the "**/**" character at the end of the URL to avoid receiving an error.</span></span>

   - <span data-ttu-id="0adab-175">**ID de inquilino**: el ID de inquilino de Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="0adab-175">**Tenant ID**: The Azure Active Directory (Azure AD) tenant ID.</span></span>

   - <span data-ttu-id="0adab-176">**ID de la aplicación de AAD**: id. de aplicación (cliente) creado para la aplicación registrada en el portal de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="0adab-176">**AAD Application ID**: The application (client) ID created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="0adab-177">Recibió esta información anteriormente durante el paso [Registrar la aplicación en Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="0adab-177">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   - <span data-ttu-id="0adab-178">**Secreto de aplicación de AAD**: secreto de aplicación creado para la aplicación registrada en el portal de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="0adab-178">**AAD Application Secret**: The client secret created for the application registered in the Microsoft Azure portal.</span></span> <span data-ttu-id="0adab-179">Recibió esta información anteriormente durante el paso [Registrar la aplicación en Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span><span class="sxs-lookup"><span data-stu-id="0adab-179">You received this information earlier during the step [Register the app in Microsoft Azure](hr-admin-integration-common-data-service-virtual-entities.md#register-the-app-in-microsoft-azure).</span></span>

   ![Fuente de datos de HR de Microsoft](./media/hr-admin-integration-virtual-entities-hr-data-source.jpg)

9. <span data-ttu-id="0adab-181">Seleccione **Guardar y cerrar**.</span><span class="sxs-lookup"><span data-stu-id="0adab-181">Select **Save & Close**.</span></span>

### <a name="grant-app-permissions-in-human-resources"></a><span data-ttu-id="0adab-182">Conceder permisos de aplicación en Human Resources</span><span class="sxs-lookup"><span data-stu-id="0adab-182">Grant app permissions in Human Resources</span></span>

<span data-ttu-id="0adab-183">Otorgar permisos para los las dos aplicaciones de Azure AD en Human Resources:</span><span class="sxs-lookup"><span data-stu-id="0adab-183">Grant permissions for the two Azure AD applications in Human Resources:</span></span>

- <span data-ttu-id="0adab-184">La aplicación creada para su inquilino en el portal de Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="0adab-184">The app created for your tenant in the Microsoft Azure portal</span></span>
- <span data-ttu-id="0adab-185">La aplicación Dynamics 365 HR Virtual Tabla instalada en el entorno de Power Apps</span><span class="sxs-lookup"><span data-stu-id="0adab-185">The Dynamics 365 HR Virtual Table app installed in the Power Apps environment</span></span> 

1. <span data-ttu-id="0adab-186">En Human Resources, abra la página **Aplicaciones de Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="0adab-186">In Human Resources, open the **Azure Active Directory applications** page.</span></span>

2. <span data-ttu-id="0adab-187">Seleccione **Nuevo** para crear un nuevo registro de aplicación.</span><span class="sxs-lookup"><span data-stu-id="0adab-187">Select **New** to create a new application record:</span></span>

    - <span data-ttu-id="0adab-188">En el campo **Id. de cliente**, ingrese el ID de cliente de la aplicación que registró en el portal de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="0adab-188">In the **Client ID** field, enter the client ID of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="0adab-189">En el campo **Nombre**, ingrese el nombre de la aplicación que registró en el portal de Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="0adab-189">In the **Name** field, enter the name of the app you registered in the Microsoft Azure portal.</span></span>
    - <span data-ttu-id="0adab-190">En el campo **ID de usuario**, seleccione el ID de un usuario con permisos de administrador en Human Resources y el entorno de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="0adab-190">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

3. <span data-ttu-id="0adab-191">Seleccione **Nuevo** para crear un segundo registro de aplicación:</span><span class="sxs-lookup"><span data-stu-id="0adab-191">Select **New** to create a second application record:</span></span>

    - <span data-ttu-id="0adab-192">**Id. de cliente**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span><span class="sxs-lookup"><span data-stu-id="0adab-192">**Client Id**: f9be0c49-aa22-4ec6-911a-c5da515226ff</span></span>
    - <span data-ttu-id="0adab-193">**Nombre**: Dynamics 365 HR Virtual Table</span><span class="sxs-lookup"><span data-stu-id="0adab-193">**Name**: Dynamics 365 HR Virtual Table</span></span>
    - <span data-ttu-id="0adab-194">En el campo **ID de usuario**, seleccione el ID de un usuario con permisos de administrador en Human Resources y el entorno de Power Apps.</span><span class="sxs-lookup"><span data-stu-id="0adab-194">In the **User ID** field, select the user ID of a user with admin permissions in Human Resources and the Power Apps environment.</span></span>

## <a name="generate-virtual-tables"></a><span data-ttu-id="0adab-195">Generar tablas virtuales</span><span class="sxs-lookup"><span data-stu-id="0adab-195">Generate virtual tables</span></span>

<span data-ttu-id="0adab-196">Cuando se haya completado la configuración, puede seleccionar las tablas virtuales que desea generar y habilitar en su instancia de Dataverse.</span><span class="sxs-lookup"><span data-stu-id="0adab-196">When setup completes, you can select the virtual tables you want to generate and enable in your Dataverse instance.</span></span>

1. <span data-ttu-id="0adab-197">En Human Resources, abra la página **Integración de Microsoft Dataverse**.</span><span class="sxs-lookup"><span data-stu-id="0adab-197">In Human Resources, open the **Microsoft Dataverse integration** page.</span></span>

2. <span data-ttu-id="0adab-198">Seleccione la pestaña **Tablas virtuales**.</span><span class="sxs-lookup"><span data-stu-id="0adab-198">Select the **Virtual tables** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="0adab-199">El botón de alternancia **Habilitar tablas virtuales** se establecerá en **Sí** automáticamente cuando se haya completado toda la configuración necesaria.</span><span class="sxs-lookup"><span data-stu-id="0adab-199">The **Enable virtual tables** toggle will be set to **Yes** automatically when all required setup has been completed.</span></span> <span data-ttu-id="0adab-200">Si el botón de alternancia está configurado en **No**, revise los pasos de las secciones anteriores de este documento para asegurarse de completar toda la configuración los requisitos previos.</span><span class="sxs-lookup"><span data-stu-id="0adab-200">If the toggle is set to **No**, review the steps in previous sections of this document to ensure all prerequisite setup is completed.</span></span>

3. <span data-ttu-id="0adab-201">Seleccione la tabla (o tablas) que desea generar en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="0adab-201">Select the table or tables you want to generate in Dataverse.</span></span>

4. <span data-ttu-id="0adab-202">Seleccione **Generar/actualizar**.</span><span class="sxs-lookup"><span data-stu-id="0adab-202">Select **Generate/refresh**.</span></span>

![Integración de Dataverse](./media/hr-admin-integration-dataverse-integration.png)

## <a name="check-table-generation-status"></a><span data-ttu-id="0adab-204">Comprobar el estado de generación de tablas</span><span class="sxs-lookup"><span data-stu-id="0adab-204">Check table generation status</span></span>

<span data-ttu-id="0adab-205">Las tablas virtuales se generan en Dataverse mediante un proceso asincrónico en segundo plano.</span><span class="sxs-lookup"><span data-stu-id="0adab-205">Virtual tables are generated in Dataverse through an asynchronous background process.</span></span> <span data-ttu-id="0adab-206">Actualizaciones de la visualización del proceso en el centro de actividades.</span><span class="sxs-lookup"><span data-stu-id="0adab-206">Updates on the process display in the action center.</span></span> <span data-ttu-id="0adab-207">Los detalles del proceso, incluidos los registros de errores, aparecen en la página **Automatizaciones de procesos**.</span><span class="sxs-lookup"><span data-stu-id="0adab-207">Details on the process, including error logs, appear in the **Process automations** page.</span></span>

1. <span data-ttu-id="0adab-208">En Recursos humanos, abra la página **Automatizaciones de procesos**.</span><span class="sxs-lookup"><span data-stu-id="0adab-208">In Human Resources, open the **Process automations** page.</span></span>

2. <span data-ttu-id="0adab-209">Seleccione la pestaña **Procesos en segundo plano**.</span><span class="sxs-lookup"><span data-stu-id="0adab-209">Select the **Background processes** tab.</span></span>

3. <span data-ttu-id="0adab-210">Seleccione **Proceso en segundo plano de operación asincrónica de sondeo de tabla virtual**.</span><span class="sxs-lookup"><span data-stu-id="0adab-210">Select **Virtual table poll async operation background process**.</span></span>

4. <span data-ttu-id="0adab-211">Seleccione **Ver los resultados más recientes**.</span><span class="sxs-lookup"><span data-stu-id="0adab-211">Select **View most recent results**.</span></span>

<span data-ttu-id="0adab-212">El panel deslizante muestra los resultados de ejecución más recientes del proceso.</span><span class="sxs-lookup"><span data-stu-id="0adab-212">The slideout pane displays the most recent execution results for the process.</span></span> <span data-ttu-id="0adab-213">Puede ver el registro del proceso, que incluye los errores devueltos por Dataverse.</span><span class="sxs-lookup"><span data-stu-id="0adab-213">You can view the log for the process, including any errors returned from Dataverse.</span></span>

## <a name="see-also"></a><span data-ttu-id="0adab-214">Consulte también</span><span class="sxs-lookup"><span data-stu-id="0adab-214">See also</span></span>

[<span data-ttu-id="0adab-215">¿Qué es Dataverse?</span><span class="sxs-lookup"><span data-stu-id="0adab-215">What is Dataverse?</span></span>](/powerapps/maker/common-data-service/data-platform-intro)<br>
[<span data-ttu-id="0adab-216">Tablas en Dataverse</span><span class="sxs-lookup"><span data-stu-id="0adab-216">Tables in Dataverse</span></span>](/powerapps/maker/common-data-service/entity-overview)<br>
[<span data-ttu-id="0adab-217">Visión general de las relaciones entre tablas</span><span class="sxs-lookup"><span data-stu-id="0adab-217">Table relationships overview</span></span>](/powerapps/maker/common-data-service/relationships-overview)<br>
[<span data-ttu-id="0adab-218">Crear y editar tablas virtuales que contienen datos de un origen de datos externo</span><span class="sxs-lookup"><span data-stu-id="0adab-218">Create and edit virtual tables that contain data from an external data source</span></span>](/powerapps/maker/common-data-service/create-edit-virtual-entities)<br>
[<span data-ttu-id="0adab-219">¿Que son los portales de Power Apps?</span><span class="sxs-lookup"><span data-stu-id="0adab-219">What is Power Apps portals?</span></span>](/powerapps/maker/portals/overview)<br>
[<span data-ttu-id="0adab-220">Descripción general de la creación de aplicaciones en Power Apps</span><span class="sxs-lookup"><span data-stu-id="0adab-220">Overview of creating apps in Power Apps</span></span>](/powerapps/maker/)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
