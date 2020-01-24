---
title: Implementar un inquilino nuevo de comercio electrónico
description: Este tema describe cómo implementar un inquilino nuevo de comercio electrónico mediante Microsoft Dynamics Lifecycle Services (LCS).
author: psimolin
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 10dab1e62446ff7f60ad48fd0841bde5cfd29e12
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "2945522"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="5f2bb-103">Implementar un inquilino nuevo de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="5f2bb-103">Deploy a new e-Commerce tenant</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="5f2bb-104">Este tema describe cómo implementar un sitio nuevo de comercio electrónico mediante Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="5f2bb-104">This topic describes how to deploy a new e-Commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="overview"></a><span data-ttu-id="5f2bb-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="5f2bb-105">Overview</span></span>
    
<span data-ttu-id="5f2bb-106">Microsoft Dynamics Lifecycle Services (LCS) es un espacio de colaboración basado en la nube que los socios y clientes pueden utilizar para administrar sus proyectos y entornos, ver la información más reciente de los productos y características de Microsoft Dynamics, y crear, realizar un seguimiento y examinar incidentes de soporte.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-106">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="5f2bb-107">Las características de administración de comercio electrónico están integradas en LCS.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-107">E-Commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="5f2bb-108">Para obtener más información acerca de LCS, consulte el [Manual del usuario de Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="5f2bb-108">To learn more about LCS, see the [Lifecycle Services User Guide](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="5f2bb-109">Introducción</span><span class="sxs-lookup"><span data-stu-id="5f2bb-109">Get started</span></span>

<span data-ttu-id="5f2bb-110">Para poder inicializar el comercio electrónico, debe inicializar un proyecto, un entorno y Retail Cloud Scale Unit (RCSU).</span><span class="sxs-lookup"><span data-stu-id="5f2bb-110">Before you can initialize e-Commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="5f2bb-111">Para hacer la inicialización en LCS, debe tener permisos para rol Propietario de proyecto o Administrador de entornos.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-111">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="5f2bb-112">Se admiten las topologías de entorno de espacio aislado y producción.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-112">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="5f2bb-113">Para obtener más información sobre los entornos, consulte [Planificación de entorno](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="5f2bb-113">For more information about environments, see [Environment planning](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="5f2bb-114">Para obtener más información acerca de RCSU, consulte [Inicializar Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="5f2bb-114">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="5f2bb-115">Inicializar comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="5f2bb-115">Initialize e-Commerce</span></span>

<span data-ttu-id="5f2bb-116">Use este procedimiento para inicializar la característica de comercio electrónico en un entorno existente.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-116">Use this procedure to initialize the e-Commerce feature in an existing environment.</span></span>

<span data-ttu-id="5f2bb-117">Antes de comenzar, asegúrese de tener la siguiente información necesaria:</span><span class="sxs-lookup"><span data-stu-id="5f2bb-117">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="5f2bb-118">Se usará la RCSU.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-118">The RCSU that will be used.</span></span>
- <span data-ttu-id="5f2bb-119">El grupo de seguridad de Microsoft Azure Active Directory que se usará para los administradores del sistema de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-119">The Microsoft Azure Active Directory security group that will be used for e-Commerce system admins.</span></span>
- <span data-ttu-id="5f2bb-120">El grupo de seguridad de Microsoft Azure Active Directory que se usará para los moderadores de clasificaciones y revisiones.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-120">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="5f2bb-121">Los dominios que se asociarán al entorno.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-121">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="5f2bb-122">Además, puede recopilar la siguiente información opcional:</span><span class="sxs-lookup"><span data-stu-id="5f2bb-122">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="5f2bb-123">información de empresa-consumidor (B2C) de Azure AD:</span><span class="sxs-lookup"><span data-stu-id="5f2bb-123">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="5f2bb-124">Nombre del inquilino.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-124">Tenant Name.</span></span>
    - <span data-ttu-id="5f2bb-125">Id. de cliente.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-125">Client ID.</span></span>
    - <span data-ttu-id="5f2bb-126">Dominio personalizado de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-126">Login Custom Domain.</span></span>
    - <span data-ttu-id="5f2bb-127">Dirección URL de respuesta.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-127">Reply URL.</span></span>
    - <span data-ttu-id="5f2bb-128">Id. de directiva de inicio de sesión de suscripción.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-128">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="5f2bb-129">Id. de directiva de contraseña de restablecimiento.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-129">Reset password Policy ID.</span></span>
    - <span data-ttu-id="5f2bb-130">Editar id. de directiva de perfil.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-130">Edit Profile Policy ID.</span></span>

[!NOTE]
<span data-ttu-id="5f2bb-131">Esta información se puede agregar más adelante, con una solicitud de servicio.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-131">This information can be added later, through a service request.</span></span>

<span data-ttu-id="5f2bb-132">Una vez que haya recopilado la información necesaria, siga estos pasos para inicializar el comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-132">After you've collected the required information, follow these steps to initialize e-Commerce.</span></span>

1. <span data-ttu-id="5f2bb-133">Inicie sesión en [LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="5f2bb-133">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="5f2bb-134">Abre el proyecto que contiene el entorno donde desea inicializar el comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-134">Open the project that contains the environment where you want to initialize e-Commerce.</span></span>
1. <span data-ttu-id="5f2bb-135">En la sección **Entornos**, seleccione el entorno.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-135">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="5f2bb-136">En **Características del entorno**, seleccione el vínculo **Administración de venta minorista**.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-136">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="5f2bb-137">En la pestaña **Comercio electrónico**, seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-137">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="5f2bb-138">Aparece un cuadro de diálogo, donde debe especificar la información necesaria para el aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-138">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="5f2bb-139">Rellene la información necesaria y, a continuación, vaya a la página siguiente.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-139">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="5f2bb-140">En la página siguiente, rellene la información necesaria y, a continuación, envíe el formulario.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-140">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="5f2bb-141">Se le devolverá a la pestaña **Comercio electrónico**, donde debería ver que se ha iniciado la inicialización.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-141">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="5f2bb-142">Para ver el estado de la inicialización, elija **Actualizar** o vuelva a la pestaña **Comercio electrónico** más adelante.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-142">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="5f2bb-143">Cuando el comercio electrónico se inicializa desde LCS, el sistema aprovisiona varios componentes necesarios para el comercio electrónico y los asocia al entorno.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-143">When e-Commerce is initialized from LCS, the system provisions several components that are required for e-Commerce and associates them with the environment.</span></span> <span data-ttu-id="5f2bb-144">Una vez que se completa el aprovisionamiento, se actualizará la pestaña **Comercio electrónico** de la página **Administración de Retail** para reflejar el aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-144">After provisioning is completed, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="5f2bb-145">La página muestra las últimas implementaciones de personalización y el estado de cualquier otra implementación en curso.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-145">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="5f2bb-146">También incluye vínculos al sitio de comercio electrónico y la herramienta de administración del sitio de comercio electrónico (la herramienta de creación).</span><span class="sxs-lookup"><span data-stu-id="5f2bb-146">It also includes links to the e-Commerce site and the e-Commerce site management tool (the authoring tool).</span></span>

## <a name="access-the-authoring-environment"></a><span data-ttu-id="5f2bb-147">Acceso al entorno de creación</span><span class="sxs-lookup"><span data-stu-id="5f2bb-147">Access the authoring environment</span></span>

<span data-ttu-id="5f2bb-148">Para obtener acceso al entorno de creación, vaya a la pestaña **Comercio electrónico** de la página **Administración de Retail**.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-148">To access the authoring environment, go to the **e-Commerce** tab on the **Retail management** page.</span></span> <span data-ttu-id="5f2bb-149">Aquí, encontrará vínculos al sitio de comercio electrónico y la herramienta de administración del sitio.</span><span class="sxs-lookup"><span data-stu-id="5f2bb-149">There, you will find links to your e-Commerce site and the site management tool.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5f2bb-150">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5f2bb-150">Additional resources</span></span>

[<span data-ttu-id="5f2bb-151">Configurar su nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="5f2bb-151">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="5f2bb-152">Crear un sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="5f2bb-152">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="5f2bb-153">Asociar un sitio en línea con un canal</span><span class="sxs-lookup"><span data-stu-id="5f2bb-153">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="5f2bb-154">Administrar archivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="5f2bb-154">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="5f2bb-155">Configurar páginas personalizadas para inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="5f2bb-155">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="5f2bb-156">Agregar soporte para una red de entrega de contenido (CDN)</span><span class="sxs-lookup"><span data-stu-id="5f2bb-156">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="5f2bb-157">Habilitar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="5f2bb-157">Enable location-based store detection</span></span>](enable-store-detection.md)
