---
title: Solucionar problemas durante la sincronización
description: Este tema proporciona información para la solución de problemas que puede ayudarlo a solucionar problemas durante la sincronización inicial.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: c716707140c85b06ad2f084c10c4b2d0ecfea82e
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754023"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="106c9-103">Solucionar problemas durante la sincronización</span><span class="sxs-lookup"><span data-stu-id="106c9-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="106c9-104">Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Dataverse.</span><span class="sxs-lookup"><span data-stu-id="106c9-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="106c9-105">Específicamente proporciona información que puede ayudarlo a solucionar problemas durante la sincronización inicial.</span><span class="sxs-lookup"><span data-stu-id="106c9-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="106c9-106">Algunos de los problemas que aborda este tema pueden requerir la característica de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="106c9-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="106c9-107">La sección para cada problema explica si se requiere una característica o credenciales específicas.</span><span class="sxs-lookup"><span data-stu-id="106c9-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="106c9-108">Verificar los errores de sincronización inicial en una aplicación Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="106c9-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="106c9-109">Después de habilitar las plantillas de asignación, el estado de los mapas debe ser **Ejecutando**.</span><span class="sxs-lookup"><span data-stu-id="106c9-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="106c9-110">Si el estado es **No ejecutando**, se produjeron errores durante la sincronización inicial.</span><span class="sxs-lookup"><span data-stu-id="106c9-110">If the status is **Not running**, errors occurred during initial synchronization.</span></span> <span data-ttu-id="106c9-111">Para ver los errores, seleccione la pestaña **Detalles de sincronización inicial** en la página **Escritura doble**.</span><span class="sxs-lookup"><span data-stu-id="106c9-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Error en la pestaña Detalles de sincronización inicial](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="106c9-113">No puede completar la sincronización inicial: 400 Solicitud incorrecta</span><span class="sxs-lookup"><span data-stu-id="106c9-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="106c9-114">**Rol requerido para arreglar el error:** Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="106c9-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="106c9-115">Es posible que reciba el siguiente mensaje de error cuando intente ejecutar la asignación y la sincronización inicial:</span><span class="sxs-lookup"><span data-stu-id="106c9-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="106c9-116">*(\[Solicitud incorrecta\]: el servidor remoto devolvió un error: (400) Solicitud incorrecta.), se produjo un error en la exportación de AX*</span><span class="sxs-lookup"><span data-stu-id="106c9-116">*(\[Bad Request\], The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="106c9-117">A continuación se muestra un ejemplo del mensaje de error completo.</span><span class="sxs-lookup"><span data-stu-id="106c9-117">Here is an example of the full error message.</span></span>

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

<span data-ttu-id="106c9-118">Si este error ocurre de manera constante y no puede completar la sincronización inicial, siga estos pasos para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="106c9-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="106c9-119">Inicie sesión en la máquina virtual (VM) para la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="106c9-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="106c9-120">Abra Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="106c9-120">Open Microsoft Management Console.</span></span>
3. <span data-ttu-id="106c9-121">En el panel **Servicios**, asegúrese de que el servicio de exportación de marco de Microsoft Dynamics 365 Data se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="106c9-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="106c9-122">Reinícielo si se ha detenido, porque la sincronización inicial lo requiere.</span><span class="sxs-lookup"><span data-stu-id="106c9-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="106c9-123">Error de sincronización inicial: 403 Prohibido</span><span class="sxs-lookup"><span data-stu-id="106c9-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="106c9-124">Es posible que reciba el siguiente mensaje de error durante la sincronización inicial:</span><span class="sxs-lookup"><span data-stu-id="106c9-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="106c9-125">*(\[Prohibido\], el servidor remoto devolvión un error: (403) Prohibido.), exportación AX encontró un error*</span><span class="sxs-lookup"><span data-stu-id="106c9-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="106c9-126">Para arreglar el problema, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="106c9-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="106c9-127">Iniciar sesión en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="106c9-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="106c9-128">En la págona **aplicaciones Azure Active Directory**, elimine el cliente **DtAppID**, y luego agréguelo nuevamente.</span><span class="sxs-lookup"><span data-stu-id="106c9-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Cliente DtAppID en la lista de aplicaciones de Azure AD](media/aad_applications.png)

## <a name="self-reference-or-circular-reference-failures-during-initial-synchronization"></a><span data-ttu-id="106c9-130">Errores de autorreferencia o de referencia circular durante la sincronización inicial</span><span class="sxs-lookup"><span data-stu-id="106c9-130">Self-reference or circular reference failures during initial synchronization</span></span>

<span data-ttu-id="106c9-131">Es posible que reciba mensajes de error si alguna de sus asignaciones tiene autorreferencias o referencias circulares.</span><span class="sxs-lookup"><span data-stu-id="106c9-131">You might receive an error messages if any of your mappings have self-references or circular references.</span></span> <span data-ttu-id="106c9-132">Los errores se dividen en estas categorías:</span><span class="sxs-lookup"><span data-stu-id="106c9-132">The errors fall into these categories:</span></span>

- [<span data-ttu-id="106c9-133">Errores en la asignación de tabla Proveedores V2–to–msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="106c9-133">Errors in the Vendors V2–to–msdyn_vendors table mapping</span></span>](#error-vendor-map)
- [<span data-ttu-id="106c9-134">Errores en la asignación de tabla Clientes V3–to–Accounts</span><span class="sxs-lookup"><span data-stu-id="106c9-134">Errors in the Customers V3–to–Accounts table mapping</span></span>](#error-customer-map)

## <a name="resolve-errors-in-the-vendors-v2tomsdyn_vendors-table-mapping"></a><a id="error-vendor-map"></a><span data-ttu-id="106c9-135">Resolver errores en la asignación de tabla Proveedores V2–to–msdyn_vendors</span><span class="sxs-lookup"><span data-stu-id="106c9-135">Resolve errors in the Vendors V2–to–msdyn_vendors table mapping</span></span>

<span data-ttu-id="106c9-136">Puede encontrar los siguientes errores de sincronización inicial en la asignación de **Proveedores V2** a **msdyn\_vendors** si las tablas tienen filas existentes con valores en las columnas **PrimaryContactPersonId** e **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="106c9-136">You might encounter initial synchronization errors for the mapping of **Vendors V2** to **msdyn\_vendors** if the tables have existing rows where there are values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns.</span></span> <span data-ttu-id="106c9-137">Estos errores se producen porque **InvoiceVendorAccountNumber** es una columna de autorreferencia y **PrimaryContactPersonId** es una referencia circular en la asignación del proveedor.</span><span class="sxs-lookup"><span data-stu-id="106c9-137">These errors occur because **InvoiceVendorAccountNumber** is a self-referencing column, and **PrimaryContactPersonId** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="106c9-138">Los mensajes de error que reciba tendrán el siguiente formulario.</span><span class="sxs-lookup"><span data-stu-id="106c9-138">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="106c9-139">*No se pudo resolver el guid para el campo: \<field\>. No se encontró la búsqueda: \<value\>. Pruebe estas URL para verificar si los datos de referencia existen: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="106c9-139">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="106c9-140">A continuación, encontrará algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="106c9-140">Here are some examples:</span></span>

- <span data-ttu-id="106c9-141">*No se pudo resolver el guid para el campo: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. No se encontró la busqueda: 000056. Pruebe estas URL para verificar si los datos de referencia existen: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="106c9-141">*Couldn't resolve the guid for the field: msdyn\_vendorprimarycontactperson.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="106c9-142">*No se pudo resolver el guid para el campo: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. No se encontró la búsqueda V24-1 . Pruebe estas URL para verificar si los datos de referencia existen: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span><span class="sxs-lookup"><span data-stu-id="106c9-142">*Couldn't resolve the guid for the field: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. The lookup was not found: V24-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/msdn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber eq 'V24-1'`*</span></span>

<span data-ttu-id="106c9-143">Si tiene filas con valores en estos campos en la tabla del proveedor, en las columnas **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** siga estos pasos para completar la sincronización inicial.</span><span class="sxs-lookup"><span data-stu-id="106c9-143">If any rows in the vendor table have values in the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns, follow these steps to complete the initial synchronization.</span></span>

1. <span data-ttu-id="106c9-144">En la aplicación Finance and Operations, elimine las columnas **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** de la asignación y guarde la asignación.</span><span class="sxs-lookup"><span data-stu-id="106c9-144">In the Finance and Operations app, delete the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns from the mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="106c9-145">En la página de asignación de doble escritura para **Proveedores V2 (msdyn\_vendors)**, en la pestaña **Asignaciones de tablas**, en el filtro izquierdo, seleccione **Finance and Operations apps.Vendors V2**.</span><span class="sxs-lookup"><span data-stu-id="106c9-145">On the dual-write mapping page for **Vendors V2 (msdyn\_vendors)**, on the **Table mappings** tab, in the left filter, select **Finance and Operations apps.Vendors V2**.</span></span> <span data-ttu-id="106c9-146">En el filtro derecho, seleccione **Sales.Vendor**.</span><span class="sxs-lookup"><span data-stu-id="106c9-146">In the right filter, select **Sales.Vendor**.</span></span>
    2. <span data-ttu-id="106c9-147">Busque **primarycontactperson** para encontrar la columna de origen **PrimaryContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="106c9-147">Search for **primarycontactperson** to find the **PrimaryContactPersonId** source column.</span></span>
    3. <span data-ttu-id="106c9-148">Seleccione **Acciones** y luego seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="106c9-148">Select **Actions**, and then select **Delete**.</span></span>

        ![Eliminar la columna PrimaryContactPersonId](media/vend_selfref3.png)

    4. <span data-ttu-id="106c9-150">Repita estos pasos para eliminar la columna **InvoiceVendorAccountNumber**.</span><span class="sxs-lookup"><span data-stu-id="106c9-150">Repeat these steps to delete the **InvoiceVendorAccountNumber** column.</span></span>

        ![Eliminar la columna InvoiceVendorAccountNumber](media/vend-selfref4.png)

    5. <span data-ttu-id="106c9-152">Guardar los cambios en la asignación.</span><span class="sxs-lookup"><span data-stu-id="106c9-152">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="106c9-153">Active el seguimiento de cambios para la tabla **Proveedores V2**.</span><span class="sxs-lookup"><span data-stu-id="106c9-153">Turn off change tracking for the **Vendors V2** table.</span></span>

    1. <span data-ttu-id="106c9-154">En espacio de trabajo **Administración de datos**, seleccione la ventana **Tablas de datos**.</span><span class="sxs-lookup"><span data-stu-id="106c9-154">In the **Data management** workspace, select the **Data tables** tile.</span></span>
    2. <span data-ttu-id="106c9-155">Seleccione la tabla **Proveedores V2**.</span><span class="sxs-lookup"><span data-stu-id="106c9-155">Select the **Vendors V2** table.</span></span>
    3. <span data-ttu-id="106c9-156">En el panel de acciones, seleccione **Opciones** y después seleccione **Change Tracking**.</span><span class="sxs-lookup"><span data-stu-id="106c9-156">On the Action Pane, select **Options**, and then select **Change tracking**.</span></span>

        ![Seleccionar la opción Change Tracking](media/selfref_options.png)

    4. <span data-ttu-id="106c9-158">Seleccione **Deshabilitar Change Tracking**.</span><span class="sxs-lookup"><span data-stu-id="106c9-158">Select **Disable Change Tracking**.</span></span>

        ![Seleccionar Deshabilitar Change Tracking](media/selfref_tracking.png)

3. <span data-ttu-id="106c9-160">Ejecutar la sincronización inicial para la asignación de **Proveedores V2 (msdyn\_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="106c9-160">Run initial synchronization for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="106c9-161">La sincronización inicial debe ejecutarse correctamente sin ningún error.</span><span class="sxs-lookup"><span data-stu-id="106c9-161">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="106c9-162">Ejecute la sincronización inicial para la asignación **Contactos CDS V2 (contactos)**.</span><span class="sxs-lookup"><span data-stu-id="106c9-162">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span> <span data-ttu-id="106c9-163">Debe sincronizar esta asignación si desea sincronizar la columna de contacto principal en la tabla proveedores, ya que la sincronización inicial también debe efectuarse para las filas de contactos.</span><span class="sxs-lookup"><span data-stu-id="106c9-163">You must sync this mapping if you want to sync the primary contact column on the vendors table, because initial synchronization must also be done for the contact rows.</span></span>
5. <span data-ttu-id="106c9-164">Agregue las columnas **PrimaryContactPersonId** e **InvoiceVendorAccountNumber** otra vez a la asignación **Proveedores V2 (msdyn\_vendors)** y guarde la asignación.</span><span class="sxs-lookup"><span data-stu-id="106c9-164">Add the **PrimaryContactPersonId** and **InvoiceVendorAccountNumber** columns back to the **Vendors V2 (msdyn\_vendors)** mapping, and then save the mapping.</span></span>
6. <span data-ttu-id="106c9-165">Vuelva a ejecutar la sincronización inicial para la asignación de **Proveedores V2 (msdyn\_vendors)**.</span><span class="sxs-lookup"><span data-stu-id="106c9-165">Run initial synchronization again for the **Vendors V2 (msdyn\_vendors)** mapping.</span></span> <span data-ttu-id="106c9-166">Dado que Change Tracking está desactivado, todas las filas se sincronizarán.</span><span class="sxs-lookup"><span data-stu-id="106c9-166">Because change tracking is turned off, all the rows will be synced.</span></span>
7. <span data-ttu-id="106c9-167">Vuelva a activar Change Tracking para la tabla **Proveedores V2**.</span><span class="sxs-lookup"><span data-stu-id="106c9-167">Turn change tracking back on for the **Vendors V2** table.</span></span>

## <a name="resolve-errors-in-the-customers-v3toaccounts-table-mapping"></a><a id="error-customer-map"></a><span data-ttu-id="106c9-168">Resolver errores en la asignación de tabla Clientes V3–to–Accounts</span><span class="sxs-lookup"><span data-stu-id="106c9-168">Resolve errors in the Customers V3–to–Accounts table mapping</span></span>

<span data-ttu-id="106c9-169">Puede encontrar los siguientes errores de sincronización inicial en la asignación de **Clientes V3** a **Cuentas** si las tablas tienen filas existentes con valores en las columnas **ContactPersonID** e **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="106c9-169">You might encounter initial synchronization errors for the mapping of **Customers V3** to **Accounts** if the tables have existing rows where there are values in the **ContactPersonID** and **InvoiceAccount** columns.</span></span> <span data-ttu-id="106c9-170">Estos errores se producen porque **InvoiceAccount** es una columna de autorreferencia y **ContactPersonID** es una referencia circular en la asignación del proveedor.</span><span class="sxs-lookup"><span data-stu-id="106c9-170">These errors occur because **InvoiceAccount** is a self-referencing column, and **ContactPersonID** is a circular reference in the vendor mapping.</span></span>

<span data-ttu-id="106c9-171">Los mensajes de error que reciba tendrán el siguiente formulario.</span><span class="sxs-lookup"><span data-stu-id="106c9-171">The error messages that you receive will have the following form.</span></span>

<span data-ttu-id="106c9-172">*No se pudo resolver el guid para el campo: \<field\>. No se encontró la búsqueda: \<value\>. Pruebe estas URL para verificar si los datos de referencia existen: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span><span class="sxs-lookup"><span data-stu-id="106c9-172">*Couldn't resolve the guid for the field: \<field\>. The lookup was not found: \<value\>. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/<entity>?$select=<field>&$filter=<field> eq <value>`*</span></span>

<span data-ttu-id="106c9-173">A continuación, encontrará algunos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="106c9-173">Here are some examples:</span></span>

- <span data-ttu-id="106c9-174">*No se pudo resolver el guid para el campo: primarycontactid.msdyn\_contactpersonid. No se encontró la busqueda: 000056. Pruebe estas URL para verificar si los datos de referencia existen: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span><span class="sxs-lookup"><span data-stu-id="106c9-174">*Couldn't resolve the guid for the field: primarycontactid.msdyn\_contactpersonid. The lookup was not found: 000056. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/contacts?$select=msdyn_contactpersonid.contactid&$filter=msdyn_contactpersonid eq '000056'`*</span></span>
- <span data-ttu-id="106c9-175">*No se pudo resolver el guid para el campo: msdyn\_billingaccount.accountnumber. No se encontró la búsqueda: 1206-1 . Pruebe estas URL para verificar si los datos de referencia existen: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span><span class="sxs-lookup"><span data-stu-id="106c9-175">*Couldn't resolve the guid for the field: msdyn\_billingaccount.accountnumber. The lookup was not found: 1206-1. Try this URL(s) to check if the reference data exists: `https://focdsdevtest2.crm.dynamics.com/api/data/v9.0/accounts?$select=accountnumber.account&$filter=accountnumber eq '1206-1'`*</span></span>

<span data-ttu-id="106c9-176">Si tiene filas en la tabla del cliente con valores en las columnas **ContactPersonID** e **InvoiceAccount**, siga estos pasos para completar la sincronización inicial.</span><span class="sxs-lookup"><span data-stu-id="106c9-176">If any rows in the customer table have values in the **ContactPersonID** and **InvoiceAccount** columns, follow these steps to complete the initial synchronization.</span></span> <span data-ttu-id="106c9-177">Puede usar este enfoque para cualquier tabla lista para usar como **Cuentas** y **Contactos**.</span><span class="sxs-lookup"><span data-stu-id="106c9-177">You can use this approach for any out-of-box tables, such **Accounts** and **Contacts**.</span></span>

1. <span data-ttu-id="106c9-178">En la aplicación Finance and Operations, elimine las columnas **ContactPersonId** e **InvoiceAccount** de la asignación **Clientes V3 (cuentas)** y guarde la asignación.</span><span class="sxs-lookup"><span data-stu-id="106c9-178">In the Finance and Operations app, delete the **ContactPersonID** and **InvoiceAccount** columns from the **Customers V3 (accounts)** mapping, and then save the mapping.</span></span>

    1. <span data-ttu-id="106c9-179">En la página de mapeo de doble escritura para **Clientes V3 (cuentas)**, en la pestaña **Asignaciones de tablas**. En el filtro izquierdo, seleccione **Finance and Operations app.Customers V3**.</span><span class="sxs-lookup"><span data-stu-id="106c9-179">On the dual-write mapping page for **Customers V3 (accounts)**, on the **Table mappings** tab, in the left filter, select **Finance and Operations app.Customers V3**.</span></span> <span data-ttu-id="106c9-180">En el filtro derecho, seleccione **Dataverse.Account**.</span><span class="sxs-lookup"><span data-stu-id="106c9-180">In the right filter, select **Dataverse.Account**.</span></span>
    2. <span data-ttu-id="106c9-181">Busque **contactperson** para encontrar la columna de origen **ContactPersonID**.</span><span class="sxs-lookup"><span data-stu-id="106c9-181">Search for **contactperson** to find the **ContactPersonID** source column.</span></span>
    3. <span data-ttu-id="106c9-182">Seleccione **Acciones** y luego seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="106c9-182">Select **Actions**, and then select **Delete**.</span></span>

        ![Eliminar la columna ContactPersonID](media/cust_selfref3.png)

    4. <span data-ttu-id="106c9-184">Repita estos pasos para eliminar la columna **InvoiceAccount**.</span><span class="sxs-lookup"><span data-stu-id="106c9-184">Repeat these steps to delete the **InvoiceAccount** column.</span></span>

        ![Eliminar la columna InvoiceAccount](media/cust_selfref4.png)

    5. <span data-ttu-id="106c9-186">Guardar los cambios en la asignación.</span><span class="sxs-lookup"><span data-stu-id="106c9-186">Save your changes to the mapping.</span></span>

2. <span data-ttu-id="106c9-187">Desactive el seguimiento de cambios para la tabla **Clientes V3**.</span><span class="sxs-lookup"><span data-stu-id="106c9-187">Turn off change tracking for the **Customers V3** table.</span></span>

    1. <span data-ttu-id="106c9-188">En espacio de trabajo **Administración de datos**, seleccione la ventana **Tablas de datos**.</span><span class="sxs-lookup"><span data-stu-id="106c9-188">In the **Data management** workspace, select the **Data tables** tile.</span></span>
    2. <span data-ttu-id="106c9-189">Seleccione la tabla **Clientes V3**.</span><span class="sxs-lookup"><span data-stu-id="106c9-189">Select the **Customers V3** table.</span></span>
    3. <span data-ttu-id="106c9-190">En el panel de acciones, seleccione **Opciones** y después seleccione **Change Tracking**.</span><span class="sxs-lookup"><span data-stu-id="106c9-190">On the Action Pane, select **Options**, and then select **Change tracking**.</span></span>

        ![Seleccionar la opción Change Tracking](media/selfref_options.png)

    4. <span data-ttu-id="106c9-192">Seleccione **Deshabilitar Change Tracking**.</span><span class="sxs-lookup"><span data-stu-id="106c9-192">Select **Disable Change Tracking**.</span></span>

        ![Seleccionar Deshabilitar Change Tracking](media/selfref_tracking.png)

3. <span data-ttu-id="106c9-194">Ejecute otra vez la sincronización inicial para la asignación **Clientes V3 (Cuentas)**.</span><span class="sxs-lookup"><span data-stu-id="106c9-194">Run initial synchronization for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="106c9-195">La sincronización inicial debe ejecutarse correctamente sin ningún error.</span><span class="sxs-lookup"><span data-stu-id="106c9-195">The initial synchronization should run successfully, without any errors.</span></span>
4. <span data-ttu-id="106c9-196">Ejecute la sincronización inicial para la asignación **Contactos CDS V2 (contactos)**.</span><span class="sxs-lookup"><span data-stu-id="106c9-196">Run initial synchronization for the **CDS Contacts V2 (contacts)** mapping.</span></span>

    > [!NOTE]
    > <span data-ttu-id="106c9-197">Hay dos asignaciones que tienen el mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="106c9-197">There are two maps that have the same name.</span></span> <span data-ttu-id="106c9-198">Asegúrese de seleccionar la asignación tenga la descripción siguiente en la pestaña **Detalles**: **Plantilla de doble escritura para sincronización entre Contactos de proveedor FO.CDS V2 con CDS.Contacts. Requiere nuevo paquete \[Dynamics365SupplyChainExtended\].**</span><span class="sxs-lookup"><span data-stu-id="106c9-198">Be sure to select the map that has the following description on the **Details** tab: **Dual-write template for sync between FO.CDS Vendor Contacts V2 to CDS.Contacts. Requires new package \[Dynamics365SupplyChainExtended\].**</span></span>

5. <span data-ttu-id="106c9-199">Vuelva a agregar las columnas **InvoiceAccount** y **ContactPersonId** a la asignación **Clientes V3 (Cuentas)** y guarde la asignación.</span><span class="sxs-lookup"><span data-stu-id="106c9-199">Add the **InvoiceAccount** and **ContactPersonId** columns back to the **Customers V3 (Accounts)** mapping, and then save the mapping.</span></span> <span data-ttu-id="106c9-200">Tanto la columna **InvoiceAccount** como la columna **ContactPersonId** vuelven a ser parte del modo de sincronización en vivo.</span><span class="sxs-lookup"><span data-stu-id="106c9-200">Both the **InvoiceAccount** column and the **ContactPersonId** column are now part of live synchronization mode again.</span></span> <span data-ttu-id="106c9-201">En el siguiente paso, completará la sincronización inicial para estas columnas.</span><span class="sxs-lookup"><span data-stu-id="106c9-201">In the next step, you will do the initial synchronization for these columns.</span></span>
6. <span data-ttu-id="106c9-202">Ejecute otra vez la sincronización inicial para la asignación **Clientes V3 (Cuentas)**.</span><span class="sxs-lookup"><span data-stu-id="106c9-202">Run initial synchronization again for the **Customers V3 (Accounts)** mapping.</span></span> <span data-ttu-id="106c9-203">Debido a que el seguimiento de cambios está deshabilitado, los datos para **InvoiceAccount** y **ContactPersonId** se sincronizarán desde la aplicación Finance and Operations a Dataverse.</span><span class="sxs-lookup"><span data-stu-id="106c9-203">Because change tracking is turned off, the data for **InvoiceAccount** and **ContactPersonId** will be synced from the Finance and Operations app to Dataverse.</span></span>
7. <span data-ttu-id="106c9-204">Para sincronizar los datos para **InvoiceAccount** y **ContactPersonId** desde Dataverse a la aplicación Finance and Operations, debe utilizar un proyecto de integración de datos.</span><span class="sxs-lookup"><span data-stu-id="106c9-204">To sync the data for **InvoiceAccount** and **ContactPersonId** from Dataverse to the Finance and Operations app, you must use a data integration project.</span></span>

    1. <span data-ttu-id="106c9-205">En Power Apps, cree un proyecto de integración de datos entre **Sales.Account** y las tablas **Finance and Operations.Customers V3**.</span><span class="sxs-lookup"><span data-stu-id="106c9-205">In Power Apps, create a data integration project between the **Sales.Account** and **Finance and Operations apps.Customers V3** tables.</span></span> <span data-ttu-id="106c9-206">La dirección de datos debe ser de Dataverse a la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="106c9-206">The data direction must be from Dataverse to the Finance and Operations app.</span></span> <span data-ttu-id="106c9-207">Como **InvoiceAccount** es un nuevo atributo en doble escritura, es posible que desee omitir la sincronización inicial para este atributo.</span><span class="sxs-lookup"><span data-stu-id="106c9-207">Because **InvoiceAccount** is a new attribute in dual-write, you might want to skip initial synchronization for it.</span></span> <span data-ttu-id="106c9-208">Para obtener más información, consulte [Integrar datos en Dataverse](https://docs.microsoft.com/power-platform/admin/data-integrator).</span><span class="sxs-lookup"><span data-stu-id="106c9-208">For more information, see [Integrate data into Dataverse](https://docs.microsoft.com/power-platform/admin/data-integrator).</span></span>

        <span data-ttu-id="106c9-209">La siguiente ilustración muestra un proyecto que actualiza **CustomerAccount** y **ContactPersonId**.</span><span class="sxs-lookup"><span data-stu-id="106c9-209">The following illustration shows a project that updates **CustomerAccount** and **ContactPersonId**.</span></span>

        ![Proyecto de integración de datos para actualizar CustomerAccount y ContactPersonId](media/cust_selfref6.png)

    2. <span data-ttu-id="106c9-211">Agregue los criterios de la empresa en el filtro del lado Dataverse, de forma que solo las filas que coinciden con los criterios de filtro se actualizarán en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="106c9-211">Add the company criteria in the filter on the Dataverse side, so that only rows that match the filter criteria will be updated in the Finance and Operations app.</span></span> <span data-ttu-id="106c9-212">Para agregar un filtro, seleccione el botón del filtro.</span><span class="sxs-lookup"><span data-stu-id="106c9-212">To add a filter, select the filter button.</span></span> <span data-ttu-id="106c9-213">Posteriormente, en el cuadro de diálogo **Editar consulta** puede agregar una consulta de filtro como **\_msdyn\_company\_value eq '\<guid\>'**.</span><span class="sxs-lookup"><span data-stu-id="106c9-213">Then, in the **Edit query** dialog box, you can add a filter query such as **\_msdyn\_company\_value eq '\<guid\>'**.</span></span> 

        > <span data-ttu-id="106c9-214">[NOTA] Si el botón del filtro no está presente, cree un ticket de soporte para solicitar al equipo de integración de datos que habilite la capacidad de filtro en su inquilino.</span><span class="sxs-lookup"><span data-stu-id="106c9-214">[NOTE] If the filter button isn't present, create a support ticket to ask the data integration team to enable the filter capability on your tenant.</span></span>

        <span data-ttu-id="106c9-215">Si no especifica una consulta de filtro para **\_msdyn\_company\_value**, entonces todas las filas se sincronizarán.</span><span class="sxs-lookup"><span data-stu-id="106c9-215">If you don't enter a filter query for **\_msdyn\_company\_value**, all the rows will be synced.</span></span>

        ![Agregar una consulta de filtro](media/cust_selfref7.png)

    <span data-ttu-id="106c9-217">La sincronización inicial de las filas ahora se ha completado.</span><span class="sxs-lookup"><span data-stu-id="106c9-217">The initial synchronization of the rows is now completed.</span></span>

8. <span data-ttu-id="106c9-218">En la aplicación Finance and Operations, vuelva a activar Change Tracking en la tabla **Clientes V3**.</span><span class="sxs-lookup"><span data-stu-id="106c9-218">In the Finance and Operations app, turn change tracking back on for the **Customers V3** table.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]