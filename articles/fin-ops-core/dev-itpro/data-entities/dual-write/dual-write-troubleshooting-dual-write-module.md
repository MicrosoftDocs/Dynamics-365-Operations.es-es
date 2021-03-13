---
title: Solucionar problemas de doble escritura en aplicaciones de Finance and Operations
description: Este tema proporciona información de solución de problemas que puede ayudarlo a solucionar problemas con el módulo de escritura doble en aplicaciones Finance and Operations.
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
ms.openlocfilehash: 3ffeb2de0acc1761bccf62a1a124852c504e2a3a
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "5131254"
---
# <a name="troubleshoot-dual-write-issues-in-finance-and-operations-apps"></a><span data-ttu-id="72e94-103">Solucionar problemas de doble escritura en aplicaciones de Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="72e94-103">Troubleshoot dual-write issues in Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="72e94-104">Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Dataverse.</span><span class="sxs-lookup"><span data-stu-id="72e94-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="72e94-105">Específicamente, proporciona información que puede ayudarlo a solucionar problemas con el módulo de **Escritura doble** en aplicaciones Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="72e94-105">Specifically, it provides information that can help you fix issues with the **Dual-write** module in Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="72e94-106">Algunos de los problemas que aborda este tema pueden requerir la función de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="72e94-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="72e94-107">La sección para cada problema explica si se requiere una función o credenciales específicas.</span><span class="sxs-lookup"><span data-stu-id="72e94-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a><span data-ttu-id="72e94-108">No puede cargar el módulo de doble escritura en una aplicación Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="72e94-108">You can't load the dual-write module in a Finance and Operations app</span></span>

<span data-ttu-id="72e94-109">Si no puede abrir la página **Doble escritura** seleccionando el mosaico **Doble escritura** en el espacio de trabajo **Gestión de datos**, el servicio de integración de datos probablemente esté inactivo.</span><span class="sxs-lookup"><span data-stu-id="72e94-109">If you can't open the **Dual-write** page by selecting the **Dual Write** tile in the **Data management** workspace, the data integration service is probably down.</span></span> <span data-ttu-id="72e94-110">Cree un ticket de soporte para solicitar un reinicio del servicio de integración de datos.</span><span class="sxs-lookup"><span data-stu-id="72e94-110">Create a support ticket to request a restart of the data integration service.</span></span>

## <a name="error-when-you-try-to-create-a-new-table-map"></a><span data-ttu-id="72e94-111">Error al intentar crear una nueva asignación de tabla</span><span class="sxs-lookup"><span data-stu-id="72e94-111">Error when you try to create a new table map</span></span>

<span data-ttu-id="72e94-112">**Credenciales necesarias para solucionar el problema**: el mismo usuario que configuró la doble escritura.</span><span class="sxs-lookup"><span data-stu-id="72e94-112">**Required credentials to fix the issue:** The same user that setup dual-write.</span></span>

<span data-ttu-id="72e94-113">Es posible que reciba el siguiente mensaje de error cuando intente configurar una nueva tabla para doble escritura.</span><span class="sxs-lookup"><span data-stu-id="72e94-113">You might receive the following error message when you try to configure a new table for dual-write.</span></span> <span data-ttu-id="72e94-114">El único usuario que puede crear una asignación es el usuario que configuró la conexión de doble escritura.</span><span class="sxs-lookup"><span data-stu-id="72e94-114">The only user that can create a map is the user who setup the dual-write connection.</span></span>

<span data-ttu-id="72e94-115">*El código de estado de respuesta no indica éxito: 401 (No autorizado)*</span><span class="sxs-lookup"><span data-stu-id="72e94-115">*Response status code does not indicate success: 401 (Unauthorized)*</span></span>


## <a name="error-when-you-open-the-dual-write-user-interface"></a><span data-ttu-id="72e94-116">Error al abrir la interfaz de usuario de doble escritura</span><span class="sxs-lookup"><span data-stu-id="72e94-116">Error when you open the dual-write user interface</span></span>

<span data-ttu-id="72e94-117">Es posible que reciba el siguiente mensaje de error cuando intente acceder a la escritura doble desde el espacio de trabajo **Gestión de datos**:</span><span class="sxs-lookup"><span data-stu-id="72e94-117">You might receive the following error message when you try to access dual-write from the **Data management** workspace:</span></span>

<span data-ttu-id="72e94-118">*login.microsoftonline.com se negó a conectarse.*</span><span class="sxs-lookup"><span data-stu-id="72e94-118">*login.microsoftonline.com refused to connect.*</span></span>

<span data-ttu-id="72e94-119">Para solucionar el problema, inicie sesión utilizando una ventana InPrivate en Microsoft Edge, una ventana de incógnito en Chromium o una ventana de incógnito en Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="72e94-119">To fix the issue, sign in by using an InPrivate window in Microsoft Edge, an incognito window in Chromium, or an incognito window in Google Chrome.</span></span> <span data-ttu-id="72e94-120">También debe desbloquear o borrar las cookies de terceros.</span><span class="sxs-lookup"><span data-stu-id="72e94-120">You must also unblock or clear third-party cookies.</span></span>

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-table-mapping"></a><span data-ttu-id="72e94-121">Error al vincular el entorno para doble escritura o agregar una nueva asignación de tabla</span><span class="sxs-lookup"><span data-stu-id="72e94-121">Error when you link the environment for dual-write or add a new table mapping</span></span>

<span data-ttu-id="72e94-122">**Rol requerido para solucionar el problema**: Administrador del sistema en aplicaciones de Finance and Operations y Dataverse.</span><span class="sxs-lookup"><span data-stu-id="72e94-122">**Required role to fix the issue:** System administrator in both Finance and Operations apps and Dataverse.</span></span>

<span data-ttu-id="72e94-123">Puede encontrar el siguiente error al vincular o crear mapas:</span><span class="sxs-lookup"><span data-stu-id="72e94-123">You might encounter the following error when linking or creating maps:</span></span>

<span data-ttu-id="72e94-124">*El código de estado de respuesta no indica éxito: 403 (tokenexchange).<br> Id. de sesión: \<your session id\><br> Id. de actividad raíz: \<your root activity id\>*</span><span class="sxs-lookup"><span data-stu-id="72e94-124">*Response status code does not indicate success: 403 (tokenexchange).<br> Session ID: \<your session id\><br> Root activity ID: \<your root activity id\>*</span></span>

<span data-ttu-id="72e94-125">Este error puede ocurrir si no tiene permisos suficientes para vincular escritura doble o crear mapas.</span><span class="sxs-lookup"><span data-stu-id="72e94-125">This error can occur if you don't have sufficient permissions to link dual-write or create maps.</span></span> <span data-ttu-id="72e94-126">Este error también puede ocurrir si el entorno de Dataverse se restableció sin desvincular la doble escritura.</span><span class="sxs-lookup"><span data-stu-id="72e94-126">This error can also occur if the Dataverse environment was reset without unlinking dual-write.</span></span> <span data-ttu-id="72e94-127">Cualquier usuario con rol de administrador del sistema en aplicaciones de Finance and Operations y Dataverse puede vincular los entornos.</span><span class="sxs-lookup"><span data-stu-id="72e94-127">Any user with system administrator role in both Finance and Operations apps and Dataverse can link the environments.</span></span> <span data-ttu-id="72e94-128">Solo el usuario que configuró la conexión de doble escritura puede agregar nuevas asignaciones de tabla.</span><span class="sxs-lookup"><span data-stu-id="72e94-128">Only the user who setup the dual-write connection can add new table maps.</span></span> <span data-ttu-id="72e94-129">Después de la configuración, cualquier usuario con función de administrador del sistema puede monitorear el estado y editar las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="72e94-129">After setup, any user with system administrator role can monitor the status and edit the mappings.</span></span>

## <a name="error-when-you-stop-the-table-mapping"></a><span data-ttu-id="72e94-130">Error al detener la asignación de tabla</span><span class="sxs-lookup"><span data-stu-id="72e94-130">Error when you stop the table mapping</span></span>

<span data-ttu-id="72e94-131">Es posible que reciba el siguiente mensaje de error cuando intenta detener las asignaciones de tabla:</span><span class="sxs-lookup"><span data-stu-id="72e94-131">You might receive the following error message when you try to stop the table mappings:</span></span>

<span data-ttu-id="72e94-132">*\[Prohibido\], \[{"status": 403,"source":"","message":"Error del intercambio de tokens: el usuario no puede acceder a la conexión dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], El servidor remoto devolvió un error: (403) Prohibido.*</span><span class="sxs-lookup"><span data-stu-id="72e94-132">*\[Forbidden\], \[{"status":403,"source":"","message":"Error from token exchange: User is not allowed to access connection dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], The remote server returned an error: (403) Forbidden.*</span></span>

<span data-ttu-id="72e94-133">Este error ocurre cuando el entorno vinculado Dataverse no está disponible.</span><span class="sxs-lookup"><span data-stu-id="72e94-133">This error occurs when the linked Dataverse environment isn't available.</span></span>

<span data-ttu-id="72e94-134">Para solucionar el problema, cree un ticket para el equipo de integración de datos.</span><span class="sxs-lookup"><span data-stu-id="72e94-134">To fix the issue, create a ticket for the Data Integration team.</span></span> <span data-ttu-id="72e94-135">Adjunte la traza de red para que el equipo de integración de datos pueda marcar los mapas como **No ejecutando** en el back-end.</span><span class="sxs-lookup"><span data-stu-id="72e94-135">Attach the network trace so that the Data Integration team can mark the maps as **Not running** in the back end.</span></span>

## <a name="error-while-trying-to-start-a-table-mapping"></a><span data-ttu-id="72e94-136">Error al intentar iniciar una asignación de tabla</span><span class="sxs-lookup"><span data-stu-id="72e94-136">Error while trying to start a table mapping</span></span>

<span data-ttu-id="72e94-137">Es posible que reciba un error como el siguiente cuando intenta establecer ese estado de una asignación como **En ejecución**:</span><span class="sxs-lookup"><span data-stu-id="72e94-137">You might receive an error like the following when you try to set that state of a mapping to **Running**:</span></span>

<span data-ttu-id="72e94-138">*No se puede completar la sincronización de datos inicial. Error: error de doble escritura - error en el registro del complemento: no se pueden construir metadatos de búsqueda de doble escritura. La referencia de objeto de error no está establecida en una instancia de un objeto*.</span><span class="sxs-lookup"><span data-stu-id="72e94-138">*Unable to complete initial data sync. Error: dual-write failure - plugin registration failed: Unable to build dual-write lookup metadata. Error object reference not set to an instance of an object.*</span></span>

<span data-ttu-id="72e94-139">La solución para este error depende de la causa del error:</span><span class="sxs-lookup"><span data-stu-id="72e94-139">The fix for this error depends on the cause of the error:</span></span>

+ <span data-ttu-id="72e94-140">Si la asignación tiene asignaciones dependientes, asegúrese de habilitar las asignaciones dependientes de esta asignación de tabla.</span><span class="sxs-lookup"><span data-stu-id="72e94-140">If the mapping has dependent mappings, then make sure to enable the dependent mappings of this table mapping.</span></span>
+ <span data-ttu-id="72e94-141">Es posible que falten columnas de origen o destino en la asignación.</span><span class="sxs-lookup"><span data-stu-id="72e94-141">The mapping might be missing source or destination columns.</span></span> <span data-ttu-id="72e94-142">Si falta una columna en la aplicación de Finance and Operations, siga los pasos de la sección [Problema de columnas de tabla faltantes en asignaciones](dual-write-troubleshooting-finops-upgrades.md#missing-table-columns-issue-on-maps).</span><span class="sxs-lookup"><span data-stu-id="72e94-142">If a column in the Finance and Operations app is missing, then follow the steps in the section [Missing table columns issue on maps](dual-write-troubleshooting-finops-upgrades.md#missing-table-columns-issue-on-maps).</span></span> <span data-ttu-id="72e94-143">Si falta una columna en Dataverse, haga clic en el botón **Actualizar tablas** en la asignación para que las columnas se rellenen automáticamente en la asignación.</span><span class="sxs-lookup"><span data-stu-id="72e94-143">If a column in Dataverse is missing, then click **Refresh tables** button on the mapping so that the columns are automatically populated back into the mapping.</span></span>
