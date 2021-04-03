---
title: Implementar un inquilino nuevo de comercio electrónico
description: Este tema describe cómo implementar un sitio nuevo de comercio electrónico de Dynamics 365 Commerce mediante Microsoft Dynamics Lifecycle Services (LCS).
author: psimolin
manager: annbe
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d31e3e7248809a00ad51183b80205d1351567ab3
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477885"
---
# <a name="deploy-a-new-e-commerce-tenant"></a><span data-ttu-id="69355-103">Implementar un inquilino nuevo de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="69355-103">Deploy a new e-commerce tenant</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="69355-104">Este tema describe cómo implementar un sitio nuevo de comercio electrónico de Dynamics 365 Commerce mediante Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="69355-104">This topic describes how to deploy a new Dynamics 365 Commerce e-commerce site by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="69355-105">Microsoft Dynamics Lifecycle Services (LCS) es un espacio de colaboración basado en la nube que los socios y clientes pueden utilizar para administrar sus proyectos y entornos, ver la información más reciente de los productos y características de Microsoft Dynamics, y crear, realizar un seguimiento y examinar incidentes de soporte.</span><span class="sxs-lookup"><span data-stu-id="69355-105">Microsoft Dynamics Lifecycle Services (LCS) is a cloud-based collaborative workspace that partners and customers can use to manage their projects and environments, view the latest information about Microsoft Dynamics products and features, and create, track, and browse support incidents.</span></span> <span data-ttu-id="69355-106">Las características de administración de comercio electrónico están integradas en LCS.</span><span class="sxs-lookup"><span data-stu-id="69355-106">E-commerce management features are integrated into LCS.</span></span>

<span data-ttu-id="69355-107">Para obtener más información acerca de LCS, consulte el [Manual del usuario de Lifecycle Services](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span><span class="sxs-lookup"><span data-stu-id="69355-107">To learn more about LCS, see the [Lifecycle Services User Guide](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide).</span></span>
    
## <a name="get-started"></a><span data-ttu-id="69355-108">Introducción</span><span class="sxs-lookup"><span data-stu-id="69355-108">Get started</span></span>

<span data-ttu-id="69355-109">Para poder inicializar el comercio electrónico, debe inicializar un proyecto, un entorno y Retail Cloud Scale Unit (RCSU).</span><span class="sxs-lookup"><span data-stu-id="69355-109">Before you can initialize e-commerce, you must initialize a project, an environment, and a Retail Cloud Scale Unit (RCSU).</span></span> <span data-ttu-id="69355-110">Para hacer la inicialización en LCS, debe tener permisos para rol Propietario de proyecto o Administrador de entornos.</span><span class="sxs-lookup"><span data-stu-id="69355-110">To do the initialization in LCS, you must have permissions for either the Project Owner or Environment manager role.</span></span> <span data-ttu-id="69355-111">Se admiten las topologías de entorno de espacio aislado y producción.</span><span class="sxs-lookup"><span data-stu-id="69355-111">The production and sandbox environment topologies are supported.</span></span>

<span data-ttu-id="69355-112">Para obtener más información sobre los entornos, consulte [Planificación de entorno](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span><span class="sxs-lookup"><span data-stu-id="69355-112">For more information about environments, see [Environment planning](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/imp-lifecycle/environment-planning).</span></span> <span data-ttu-id="69355-113">Para obtener más información acerca de RCSU, consulte [Inicializar Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span><span class="sxs-lookup"><span data-stu-id="69355-113">For more information about RCSU, see [Initialize Retail Cloud Scale Unit](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/deployment/initialize-retail-channels).</span></span>

## <a name="initialize-e-commerce"></a><span data-ttu-id="69355-114">Inicializar comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="69355-114">Initialize e-commerce</span></span>

<span data-ttu-id="69355-115">Use este procedimiento para inicializar la característica de comercio electrónico en un entorno existente.</span><span class="sxs-lookup"><span data-stu-id="69355-115">Use this procedure to initialize the e-commerce feature in an existing environment.</span></span>

<span data-ttu-id="69355-116">Antes de comenzar, asegúrese de tener la siguiente información necesaria:</span><span class="sxs-lookup"><span data-stu-id="69355-116">Before you begin, make sure that you have the following required information:</span></span>

- <span data-ttu-id="69355-117">Se usará la RCSU.</span><span class="sxs-lookup"><span data-stu-id="69355-117">The RCSU that will be used.</span></span>
- <span data-ttu-id="69355-118">El grupo de seguridad de Microsoft Azure Active Directory que se usará para los administradores del sistema de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="69355-118">The Microsoft Azure Active Directory security group that will be used for e-commerce system admins.</span></span>
- <span data-ttu-id="69355-119">El grupo de seguridad de Microsoft Azure Active Directory que se usará para los moderadores de clasificaciones y revisiones.</span><span class="sxs-lookup"><span data-stu-id="69355-119">The Microsoft Azure Active Directory security group that will be used for ratings and reviews moderators.</span></span>
- <span data-ttu-id="69355-120">Los dominios que se asociarán al entorno.</span><span class="sxs-lookup"><span data-stu-id="69355-120">The domains that will be associated with the environment.</span></span>

<span data-ttu-id="69355-121">Además, puede recopilar la siguiente información opcional:</span><span class="sxs-lookup"><span data-stu-id="69355-121">In addition, you can collect the following optional information:</span></span>

- <span data-ttu-id="69355-122">información de empresa-consumidor (B2C) de Azure AD:</span><span class="sxs-lookup"><span data-stu-id="69355-122">Azure AD business-to-consumer (B2C) information:</span></span>

    - <span data-ttu-id="69355-123">Nombre del inquilino.</span><span class="sxs-lookup"><span data-stu-id="69355-123">Tenant Name.</span></span>
    - <span data-ttu-id="69355-124">Id. de cliente.</span><span class="sxs-lookup"><span data-stu-id="69355-124">Client ID.</span></span>
    - <span data-ttu-id="69355-125">Dominio personalizado de inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="69355-125">Login Custom Domain.</span></span>
    - <span data-ttu-id="69355-126">Dirección URL de respuesta.</span><span class="sxs-lookup"><span data-stu-id="69355-126">Reply URL.</span></span>
    - <span data-ttu-id="69355-127">Id. de directiva de registro e inicio de sesión.</span><span class="sxs-lookup"><span data-stu-id="69355-127">SignUp SignIn Policy ID.</span></span>
    - <span data-ttu-id="69355-128">Id. de directiva de contraseña de restablecimiento.</span><span class="sxs-lookup"><span data-stu-id="69355-128">Reset password Policy ID.</span></span>
    - <span data-ttu-id="69355-129">Id. de directiva de edición de perfil.</span><span class="sxs-lookup"><span data-stu-id="69355-129">Edit Profile Policy ID.</span></span>

> [!NOTE]
> <span data-ttu-id="69355-130">Esta información se puede agregar más adelante, con una solicitud de servicio.</span><span class="sxs-lookup"><span data-stu-id="69355-130">This information can be added later, through a service request.</span></span>

<span data-ttu-id="69355-131">Una vez que haya recopilado la información necesaria, siga estos pasos para inicializar el comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="69355-131">After you've collected the required information, follow these steps to initialize e-commerce.</span></span>

1. <span data-ttu-id="69355-132">Inicie sesión en [LCS](https://lcs.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="69355-132">Sign in to [LCS](https://lcs.dynamics.com).</span></span>
1. <span data-ttu-id="69355-133">Abre el proyecto que contiene el entorno donde desea inicializar el comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="69355-133">Open the project that contains the environment where you want to initialize e-commerce.</span></span>
1. <span data-ttu-id="69355-134">En la sección **Entornos**, seleccione el entorno.</span><span class="sxs-lookup"><span data-stu-id="69355-134">In the **Environments** section, select the environment.</span></span>
1. <span data-ttu-id="69355-135">En **Características del entorno**, seleccione el vínculo **Administración de venta minorista**.</span><span class="sxs-lookup"><span data-stu-id="69355-135">Under **Environment features**, select the **Retail manage** link.</span></span>
1. <span data-ttu-id="69355-136">En la pestaña **Comercio electrónico**, seleccione **Configuración**.</span><span class="sxs-lookup"><span data-stu-id="69355-136">On the **e-Commerce** tab, select **Setup**.</span></span> <span data-ttu-id="69355-137">Aparece un cuadro de diálogo, donde debe especificar la información necesaria para el aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="69355-137">A dialog box appears, where you must enter the information that is required for provisioning.</span></span>
1. <span data-ttu-id="69355-138">Rellene la información necesaria y, a continuación, vaya a la página siguiente.</span><span class="sxs-lookup"><span data-stu-id="69355-138">Fill in the required information, and then go to the next page.</span></span>
1. <span data-ttu-id="69355-139">En la página siguiente, rellene la información necesaria y, a continuación, envíe el formulario.</span><span class="sxs-lookup"><span data-stu-id="69355-139">On the next page, fill in the required information, and then submit the form.</span></span> <span data-ttu-id="69355-140">Se le devolverá a la pestaña **Comercio electrónico**, donde debería ver que se ha iniciado la inicialización.</span><span class="sxs-lookup"><span data-stu-id="69355-140">You're returned to the **e-Commerce** tab, where you should see that initialization has been started.</span></span>
1. <span data-ttu-id="69355-141">Para ver el estado de la inicialización, elija **Actualizar** o vuelva a la pestaña **Comercio electrónico** más adelante.</span><span class="sxs-lookup"><span data-stu-id="69355-141">To view the initialization status, either **Refresh** or return to the **e-Commerce** tab later.</span></span>
    
<span data-ttu-id="69355-142">Cuando el comercio electrónico se inicializa desde LCS, el sistema aprovisiona varios componentes necesarios para el comercio electrónico y los asocia al entorno.</span><span class="sxs-lookup"><span data-stu-id="69355-142">When e-commerce is initialized from LCS, the system provisions several components that are required for e-commerce and associates them with the environment.</span></span> <span data-ttu-id="69355-143">Una vez que se completa el aprovisionamiento, se actualizará la pestaña **Comercio electrónico** de la página **Administración de Retail** para reflejar el aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="69355-143">After provisioning is complete, the **e-Commerce** tab on the **Retail management** page is updated to reflect the provisioning.</span></span> <span data-ttu-id="69355-144">La página muestra las últimas implementaciones de personalización y el estado de cualquier otra implementación en curso.</span><span class="sxs-lookup"><span data-stu-id="69355-144">The page shows the latest customization deployments and the status of any other ongoing deployments.</span></span> <span data-ttu-id="69355-145">También incluye vínculos al sitio de comercio electrónico y al generador de sitios de comercio electrónico donde se crean los sitios.</span><span class="sxs-lookup"><span data-stu-id="69355-145">It also includes links to the e-commerce site and the Commerce site builder where sites are authored.</span></span>

## <a name="access-commerce-site-builder"></a><span data-ttu-id="69355-146">Acceder al generador de sitios de Commerce</span><span class="sxs-lookup"><span data-stu-id="69355-146">Access Commerce site builder</span></span>

<span data-ttu-id="69355-147">Para acceder al generador de sitios de Commerce, vaya a la pestaña **Comercio electrónico** en la página **Gestión de ventas** en LCS y seleccione el vínculo **herramienta de gestión de sitios de comercio electrónico**.</span><span class="sxs-lookup"><span data-stu-id="69355-147">To access Commerce site builder, go to the **e-Commerce** tab on the **Retail management** page in LCS and select the **e-Commerce site management tool** link.</span></span> <span data-ttu-id="69355-148">La página de aterrizaje del generador de sitios muestra una vista de nivel de suscriptor.</span><span class="sxs-lookup"><span data-stu-id="69355-148">The site builder landing page displays a tenant-level view.</span></span> <span data-ttu-id="69355-149">En esta página puede:</span><span class="sxs-lookup"><span data-stu-id="69355-149">From this page, you can:</span></span>

- <span data-ttu-id="69355-150">Modificar la configuración de nivel de suscriptor.</span><span class="sxs-lookup"><span data-stu-id="69355-150">Modify tenant-level settings.</span></span>
- <span data-ttu-id="69355-151">Navegar a cualquier sitio que haya creado y tenga permiso para ver.</span><span class="sxs-lookup"><span data-stu-id="69355-151">Navigate to any site you have created, and have permission to view.</span></span> 
- <span data-ttu-id="69355-152">Acceder a las funciones de Revisiones, como moderación e informes.</span><span class="sxs-lookup"><span data-stu-id="69355-152">Access Reviews features such as moderation and reporting.</span></span>
- <span data-ttu-id="69355-153">Crear un nuevo sitio.</span><span class="sxs-lookup"><span data-stu-id="69355-153">Create a new site.</span></span> <span data-ttu-id="69355-154">Para obtener más información acerca de cómo crear un sitio nuevo, consulte [Crear un sitio de comercio electrónico](create-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="69355-154">For more information about how to create a new site, see [Create an e-commerce site](create-ecommerce-site.md) .</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="69355-155">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="69355-155">Additional resources</span></span>

[<span data-ttu-id="69355-156">Configurar su nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="69355-156">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="69355-157">Crear un sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="69355-157">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="69355-158">Asociar un sitio de Dynamics 365 Commerce con un canal en línea</span><span class="sxs-lookup"><span data-stu-id="69355-158">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="69355-159">Administrar archivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="69355-159">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="69355-160">Subir redireccionamientos de URL en grandes cantidades</span><span class="sxs-lookup"><span data-stu-id="69355-160">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="69355-161">Configurar un inquilino B2C en Commerce</span><span class="sxs-lookup"><span data-stu-id="69355-161">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="69355-162">Configurar páginas personalizadas para inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="69355-162">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="69355-163">Configurar múltiples inquilinos B2C en un entorno de Commerce</span><span class="sxs-lookup"><span data-stu-id="69355-163">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="69355-164">Agregar soporte para una red de entrega de contenido (CDN)</span><span class="sxs-lookup"><span data-stu-id="69355-164">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="69355-165">Habilitar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="69355-165">Enable location-based store detection</span></span>](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
