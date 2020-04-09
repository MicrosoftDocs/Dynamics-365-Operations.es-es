---
title: Solucione problemas con el módulo de doble escritura en aplicaciones Finance and Operations
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 34c10e38400a72a670a93f2a72d0aa7a4aed561a
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/27/2020
ms.locfileid: "3172769"
---
# <a name="troubleshoot-issues-with-the-dual-write-module-in-finance-and-operations-apps"></a><span data-ttu-id="4efcb-103">Solucione problemas con el módulo de doble escritura en aplicaciones Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4efcb-103">Troubleshoot issues with the Dual-write module in Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="4efcb-104">Este tema proporciona información para solución de problemas de integración de escritura doble entre las aplicaciones de Finance and Operations y Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="4efcb-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="4efcb-105">Específicamente, proporciona información que puede ayudarlo a solucionar problemas con el módulo de **Escritura doble** en aplicaciones Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="4efcb-105">Specifically, it provides information that can help you fix issues with the **Dual-write** module in Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4efcb-106">Algunos de los problemas que aborda este tema pueden requerir la función de administrador del sistema o Microsoft Azure Active Directory (Azure AD) credenciales de administrador de inquilinos.</span><span class="sxs-lookup"><span data-stu-id="4efcb-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="4efcb-107">La sección para cada problema explica si se requiere una función o credenciales específicas.</span><span class="sxs-lookup"><span data-stu-id="4efcb-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-load-the-dual-write-module-in-a-finance-and-operations-app"></a><span data-ttu-id="4efcb-108">No puede cargar el módulo de doble escritura en una aplicación Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="4efcb-108">You can't load the Dual-write module in a Finance and Operations app</span></span>

<span data-ttu-id="4efcb-109">Si no puede abrir la página **Doble escritura** seleccionando el mosaico **Doble escritura** en el espacio de trabajo **Gestión de datos**, el servicio de integración de datos probablemente esté inactivo.</span><span class="sxs-lookup"><span data-stu-id="4efcb-109">If you can't open the **Dual-write** page by selecting the **Dual Write** tile in the **Data management** workspace, the data integration service is probably down.</span></span> <span data-ttu-id="4efcb-110">Cree un ticket de soporte para solicitar un reinicio del servicio de integración de datos.</span><span class="sxs-lookup"><span data-stu-id="4efcb-110">Create a support ticket to request a restart of the data integration service.</span></span>

## <a name="error-when-you-try-to-create-a-new-entity-mapping"></a><span data-ttu-id="4efcb-111">Error al intentar crear una nueva asignación de entidad</span><span class="sxs-lookup"><span data-stu-id="4efcb-111">Error when you try to create a new entity mapping</span></span>

<span data-ttu-id="4efcb-112">**Credenciales requeridas para arreglar el problema:** Administrador de inquilinos Azure AD</span><span class="sxs-lookup"><span data-stu-id="4efcb-112">**Required credentials to fix the issue:** Azure AD tenant admin</span></span>

<span data-ttu-id="4efcb-113">Es posible que reciba el siguiente mensaje de error cuando intente configurar una nueva entidad para doble escritura:</span><span class="sxs-lookup"><span data-stu-id="4efcb-113">You might receive the following error message when you try to configure a new entity for dual-write:</span></span>

<span data-ttu-id="4efcb-114">*El código de estado de respuesta no indica éxito: 401 (No autorizado)*</span><span class="sxs-lookup"><span data-stu-id="4efcb-114">*Response status code does not indicate success: 401 (Unauthorized)*</span></span>

<span data-ttu-id="4efcb-115">Este error ocurre porque solo un administrador de inquilino Azure AD puede agregar una nueva asignación de entidad.</span><span class="sxs-lookup"><span data-stu-id="4efcb-115">This error occurs because only an Azure AD tenant admin can add a new entity mapping.</span></span>

<span data-ttu-id="4efcb-116">Para solucionar el problema, inicie sesión en aplicaciones Finance and Operations como inquilino administrador Azure AD.</span><span class="sxs-lookup"><span data-stu-id="4efcb-116">To fix the issue, sign in to the Finance and Operations app as an Azure AD admin tenant.</span></span> <span data-ttu-id="4efcb-117">También debe ir a web.PowerApps.com y revalidar su conexión.</span><span class="sxs-lookup"><span data-stu-id="4efcb-117">You must also go to web.PowerApps.com and revalidate your connection.</span></span>

## <a name="error-when-you-open-the-dual-write-user-interface"></a><span data-ttu-id="4efcb-118">Error al abrir la interfaz de usuario de doble escritura</span><span class="sxs-lookup"><span data-stu-id="4efcb-118">Error when you open the dual-write user interface</span></span>

<span data-ttu-id="4efcb-119">Es posible que reciba el siguiente mensaje de error cuando intente acceder a la escritura doble desde el espacio de trabajo **Gestión de datos**:</span><span class="sxs-lookup"><span data-stu-id="4efcb-119">You might receive the following error message when you try to access dual-write from the **Data management** workspace:</span></span>

<span data-ttu-id="4efcb-120">*login.microsoftonline.com se negó a conectarse.*</span><span class="sxs-lookup"><span data-stu-id="4efcb-120">*login.microsoftonline.com refused to connect.*</span></span>

<span data-ttu-id="4efcb-121">Para solucionar el problema, inicie sesión utilizando una ventana InPrivate en Microsoft Edge, una ventana de incógnito en Chromium o una ventana de incógnito en Google Chrome.</span><span class="sxs-lookup"><span data-stu-id="4efcb-121">To fix the issue, sign in by using an InPrivate window in Microsoft Edge, an incognito window in Chromium, or an incognito window in Google Chrome.</span></span> <span data-ttu-id="4efcb-122">También debe desbloquear o borrar las cookies de terceros.</span><span class="sxs-lookup"><span data-stu-id="4efcb-122">You must also unblock or clear third-party cookies.</span></span>

## <a name="error-when-you-link-the-environment-for-dual-write-or-add-a-new-entity-mapping"></a><span data-ttu-id="4efcb-123">Error al vincular el entorno para doble escritura o agregar una nueva asignación de entidad</span><span class="sxs-lookup"><span data-stu-id="4efcb-123">Error when you link the environment for dual-write or add a new entity mapping</span></span>

<span data-ttu-id="4efcb-124">**Credenciales requeridas para arreglar el problema:** Administrador de inquilinos Azure AD</span><span class="sxs-lookup"><span data-stu-id="4efcb-124">**Required credentials to fix the issue:** Azure AD tenant admin</span></span>

<span data-ttu-id="4efcb-125">Puede encontrar el siguiente error al vincular o crear mapas:</span><span class="sxs-lookup"><span data-stu-id="4efcb-125">You might encounter the following error when linking or creating maps:</span></span>

<span data-ttu-id="4efcb-126">*El código de estado de respuesta no indica éxito: 403 (tokenexchange).<br> ID de sesión: \<su id de sesión\><br> ID de actividad raíz: \<su id de actividad raíz\>*</span><span class="sxs-lookup"><span data-stu-id="4efcb-126">*Response status code does not indicate success: 403 (tokenexchange).<br> Session ID: \<your session id\><br> Root activity ID: \<your root activity id\>*</span></span>

<span data-ttu-id="4efcb-127">Este error puede ocurrir si no tiene permisos suficientes para vincular escritura doble o crear mapas.</span><span class="sxs-lookup"><span data-stu-id="4efcb-127">This error can occur if you don't have sufficient permissions to link dual-write or create maps.</span></span> <span data-ttu-id="4efcb-128">Debes usar una cuenta de administrador de inquilinos de Azure AD para vincular entornos y agregar nuevas asignaciones de entidades.</span><span class="sxs-lookup"><span data-stu-id="4efcb-128">You must use an Azure AD tenant admin account to link environments and add new entity mappings.</span></span> <span data-ttu-id="4efcb-129">Sin embargo, después de la configuración, puede usar una cuenta que no sea de administrador para seguir el estado y editar las asignaciones.</span><span class="sxs-lookup"><span data-stu-id="4efcb-129">However, after setup, you can use a non-admin account to monitor status and edit the mappings.</span></span>

## <a name="error-when-you-stop-the-entity-mapping"></a><span data-ttu-id="4efcb-130">Error al detener la asignación de entidad</span><span class="sxs-lookup"><span data-stu-id="4efcb-130">Error when you stop the entity mapping</span></span>

<span data-ttu-id="4efcb-131">Es posible que reciba el siguiente mensaje de error cuando intenta detener las asignaciones de entidad:</span><span class="sxs-lookup"><span data-stu-id="4efcb-131">You might receive the following error message when you try to stop the entity mappings:</span></span>

<span data-ttu-id="4efcb-132">*\[Prohibido\], \[{"status": 403,"source":"","message":"Error del intercambio de tokens: el usuario no puede acceder a la conexión dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], El servidor remoto devolvió un error: (403) Prohibido.*</span><span class="sxs-lookup"><span data-stu-id="4efcb-132">*\[Forbidden\], \[{"status":403,"source":"","message":"Error from token exchange: User is not allowed to access connection dynamicscrmonline/xxxxxx-xxxx-xxxx-xxxxxxxx"}\], The remote server returned an error: (403) Forbidden.*</span></span>

<span data-ttu-id="4efcb-133">Este error ocurre cuando el entorno vinculado Common Data Service no está disponible.</span><span class="sxs-lookup"><span data-stu-id="4efcb-133">This error occurs when the linked Common Data Service environment isn't available.</span></span>

<span data-ttu-id="4efcb-134">Para solucionar el problema, cree un ticket para el equipo de integración de datos.</span><span class="sxs-lookup"><span data-stu-id="4efcb-134">To fix the issue, create a ticket for the Data Integration team.</span></span> <span data-ttu-id="4efcb-135">Adjunte la traza de red para que el equipo de integración de datos pueda marcar los mapas como **No ejecutando** en el back-end.</span><span class="sxs-lookup"><span data-stu-id="4efcb-135">Attach the network trace so that the Data Integration team can mark the maps as **Not running** in the back end.</span></span>
