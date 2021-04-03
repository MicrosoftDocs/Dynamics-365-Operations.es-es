---
title: Agregar soporte para una red de entrega de contenido (CDN)
description: Este tema describe cómo agregar una red de entrega de contenido (CDN) a su entorno de Microsoft Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 07/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: d653b072eca134c765a5db5659b228648fc13c4a
ms.sourcegitcommit: 3fe4d9a33447aa8a62d704fbbf18aeb9cb667baa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "5582728"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a><span data-ttu-id="8bb77-103">Agregar soporte para una red de entrega de contenido (CDN)</span><span class="sxs-lookup"><span data-stu-id="8bb77-103">Add support for a content delivery network (CDN)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8bb77-104">Este tema describe cómo agregar una red de entrega de contenido (CDN) a su entorno de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="8bb77-104">This topic describes how to add a content delivery network (CDN) to your Microsoft Dynamics 365 Commerce environment.</span></span>

<span data-ttu-id="8bb77-105">Al configurar un entorno de comercio electrónico en Dynamics 365 Commerce, puede definirlo para trabajar con su servicio de CDN.</span><span class="sxs-lookup"><span data-stu-id="8bb77-105">When you set up an e-commerce environment in Dynamics 365 Commerce, you can configure it to work with your CDN service.</span></span> 

<span data-ttu-id="8bb77-106">Su dominio personalizado se puede habilitar durante el proceso de aprovisionamiento para su entorno de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="8bb77-106">Your custom domain can be enabled during the provisioning process for your e-commerce environment.</span></span> <span data-ttu-id="8bb77-107">Como alternativa, puede usar una solicitud de servicio para configurarlo una vez que se ha completado el proceso de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="8bb77-107">Alternatively, you can use a service request to set it up after the provisioning process is completed.</span></span> <span data-ttu-id="8bb77-108">El proceso de aprovisionamiento para el entorno de comercio electrónico genera un nombre de host que esté asociado al entorno.</span><span class="sxs-lookup"><span data-stu-id="8bb77-108">The provisioning process for the e-commerce environment generates a host name that is associated with the environment.</span></span> <span data-ttu-id="8bb77-109">Este nombre de host tiene el siguiente formato, donde \<*e-commerce-tenant-name*\> es el nombre del entorno:</span><span class="sxs-lookup"><span data-stu-id="8bb77-109">This host name has the following format, where \<*e-commerce-tenant-name*\> is the name of your environment:</span></span>

<span data-ttu-id="8bb77-110">&lt;nombre-inquilino-comercio-electrónico&gt;.commerce.dynamics.com</span><span class="sxs-lookup"><span data-stu-id="8bb77-110">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span></span>

<span data-ttu-id="8bb77-111">El nombre de host o el extremo que se genera durante el proceso de aprovisionamiento admite un certificado de capa de sockets seguros (SSL) solo para \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="8bb77-111">The host name or endpoint that is generated during the provisioning process supports a Secure Sockets Layer (SSL) certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="8bb77-112">No admite SSL para dominios personalizados.</span><span class="sxs-lookup"><span data-stu-id="8bb77-112">It doesn't support SSL for custom domains.</span></span> <span data-ttu-id="8bb77-113">Por lo tanto, debe finalizar SSL para los dominios personalizados en su CDN y reenviar el tráfico desde la CDN al nombre de host o extremo que Commerce generó.</span><span class="sxs-lookup"><span data-stu-id="8bb77-113">Therefore, you must terminate SSL for custom domains in your CDN and forward traffic from the CDN to the host name or endpoint that Commerce generated.</span></span> 

<span data-ttu-id="8bb77-114">Además, los (archivos JavaScript o de hojas de estilo CSS \[CSS\] ) *estáticos* de Commerce se sirven desde el extremo que Commerce generó (\*.commerce.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="8bb77-114">Additionally, the *statics* (JavaScript or Cascading Style Sheets \[CSS\] files) from Commerce are served from the endpoint that Commerce generated (\*.commerce.dynamics.com).</span></span> <span data-ttu-id="8bb77-115">La estática solo se puede almacenar en caché si el nombre de host o extremo que Commerce generó se coloca detrás de la CDN.</span><span class="sxs-lookup"><span data-stu-id="8bb77-115">The statics can be cached only if the host name or endpoint that Commerce generated is put behind the CDN.</span></span>

## <a name="set-up-ssl"></a><span data-ttu-id="8bb77-116">Configurar SSL</span><span class="sxs-lookup"><span data-stu-id="8bb77-116">Set up SSL</span></span>

<span data-ttu-id="8bb77-117">Para ayudar a garantizar que SSL está configurado, y que la estática se almacena en caché, debe configurar su CDN para que se asocie al nombre de host que Commerce generó para su entorno.</span><span class="sxs-lookup"><span data-stu-id="8bb77-117">To help guarantee that SSL is set up, and that statics are cached, you must configure your CDN so that it is associated with the host name that Commerce generated for your environment.</span></span> <span data-ttu-id="8bb77-118">También debe almacenar en caché el siguiente patrón solo para estática:</span><span class="sxs-lookup"><span data-stu-id="8bb77-118">You must also cache the following pattern for statics only:</span></span> 

<span data-ttu-id="8bb77-119">/\_msdyn365/\_scnr/\*</span><span class="sxs-lookup"><span data-stu-id="8bb77-119">/\_msdyn365/\_scnr/\*</span></span>

<span data-ttu-id="8bb77-120">Tras aprovisionar su entorno de Commerce con el dominio personalizado que se proporciona, o una vez que proporciona el dominio personalizado para su entorno usando una solicitud de servicio, apunte su dominio personalizado al nombre de host o extremo que Commerce generó.</span><span class="sxs-lookup"><span data-stu-id="8bb77-120">After you provision your Commerce environment with the custom domain that is provided, or after you provide the custom domain for your environment by using a service request, point your custom domain to the host name or endpoint that Commerce generated.</span></span>

<span data-ttu-id="8bb77-121">Como se ha mencionado anteriormente, el nombre de host o extremo generado admite un certificado SSL solo para \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="8bb77-121">As was previously mentioned, the generated host name or endpoint supports an SSL certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="8bb77-122">No admite SSL para dominios personalizados.</span><span class="sxs-lookup"><span data-stu-id="8bb77-122">It doesn't support SSL for custom domains.</span></span>

## <a name="cdn-services"></a><span data-ttu-id="8bb77-123">Servicios CDN</span><span class="sxs-lookup"><span data-stu-id="8bb77-123">CDN services</span></span>

<span data-ttu-id="8bb77-124">Cualquier servicio de CDN se puede usar con un entorno de Commerce.</span><span class="sxs-lookup"><span data-stu-id="8bb77-124">Any CDN service can be used with a Commerce environment.</span></span> <span data-ttu-id="8bb77-125">Estos son dos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="8bb77-125">Here are two examples:</span></span>

- <span data-ttu-id="8bb77-126">**Microsoft Azure Front Door Service**: la solución de CDN de Azure.</span><span class="sxs-lookup"><span data-stu-id="8bb77-126">**Microsoft Azure Front Door Service** – The Azure CDN solution.</span></span> <span data-ttu-id="8bb77-127">Para obtener más información acerca de Azure Front Door Service, consulte [Documentación de Azure Front Door Service](https://docs.microsoft.com/azure/frontdoor/).</span><span class="sxs-lookup"><span data-stu-id="8bb77-127">For more information about Azure Front Door Service, see [Azure Front Door Service Documentation](https://docs.microsoft.com/azure/frontdoor/).</span></span>
- <span data-ttu-id="8bb77-128">**Acelerador de sitios dinámicos de Akamai**: para obtener más información, consulte [Acelerador de sitios dinámicos](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span><span class="sxs-lookup"><span data-stu-id="8bb77-128">**Akamai Dynamic Site Accelerator** – For more information, see [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span></span>

## <a name="cdn-setup"></a><span data-ttu-id="8bb77-129">Configuración de CDN</span><span class="sxs-lookup"><span data-stu-id="8bb77-129">CDN setup</span></span>

<span data-ttu-id="8bb77-130">El proceso de configuración de CDN consta de estos pasos generales:</span><span class="sxs-lookup"><span data-stu-id="8bb77-130">The CDN setup process consists of these general steps:</span></span>

1. <span data-ttu-id="8bb77-131">Agregue un host front-end.</span><span class="sxs-lookup"><span data-stu-id="8bb77-131">Add a front-end host.</span></span>
1. <span data-ttu-id="8bb77-132">Configure un grupo back-end.</span><span class="sxs-lookup"><span data-stu-id="8bb77-132">Configure a backend pool.</span></span>
1. <span data-ttu-id="8bb77-133">Configurar reglas para enrutamiento y almacenamiento en caché.</span><span class="sxs-lookup"><span data-stu-id="8bb77-133">Set up rules for routing and caching.</span></span>

### <a name="add-a-front-end-host"></a><span data-ttu-id="8bb77-134">Agregar un host front-end</span><span class="sxs-lookup"><span data-stu-id="8bb77-134">Add a front-end host</span></span>

<span data-ttu-id="8bb77-135">Se puede usar cualquier servicio de CDN, pero para el ejemplo que se muestra en este tema, se usa Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="8bb77-135">Any CDN service can be used, but for the example in this topic, Azure Front Door Service is used.</span></span> 

<span data-ttu-id="8bb77-136">Para obtener información acerca de cómo configurar Azure Front Door Service, consulte [Inicio rápido: crear una puerta delantera para una aplicación web global de alta disponibilidad](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span><span class="sxs-lookup"><span data-stu-id="8bb77-136">For information about how to set up Azure Front Door Service, see [Quickstart: Create a Front Door for a highly available global web application](https://docs.microsoft.com/azure/frontdoor/quickstart-create-front-door).</span></span>

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a><span data-ttu-id="8bb77-137">Configurar un grupo back-end en Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="8bb77-137">Configure a backend pool in Azure Front Door Service</span></span>

<span data-ttu-id="8bb77-138">Para configurar un grupo back-end en Azure Front Door Service, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8bb77-138">To configure a backend pool in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="8bb77-139">Agregue **&lt;nombre-comercio-electrónico-inquilino&gt;.commerce.dynamics.com** a un grupo back-end como host personalizado que tenga un encabezado de host de back-end vacío.</span><span class="sxs-lookup"><span data-stu-id="8bb77-139">Add **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** to a backend pool as a custom host that has an empty backend host header.</span></span>
1. <span data-ttu-id="8bb77-140">En **Equilibrio de carga**, deje los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="8bb77-140">Under **Load balancing**, leave the default values.</span></span>

<span data-ttu-id="8bb77-141">En la ilustración siguiente se muestra el cuadro de diálogo **Agregar un grupo back-end** en Azure Front Door Service con el nombre de host del back-end.</span><span class="sxs-lookup"><span data-stu-id="8bb77-141">The following illustration shows the **Add a backend** dialog box in Azure Front Door Service with the backend host name entered.</span></span>

![Cuadro de diálogo Agregar un grupo back-end](./media/CDN_BackendPool.png)

<span data-ttu-id="8bb77-143">En la ilustración siguiente se muestra el cuadro de diálogo **Agregar un grupo back-end** en Azure Front Door Service con los valores de equilibrio de carga predeterminados.</span><span class="sxs-lookup"><span data-stu-id="8bb77-143">The following illustration shows the **Add a backend pool** dialog box in Azure Front Door Service with the default load balancing values.</span></span>

![Cuadro de diálogo Agregar un grupo back-end (continuación)](./media/CDN_BackendPool_2.png)

### <a name="set-up-rules-in-azure-front-door-service"></a><span data-ttu-id="8bb77-145">Configurar reglas en Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="8bb77-145">Set up rules in Azure Front Door Service</span></span>

<span data-ttu-id="8bb77-146">Para configurar una regla de ruta en Azure Front Door Service, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8bb77-146">To set up a routing rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="8bb77-147">Agregar una regla de ruta.</span><span class="sxs-lookup"><span data-stu-id="8bb77-147">Add a routing rule.</span></span>
1. <span data-ttu-id="8bb77-148">En el campo **Nombre**, especifique **predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="8bb77-148">In the **Name** field, enter **default**.</span></span>
1. <span data-ttu-id="8bb77-149">En el campo **Protocolo aceptado**, seleccione **HTTP y HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="8bb77-149">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="8bb77-150">En el campo **Hosts de front-end**, especifique **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="8bb77-150">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="8bb77-151">En **Patrones de coincidencia**, en el campo superior, especifique **/\***.</span><span class="sxs-lookup"><span data-stu-id="8bb77-151">Under **Patterns to match**, in the upper field, enter **/\***.</span></span>
1. <span data-ttu-id="8bb77-152">En **Detalles de ruta**, establezca la opción **Tipo de ruta** en **Reenviar**.</span><span class="sxs-lookup"><span data-stu-id="8bb77-152">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="8bb77-153">En el campo **Grupo back-end**, seleccione **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="8bb77-153">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="8bb77-154">En el grupo del campo **Protocolo de reenvío**, seleccione la opción **Confrontar solicitud**.</span><span class="sxs-lookup"><span data-stu-id="8bb77-154">In the **Forwarding protocol** field group, select the **Match request** option.</span></span> 
1. <span data-ttu-id="8bb77-155">Establezca la opción **URL Rewrite** en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="8bb77-155">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="8bb77-156">Establezca la opción **Memoria caché** en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="8bb77-156">Set the **Caching** option to **Disabled**.</span></span>

<span data-ttu-id="8bb77-157">Para configurar una regla de almacenamiento en caché en Azure Front Door Service, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="8bb77-157">To set up a caching rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="8bb77-158">Agregue una regla de almacenamiento en caché.</span><span class="sxs-lookup"><span data-stu-id="8bb77-158">Add a caching rule.</span></span>
1. <span data-ttu-id="8bb77-159">En el campo **Nombre**, especifique **estática**.</span><span class="sxs-lookup"><span data-stu-id="8bb77-159">In the **Name** field, enter **statics**.</span></span>
1. <span data-ttu-id="8bb77-160">En el campo **Protocolo aceptado**, seleccione **HTTP y HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="8bb77-160">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="8bb77-161">En el campo **Hosts de front-end**, especifique **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="8bb77-161">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="8bb77-162">En **Patrones de coincidencia**, en el campo superior, especifique **/\_msdyn365/\_scnr/\***.</span><span class="sxs-lookup"><span data-stu-id="8bb77-162">Under **Patterns to match**, in the upper field, **/\_msdyn365/\_scnr/\***.</span></span>
1. <span data-ttu-id="8bb77-163">En **Detalles de ruta**, establezca la opción **Tipo de ruta** en **Reenviar**.</span><span class="sxs-lookup"><span data-stu-id="8bb77-163">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="8bb77-164">En el campo **Grupo back-end**, seleccione **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="8bb77-164">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="8bb77-165">En el grupo del campo **Protocolo de reenvío**, seleccione la opción **Confrontar solicitud**.</span><span class="sxs-lookup"><span data-stu-id="8bb77-165">In the **Forwarding protocol** field group, select the **Match request** option.</span></span>
1. <span data-ttu-id="8bb77-166">Establezca la opción **URL Rewrite** en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="8bb77-166">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="8bb77-167">Establezca la opción **Memoria caché** en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="8bb77-167">Set the **Caching** option to **Disabled**.</span></span>
1. <span data-ttu-id="8bb77-168">En el campo **Comportamiento del almacenamiento en caché de cadenas de consulta**, seleccione **Almacenar en caché todas las URL únicas**.</span><span class="sxs-lookup"><span data-stu-id="8bb77-168">In the **Query string caching behavior** field, select **Cache every unique URL**.</span></span>
1. <span data-ttu-id="8bb77-169">En el grupo del campo **Compresión dinámica**, seleccione la opción **Habilitado**.</span><span class="sxs-lookup"><span data-stu-id="8bb77-169">In the **Dynamic compression** field group, select the **Enabled** option.</span></span>

<span data-ttu-id="8bb77-170">En la ilustración siguiente se muestra el cuadro de diálogo **Agregar una regla** en Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="8bb77-170">The following illustration shows the **Add a rule** dialog box in Azure Front Door Service.</span></span>

![Cuadro de diálogo Agregar una regla](./media/CDN_CachingRule.png)

> [!WARNING]
> <span data-ttu-id="8bb77-172">Si el dominio que usará ya está activo y en funcionamiento, cree una incidencia de soporte técnico desde el icono **Soporte técnico** en [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) para obtener asistencia para sus próximos pasos.</span><span class="sxs-lookup"><span data-stu-id="8bb77-172">If the domain that you will use is already active and live, create a support ticket from the **Support** tile in [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) to get assistance for your next steps.</span></span> <span data-ttu-id="8bb77-173">Para más información, consulte [Obtener soporte técnico para aplicaciones de Finance and Operations o Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="8bb77-173">For more information, see [Get support for Finance and Operations apps or Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

<span data-ttu-id="8bb77-174">Si su dominio es nuevo y no es un dominio activo preexistente, puede agregar su dominio personalizado a la configuración de Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="8bb77-174">If your domain is new and is not a pre-existing live domain, you can add your custom domain to the configuration for Azure Front Door Service.</span></span> <span data-ttu-id="8bb77-175">Esto permitirá que el tráfico web se dirija a su sitio a través de la instancia de Azure Front Door.</span><span class="sxs-lookup"><span data-stu-id="8bb77-175">This will enable web traffic to direct to your site via the Azure Front Door instance.</span></span> <span data-ttu-id="8bb77-176">Para agregar el dominio personalizado (por ejemplo, `www.fabrikam.com`), debe configurar un nombre canónico (CNAME) para el dominio.</span><span class="sxs-lookup"><span data-stu-id="8bb77-176">To add the custom domain (for example, `www.fabrikam.com`), you must configure a Canonical Name (CNAME) for the domain.</span></span>

<span data-ttu-id="8bb77-177">En la ilustración siguiente se muestra el cuadro de diálogo **Configuración de CNAME** en Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="8bb77-177">The following illustration shows the **CNAME configuration** dialog box in Azure Front Door Service.</span></span>

![Cuadro de diálogo Configuración de CNAME](./media/CNAME_Configuration.png)

<span data-ttu-id="8bb77-179">Puede usar Azure Front Door Service para administrar el certificado o usar su propio certificado para el dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="8bb77-179">You can use Azure Front Door Service to manage the certificate, or you can use your own certificate for the custom domain.</span></span>

<span data-ttu-id="8bb77-180">En la ilustración siguiente se muestra el cuadro de diálogo **Personalizar HTTPS de dominio** en Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="8bb77-180">The following illustration shows the **Custom Domain HTTPS** dialog box in Azure Front Door Service.</span></span>

![Cuadro de diálogo Personalizar HTTPS de dominio](./media/Custom_Domain_HTTPS.png)

<span data-ttu-id="8bb77-182">Para obtener instrucciones detalladas sobre cómo agregar un dominio personalizado a Azure Front Door, consulte [Agregar un dominio personalizado a su instancia de Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-custom-domain).</span><span class="sxs-lookup"><span data-stu-id="8bb77-182">For detailed instructions on adding a custom domain to your Azure Front Door, see [Add a custom domain to your Front Door](https://docs.microsoft.com/azure/frontdoor/front-door-custom-domain).</span></span>

<span data-ttu-id="8bb77-183">Su CDN debe estar ahora configurado correctamente para que se pueda usar con su sitio de Commerce.</span><span class="sxs-lookup"><span data-stu-id="8bb77-183">Your CDN should now be correctly configured so that it can be used with your Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8bb77-184">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="8bb77-184">Additional resources</span></span>

[<span data-ttu-id="8bb77-185">Opciones de implementación de la red de entrega de contenido</span><span class="sxs-lookup"><span data-stu-id="8bb77-185">Content delivery network implementation options</span></span>](cdn-options.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
