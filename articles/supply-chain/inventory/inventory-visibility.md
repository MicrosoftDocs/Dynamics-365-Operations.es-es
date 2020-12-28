---
title: Complemento de visibilidad de inventario
description: Este tema describe cómo instalar y configurar el complemento de visibilidad de inventario para Dynamics 365 Supply Chain Management.
author: chuzheng
manager: tfehr
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 2976153a6a7e4b4130e8f7673ed128945aeabf65
ms.sourcegitcommit: 03c2e1717b31e4c17ee7bb9004d2ba8cf379a036
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "4625074"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="3ab74-103">Complemento de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="3ab74-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="3ab74-104">El complemento de visibilidad de inventario es un microservicio independiente y altamente escalable que permite el seguimiento del inventario disponible en tiempo real, lo que proporciona una vista global de la visibilidad del inventario.</span><span class="sxs-lookup"><span data-stu-id="3ab74-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="3ab74-105">Toda la información relacionada con el inventario disponible se exporta al servicio casi en tiempo real mediante la integración de SQL de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="3ab74-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="3ab74-106">Los sistemas externos acceden al servicio a través de API RESTful para consultar información disponible sobre conjuntos de dimensiones dados, recuperando así una lista de posiciones disponibles disponibles.</span><span class="sxs-lookup"><span data-stu-id="3ab74-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="3ab74-107">Inventory Visibility es un microservicio construido en Common Data Service, lo que significa que puede ampliarlo creando Power Apps y aplicando Power BI para proporcionar una funcionalidad personalizada para satisfacer los requisitos de su negocio.</span><span class="sxs-lookup"><span data-stu-id="3ab74-107">Inventory Visibility is a microservice built on the Common Data Service, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="3ab74-108">También es posible actualizar el índice para realizar consultas de inventario.</span><span class="sxs-lookup"><span data-stu-id="3ab74-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="3ab74-109">Inventory Visibility ofrece opciones de configuración que le permiten integrarse con varios sistemas de terceros.</span><span class="sxs-lookup"><span data-stu-id="3ab74-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="3ab74-110">Admite la dimensión de inventario estandarizado, la extensibilidad personalizada y las cantidades calculadas configurables estandarizadas.</span><span class="sxs-lookup"><span data-stu-id="3ab74-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="3ab74-111">Este tema describe cómo instalar y configurar el complemento de visibilidad de inventario para Dynamics 365 Supply Chain Management y cómo utilizar su interfaz de programación de aplicaciones (API).</span><span class="sxs-lookup"><span data-stu-id="3ab74-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="3ab74-112">Instalar el complemento de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="3ab74-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="3ab74-113">Debe instalar el complemento de visibilidad de inventario mediante Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="3ab74-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="3ab74-114">LCS es un portal de colaboración que proporciona un entorno y un conjunto de servicios actualizados periódicamente que le ayudan a gestionar el ciclo de vida de la aplicación de sus aplicaciones de Dynamics 365 Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="3ab74-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="3ab74-115">Para obtener más información, consulte [Recursos de Lifecycle Services](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span><span class="sxs-lookup"><span data-stu-id="3ab74-115">For more information, see [Lifecycle Services resources](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span></span>

### <a name="prerequisites"></a><span data-ttu-id="3ab74-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="3ab74-116">Prerequisites</span></span>

<span data-ttu-id="3ab74-117">Para poder instalar el complemento de visibilidad de inventario, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ab74-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="3ab74-118">Obtenga un proyecto de implementación de LCS con al menos un entorno implementado.</span><span class="sxs-lookup"><span data-stu-id="3ab74-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="3ab74-119">Genere las claves beta para su oferta en LCS.</span><span class="sxs-lookup"><span data-stu-id="3ab74-119">Generate the beta keys for your offering in LCS.</span></span>
- <span data-ttu-id="3ab74-120">Habilite las claves beta para su oferta para su usuario en LCS.</span><span class="sxs-lookup"><span data-stu-id="3ab74-120">Enable the beta keys for your offering for your user in LCS.</span></span>
- <span data-ttu-id="3ab74-121">Póngase en contacto con el equipo de productos de visibilidad de inventario de Microsoft y proporcione un identificador de entorno en el que desea implementar el complemento de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="3ab74-121">Contact the Microsoft Inventory Visibility product team and provide an environment ID where you want to deploy the Inventory Visibility Add-in.</span></span>

<span data-ttu-id="3ab74-122">Si tiene alguna pregunta sobre estos requisitos previos, comuníquese con el equipo de productos de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="3ab74-122">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="3ab74-123">Instalar el complemento</span><span class="sxs-lookup"><span data-stu-id="3ab74-123">Install the add-in</span></span>

<span data-ttu-id="3ab74-124">Para instalar el complemento de visibilidad de inventario, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ab74-124">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="3ab74-125">Inicie sesión en el portal de [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="3ab74-125">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="3ab74-126">En la página de inicio, seleccione el proyecto donde se implementa su entorno.</span><span class="sxs-lookup"><span data-stu-id="3ab74-126">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="3ab74-127">En la página del proyecto, seleccione el entorno donde desea instalar el complemento.</span><span class="sxs-lookup"><span data-stu-id="3ab74-127">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="3ab74-128">En la página del entorno, desplácese hacia abajo hasta que vea la sección **Complementos de entorno**.</span><span class="sxs-lookup"><span data-stu-id="3ab74-128">On the environment page, scroll down until you see the **Environment add-ins** section.</span></span> <span data-ttu-id="3ab74-129">Si la sección no está visible, asegúrese de que las claves beta de requisito previo se hayan procesado por completo.</span><span class="sxs-lookup"><span data-stu-id="3ab74-129">If the section isn't visible, make sure the prerequisite beta keys have been fully processed.</span></span>
1. <span data-ttu-id="3ab74-130">En la sección **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="3ab74-130">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
    <span data-ttu-id="3ab74-131">![Página de entorno en LCS](media/inventory-visibility-environment.png "Página de entorno en LCS")</span><span class="sxs-lookup"><span data-stu-id="3ab74-131">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>
1. <span data-ttu-id="3ab74-132">Seleccione el vínculo **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="3ab74-132">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="3ab74-133">Se abre una lista de complementos disponibles.</span><span class="sxs-lookup"><span data-stu-id="3ab74-133">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="3ab74-134">Seleccione **Servicio de inventario** en la lista.</span><span class="sxs-lookup"><span data-stu-id="3ab74-134">Select **Inventory service** from the list.</span></span> <span data-ttu-id="3ab74-135">(Tenga en cuenta que esto ahora puede aparecer como **Complemento de visibilidad de inventario para Dynamics 365 Supply Chain Management**).</span><span class="sxs-lookup"><span data-stu-id="3ab74-135">(Note, this may now be listed as **Inventory Visibility Add-in for Dynamics 365 Supply Chain Management**.)</span></span>
1. <span data-ttu-id="3ab74-136">Ingrese valores para los siguientes campos para su entorno:</span><span class="sxs-lookup"><span data-stu-id="3ab74-136">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="3ab74-137">**ID de aplicación de AAD**</span><span class="sxs-lookup"><span data-stu-id="3ab74-137">**AAD application ID**</span></span>
    - <span data-ttu-id="3ab74-138">**Id. de suscriptor de AAD**</span><span class="sxs-lookup"><span data-stu-id="3ab74-138">**AAD tenant ID**</span></span>

    <span data-ttu-id="3ab74-139">![Agregar en la página de configuración](media/inventory-visibility-setup.png "Página de configuración del complemento")</span><span class="sxs-lookup"><span data-stu-id="3ab74-139">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="3ab74-140">Acepte los términos y condiciones seleccionando la casilla de verificación **Términos y Condiciones**.</span><span class="sxs-lookup"><span data-stu-id="3ab74-140">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="3ab74-141">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="3ab74-141">Select **Install**.</span></span> <span data-ttu-id="3ab74-142">El estado del complemento se mostrará como **Instalando**.</span><span class="sxs-lookup"><span data-stu-id="3ab74-142">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="3ab74-143">Cuando haya terminado, actualice la página para ver el cambio de estado a **Instalado**.</span><span class="sxs-lookup"><span data-stu-id="3ab74-143">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="get-a-security-service-token"></a><span data-ttu-id="3ab74-144">Obtenga un token de servicio de seguridad</span><span class="sxs-lookup"><span data-stu-id="3ab74-144">Get a security service token</span></span>

<span data-ttu-id="3ab74-145">Para obtener un token de servicio de seguridad, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ab74-145">To get a security service token, do the following:</span></span>

1. <span data-ttu-id="3ab74-146">Conseguir su `aadToken` y llamar al punto final: https://securityservice.operations365.dynamics.com/token.</span><span class="sxs-lookup"><span data-stu-id="3ab74-146">Get your `aadToken` and call the endpoint: https://securityservice.operations365.dynamics.com/token.</span></span>
1. <span data-ttu-id="3ab74-147">Reemplace `client_assertion` en el cuerpo con su `aadToken`.</span><span class="sxs-lookup"><span data-stu-id="3ab74-147">Replace the `client_assertion` in the body with your `aadToken`.</span></span>
1. <span data-ttu-id="3ab74-148">Reemplace el contexto en el cuerpo con el entorno donde desea implementar el complemento.</span><span class="sxs-lookup"><span data-stu-id="3ab74-148">Replace the context in the body with the environment where you want to deploy the add-in.</span></span>
1. <span data-ttu-id="3ab74-149">Reemplace el alcance en el cuerpo con lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="3ab74-149">Replace the scope in the body with the following:</span></span>

    - <span data-ttu-id="3ab74-150">Alcance para MCK - "https://inventoryservice.operations365.dynamics.cn/.default"</span><span class="sxs-lookup"><span data-stu-id="3ab74-150">Scope for MCK - "https://inventoryservice.operations365.dynamics.cn/.default"</span></span>  
    <span data-ttu-id="3ab74-151">(Puede encontrar el ID de aplicación e ID de inquilino de Azure Active Directory para MCK en `appsettings.mck.json`).</span><span class="sxs-lookup"><span data-stu-id="3ab74-151">(You can find the Azure Active Directory application ID and tenant ID for MCK in `appsettings.mck.json`.)</span></span>
    - <span data-ttu-id="3ab74-152">Alcance para PROD - "https://inventoryservice.operations365.dynamics.com/.default"</span><span class="sxs-lookup"><span data-stu-id="3ab74-152">Scope for PROD - "https://inventoryservice.operations365.dynamics.com/.default"</span></span>  
    <span data-ttu-id="3ab74-153">(Puede encontrar el ID de aplicación e ID de inquilino de Azure Active Directory para PROD en `appsettings.prod.json`).</span><span class="sxs-lookup"><span data-stu-id="3ab74-153">(You can find the Azure Active Directory application ID and tenant ID for PROD in `appsettings.prod.json`.)</span></span>

    <span data-ttu-id="3ab74-154">El resultado se parecerá al ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="3ab74-154">The result should resemble the following example.</span></span>

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{**Your_AADToken**}",
        "scope":"**https://inventoryservice.operations365.dynamics.com/.default**",
        "context": "**5dbf6cc8-255e-4de2-8a25-2101cd5649b4**",
        "context_type": "finops-env"
    }
    ```

1. <span data-ttu-id="3ab74-155">Obtendrá `access_token` como respuesta.</span><span class="sxs-lookup"><span data-stu-id="3ab74-155">You will get an `access_token` in response.</span></span> <span data-ttu-id="3ab74-156">Esto es lo que necesita como token de portador para llamar a la API de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="3ab74-156">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="3ab74-157">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="3ab74-157">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="uninstall-the-add-in"></a><span data-ttu-id="3ab74-158">Desinstalar el complemento</span><span class="sxs-lookup"><span data-stu-id="3ab74-158">Uninstall the add-in</span></span>

<span data-ttu-id="3ab74-159">Para desinstalar el complemento, seleccione **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="3ab74-159">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="3ab74-160">Actualizar LCS y el complemento de visibilidad de inventario se eliminarán.</span><span class="sxs-lookup"><span data-stu-id="3ab74-160">Refresh LCS and the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="3ab74-161">El proceso de desinstalación eliminará el registro del complemento y también iniciará un trabajo para limpiar todos los datos comerciales almacenados en el servicio.</span><span class="sxs-lookup"><span data-stu-id="3ab74-161">The uninstall process will remove the add-in registration and also start a job to clean up all of the business data stored in the service.</span></span>

## <a name="inventory-visibility-add-in-public-api"></a><span data-ttu-id="3ab74-162">Complemento de visibilidad de inventario en API pública</span><span class="sxs-lookup"><span data-stu-id="3ab74-162">Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="3ab74-163">La API de REST pública del complemento de visibilidad de inventario presenta varios puntos finales específicos de integración.</span><span class="sxs-lookup"><span data-stu-id="3ab74-163">The public REST API of the of the Inventory Visibility Add-in presents several specific endpoints of integration.</span></span> <span data-ttu-id="3ab74-164">Admite tres tipos principales de interacción:</span><span class="sxs-lookup"><span data-stu-id="3ab74-164">It supports three main interaction types:</span></span>

- <span data-ttu-id="3ab74-165">Publicar cambios disponibles en el complemento desde un sistema externo.</span><span class="sxs-lookup"><span data-stu-id="3ab74-165">Posting on-hand changes to the add-in from an external system.</span></span>
- <span data-ttu-id="3ab74-166">Consultar cantidades actuales disponibles desde un sistema externo.</span><span class="sxs-lookup"><span data-stu-id="3ab74-166">Querying current on-hand quantities from an external system.</span></span>
- <span data-ttu-id="3ab74-167">Sincronización automática con Supply Chain Management disponible.</span><span class="sxs-lookup"><span data-stu-id="3ab74-167">Automatic synchronization with Supply Chain Management on-hand.</span></span>

<span data-ttu-id="3ab74-168">La sincronización automática no forma parte de la API pública, sino que se gestiona en segundo plano para los entornos que han habilitado el complemento de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="3ab74-168">The automatic synchronization isn't part of the public API but is instead handled in the background for environments that have enabled the Inventory Visibility Add-in.</span></span>

### <a name="authentication"></a><span data-ttu-id="3ab74-169">Autentificación</span><span class="sxs-lookup"><span data-stu-id="3ab74-169">Authentication</span></span>

<span data-ttu-id="3ab74-170">El token de seguridad de la plataforma se utiliza para llamar al complemento de visibilidad de inventario, por lo que debe generar un token de Azure Active Directory usando su aplicación de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3ab74-170">The platform security token is used to call the Inventory Visibility Add-in, so you must generate an Azure Active Directory token using your Azure Active Directory application.</span></span>

<span data-ttu-id="3ab74-171">Para obtener más información sobre cómo obtener el token de seguridad, consulte [Instalar el complemento de visibilidad de inventario](#install-add-in).</span><span class="sxs-lookup"><span data-stu-id="3ab74-171">For more information about how to get the security token, see [Install the Inventory Visibility Add-in](#install-add-in).</span></span>

### <a name="configure-the-inventory-visibility-api"></a><span data-ttu-id="3ab74-172">Configurar la API de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="3ab74-172">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="3ab74-173">Antes de utilizar el servicio, debe completar las configuraciones descritas en las siguientes subsecciones.</span><span class="sxs-lookup"><span data-stu-id="3ab74-173">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="3ab74-174">La configuración puede variar según los detalles de su entorno.</span><span class="sxs-lookup"><span data-stu-id="3ab74-174">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="3ab74-175">Incluye principalmente cuatro partes:</span><span class="sxs-lookup"><span data-stu-id="3ab74-175">It primarily includes four parts:</span></span>

- [<span data-ttu-id="3ab74-176">Partición</span><span class="sxs-lookup"><span data-stu-id="3ab74-176">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="3ab74-177">Configuraciones de dimensiones</span><span class="sxs-lookup"><span data-stu-id="3ab74-177">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="3ab74-178">Indexación</span><span class="sxs-lookup"><span data-stu-id="3ab74-178">Indexing</span></span>](#indexing)
- [<span data-ttu-id="3ab74-179">Medida personalizada</span><span class="sxs-lookup"><span data-stu-id="3ab74-179">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="3ab74-180">Partición</span><span class="sxs-lookup"><span data-stu-id="3ab74-180">Partitioning</span></span>

<span data-ttu-id="3ab74-181">El particionamiento puede influir significativamente en el rendimiento de la API de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="3ab74-181">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="3ab74-182">Es una buena idea definir un esquema que permita pequeñas agrupaciones de datos y al mismo tiempo permita consultas de datos significativas.</span><span class="sxs-lookup"><span data-stu-id="3ab74-182">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="3ab74-183">`organizationId` (`dataAreaId` en Supply Chain Management) siempre formará parte de la partición y, de forma predeterminada, la Visibilidad de inventario está configurada para particionar por dimensiones como *Sitio + Ubicación*.</span><span class="sxs-lookup"><span data-stu-id="3ab74-183">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="3ab74-184">Esto significa que el servicio siempre debe consultarse con estas dimensiones definidas en los filtros.</span><span class="sxs-lookup"><span data-stu-id="3ab74-184">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="3ab74-185">*Sitio* y *Ubicación* son dos dimensiones predeterminadas generales en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="3ab74-185">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="3ab74-186">En Supply Chain Management, esas dimensiones se denominan *Sitio* (`InventSiteId`) y *Almacén* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="3ab74-186">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="3ab74-187">Configuraciones de dimensiones</span><span class="sxs-lookup"><span data-stu-id="3ab74-187">Dimension configurations</span></span>

<span data-ttu-id="3ab74-188">Inventory Visibility proporcionará una lista de dimensiones predeterminadas generales para permitir la integración del sistema de múltiples fuentes.</span><span class="sxs-lookup"><span data-stu-id="3ab74-188">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="3ab74-189">La siguiente tabla enumera las dimensiones de inventario que serán los nombres de dimensión predeterminados en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="3ab74-189">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="3ab74-190">Tipo de dimensión</span><span class="sxs-lookup"><span data-stu-id="3ab74-190">Dimension type</span></span> | <span data-ttu-id="3ab74-191">Nombre de dimensión</span><span class="sxs-lookup"><span data-stu-id="3ab74-191">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="3ab74-192">Producto</span><span class="sxs-lookup"><span data-stu-id="3ab74-192">Product</span></span> | `ColorId` |
| <span data-ttu-id="3ab74-193">Producto</span><span class="sxs-lookup"><span data-stu-id="3ab74-193">Product</span></span> | `SizeId` |
| <span data-ttu-id="3ab74-194">Producto</span><span class="sxs-lookup"><span data-stu-id="3ab74-194">Product</span></span> | `StyleId` |
| <span data-ttu-id="3ab74-195">Producto</span><span class="sxs-lookup"><span data-stu-id="3ab74-195">Product</span></span> | `ConfigId` |
| <span data-ttu-id="3ab74-196">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="3ab74-196">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="3ab74-197">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="3ab74-197">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="3ab74-198">Ubicación</span><span class="sxs-lookup"><span data-stu-id="3ab74-198">Location</span></span> | `LocationId` |
| <span data-ttu-id="3ab74-199">Ubicación</span><span class="sxs-lookup"><span data-stu-id="3ab74-199">Location</span></span> | `SiteId` |
| <span data-ttu-id="3ab74-200">Estado de inventario</span><span class="sxs-lookup"><span data-stu-id="3ab74-200">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="3ab74-201">Específico del almacén</span><span class="sxs-lookup"><span data-stu-id="3ab74-201">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="3ab74-202">Específico del almacén</span><span class="sxs-lookup"><span data-stu-id="3ab74-202">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="3ab74-203">Específico del almacén</span><span class="sxs-lookup"><span data-stu-id="3ab74-203">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="3ab74-204">El tipo de dimensión enumerado en la tabla anterior es solo para referencia.</span><span class="sxs-lookup"><span data-stu-id="3ab74-204">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="3ab74-205">No es necesario definir el tipo de dimensión en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="3ab74-205">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="3ab74-206">Si existe una dimensión personalizada y necesita fluir a un valor predeterminado cuando la usa Inventory Visibility, puede configurar el nombre de la **Dimensión personalizada** en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="3ab74-206">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="3ab74-207">Los sistemas externos acceden a la visibilidad del inventario a través de API RESTful que permiten consultar información disponible sobre conjuntos de dimensiones dados.</span><span class="sxs-lookup"><span data-stu-id="3ab74-207">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="3ab74-208">Para la integración, Inventory Visibility le permite configurar el *origen de datos del canal externo* y la dimensión de origen en las *dimensiones objetivo* de Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="3ab74-208">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="3ab74-209">Las dimensiones de destino deben ser una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="3ab74-209">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="3ab74-210">Dimensiones predeterminadas en visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="3ab74-210">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="3ab74-211">Dimensiones personalizadas</span><span class="sxs-lookup"><span data-stu-id="3ab74-211">Custom dimensions</span></span>

<span data-ttu-id="3ab74-212">El propósito de la configuración de dimensiones es estandarizar la integración de múltiples sistemas para la consulta de dimensiones y el evento de publicación con dimensiones.</span><span class="sxs-lookup"><span data-stu-id="3ab74-212">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="3ab74-213">Indexación</span><span class="sxs-lookup"><span data-stu-id="3ab74-213">Indexing</span></span>

<span data-ttu-id="3ab74-214">La mayoría de las veces, la consulta de inventario disponible no solo estará en el nivel "total" más alto, sino que es posible que desee ver los resultados agregados según las dimensiones del inventario.</span><span class="sxs-lookup"><span data-stu-id="3ab74-214">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="3ab74-215">La visibilidad de inventario proporciona flexibilidad al permitirle configurar los índices, que se basan en la dimensión o la combinación de las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="3ab74-215">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="3ab74-216">Actualmente, solo puede configurar índices hasta un máximo de cinco.</span><span class="sxs-lookup"><span data-stu-id="3ab74-216">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="3ab74-217">Debe considerar cuidadosamente qué dimensión o combinación de dimensiones utilizará antes de la implementación para asegurarse de que satisfará sus necesidades comerciales.</span><span class="sxs-lookup"><span data-stu-id="3ab74-217">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="3ab74-218">Por ejemplo, si desea consultar productos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="3ab74-218">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="3ab74-219">Consultar el producto agregado disponible por dimensiones *Color* y *Talla*.</span><span class="sxs-lookup"><span data-stu-id="3ab74-219">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="3ab74-220">En algunos casos, solo desea consultar el producto en total.</span><span class="sxs-lookup"><span data-stu-id="3ab74-220">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="3ab74-221">Tendría dos índices definidos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="3ab74-221">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="3ab74-222">El corchete vacío se agregará según el ID del producto dentro de la partición.</span><span class="sxs-lookup"><span data-stu-id="3ab74-222">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="3ab74-223">La indexación define cómo puede agrupar sus resultados en función de la configuración de consulta `groupBy`.</span><span class="sxs-lookup"><span data-stu-id="3ab74-223">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="3ab74-224">En este caso, si no define valores para `groupBy`, obtendrá totales por `productid`.</span><span class="sxs-lookup"><span data-stu-id="3ab74-224">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="3ab74-225">De lo contrario, si define `groupBy` como `groupBy=ColorId&groupBy=SizeId`, obtendrá varias líneas devueltas, según las diferentes combinaciones de colores y tamaños en el sistema.</span><span class="sxs-lookup"><span data-stu-id="3ab74-225">Otherwise if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="3ab74-226">Puede poner sus criterios de consulta en el cuerpo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="3ab74-226">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="3ab74-227">Aquí hay una consulta de muestra sobre el producto con combinación de color y tamaño.</span><span class="sxs-lookup"><span data-stu-id="3ab74-227">Here is a sample query on the product with color and size combination.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="custom-measurement"></a><span data-ttu-id="3ab74-228">Medida personalizada</span><span class="sxs-lookup"><span data-stu-id="3ab74-228">Custom measurement</span></span>

<span data-ttu-id="3ab74-229">Las cantidades de medición predeterminadas están vinculadas a Supply Chain Management; sin embargo, es posible que desee tener una cantidad que se componga de una combinación de las mediciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="3ab74-229">The default measurement quantities are linked to Supply Chain Management, however you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="3ab74-230">Para hacer esto, puede tener una configuración de cantidades personalizadas, que se agregarán a la salida de las consultas disponibles.</span><span class="sxs-lookup"><span data-stu-id="3ab74-230">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="3ab74-231">La funcionalidad simplemente le permite definir un conjunto de medidas que se agregarán, y / o un conjunto de medidas que se restarán, a partir de la medida personalizada.</span><span class="sxs-lookup"><span data-stu-id="3ab74-231">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="3ab74-232">Por ejemplo, con la siguiente condición de consulta, configurará la cantidad de medida personalizada como `MyCustomAvailableforReservation` para ser consumido por el sistema de consumo.</span><span class="sxs-lookup"><span data-stu-id="3ab74-232">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            }
        }
    }
]

```



| <span data-ttu-id="3ab74-233">Sistema de consumo</span><span class="sxs-lookup"><span data-stu-id="3ab74-233">Consumption system</span></span> | <span data-ttu-id="3ab74-234">Medidas calculadas</span><span class="sxs-lookup"><span data-stu-id="3ab74-234">Calculated measurers</span></span> | <span data-ttu-id="3ab74-235">Origen de datos</span><span class="sxs-lookup"><span data-stu-id="3ab74-235">Data source</span></span> | <span data-ttu-id="3ab74-236">Modificador</span><span class="sxs-lookup"><span data-stu-id="3ab74-236">Modifier</span></span> | <span data-ttu-id="3ab74-237">Tipo de cálculo del modificador</span><span class="sxs-lookup"><span data-stu-id="3ab74-237">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="3ab74-238">Adición</span><span class="sxs-lookup"><span data-stu-id="3ab74-238">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="3ab74-239">Adición</span><span class="sxs-lookup"><span data-stu-id="3ab74-239">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="3ab74-240">Resta</span><span class="sxs-lookup"><span data-stu-id="3ab74-240">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="3ab74-241">Adición</span><span class="sxs-lookup"><span data-stu-id="3ab74-241">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="3ab74-242">Resta</span><span class="sxs-lookup"><span data-stu-id="3ab74-242">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="3ab74-243">Adición</span><span class="sxs-lookup"><span data-stu-id="3ab74-243">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="3ab74-244">Adición</span><span class="sxs-lookup"><span data-stu-id="3ab74-244">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="3ab74-245">Resta</span><span class="sxs-lookup"><span data-stu-id="3ab74-245">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="3ab74-246">Resta</span><span class="sxs-lookup"><span data-stu-id="3ab74-246">Subtraction</span></span> |

<span data-ttu-id="3ab74-247">Con eso, la consulta sobre la cantidad de medición personalizada devolverá el siguiente resultado.</span><span class="sxs-lookup"><span data-stu-id="3ab74-247">With that, the query on the custom measurement quantity will return the following output.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="3ab74-248">La salida `MyCustomAvailableforReservation` se basa en la configuración de cálculo en las medidas personalizadas como:</span><span class="sxs-lookup"><span data-stu-id="3ab74-248">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="3ab74-249">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="3ab74-249">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="3ab74-250">Publicar cambios disponibles</span><span class="sxs-lookup"><span data-stu-id="3ab74-250">Posting on-hand changes</span></span>

<span data-ttu-id="3ab74-251">La URL exacta en la que se publicará el evento dependerá de su región geográfica.</span><span class="sxs-lookup"><span data-stu-id="3ab74-251">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="3ab74-252">Tomará la forma:</span><span class="sxs-lookup"><span data-stu-id="3ab74-252">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="3ab74-253">Cuando se autentica, esta URL se puede utilizar junto con el método HTTP `POST` para enviar eventos de cambio disponibles al servicio.</span><span class="sxs-lookup"><span data-stu-id="3ab74-253">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="3ab74-254">Se usa un encabezado especial para comunicarse con los servicios de Dynamics 365 a través de solicitudes HTTP, que denota el Id. De entorno de la instancia de Supply Chain Management a la que están vinculados los datos.</span><span class="sxs-lookup"><span data-stu-id="3ab74-254">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="3ab74-255">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="3ab74-255">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="3ab74-256">Publicación de cambios disponibles ejemplo de consulta 1</span><span class="sxs-lookup"><span data-stu-id="3ab74-256">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="3ab74-257">Este ejemplo muestra un escenario en el que establecerá la configuración de dimensión en Power Apps.</span><span class="sxs-lookup"><span data-stu-id="3ab74-257">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="3ab74-258">Utilice la siguiente consulta para configurar la asignación de dimensiones en Power Apps:</span><span class="sxs-lookup"><span data-stu-id="3ab74-258">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="3ab74-259">Ahora puede especificar `dimensionDataSource` y usar dimensiones personalizadas en sus consultas.</span><span class="sxs-lookup"><span data-stu-id="3ab74-259">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="3ab74-260">El sistema convertirá automáticamente las dimensiones personalizadas en dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="3ab74-260">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensionDataSource": "pos",
    "dimensions": {
        "PosSizeId": "Large",
        "PosColorId": "Red",
        "PosSiteId": "2",
        "PosLocationId": "21"
    }
}
```

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="3ab74-261">Publicación de cambios disponibles ejemplo de consulta 2</span><span class="sxs-lookup"><span data-stu-id="3ab74-261">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="3ab74-262">Este ejemplo muestra un escenario en el que no se establecen asignaciones para la configuración de dimensión en Power Apps, por lo que la publicación también debe usar las dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="3ab74-262">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="3ab74-263">Todas las dimensiones deben ser dimensiones base cuando el campo `dimensionDataSource` es nulo, vacío o espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="3ab74-263">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

```json
{
    "id": "demo-test-00007",
    "organizationId": "usmf",
    "productId": "MyProduct",
    "quantities": {
        "pos": {
            "Outbound": 1
        }
    },
    "dimensions": {
        "SizeId": "Large",
        "ColorId": "Red",
        "SiteId": "2",
        "LocationId": "21"
    }
}
```

#### <a name="json-document-field-properties"></a><span data-ttu-id="3ab74-264">Propiedades de campo de documento JSON</span><span class="sxs-lookup"><span data-stu-id="3ab74-264">JSON document field properties</span></span>

<span data-ttu-id="3ab74-265">Los campos de los ejemplos de consultas JSON proporcionados anteriormente tienen las propiedades enumeradas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="3ab74-265">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="3ab74-266">Id. del campo</span><span class="sxs-lookup"><span data-stu-id="3ab74-266">Field ID</span></span> | <span data-ttu-id="3ab74-267">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ab74-267">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="3ab74-268">Un ID único para el evento de cambio específico.</span><span class="sxs-lookup"><span data-stu-id="3ab74-268">A unique ID for the specific change event.</span></span> <span data-ttu-id="3ab74-269">Este ID se utiliza para garantizar que si la comunicación con el servicio falla durante la publicación, volver a enviar el evento no resultará en que el mismo evento se cuente dos veces en el sistema.</span><span class="sxs-lookup"><span data-stu-id="3ab74-269">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="3ab74-270">El identificador de la organización vinculada al evento.</span><span class="sxs-lookup"><span data-stu-id="3ab74-270">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="3ab74-271">Esto se asigna a las organizaciones de Supply Chain Management o los ID de área de datos.</span><span class="sxs-lookup"><span data-stu-id="3ab74-271">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="3ab74-272">El identificador del producto en cuestión.</span><span class="sxs-lookup"><span data-stu-id="3ab74-272">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="3ab74-273">La cantidad por la que se debe cambiar el producto disponible.</span><span class="sxs-lookup"><span data-stu-id="3ab74-273">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="3ab74-274">Si, por ejemplo, se añadieran 10 bagels nuevos a un estante, este valor sería 10.</span><span class="sxs-lookup"><span data-stu-id="3ab74-274">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="3ab74-275">Si luego se sacaran 3 bagels del estante o se vendieran, este valor sería -3.</span><span class="sxs-lookup"><span data-stu-id="3ab74-275">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="3ab74-276">La fuente de datos de las dimensiones utilizadas en la consulta y el evento de cambio de publicación.</span><span class="sxs-lookup"><span data-stu-id="3ab74-276">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="3ab74-277">Si especifica la fuente de datos, puede utilizar las dimensiones personalizadas de la fuente de datos especificada.</span><span class="sxs-lookup"><span data-stu-id="3ab74-277">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="3ab74-278">Con la configuración de dimensión, Inventory Visibility puede asignar las dimensiones personalizadas a las dimensiones predeterminadas generales.</span><span class="sxs-lookup"><span data-stu-id="3ab74-278">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="3ab74-279">Si no se especifica `dimensionDataSource`, solo puede utilizar las dimensiones predeterminadas generales en sus consultas.</span><span class="sxs-lookup"><span data-stu-id="3ab74-279">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="3ab74-280">Una bolsa dinámica de pares clave / valor.</span><span class="sxs-lookup"><span data-stu-id="3ab74-280">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="3ab74-281">Estos se asignarán a algunas de las dimensiones en Supply Chain Management, pero también puede agregar dimensiones personalizadas (como *Origen*) que puede indicar si el evento provenía de Supply Chain Management o de un sistema externo.</span><span class="sxs-lookup"><span data-stu-id="3ab74-281">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="3ab74-282">Consultando la corriente disponible</span><span class="sxs-lookup"><span data-stu-id="3ab74-282">Querying current on-hand</span></span>

<span data-ttu-id="3ab74-283">El punto final para consultar el actual disponible tendrá una URL similar:</span><span class="sxs-lookup"><span data-stu-id="3ab74-283">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="3ab74-284">Se consultará con el método HTTP `POST`.</span><span class="sxs-lookup"><span data-stu-id="3ab74-284">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="3ab74-285">Ejemplo 1 de consulta actual disponible</span><span class="sxs-lookup"><span data-stu-id="3ab74-285">Current on-hand query example 1</span></span>

<span data-ttu-id="3ab74-286">Este ejemplo muestra un escenario en el que ya ha completado la configuración de dimensión en Power Apps.</span><span class="sxs-lookup"><span data-stu-id="3ab74-286">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="3ab74-287">Utilice la siguiente consulta para configurar la asignación de dimensiones en Power Apps:</span><span class="sxs-lookup"><span data-stu-id="3ab74-287">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="3ab74-288">Ahora puede especificar `dimensionDataSource` y usar dimensiones personalizadas en sus consultas.</span><span class="sxs-lookup"><span data-stu-id="3ab74-288">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="3ab74-289">El sistema convertirá automáticamente las dimensiones personalizadas en dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="3ab74-289">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="3ab74-290">Puede especificar `DimensionDataSource` en `filters` y especificar dimensiones personalizadas en `filters` y `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="3ab74-290">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="3ab74-291">El sistema convertirá automáticamente las dimensiones personalizadas en dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="3ab74-291">The system will automatically convert custom dimensions to base dimensions.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "DimensionDataSource": ["Pos"],
        "PosLocationId": ["21"],
        "PosSiteId": ["2"],
        "PosColorId": ["Red"]
    },
    "groupByValues": [
        "PosSizeId",
        "PosColorId"
    ],
    "returnNegative": true
}
```

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="3ab74-292">Ejemplo 2 de consulta actual disponible</span><span class="sxs-lookup"><span data-stu-id="3ab74-292">Current on-hand query example 2</span></span>

<span data-ttu-id="3ab74-293">Este ejemplo muestra un escenario en el que no se establecen asignaciones para la configuración de dimensión en Power Apps, por lo que la publicación también debe usar las dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="3ab74-293">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="3ab74-294">Todas las dimensiones deben ser dimensiones base cuando el campo `dimensionDataSource`, bajo `filters`, es nulo, vacío o espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="3ab74-294">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

```json
{
    "filters": {
        "OrganizationId": ["usmf"],
        "ProductId": ["MyProduct"],
        "LocationId": ["21"],
        "SiteId": ["2"],
        "ColorId": ["Red"]
    },
    "groupByValues": [
        "SizeId",
        "ColorId"
    ],
    "returnNegative": true
}
```

#### <a name="example-return-result"></a><span data-ttu-id="3ab74-295">Resultado devuelto de ejemplo</span><span class="sxs-lookup"><span data-stu-id="3ab74-295">Example return result</span></span>

<span data-ttu-id="3ab74-296">Las consultas que se muestran en los ejemplos anteriores podrían devolver un resultado como este.</span><span class="sxs-lookup"><span data-stu-id="3ab74-296">The queries shown in the previous examples could return a result like this.</span></span>

```json
[
    {
        "productId": "MyProduct",
        "dimensions": {
            "colorid": "Red"
        },
        "quantities": {
            "mypos": {
                "outbound": 20.0,
                "inbound": 80.0
            },
            "fno": {
                "availphysical": 100.0,
                "orderedintotal": 50.0,
                "orderedreserved": 10.0
            },
            "exterchannel": {
                "received": 90.0,
                "scheduled": 30.0,
                "issued": 60.0,
                "reserved": 40.0
            },
            "CustomChannel": {
                "MyCustomAvailableforReservation": 220.0
            }
        }
    }
]
```

<span data-ttu-id="3ab74-297">Tenga en cuenta que los campos de cantidades están estructurados como un diccionario de medidas y sus valores asociados.</span><span class="sxs-lookup"><span data-stu-id="3ab74-297">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>
