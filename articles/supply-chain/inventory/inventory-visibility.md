---
title: Complemento de visibilidad de inventario
description: Este tema describe cómo instalar y configurar el complemento de visibilidad de inventario para Dynamics 365 Supply Chain Management.
author: sherry-zheng
manager: tfehr
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 4e6f7e0a3978bbf7e520f8cbcfd27c4cfe507777
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2021
ms.locfileid: "5114679"
---
# <a name="inventory-visibility-add-in"></a><span data-ttu-id="638e4-103">Complemento de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="638e4-103">Inventory Visibility Add-in</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]
[!INCLUDE [cc-data-platform-banner](../../includes/cc-data-platform-banner.md)]

<span data-ttu-id="638e4-104">El complemento de visibilidad de inventario es un microservicio independiente y altamente escalable que permite el seguimiento del inventario disponible en tiempo real, lo que proporciona una vista global de la visibilidad del inventario.</span><span class="sxs-lookup"><span data-stu-id="638e4-104">The Inventory Visibility Add-in is an independent and highly scalable microservice that enables real-time on-hand inventory tracking, thus providing a global view of inventory visibility.</span></span>

<span data-ttu-id="638e4-105">Toda la información relacionada con el inventario disponible se exporta al servicio casi en tiempo real mediante la integración de SQL de bajo nivel.</span><span class="sxs-lookup"><span data-stu-id="638e4-105">All information that relates to on-hand inventory is exported to the service in near real-time through low-level SQL integration.</span></span> <span data-ttu-id="638e4-106">Los sistemas externos acceden al servicio a través de API RESTful para consultar información disponible sobre conjuntos de dimensiones dados, recuperando así una lista de posiciones disponibles disponibles.</span><span class="sxs-lookup"><span data-stu-id="638e4-106">External systems access the service through RESTful APIs to query on-hand information on given sets of dimensions, thus retrieving a list of available on-hand positions.</span></span>

<span data-ttu-id="638e4-107">Inventory Visibility es un microservicio construido en Microsoft Dataverse, lo que significa que puede ampliarlo creando Power Apps y aplicando Power BI para proporcionar una funcionalidad personalizada para satisfacer los requisitos de su negocio.</span><span class="sxs-lookup"><span data-stu-id="638e4-107">Inventory Visibility is a microservice built on Microsoft Dataverse, which means you can extend it by building Power Apps and applying Power BI to provide customized functionality to meet your business requirements.</span></span> <span data-ttu-id="638e4-108">También es posible actualizar el índice para realizar consultas de inventario.</span><span class="sxs-lookup"><span data-stu-id="638e4-108">It is also possible to upgrade the index to do inventory queries.</span></span>

<span data-ttu-id="638e4-109">Inventory Visibility ofrece opciones de configuración que le permiten integrarse con varios sistemas de terceros.</span><span class="sxs-lookup"><span data-stu-id="638e4-109">Inventory Visibility provides configuration options that let it integrate with multiple third-party systems.</span></span> <span data-ttu-id="638e4-110">Admite la dimensión de inventario estandarizado, la extensibilidad personalizada y las cantidades calculadas configurables estandarizadas.</span><span class="sxs-lookup"><span data-stu-id="638e4-110">It supports the standardized inventory dimension, customized extensibility, and standardized, configurable calculated quantities.</span></span>

<span data-ttu-id="638e4-111">Este tema describe cómo instalar y configurar el complemento de visibilidad de inventario para Dynamics 365 Supply Chain Management y cómo utilizar su interfaz de programación de aplicaciones (API).</span><span class="sxs-lookup"><span data-stu-id="638e4-111">This topic describes how to install and configure the Inventory Visibility Add-in for Dynamics 365 Supply Chain Management, and how to use its application programming interface (API).</span></span>

## <a name="install-the-inventory-visibility-add-in"></a><span data-ttu-id="638e4-112">Instalar el complemento de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="638e4-112">Install the Inventory Visibility Add-in</span></span>

<span data-ttu-id="638e4-113">Debe instalar el complemento de visibilidad de inventario mediante Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="638e4-113">You need to install the Inventory Visibility Add-in using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="638e4-114">LCS es un portal de colaboración que proporciona un entorno y un conjunto de servicios actualizados periódicamente que le ayudan a gestionar el ciclo de vida de la aplicación de sus aplicaciones de Dynamics 365 Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="638e4-114">LCS is a collaboration portal that provides an environment and a set of regularly updated services that help you manage the application lifecycle of your Dynamics 365 Finance and Operations apps.</span></span>

<span data-ttu-id="638e4-115">Para obtener más información, consulte [Recursos de Lifecycle Services](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span><span class="sxs-lookup"><span data-stu-id="638e4-115">For more information, see [Lifecycle Services resources](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs).</span></span>

### <a name="prerequisites"></a><span data-ttu-id="638e4-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="638e4-116">Prerequisites</span></span>

<span data-ttu-id="638e4-117">Para poder instalar el complemento de visibilidad de inventario, debe hacer lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="638e4-117">Before you install the Inventory Visibility Add-in, you must do the following:</span></span>

- <span data-ttu-id="638e4-118">Obtenga un proyecto de implementación de LCS con al menos un entorno implementado.</span><span class="sxs-lookup"><span data-stu-id="638e4-118">Obtain an LCS implementation project with at least one environment deployed.</span></span>
- <span data-ttu-id="638e4-119">Genere las claves beta para su oferta en LCS.</span><span class="sxs-lookup"><span data-stu-id="638e4-119">Generate the beta keys for your offering in LCS.</span></span>
- <span data-ttu-id="638e4-120">Habilite las claves beta para su oferta para su usuario en LCS.</span><span class="sxs-lookup"><span data-stu-id="638e4-120">Enable the beta keys for your offering for your user in LCS.</span></span>
- <span data-ttu-id="638e4-121">Póngase en contacto con el equipo de productos de visibilidad de inventario de Microsoft y proporcione un identificador de entorno en el que desea implementar el complemento de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="638e4-121">Contact the Microsoft Inventory Visibility product team and provide an environment ID where you want to deploy the Inventory Visibility Add-in.</span></span>

<span data-ttu-id="638e4-122">Si tiene alguna pregunta sobre estos requisitos previos, comuníquese con el equipo de productos de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="638e4-122">If you have any questions about these prerequisites, please contact the Inventory Visibility product team.</span></span>

### <a name="install-the-add-in"></a><a name="install-add-in"></a><span data-ttu-id="638e4-123">Instalar el complemento</span><span class="sxs-lookup"><span data-stu-id="638e4-123">Install the add-in</span></span>

<span data-ttu-id="638e4-124">Para instalar el complemento de visibilidad de inventario, haga lo siguiente:</span><span class="sxs-lookup"><span data-stu-id="638e4-124">To install the Inventory Visibility Add-in, do the following:</span></span>

1. <span data-ttu-id="638e4-125">Inicie sesión en el portal de [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="638e4-125">Sign in to the [Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index) portal.</span></span>
1. <span data-ttu-id="638e4-126">En la página de inicio, seleccione el proyecto donde se implementa su entorno.</span><span class="sxs-lookup"><span data-stu-id="638e4-126">On the home page, select the project where your environment is deployed.</span></span>
1. <span data-ttu-id="638e4-127">En la página del proyecto, seleccione el entorno donde desea instalar el complemento.</span><span class="sxs-lookup"><span data-stu-id="638e4-127">On the project page, select the environment where you want to install the add-in.</span></span>
1. <span data-ttu-id="638e4-128">En la página del entorno, desplácese hacia abajo hasta que vea la sección **Complementos de entorno**.</span><span class="sxs-lookup"><span data-stu-id="638e4-128">On the environment page, scroll down until you see the **Environment add-ins** section.</span></span> <span data-ttu-id="638e4-129">Si la sección no está visible, asegúrese de que las claves beta de requisito previo se hayan procesado por completo.</span><span class="sxs-lookup"><span data-stu-id="638e4-129">If the section isn't visible, make sure the prerequisite beta keys have been fully processed.</span></span>
1. <span data-ttu-id="638e4-130">En la sección **Complementos de entorno**, seleccione **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="638e4-130">In the **Environment add-ins** section, select **Install a new add-in**.</span></span>
    <span data-ttu-id="638e4-131">![Página de entorno en LCS](media/inventory-visibility-environment.png "Página de entorno en LCS")</span><span class="sxs-lookup"><span data-stu-id="638e4-131">![The environment page in LCS](media/inventory-visibility-environment.png "The environment page in LCS")</span></span>
1. <span data-ttu-id="638e4-132">Seleccione el vínculo **Instalar un nuevo complemento**.</span><span class="sxs-lookup"><span data-stu-id="638e4-132">Select the **Install a new add-in** link.</span></span> <span data-ttu-id="638e4-133">Se abre una lista de complementos disponibles.</span><span class="sxs-lookup"><span data-stu-id="638e4-133">A list of available add-ins opens.</span></span>
1. <span data-ttu-id="638e4-134">Seleccione **Servicio de inventario** en la lista.</span><span class="sxs-lookup"><span data-stu-id="638e4-134">Select **Inventory service** from the list.</span></span> <span data-ttu-id="638e4-135">(Tenga en cuenta que esto ahora puede aparecer como **Complemento de visibilidad de inventario para Dynamics 365 Supply Chain Management**).</span><span class="sxs-lookup"><span data-stu-id="638e4-135">(Note, this may now be listed as **Inventory Visibility Add-in for Dynamics 365 Supply Chain Management**.)</span></span>
1. <span data-ttu-id="638e4-136">Ingrese valores para los siguientes campos para su entorno:</span><span class="sxs-lookup"><span data-stu-id="638e4-136">Enter values for the following fields for your environment:</span></span>

    - <span data-ttu-id="638e4-137">**ID de aplicación de AAD**</span><span class="sxs-lookup"><span data-stu-id="638e4-137">**AAD application ID**</span></span>
    - <span data-ttu-id="638e4-138">**Id. de suscriptor de AAD**</span><span class="sxs-lookup"><span data-stu-id="638e4-138">**AAD tenant ID**</span></span>

    <span data-ttu-id="638e4-139">![Agregar en la página de configuración](media/inventory-visibility-setup.png "Página de configuración del complemento")</span><span class="sxs-lookup"><span data-stu-id="638e4-139">![Add in setup page](media/inventory-visibility-setup.png "Add-in setup page")</span></span>

1. <span data-ttu-id="638e4-140">Acepte los términos y condiciones seleccionando la casilla de verificación **Términos y Condiciones**.</span><span class="sxs-lookup"><span data-stu-id="638e4-140">Agree to the terms and condition by selecting the **Terms and conditions** check box.</span></span>
1. <span data-ttu-id="638e4-141">Seleccione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="638e4-141">Select **Install**.</span></span> <span data-ttu-id="638e4-142">El estado del complemento se mostrará como **Instalando**.</span><span class="sxs-lookup"><span data-stu-id="638e4-142">The status of the add-in will show as **Installing**.</span></span> <span data-ttu-id="638e4-143">Cuando haya terminado, actualice la página para ver el cambio de estado a **Instalado**.</span><span class="sxs-lookup"><span data-stu-id="638e4-143">When it's done, refresh the page to see the status change to **Installed**.</span></span>

### <a name="get-a-security-service-token"></a><span data-ttu-id="638e4-144">Obtenga un token de servicio de seguridad</span><span class="sxs-lookup"><span data-stu-id="638e4-144">Get a security service token</span></span>

<span data-ttu-id="638e4-145">Obtenga un token de servicio de seguridad de la siguiente forma:</span><span class="sxs-lookup"><span data-stu-id="638e4-145">Get a security service token by doing the following:</span></span>

1. <span data-ttu-id="638e4-146">Inicie sesión en Azure Portal y utilícelo para encontrar el `clientId` y el `clientSecret` para su aplicación Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="638e4-146">Sign in to Azure Portal and use it to find the `clientId` and `clientSecret` for your Supply Chain Management application.</span></span>
1. <span data-ttu-id="638e4-147">Busque un token Azure Active Directory (`aadToken`) enviando una solicitud HTTP con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="638e4-147">Fetch an Azure Active Directory token (`aadToken`) by submitting an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="638e4-148">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span><span class="sxs-lookup"><span data-stu-id="638e4-148">**URL** - `https://login.microsoftonline.com/${aadTenantId}/oauth2/token`</span></span>
    - <span data-ttu-id="638e4-149">**Método** - `GET`</span><span class="sxs-lookup"><span data-stu-id="638e4-149">**Method** - `GET`</span></span>
    - <span data-ttu-id="638e4-150">**Contenido del cuerpo (datos del formulario)**:</span><span class="sxs-lookup"><span data-stu-id="638e4-150">**Body content (form data)**:</span></span>

        | <span data-ttu-id="638e4-151">key</span><span class="sxs-lookup"><span data-stu-id="638e4-151">key</span></span> | <span data-ttu-id="638e4-152">valor</span><span class="sxs-lookup"><span data-stu-id="638e4-152">value</span></span> |
        | --- | --- |
        | <span data-ttu-id="638e4-153">client_id</span><span class="sxs-lookup"><span data-stu-id="638e4-153">client_id</span></span> | <span data-ttu-id="638e4-154">${aadAppId}</span><span class="sxs-lookup"><span data-stu-id="638e4-154">${aadAppId}</span></span> |
        | <span data-ttu-id="638e4-155">client_secret</span><span class="sxs-lookup"><span data-stu-id="638e4-155">client_secret</span></span> | <span data-ttu-id="638e4-156">${aadAppSecret}</span><span class="sxs-lookup"><span data-stu-id="638e4-156">${aadAppSecret}</span></span> |
        | <span data-ttu-id="638e4-157">grant_type</span><span class="sxs-lookup"><span data-stu-id="638e4-157">grant_type</span></span> | <span data-ttu-id="638e4-158">client_credentials</span><span class="sxs-lookup"><span data-stu-id="638e4-158">client_credentials</span></span> |
        | <span data-ttu-id="638e4-159">resource</span><span class="sxs-lookup"><span data-stu-id="638e4-159">resource</span></span> | <span data-ttu-id="638e4-160">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span><span class="sxs-lookup"><span data-stu-id="638e4-160">0cdb527f-a8d1-4bf8-9436-b352c68682b2</span></span> |
1. <span data-ttu-id="638e4-161">Debería recibir un `aadToken` en respuesta, que se parece al siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="638e4-161">You should receive an `aadToken` in response, which resembles the following example.</span></span>

    ```json
    {
    "token_type": "Bearer",
    "expires_in": "3599",
    "ext_expires_in": "3599",
    "expires_on": "1610466645",
    "not_before": "1610462745",
    "resource": "0cdb527f-a8d1-4bf8-9436-b352c68682b2",
    "access_token": "eyJ0eX...8WQ"
    }
    ```

1. <span data-ttu-id="638e4-162">Formule una solicitud JSON similar a la siguiente:</span><span class="sxs-lookup"><span data-stu-id="638e4-162">Formulate a JSON request that resembles the following:</span></span>

    ```json
    {
        "grant_type": "client_credentials",
        "client_assertion_type":"aad_app",
        "client_assertion": "{Your_AADToken}",
        "scope":"https://inventoryservice.operations365.dynamics.com/.default",
        "context": "5dbf6cc8-255e-4de2-8a25-2101cd5649b4",
        "context_type": "finops-env"
    }
    ```

    <span data-ttu-id="638e4-163">Donde:</span><span class="sxs-lookup"><span data-stu-id="638e4-163">Where:</span></span>
    - <span data-ttu-id="638e4-164">El valor `client_assertion` debe ser el `aadToken` que recibió en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="638e4-164">The `client_assertion` value must be the `aadToken` you received in the previous step.</span></span>
    - <span data-ttu-id="638e4-165">El valor `context` debe ser el ID de entorno en el que desea implementar el complemento.</span><span class="sxs-lookup"><span data-stu-id="638e4-165">The `context` value must be the environment ID where you want to deploy the add-in.</span></span>
    - <span data-ttu-id="638e4-166">Configure todos los demás valores como se muestra en el ejemplo.</span><span class="sxs-lookup"><span data-stu-id="638e4-166">Set all of other values as shown in the example.</span></span>

1. <span data-ttu-id="638e4-167">Envíe una solicitud HTTP con las siguientes propiedades:</span><span class="sxs-lookup"><span data-stu-id="638e4-167">Submit an HTTP request with the following properties:</span></span>
    - <span data-ttu-id="638e4-168">**URL** - `https://securityservice.operations365.dynamics.com/token`</span><span class="sxs-lookup"><span data-stu-id="638e4-168">**URL** - `https://securityservice.operations365.dynamics.com/token`</span></span>
    - <span data-ttu-id="638e4-169">**Método** - `POST`</span><span class="sxs-lookup"><span data-stu-id="638e4-169">**Method** - `POST`</span></span>
    - <span data-ttu-id="638e4-170">**Encabezado HTTP** - Incluya la versión de API (la clave es `Api-Version` y el valor es `1.0`)</span><span class="sxs-lookup"><span data-stu-id="638e4-170">**HTTP header** - Include the API version (key is `Api-Version` and value is `1.0`)</span></span>
    - <span data-ttu-id="638e4-171">**Contenido del cuerpo** - Incluya la solicitud JSON que creó en el paso anterior.</span><span class="sxs-lookup"><span data-stu-id="638e4-171">**Body content** - Include the JSON request that you created in the previous step.</span></span>

1. <span data-ttu-id="638e4-172">Obtendrá `access_token` como respuesta.</span><span class="sxs-lookup"><span data-stu-id="638e4-172">You will get an `access_token` in response.</span></span> <span data-ttu-id="638e4-173">Esto es lo que necesita como token de portador para llamar a la API de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="638e4-173">This is what you need as a bearer token to call the Inventory Visibility API.</span></span> <span data-ttu-id="638e4-174">He aquí un ejemplo.</span><span class="sxs-lookup"><span data-stu-id="638e4-174">Here is an example.</span></span>

    ```json
    {
        "access_token": "{Returned_Token}",
        "token_type": "bearer",
        "expires_in": 1200
    }
    ```

### <a name="uninstall-the-add-in"></a><span data-ttu-id="638e4-175">Desinstalar el complemento</span><span class="sxs-lookup"><span data-stu-id="638e4-175">Uninstall the add-in</span></span>

<span data-ttu-id="638e4-176">Para desinstalar el complemento, seleccione **Desinstalar**.</span><span class="sxs-lookup"><span data-stu-id="638e4-176">To uninstall the add-in, select **Uninstall**.</span></span> <span data-ttu-id="638e4-177">Actualizar LCS y el complemento de visibilidad de inventario se eliminarán.</span><span class="sxs-lookup"><span data-stu-id="638e4-177">Refresh LCS and the Inventory Visibility Add-in will be removed.</span></span> <span data-ttu-id="638e4-178">El proceso de desinstalación eliminará el registro del complemento y también iniciará un trabajo para limpiar todos los datos comerciales almacenados en el servicio.</span><span class="sxs-lookup"><span data-stu-id="638e4-178">The uninstall process will remove the add-in registration and also start a job to clean up all of the business data stored in the service.</span></span>

## <a name="inventory-visibility-add-in-public-api"></a><span data-ttu-id="638e4-179">Complemento de visibilidad de inventario en API pública</span><span class="sxs-lookup"><span data-stu-id="638e4-179">Inventory Visibility Add-in public API</span></span>

<span data-ttu-id="638e4-180">La API de REST pública del complemento de visibilidad de inventario presenta varios puntos finales específicos de integración.</span><span class="sxs-lookup"><span data-stu-id="638e4-180">The public REST API of the of the Inventory Visibility Add-in presents several specific endpoints of integration.</span></span> <span data-ttu-id="638e4-181">Admite tres tipos principales de interacción:</span><span class="sxs-lookup"><span data-stu-id="638e4-181">It supports three main interaction types:</span></span>

- <span data-ttu-id="638e4-182">Publicar cambios disponibles en el complemento desde un sistema externo.</span><span class="sxs-lookup"><span data-stu-id="638e4-182">Posting on-hand changes to the add-in from an external system.</span></span>
- <span data-ttu-id="638e4-183">Consultar cantidades actuales disponibles desde un sistema externo.</span><span class="sxs-lookup"><span data-stu-id="638e4-183">Querying current on-hand quantities from an external system.</span></span>
- <span data-ttu-id="638e4-184">Sincronización automática con Supply Chain Management disponible.</span><span class="sxs-lookup"><span data-stu-id="638e4-184">Automatic synchronization with Supply Chain Management on-hand.</span></span>

<span data-ttu-id="638e4-185">La sincronización automática no forma parte de la API pública, sino que se gestiona en segundo plano para los entornos que han habilitado el complemento de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="638e4-185">The automatic synchronization isn't part of the public API but is instead handled in the background for environments that have enabled the Inventory Visibility Add-in.</span></span>

### <a name="authentication"></a><span data-ttu-id="638e4-186">Autentificación</span><span class="sxs-lookup"><span data-stu-id="638e4-186">Authentication</span></span>

<span data-ttu-id="638e4-187">El token de seguridad de la plataforma se utiliza para llamar al complemento de visibilidad de inventario, por lo que debe generar un token de Azure Active Directory usando su aplicación de Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="638e4-187">The platform security token is used to call the Inventory Visibility Add-in, so you must generate an Azure Active Directory token using your Azure Active Directory application.</span></span>

<span data-ttu-id="638e4-188">Para obtener más información sobre cómo obtener el token de seguridad, consulte [Instalar el complemento de visibilidad de inventario](#install-add-in).</span><span class="sxs-lookup"><span data-stu-id="638e4-188">For more information about how to get the security token, see [Install the Inventory Visibility Add-in](#install-add-in).</span></span>

### <a name="configure-the-inventory-visibility-api"></a><span data-ttu-id="638e4-189">Configurar la API de visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="638e4-189">Configure the Inventory Visibility API</span></span>

<span data-ttu-id="638e4-190">Antes de utilizar el servicio, debe completar las configuraciones descritas en las siguientes subsecciones.</span><span class="sxs-lookup"><span data-stu-id="638e4-190">Before using the service, you must complete the configurations described in the following subsections.</span></span> <span data-ttu-id="638e4-191">La configuración puede variar según los detalles de su entorno.</span><span class="sxs-lookup"><span data-stu-id="638e4-191">The configuration may vary based on the details of your environment.</span></span> <span data-ttu-id="638e4-192">Incluye principalmente cuatro partes:</span><span class="sxs-lookup"><span data-stu-id="638e4-192">It primarily includes four parts:</span></span>

- [<span data-ttu-id="638e4-193">Partición</span><span class="sxs-lookup"><span data-stu-id="638e4-193">Partitioning</span></span>](#partitioning)
- [<span data-ttu-id="638e4-194">Configuraciones de dimensiones</span><span class="sxs-lookup"><span data-stu-id="638e4-194">Dimension configurations</span></span>](#dimension-configurations)
- [<span data-ttu-id="638e4-195">Indexación</span><span class="sxs-lookup"><span data-stu-id="638e4-195">Indexing</span></span>](#indexing)
- [<span data-ttu-id="638e4-196">Medida personalizada</span><span class="sxs-lookup"><span data-stu-id="638e4-196">Custom measurement</span></span>](#custom-measurement)

#### <a name="partitioning"></a><span data-ttu-id="638e4-197">Partición</span><span class="sxs-lookup"><span data-stu-id="638e4-197">Partitioning</span></span>

<span data-ttu-id="638e4-198">El particionamiento puede influir significativamente en el rendimiento de la API de visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="638e4-198">Partitioning can significantly influence the performance of the Inventory Visibility API.</span></span> <span data-ttu-id="638e4-199">Es una buena idea definir un esquema que permita pequeñas agrupaciones de datos y al mismo tiempo permita consultas de datos significativas.</span><span class="sxs-lookup"><span data-stu-id="638e4-199">It's a good idea to define a scheme that allows for small groupings of data while still allowing for meaningful data queries.</span></span>

<span data-ttu-id="638e4-200">`organizationId` (`dataAreaId` en Supply Chain Management) siempre formará parte de la partición y, de forma predeterminada, la Visibilidad de inventario está configurada para particionar por dimensiones como *Sitio + Ubicación*.</span><span class="sxs-lookup"><span data-stu-id="638e4-200">The `organizationId` (`dataAreaId` in Supply Chain Management) will always be part of the partitioning, and by default Inventory Visibility is set to partition by dimensions as *Site + Location*.</span></span> <span data-ttu-id="638e4-201">Esto significa que el servicio siempre debe consultarse con estas dimensiones definidas en los filtros.</span><span class="sxs-lookup"><span data-stu-id="638e4-201">This means that the service must always be queried with these dimensions defined on the filters.</span></span>

> [!NOTE]
> <span data-ttu-id="638e4-202">*Sitio* y *Ubicación* son dos dimensiones predeterminadas generales en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="638e4-202">*Site* and *Location* are two general default dimensions in Inventory Visibility.</span></span> <span data-ttu-id="638e4-203">En Supply Chain Management, esas dimensiones se denominan *Sitio* (`InventSiteId`) y *Almacén* (`InventLocationId`)</span><span class="sxs-lookup"><span data-stu-id="638e4-203">In Supply Chain Management, those dimensions are called *Site* (`InventSiteId`) and *Warehouse* (`InventLocationId`)</span></span>

### <a name="dimension-configurations"></a><span data-ttu-id="638e4-204">Configuraciones de dimensiones</span><span class="sxs-lookup"><span data-stu-id="638e4-204">Dimension configurations</span></span>

<span data-ttu-id="638e4-205">Inventory Visibility proporcionará una lista de dimensiones predeterminadas generales para permitir la integración del sistema de múltiples fuentes.</span><span class="sxs-lookup"><span data-stu-id="638e4-205">Inventory Visibility will provide a list of general default dimensions to enable the multiple source system integration.</span></span>

<span data-ttu-id="638e4-206">La siguiente tabla enumera las dimensiones de inventario que serán los nombres de dimensión predeterminados en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="638e4-206">The following table lists the inventory dimensions that will be the default dimension names in Inventory Visibility.</span></span>

| <span data-ttu-id="638e4-207">Tipo de dimensión</span><span class="sxs-lookup"><span data-stu-id="638e4-207">Dimension type</span></span> | <span data-ttu-id="638e4-208">Nombre de dimensión</span><span class="sxs-lookup"><span data-stu-id="638e4-208">Dimension name</span></span> |
|---|---|
| <span data-ttu-id="638e4-209">Producto</span><span class="sxs-lookup"><span data-stu-id="638e4-209">Product</span></span> | `ColorId` |
| <span data-ttu-id="638e4-210">Producto</span><span class="sxs-lookup"><span data-stu-id="638e4-210">Product</span></span> | `SizeId` |
| <span data-ttu-id="638e4-211">Producto</span><span class="sxs-lookup"><span data-stu-id="638e4-211">Product</span></span> | `StyleId` |
| <span data-ttu-id="638e4-212">Producto</span><span class="sxs-lookup"><span data-stu-id="638e4-212">Product</span></span> | `ConfigId` |
| <span data-ttu-id="638e4-213">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="638e4-213">Tracking</span></span> | `BatchId` |
| <span data-ttu-id="638e4-214">Seguimiento</span><span class="sxs-lookup"><span data-stu-id="638e4-214">Tracking</span></span> | `SerialId` |
| <span data-ttu-id="638e4-215">Ubicación</span><span class="sxs-lookup"><span data-stu-id="638e4-215">Location</span></span> | `LocationId` |
| <span data-ttu-id="638e4-216">Ubicación</span><span class="sxs-lookup"><span data-stu-id="638e4-216">Location</span></span> | `SiteId` |
| <span data-ttu-id="638e4-217">Estado de inventario</span><span class="sxs-lookup"><span data-stu-id="638e4-217">Inventory Status</span></span> | `StatusId` |
| <span data-ttu-id="638e4-218">Específico del almacén</span><span class="sxs-lookup"><span data-stu-id="638e4-218">Warehouse Specific</span></span> | `WMSLocationId` |
| <span data-ttu-id="638e4-219">Específico del almacén</span><span class="sxs-lookup"><span data-stu-id="638e4-219">Warehouse Specific</span></span> | `WMSPalletId` |
| <span data-ttu-id="638e4-220">Específico del almacén</span><span class="sxs-lookup"><span data-stu-id="638e4-220">Warehouse Specific</span></span> | `LicensePlateId` |

> [!NOTE]
> <span data-ttu-id="638e4-221">El tipo de dimensión enumerado en la tabla anterior es solo para referencia.</span><span class="sxs-lookup"><span data-stu-id="638e4-221">The dimension type listed in the previous table is for reference only.</span></span> <span data-ttu-id="638e4-222">No es necesario definir el tipo de dimensión en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="638e4-222">You don't need to define the dimension type in Inventory Visibility.</span></span>

<span data-ttu-id="638e4-223">Si existe una dimensión personalizada y necesita fluir a un valor predeterminado cuando la usa Inventory Visibility, puede configurar el nombre de la **Dimensión personalizada** en Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="638e4-223">If a custom dimension exists and needs to flow to a default value when consumed by Inventory Visibility, you can configure the **Custom dimension** name in Inventory Visibility.</span></span>

<span data-ttu-id="638e4-224">Los sistemas externos acceden a la visibilidad del inventario a través de API RESTful que permiten consultar información disponible sobre conjuntos de dimensiones dados.</span><span class="sxs-lookup"><span data-stu-id="638e4-224">External systems access Inventory Visibility through RESTful APIs that enable on-hand information on given sets of dimensions to be queried.</span></span> <span data-ttu-id="638e4-225">Para la integración, Inventory Visibility le permite configurar el *origen de datos del canal externo* y la dimensión de origen en las *dimensiones objetivo* de Visibilidad de inventario.</span><span class="sxs-lookup"><span data-stu-id="638e4-225">For the integration, Inventory Visibility enables you to configure the *external channel data source* and the source dimension to the *target dimensions* in Inventory Visibility.</span></span>

<span data-ttu-id="638e4-226">Las dimensiones de destino deben ser una de las siguientes:</span><span class="sxs-lookup"><span data-stu-id="638e4-226">The target dimensions should be one of the following:</span></span>

- <span data-ttu-id="638e4-227">Dimensiones predeterminadas en visibilidad de inventario</span><span class="sxs-lookup"><span data-stu-id="638e4-227">Default dimensions in Inventory Visibility</span></span>
- <span data-ttu-id="638e4-228">Dimensiones personalizadas</span><span class="sxs-lookup"><span data-stu-id="638e4-228">Custom dimensions</span></span>

<span data-ttu-id="638e4-229">El propósito de la configuración de dimensiones es estandarizar la integración de múltiples sistemas para la consulta de dimensiones y el evento de publicación con dimensiones.</span><span class="sxs-lookup"><span data-stu-id="638e4-229">The purpose of dimension configuration is to standardize the multi-system integration for the query on dimensions and the posting event with dimensions.</span></span>

#### <a name="indexing"></a><span data-ttu-id="638e4-230">Indexación</span><span class="sxs-lookup"><span data-stu-id="638e4-230">Indexing</span></span>

<span data-ttu-id="638e4-231">La mayoría de las veces, la consulta de inventario disponible no solo estará en el nivel "total" más alto, sino que es posible que desee ver los resultados agregados según las dimensiones del inventario.</span><span class="sxs-lookup"><span data-stu-id="638e4-231">Most of the time, the inventory on-hand query will not only be on the highest "total" level, but you may want to see results aggregated based on the inventory dimensions.</span></span>

<span data-ttu-id="638e4-232">La visibilidad de inventario proporciona flexibilidad al permitirle configurar los índices, que se basan en la dimensión o la combinación de las dimensiones.</span><span class="sxs-lookup"><span data-stu-id="638e4-232">Inventory Visibility provides flexibility by allowing you to set up the indexes, which are based on the dimension or the combination of the dimensions.</span></span>

> [!NOTE]
> <span data-ttu-id="638e4-233">Actualmente, solo puede configurar índices hasta un máximo de cinco.</span><span class="sxs-lookup"><span data-stu-id="638e4-233">Currently, you can only configure indexes to a maximum of five.</span></span> <span data-ttu-id="638e4-234">Debe considerar cuidadosamente qué dimensión o combinación de dimensiones utilizará antes de la implementación para asegurarse de que satisfará sus necesidades comerciales.</span><span class="sxs-lookup"><span data-stu-id="638e4-234">You need to carefully consider which dimension or dimension combination you will use before the implementation to ensure that it will meet your business needs.</span></span> <span data-ttu-id="638e4-235">Por ejemplo, si desea consultar productos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="638e4-235">For example, if you want to query products as follows:</span></span>

- <span data-ttu-id="638e4-236">Consultar el producto agregado disponible por dimensiones *Color* y *Talla*.</span><span class="sxs-lookup"><span data-stu-id="638e4-236">Query the aggregated product on-hand by the *Color* and *Size* dimensions.</span></span>
- <span data-ttu-id="638e4-237">En algunos casos, solo desea consultar el producto en total.</span><span class="sxs-lookup"><span data-stu-id="638e4-237">In some cases, you just want to query on the product in total.</span></span>

<span data-ttu-id="638e4-238">Tendría dos índices definidos de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="638e4-238">You would have two indexes defined as the following:</span></span>

- `["ColorId", "SizeId"]`
- `[]`

<span data-ttu-id="638e4-239">El corchete vacío se agregará según el ID del producto dentro de la partición.</span><span class="sxs-lookup"><span data-stu-id="638e4-239">The empty bracket will aggregate based on the product ID within the partition.</span></span>

<span data-ttu-id="638e4-240">La indexación define cómo puede agrupar sus resultados en función de la configuración de consulta `groupBy`.</span><span class="sxs-lookup"><span data-stu-id="638e4-240">The indexing defines how you can group your results based on the `groupBy` query setting.</span></span> <span data-ttu-id="638e4-241">En este caso, si no define valores para `groupBy`, obtendrá totales por `productid`.</span><span class="sxs-lookup"><span data-stu-id="638e4-241">In this case if you don't define any `groupBy` values, you'll get totals by `productid`.</span></span> <span data-ttu-id="638e4-242">De lo contrario, si define `groupBy` como `groupBy=ColorId&groupBy=SizeId`, obtendrá varias líneas devueltas, según las diferentes combinaciones de colores y tamaños en el sistema.</span><span class="sxs-lookup"><span data-stu-id="638e4-242">Otherwise if you define `groupBy` as `groupBy=ColorId&groupBy=SizeId`, you'll get multiple lines returned, based on the different color and size combinations in the system.</span></span>

<span data-ttu-id="638e4-243">Puede poner sus criterios de consulta en el cuerpo de la solicitud.</span><span class="sxs-lookup"><span data-stu-id="638e4-243">You can put your query criteria in the request body.</span></span>

<span data-ttu-id="638e4-244">Aquí hay una consulta de muestra sobre el producto con combinación de color y tamaño.</span><span class="sxs-lookup"><span data-stu-id="638e4-244">Here is a sample query on the product with color and size combination.</span></span>

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

#### <a name="custom-measurement"></a><span data-ttu-id="638e4-245">Medida personalizada</span><span class="sxs-lookup"><span data-stu-id="638e4-245">Custom measurement</span></span>

<span data-ttu-id="638e4-246">Las cantidades de medición predeterminadas están vinculadas a Supply Chain Management; sin embargo, es posible que desee tener una cantidad que se componga de una combinación de las mediciones predeterminadas.</span><span class="sxs-lookup"><span data-stu-id="638e4-246">The default measurement quantities are linked to Supply Chain Management, however you may want to have a quantity that is made up of a combination of the default measurements.</span></span> <span data-ttu-id="638e4-247">Para hacer esto, puede tener una configuración de cantidades personalizadas, que se agregarán a la salida de las consultas disponibles.</span><span class="sxs-lookup"><span data-stu-id="638e4-247">To do this, you can have a configuration of custom quantities, which will be added to the output of the on-hand queries.</span></span>

<span data-ttu-id="638e4-248">La funcionalidad simplemente le permite definir un conjunto de medidas que se agregarán, y / o un conjunto de medidas que se restarán, a partir de la medida personalizada.</span><span class="sxs-lookup"><span data-stu-id="638e4-248">The functionality simply allows you to define a set of measures that will be added, and/or a set of measures that will be subtracted, in order to form the custom measurement.</span></span>

<span data-ttu-id="638e4-249">Por ejemplo, con la siguiente condición de consulta, configurará la cantidad de medida personalizada como `MyCustomAvailableforReservation` para ser consumido por el sistema de consumo.</span><span class="sxs-lookup"><span data-stu-id="638e4-249">For example, with the following query condition, you will configure the custom measurement quantity as `MyCustomAvailableforReservation` to be consumed by the consumption system.</span></span>

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



| <span data-ttu-id="638e4-250">Sistema de consumo</span><span class="sxs-lookup"><span data-stu-id="638e4-250">Consumption system</span></span> | <span data-ttu-id="638e4-251">Medidas calculadas</span><span class="sxs-lookup"><span data-stu-id="638e4-251">Calculated measurers</span></span> | <span data-ttu-id="638e4-252">Origen de datos</span><span class="sxs-lookup"><span data-stu-id="638e4-252">Data source</span></span> | <span data-ttu-id="638e4-253">Modificador</span><span class="sxs-lookup"><span data-stu-id="638e4-253">Modifier</span></span> | <span data-ttu-id="638e4-254">Tipo de cálculo del modificador</span><span class="sxs-lookup"><span data-stu-id="638e4-254">Modifier calculation type</span></span> |
|---|---|---|---|---|
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `availphysical` | <span data-ttu-id="638e4-255">Adición</span><span class="sxs-lookup"><span data-stu-id="638e4-255">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedintotal` | <span data-ttu-id="638e4-256">Adición</span><span class="sxs-lookup"><span data-stu-id="638e4-256">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `fno` | `orderedreserved` | <span data-ttu-id="638e4-257">Resta</span><span class="sxs-lookup"><span data-stu-id="638e4-257">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `inbound` | <span data-ttu-id="638e4-258">Adición</span><span class="sxs-lookup"><span data-stu-id="638e4-258">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `mypos` | `outbound` | <span data-ttu-id="638e4-259">Resta</span><span class="sxs-lookup"><span data-stu-id="638e4-259">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `received` | <span data-ttu-id="638e4-260">Adición</span><span class="sxs-lookup"><span data-stu-id="638e4-260">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `scheduled` | <span data-ttu-id="638e4-261">Adición</span><span class="sxs-lookup"><span data-stu-id="638e4-261">Addition</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `issued` | <span data-ttu-id="638e4-262">Resta</span><span class="sxs-lookup"><span data-stu-id="638e4-262">Subtraction</span></span> |
| `CustomChannel` | `MyCustomAvailableforReservation` | `exterchannel` | `reserved` | <span data-ttu-id="638e4-263">Resta</span><span class="sxs-lookup"><span data-stu-id="638e4-263">Subtraction</span></span> |

<span data-ttu-id="638e4-264">Con eso, la consulta sobre la cantidad de medición personalizada devolverá el siguiente resultado.</span><span class="sxs-lookup"><span data-stu-id="638e4-264">With that, the query on the custom measurement quantity will return the following output.</span></span>

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

<span data-ttu-id="638e4-265">La salida `MyCustomAvailableforReservation` se basa en la configuración de cálculo en las medidas personalizadas como:</span><span class="sxs-lookup"><span data-stu-id="638e4-265">The `MyCustomAvailableforReservation` output is based on the calculation setting in the custom measurements as:</span></span>  
 <span data-ttu-id="638e4-266">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span><span class="sxs-lookup"><span data-stu-id="638e4-266">*100 + 50 + 80 + 90 + 30 &ndash; 10 &ndash; 20 &ndash; 60 &ndash; 40 = 220*</span></span>

### <a name="posting-on-hand-changes"></a><span data-ttu-id="638e4-267">Publicar cambios disponibles</span><span class="sxs-lookup"><span data-stu-id="638e4-267">Posting on-hand changes</span></span>

<span data-ttu-id="638e4-268">La URL exacta en la que se publicará el evento dependerá de su región geográfica.</span><span class="sxs-lookup"><span data-stu-id="638e4-268">The exact URL that the event will be posted to will depend on your geographical region.</span></span> <span data-ttu-id="638e4-269">Tomará la forma:</span><span class="sxs-lookup"><span data-stu-id="638e4-269">It will take the form:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand`

<span data-ttu-id="638e4-270">Cuando se autentica, esta URL se puede utilizar junto con el método HTTP `POST` para enviar eventos de cambio disponibles al servicio.</span><span class="sxs-lookup"><span data-stu-id="638e4-270">When authenticated, this URL can be used along with the HTTP `POST` method to send on-hand change events to the service.</span></span>

<span data-ttu-id="638e4-271">Se usa un encabezado especial para comunicarse con los servicios de Dynamics 365 a través de solicitudes HTTP, que denota el Id. De entorno de la instancia de Supply Chain Management a la que están vinculados los datos.</span><span class="sxs-lookup"><span data-stu-id="638e4-271">A special header is used for communicating with Dynamics 365 services through HTTP requests, denoting the environment ID of the Supply Chain Management instance the data is linked to.</span></span> <span data-ttu-id="638e4-272">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="638e4-272">For example:</span></span>

`x-ms-environment-id: 2db79622-f97a-4d64-9844-d12efed41796`

#### <a name="posting-on-hand-changes-query-example-1"></a><span data-ttu-id="638e4-273">Publicación de cambios disponibles ejemplo de consulta 1</span><span class="sxs-lookup"><span data-stu-id="638e4-273">Posting on-hand changes query example 1</span></span>

<span data-ttu-id="638e4-274">Este ejemplo muestra un escenario en el que establecerá la configuración de dimensión en Power Apps.</span><span class="sxs-lookup"><span data-stu-id="638e4-274">This example shows a scenario where you will set up the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="638e4-275">Utilice la siguiente consulta para configurar la asignación de dimensiones en Power Apps:</span><span class="sxs-lookup"><span data-stu-id="638e4-275">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="638e4-276">Ahora puede especificar `dimensionDataSource` y usar dimensiones personalizadas en sus consultas.</span><span class="sxs-lookup"><span data-stu-id="638e4-276">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="638e4-277">El sistema convertirá automáticamente las dimensiones personalizadas en dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="638e4-277">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="posting-on-hand-changes-query-example-2"></a><span data-ttu-id="638e4-278">Publicación de cambios disponibles ejemplo de consulta 2</span><span class="sxs-lookup"><span data-stu-id="638e4-278">Posting on-hand changes query example 2</span></span>

<span data-ttu-id="638e4-279">Este ejemplo muestra un escenario en el que no se establecen asignaciones para la configuración de dimensión en Power Apps, por lo que la publicación también debe usar las dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="638e4-279">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="638e4-280">Todas las dimensiones deben ser dimensiones base cuando el campo `dimensionDataSource` es nulo, vacío o espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="638e4-280">All dimensions must be base dimensions when the `dimensionDataSource` field is null, empty, or whitespace.</span></span>

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

#### <a name="json-document-field-properties"></a><span data-ttu-id="638e4-281">Propiedades de campo de documento JSON</span><span class="sxs-lookup"><span data-stu-id="638e4-281">JSON document field properties</span></span>

<span data-ttu-id="638e4-282">Los campos de los ejemplos de consultas JSON proporcionados anteriormente tienen las propiedades enumeradas en la siguiente tabla.</span><span class="sxs-lookup"><span data-stu-id="638e4-282">The fields from the JSON query examples provided previously have the properties listed in the following table.</span></span>

| <span data-ttu-id="638e4-283">Id. del campo</span><span class="sxs-lookup"><span data-stu-id="638e4-283">Field ID</span></span> | <span data-ttu-id="638e4-284">Descripción</span><span class="sxs-lookup"><span data-stu-id="638e4-284">Description</span></span> |
|---|---|
| `id` | <span data-ttu-id="638e4-285">Un ID único para el evento de cambio específico.</span><span class="sxs-lookup"><span data-stu-id="638e4-285">A unique ID for the specific change event.</span></span> <span data-ttu-id="638e4-286">Este ID se utiliza para garantizar que si la comunicación con el servicio falla durante la publicación, volver a enviar el evento no resultará en que el mismo evento se cuente dos veces en el sistema.</span><span class="sxs-lookup"><span data-stu-id="638e4-286">This ID is used to ensure that if communication with the service fails during posting, resubmitting the event would not result in the same event being counted twice in the system.</span></span> |
| `organizationId` | <span data-ttu-id="638e4-287">El identificador de la organización vinculada al evento.</span><span class="sxs-lookup"><span data-stu-id="638e4-287">The identifier of the organization linked to the event.</span></span> <span data-ttu-id="638e4-288">Esto se asigna a las organizaciones de Supply Chain Management o los ID de área de datos.</span><span class="sxs-lookup"><span data-stu-id="638e4-288">This maps to Supply Chain Management organizations or data area IDs.</span></span> |
| `productId` | <span data-ttu-id="638e4-289">El identificador del producto en cuestión.</span><span class="sxs-lookup"><span data-stu-id="638e4-289">The identifier of the product in question.</span></span> |
| `quantity` | <span data-ttu-id="638e4-290">La cantidad por la que se debe cambiar el producto disponible.</span><span class="sxs-lookup"><span data-stu-id="638e4-290">The quantity by which the on-hand needs to be changed.</span></span> <span data-ttu-id="638e4-291">Si, por ejemplo, se añadieran 10 bagels nuevos a un estante, este valor sería 10.</span><span class="sxs-lookup"><span data-stu-id="638e4-291">If, for instance, 10 new bagels were added to a shelf, this value would be 10.</span></span> <span data-ttu-id="638e4-292">Si luego se sacaran 3 bagels del estante o se vendieran, este valor sería -3.</span><span class="sxs-lookup"><span data-stu-id="638e4-292">If 3 bagels were then removed from the shelf or sold, this value would be -3.</span></span> |
| `dimensionDataSource` | <span data-ttu-id="638e4-293">La fuente de datos de las dimensiones utilizadas en la consulta y el evento de cambio de publicación.</span><span class="sxs-lookup"><span data-stu-id="638e4-293">The data source of the dimensions used in the posting change event and query.</span></span> <span data-ttu-id="638e4-294">Si especifica la fuente de datos, puede utilizar las dimensiones personalizadas de la fuente de datos especificada.</span><span class="sxs-lookup"><span data-stu-id="638e4-294">If you specify the data source, you can use the custom dimensions from the specified data source.</span></span> <span data-ttu-id="638e4-295">Con la configuración de dimensión, Inventory Visibility puede asignar las dimensiones personalizadas a las dimensiones predeterminadas generales.</span><span class="sxs-lookup"><span data-stu-id="638e4-295">With the dimension configuration, Inventory Visibility can map the custom dimensions to the general default dimensions.</span></span> <span data-ttu-id="638e4-296">Si no se especifica `dimensionDataSource`, solo puede utilizar las dimensiones predeterminadas generales en sus consultas.</span><span class="sxs-lookup"><span data-stu-id="638e4-296">If the `dimensionDataSource` is not specified, you can only use the general default dimensions in your queries.</span></span>   |
| `dimensions` | <span data-ttu-id="638e4-297">Una bolsa dinámica de pares clave / valor.</span><span class="sxs-lookup"><span data-stu-id="638e4-297">A dynamic bag of key/value pairs.</span></span> <span data-ttu-id="638e4-298">Estos se asignarán a algunas de las dimensiones en Supply Chain Management, pero también puede agregar dimensiones personalizadas (como *Origen*) que puede indicar si el evento provenía de Supply Chain Management o de un sistema externo.</span><span class="sxs-lookup"><span data-stu-id="638e4-298">These will map to some of the dimensions in Supply Chain Management, but you could also add custom dimensions (like *Source*) that may denote if the event was coming from Supply Chain Management or an external system.</span></span> |

### <a name="querying-current-on-hand"></a><span data-ttu-id="638e4-299">Consultando la corriente disponible</span><span class="sxs-lookup"><span data-stu-id="638e4-299">Querying current on-hand</span></span>

<span data-ttu-id="638e4-300">El punto final para consultar el actual disponible tendrá una URL similar:</span><span class="sxs-lookup"><span data-stu-id="638e4-300">The endpoint for querying the current on-hand will have a similar URL:</span></span>

`https://{serviceURL}/api/environment/{environmentId}/onhand/indexquery`

<span data-ttu-id="638e4-301">Se consultará con el método HTTP `POST`.</span><span class="sxs-lookup"><span data-stu-id="638e4-301">It will be queried with the HTTP `POST` method.</span></span>

#### <a name="current-on-hand-query-example-1"></a><span data-ttu-id="638e4-302">Ejemplo 1 de consulta actual disponible</span><span class="sxs-lookup"><span data-stu-id="638e4-302">Current on-hand query example 1</span></span>

<span data-ttu-id="638e4-303">Este ejemplo muestra un escenario en el que ya ha completado la configuración de dimensión en Power Apps.</span><span class="sxs-lookup"><span data-stu-id="638e4-303">This example shows a scenario where you have already completed the dimension configuration in Power Apps.</span></span>

<span data-ttu-id="638e4-304">Utilice la siguiente consulta para configurar la asignación de dimensiones en Power Apps:</span><span class="sxs-lookup"><span data-stu-id="638e4-304">Use the following query to configure the dimension mapping in Power Apps:</span></span>

```json
{
    "PosSizeId": "SizeId",
    "PosColorId": "ColorId",
    "PosSiteId": "SiteId",
    "PosLocationId": "LocationId"
}
```

<span data-ttu-id="638e4-305">Ahora puede especificar `dimensionDataSource` y usar dimensiones personalizadas en sus consultas.</span><span class="sxs-lookup"><span data-stu-id="638e4-305">Now you can specify the `dimensionDataSource` and use custom dimensions in your queries.</span></span> <span data-ttu-id="638e4-306">El sistema convertirá automáticamente las dimensiones personalizadas en dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="638e4-306">The system will automatically convert custom dimensions to base dimensions.</span></span> <span data-ttu-id="638e4-307">Puede especificar `DimensionDataSource` en `filters` y especificar dimensiones personalizadas en `filters` y `groupByValues`.</span><span class="sxs-lookup"><span data-stu-id="638e4-307">You can specify the `DimensionDataSource` in `filters` and specify custom dimensions in both `filters` and `groupByValues`.</span></span> <span data-ttu-id="638e4-308">El sistema convertirá automáticamente las dimensiones personalizadas en dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="638e4-308">The system will automatically convert custom dimensions to base dimensions.</span></span>

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

#### <a name="current-on-hand-query-example-2"></a><span data-ttu-id="638e4-309">Ejemplo 2 de consulta actual disponible</span><span class="sxs-lookup"><span data-stu-id="638e4-309">Current on-hand query example 2</span></span>

<span data-ttu-id="638e4-310">Este ejemplo muestra un escenario en el que no se establecen asignaciones para la configuración de dimensión en Power Apps, por lo que la publicación también debe usar las dimensiones base.</span><span class="sxs-lookup"><span data-stu-id="638e4-310">This example shows a scenario where no mappings are set up for the dimension configuration in Power Apps, so the posting should also use the base dimensions.</span></span> <span data-ttu-id="638e4-311">Todas las dimensiones deben ser dimensiones base cuando el campo `dimensionDataSource`, bajo `filters`, es nulo, vacío o espacio en blanco.</span><span class="sxs-lookup"><span data-stu-id="638e4-311">All dimensions must be base dimensions when the `dimensionDataSource` field, under `filters` is null, empty, or whitespace.</span></span>

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

#### <a name="example-return-result"></a><span data-ttu-id="638e4-312">Resultado devuelto de ejemplo</span><span class="sxs-lookup"><span data-stu-id="638e4-312">Example return result</span></span>

<span data-ttu-id="638e4-313">Las consultas que se muestran en los ejemplos anteriores podrían devolver un resultado como este.</span><span class="sxs-lookup"><span data-stu-id="638e4-313">The queries shown in the previous examples could return a result like this.</span></span>

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

<span data-ttu-id="638e4-314">Tenga en cuenta que los campos de cantidades están estructurados como un diccionario de medidas y sus valores asociados.</span><span class="sxs-lookup"><span data-stu-id="638e4-314">Note that the quantities fields are structured as a dictionary of measures and their associated values.</span></span>
