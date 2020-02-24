---
title: Agregar soporte para una red de entrega de contenido (CDN)
description: Este tema describe cómo agregar una red de entrega de contenido (CDN) a su entorno de Microsoft Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: bf5a0da2803f985e6c0c04dd9916977397173d11
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3001631"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a><span data-ttu-id="5b942-103">Agregar soporte para una red de entrega de contenido (CDN)</span><span class="sxs-lookup"><span data-stu-id="5b942-103">Add support for a content delivery network (CDN)</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="5b942-104">Este tema describe cómo agregar una red de entrega de contenido (CDN) a su entorno de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5b942-104">This topic describes how to add a content delivery network (CDN) to your Microsoft Dynamics 365 Commerce environment.</span></span>

## <a name="overview"></a><span data-ttu-id="5b942-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="5b942-105">Overview</span></span>

<span data-ttu-id="5b942-106">Al configurar un entorno de comercio electrónico en Dynamics 365 Commerce, puede definirlo para trabajar con su servicio de CDN.</span><span class="sxs-lookup"><span data-stu-id="5b942-106">When you set up an e-Commerce environment in Dynamics 365 Commerce, you can configure it to work with your CDN service.</span></span> 

<span data-ttu-id="5b942-107">Su dominio personalizado se puede habilitar durante el proceso de aprovisionamiento para su entorno de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="5b942-107">Your custom domain can be enabled during the provisioning process for your e-Commerce environment.</span></span> <span data-ttu-id="5b942-108">Como alternativa, puede usar una solicitud de servicio para configurarlo una vez que se ha completado el proceso de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="5b942-108">Alternatively, you can use a service request to set it up after the provisioning process is completed.</span></span> <span data-ttu-id="5b942-109">El proceso de aprovisionamiento para el entorno de comercio electrónico genera un nombre de host que esté asociado al entorno.</span><span class="sxs-lookup"><span data-stu-id="5b942-109">The provisioning process for the e-Commerce environment generates a host name that is associated with the environment.</span></span> <span data-ttu-id="5b942-110">Este nombre de host tiene el siguiente formato, donde *nombre-inquilino-comercio-electrónico* es el nombre del entorno:</span><span class="sxs-lookup"><span data-stu-id="5b942-110">This host name has the following format, where *e-commerce-tenant-name* is the name of your environment:</span></span>

<span data-ttu-id="5b942-111">&lt;nombre-inquilino-comercio-electrónico&gt;.commerce.dynamics.com</span><span class="sxs-lookup"><span data-stu-id="5b942-111">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span></span>

<span data-ttu-id="5b942-112">El nombre de host o el extremo que se genera durante el proceso de aprovisionamiento admite un certificado de capa de sockets seguros (SSL) solo para \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="5b942-112">The host name or endpoint that is generated during the provisioning process supports a Secure Sockets Layer (SSL) certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="5b942-113">No admite SSL para dominios personalizados.</span><span class="sxs-lookup"><span data-stu-id="5b942-113">It doesn't support SSL for custom domains.</span></span> <span data-ttu-id="5b942-114">Por lo tanto, debe finalizar SSL para los dominios personalizados en su CDN y reenviar el tráfico desde la CDN al nombre de host o extremo que Commerce generó.</span><span class="sxs-lookup"><span data-stu-id="5b942-114">Therefore, you must terminate SSL for custom domains in your CDN and forward traffic from the CDN to the host name or endpoint that Commerce generated.</span></span> 

<span data-ttu-id="5b942-115">Además, los (archivos JavaScript o de hojas de estilo CSS \[CSS\] ) *estáticos* de Commerce se sirven desde el extremo que Commerce generó (\*.commerce.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="5b942-115">Additionally, the *statics* (JavaScript or Cascading Style Sheets \[CSS\] files) from Commerce are served from the endpoint that Commerce generated (\*.commerce.dynamics.com).</span></span> <span data-ttu-id="5b942-116">La estática solo se puede almacenar en caché si el nombre de host o extremo que Commerce generó se coloca detrás de la CDN.</span><span class="sxs-lookup"><span data-stu-id="5b942-116">The statics can be cached only if the host name or endpoint that Commerce generated is put behind the CDN.</span></span>

## <a name="set-up-ssl"></a><span data-ttu-id="5b942-117">Configurar SSL</span><span class="sxs-lookup"><span data-stu-id="5b942-117">Set up SSL</span></span>

<span data-ttu-id="5b942-118">Para ayudar a garantizar que SSL está configurado, y que la estática se almacena en caché, debe configurar su CDN para que se asocie al nombre de host que Commerce generó para su entorno.</span><span class="sxs-lookup"><span data-stu-id="5b942-118">To help guarantee that SSL is set up, and that statics are cached, you must configure your CDN so that it is associated with the host name that Commerce generated for your environment.</span></span> <span data-ttu-id="5b942-119">También debe almacenar en caché el siguiente patrón solo para estática:</span><span class="sxs-lookup"><span data-stu-id="5b942-119">You must also cache the following pattern for statics only:</span></span> 

<span data-ttu-id="5b942-120">/\_msdyn365/\_scnr/\*</span><span class="sxs-lookup"><span data-stu-id="5b942-120">/\_msdyn365/\_scnr/\*</span></span>

<span data-ttu-id="5b942-121">Tras aprovisionar su entorno de Commerce con el dominio personalizado que se proporciona, o una vez que proporciona el dominio personalizado para su entorno usando una solicitud de servicio, apunte su dominio personalizado al nombre de host o extremo que Commerce generó.</span><span class="sxs-lookup"><span data-stu-id="5b942-121">After you provision your Commerce environment with the custom domain that is provided, or after you provide the custom domain for your environment by using a service request, point your custom domain to the host name or endpoint that Commerce generated.</span></span>

<span data-ttu-id="5b942-122">Como se ha mencionado anteriormente, el nombre de host o extremo generado admite un certificado SSL solo para \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="5b942-122">As was previously mentioned, the generated host name or endpoint supports an SSL certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="5b942-123">No admite SSL para dominios personalizados.</span><span class="sxs-lookup"><span data-stu-id="5b942-123">It doesn't support SSL for custom domains.</span></span>

## <a name="cdn-services"></a><span data-ttu-id="5b942-124">Servicios CDN</span><span class="sxs-lookup"><span data-stu-id="5b942-124">CDN services</span></span>

<span data-ttu-id="5b942-125">Cualquier servicio de CDN se puede usar con un entorno de Commerce.</span><span class="sxs-lookup"><span data-stu-id="5b942-125">Any CDN service can be used with a Commerce environment.</span></span> <span data-ttu-id="5b942-126">Estos son dos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="5b942-126">Here are two examples:</span></span>

- <span data-ttu-id="5b942-127">**Microsoft Azure Front Door Service**: la solución de CDN de Azure.</span><span class="sxs-lookup"><span data-stu-id="5b942-127">**Microsoft Azure Front Door Service** – The Azure CDN solution.</span></span> <span data-ttu-id="5b942-128">Para obtener más información acerca de Azure Front Door Service, consulte [Documentación de Azure Front Door Service](https://docs.microsoft.com/azure/frontdoor/).</span><span class="sxs-lookup"><span data-stu-id="5b942-128">For more information about Azure Front Door Service, see [Azure Front Door Service Documentation](https://docs.microsoft.com/azure/frontdoor/).</span></span>
- <span data-ttu-id="5b942-129">**Acelerador de sitios dinámicos de Akamai**: para obtener más información, consulte [Acelerador de sitios dinámicos](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span><span class="sxs-lookup"><span data-stu-id="5b942-129">**Akamai Dynamic Site Accelerator** – For more information, see [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span></span>

## <a name="cdn-setup"></a><span data-ttu-id="5b942-130">Configuración de CDN</span><span class="sxs-lookup"><span data-stu-id="5b942-130">CDN setup</span></span>

<span data-ttu-id="5b942-131">El proceso de configuración de CDN consta de estos pasos generales:</span><span class="sxs-lookup"><span data-stu-id="5b942-131">The CDN setup process consists of these general steps:</span></span>

1. <span data-ttu-id="5b942-132">Agregue un host front-end.</span><span class="sxs-lookup"><span data-stu-id="5b942-132">Add a front-end host.</span></span>
1. <span data-ttu-id="5b942-133">Configurar un grupo back-end.</span><span class="sxs-lookup"><span data-stu-id="5b942-133">Configure a back-end pool.</span></span>
1. <span data-ttu-id="5b942-134">Configurar reglas para enrutamiento y almacenamiento en caché.</span><span class="sxs-lookup"><span data-stu-id="5b942-134">Set up rules for routing and caching.</span></span>

### <a name="add-a-front-end-host"></a><span data-ttu-id="5b942-135">Agregar un host front-end</span><span class="sxs-lookup"><span data-stu-id="5b942-135">Add a front-end host</span></span>

<span data-ttu-id="5b942-136">Se puede usar cualquier servicio de CDN, pero para el ejemplo que se muestra en este tema, se usa Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="5b942-136">Any CDN service can be used, but for the example in this topic, Azure Front Door Service is used.</span></span> 

<span data-ttu-id="5b942-137">Para obtener información acerca de cómo configurar Azure Front Door Service, consulte [Inicio rápido: crear una puerta delantera para una aplicación web global de alta disponibilidad](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span><span class="sxs-lookup"><span data-stu-id="5b942-137">For information about how to set up Azure Front Door Service, see [Quickstart: Create a Front Door for a highly available global web application](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span></span>

### <a name="configure-a-back-end-pool-in-azure-front-door-service"></a><span data-ttu-id="5b942-138">Configurar un grupo back-end en Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="5b942-138">Configure a back-end pool in Azure Front Door Service</span></span>

<span data-ttu-id="5b942-139">Para configurar un grupo back-end en Azure Front Door Service, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="5b942-139">To configure a back-end pool in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="5b942-140">Agregue **&lt;nombre-comercio-electrónico-inquilino&gt;.commerce.dynamics.com** a un grupo back-end como host personalizado que tenga un encabezado de host de back-end vacío.</span><span class="sxs-lookup"><span data-stu-id="5b942-140">Add **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** to a back-end pool as a custom host that has an empty back-end host header.</span></span>
1. <span data-ttu-id="5b942-141">En **Sondeos de estado**, en el campo **Ruta**, especifique **/keepalive**.</span><span class="sxs-lookup"><span data-stu-id="5b942-141">Under **Health probes**, in the **Path** field, enter **/keepalive**.</span></span>
1. <span data-ttu-id="5b942-142">En el campo **Intervalos (segundos)**, especifique **255**.</span><span class="sxs-lookup"><span data-stu-id="5b942-142">In the **Intervals (seconds)** field, enter **255**.</span></span>
1. <span data-ttu-id="5b942-143">En **Equilibrio de carga**, deje los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="5b942-143">Under **Load balancing**, leave the default values.</span></span>

<span data-ttu-id="5b942-144">En la ilustración siguiente se muestra el cuadro de diálogo **Agregar un grupo back-end** en Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="5b942-144">The following illustration shows the **Add a backend pool** dialog box in Azure Front Door Service.</span></span>

![Cuadro de diálogo Agregar un grupo back-end](./media/CDN_BackendPool.png)

### <a name="set-up-rules-in-azure-front-door-service"></a><span data-ttu-id="5b942-146">Configurar reglas en Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="5b942-146">Set up rules in Azure Front Door Service</span></span>

<span data-ttu-id="5b942-147">Para configurar una regla de ruta en Azure Front Door Service, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="5b942-147">To set up a routing rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="5b942-148">Agregar una regla de ruta.</span><span class="sxs-lookup"><span data-stu-id="5b942-148">Add a routing rule.</span></span>
1. <span data-ttu-id="5b942-149">En el campo **Nombre**, especifique **predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="5b942-149">In the **Name** field, enter **default**.</span></span>
1. <span data-ttu-id="5b942-150">En el campo **Protocolo aceptado**, seleccione **HTTP y HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="5b942-150">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="5b942-151">En el campo **Hosts de front-end**, especifique **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="5b942-151">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="5b942-152">En **Patrones de coincidencia**, en el campo superior, especifique **/\***.</span><span class="sxs-lookup"><span data-stu-id="5b942-152">Under **Patterns to match**, in the upper field, enter **/\***.</span></span>
1. <span data-ttu-id="5b942-153">En **Detalles de ruta**, establezca la opción **Tipo de ruta** en **Reenviar**.</span><span class="sxs-lookup"><span data-stu-id="5b942-153">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="5b942-154">En el campo **Grupo back-end**, seleccione **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="5b942-154">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="5b942-155">En el grupo del campo **Protocolo de reenvío**, seleccione la opción **Confrontar solicitud**.</span><span class="sxs-lookup"><span data-stu-id="5b942-155">In the **Forwarding protocol** field group, select the **Match request** option.</span></span> 
1. <span data-ttu-id="5b942-156">Establezca la opción **URL Rewrite** en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="5b942-156">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="5b942-157">Establezca la opción **Memoria caché** en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="5b942-157">Set the **Caching** option to **Disabled**.</span></span>

<span data-ttu-id="5b942-158">Para configurar una regla de almacenamiento en caché en Azure Front Door Service, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="5b942-158">To set up a caching rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="5b942-159">Agregue una regla de almacenamiento en caché.</span><span class="sxs-lookup"><span data-stu-id="5b942-159">Add a caching rule.</span></span>
1. <span data-ttu-id="5b942-160">En el campo **Nombre**, especifique **estática**.</span><span class="sxs-lookup"><span data-stu-id="5b942-160">In the **Name** field, enter **statics**.</span></span>
1. <span data-ttu-id="5b942-161">En el campo **Protocolo aceptado**, seleccione **HTTP y HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="5b942-161">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="5b942-162">En el campo **Hosts de front-end**, especifique **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="5b942-162">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="5b942-163">En **Patrones de coincidencia**, en el campo superior, especifique **/\_msdyn365/\_scnr/\***.</span><span class="sxs-lookup"><span data-stu-id="5b942-163">Under **Patterns to match**, in the upper field, **/\_msdyn365/\_scnr/\***.</span></span>
1. <span data-ttu-id="5b942-164">En **Detalles de ruta**, establezca la opción **Tipo de ruta** en **Reenviar**.</span><span class="sxs-lookup"><span data-stu-id="5b942-164">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="5b942-165">En el campo **Grupo back-end**, seleccione **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="5b942-165">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="5b942-166">En el grupo del campo **Protocolo de reenvío**, seleccione la opción **Confrontar solicitud**.</span><span class="sxs-lookup"><span data-stu-id="5b942-166">In the **Forwarding protocol** field group, select the **Match request** option.</span></span>
1. <span data-ttu-id="5b942-167">Establezca la opción **URL Rewrite** en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="5b942-167">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="5b942-168">Establezca la opción **Memoria caché** en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="5b942-168">Set the **Caching** option to **Disabled**.</span></span>
1. <span data-ttu-id="5b942-169">En el campo **Comportamiento del almacenamiento en caché de cadenas de consulta**, seleccione **Almacenar en caché todas las URL únicas**.</span><span class="sxs-lookup"><span data-stu-id="5b942-169">In the **Query string caching behavior** field, select **Cache every unique URL**.</span></span>
1. <span data-ttu-id="5b942-170">En el grupo del campo **Compresión dinámica**, seleccione la opción **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="5b942-170">In the **Dynamic compression** field group, select the **Enabled** option.</span></span>

<span data-ttu-id="5b942-171">En la ilustración siguiente se muestra el cuadro de diálogo **Agregar una regla** en Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="5b942-171">The following illustration shows the **Add a rule** dialog box in Azure Front Door Service.</span></span>

![Cuadro de diálogo Agregar una regla](./media/CDN_CachingRule.png)

<span data-ttu-id="5b942-173">Tras la implementación de esta configuración inicial, debe agregar su dominio personalizado a la configuración para Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="5b942-173">After this initial configuration is deployed, you must add your custom domain to the configuration for Azure Front Door Service.</span></span> <span data-ttu-id="5b942-174">Para agregar el dominio personalizado (por ejemplo, `www.fabrikam.com`), debe configurar un nombre canónico (CNAME) para el dominio.</span><span class="sxs-lookup"><span data-stu-id="5b942-174">To add the custom domain (for example, `www.fabrikam.com`), you must configure a Canonical Name (CNAME) for the domain.</span></span>

<span data-ttu-id="5b942-175">En la ilustración siguiente se muestra el cuadro de diálogo **Configuración de CNAME** en Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="5b942-175">The following illustration shows the **CNAME configuration** dialog box in Azure Front Door Service.</span></span>

![Cuadro de diálogo Configuración de CNAME](./media/CNAME_Configuration.png)

> [!NOTE]
> <span data-ttu-id="5b942-177">Si el dominio que usará ya está activo, póngase en contacto con soporte técnico para habilitar este dominio con Azure Front Door Service para configurar una prueba.</span><span class="sxs-lookup"><span data-stu-id="5b942-177">If the domain that you will use is already active and live, contact support to enable this domain with Azure Front Door Service to set up a test.</span></span>

<span data-ttu-id="5b942-178">Puede usar Azure Front Door Service para administrar el certificado o usar su propio certificado para el dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="5b942-178">You can use Azure Front Door Service to manage the certificate, or you can use your own certificate for the custom domain.</span></span>

<span data-ttu-id="5b942-179">En la ilustración siguiente se muestra el cuadro de diálogo **Personalizar HTTPS de dominio** en Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="5b942-179">The following illustration shows the **Custom Domain HTTPS** dialog box in Azure Front Door Service.</span></span>

![Cuadro de diálogo Personalizar HTTPS de dominio](./media/Custom_Domain_HTTPS.png)

<span data-ttu-id="5b942-181">Su CDN debe estar ahora configurado correctamente para que se pueda usar con su sitio de Commerce.</span><span class="sxs-lookup"><span data-stu-id="5b942-181">Your CDN should now be correctly configured so that it can be used with your Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5b942-182">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5b942-182">Additional resources</span></span>

[<span data-ttu-id="5b942-183">Configurar su nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="5b942-183">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="5b942-184">Implementar un sitio nuevo de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="5b942-184">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="5b942-185">Crear un sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="5b942-185">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="5b942-186">Asociar un sitio en línea con un canal</span><span class="sxs-lookup"><span data-stu-id="5b942-186">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="5b942-187">Administrar archivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="5b942-187">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="5b942-188">Configurar páginas personalizadas para inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="5b942-188">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="5b942-189">Habilitar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="5b942-189">Enable location-based store detection</span></span>](enable-store-detection.md)
