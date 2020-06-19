---
title: Solucionar problemas durante la sincronización
description: Este tema proporciona información para la solución de problemas que puede ayudarlo a solucionar problemas durante la sincronización inicial.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 10065039fce441d7f96f700ff826d959e96f2479
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410090"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="3af07-103">Solucionar problemas durante la sincronización</span><span class="sxs-lookup"><span data-stu-id="3af07-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="3af07-104">Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="3af07-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="3af07-105">Específicamente proporciona información que puede ayudarlo a solucionar problemas durante la sincronización inicial.</span><span class="sxs-lookup"><span data-stu-id="3af07-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3af07-106">Algunos de los problemas que aborda este tema pueden requerir la característica de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="3af07-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="3af07-107">La sección para cada problema explica si se requiere una característica o credenciales específicas.</span><span class="sxs-lookup"><span data-stu-id="3af07-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="3af07-108">Verificar los errores de sincronización inicial en una aplicación Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="3af07-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="3af07-109">Después de habilitar las plantillas de asignación, el estado de los mapas debe ser **Ejecutando**.</span><span class="sxs-lookup"><span data-stu-id="3af07-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="3af07-110">Si el estado es **No ejecutando**, se produjeron errores durante la sincronización inicial.</span><span class="sxs-lookup"><span data-stu-id="3af07-110">If the status is **Not running**, errors occurred during initial synchronization.</span></span> <span data-ttu-id="3af07-111">Para ver los errores, seleccione la pestaña **Detalles de sincronización inicial** en la página **Escritura doble**.</span><span class="sxs-lookup"><span data-stu-id="3af07-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Pestaña de detalles de sincronización inicial](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="3af07-113">No puede completar la sincronización inicial: 400 Solicitud incorrecta</span><span class="sxs-lookup"><span data-stu-id="3af07-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="3af07-114">**Rol requerido para arreglar el error:** Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="3af07-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="3af07-115">Es posible que reciba el siguiente mensaje de error cuando intente ejecutar la asignación y la sincronización inicial:</span><span class="sxs-lookup"><span data-stu-id="3af07-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="3af07-116">*El servidor remoto devolvió un error: (400) Solicitud incorrecta.), exportación AX encontró un error*</span><span class="sxs-lookup"><span data-stu-id="3af07-116">*The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="3af07-117">A continuación se muestra un ejemplo del mensaje de error completo.</span><span class="sxs-lookup"><span data-stu-id="3af07-117">Here is an example of the full error message.</span></span>

```console
Dual write Initial Sync completed with status: Error. Following are the details:
Executed leg: From AX Financial dimensions to CRM msdyn_dimensionattributes
with exported records count: 0, ImportRecordsErrorCount: 0,
ImportRecordsInsertedCount: 0 and ImportRecordsUpdatedCount: 0
ErrorsDetails:
Dual write Initial sync failed
Message: ([Bad Request], The remote server returned an error: (400) Bad Request.), AX export encountered an error
Stacktrace: at
Microsoft.Dynamics.Integrator.QueryGenerator.AxClient.\<ExportAxPackage\>d__16.MoveNext()
in X:\\bt\\1024532\\repo\\src\\Core\\QueryGenerator\\AxClient.cs:line 265
\--- End of stack trace from previous location where exception was thrown ---
at System.Runtime.ExceptionServices.ExceptionDispatchInfo.Throw()
at System.Runtime.CompilerServices.TaskAwaiter.HandleNonSuccessAndDebuggerNotification(Task task)
at Microsoft.D365.ServicePlatform.Context.ServiceContext.Activity.\<ExecuteAsync\>d__11\`2.MoveNext()
\--- End of stack trace from previous location where exception was thrown ---
```

<span data-ttu-id="3af07-118">Si este error ocurre de manera constante y no puede completar la sincronización inicial, siga estos pasos para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="3af07-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="3af07-119">Inicie sesión en la máquina virtual (VM) para la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3af07-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="3af07-120">Abra Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="3af07-120">Open Microsoft Management Console.</span></span>
3. <span data-ttu-id="3af07-121">En el panel **Servicios**, asegúrese de que el servicio de exportación de marco de Microsoft Dynamics 365 Data se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="3af07-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="3af07-122">Reinícielo si se ha detenido, porque la sincronización inicial lo requiere.</span><span class="sxs-lookup"><span data-stu-id="3af07-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="3af07-123">Error de sincronización inicial: 403 Prohibido</span><span class="sxs-lookup"><span data-stu-id="3af07-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="3af07-124">Es posible que reciba el siguiente mensaje de error durante la sincronización inicial:</span><span class="sxs-lookup"><span data-stu-id="3af07-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="3af07-125">*(\[Prohibido\], el servidor remoto devolvión un error: (403) Prohibido.), exportación AX encontró un error*</span><span class="sxs-lookup"><span data-stu-id="3af07-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="3af07-126">Para arreglar el problema, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="3af07-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="3af07-127">Iniciar sesión en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3af07-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="3af07-128">En la págona **aplicaciones Azure Active Directory**, elimine el cliente **DtAppID**, y luego agréguelo nuevamente.</span><span class="sxs-lookup"><span data-stu-id="3af07-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Lista de aplicaciones Azure AD](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a><span data-ttu-id="3af07-130">Errores de autorreferencia o de referencia circular durante la sincronización inicial</span><span class="sxs-lookup"><span data-stu-id="3af07-130">Self-reference or circular-reference failures during initial synchronization</span></span>

<span data-ttu-id="3af07-131">Es posible que reciba mensajes de error si alguna de sus asignaciones tiene autorreferencias o referencias circulares.</span><span class="sxs-lookup"><span data-stu-id="3af07-131">You might receive an error messages if any of your mappings have self-references or circular references.</span></span> <span data-ttu-id="3af07-132">Los errores se dividen en estas categorías:</span><span class="sxs-lookup"><span data-stu-id="3af07-132">The errors fall into these categories:</span></span>

- [<span data-ttu-id="3af07-133">Mapeo de entidades Proveedores V2 con msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="3af07-133">Vendors V2 to msdyn_vendors entity mapping</span></span>](#error-vendor-map)
- [<span data-ttu-id="3af07-134">Mapeo de entidades Clientes V3 a Cuentas</span><span class="sxs-lookup"><span data-stu-id="3af07-134">Customers V3 to Accounts entity mapping</span></span>](#error-customer-map)

## <a name="resolve-an-error-in-vendors-v2-to-msdyn_vendors-entity-mapping"></a><a id="error-vendor-map"></a><span data-ttu-id="3af07-135">Resolver un error en el mapeo de entidades Vendors V2 a msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="3af07-135">Resolve an error in Vendors V2 to msdyn_vendors entity mapping</span></span>

<span data-ttu-id="3af07-136">Puede encontrar los siguientes errores de sincronización inicial en el mapeo **Proveedores V2** con **msdyn_vendors** si las entidades tienen registros existentes con valores en los campos **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="3af07-136">You might run into the following initial sync errors on the **Vendors V2** to **msdyn_vendors** mapping if the entities have existing records with values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields.</span></span> <span data-ttu-id="3af07-137">Esto se debe a que **InvoiceVendorAccountNumber** es un campo de autorreferencia y **PrimaryContactPersonId** es una referencia circular en el mapeo del proveedor.</span><span class="sxs-lookup"><span data-stu-id="3af07-137">This because **InvoiceVendorAccountNumber** is a self-referencing field, and **PrimaryContactPersonId** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="3af07-138">*No se pudo resolver el guid para el campo: <field> . No se encontró la búsqueda: <value> . Pruebe estas URL para verificar si los datos de referencia existen: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span><span class="sxs-lookup"><span data-stu-id="3af07-138">*Couldn't resolve the guid for the field: <field>. The lookup was not found: <value>. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span></span>

<span data-ttu-id="3af07-139">Aquí hay un par de ejemplos:</span><span class="sxs-lookup"><span data-stu-id="3af07-139">Here are a couple of examples:</span></span>

- <span data-ttu-id="3af07-140">*No se pudo resolver el guid para el campo: msdyn_vendorprimarycontactperson.msdyn_contactpersonid. No se encontró la búsqueda: 000056. Pruebe estas URL para verificar si los datos de referencia existen: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span><span class="sxs-lookup"><span data-stu-id="3af07-140">*Couldn't resolve the guid for the field: msdyn_vendorprimarycontactperson.msdyn_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span></span>
- <span data-ttu-id="3af07-141">*No se pudo resolver el guid para el campo: msdyn_invoicevendoraccountnumber.msdyn_vendoraccountnumber. No se encontró la búsqueda: V24-1. Pruebe estas URL para verificar si los datos de referencia existen: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'*</span><span class="sxs-lookup"><span data-stu-id="3af07-141">*Couldn't resolve the guid for the field: msdyn_invoicevendoraccountnumber.msdyn_vendoraccountnumber. The lookup was not found: V24-1. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'*</span></span>

<span data-ttu-id="3af07-142">Si tiene registros con valores en estos campos en la entidad del proveedor, siga los pasos en la sección a continuación para completar la sincronización inicial con éxito.</span><span class="sxs-lookup"><span data-stu-id="3af07-142">If you have records with values in these fields in the vendor entity follow the steps in the below section to complete initial sync successfully.</span></span>

1. <span data-ttu-id="3af07-143">En la aplicación Finance and Operations, elimine los campos **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** del mapeo y guarde los cambios.</span><span class="sxs-lookup"><span data-stu-id="3af07-143">In the Finance and Operations app, delete the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields from the mapping and save the changes.</span></span>

    1. <span data-ttu-id="3af07-144">Navegue a la página de mapeo de doble escritura para **Proveedores V2 (msdyn_vendors)** y seleccione la pestaña **Asignaciones de entidades**. En el filtro izquierdo, seleccione **Aplicaciones Finance and Operations.Proveedores V2**.</span><span class="sxs-lookup"><span data-stu-id="3af07-144">Navigate to the dual-write mapping page for **Vendors V2 (msdyn_vendors)**, and select the **Entity mappings** tab. In the left filter, select **Finance and Operations apps.Vendors V2**.</span></span> <span data-ttu-id="3af07-145">En el filtro derecho, seleccione **Sales.Vendor**.</span><span class="sxs-lookup"><span data-stu-id="3af07-145">In the right filter, select **Sales.Vendor**.</span></span>

    2. <span data-ttu-id="3af07-146">Busque **primarycontactperson** para encontrar el campo de origen **PrimaryContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="3af07-146">Search for **primarycontactperson** to find the source field **PrimaryContactPersonId**.</span></span>
    
    3. <span data-ttu-id="3af07-147">Haga clic en el botón **Accionees** y seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="3af07-147">Click the **Actions** button, and select **Delete**.</span></span>
    
        ![Autorreferencia o referencia circular 3](media/vend_selfref3.png)
    
    4. <span data-ttu-id="3af07-149">Repita para eliminar el campo **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="3af07-149">Repeat to delete the **InvoiceVendorAccountNumber** field.</span></span>
    
        ![Autorreferencia o referencia circular 4](media/vend-selfref4.png)
    
    5. <span data-ttu-id="3af07-151">Guardar los cambios de mapeo.</span><span class="sxs-lookup"><span data-stu-id="3af07-151">Save the mapping changes.</span></span>

2. <span data-ttu-id="3af07-152">Deshabilite el seguimiento de cambios para la entidad **Proveedores V2**.</span><span class="sxs-lookup"><span data-stu-id="3af07-152">Disable the change tracking for the **Vendors V2** entity.</span></span>

    1. <span data-ttu-id="3af07-153">Navegue a **Gestión de datos \> Entidades de datos**.</span><span class="sxs-lookup"><span data-stu-id="3af07-153">Navigate to **Data management \> Data Entities**.</span></span>
    
    2. <span data-ttu-id="3af07-154">Seleccione la entidad **Proveedores V2**.</span><span class="sxs-lookup"><span data-stu-id="3af07-154">Select the **Vendors V2** entity.</span></span>
    
    3. <span data-ttu-id="3af07-155">Haga clic en **Opciones** en la barra de menú, y luego **Seguimiento de cambios**.</span><span class="sxs-lookup"><span data-stu-id="3af07-155">Click **Options** from the menu bar, and then **Change tracking**.</span></span>
    
        ![Autorreferencia o referencia circular 5](media/selfref_options.png)
    
    4. <span data-ttu-id="3af07-157">Haga clic en **Deshabilitar seguimiento de cambios**.</span><span class="sxs-lookup"><span data-stu-id="3af07-157">Click **Disable Change Tracking**.</span></span>
    
        ![Autorreferencia o referencia circular 6](media/selfref_tracking.png)

3. <span data-ttu-id="3af07-159">Ejecute la sincronización inicial de mapeo de **Proveedores V2 (msdyn_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="3af07-159">Run the initial sync of **Vendors V2 (msdyn_vendors)** mapping.</span></span> <span data-ttu-id="3af07-160">La sincronización inicial debe ejecutarse correctamente sin ningún error.</span><span class="sxs-lookup"><span data-stu-id="3af07-160">The initial sync should run successfully without any errors.</span></span>

4. <span data-ttu-id="3af07-161">Ejecute la sincronización inicial para el mapeo **Contactos CDS V2 (contactos)**.</span><span class="sxs-lookup"><span data-stu-id="3af07-161">Run the initial sync for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="3af07-162">Debe sincronizar esta asignación si desea sincronizar el campo de contacto principal en la entidad del proveedor, ya que los registros de contactos también deben sincronizarse inicialmente.</span><span class="sxs-lookup"><span data-stu-id="3af07-162">You must sync this mapping if you want to sync primary contact field on vendors entity as the contacts records also need to be initial synced.</span></span>

5. <span data-ttu-id="3af07-163">Agregue los campos **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** de vuelta al mapeo **Proveedores V2 (msdyn_vendors)** y guarde el mapeo.</span><span class="sxs-lookup"><span data-stu-id="3af07-163">Add the fields **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** back to the **Vendors V2 (msdyn_vendors)** mapping and save the mapping.</span></span>

6. <span data-ttu-id="3af07-164">Ejecute de nuevo la sincronización inicial para el mapeo **Proveedores V2 (msdyn_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="3af07-164">Run the initial sync again for the **Vendors V2 (msdyn_vendors)** mapping.</span></span> <span data-ttu-id="3af07-165">Todos los registros se sincronizarán porque el seguimiento de cambios está deshabilitado.</span><span class="sxs-lookup"><span data-stu-id="3af07-165">All the records will be synced, because change tracking is disabled.</span></span>

7. <span data-ttu-id="3af07-166">Habilite el seguimiento de cambios para la entidad **Proveedores V2**.</span><span class="sxs-lookup"><span data-stu-id="3af07-166">Enable change tracking for the **Vendors V2** entity.</span></span>

## <a name="resolve-an-error-in-customers-v3-to-accounts-entity-mapping"></a><a id="error-customer-map"></a><span data-ttu-id="3af07-167">Resolver un error en la asignación de entidades Clientes V3 a Cuentas</span><span class="sxs-lookup"><span data-stu-id="3af07-167">Resolve an error in Customers V3 to Accounts entity mapping</span></span>

<span data-ttu-id="3af07-168">Puede encontrar los siguientes errores de sincronización inicial en el mapeo **Clientes V3** con **Cuentas** si las entidades tienen registros existentes con valores en los campos **ContactPersonID** e **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="3af07-168">You might run into the following initial sync errors on the **Customers V3** to **Accounts** mapping if the entities have existing records with values in the **ContactPersonID** and **InvoiceAccount** fields.</span></span> <span data-ttu-id="3af07-169">Esto se debe a que **InvoiceAccount** es un campo de autorreferencia y **ContactPersonID** es una referencia circular en el mapeo del proveedor.</span><span class="sxs-lookup"><span data-stu-id="3af07-169">This because **InvoiceAccount** is a self-referencing field, and **ContactPersonID** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="3af07-170">*No se pudo resolver el guid para el campo: <field> . No se encontró la búsqueda: <value> . Pruebe estas URL para verificar si los datos de referencia existen: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span><span class="sxs-lookup"><span data-stu-id="3af07-170">*Couldn't resolve the guid for the field: <field>. The lookup was not found: <value>. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>*</span></span>

- <span data-ttu-id="3af07-171">*No se pudo resolver el guid para el campo: primarycontactid.msdyn_contactpersonid. No se encontró la búsqueda: 000056. Pruebe estas URL para verificar si los datos de referencia existen: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span><span class="sxs-lookup"><span data-stu-id="3af07-171">*Couldn't resolve the guid for the field: primarycontactid.msdyn_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'*</span></span>
- <span data-ttu-id="3af07-172">*No se pudo resolver el guid para el campo: msdyn_billingaccount.accountnumber. No se encontró la búsqueda: 1206-1. Pruebe estas URL para verificar si los datos de referencia existen: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'*</span><span class="sxs-lookup"><span data-stu-id="3af07-172">*Couldn't resolve the guid for the field: msdyn_billingaccount.accountnumber. The lookup was not found: 1206-1. Try this URL(s) to check if the reference data exists: https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'*</span></span>

<span data-ttu-id="3af07-173">Si tiene registros con valores en estos campos en la entidad del cliente, siga los pasos de la sección a continuación para completar la sincronización inicial con éxito.</span><span class="sxs-lookup"><span data-stu-id="3af07-173">If you have records with values in these fields in the customer entity follow the steps in the below section to complete initial sync successfully.</span></span> <span data-ttu-id="3af07-174">Puede usar este enfoque para cualquier entidad lista para usar como Cuentas y Contactos.</span><span class="sxs-lookup"><span data-stu-id="3af07-174">You can use this approach for any out-of-the-box entities such Accounts and Contacts.</span></span>

1. <span data-ttu-id="3af07-175">En la aplicación Finance and Operations, elimine los campos **ContactPersonId** e **InvoiceAccount** del mapeo **Customers V3 (cuentas)** y guarde el mapeo.</span><span class="sxs-lookup"><span data-stu-id="3af07-175">In the Finance and Operations app, delete the fields **ContactPersonID** and **InvoiceAccount** from the **Customers V3 (accounts)** mapping and save the mapping.</span></span>

    1. <span data-ttu-id="3af07-176">Navegue a la página de mapeo de doble escritura para **Proveedores V3 (cuentass)** y seleccione la pestaña **Mapeos de entidades**. En el filtro izquierdo, seleccione **Aplicación Finance and Operations.Proveedores V3**.</span><span class="sxs-lookup"><span data-stu-id="3af07-176">Navigate to the dual-write mapping page for **Customers V3 (accounts)**, select the **Entity mappings** tab. In the left filter, select **Finance and Operations app.Customers V3**.</span></span> <span data-ttu-id="3af07-177">En el filtro derecho, seleccione **Common Data Service.Account**.</span><span class="sxs-lookup"><span data-stu-id="3af07-177">In the right filter, select **Common Data Service.Account**.</span></span>

    2. <span data-ttu-id="3af07-178">Busque **contactperson** para encontrar el campo de origen **ContactPersonID**.</span><span class="sxs-lookup"><span data-stu-id="3af07-178">Search for **contactperson** to find the source field **ContactPersonID**.</span></span>
    
    3. <span data-ttu-id="3af07-179">Haga clic en el botón **Accionees** y seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="3af07-179">Click the **Actions** button, and select **Delete**.</span></span>
    
        ![Autorreferencia o referencia circular 3](media/cust_selfref3.png)
    
    4. <span data-ttu-id="3af07-181">Repita para eliminar el campo **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="3af07-181">Repeat to delete the **InvoiceAccount** field.</span></span>
    
        ![Autorreferencia o referencia circular](media/cust_selfref4.png)
    
    5. <span data-ttu-id="3af07-183">Guardar los cambios de mapeo.</span><span class="sxs-lookup"><span data-stu-id="3af07-183">Save the mapping changes.</span></span>

2. <span data-ttu-id="3af07-184">Deshabilite el seguimiento de cambios para la entidad **Clientes V3**.</span><span class="sxs-lookup"><span data-stu-id="3af07-184">Disable the change tracking for the **Customers V3** entity.</span></span>

    1. <span data-ttu-id="3af07-185">Navegue a **Gestión de datos \> Entidades de datos**.</span><span class="sxs-lookup"><span data-stu-id="3af07-185">Navigate to **Data management \> Data Entities**.</span></span>
    
    2. <span data-ttu-id="3af07-186">Seleccione la entidad **Clientes V3**.</span><span class="sxs-lookup"><span data-stu-id="3af07-186">Select the **Customers V3** entity.</span></span>
    
    3. <span data-ttu-id="3af07-187">Haga clic en **Opciones** en la barra de menú, y luego **Seguimiento de cambios**.</span><span class="sxs-lookup"><span data-stu-id="3af07-187">Click **Options** from the menu bar, and then **Change tracking**.</span></span>
    
        ![Autorreferencia o referencia circular 5](media/selfref_options.png)
    
    4. <span data-ttu-id="3af07-189">Haga clic en **Deshabilitar seguimiento de cambios**.</span><span class="sxs-lookup"><span data-stu-id="3af07-189">Click **Disable Change Tracking**.</span></span>
    
        ![Autorreferencia o referencia circular 6](media/selfref_tracking.png)

3. <span data-ttu-id="3af07-191">Ejecute la sincronización inicial para el mapeo **Clientes V3 (Cuentas)**.</span><span class="sxs-lookup"><span data-stu-id="3af07-191">Run the initial sync for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="3af07-192">La sincronización inicial debe ejecutarse correctamente sin ningún error.</span><span class="sxs-lookup"><span data-stu-id="3af07-192">The initial sync should run successfully without any errors.</span></span>

4. <span data-ttu-id="3af07-193">Ejecute la sincronización inicial para el mapeo **Contactos CDS V2 (contactos)**.</span><span class="sxs-lookup"><span data-stu-id="3af07-193">Run the initial sync for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="3af07-194">Hay 2 mapas con el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="3af07-194">There are 2 maps with the same name.</span></span> <span data-ttu-id="3af07-195">Seleccione el que tenga la descripción **Plantilla de doble escritura para sincronización entre Contactos de proveedor FO.CDS V2 con CDS.Contacts. Requiere nuevo paquete \[Dynamics365SupplyChainExtended\].**</span><span class="sxs-lookup"><span data-stu-id="3af07-195">Select the one with the description **Dual-write template for sync between FO.CDS Vendor Contacts V2 to CDS.Contacts. Requires new package \[Dynamics365SupplyChainExtended\].**</span></span> <span data-ttu-id="3af07-196">en la pestaña **Detalles** del mapa.</span><span class="sxs-lookup"><span data-stu-id="3af07-196">on the **Details** tab of the map.</span></span>

5. <span data-ttu-id="3af07-197">Agregue los campos **InvoiceAccount** y **ContactPersonId** de vuelta al mapeo **Clientes V3 (Cuentas)** y guarde el mapeo.</span><span class="sxs-lookup"><span data-stu-id="3af07-197">Add the fields **InvoiceAccount** and **ContactPersonId** back to the **Customers V3 (Accounts)** mapping and save the mapping.</span></span> <span data-ttu-id="3af07-198">Ahora, tanto el campo **InvoiceAccount** como el campo **ContactPersonId** vuelven a ser parte del modo de sincronización en vivo.</span><span class="sxs-lookup"><span data-stu-id="3af07-198">Now, both the **InvoiceAccount** field and the **ContactPersonId** field are again part of live sync mode.</span></span> <span data-ttu-id="3af07-199">En el siguiente paso, completará la sincronización inicial para estos campos.</span><span class="sxs-lookup"><span data-stu-id="3af07-199">In the next step, you complete the initial sync for these fields.</span></span>

6. <span data-ttu-id="3af07-200">Ejecute otra vez la sincronización inicial para el mapeo **Clientes V3 (Cuentas)**.</span><span class="sxs-lookup"><span data-stu-id="3af07-200">Run the initial sync again for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="3af07-201">Debido a que el seguimiento de cambios está deshabilitado, ejecutar la sincronización sincronizará los datos para **InvoiceAccount** y **ContactPersonId** desde la aplicación Finance and Operations a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="3af07-201">Because change tracking is disabled, running the sync will sync the data for **InvoiceAccount** and **ContactPersonId** from the Finance and Operations app to Common Data Service.</span></span>

7. <span data-ttu-id="3af07-202">Para sincronizar los datos para **InvoiceAccount** y **ContactPersonId** desde Common Data Service a Finance and Operations, utilice un proyecto de integración de datos.</span><span class="sxs-lookup"><span data-stu-id="3af07-202">To sync the data for **InvoiceAccount** and **ContactPersonId** from Common Data Service to the Finance and Operations, you use a data integration project.</span></span>

    1. <span data-ttu-id="3af07-203">En Power Apps, cree un proyecto de integración de datos entre **Sales.Account** y las entidades **Aplicaciones de Finance and Operations.Clientes V3**.</span><span class="sxs-lookup"><span data-stu-id="3af07-203">In Power Apps, create a data integration project between the **Sales.Account** and **Finance and Operations apps.Customers V3** entities.</span></span> <span data-ttu-id="3af07-204">La dirección de datos debe ser de Common Data Service a la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3af07-204">The data direction must be from Common Data Service to the Finance and Operations app.</span></span>  <span data-ttu-id="3af07-205">Como **InvoiceAccount** es un nuevo atributo en doble escritura, es posible que desee omitir la sincronización inicial para este atributo.</span><span class="sxs-lookup"><span data-stu-id="3af07-205">Because **InvoiceAccount** is a new attribute in dual-write, you may want to skip initial sync for this attribute.</span></span> <span data-ttu-id="3af07-206">Para obtener más información, consulte [Integrar datos en Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="3af07-206">For more information, see [Integrate data into Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span></span>

        <span data-ttu-id="3af07-207">La siguiente imagen muestra un proyecto que actualiza **CustomerAccount** y **ContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="3af07-207">The following image shows a project that updates **CustomerAccount** and **ContactPersonId**.</span></span>

        ![Autorreferencia o referencia circular](media/cust_selfref6.png)

    2. <span data-ttu-id="3af07-209">Agregue los criterios de la empresa en el filtro del lado Common Data Service, porque solo los registros que coinciden con los criterios de filtro se actualizarán en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3af07-209">Add the company criteria in the filter on Common Data Service side, because only the records that match filter criteria will be updated in the Finance and Operations app.</span></span> <span data-ttu-id="3af07-210">Para agregar un filtro, haga clic en el icono del filtro.</span><span class="sxs-lookup"><span data-stu-id="3af07-210">To add a filter, click the filter icon.</span></span> <span data-ttu-id="3af07-211">En el cuadro de diálogo **Editar consulta** puede agregar una consulta de filtro como **_msdyn_company_value eq '\<guid\>'**.</span><span class="sxs-lookup"><span data-stu-id="3af07-211">In the **Edit query** dialog, you can add a filter query like **_msdyn_company_value eq '\<guid\>'**.</span></span> <span data-ttu-id="3af07-212">Si el icono de filtro no está presente, cree un ticket de soporte para solicitar al equipo de integración de datos que habilite la capacidad de filtro en su inquilino.</span><span class="sxs-lookup"><span data-stu-id="3af07-212">If the filter icon is not present, create a support ticket to ask the data integration team to enable the filter capability on your tenant.</span></span> <span data-ttu-id="3af07-213">Si no introduce una consulta de filtro para **_msdyn_company_value**, entonces todos los registros están sincronizados.</span><span class="sxs-lookup"><span data-stu-id="3af07-213">If you do not enter a filter query for **_msdyn_company_value**, then all the records are synced.</span></span>

        ![Autorreferencia o referencia circular](media/cust_selfref7.png)

        <span data-ttu-id="3af07-215">Esto completa la sincronización inicial de los registros.</span><span class="sxs-lookup"><span data-stu-id="3af07-215">This completes the initial sync of the records.</span></span>

8. <span data-ttu-id="3af07-216">Habilite el seguimiento de cambios para la entidad **Clientes V3** en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3af07-216">Enable change tracking for the **Customers V3** entity in the Finance and Operations app.</span></span>

