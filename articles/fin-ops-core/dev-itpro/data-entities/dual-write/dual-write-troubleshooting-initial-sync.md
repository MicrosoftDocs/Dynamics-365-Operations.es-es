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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 4d0ca1fb4b7a4964194516544686b6bb7d26e76c
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997335"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="247d0-103">Solucionar problemas durante la sincronización</span><span class="sxs-lookup"><span data-stu-id="247d0-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="247d0-104">Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="247d0-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="247d0-105">Específicamente proporciona información que puede ayudarlo a solucionar problemas durante la sincronización inicial.</span><span class="sxs-lookup"><span data-stu-id="247d0-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="247d0-106">Algunos de los problemas que aborda este tema pueden requerir la característica de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="247d0-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="247d0-107">La sección para cada problema explica si se requiere una característica o credenciales específicas.</span><span class="sxs-lookup"><span data-stu-id="247d0-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="247d0-108">Verificar los errores de sincronización inicial en una aplicación Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="247d0-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="247d0-109">Después de habilitar las plantillas de asignación, el estado de los mapas debe ser **Ejecutando**.</span><span class="sxs-lookup"><span data-stu-id="247d0-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="247d0-110">Si el estado es **No ejecutando** , se produjeron errores durante la sincronización inicial.</span><span class="sxs-lookup"><span data-stu-id="247d0-110">If the status is **Not running** , errors occurred during initial synchronization.</span></span> <span data-ttu-id="247d0-111">Para ver los errores, seleccione la pestaña **Detalles de sincronización inicial** en la página **Escritura doble**.</span><span class="sxs-lookup"><span data-stu-id="247d0-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Error en la pestaña Detalles de sincronización inicial](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="247d0-113">No puede completar la sincronización inicial: 400 Solicitud incorrecta</span><span class="sxs-lookup"><span data-stu-id="247d0-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="247d0-114">**Rol requerido para arreglar el error:** Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="247d0-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="247d0-115">Es posible que reciba el siguiente mensaje de error cuando intente ejecutar la asignación y la sincronización inicial:</span><span class="sxs-lookup"><span data-stu-id="247d0-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="247d0-116">*(\[Solicitud incorrecta\]: el servidor remoto devolvió un error: (400) Solicitud incorrecta.), se produjo un error en la exportación de AX*</span><span class="sxs-lookup"><span data-stu-id="247d0-116">*(\[Bad Request\], The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="247d0-117">A continuación se muestra un ejemplo del mensaje de error completo.</span><span class="sxs-lookup"><span data-stu-id="247d0-117">Here is an example of the full error message.</span></span>

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

<span data-ttu-id="247d0-118">Si este error ocurre de manera constante y no puede completar la sincronización inicial, siga estos pasos para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="247d0-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="247d0-119">Inicie sesión en la máquina virtual (VM) para la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="247d0-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="247d0-120">Abra Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="247d0-120">Open Microsoft Management Console.</span></span>
3. <span data-ttu-id="247d0-121">En el panel **Servicios** , asegúrese de que el servicio de exportación de marco de Microsoft Dynamics 365 Data se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="247d0-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="247d0-122">Reinícielo si se ha detenido, porque la sincronización inicial lo requiere.</span><span class="sxs-lookup"><span data-stu-id="247d0-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="247d0-123">Error de sincronización inicial: 403 Prohibido</span><span class="sxs-lookup"><span data-stu-id="247d0-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="247d0-124">Es posible que reciba el siguiente mensaje de error durante la sincronización inicial:</span><span class="sxs-lookup"><span data-stu-id="247d0-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="247d0-125">*(\[Prohibido\], el servidor remoto devolvión un error: (403) Prohibido.), exportación AX encontró un error*</span><span class="sxs-lookup"><span data-stu-id="247d0-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="247d0-126">Para arreglar el problema, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="247d0-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="247d0-127">Iniciar sesión en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="247d0-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="247d0-128">En la págona **aplicaciones Azure Active Directory** , elimine el cliente **DtAppID** , y luego agréguelo nuevamente.</span><span class="sxs-lookup"><span data-stu-id="247d0-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Cliente DtAppID en la lista de aplicaciones de Azure AD](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a><span data-ttu-id="247d0-130">Errores de autorreferencia o de referencia circular durante la sincronización inicial</span><span class="sxs-lookup"><span data-stu-id="247d0-130">Self-reference or circular reference failures during initial synchronization</span></span>

<span data-ttu-id="247d0-131">Es posible que reciba mensajes de error si alguna de sus asignaciones tiene autorreferencias o referencias circulares.</span><span class="sxs-lookup"><span data-stu-id="247d0-131">You might receive an error messages if any of your mappings have self-references or circular references.</span></span> <span data-ttu-id="247d0-132">Los errores se dividen en estas categorías:</span><span class="sxs-lookup"><span data-stu-id="247d0-132">The errors fall into these categories:</span></span>

- [<span data-ttu-id="247d0-133">Errores en la asignación de entidades Proveedores V2–to–msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="247d0-133">Errors in the Vendors V2–to–msdyn_vendors entity mapping</span></span>](#error-vendor-map)
- [<span data-ttu-id="247d0-134">Errores en la asignación de entidades Clientes V3–to–Accounts</span><span class="sxs-lookup"><span data-stu-id="247d0-134">Errors in the Customers V3–to–Accounts entity mapping</span></span>](#error-customer-map)

## <a name="resolve-errors-in-the-vendors-v2tomsdyn_vendors-entity-mapping"></a><a id="error-vendor-map"></a><span data-ttu-id="247d0-135">Resolver errores en la asignación de entidades Proveedores V2–to–msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="247d0-135">Resolve errors in the Vendors V2–to–msdyn_vendors entity mapping</span></span>

<span data-ttu-id="247d0-136">Puede encontrar los siguientes errores de sincronización inicial en la asignación de **Proveedores V2** a **msdyn\_vendors** si las entidades tienen registros existentes con valores en los campos **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="247d0-136">You might encounter initial synchronization errors for the mapping of **Vendors V2** to **msdyn\_vendors** if the entities have existing records where there are values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields.</span></span> <span data-ttu-id="247d0-137">Estos errores se producen porque **InvoiceVendorAccountNumber** es un campo de autorreferencia y **PrimaryContactPersonId** es una referencia circular en la asignación del proveedor.</span><span class="sxs-lookup"><span data-stu-id="247d0-137">These errors occur because **InvoiceVendorAccountNumber** is a self-referencing field, and **PrimaryContactPersonId** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="247d0-138">Los mensajes de error que reciba tendrán el siguiente formulario.</span><span class="sxs-lookup"><span data-stu-id="247d0-138">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="247d0-139">*No se pudo resolver el guid para el campo: \<field\>. No se encontró la búsqueda: \<value\>. Pruebe estas URL para verificar si los datos de referencia existen: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="247d0-139">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="247d0-140">A continuación, encontrará algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="247d0-140">Here are some examples:</span></span>

- <span data-ttu-id="247d0-141">*No se pudo resolver el guid para el campo: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. No se encontró la busqueda: 000056. Pruebe estas URL para verificar si los datos de referencia existen: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="247d0-141">*Couldn't resolve the guid for the field: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="247d0-142">*No se pudo resolver el guid para el campo: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. No se encontró la búsqueda V24-1 . Pruebe estas URL para verificar si los datos de referencia existen: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span><span class="sxs-lookup"><span data-stu-id="247d0-142">*Couldn't resolve the guid for the field: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. The lookup was not found: V24-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span></span>

<span data-ttu-id="247d0-143">Si tiene registros con valores en estos campos en la entidad del proveedor, en los campos **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** siga estos pasos para completar la sincronización inicial.</span><span class="sxs-lookup"><span data-stu-id="247d0-143">If any records in the vendor entity have values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields, follow these steps to complete the initial synchronization.</span></span>

1. <span data-ttu-id="247d0-144">En la aplicación Finance and Operations, elimine los campos **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** de la asignación y guarde la asignación.</span><span class="sxs-lookup"><span data-stu-id="247d0-144">In the Finance and Operations app, delete the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields from the mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="247d0-145">En la página de asignación de doble escritura para **Proveedores V2 (msdyn\_vendors)** , en la pestaña **Asignaciones de entidades** , en el filtro izquierdo, seleccione **Finance and Operationsapps.Vendors V2**.</span><span class="sxs-lookup"><span data-stu-id="247d0-145">On the dual-write mapping page for **Vendors V2 (msdyn\_vendors)** , on the **Entity mappings** tab, in the left filter, select **Finance and Operations apps.Vendors V2**.</span></span> <span data-ttu-id="247d0-146">En el filtro derecho, seleccione **Sales.Vendor**.</span><span class="sxs-lookup"><span data-stu-id="247d0-146">In the right filter, select **Sales.Vendor**.</span></span>
    2. <span data-ttu-id="247d0-147">Busque **primarycontactperson** para encontrar el campo de origen **PrimaryContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="247d0-147">Search for **primarycontactperson** to find the **PrimaryContactPersonId** source field.</span></span>
    3. <span data-ttu-id="247d0-148">Seleccione **Acciones** y luego seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="247d0-148">Select **Actions** , and then select **Delete**.</span></span>

        ![Eliminar el campo PrimaryContactPersonId](media/vend_selfref3.png)

    4. <span data-ttu-id="247d0-150">Repita estos pasos para eliminar el campo **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="247d0-150">Repeat these steps to delete the **InvoiceVendorAccountNumber** field.</span></span>

        ![Eliminar el campo InvoiceVendorAccountNumber](media/vend-selfref4.png)

    5. <span data-ttu-id="247d0-152">Guardar los cambios en la asignación.</span><span class="sxs-lookup"><span data-stu-id="247d0-152">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="247d0-153">Active el seguimiento de cambios para la entidad **Proveedores V2**.</span><span class="sxs-lookup"><span data-stu-id="247d0-153">Turn off change tracking for the **Vendors V2** entity.</span></span>

    1. <span data-ttu-id="247d0-154">En espacio de trabajo **Administración de datos** , seleccione la ventana **Entidades de datos**.</span><span class="sxs-lookup"><span data-stu-id="247d0-154">In the **Data management** workspace, select the **Data entities** tile.</span></span>
    2. <span data-ttu-id="247d0-155">Seleccione la entidad **Proveedores V2**.</span><span class="sxs-lookup"><span data-stu-id="247d0-155">Select the **Vendors V2** entity.</span></span>
    3. <span data-ttu-id="247d0-156">En el panel de acciones, seleccione **Opciones** y después seleccione **Change Tracking**.</span><span class="sxs-lookup"><span data-stu-id="247d0-156">On the Action Pane, select **Options** , and then select **Change tracking**.</span></span>

        ![Seleccionar la opción Change Tracking](media/selfref_options.png)

    4. <span data-ttu-id="247d0-158">Seleccione **Deshabilitar Change Tracking**.</span><span class="sxs-lookup"><span data-stu-id="247d0-158">Select **Disable Change Tracking**.</span></span>

        ![Seleccionar Deshabilitar Change Tracking](media/selfref_tracking.png)

3. <span data-ttu-id="247d0-160">Ejecutar la sincronización inicial para la asignación de **Proveedores V2 (msdyn\_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="247d0-160">Run initial synchronization for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="247d0-161">La sincronización inicial debe ejecutarse correctamente sin ningún error.</span><span class="sxs-lookup"><span data-stu-id="247d0-161">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="247d0-162">Ejecute la sincronización inicial para la asignación **Contactos CDS V2 (contactos)**.</span><span class="sxs-lookup"><span data-stu-id="247d0-162">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="247d0-163">Debe sincronizar esta asignación si desea sincronizar el campo de contacto principal en la entidad proveedores, ya que la sincronización inicial también debe efectuarse para los registros de contactos.</span><span class="sxs-lookup"><span data-stu-id="247d0-163">You must sync this mapping if you want to sync the primary contact field on the vendors entity, because initial synchronization must also be done for the contact records.</span></span>
5. <span data-ttu-id="247d0-164">Agregue los campos **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** otra vez a la asignación **Proveedores V2 (msdyn\_vendors)** y guarde la asignación.</span><span class="sxs-lookup"><span data-stu-id="247d0-164">Add the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** fields back to the **Vendors V2 (msdyn\_vendors)** mapping, and then save the mapping.</span></span>
6. <span data-ttu-id="247d0-165">Vuelva a ejecutar la sincronización inicial para la asignación de **Proveedores V2 (msdyn\_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="247d0-165">Run initial synchronization again for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="247d0-166">Dado que Change Tracking está desactivado, todos los registros se sincronizarán.</span><span class="sxs-lookup"><span data-stu-id="247d0-166">Because change tracking is turned off, all the records will be synced.</span></span>
7. <span data-ttu-id="247d0-167">Vuelva a activar Change Tracking para la entidad **Proveedores V2**.</span><span class="sxs-lookup"><span data-stu-id="247d0-167">Turn change tracking back on for the **Vendors V2** entity.</span></span>

## <a name="resolve-errors-in-the-customers-v3toaccounts-entity-mapping"></a><a id="error-customer-map"></a><span data-ttu-id="247d0-168">Resolver errores en la asignación de entidades Clientes V3–to–Accounts</span><span class="sxs-lookup"><span data-stu-id="247d0-168">Resolve errors in the Customers V3–to–Accounts entity mapping</span></span>

<span data-ttu-id="247d0-169">Puede encontrar los siguientes errores de sincronización inicial en la asignación de **Clientes V3** a **Cuentas** si las entidades tienen registros existentes con valores en los campos **ContactPersonID** e **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="247d0-169">You might encounter initial synchronization errors for the mapping of **Customers V3** to **Accounts** if the entities have existing records where there are values in the **ContactPersonID** and **InvoiceAccount** fields.</span></span> <span data-ttu-id="247d0-170">Estos errores se producen porque **InvoiceAccount** es un campo de autorreferencia y **ContactPersonID** es una referencia circular en el mapeo del proveedor.</span><span class="sxs-lookup"><span data-stu-id="247d0-170">These errors occur because **InvoiceAccount** is a self-referencing field, and **ContactPersonID** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="247d0-171">Los mensajes de error que reciba tendrán el siguiente formulario.</span><span class="sxs-lookup"><span data-stu-id="247d0-171">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="247d0-172">*No se pudo resolver el guid para el campo: \<field\>. No se encontró la búsqueda: \<value\>. Pruebe estas URL para verificar si los datos de referencia existen: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="247d0-172">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="247d0-173">A continuación, encontrará algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="247d0-173">Here are some examples:</span></span>

- <span data-ttu-id="247d0-174">*No se pudo resolver el guid para el campo: primarycontactid.msdyn\_contactpersonid. No se encontró la busqueda: 000056. Pruebe estas URL para verificar si los datos de referencia existen: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="247d0-174">*Couldn't resolve the guid for the field: primarycontactid.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="247d0-175">*No se pudo resolver el guid para el campo: msdyn\_billingaccount.accountnumber. No se encontró la búsqueda: 1206-1 . Pruebe estas URL para verificar si los datos de referencia existen: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span><span class="sxs-lookup"><span data-stu-id="247d0-175">*Couldn't resolve the guid for the field: msdyn\_billingaccount.accountnumber. The lookup was not found: 1206-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span></span>

<span data-ttu-id="247d0-176">Si tiene registros en la entidad cliente con valores en los campos **ContactPersonID** e **InvoiceAccount** siga estos pasos para completar la sincronización inicial.</span><span class="sxs-lookup"><span data-stu-id="247d0-176">If any records in the customer entity have values in the **ContactPersonID** and **InvoiceAccount** fields, follow these steps to complete the initial synchronization.</span></span> <span data-ttu-id="247d0-177">Puede usar este enfoque para cualquier entidad lista para usar como **Cuentas** y **Contactos**.</span><span class="sxs-lookup"><span data-stu-id="247d0-177">You can use this approach for any out-of-box entities, such **Accounts** and **Contacts**.</span></span>

1. <span data-ttu-id="247d0-178">En la aplicación Finance and Operations, elimine los campos **ContactPersonId** e **InvoiceAccount** de la asignación **Clientes V3 (cuentas)** y guarde la asignación.</span><span class="sxs-lookup"><span data-stu-id="247d0-178">In the Finance and Operations app, delete the **ContactPersonID** and **InvoiceAccount** fields from the **Customers V3 (accounts)** mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="247d0-179">En la página de mapeo de doble escritura para **Clientes V3 (cuentas)** , en la pestaña **Asignaciones de entidades**. En el filtro izquierdo, seleccione **Finance and Operations app.Customers V3**.</span><span class="sxs-lookup"><span data-stu-id="247d0-179">On the dual-write mapping page for **Customers V3 (accounts)** , on the **Entity mappings** tab, in the left filter, select **Finance and Operations app.Customers V3**.</span></span> <span data-ttu-id="247d0-180">En el filtro derecho, seleccione **Common Data Service.Account**.</span><span class="sxs-lookup"><span data-stu-id="247d0-180">In the right filter, select **Common Data Service.Account**.</span></span>
    2. <span data-ttu-id="247d0-181">Busque **contactperson** para encontrar el campo de origen **ContactPersonID**.</span><span class="sxs-lookup"><span data-stu-id="247d0-181">Search for **contactperson** to find the **ContactPersonID** source field.</span></span>
    3. <span data-ttu-id="247d0-182">Seleccione **Acciones** y luego seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="247d0-182">Select **Actions** , and then select **Delete**.</span></span>

        ![Eliminar el campo ContactPersonID](media/cust_selfref3.png)

    4. <span data-ttu-id="247d0-184">Repita estos pasos para eliminar el campo **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="247d0-184">Repeat these steps to delete the **InvoiceAccount** field.</span></span>

        ![Eliminar el campo InvoiceAccount](media/cust_selfref4.png)

    5. <span data-ttu-id="247d0-186">Guardar los cambios en la asignación.</span><span class="sxs-lookup"><span data-stu-id="247d0-186">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="247d0-187">Active el seguimiento de cambios para la entidad **Clientes V3**.</span><span class="sxs-lookup"><span data-stu-id="247d0-187">Turn off change tracking for the **Customers V3** entity.</span></span>

    1. <span data-ttu-id="247d0-188">En espacio de trabajo **Administración de datos** , seleccione la ventana **Entidades de datos**.</span><span class="sxs-lookup"><span data-stu-id="247d0-188">In the **Data management** workspace, select the **Data entities** tile.</span></span>
    2. <span data-ttu-id="247d0-189">Seleccione la entidad **Clientes V3**.</span><span class="sxs-lookup"><span data-stu-id="247d0-189">Select the **Customers V3** entity.</span></span>
    3. <span data-ttu-id="247d0-190">En el panel de acciones, seleccione **Opciones** y después seleccione **Change Tracking**.</span><span class="sxs-lookup"><span data-stu-id="247d0-190">On the Action Pane, select **Options** , and then select **Change tracking**.</span></span>

        ![Seleccionar la opción Change Tracking](media/selfref_options.png)

    4. <span data-ttu-id="247d0-192">Seleccione **Deshabilitar Change Tracking**.</span><span class="sxs-lookup"><span data-stu-id="247d0-192">Select **Disable Change Tracking**.</span></span>

        ![Seleccionar Deshabilitar Change Tracking](media/selfref_tracking.png)

3. <span data-ttu-id="247d0-194">Ejecute otra vez la sincronización inicial para la asignación **Clientes V3 (Cuentas)**.</span><span class="sxs-lookup"><span data-stu-id="247d0-194">Run initial synchronization for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="247d0-195">La sincronización inicial debe ejecutarse correctamente sin ningún error.</span><span class="sxs-lookup"><span data-stu-id="247d0-195">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="247d0-196">Ejecute la sincronización inicial para la asignación **Contactos CDS V2 (contactos)**.</span><span class="sxs-lookup"><span data-stu-id="247d0-196">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span>

    > [!NOTE]
    > <span data-ttu-id="247d0-197">Hay dos asignaciones que tienen el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="247d0-197">There are two maps that have the same name.</span></span> <span data-ttu-id="247d0-198">Asegúrese de seleccionar la asignación tenga la descripción siguiente en la pestaña **Detalles** : **Plantilla de doble escritura para sincronización entre Contactos de proveedor FO.CDS V2 con CDS.Contacts. Requiere nuevo paquete \[Dynamics365SupplyChainExtended\].**</span><span class="sxs-lookup"><span data-stu-id="247d0-198">Be sure to select the map that has the following description on the **Details** tab: **Dual-write template for sync between FO.CDS Vendor Contacts V2 to CDS.Contacts. Requires new package \[Dynamics365SupplyChainExtended\].**</span></span>

5. <span data-ttu-id="247d0-199">Vuelva a agregar los campos **InvoiceAccount** y **ContactPersonId** a la asignación **Clientes V3 (Cuentas)** y guarde la asignación.</span><span class="sxs-lookup"><span data-stu-id="247d0-199">Add the **InvoiceAccount** and **ContactPersonId** fields back to the **Customers V3 (Accounts)** mapping, and then save the mapping.</span></span> <span data-ttu-id="247d0-200">Tanto el campo **InvoiceAccount** como el campo **ContactPersonId** vuelven a ser parte del modo de sincronización en vivo.</span><span class="sxs-lookup"><span data-stu-id="247d0-200">Both the **InvoiceAccount** field and the **ContactPersonId** field are now part of live synchronization mode again.</span></span> <span data-ttu-id="247d0-201">En el siguiente paso, completará la sincronización inicial para estos campos.</span><span class="sxs-lookup"><span data-stu-id="247d0-201">In the next step, you will do the initial synchronization for these fields.</span></span>
6. <span data-ttu-id="247d0-202">Ejecute otra vez la sincronización inicial para la asignación **Clientes V3 (Cuentas)**.</span><span class="sxs-lookup"><span data-stu-id="247d0-202">Run initial synchronization again for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="247d0-203">Debido a que el seguimiento de cambios está deshabilitado, los datos para **InvoiceAccount** y **ContactPersonId** se sincronizarán desde la aplicación Finance and Operations a Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="247d0-203">Because change tracking is turned off, the data for **InvoiceAccount** and **ContactPersonId** will be synced from the Finance and Operations app to Common Data Service.</span></span>
7. <span data-ttu-id="247d0-204">Para sincronizar los datos para **InvoiceAccount** y **ContactPersonId** desde Common Data Service a la aplicación Finance and Operations, debe utilizar un proyecto de integración de datos.</span><span class="sxs-lookup"><span data-stu-id="247d0-204">To sync the data for **InvoiceAccount** and **ContactPersonId** from Common Data Service to the Finance and Operations app, you must use a data integration project.</span></span>

    1. <span data-ttu-id="247d0-205">En Power Apps, cree un proyecto de integración de datos entre **Sales.Account** y las entidades **Finance and Operations.Customers V3**.</span><span class="sxs-lookup"><span data-stu-id="247d0-205">In Power Apps, create a data integration project between the **Sales.Account** and **Finance and Operations apps.Customers V3** entities.</span></span> <span data-ttu-id="247d0-206">La dirección de datos debe ser de Common Data Service a la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="247d0-206">The data direction must be from Common Data Service to the Finance and Operations app.</span></span> <span data-ttu-id="247d0-207">Como **InvoiceAccount** es un nuevo atributo en doble escritura, es posible que desee omitir la sincronización inicial para este atributo.</span><span class="sxs-lookup"><span data-stu-id="247d0-207">Because **InvoiceAccount** is a new attribute in dual-write, you might want to skip initial synchronization for it.</span></span> <span data-ttu-id="247d0-208">Para obtener más información, consulte [Integrar datos en Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="247d0-208">For more information, see [Integrate data into Common Data Service](https://docs.microsoft.com/power-platform/admin/data-integrator).</span></span>

        <span data-ttu-id="247d0-209">La siguiente ilustración muestra un proyecto que actualiza **CustomerAccount** y **ContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="247d0-209">The following illustration shows a project that updates **CustomerAccount** and **ContactPersonId**.</span></span>

        ![Proyecto de integración de datos para actualizar CustomerAccount y ContactPersonId](media/cust_selfref6.png)

    2. <span data-ttu-id="247d0-211">Agregue los criterios de la empresa en el filtro del lado Common Data Service, de forma que solo los registros que coinciden con los criterios de filtro se actualizarán en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="247d0-211">Add the company criteria in the filter on the Common Data Service side, so that only records that match the filter criteria will be updated in the Finance and Operations app.</span></span> <span data-ttu-id="247d0-212">Para agregar un filtro, seleccione el botón del filtro.</span><span class="sxs-lookup"><span data-stu-id="247d0-212">To add a filter, select the filter button.</span></span> <span data-ttu-id="247d0-213">Posteriormente, en el cuadro de diálogo **Editar consulta** puede agregar una consulta de filtro como **\_msdyn\_company\_value eq '\<guid\>'**.</span><span class="sxs-lookup"><span data-stu-id="247d0-213">Then, in the **Edit query** dialog box, you can add a filter query such as **\_msdyn\_company\_value eq '\<guid\>'**.</span></span> 

        > <span data-ttu-id="247d0-214">[NOTA] Si el botón del filtro no está presente, cree un ticket de soporte para solicitar al equipo de integración de datos que habilite la capacidad de filtro en su inquilino.</span><span class="sxs-lookup"><span data-stu-id="247d0-214">[NOTE] If the filter button isn't present, create a support ticket to ask the data integration team to enable the filter capability on your tenant.</span></span>

        <span data-ttu-id="247d0-215">Si no especifica una consulta de filtro para **\_msdyn\_company\_value** , entonces todos los registros se sincronizarán.</span><span class="sxs-lookup"><span data-stu-id="247d0-215">If you don't enter a filter query for **\_msdyn\_company\_value** , all the records will be synced.</span></span>

        ![Agregar una consulta de filtro](media/cust_selfref7.png)

    <span data-ttu-id="247d0-217">La sincronización inicial de los registros ahora se ha completado.</span><span class="sxs-lookup"><span data-stu-id="247d0-217">The initial synchronization of the records is now completed.</span></span>

8. <span data-ttu-id="247d0-218">En la aplicación Finance and Operations, vuelva a activar Change Tracking en la entidad **Clientes V3**.</span><span class="sxs-lookup"><span data-stu-id="247d0-218">In the Finance and Operations app, turn change tracking back on for the **Customers V3** entity.</span></span>
