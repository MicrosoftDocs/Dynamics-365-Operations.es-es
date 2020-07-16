---
title: Implementar un inquilino nuevo de comercio electrónico
description: Este tema describe cómo implementar un inquilino nuevo de comercio electrónico mediante Microsoft Dynamics Lifecycle Services (LCS).
author: psimolin
manager: annbe
ms.date: 07/02/2020
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
ms.openlocfilehash: 00f35b516dbf6ab4d4d9171c84a16b89f6afe832
ms.sourcegitcommit: adf196c51e2b6f532d99c177b4c6778cea8a2efc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/02/2020
ms.locfileid: "3533284"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="c0b53-103">Implementar un inquilino nuevo de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="c0b53-103">Deploy a new e-Commerce tenant</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="c0b53-104">Este tema describe cómo implementar un sitio nuevo de comercio electrónico mediante Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="c0b53-104">This topic describes how to deploy a new e-Commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

## <a name="overview"></a><span data-ttu-id="c0b53-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="c0b53-105">Overview</span></span>

<span data-ttu-id="c0b53-106">Microsoft Dynamics Lifecycle Services (LCS) es un espacio de colaboración basado en la nube que los socios y clientes pueden utilizar para administrar sus proyectos y entornos, ver la información más reciente de los productos y características de Microsoft Dynamics, y crear, realizar un seguimiento y examinar incidentes de soporte.</span><span class="sxs-lookup"><span data-stu-id="c0b53-106">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="c0b53-107">Las características de administración de comercio electrónico están integradas en LCS.</span><span class="sxs-lookup"><span data-stu-id="c0b53-107">E-Commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="c0b53-108">Para obtener más información acerca de LCS, consulte el [Manual del usuario de Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="c0b53-108">To learn more about LCS, see the [Lifecycle Services User Guide](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="c0b53-109">Introducción</span><span class="sxs-lookup"><span data-stu-id="c0b53-109">Get started</span></span>

<span data-ttu-id="c0b53-110">Para poder inicializar el comercio electrónico, debe inicializar un proyecto, un entorno y Retail Cloud Scale Unit (RCSU).</span><span class="sxs-lookup"><span data-stu-id="c0b53-110">Before you can initialize e-Commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="c0b53-111">Para hacer la inicialización en LCS, debe tener permisos para rol Propietario de proyecto o Administrador de entornos.</span><span class="sxs-lookup"><span data-stu-id="c0b53-111">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="c0b53-112">Se admiten las topologías de entorno de espacio aislado y producción.</span><span class="sxs-lookup"><span data-stu-id="c0b53-112">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="c0b53-113">Para obtener más información sobre los entornos, consulte [Planificación de entorno](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="c0b53-113">For more information about environments, see [Environment planning](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="c0b53-114">Para obtener más información acerca de RCSU, consulte [Inicializar Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="c0b53-114">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="c0b53-115">Inicializar comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="c0b53-115">Initialize e-Commerce</span></span>

<span data-ttu-id="c0b53-116">Use este procedimiento para inicializar la característica de comercio electrónico en un entorno existente.</span><span class="sxs-lookup"><span data-stu-id="c0b53-116">Use this procedure to initialize the e-Commerce feature in an existing environment.</span></span>

<span data-ttu-id="c0b53-117">Antes de comenzar, asegúrese de tener la siguiente información necesaria:</span><span class="sxs-lookup"><span data-stu-id="c0b53-117">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="c0b53-118">Se usará la RCSU.</span><span class="sxs-lookup"><span data-stu-id="c0b53-118">The RCSU that will be used.</span></span>
- <span data-ttu-id="c0b53-119">El grupo de seguridad de Microsoft Azure Active Directory que se usará para los administradores del sistema de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="c0b53-119">The Microsoft Azure Active Directory security group that will be used for e-Commerce system admins.</span></span>
- <span data-ttu-id="c0b53-120">El grupo de seguridad de Microsoft Azure Active Directory que se usará para los moderadores de clasificaciones y revisiones.</span><span class="sxs-lookup"><span data-stu-id="c0b53-120">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="c0b53-121">Los dominios que se asociarán al entorno.</span><span class="sxs-lookup"><span data-stu-id="c0b53-121">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="c0b53-122">Además, puede recopilar la siguiente información opcional:</span><span class="sxs-lookup"><span data-stu-id="c0b53-122">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="c0b53-123">información de empresa-consumidor (B2C) de Azure AD:</span><span class="sxs-lookup"><span data-stu-id="c0b53-123">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="c0b53-124">Nombre del inquilino.</span><span class="sxs-lookup"><span data-stu-id="c0b53-124">Tenant Name.</span></span>
    - <span data-ttu-id="c0b53-125">Id. de cliente.</span><span class="sxs-lookup"><span data-stu-id="c0b53-125">Client ID.</span></span>
    - <span data-ttu-id="c0b53-126">Dominio personalizado de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="c0b53-126">Login Custom Domain.</span></span>
    - <span data-ttu-id="c0b53-127">Dirección URL de respuesta.</span><span class="sxs-lookup"><span data-stu-id="c0b53-127">Reply URL.</span></span>
    - <span data-ttu-id="c0b53-128">Id. de directiva de registro e inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="c0b53-128">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="c0b53-129">Id. de directiva de contraseña de restablecimiento.</span><span class="sxs-lookup"><span data-stu-id="c0b53-129">Reset password Policy ID.</span></span>
    - <span data-ttu-id="c0b53-130">Id. de directiva de edición de perfil.</span><span class="sxs-lookup"><span data-stu-id="c0b53-130">Edit Profile Policy ID.</span></span>

> [!NOTE]
> <span data-ttu-id="c0b53-131">Esta información se puede agregar más adelante, con una solicitud de servicio.</span><span class="sxs-lookup"><span data-stu-id="c0b53-131">This information can be added later, through a service request.</span></span>

<span data-ttu-id="c0b53-132">Una vez que haya recopilado la información necesaria, siga estos pasos para inicializar el comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="c0b53-132">After you've collected the required information, follow these steps to initialize e-Commerce.</span></span>

1. <span data-ttu-id="c0b53-133">Inicie sesión en [LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="c0b53-133">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="c0b53-134">Abre el proyecto que contiene el entorno donde desea inicializar el comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="c0b53-134">Open the project that contains the environment where you want to initialize e-Commerce.</span></span>
1. <span data-ttu-id="c0b53-135">En la sección **Entornos**, seleccione el entorno.</span><span class="sxs-lookup"><span data-stu-id="c0b53-135">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="c0b53-136">En **Características del entorno**, seleccione el vínculo **Administración de venta minorista**.</span><span class="sxs-lookup"><span data-stu-id="c0b53-136">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="c0b53-137">En la pestaña **Comercio electrónico**, seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="c0b53-137">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="c0b53-138">Aparece un cuadro de diálogo, donde debe especificar la información necesaria para el aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="c0b53-138">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="c0b53-139">Rellene la información necesaria y, a continuación, vaya a la página siguiente.</span><span class="sxs-lookup"><span data-stu-id="c0b53-139">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="c0b53-140">En la página siguiente, rellene la información necesaria y, a continuación, envíe el formulario.</span><span class="sxs-lookup"><span data-stu-id="c0b53-140">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="c0b53-141">Se le devolverá a la pestaña **Comercio electrónico**, donde debería ver que se ha iniciado la inicialización.</span><span class="sxs-lookup"><span data-stu-id="c0b53-141">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="c0b53-142">Para ver el estado de la inicialización, elija **Actualizar** o vuelva a la pestaña **Comercio electrónico** más adelante.</span><span class="sxs-lookup"><span data-stu-id="c0b53-142">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="c0b53-143">Cuando el comercio electrónico se inicializa desde LCS, el sistema aprovisiona varios componentes necesarios para el comercio electrónico y los asocia al entorno.</span><span class="sxs-lookup"><span data-stu-id="c0b53-143">When e-Commerce is initialized from LCS, the system provisions several components that are required for e-Commerce and associates them with the environment.</span></span> <span data-ttu-id="c0b53-144">Una vez que se completa el aprovisionamiento, se actualizará la pestaña **Comercio electrónico** de la página **Administración de Retail** para reflejar el aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="c0b53-144">After provisioning is complete, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="c0b53-145">La página muestra las últimas implementaciones de personalización y el estado de cualquier otra implementación en curso.</span><span class="sxs-lookup"><span data-stu-id="c0b53-145">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="c0b53-146">También incluye vínculos al sitio de comercio electrónico y al generador de sitios de comercio electrónico donde se crean los sitios.</span><span class="sxs-lookup"><span data-stu-id="c0b53-146">It also includes links to the e-Commerce site and the e-Commerce site builder where sites are authored.</span></span>

## <a name="access-site-builder"></a><span data-ttu-id="c0b53-147">Acceder al generador de sitios</span><span class="sxs-lookup"><span data-stu-id="c0b53-147">Access site builder</span></span>

<span data-ttu-id="c0b53-148">Para acceder al generador de sitios, vaya a la pestaña **Comercio electrónico** en la página **Gestión de ventas** en LCS y seleccione el vínculo **herramienta de gestión de sitios de comercio electrónico**.</span><span class="sxs-lookup"><span data-stu-id="c0b53-148">To access site builder, go to the **e-Commerce** tab on the **Retail management** page in LCS and select the **e-Commerce site management tool** link.</span></span> <span data-ttu-id="c0b53-149">La página de aterrizaje del generador de sitios muestra una vista de nivel de suscriptor.</span><span class="sxs-lookup"><span data-stu-id="c0b53-149">The site builder landing page displays a tenant-level view.</span></span> <span data-ttu-id="c0b53-150">En esta página puede:</span><span class="sxs-lookup"><span data-stu-id="c0b53-150">From this page, you can:</span></span>

- <span data-ttu-id="c0b53-151">Modificar la configuración de nivel de suscriptor.</span><span class="sxs-lookup"><span data-stu-id="c0b53-151">Modify tenant-level settings.</span></span>
- <span data-ttu-id="c0b53-152">Navegar a cualquier sitio que haya creado y tenga permiso para ver.</span><span class="sxs-lookup"><span data-stu-id="c0b53-152">Navigate to any site you have created, and have permission to view.</span></span> 
- <span data-ttu-id="c0b53-153">Acceder a las funciones de Revisiones, como moderación e informes.</span><span class="sxs-lookup"><span data-stu-id="c0b53-153">Access Reviews features such as moderation and reporting.</span></span>
- <span data-ttu-id="c0b53-154">Crear un nuevo sitio.</span><span class="sxs-lookup"><span data-stu-id="c0b53-154">Create a new site.</span></span> <span data-ttu-id="c0b53-155">Para obtener más información acerca de cómo crear un sitio nuevo, consulte [Crear un sitio de comercio electrónico](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="c0b53-155">For more information about how to create a new site, see [Create an e-Commerce site](create-ecommerce-site.md) .</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="c0b53-156">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c0b53-156">Additional resources</span></span>

[<span data-ttu-id="c0b53-157">Configurar su nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="c0b53-157">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="c0b53-158">Crear un sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="c0b53-158">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="c0b53-159">Asociar un sitio en línea con un canal</span><span class="sxs-lookup"><span data-stu-id="c0b53-159">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="c0b53-160">Administrar archivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="c0b53-160">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="c0b53-161">Subir redireccionamientos de URL en grandes cantidades</span><span class="sxs-lookup"><span data-stu-id="c0b53-161">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="c0b53-162">Configurar un inquilino B2C en Commerce</span><span class="sxs-lookup"><span data-stu-id="c0b53-162">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="c0b53-163">Configurar páginas personalizadas para inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="c0b53-163">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="c0b53-164">Configurar múltiples inquilinos B2C en un entorno de Commerce</span><span class="sxs-lookup"><span data-stu-id="c0b53-164">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="c0b53-165">Agregar soporte para una red de entrega de contenido (CDN)</span><span class="sxs-lookup"><span data-stu-id="c0b53-165">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="c0b53-166">Habilitar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="c0b53-166">Enable location-based store detection</span></span>](enable-store-detection.md)
