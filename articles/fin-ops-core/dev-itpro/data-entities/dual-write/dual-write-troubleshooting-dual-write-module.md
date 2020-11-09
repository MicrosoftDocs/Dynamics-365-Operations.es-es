---
title: Solucionar problemas con el módulo de doble escritura en aplicaciones Finance and Operations
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
ms.openlocfilehash: f99f3760e75ec1bbf2ccdea497cf2eec3e28e233
ms.sourcegitcommit: 0a741b131ed71f6345d4219a47cf5f71fec6744b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "3997383"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a><span data-ttu-id="c7b12-103">Solucionar problemas con el módulo de doble escritura en aplicaciones Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c7b12-103">Troubleshoot issues with the dual-write module in Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c7b12-104">Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c7b12-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="c7b12-105">Específicamente, proporciona información que puede ayudarlo a solucionar problemas con el módulo de **Escritura doble** en aplicaciones Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c7b12-105">Specifically, it provides information that can help you fix issues with the **Dual-write** module in Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c7b12-106">Algunos de los problemas que aborda este tema pueden requerir la función de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="c7b12-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="c7b12-107">La sección para cada problema explica si se requiere una función o credenciales específicas.</span><span class="sxs-lookup"><span data-stu-id="c7b12-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a><span data-ttu-id="c7b12-108">No puede cargar el módulo de doble escritura en una aplicación Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c7b12-108">You can't load the dual-write module in a Finance and Operations app</span></span>

<span data-ttu-id="c7b12-109">Si no puede abrir la página **Doble escritura** seleccionando el mosaico **Doble escritura** en el espacio de trabajo **Gestión de datos** , el servicio de integración de datos probablemente esté inactivo.</span><span class="sxs-lookup"><span data-stu-id="c7b12-109">If you can't open the **Dual-write** page by selecting the **Dual Write** tile in the **Data management** workspace, the data integration service is probably down.</span></span> <span data-ttu-id="c7b12-110">Cree un ticket de soporte para solicitar un reinicio del servicio de integración de datos.</span><span class="sxs-lookup"><span data-stu-id="c7b12-110">Create a support ticket to request a restart of the data integration service.</span></span>

## <a name="error-when-you-try-to-create-a-new-entity-map"></a><span data-ttu-id="c7b12-111">Error al intentar crear una nueva asignación de entidad</span><span class="sxs-lookup"><span data-stu-id="c7b12-111">Error when you try to create a new entity map</span></span>

<span data-ttu-id="c7b12-112">**Credenciales necesarias para solucionar el problema** : el mismo usuario que configuró la doble escritura.</span><span class="sxs-lookup"><span data-stu-id="c7b12-112">**Required credentials to fix the issue:** The same user that setup dual-write.</span></span>

<span data-ttu-id="c7b12-113">Es posible que reciba el siguiente mensaje de error cuando intente configurar una nueva entidad para doble escritura.</span><span class="sxs-lookup"><span data-stu-id="c7b12-113">You might receive the following error message when you try to configure a new entity for dual-write.</span></span> <span data-ttu-id="c7b12-114">El único usuario que puede crear una asignación es el usuario que configuró la conexión de doble escritura.</span><span class="sxs-lookup"><span data-stu-id="c7b12-114">The only user that can create a map is the user who setup the dual-write connection.</span></span>

<span data-ttu-id="c7b12-115">*El código de estado de respuesta no indica éxito: 401 (No autorizado)*</span><span class="sxs-lookup"><span data-stu-id="c7b12-115">*Response status code does not indicate success: 401 (Unauthorized)*</span></span>


## <a name="error-when-you-open-the-dual-write-user-interface"></a><span data-ttu-id="c7b12-116">Error al abrir la interfaz de usuario de doble escritura</span><span class="sxs-lookup"><span data-stu-id="c7b12-116">Error when you open the dual-write user interface</span></span>

<span data-ttu-id="c7b12-117">Es posible que reciba el siguiente mensaje de error cuando intente acceder a la escritura doble desde el espacio de trabajo **Gestión de datos** :</span><span class="sxs-lookup"><span data-stu-id="c7b12-117">You might receive the following error message when you try to access dual-write from the **Data management** workspace:</span></span>

<span data-ttu-id="c7b12-118">*login.microsoftonline.com se negó a conectarse.*</span><span class="sxs-lookup"><span data-stu-id="c7b12-118">*login.microsoftonline.com refused to connect.*</span></span>

<span data-ttu-id="c7b12-119">Para solucionar el problema, inicie sesión utilizando una ventana InPrivate en Microsoft Edge, una ventana de incógnito en Chromium o una ventana de incógnito en Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="c7b12-119">To fix the issue, sign in by using an InPrivate window in Microsoft Edge, an incognito window in Chromium, or an incognito window in Google Chrome.</span></span> <span data-ttu-id="c7b12-120">También debe desbloquear o borrar las cookies de terceros.</span><span class="sxs-lookup"><span data-stu-id="c7b12-120">You must also unblock or clear third-party cookies.</span></span>

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-entity-mapping"></a><span data-ttu-id="c7b12-121">Error al vincular el entorno para doble escritura o agregar una nueva asignación de entidad</span><span class="sxs-lookup"><span data-stu-id="c7b12-121">Error when you link the environment for dual-write or add a new entity mapping</span></span>

<span data-ttu-id="c7b12-122">**Rol requerido para solucionar el problema** : Administrador del sistema en aplicaciones de Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="c7b12-122">**Required role to fix the issue:** System administrator in both Finance and Operations apps and Common Data Service.</span></span>

<span data-ttu-id="c7b12-123">Puede encontrar el siguiente error al vincular o crear mapas:</span><span class="sxs-lookup"><span data-stu-id="c7b12-123">You might encounter the following error when linking or creating maps:</span></span>

<span data-ttu-id="c7b12-124">*El código de estado de respuesta no indica éxito: 403 (tokenexchange).<br> Id. de sesión: \<your session id\><br> Id. de actividad raíz: \<your root activity id\>*</span><span class="sxs-lookup"><span data-stu-id="c7b12-124">*Response status code does not indicate success: 403 (tokenexchange).<br> Session ID: \<your session id\><br> Root activity ID: \<your root activity id\>*</span></span>

<span data-ttu-id="c7b12-125">Este error puede ocurrir si no tiene permisos suficientes para vincular escritura doble o crear mapas.</span><span class="sxs-lookup"><span data-stu-id="c7b12-125">This error can occur if you don't have sufficient permissions to link dual-write or create maps.</span></span> <span data-ttu-id="c7b12-126">Este error también puede ocurrir si el entorno de Common Data Service se restableció sin desvincular la doble escritura.</span><span class="sxs-lookup"><span data-stu-id="c7b12-126">This error can also occur if the Common Data Service environment was reset without unlinking dual-write.</span></span> <span data-ttu-id="c7b12-127">Cualquier usuario con rol de administrador del sistema en aplicaciones de Finance and Operations y Common Data Service puede vincular los entornos.</span><span class="sxs-lookup"><span data-stu-id="c7b12-127">Any user with system administrator role in both Finance and Operations apps and Common Data Service can link the environments.</span></span> <span data-ttu-id="c7b12-128">Solo el usuario que configuró la conexión de doble escritura puede agregar nuevas asignaciones de entidad.</span><span class="sxs-lookup"><span data-stu-id="c7b12-128">Only the user who setup the dual-write connection can add new entity maps.</span></span> <span data-ttu-id="c7b12-129">Después de la configuración, cualquier usuario con función de administrador del sistema puede monitorear el estado y editar las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="c7b12-129">After setup, any user with system administrator role can monitor the status and edit the mappings.</span></span>

## <a name="error-when-you-stop-the-entity-mapping"></a><span data-ttu-id="c7b12-130">Error al detener la asignación de entidad</span><span class="sxs-lookup"><span data-stu-id="c7b12-130">Error when you stop the entity mapping</span></span>

<span data-ttu-id="c7b12-131">Es posible que reciba el siguiente mensaje de error cuando intenta detener las asignaciones de entidad:</span><span class="sxs-lookup"><span data-stu-id="c7b12-131">You might receive the following error message when you try to stop the entity mappings:</span></span>

<span data-ttu-id="c7b12-132">*\[Prohibido\], \[{"status": 403,"source":"","message":"Error del intercambio de tokens: el usuario no puede acceder a la conexión dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], El servidor remoto devolvió un error: (403) Prohibido.*</span><span class="sxs-lookup"><span data-stu-id="c7b12-132">*\[Forbidden\], \[{"status":403,"source":"","message":"Error from token exchange: User is not allowed to access connection dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], The remote server returned an error: (403) Forbidden.*</span></span>

<span data-ttu-id="c7b12-133">Este error ocurre cuando el entorno vinculado Common Data Service no está disponible.</span><span class="sxs-lookup"><span data-stu-id="c7b12-133">This error occurs when the linked Common Data Service environment isn't available.</span></span>

<span data-ttu-id="c7b12-134">Para solucionar el problema, cree un ticket para el equipo de integración de datos.</span><span class="sxs-lookup"><span data-stu-id="c7b12-134">To fix the issue, create a ticket for the Data Integration team.</span></span> <span data-ttu-id="c7b12-135">Adjunte la traza de red para que el equipo de integración de datos pueda marcar los mapas como **No ejecutando** en el back-end.</span><span class="sxs-lookup"><span data-stu-id="c7b12-135">Attach the network trace so that the Data Integration team can mark the maps as **Not running** in the back end.</span></span>

## <a name="error-while-trying-to-start-an-entity-mapping"></a><span data-ttu-id="c7b12-136">Error al intentar iniciar una asignación de entidad</span><span class="sxs-lookup"><span data-stu-id="c7b12-136">Error while trying to start an entity mapping</span></span>

<span data-ttu-id="c7b12-137">Es posible que reciba un error como el siguiente cuando intenta establecer ese estado de una asignación como **En ejecución** :</span><span class="sxs-lookup"><span data-stu-id="c7b12-137">You might receive an error like the following when you try to set that state of a mapping to **Running** :</span></span>

<span data-ttu-id="c7b12-138">*No se puede completar la sincronización de datos inicial. Error: error de doble escritura - error en el registro del complemento: no se pueden construir metadatos de búsqueda de doble escritura. La referencia de objeto de error no está establecida en una instancia de un objeto*.</span><span class="sxs-lookup"><span data-stu-id="c7b12-138">*Unable to complete initial data sync. Error: dual-write failure - plugin registration failed: Unable to build dual-write lookup metadata. Error object reference not set to an instance of an object.*</span></span>

<span data-ttu-id="c7b12-139">La solución para este error depende de la causa del error:</span><span class="sxs-lookup"><span data-stu-id="c7b12-139">The fix for this error depends on the cause of the error:</span></span>

+ <span data-ttu-id="c7b12-140">Si la asignación tiene asignaciones dependientes, asegúrese de habilitar las asignaciones dependientes de esta asignación de entidad.</span><span class="sxs-lookup"><span data-stu-id="c7b12-140">If the mapping has dependent mappings, then make sure to enable the dependent mappings of this entity mapping.</span></span>
+ <span data-ttu-id="c7b12-141">Es posible que falten campos de origen o destino en la asignación.</span><span class="sxs-lookup"><span data-stu-id="c7b12-141">The mapping might be missing source or destination fields.</span></span> <span data-ttu-id="c7b12-142">Si falta un campo en la aplicación de Finance and Operations, siga los pasos de la sección [Problema de campos de entidad faltantes en mapas](dual-write-troubleshooting-finops-upgrades.md#missing-entity-fields-issue-on-maps).</span><span class="sxs-lookup"><span data-stu-id="c7b12-142">If a field in the Finance and Operations app is missing, then follow the steps in the section [Missing entity fields issue on maps](dual-write-troubleshooting-finops-upgrades.md#missing-entity-fields-issue-on-maps).</span></span> <span data-ttu-id="c7b12-143">Si falta un campo en Common Data Service, haga clic en el botón **Actualizar entidades** en la asignación para que los campos se rellenen automáticamente en la asignación.</span><span class="sxs-lookup"><span data-stu-id="c7b12-143">If a field in Common Data Service is missing, then click **Refresh entities** button on the mapping so that the fields are automatically populated back into the mapping.</span></span>
