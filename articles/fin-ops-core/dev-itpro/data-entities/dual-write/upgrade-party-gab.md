---
title: Actualizar al modelo de parte y libreta de direcciones global
description: Este tema describe cómo actualizar datos de escritura dual al modelo de libreta de direcciones global y de grupo.
author: RamaKrishnamoorthy
ms.date: 03/31/2021
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2021-03-31
ms.openlocfilehash: 90ddbe704ab21d62752b581a813601e8986c2103
ms.sourcegitcommit: 180548e3c10459776cf199989d3753e0c1555912
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2021
ms.locfileid: "6112682"
---
# <a name="upgrade-to-the-party-and-global-address-book-model"></a><span data-ttu-id="782c7-103">Actualizar al modelo de parte y libreta de direcciones global</span><span class="sxs-lookup"><span data-stu-id="782c7-103">Upgrade to the party and global address book model</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="782c7-104">La [Plantilla de Microsoft Azure Data Factory](https://aka.ms/dual-write-gab-adf) le ayuda a actualizar los datos de tabla **Cuenta**, **Contacto** y **Proveedor** en escritura dual en el modelo de libreta de direcciones global y de grupo.</span><span class="sxs-lookup"><span data-stu-id="782c7-104">The [Microsoft Azure Data Factory template](https://aka.ms/dual-write-gab-adf) helps you upgrade existing **Account**, **Contact**, and **Vendor** table data in dual-write to the party and global address book model.</span></span> <span data-ttu-id="782c7-105">La plantilla reconcilia los datos de aplicaciones de aplicaciones Finance and Operations y aplicaciones Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="782c7-105">The template reconciles the data from both finance and operations apps and customer engagement applications.</span></span> <span data-ttu-id="782c7-106">Al final del proceso, los campos **Parte** y **Contacto** de registros de **Parte** se crearán y asociarán con los registros **Cuenta**, **Contacto** y **Vendedor** en aplicaciones de participación del cliente.</span><span class="sxs-lookup"><span data-stu-id="782c7-106">At the end of the process, **Party** and **Contact** fields for **Party** records will be created and associated with **Account**, **Contact**, and **Vendor** records in customer engagement applications.</span></span> <span data-ttu-id="782c7-107">Un archivo .csv (`FONewParty.csv`) se genera para crear nuevos registros de **Parte** dentro de la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="782c7-107">A .csv file (`FONewParty.csv`) is generated to create new **Party** records inside the finance and operations app.</span></span> <span data-ttu-id="782c7-108">Este tema proporciona instrucciones sobre cómo usar la plantilla de Data Factory y actualizar sus datos.</span><span class="sxs-lookup"><span data-stu-id="782c7-108">This topic provides instructions about how to use the Data Factory template and upgrade your data.</span></span>

<span data-ttu-id="782c7-109">Si no tiene ninguna personalización, puede usar la plantilla tal cual.</span><span class="sxs-lookup"><span data-stu-id="782c7-109">If you don’t have any customizations, you can use the template as is.</span></span> <span data-ttu-id="782c7-110">Si tiene personalizaciones para **Cuenta**, **Contacto** y **Vendedor**, debe modificar la plantilla siguiendo las siguientes instrucciones.</span><span class="sxs-lookup"><span data-stu-id="782c7-110">If you have customizations for **Account**, **Contact**, and **Vendor** then you must modify the template using the following instructions.</span></span>

> [!NOTE]
> <span data-ttu-id="782c7-111">La plantilla solo actualiza los datos de **Parte**.</span><span class="sxs-lookup"><span data-stu-id="782c7-111">The template only upgrades the **Party** data.</span></span> <span data-ttu-id="782c7-112">En una versión futura, se incluirán direcciones postales y electrónicas.</span><span class="sxs-lookup"><span data-stu-id="782c7-112">In a future release, postal and electronic addresses will be included.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="782c7-113">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="782c7-113">Prerequisites</span></span>

<span data-ttu-id="782c7-114">Se requieren los siguientes requisitos previos para actualizar al modelo de libreta de direcciones global y de grupo:</span><span class="sxs-lookup"><span data-stu-id="782c7-114">The following prerequisites are required to upgrade to the party and global address book model:</span></span>

+ [<span data-ttu-id="782c7-115">Suscripción a Azure</span><span class="sxs-lookup"><span data-stu-id="782c7-115">Azure subscription</span></span>](https://portal.azure.com/)
+ [<span data-ttu-id="782c7-116">Acceso a la plantilla</span><span class="sxs-lookup"><span data-stu-id="782c7-116">Access to the template</span></span>](https://aka.ms/dual-write-gab-adf)
+ <span data-ttu-id="782c7-117">Debe ser un cliente de escritura dual existente.</span><span class="sxs-lookup"><span data-stu-id="782c7-117">You must be an existing dual-write customer.</span></span>

## <a name="prepare-for-the-upgrade"></a><span data-ttu-id="782c7-118">Prepararse para la actualización</span><span class="sxs-lookup"><span data-stu-id="782c7-118">Prepare for the upgrade</span></span>
<span data-ttu-id="782c7-119">Se necesitan las siguientes actividades para prepararse para la actualización:</span><span class="sxs-lookup"><span data-stu-id="782c7-119">The following activities are needed to prepare for the upgrade:</span></span>

+ <span data-ttu-id="782c7-120">**Totalmente sincronizado**: ambos entornos están en un estado completamente sincronizado para **Cuenta (cliente)**, **Contacto** y **Proveedor**.</span><span class="sxs-lookup"><span data-stu-id="782c7-120">**Fully synced**: Both environments are in a fully synced state for **Account (Customer)**, **Contact**, and **Vendor**.</span></span>
+ <span data-ttu-id="782c7-121">**Claves de integración**: las tablas **Cuenta (cliente)**, **Contacto** y **Vendedor** de las aplicaciones de interacción con el cliente utilizan las claves de integración que se envían listas para usar.</span><span class="sxs-lookup"><span data-stu-id="782c7-121">**Integration keys**: **Account (Customer)**, **Contact**, and **Vendor** tables in customer engagement apps are using the integration keys that shipped out-of-the-box.</span></span> <span data-ttu-id="782c7-122">Si personalizó las claves de integración, debe personalizar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="782c7-122">If you customized the integration keys, you must customize the template.</span></span>
+ <span data-ttu-id="782c7-123">**Número de parte**: todos los registros de **Cuenta (cliente)**, **Contacto** y **Vendedor** que se actualizarán tienen un número de **Parte**.</span><span class="sxs-lookup"><span data-stu-id="782c7-123">**Party number**: All **Account (Customer)**, **Contact**, and **Vendor** records that will be upgraded have a **Party** number.</span></span> <span data-ttu-id="782c7-124">Los registros sin número de **Parte** se ignorarán.</span><span class="sxs-lookup"><span data-stu-id="782c7-124">Records without a **Party** number will be ignored.</span></span> <span data-ttu-id="782c7-125">Si desea actualizar esos registros, agregue un número de **Parte** antes de iniciar el proceso de actualización.</span><span class="sxs-lookup"><span data-stu-id="782c7-125">If you want to upgrade those records, add a **Party** number to them before you start the upgrade process.</span></span>
+ <span data-ttu-id="782c7-126">**Interrupción del sistema**: durante el proceso de actualización, deberá desconectar los entornos de Finance and Operations y entornos sin conexión Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="782c7-126">**System outage**: During the upgrade process, you will have to take both the finance and operations and customer engagement environments offline.</span></span>
+ <span data-ttu-id="782c7-127">**Instantánea**: toma instantáneas de aplicaciones de Finance and Operaciones y aplicaciones Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="782c7-127">**Snapshot**: Take snapshots of both the finance and operations apps and customer engagement apps.</span></span> <span data-ttu-id="782c7-128">Utilice las instantáneas para restaurar el estado anterior si es necesario.</span><span class="sxs-lookup"><span data-stu-id="782c7-128">Use the snapshots to restore the previous state if you need to.</span></span>

## <a name="deployment"></a><span data-ttu-id="782c7-129">Implementación</span><span class="sxs-lookup"><span data-stu-id="782c7-129">Deployment</span></span>

1. <span data-ttu-id="782c7-130">Descarga la plantilla de [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span><span class="sxs-lookup"><span data-stu-id="782c7-130">Download the template from [Dynamics-365-FastTrack-Implementation-Assets](https://aka.ms/dual-write-gab-adf).</span></span>

2. <span data-ttu-id="782c7-131">Inicie sesión en [Microsoft Azure](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="782c7-131">Sign in to [Microsoft Azure](https://portal.azure.com/).</span></span>

3. <span data-ttu-id="782c7-132">Cree un [grupo de recursos](/azure/azure-resource-manager/management/manage-resource-groups-portal).</span><span class="sxs-lookup"><span data-stu-id="782c7-132">Create a [resource group](/azure/azure-resource-manager/management/manage-resource-groups-portal).</span></span>

4. <span data-ttu-id="782c7-133">Cree una [cuenta de almacenamiento](/azure/storage/common/storage-account-create?tabs=azure-portal) en el grupo de recursos que creó.</span><span class="sxs-lookup"><span data-stu-id="782c7-133">Create a [storage account](/azure/storage/common/storage-account-create?tabs=azure-portal) in the resource group that you created.</span></span>

5. <span data-ttu-id="782c7-134">Cree una [factoría de datos](/azure/data-factory/quickstart-create-data-factory-portal) en el grupo de recursos anterior que creó.</span><span class="sxs-lookup"><span data-stu-id="782c7-134">Create a [data factory](/azure/data-factory/quickstart-create-data-factory-portal) in above resource group that you created.</span></span>

6. <span data-ttu-id="782c7-135">Abra la fábrica de datos y seleccione el mosaico **Autor y monitor**.</span><span class="sxs-lookup"><span data-stu-id="782c7-135">Open the data factory and select the **Author & Monitor** tile.</span></span>

7. <span data-ttu-id="782c7-136">Sobre la pestaña **Gestionar**, seleccione **Plantilla ARM**.</span><span class="sxs-lookup"><span data-stu-id="782c7-136">On the **Manage** tab, select **ARM template**.</span></span>

8. <span data-ttu-id="782c7-137">Seleccione **Importar plantilla ARM** para importar la plantilla de **Parte**.</span><span class="sxs-lookup"><span data-stu-id="782c7-137">Select the **Import ARM template** to import the **Party** template.</span></span>

9. <span data-ttu-id="782c7-138">Importe la plantilla a la factoría de datos.</span><span class="sxs-lookup"><span data-stu-id="782c7-138">Import the template into the data factory.</span></span> <span data-ttu-id="782c7-139">Ingrese los siguientes valores para **Detalles del proyecto** y **Detalles de la instancia**.</span><span class="sxs-lookup"><span data-stu-id="782c7-139">Enter the following values for **Project details** and **Instance details**.</span></span>

    <span data-ttu-id="782c7-140">Campo</span><span class="sxs-lookup"><span data-stu-id="782c7-140">Field</span></span> | <span data-ttu-id="782c7-141">Valor</span><span class="sxs-lookup"><span data-stu-id="782c7-141">Value</span></span>
    ---|---
    <span data-ttu-id="782c7-142">Suscripción</span><span class="sxs-lookup"><span data-stu-id="782c7-142">Subscription</span></span> | <span data-ttu-id="782c7-143">Suscripción a Azure</span><span class="sxs-lookup"><span data-stu-id="782c7-143">Azure subscription</span></span>
    <span data-ttu-id="782c7-144">Grupo de recursos</span><span class="sxs-lookup"><span data-stu-id="782c7-144">Resource group</span></span> | <span data-ttu-id="782c7-145">Proporcione el mismo recurso con el que se crea la cuenta de almacenamiento.</span><span class="sxs-lookup"><span data-stu-id="782c7-145">Provide same resource under which storage account is created.</span></span>
    <span data-ttu-id="782c7-146">Región</span><span class="sxs-lookup"><span data-stu-id="782c7-146">Region</span></span> | <span data-ttu-id="782c7-147">Especifique la región.</span><span class="sxs-lookup"><span data-stu-id="782c7-147">Specify region.</span></span>
    <span data-ttu-id="782c7-148">Nombre de la fábrica</span><span class="sxs-lookup"><span data-stu-id="782c7-148">Factory Name</span></span> | <span data-ttu-id="782c7-149">Especifique el nombre de la fábrica.</span><span class="sxs-lookup"><span data-stu-id="782c7-149">Specify factory name.</span></span>
    <span data-ttu-id="782c7-150">FO Linked Service_service Clave principal</span><span class="sxs-lookup"><span data-stu-id="782c7-150">FO Linked Service_service Principal Key</span></span> | <span data-ttu-id="782c7-151">Especifique la clave de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="782c7-151">Specify the application's key.</span></span>
    <span data-ttu-id="782c7-152">Cadena de conexión de Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="782c7-152">Azure Blob Storage_connection String</span></span> | <span data-ttu-id="782c7-153">Cadena de conexión de Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="782c7-153">Azure Blob storage connection string.</span></span>
    <span data-ttu-id="782c7-154">Contraseña de servicio vinculado de Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="782c7-154">Dynamics Crm Linked Service_password</span></span> | <span data-ttu-id="782c7-155">La contraseña de la cuenta de usuario que especificó como nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="782c7-155">The password for the user account you specified as the username.</span></span>
    <span data-ttu-id="782c7-156">FO Linked Service_properties_type Properties_url</span><span class="sxs-lookup"><span data-stu-id="782c7-156">FO Linked Service_properties_type Properties_url</span></span>  | `https://sampledynamics.sandbox-operationsdynamics.com/data`
    <span data-ttu-id="782c7-157">FO Linked Service_properties_type Properties_tenant</span><span class="sxs-lookup"><span data-stu-id="782c7-157">FO Linked Service_properties_type Properties_tenant</span></span> | <span data-ttu-id="782c7-158">Especifique la información del inquilino (nombre de dominio o ID de inquilino) bajo la cual reside su aplicación.</span><span class="sxs-lookup"><span data-stu-id="782c7-158">Specify the tenant information (domain name or tenant ID) under which your application resides.</span></span>
    <span data-ttu-id="782c7-159">FO Linked Service_properties_type Properties_aad Resource Id</span><span class="sxs-lookup"><span data-stu-id="782c7-159">FO Linked Service_properties_type Properties_aad Resource Id</span></span> | `https://sampledynamics.sandboxoperationsdynamics.com`
    <span data-ttu-id="782c7-160">FO Linked Service_properties_type Properties_service Principal Id</span><span class="sxs-lookup"><span data-stu-id="782c7-160">FO Linked Service_properties_type Properties_service Principal Id</span></span> | <span data-ttu-id="782c7-161">Especifique el Id. de cliente de la aplicación.</span><span class="sxs-lookup"><span data-stu-id="782c7-161">Specify the application's client ID.</span></span>
    <span data-ttu-id="782c7-162">Dynamics Crm Linked Service_properties_type Properties_username</span><span class="sxs-lookup"><span data-stu-id="782c7-162">Dynamics Crm Linked Service_properties_type Properties_username</span></span> | <span data-ttu-id="782c7-163">El nombre de usuario para conectarse a Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="782c7-163">The username to connect to Dynamics 365.</span></span>

    <span data-ttu-id="782c7-164">Para obtener más información, consulte los temas siguientes:</span><span class="sxs-lookup"><span data-stu-id="782c7-164">For additional information, refer to the following topics:</span></span> 
    
    - [<span data-ttu-id="782c7-165">Promocionar manualmente una plantilla de Resource Manager para cada entorno</span><span class="sxs-lookup"><span data-stu-id="782c7-165">Manually promote a Resource Manager template for each environment</span></span>](/azure/data-factory/continuous-integration-deployment#manually-promote-a-resource-manager-template-for-each-environment)
    - [<span data-ttu-id="782c7-166">Propiedades de servicios vinculados</span><span class="sxs-lookup"><span data-stu-id="782c7-166">Linked service properties</span></span>](/azure/data-factory/connector-dynamics-ax#linked-service-properties)
    - [<span data-ttu-id="782c7-167">Copiar datos con Azure Data Factory</span><span class="sxs-lookup"><span data-stu-id="782c7-167">Copy data using Azure Data Factory</span></span>](/azure/data-factory/connector-dynamics-crm-office-365#dynamics-365-and-dynamics-crm-online)

10. <span data-ttu-id="782c7-168">Después de la implementación, valide los conjuntos de datos, el flujo de datos y el servicio vinculado de la factoría de datos.</span><span class="sxs-lookup"><span data-stu-id="782c7-168">After deployment, validate the datasets, data flow, and linked service of the data factory.</span></span>

   ![Conjuntos de datos, flujo de datos y servicio vinculado](media/data-factory-validate.png)

11. <span data-ttu-id="782c7-170">Navegar a **Gestionar**.</span><span class="sxs-lookup"><span data-stu-id="782c7-170">Navigate to **Manage**.</span></span> <span data-ttu-id="782c7-171">Debajo de **Conexiones**, seleccione **Servicio vinculado**.</span><span class="sxs-lookup"><span data-stu-id="782c7-171">Under **Connections**, select **Linked Service**.</span></span> <span data-ttu-id="782c7-172">Seleccione **DynamicsCrmLinkedService**.</span><span class="sxs-lookup"><span data-stu-id="782c7-172">Select **DynamicsCrmLinkedService**.</span></span> <span data-ttu-id="782c7-173">En el formulario **Editar servicio vinculado (Dynamics CRM)**, ingrese los siguientes valores.</span><span class="sxs-lookup"><span data-stu-id="782c7-173">In the **Edit linked service (Dynamics CRM)** form, enter the following values.</span></span>

    <span data-ttu-id="782c7-174">Campo</span><span class="sxs-lookup"><span data-stu-id="782c7-174">Field</span></span> | <span data-ttu-id="782c7-175">Valor</span><span class="sxs-lookup"><span data-stu-id="782c7-175">Value</span></span>
    ---|---
    <span data-ttu-id="782c7-176">Nombre</span><span class="sxs-lookup"><span data-stu-id="782c7-176">Name</span></span> | <span data-ttu-id="782c7-177">DynamicsCrmLinkedService</span><span class="sxs-lookup"><span data-stu-id="782c7-177">DynamicsCrmLinkedService</span></span>
    <span data-ttu-id="782c7-178">Descripción</span><span class="sxs-lookup"><span data-stu-id="782c7-178">Description</span></span> | <span data-ttu-id="782c7-179">Servicios vinculados para conectarse con la instancia de CRM para obtener datos de entidades</span><span class="sxs-lookup"><span data-stu-id="782c7-179">Linked services to connect with CRM instance to fetch entities data</span></span>
    <span data-ttu-id="782c7-180">Conectarse a través del tiempo de ejecución de integración</span><span class="sxs-lookup"><span data-stu-id="782c7-180">Connect via integration runtime</span></span> | <span data-ttu-id="782c7-181">AutoResolvelntegrationRuntime</span><span class="sxs-lookup"><span data-stu-id="782c7-181">AutoResolvelntegrationRuntime</span></span>
    <span data-ttu-id="782c7-182">Tipo de implementación</span><span class="sxs-lookup"><span data-stu-id="782c7-182">Deployment type</span></span> | <span data-ttu-id="782c7-183">En línea</span><span class="sxs-lookup"><span data-stu-id="782c7-183">Online</span></span>
    <span data-ttu-id="782c7-184">URI del servicio</span><span class="sxs-lookup"><span data-stu-id="782c7-184">Service Uri</span></span> | `https://<organization-name>.crm[x].dynamics.com`
    <span data-ttu-id="782c7-185">Tipo de autenticación</span><span class="sxs-lookup"><span data-stu-id="782c7-185">Authentication type</span></span> | <span data-ttu-id="782c7-186">Office365</span><span class="sxs-lookup"><span data-stu-id="782c7-186">Office365</span></span>
    <span data-ttu-id="782c7-187">Nombre de usuario</span><span class="sxs-lookup"><span data-stu-id="782c7-187">User name</span></span> |
    <span data-ttu-id="782c7-188">Contraseña o Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="782c7-188">Password or Azure Key Vault</span></span> | <span data-ttu-id="782c7-189">Contraseña</span><span class="sxs-lookup"><span data-stu-id="782c7-189">Password</span></span>
    <span data-ttu-id="782c7-190">Contraseña</span><span class="sxs-lookup"><span data-stu-id="782c7-190">Password</span></span> |

## <a name="run-the-template"></a><span data-ttu-id="782c7-191">Ejecutar la plantilla</span><span class="sxs-lookup"><span data-stu-id="782c7-191">Run the template</span></span>

1. <span data-ttu-id="782c7-192">Detenga las asignaciones de doble escritura de **Cuenta**, **Contacto** y **Proveedor** a continuación usando la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="782c7-192">Stop the following **Account**, **Contact**, and **Vendor** dual-write maps using the Finance and Operations app.</span></span>

    + <span data-ttu-id="782c7-193">Clientes V3 (cuentas)</span><span class="sxs-lookup"><span data-stu-id="782c7-193">Customers V3(accounts)</span></span>
    + <span data-ttu-id="782c7-194">Clientes V3 (contactos)</span><span class="sxs-lookup"><span data-stu-id="782c7-194">Customers V3(contacts)</span></span>
    + <span data-ttu-id="782c7-195">Contactos de CDS V2 (contactos)</span><span class="sxs-lookup"><span data-stu-id="782c7-195">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="782c7-196">Contactos de CDS V2 (contactos)</span><span class="sxs-lookup"><span data-stu-id="782c7-196">CDS Contacts V2(contacts)</span></span>
    + <span data-ttu-id="782c7-197">Proveedor V2 (msdyn_vendors)</span><span class="sxs-lookup"><span data-stu-id="782c7-197">Vendor V2 (msdyn_vendor)</span></span>

2. <span data-ttu-id="782c7-198">Asegúrese de que los mapas se eliminen de la tabla `msdy_dualwriteruntimeconfig` en Dataverse.</span><span class="sxs-lookup"><span data-stu-id="782c7-198">Make sure the maps are removed from the `msdy_dualwriteruntimeconfig` table in Dataverse.</span></span>

3. <span data-ttu-id="782c7-199">Instale [Soluciones de libreta de direcciones global y de fiesta de escritura dual](https://aka.ms/dual-write-gab) de AppSource.</span><span class="sxs-lookup"><span data-stu-id="782c7-199">Install [Dual-write Party and Global Address Book Solutions](https://aka.ms/dual-write-gab) from AppSource.</span></span>

4. <span data-ttu-id="782c7-200">En la aplicación Finance and Operations, si las siguientes tablas contienen datos, ejecuta **Sincronización inicial** para ellos.</span><span class="sxs-lookup"><span data-stu-id="782c7-200">In the finance and operations app, if the following tables contain data, then run **Initial Sync** for them.</span></span>

    + <span data-ttu-id="782c7-201">Formas de saludo</span><span class="sxs-lookup"><span data-stu-id="782c7-201">Salutations</span></span>
    + <span data-ttu-id="782c7-202">Tipos de carácter personal</span><span class="sxs-lookup"><span data-stu-id="782c7-202">Personal character types</span></span>
    + <span data-ttu-id="782c7-203">Cierre de agradecimiento</span><span class="sxs-lookup"><span data-stu-id="782c7-203">Complimentary closing</span></span>
    + <span data-ttu-id="782c7-204">Cargos de persona de contacto</span><span class="sxs-lookup"><span data-stu-id="782c7-204">Contact person titles</span></span>
    + <span data-ttu-id="782c7-205">Roles de toma de decisiones</span><span class="sxs-lookup"><span data-stu-id="782c7-205">Decision making roles</span></span>
    + <span data-ttu-id="782c7-206">Niveles de fidelización</span><span class="sxs-lookup"><span data-stu-id="782c7-206">Loyalty levels</span></span>

5. <span data-ttu-id="782c7-207">En la aplicación de interacción con el cliente, desactive los siguientes pasos del complemento.</span><span class="sxs-lookup"><span data-stu-id="782c7-207">In the customer engagement app, disable the following plug-in steps.</span></span>

    + <span data-ttu-id="782c7-208">Actualización de cuenta</span><span class="sxs-lookup"><span data-stu-id="782c7-208">Account Update</span></span>
         + <span data-ttu-id="782c7-209">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: actualización de cuenta</span><span class="sxs-lookup"><span data-stu-id="782c7-209">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="782c7-210">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: actualización de cuenta</span><span class="sxs-lookup"><span data-stu-id="782c7-210">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="782c7-211">Actualización de contacto</span><span class="sxs-lookup"><span data-stu-id="782c7-211">Contact Update</span></span>
         + <span data-ttu-id="782c7-212">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: actualización de contacto</span><span class="sxs-lookup"><span data-stu-id="782c7-212">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="782c7-213">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: actualización de contacto</span><span class="sxs-lookup"><span data-stu-id="782c7-213">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="782c7-214">Actualización de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="782c7-214">msdyn_party Update</span></span>
         + <span data-ttu-id="782c7-215">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: actualización de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="782c7-215">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="782c7-216">Actualización de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="782c7-216">msdyn_vendor Update</span></span>
         + <span data-ttu-id="782c7-217">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: actualización de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="782c7-217">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

6. <span data-ttu-id="782c7-218">En la aplicación de interacción con el cliente, desactive los siguientes flujos de trabajo:</span><span class="sxs-lookup"><span data-stu-id="782c7-218">In the customer engagement app, disable the following workflows:</span></span>

    + <span data-ttu-id="782c7-219">Crear proveedores en la tabla Cuentas</span><span class="sxs-lookup"><span data-stu-id="782c7-219">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="782c7-220">Crear proveedores en la tabla Cuentas</span><span class="sxs-lookup"><span data-stu-id="782c7-220">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="782c7-221">Crear proveedores de tipo persona en la tabla Contactos</span><span class="sxs-lookup"><span data-stu-id="782c7-221">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="782c7-222">Crear proveedores de tipo Persona en la tabla Proveedores</span><span class="sxs-lookup"><span data-stu-id="782c7-222">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="782c7-223">Actualizar proveedores en la tabla Cuentas</span><span class="sxs-lookup"><span data-stu-id="782c7-223">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="782c7-224">Actualizar proveedores en la tabla Proveedores</span><span class="sxs-lookup"><span data-stu-id="782c7-224">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="782c7-225">Actualizar proveedores de tipo Persona en la tabla Contactos</span><span class="sxs-lookup"><span data-stu-id="782c7-225">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="782c7-226">Actualizar proveedores de tipo Persona en la tabla Proveedores</span><span class="sxs-lookup"><span data-stu-id="782c7-226">Update Vendors of type Person in Vendors Table</span></span>

7. <span data-ttu-id="782c7-227">En la factoría de datos, ejecute la plantilla seleccionando **Activar ahora** como se muestra en la siguiente imagen.</span><span class="sxs-lookup"><span data-stu-id="782c7-227">In the data factory, run the template by selecting **Trigger now** as shown in the following image.</span></span> <span data-ttu-id="782c7-228">Este proceso puede tardar algunas horas en completarse según el volumen de datos.</span><span class="sxs-lookup"><span data-stu-id="782c7-228">This process might take a few hours to complete based on the data volume.</span></span>

    ![Ejecución de desencadenador](media/data-factory-trigger.png)

    > [!NOTE]
    > <span data-ttu-id="782c7-230">Si tiene personalizaciones para **Cuenta**, **Contacto** y **Proveedor**, debe modificar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="782c7-230">If you have customizations for **Account**, **Contact**, and **Vendor**, then you need to modify the template.</span></span>

8. <span data-ttu-id="782c7-231">Importe los nuevos registros de **Parte** en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="782c7-231">Import the new **Party** records in the Finance and Operations app.</span></span>

    + <span data-ttu-id="782c7-232">Descargue el archivo `FONewParty.csv` de Azure Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="782c7-232">Download the `FONewParty.csv` file from Azure blob storage.</span></span> <span data-ttu-id="782c7-233">La ruta es `partybootstrapping/output/FONewParty.csv`.</span><span class="sxs-lookup"><span data-stu-id="782c7-233">The path is `partybootstrapping/output/FONewParty.csv`.</span></span>
    + <span data-ttu-id="782c7-234">Convierta el archivo `FONewParty.csv` en un archivo de Excel e importe el archivo de Excel en la aplicación de Finances and Operations.</span><span class="sxs-lookup"><span data-stu-id="782c7-234">Convert the `FONewParty.csv` file into an Excel file and import the Excel file into the finance and operations app.</span></span> <span data-ttu-id="782c7-235">Si la importación de csv funciona para usted, puede importar el archivo csv directamente.</span><span class="sxs-lookup"><span data-stu-id="782c7-235">If the csv import works for you, you can import the csv file directly.</span></span> <span data-ttu-id="782c7-236">La importación puede tardar unas horas en ejecutarse, según el volumen de datos.</span><span class="sxs-lookup"><span data-stu-id="782c7-236">The import could take a few hours to run, depending on the data volume.</span></span> <span data-ttu-id="782c7-237">Para obtener más información, consulte [Resumen de trabajos de importación y exportación de datos](../data-import-export-job.md).</span><span class="sxs-lookup"><span data-stu-id="782c7-237">For more information, see [Data import and export jobs overview](../data-import-export-job.md).</span></span>

    ![Importar los registros del partido de Datavers](media/data-factory-import-party.png)

9. <span data-ttu-id="782c7-239">En la aplicación de interacción con el cliente, habilite los siguientes pasos del complemento:</span><span class="sxs-lookup"><span data-stu-id="782c7-239">In the customer engagement apps, enable the following plug-in steps:</span></span>

    + <span data-ttu-id="782c7-240">Actualización de cuenta</span><span class="sxs-lookup"><span data-stu-id="782c7-240">Account Update</span></span>
         + <span data-ttu-id="782c7-241">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: actualización de cuenta</span><span class="sxs-lookup"><span data-stu-id="782c7-241">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromAccountEntity: Update of account</span></span>
         + <span data-ttu-id="782c7-242">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: actualización de cuenta</span><span class="sxs-lookup"><span data-stu-id="782c7-242">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForCustomerTypeCodes: Update of account</span></span>
    + <span data-ttu-id="782c7-243">Actualización de contacto</span><span class="sxs-lookup"><span data-stu-id="782c7-243">Contact Update</span></span>
         + <span data-ttu-id="782c7-244">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: actualización de contacto</span><span class="sxs-lookup"><span data-stu-id="782c7-244">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromContactEntity: Update of contact</span></span>
         + <span data-ttu-id="782c7-245">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: actualización de contacto</span><span class="sxs-lookup"><span data-stu-id="782c7-245">Microsoft.Dynamics.FinanceExtended.Plugins.TriggerNotesForSellableContact: Update of contact</span></span>
    + <span data-ttu-id="782c7-246">Actualización de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="782c7-246">msdyn_party Update</span></span>
         + <span data-ttu-id="782c7-247">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: actualización de msdyn_party</span><span class="sxs-lookup"><span data-stu-id="782c7-247">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromPartyEntity: Update of msdyn_party</span></span>
    + <span data-ttu-id="782c7-248">Actualización de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="782c7-248">msdyn_vendor Update</span></span>
         + <span data-ttu-id="782c7-249">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: actualización de msdyn_vendor</span><span class="sxs-lookup"><span data-stu-id="782c7-249">Microsoft.Dynamics.GABExtended.Plugins.UpdatePartyAttributesFromVendorEntity: Update of msdyn_vendor</span></span>

10. <span data-ttu-id="782c7-250">En las aplicaciones de participación del cliente, active los siguientes flujos de trabajo si los desactivó en los pasos anteriores:</span><span class="sxs-lookup"><span data-stu-id="782c7-250">In the customer engagement apps, activate the following workflows if you deactivated them in previous steps:</span></span>

    + <span data-ttu-id="782c7-251">Crear proveedores en la tabla Cuentas</span><span class="sxs-lookup"><span data-stu-id="782c7-251">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="782c7-252">Crear proveedores en la tabla Cuentas</span><span class="sxs-lookup"><span data-stu-id="782c7-252">Create Vendors in Accounts Table</span></span>
    + <span data-ttu-id="782c7-253">Crear proveedores de tipo persona en la tabla Contactos</span><span class="sxs-lookup"><span data-stu-id="782c7-253">Create Vendors of type person in Contacts Table</span></span>
    + <span data-ttu-id="782c7-254">Crear proveedores de tipo Persona en la tabla Proveedores</span><span class="sxs-lookup"><span data-stu-id="782c7-254">Create Vendors of type Person in Vendors Table</span></span>
    + <span data-ttu-id="782c7-255">Actualizar proveedores en la tabla Cuentas</span><span class="sxs-lookup"><span data-stu-id="782c7-255">Update Vendors in Accounts Table</span></span>
    + <span data-ttu-id="782c7-256">Actualizar proveedores en la tabla Proveedores</span><span class="sxs-lookup"><span data-stu-id="782c7-256">Update Vendors in Vendors Table</span></span>
    + <span data-ttu-id="782c7-257">Actualizar proveedores de tipo Persona en la tabla Contactos</span><span class="sxs-lookup"><span data-stu-id="782c7-257">Update Vendors of type Person in Contacts Table</span></span>
    + <span data-ttu-id="782c7-258">Actualizar proveedores de tipo Persona en la tabla Proveedores</span><span class="sxs-lookup"><span data-stu-id="782c7-258">Update Vendors of type Person in Vendors Table</span></span>

11. <span data-ttu-id="782c7-259">Ejecute los mapas relacionados con la **Parte** como se indica en [Parte y libreta de direcciones global](party-gab.md).</span><span class="sxs-lookup"><span data-stu-id="782c7-259">Run the **Party**-related maps as instructed in [Party and global address book](party-gab.md).</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="782c7-260">Solución de problemas</span><span class="sxs-lookup"><span data-stu-id="782c7-260">Troubleshooting</span></span>

1. <span data-ttu-id="782c7-261">Si el proceso falla, vuelva a ejecutar la factoría de datos a partir de la actividad fallida.</span><span class="sxs-lookup"><span data-stu-id="782c7-261">If the process fails, rerun the data factory starting from the failed activity.</span></span>
2. <span data-ttu-id="782c7-262">La factoría de datos genera algunos archivos que puede utilizar con fines de validación de datos.</span><span class="sxs-lookup"><span data-stu-id="782c7-262">Some files are generated by the data factory that you can use for data validation purpose.</span></span>
3. <span data-ttu-id="782c7-263">La factoría de datos se ejecuta en función de archivos csv delimitados por comas.</span><span class="sxs-lookup"><span data-stu-id="782c7-263">The data factory runs based on csv files that are comma-delimited.</span></span> <span data-ttu-id="782c7-264">Si hay un valor de campo que tiene una coma, puede interferir con los resultados.</span><span class="sxs-lookup"><span data-stu-id="782c7-264">If there is a field value that has a comma, it may interfere with the results.</span></span> <span data-ttu-id="782c7-265">Necesitas quitar las comas.</span><span class="sxs-lookup"><span data-stu-id="782c7-265">You need to remove the commas.</span></span>
4. <span data-ttu-id="782c7-266">La pestaña **Supervisión** proporciona información sobre todos los pasos y datos procesados.</span><span class="sxs-lookup"><span data-stu-id="782c7-266">The **Monitoring** tab provides information about all steps and data processed.</span></span> <span data-ttu-id="782c7-267">Seleccione un paso específico para depurarlo.</span><span class="sxs-lookup"><span data-stu-id="782c7-267">Select a specific step to debug it.</span></span>

    ![Pestaña de seguimiento](media/data-factory-monitor.png)

## <a name="learn-more-about-the-template"></a><span data-ttu-id="782c7-269">Más información sobre la plantilla</span><span class="sxs-lookup"><span data-stu-id="782c7-269">Learn more about the template</span></span>

<span data-ttu-id="782c7-270">Puede encontrar información adicional sobre la plantilla en [Comentarios para el archivo Léame de la plantilla de Azure Data Factory](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).</span><span class="sxs-lookup"><span data-stu-id="782c7-270">You can find additional information about the template in [Comments for Azure Data Factory template readme](https://github.com/microsoft/Dynamics-365-FastTrack-Implementation-Assets/blob/master/Dual-write/Upgrade%20data%20to%20dual-write%20Party-GAB%20schema/readme.md).</span></span>
