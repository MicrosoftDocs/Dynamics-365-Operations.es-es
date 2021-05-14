---
title: Actualizar al modelo de parte y libreta de direcciones global
description: Este tema describe cómo actualizar datos de escritura dual al modelo de libreta de direcciones global y de grupo.
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
ms.service: dynamics-ax-applications
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 32128d48bfac195530d70b60e67cfd4921fc001e
ms.sourcegitcommit: a202bf67c3c2c054e2a47cb7b3145cb7c0ee635e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/25/2021
ms.locfileid: "5941092"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a><span data-ttu-id="19a74-103">Actualizar al modelo de parte y libreta de direcciones global</span><span class="sxs-lookup"><span data-stu-id="19a74-103">Upgrade to the party and global address book model</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="19a74-104">La [Plantilla de Azure Data Factory](https://aka.ms/dual-write-gab-adf) le ayuda a actualizar los datos de tabla **Cuenta**, **Contacto** y **Vendedor** en escritura dual en el modelo de libreta de direcciones global y de grupo.</span><span class="sxs-lookup"><span data-stu-id="19a74-104">The [Azure Data Factory template](https://aka.ms/dual-write-gab-adf) helps you upgrade existing **Account**, **Contact**, and **Vendor** table data in dual-write to the party and global address book model.</span></span> <span data-ttu-id="19a74-105">La plantilla reconcilia los datos de aplicaciones de Finance and Operations y aplicaciones de participación del cliente.</span><span class="sxs-lookup"><span data-stu-id="19a74-105">The template reconciles the data from both Finance and Operations apps and customer engagement applications.</span></span> <span data-ttu-id="19a74-106">Al final del proceso, los campos **Parte** y **Contacto** de registros de **Parte** se crearán y asociarán con los registros **Cuenta**, **Contacto** y **Vendedor** en aplicaciones de participación del cliente.</span><span class="sxs-lookup"><span data-stu-id="19a74-106">At the end of the process, **Party** and **Contact** fields for **Party** records will be created and associated with **Account**, **Contact**, and **Vendor** records in customer engagement applications.</span></span> <span data-ttu-id="19a74-107">Un archivo .csv (`FONewParty.csv`) se genera para crear nuevos registros de **Parte** dentro de la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="19a74-107">A .csv file (`FONewParty.csv`) is generated to create new **Party** records inside the Finance and Operations app.</span></span> <span data-ttu-id="19a74-108">Este tema proporciona las instrucciones para usar la plantilla de Data Factory y actualizar sus datos.</span><span class="sxs-lookup"><span data-stu-id="19a74-108">This topic provides the instructions to use the Data Factory template and upgrade your data.</span></span>

<span data-ttu-id="19a74-109">Si no tiene ninguna personalización, puede usar la plantilla tal cual.</span><span class="sxs-lookup"><span data-stu-id="19a74-109">If you don’t have any customizations, you can use the template as-is.</span></span> <span data-ttu-id="19a74-110">Si tiene personalizaciones para **Cuenta**, **Contacto** y **Vendedor**, debe modificar la plantilla siguiendo las siguientes instrucciones.</span><span class="sxs-lookup"><span data-stu-id="19a74-110">If you have customizations for **Account**, **Contact**, and **Vendor** then you must modify the template using the following instructions.</span></span>

> [!Note]
> <span data-ttu-id="19a74-111">La plantilla ayuda a actualizar solo los datos de **Parte**.</span><span class="sxs-lookup"><span data-stu-id="19a74-111">The template helps to upgrade only the **Party** data.</span></span> <span data-ttu-id="19a74-112">En una versión futura, se incluirán direcciones postales y electrónicas.</span><span class="sxs-lookup"><span data-stu-id="19a74-112">In a future release, postal and electronic addresses will be included.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="19a74-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="19a74-113">Prerequisites</span></span>

<span data-ttu-id="19a74-114">Estos requisitos previos son necesarios:</span><span class="sxs-lookup"><span data-stu-id="19a74-114">These prerequisites are required:</span></span>

+ [<span data-ttu-id="19a74-115">Suscripción a Azure</span><span class="sxs-lookup"><span data-stu-id="19a74-115">Azure subscription</span></span>](https://portal.azure.com/)
+ [<span data-ttu-id="19a74-116">Acceso a la plantilla</span><span class="sxs-lookup"><span data-stu-id="19a74-116">Access to the template</span></span>](https://aka.ms/dual-write-gab-adf)
+ <span data-ttu-id="19a74-117">Es un cliente de escritura dual existente.</span><span class="sxs-lookup"><span data-stu-id="19a74-117">You are an existing dual-write customer.</span></span>

## <a name="prepare-for-the-upgrade"></a><span data-ttu-id="19a74-118">Prepararse para la actualización</span><span class="sxs-lookup"><span data-stu-id="19a74-118">Prepare for the upgrade</span></span>

+ <span data-ttu-id="19a74-119">**Totalmente sincronizado**: ambos entornos están completamente sincronizados para **Cuenta (cliente)**, **Contacto** y **Vendedor**.</span><span class="sxs-lookup"><span data-stu-id="19a74-119">**Fully synched**: Both environments are fully synched state for **Account (Customer)**, **Contact**, and **Vendor**.</span></span>
+ <span data-ttu-id="19a74-120">**Claves de integración**: las tablas **Cuenta (cliente)**, **Contacto** y **Vendedor** de las aplicaciones de interacción con el cliente utilizan las claves de integración que se envían listas para usar.</span><span class="sxs-lookup"><span data-stu-id="19a74-120">**Integration keys**: **Account (Customer)**, **Contact**, and **Vendor** tables in customer engagement apps are using the integration keys that shipped out-of-the-box.</span></span> <span data-ttu-id="19a74-121">Si personalizó las claves de integración, debe personalizar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="19a74-121">If you customized the integration keys, you must customize the template.</span></span>
+ <span data-ttu-id="19a74-122">**Número de parte**: todos los registros de **Cuenta (cliente)**, **Contacto** y **Vendedor** que se actualizarán tienen un número de **Parte**.</span><span class="sxs-lookup"><span data-stu-id="19a74-122">**Party number**: All **Account (Customer)**, **Contact**, and **Vendor** records that will be upgraded have a **Party** number.</span></span> <span data-ttu-id="19a74-123">Los registros sin número de **Parte** se ignorarán.</span><span class="sxs-lookup"><span data-stu-id="19a74-123">Records without a **Party** number will be ignored.</span></span> <span data-ttu-id="19a74-124">Si desea actualizar esos registros, agregue un número de **Parte** antes de iniciar el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="19a74-124">If you want to upgrade those records, add a **Party** number to them before you start the upgrade process.</span></span>
+ <span data-ttu-id="19a74-125">**Interrupción del sistema**: durante el proceso de actualización, deberá desconectar los entornos de Finance and Operations y de participación del cliente.</span><span class="sxs-lookup"><span data-stu-id="19a74-125">**System outage**: During the upgrade process, you will have to take both the Finance and Operations and customer engagement environments offline.</span></span>
+ <span data-ttu-id="19a74-126">**Instantánea**: Toma instantáneas de aplicaciones de Finance and Operations e interacción con el cliente.</span><span class="sxs-lookup"><span data-stu-id="19a74-126">**Snapshot**: Take snapshots of both the Finance and Operations and customer engagement apps.</span></span> <span data-ttu-id="19a74-127">Utilice las instantáneas para restaurar el estado anterior si es necesario.</span><span class="sxs-lookup"><span data-stu-id="19a74-127">Use the snapshots to restore the previous state if you need to.</span></span>

## <a name="deployment"></a><span data-ttu-id="19a74-128">Implementación</span><span class="sxs-lookup"><span data-stu-id="19a74-128">Deployment</span></span>

1. <span data-ttu-id="19a74-129">Descarga la plantilla de [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span><span class="sxs-lookup"><span data-stu-id="19a74-129">Download the template from [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span></span>

2. <span data-ttu-id="19a74-130">Inicie sesión en [Microsoft Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="19a74-130">Sign in to [Microsoft Azure](https://portal.azure.com/).</span></span>

3. <span data-ttu-id="19a74-131">Cree un [grupo de recursos](/azure/azure-resource-manager/management/manage-resource-groups-portal).</span><span class="sxs-lookup"><span data-stu-id="19a74-131">Create a [resource group](/azure/azure-resource-manager/management/manage-resource-groups-portal).</span></span>

4. <span data-ttu-id="19a74-132">Cree una [cuenta de almacenamiento](/azure/storage/common/storage-account-create?tabs=azure-portal) en el grupo de recursos que creó.</span><span class="sxs-lookup"><span data-stu-id="19a74-132">Create a [storage account](/azure/storage/common/storage-account-create?tabs=azure-portal) in the resource group that you created.</span></span>

5. <span data-ttu-id="19a74-133">Cree una [factoría de datos](/azure/data-factory/quickstart-create-data-factory-portal) en el grupo de recursos anterior que creó.</span><span class="sxs-lookup"><span data-stu-id="19a74-133">Create a [data factory](/azure/data-factory/quickstart-create-data-factory-portal) in above resource group that you created.</span></span>

6. <span data-ttu-id="19a74-134">Abra la fábrica de datos y seleccione el mosaico **Autor y monitor**.</span><span class="sxs-lookup"><span data-stu-id="19a74-134">Open the data factory and select the **Author & Monitor** tile.</span></span>

7. <span data-ttu-id="19a74-135">Sobre la pestaña **Gestionar**, seleccione **Plantilla ARM**.</span><span class="sxs-lookup"><span data-stu-id="19a74-135">On the **Manage** tab, select **ARM template**.</span></span>

8. <span data-ttu-id="19a74-136">Seleccione **Importar plantilla ARM** para importar la plantilla de **Parte**.</span><span class="sxs-lookup"><span data-stu-id="19a74-136">Select the **Import ARM template** to import the **Party** template.</span></span>

9. <span data-ttu-id="19a74-137">Importe la plantilla a la factoría de datos.</span><span class="sxs-lookup"><span data-stu-id="19a74-137">Import the template into the data factory.</span></span> <span data-ttu-id="19a74-138">Ingrese los siguientes valores para **Detalles del proyecto** y **Detalles de la instancia**.</span><span class="sxs-lookup"><span data-stu-id="19a74-138">Enter the following values for **Project details** and **Instance details**.</span></span>

    <span data-ttu-id="19a74-139">Campo</span><span class="sxs-lookup"><span data-stu-id="19a74-139">Field</span></span> | <span data-ttu-id="19a74-140">Valor</span><span class="sxs-lookup"><span data-stu-id="19a74-140">Value</span></span>
    ---|---
    <span data-ttu-id="19a74-141">Suscripción</span><span class="sxs-lookup"><span data-stu-id="19a74-141">Subscription</span></span> | <span data-ttu-id="19a74-142">Suscripción a Azure</span><span class="sxs-lookup"><span data-stu-id="19a74-142">Azure subscription</span></span>
    <span data-ttu-id="19a74-143">Grupo de recursos</span><span class="sxs-lookup"><span data-stu-id="19a74-143">Resource group</span></span> | <span data-ttu-id="19a74-144">Proporcione el mismo recurso con el que se crea la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="19a74-144">Provide same resource under which storage account is created.</span></span>
    <span data-ttu-id="19a74-145">Región</span><span class="sxs-lookup"><span data-stu-id="19a74-145">Region</span></span> | <span data-ttu-id="19a74-146">Especifique la región.</span><span class="sxs-lookup"><span data-stu-id="19a74-146">Specify region.</span></span>
    <span data-ttu-id="19a74-147">Nombre de la fábrica</span><span class="sxs-lookup"><span data-stu-id="19a74-147">Factory Name</span></span> | <span data-ttu-id="19a74-148">Especifique el nombre de la fábrica.</span><span class="sxs-lookup"><span data-stu-id="19a74-148">Specify factory name.</span></span>
    <span data-ttu-id="19a74-149">FO Linked Service_service Clave principal</span><span class="sxs-lookup"><span data-stu-id="19a74-149">FO Linked Service_service Principal Key</span></span> | <span data-ttu-id="19a74-150">Especifique la clave de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19a74-150">Specify the application's key.</span></span>
    <span data-ttu-id="19a74-151">Cadena de conexión de Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="19a74-151">Azure Blob Storage_connection String</span></span> | <span data-ttu-id="19a74-152">Cadena de conexión de Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="19a74-152">Azure Blob storage connection string.</span></span>
    <span data-ttu-id="19a74-153">Contraseña de servicio vinculado de Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="19a74-153">Dynamics Crm Linked Service_password</span></span> | <span data-ttu-id="19a74-154">La contraseña de la cuenta de usuario que especificó como nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="19a74-154">The password for the user account you specified as the username.</span></span>
    <span data-ttu-id="19a74-155">FO Linked Service_properties_type Properties_url</span><span class="sxs-lookup"><span data-stu-id="19a74-155">FO Linked Service_properties_type Properties_url</span></span>  | `https://sampledynamics.sandbox-operationsdynamics.com/data`
    <span data-ttu-id="19a74-156">FO Linked Service_properties_type Properties_tenant</span><span class="sxs-lookup"><span data-stu-id="19a74-156">FO Linked Service_properties_type Properties_tenant</span></span> | <span data-ttu-id="19a74-157">Especifique la información del inquilino (nombre de dominio o ID de inquilino) bajo la cual reside su aplicación.</span><span class="sxs-lookup"><span data-stu-id="19a74-157">Specify the tenant information (domain name or tenant ID) under which your application resides.</span></span>
    <span data-ttu-id="19a74-158">FO Linked Service_properties_type Properties_aad Resource Id</span><span class="sxs-lookup"><span data-stu-id="19a74-158">FO Linked Service_properties_type Properties_aad Resource Id</span></span> | `https://sampledynamics.sandboxoperationsdynamics.com`
    <span data-ttu-id="19a74-159">FO Linked Service_properties_type Properties_service Principal Id</span><span class="sxs-lookup"><span data-stu-id="19a74-159">FO Linked Service_properties_type Properties_service Principal Id</span></span> | <span data-ttu-id="19a74-160">Especifique el Id. de cliente de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="19a74-160">Specify the application's client ID.</span></span>
    <span data-ttu-id="19a74-161">Dynamics Crm Linked Service_properties_type Properties_username</span><span class="sxs-lookup"><span data-stu-id="19a74-161">Dynamics Crm Linked Service_properties_type Properties_username</span></span> | <span data-ttu-id="19a74-162">El nombre de usuario para conectarse a Dynamics.</span><span class="sxs-lookup"><span data-stu-id="19a74-162">The username to connect to Dynamics.</span></span>

    <span data-ttu-id="19a74-163">Para más información, vea [Promocionar manualmente una plantilla de Resource Manager para cada entorno](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment), [Propiedades de servicios vinculados](/azure/data-factory/connector-dynamics-ax#linked-service-properties) y [Copiar datos con Azure Data Factory](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)</span><span class="sxs-lookup"><span data-stu-id="19a74-163">For more information, see [Manually promote a Resource Manager template for each environment](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment), [Linked service properties](/azure/data-factory/connector-dynamics-ax#linked-service-properties), and [Copy data using Azure Data Factory](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)</span></span>

10. <span data-ttu-id="19a74-164">Después de la implementación, valide los conjuntos de datos, el flujo de datos y el servicio vinculado de la factoría de datos.</span><span class="sxs-lookup"><span data-stu-id="19a74-164">After deployment, validate the datasets, data flow, and linked service of the data factory.</span></span>

   ![Conjuntos de datos, flujo de datos y servicio vinculado](media/data-factory-validate.png)

11. <span data-ttu-id="19a74-166">Navegar a **Gestionar**.</span><span class="sxs-lookup"><span data-stu-id="19a74-166">Navigate to **Manage**.</span></span> <span data-ttu-id="19a74-167">Debajo de **Conexiones**, seleccione **Servicio vinculado**.</span><span class="sxs-lookup"><span data-stu-id="19a74-167">Under **Connections**, select **Linked Service**.</span></span> <span data-ttu-id="19a74-168">Seleccione **DynamicsCrmLinkedService**.</span><span class="sxs-lookup"><span data-stu-id="19a74-168">Select **DynamicsCrmLinkedService**.</span></span> <span data-ttu-id="19a74-169">En el formulario **Editar servicio vinculado (Dynamics CRM)**, ingrese los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="19a74-169">In the **Edit linked service (Dynamics CRM)** form, enter the following values:</span></span>

    <span data-ttu-id="19a74-170">Campo</span><span class="sxs-lookup"><span data-stu-id="19a74-170">Field</span></span> | <span data-ttu-id="19a74-171">Valor</span><span class="sxs-lookup"><span data-stu-id="19a74-171">Value</span></span>
    ---|---
    <span data-ttu-id="19a74-172">Nombre</span><span class="sxs-lookup"><span data-stu-id="19a74-172">Name</span></span> | <span data-ttu-id="19a74-173">DynamicsCrmLinkedService</span><span class="sxs-lookup"><span data-stu-id="19a74-173">DynamicsCrmLinkedService</span></span>
    <span data-ttu-id="19a74-174">Descripción</span><span class="sxs-lookup"><span data-stu-id="19a74-174">Description</span></span> | <span data-ttu-id="19a74-175">Servicios vinculados para conectarse con la instancia de CRM para obtener datos de entidades</span><span class="sxs-lookup"><span data-stu-id="19a74-175">Linked services to connect with CRM instance to fetch entities data</span></span>
    <span data-ttu-id="19a74-176">Conectarse a través del tiempo de ejecución de integración</span><span class="sxs-lookup"><span data-stu-id="19a74-176">Connect via integration runtime</span></span> | <span data-ttu-id="19a74-177">AutoResolvelntegrationRuntime</span><span class="sxs-lookup"><span data-stu-id="19a74-177">AutoResolvelntegrationRuntime</span></span>
    <span data-ttu-id="19a74-178">Tipo de implementación</span><span class="sxs-lookup"><span data-stu-id="19a74-178">Deployment type</span></span> | <span data-ttu-id="19a74-179">En línea</span><span class="sxs-lookup"><span data-stu-id="19a74-179">Online</span></span>
    <span data-ttu-id="19a74-180">URI del servicio</span><span class="sxs-lookup"><span data-stu-id="19a74-180">Service Uri</span></span> | `https://<organization-name>.crm[x].dynamics.com`
    <span data-ttu-id="19a74-181">Tipo de autenticación</span><span class="sxs-lookup"><span data-stu-id="19a74-181">Authentication type</span></span> | <span data-ttu-id="19a74-182">Office365</span><span class="sxs-lookup"><span data-stu-id="19a74-182">Office365</span></span>
    <span data-ttu-id="19a74-183">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="19a74-183">User name</span></span> |
    <span data-ttu-id="19a74-184">Contraseña o Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="19a74-184">Password or Azure Key Vault</span></span> | <span data-ttu-id="19a74-185">Contraseña</span><span class="sxs-lookup"><span data-stu-id="19a74-185">Password</span></span>
    <span data-ttu-id="19a74-186">Contraseña</span><span class="sxs-lookup"><span data-stu-id="19a74-186">Password</span></span> |

## <a name="run-the-template"></a><span data-ttu-id="19a74-187">Ejecutar la plantilla</span><span class="sxs-lookup"><span data-stu-id="19a74-187">Run the template</span></span>

1. <span data-ttu-id="19a74-188">Detenga la doble escritura de **Cuenta**, **Contacto** y **Vendedor** a continuación usando la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="19a74-188">Stop the following **Account**, **Contact**, and **Vendor** dual-write using the Finance and Operations app.</span></span>

    + <span data-ttu-id="19a74-189">Clientes V3 (cuentas)</span><span class="sxs-lookup"><span data-stu-id="19a74-189">Customers V3(accounts)</span></span>
    + <span data-ttu-id="19a74-190">Clientes V3 (contactos)</span><span class="sxs-lookup"><span data-stu-id="19a74-190">Customers V3(contacts)</span></span>
    + <span data-ttu-id="19a74-191">Contactos de CDS V2 (contactos)</span><span class="sxs-lookup"><span data-stu-id="19a74-191">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="19a74-192">Contactos de CDS V2 (contactos)</span><span class="sxs-lookup"><span data-stu-id="19a74-192">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="19a74-193">Proveedor V2 (msdyn_vendors)</span><span class="sxs-lookup"><span data-stu-id="19a74-193">Vendor V2 (msdyn_vendor)</span></span>

2. <span data-ttu-id="19a74-194">Asegúrese de que los mapas se eliminen de la tabla `msdy_dualwriteruntimeconfig` en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="19a74-194">Make sure the maps are removed from the `msdy_dualwriteruntimeconfig` table in Dataverse.</span></span>

3. <span data-ttu-id="19a74-195">Instale [Soluciones de libreta de direcciones global y de fiesta de escritura dual](https://aka.ms/dual-write-gab) de AppSource.</span><span class="sxs-lookup"><span data-stu-id="19a74-195">Install [Dual-write Party and Global Address Book Solutions](https://aka.ms/dual-write-gab) from AppSource.</span></span>

4. <span data-ttu-id="19a74-196">En la aplicación Finance and Operations, si las siguientes tablas contienen datos, ejecuta **Sincronización inicial** para ellos.</span><span class="sxs-lookup"><span data-stu-id="19a74-196">In the Finance and Operations app, if the following tables contain data, then run **Initial Sync** for them.</span></span>

    + <span data-ttu-id="19a74-197">Formas de saludo</span><span class="sxs-lookup"><span data-stu-id="19a74-197">Salutations</span></span>
    + <span data-ttu-id="19a74-198">Tipos de carácter personal</span><span class="sxs-lookup"><span data-stu-id="19a74-198">Personal character types</span></span>
    + <span data-ttu-id="19a74-199">Cierre de agradecimiento</span><span class="sxs-lookup"><span data-stu-id="19a74-199">Complimentary closing</span></span>
    + <span data-ttu-id="19a74-200">Cargos de persona de contacto</span><span class="sxs-lookup"><span data-stu-id="19a74-200">Contact person titles</span></span>
    + <span data-ttu-id="19a74-201">Roles de toma de decisiones</span><span class="sxs-lookup"><span data-stu-id="19a74-201">Decision making roles</span></span>
    + <span data-ttu-id="19a74-202">Niveles de fidelización</span><span class="sxs-lookup"><span data-stu-id="19a74-202">Loyalty levels</span></span>

5. <span data-ttu-id="19a74-203">En la aplicación de interacción con el cliente, desactive los siguientes pasos del complemento.</span><span class="sxs-lookup"><span data-stu-id="19a74-203">In the customer engagement app, disable the following plugin steps.</span></span>

    + <span data-ttu-id="19a74-204">Actualización de cuentas</span><span class="sxs-lookup"><span data-stu-id="19a74-204">Account Update</span></span>
         + <span data-ttu-id="19a74-205">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: actualización de cuenta</span><span class="sxs-lookup"><span data-stu-id="19a74-205">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="19a74-206">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: actualización de cuenta</span><span class="sxs-lookup"><span data-stu-id="19a74-206">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="19a74-207">Actualización de contacto</span><span class="sxs-lookup"><span data-stu-id="19a74-207">Contact Update</span></span>
         + <span data-ttu-id="19a74-208">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: actualización de contacto</span><span class="sxs-lookup"><span data-stu-id="19a74-208">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="19a74-209">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: actualización de contacto</span><span class="sxs-lookup"><span data-stu-id="19a74-209">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="19a74-210">Actualización de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="19a74-210">msdyn_party Update</span></span>
         + <span data-ttu-id="19a74-211">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: actualización de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="19a74-211">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="19a74-212">Actualización de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="19a74-212">msdyn_vendor Update</span></span>
         + <span data-ttu-id="19a74-213">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: actualización de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="19a74-213">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

6. <span data-ttu-id="19a74-214">En la aplicación de interacción con el cliente, desactive los siguientes flujos de trabajo:</span><span class="sxs-lookup"><span data-stu-id="19a74-214">In the customer engagement app, disable the following workflows:</span></span>

    + <span data-ttu-id="19a74-215">Crear proveedores en la tabla Cuentas</span><span class="sxs-lookup"><span data-stu-id="19a74-215">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="19a74-216">Crear proveedores en la tabla Cuentas</span><span class="sxs-lookup"><span data-stu-id="19a74-216">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="19a74-217">Crear proveedores de tipo persona en la tabla Contactos</span><span class="sxs-lookup"><span data-stu-id="19a74-217">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="19a74-218">Crear proveedores de tipo Persona en la tabla Proveedores</span><span class="sxs-lookup"><span data-stu-id="19a74-218">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="19a74-219">Actualizar proveedores en la tabla Cuentas</span><span class="sxs-lookup"><span data-stu-id="19a74-219">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="19a74-220">Actualizar proveedores en la tabla Proveedores</span><span class="sxs-lookup"><span data-stu-id="19a74-220">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="19a74-221">Actualizar proveedores de tipo Persona en la tabla Contactos</span><span class="sxs-lookup"><span data-stu-id="19a74-221">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="19a74-222">Actualizar proveedores de tipo Persona en la tabla Proveedores</span><span class="sxs-lookup"><span data-stu-id="19a74-222">Update Vendors of type Person in Vendors Table</span></span>

7. <span data-ttu-id="19a74-223">En la factoría de datos, ejecute la plantilla seleccionando **Activar ahora** como se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="19a74-223">In the data factory, run the template by selecting **Trigger now** as shown in the following image.</span></span> <span data-ttu-id="19a74-224">Este proceso puede tardar algunas horas en completarse según el volumen de datos.</span><span class="sxs-lookup"><span data-stu-id="19a74-224">This process might take a few hours to complete based on the data volume.</span></span>

    ![Ejecución de desencadenador](media/data-factory-trigger.png)

    > [!NOTE]
    > <span data-ttu-id="19a74-226">Si tiene personalizaciones para **Cuenta**, **Contacto** y **Vendedor**, debe modificar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="19a74-226">If you have customizations for **Account**, **Contact**, and **Vendor** then you must modify the template.</span></span>

8. <span data-ttu-id="19a74-227">Importe los nuevos registros de **Parte** en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="19a74-227">Import the new **Party** records in the Finance and Operations app.</span></span>

    + <span data-ttu-id="19a74-228">Descargue el archivo `FONewParty.csv` de Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="19a74-228">Download the `FONewParty.csv` file from Azure blob storage.</span></span> <span data-ttu-id="19a74-229">La ruta es `partybootstrapping/output/FONewParty.csv`.</span><span class="sxs-lookup"><span data-stu-id="19a74-229">The path is `partybootstrapping/output/FONewParty.csv`.</span></span>
    + <span data-ttu-id="19a74-230">Convierta el archivo `FONewParty.csv` en un archivo de Excel e importe el archivo de Excel en la aplicación de Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="19a74-230">Convert the `FONewParty.csv` file into an Excel file and import the Excel file into the Finance and Operations app.</span></span>  <span data-ttu-id="19a74-231">Si la importación de csv funciona para usted, puede importar el archivo csv directamente.</span><span class="sxs-lookup"><span data-stu-id="19a74-231">If the csv import works for you, you can import csv file directly.</span></span> <span data-ttu-id="19a74-232">La importación puede tardar unas horas en ejecutarse, según el volumen de datos.</span><span class="sxs-lookup"><span data-stu-id="19a74-232">The import could take a few hours to run, depending on the data volume.</span></span> <span data-ttu-id="19a74-233">Para obtener más información, consulte [Resumen de trabajos de importación y exportación de datos](../data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="19a74-233">For more information, see [Data import and export jobs overview](../data-import-export-job.md).</span></span>

    ![Importar los registros del partido de Datavers](media/data-factory-import-party.png)

9. <span data-ttu-id="19a74-235">En la aplicación de interacción con el cliente, habilite los siguientes pasos del complemento:</span><span class="sxs-lookup"><span data-stu-id="19a74-235">In the customer engagement apps, enable the following plugin steps:</span></span>

    + <span data-ttu-id="19a74-236">Actualización de cuentas</span><span class="sxs-lookup"><span data-stu-id="19a74-236">Account Update</span></span>
         + <span data-ttu-id="19a74-237">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: actualización de cuenta</span><span class="sxs-lookup"><span data-stu-id="19a74-237">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="19a74-238">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: actualización de cuenta</span><span class="sxs-lookup"><span data-stu-id="19a74-238">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="19a74-239">Actualización de contacto</span><span class="sxs-lookup"><span data-stu-id="19a74-239">Contact Update</span></span>
         + <span data-ttu-id="19a74-240">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: actualización de contacto</span><span class="sxs-lookup"><span data-stu-id="19a74-240">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="19a74-241">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: actualización de contacto</span><span class="sxs-lookup"><span data-stu-id="19a74-241">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="19a74-242">Actualización de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="19a74-242">msdyn_party Update</span></span>
         + <span data-ttu-id="19a74-243">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: actualización de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="19a74-243">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="19a74-244">Actualización de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="19a74-244">msdyn_vendor Update</span></span>
         + <span data-ttu-id="19a74-245">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: actualización de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="19a74-245">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

10. <span data-ttu-id="19a74-246">En las aplicaciones de participación del cliente, active los siguientes flujos de trabajo si los desactivó en los pasos anteriores:</span><span class="sxs-lookup"><span data-stu-id="19a74-246">In the customer engagement apps, activate the following workflows if you deactivated them in previous steps:</span></span>

    + <span data-ttu-id="19a74-247">Crear proveedores en la tabla Cuentas</span><span class="sxs-lookup"><span data-stu-id="19a74-247">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="19a74-248">Crear proveedores en la tabla Cuentas</span><span class="sxs-lookup"><span data-stu-id="19a74-248">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="19a74-249">Crear proveedores de tipo persona en la tabla Contactos</span><span class="sxs-lookup"><span data-stu-id="19a74-249">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="19a74-250">Crear proveedores de tipo Persona en la tabla Proveedores</span><span class="sxs-lookup"><span data-stu-id="19a74-250">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="19a74-251">Actualizar proveedores en la tabla Cuentas</span><span class="sxs-lookup"><span data-stu-id="19a74-251">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="19a74-252">Actualizar proveedores en la tabla Proveedores</span><span class="sxs-lookup"><span data-stu-id="19a74-252">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="19a74-253">Actualizar proveedores de tipo Persona en la tabla Contactos</span><span class="sxs-lookup"><span data-stu-id="19a74-253">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="19a74-254">Actualizar proveedores de tipo Persona en la tabla Proveedores</span><span class="sxs-lookup"><span data-stu-id="19a74-254">Update Vendors of type Person in Vendors Table</span></span>

11. <span data-ttu-id="19a74-255">Ejecute los mapas relacionados con la **Parte** como se indica en [Parte y libreta de direcciones global](party-gab.md).</span><span class="sxs-lookup"><span data-stu-id="19a74-255">Run the **Party**-related maps as instructed in [Party and global address book](party-gab.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="19a74-256">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="19a74-256">Troubleshooting</span></span>

1. <span data-ttu-id="19a74-257">Si el proceso falla, vuelva a ejecutar la factoría de datos a partir de la actividad fallida.</span><span class="sxs-lookup"><span data-stu-id="19a74-257">In the process fails, rerun the data factory starting from the failed activity.</span></span>
2. <span data-ttu-id="19a74-258">La factoría de datos genera algunos archivos que puede utilizar con fines de validación de datos.</span><span class="sxs-lookup"><span data-stu-id="19a74-258">Some files are generated by the data factory that you can use for data validation purpose.</span></span>
3. <span data-ttu-id="19a74-259">La factoría de datos se ejecuta en función de archivos csv delimitados por comas.</span><span class="sxs-lookup"><span data-stu-id="19a74-259">The data factory runs based on csv files that are comma-delimited.</span></span> <span data-ttu-id="19a74-260">Si hay un valor de campo que tiene una coma, puede interferir con los resultados.</span><span class="sxs-lookup"><span data-stu-id="19a74-260">If there is a field value that has a comma, it may interfere with the results.</span></span> <span data-ttu-id="19a74-261">Necesitas quitar las comas.</span><span class="sxs-lookup"><span data-stu-id="19a74-261">You need to remove the commas.</span></span>
4. <span data-ttu-id="19a74-262">La pestaña **Supervisión** proporciona información sobre todos los pasos y datos procesados.</span><span class="sxs-lookup"><span data-stu-id="19a74-262">The **Monitoring** tab provides information about all steps and data processed.</span></span> <span data-ttu-id="19a74-263">Seleccione un paso específico para depurarlo.</span><span class="sxs-lookup"><span data-stu-id="19a74-263">Select a specific step to debug it.</span></span>

    ![Pestaña de seguimiento](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a><span data-ttu-id="19a74-265">Más información sobre la plantilla</span><span class="sxs-lookup"><span data-stu-id="19a74-265">Learn more about the template</span></span>

<span data-ttu-id="19a74-266">Puede encontrar comentarios para la plantilla en el archivo [readme.md](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).</span><span class="sxs-lookup"><span data-stu-id="19a74-266">You can find comments for the template the [readme.md](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md) file.</span></span>