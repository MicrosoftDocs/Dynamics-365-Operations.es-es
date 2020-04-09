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
ms.openlocfilehash: d51b547093825a6e7730b5fdfcfb1c081776c63c
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172723"
---
# <a name="troubleshoot-issues-during-initial-synchronization"></a><span data-ttu-id="b5b4b-103">Solucionar problemas durante la sincronización</span><span class="sxs-lookup"><span data-stu-id="b5b4b-103">Troubleshoot issues during initial synchronization</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="b5b4b-104">Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="b5b4b-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="b5b4b-105">Específicamente proporciona información que puede ayudarlo a solucionar problemas durante la sincronización inicial.</span><span class="sxs-lookup"><span data-stu-id="b5b4b-105">Specifically, it provides information that can help you fix issues that might occur during initial synchronization.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="b5b4b-106">Algunos de los problemas que aborda este tema pueden requerir la función de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="b5b4b-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="b5b4b-107">La sección para cada problema explica si se requiere una función o credenciales específicas.</span><span class="sxs-lookup"><span data-stu-id="b5b4b-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="check-for-initial-synchronization-errors-in-a-finance-and-operations-app"></a><span data-ttu-id="b5b4b-108">Verificar los errores de sincronización inicial en una aplicación Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b5b4b-108">Check for initial synchronization errors in a Finance and Operations app</span></span>

<span data-ttu-id="b5b4b-109">Después de habilitar las plantillas de asignación, el estado de los mapas debe ser **Ejecutando**.</span><span class="sxs-lookup"><span data-stu-id="b5b4b-109">After you enable the mapping templates, the status of the maps should be **Running**.</span></span> <span data-ttu-id="b5b4b-110">Si el estado es **No ejecutando**, se produjeron errores durante la sincronización inicial.</span><span class="sxs-lookup"><span data-stu-id="b5b4b-110">If the status is **Not running**, errors occurred during initial synchronization.</span></span> <span data-ttu-id="b5b4b-111">Para ver los errores, seleccione la pestaña **Detalles de sincronización inicial** en la página **Escritura doble**.</span><span class="sxs-lookup"><span data-stu-id="b5b4b-111">To view the errors, select the **Initial sync details** tab on the **Dual-write** page.</span></span>

![Pestaña de detalles de sincronización inicial](media/initial_sync_status.png)

## <a name="you-cant-complete-initial-synchronization-400-bad-request"></a><span data-ttu-id="b5b4b-113">No puede completar la sincronización inicial: 400 Solicitud incorrecta</span><span class="sxs-lookup"><span data-stu-id="b5b4b-113">You can't complete initial synchronization: 400 Bad Request</span></span>

<span data-ttu-id="b5b4b-114">**Rol requerido para arreglar el error:** Administrador del sistema</span><span class="sxs-lookup"><span data-stu-id="b5b4b-114">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="b5b4b-115">Es posible que reciba el siguiente mensaje de error cuando intente ejecutar la asignación y la sincronización inicial:</span><span class="sxs-lookup"><span data-stu-id="b5b4b-115">You might receive the following error message when you try to run the mapping and initial synchronization:</span></span>

<span data-ttu-id="b5b4b-116">*El servidor remoto devolvió un error: (400) Solicitud incorrecta.), exportación AX encontró un error*</span><span class="sxs-lookup"><span data-stu-id="b5b4b-116">*The remote server returned an error: (400) Bad Request.), AX export encountered an error*</span></span>

<span data-ttu-id="b5b4b-117">A continuación se muestra un ejemplo del mensaje de error completo.</span><span class="sxs-lookup"><span data-stu-id="b5b4b-117">Here is an example of the full error message.</span></span>

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

<span data-ttu-id="b5b4b-118">Si este error ocurre de manera constante y no puede completar la sincronización inicial, siga estos pasos para solucionar el problema.</span><span class="sxs-lookup"><span data-stu-id="b5b4b-118">If this error occurs consistently, and you can't complete the initial synchronization, follow these steps to fix the issue.</span></span>

1. <span data-ttu-id="b5b4b-119">Inicie sesión en la máquina virtual (VM) para la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b5b4b-119">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="b5b4b-120">Abra Microsoft Management Console.</span><span class="sxs-lookup"><span data-stu-id="b5b4b-120">Open Microsoft Management Console.</span></span> 
3. <span data-ttu-id="b5b4b-121">En el panel **Servicios**, asegúrese de que el servicio de exportación de marco de Microsoft Dynamics 365 Data se está ejecutando.</span><span class="sxs-lookup"><span data-stu-id="b5b4b-121">In the **Services** pane, make sure that the Microsoft Dynamics 365 Data import export framework service is running.</span></span> <span data-ttu-id="b5b4b-122">Reinícielo si se ha detenido, porque la sincronización inicial lo requiere.</span><span class="sxs-lookup"><span data-stu-id="b5b4b-122">Restart it if it has been stopped, because the initial synchronization requires it.</span></span>

## <a name="initial-synchronization-error-403-forbidden"></a><span data-ttu-id="b5b4b-123">Error de sincronización inicial: 403 Prohibido</span><span class="sxs-lookup"><span data-stu-id="b5b4b-123">Initial synchronization error: 403 Forbidden</span></span>

<span data-ttu-id="b5b4b-124">Es posible que reciba el siguiente mensaje de error durante la sincronización inicial:</span><span class="sxs-lookup"><span data-stu-id="b5b4b-124">You might receive the following error message during initial synchronization:</span></span>

<span data-ttu-id="b5b4b-125">*(\[Prohibido\], el servidor remoto devolvión un error: (403) Prohibido.), exportación AX encontró un error*</span><span class="sxs-lookup"><span data-stu-id="b5b4b-125">*(\[Forbidden\], The remote server returned an error: (403) Forbidden.), AX export encountered an error*</span></span>

<span data-ttu-id="b5b4b-126">Para arreglar el problema, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="b5b4b-126">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="b5b4b-127">Iniciar sesión en la aplicación Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b5b4b-127">Sign in to the Finance and Operations app.</span></span>
2. <span data-ttu-id="b5b4b-128">En la págona **aplicaciones Azure Active Directory**, elimine el cliente **DtAppID**, y luego agréguelo nuevamente.</span><span class="sxs-lookup"><span data-stu-id="b5b4b-128">On the **Azure Active Directory applications** page, delete the **DtAppID** client, and then add it again.</span></span>

![Lista de aplicaciones Azure AD](media/aad_applications.png)

## <a name="self-reference-failures-during-initial-synchronization"></a><span data-ttu-id="b5b4b-130">Fallos de autorreferencia durante la sincronización inicial</span><span class="sxs-lookup"><span data-stu-id="b5b4b-130">Self-reference failures during initial synchronization</span></span>

<span data-ttu-id="b5b4b-131">Es posible que reciba un mensaje de error similar al siguiente ejemplo si alguna de sus asignaciones tiene autorreferencias:</span><span class="sxs-lookup"><span data-stu-id="b5b4b-131">You might receive an error message that resembles the following example if any of your mappings have self-references:</span></span>

<span data-ttu-id="b5b4b-132">*En Vendors V2, aparece el siguiente error: ID de registro: nuevo registro, Mensaje de error: No se pudo resolver el guid para el campo: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. No se encontró el valor de búsqueda: CN-001. Pruebe estas URL para verificar si los datos de referencia existen: `https://sampleorg.crm.dynamics.com/api/data/v9.0/msdyn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber` eq 'CN-001'*</span><span class="sxs-lookup"><span data-stu-id="b5b4b-132">*On the Vendors V2, the following error: Record Id: new record, ErrorMessage: Couldn't resolve the guid for the field: msdyn\_invoicevendoraccountnumber.msdyn\_vendoraccountnumber. The lookup value was not found: CN-001. Try this URL(s) to check if the reference data exists: `https://sampleorg.crm.dynamics.com/api/data/v9.0/msdyn_vendors?$select=msdyn_vendoraccountnumber,msdyn_vendorid&$filter=msdyn_vendoraccountnumber` eq 'CN-001'*</span></span>

<span data-ttu-id="b5b4b-133">Este tipo de error ocurre durante la sincronización inicial de las asignaciones que tienen autorreferencias.</span><span class="sxs-lookup"><span data-stu-id="b5b4b-133">This type of error occurs during initial synchronization of mappings that have self-references.</span></span> <span data-ttu-id="b5b4b-134">En el ejemplo anterior, la cuenta de la factura de campo hace referencia a la entidad del proveedor.</span><span class="sxs-lookup"><span data-stu-id="b5b4b-134">In the preceding example, the field invoice account references the vendor entity.</span></span>

<span data-ttu-id="b5b4b-135">Para solucionar el problema, es posible que deba ejecutar la asignación dos veces antes de que la sincronización inicial sea exitosa.</span><span class="sxs-lookup"><span data-stu-id="b5b4b-135">To fix the issue, you might have to run the mapping two times before the initial synchronization is successful.</span></span>

