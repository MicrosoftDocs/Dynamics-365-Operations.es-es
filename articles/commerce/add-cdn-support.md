---
title: Agregar soporte para una red de entrega de contenido (CDN)
description: Este tema describe cómo agregar una red de entrega de contenido (CDN) a su entorno de Microsoft Dynamics 365 Commerce.
author: brianshook
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 59277323e0995f59d3a451395a038fa3708274eb
ms.sourcegitcommit: 9eadc7ca08e2db3fd208f5fc835551abe9d06dc8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/22/2021
ms.locfileid: "5936839"
---
# <a name="add-support-for-a-content-delivery-network-cdn"></a><span data-ttu-id="2eefc-103">Agregar soporte para una red de entrega de contenido (CDN)</span><span class="sxs-lookup"><span data-stu-id="2eefc-103">Add support for a content delivery network (CDN)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2eefc-104">Este tema describe cómo agregar una red de entrega de contenido (CDN) a su entorno de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2eefc-104">This topic describes how to add a content delivery network (CDN) to your Microsoft Dynamics 365 Commerce environment.</span></span>

<span data-ttu-id="2eefc-105">Al configurar un entorno de comercio electrónico en Dynamics 365 Commerce, puede definirlo para trabajar con su servicio de CDN.</span><span class="sxs-lookup"><span data-stu-id="2eefc-105">When you set up an e-commerce environment in Dynamics 365 Commerce, you can configure it to work with your CDN service.</span></span> 

<span data-ttu-id="2eefc-106">Su dominio personalizado se puede habilitar durante el proceso de aprovisionamiento para su entorno de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="2eefc-106">Your custom domain can be enabled during the provisioning process for your e-commerce environment.</span></span> <span data-ttu-id="2eefc-107">Como alternativa, puede usar una solicitud de servicio para configurarlo una vez que se ha completado el proceso de aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="2eefc-107">Alternatively, you can use a service request to set it up after the provisioning process is completed.</span></span> <span data-ttu-id="2eefc-108">El proceso de aprovisionamiento para el entorno de comercio electrónico genera un nombre de host que esté asociado al entorno.</span><span class="sxs-lookup"><span data-stu-id="2eefc-108">The provisioning process for the e-commerce environment generates a host name that is associated with the environment.</span></span> <span data-ttu-id="2eefc-109">Este nombre de host tiene el siguiente formato, donde \<*e-commerce-tenant-name*\> es el nombre del entorno:</span><span class="sxs-lookup"><span data-stu-id="2eefc-109">This host name has the following format, where \<*e-commerce-tenant-name*\> is the name of your environment:</span></span>

<span data-ttu-id="2eefc-110">&lt;nombre-inquilino-comercio-electrónico&gt;.commerce.dynamics.com</span><span class="sxs-lookup"><span data-stu-id="2eefc-110">&lt;e-commerce-tenant-name&gt;.commerce.dynamics.com</span></span>

<span data-ttu-id="2eefc-111">El nombre de host o el extremo que se genera durante el proceso de aprovisionamiento admite un certificado de capa de sockets seguros (SSL) solo para \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="2eefc-111">The host name or endpoint that is generated during the provisioning process supports a Secure Sockets Layer (SSL) certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="2eefc-112">No admite SSL para dominios personalizados.</span><span class="sxs-lookup"><span data-stu-id="2eefc-112">It doesn't support SSL for custom domains.</span></span> <span data-ttu-id="2eefc-113">Por lo tanto, debe finalizar SSL para los dominios personalizados en su CDN y reenviar el tráfico desde la CDN al nombre de host o extremo que Commerce generó.</span><span class="sxs-lookup"><span data-stu-id="2eefc-113">Therefore, you must terminate SSL for custom domains in your CDN and forward traffic from the CDN to the host name or endpoint that Commerce generated.</span></span> 

<span data-ttu-id="2eefc-114">Además, los (archivos JavaScript o de hojas de estilo CSS \[CSS\] ) *estáticos* de Commerce se sirven desde el extremo que Commerce generó (\*.commerce.dynamics.com).</span><span class="sxs-lookup"><span data-stu-id="2eefc-114">Additionally, the *statics* (JavaScript or Cascading Style Sheets \[CSS\] files) from Commerce are served from the endpoint that Commerce generated (\*.commerce.dynamics.com).</span></span> <span data-ttu-id="2eefc-115">La estática solo se puede almacenar en caché si el nombre de host o extremo que Commerce generó se coloca detrás de la CDN.</span><span class="sxs-lookup"><span data-stu-id="2eefc-115">The statics can be cached only if the host name or endpoint that Commerce generated is put behind the CDN.</span></span>

## <a name="set-up-ssl"></a><span data-ttu-id="2eefc-116">Configurar SSL</span><span class="sxs-lookup"><span data-stu-id="2eefc-116">Set up SSL</span></span>

<span data-ttu-id="2eefc-117">Tras aprovisionar su entorno de Commerce con el dominio personalizado que se proporciona, o una vez que proporciona el dominio personalizado para su entorno usando una solicitud de servicio, necesita trabajar con el equipo de incorporación de Commerce para planear los cambios de DNS.</span><span class="sxs-lookup"><span data-stu-id="2eefc-117">After you provision your Commerce environment with the custom domain that is provided, or after you provide the custom domain for your environment by using a service request, you need to work with the Commerce onboarding team to plan the DNS changes.</span></span>

<span data-ttu-id="2eefc-118">Como se ha mencionado anteriormente, el nombre de host o extremo generado admite un certificado SSL solo para \*.commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="2eefc-118">As was previously mentioned, the generated host name or endpoint supports an SSL certificate only for \*.commerce.dynamics.com.</span></span> <span data-ttu-id="2eefc-119">No admite SSL para dominios personalizados.</span><span class="sxs-lookup"><span data-stu-id="2eefc-119">It doesn't support SSL for custom domains.</span></span>

## <a name="cdn-services"></a><span data-ttu-id="2eefc-120">Servicios CDN</span><span class="sxs-lookup"><span data-stu-id="2eefc-120">CDN services</span></span>

<span data-ttu-id="2eefc-121">Cualquier servicio de CDN se puede usar con un entorno de Commerce.</span><span class="sxs-lookup"><span data-stu-id="2eefc-121">Any CDN service can be used with a Commerce environment.</span></span> <span data-ttu-id="2eefc-122">Estos son dos ejemplos:</span><span class="sxs-lookup"><span data-stu-id="2eefc-122">Here are two examples:</span></span>

- <span data-ttu-id="2eefc-123">**Microsoft Azure Front Door Service**: la solución de CDN de Azure.</span><span class="sxs-lookup"><span data-stu-id="2eefc-123">**Microsoft Azure Front Door Service** – The Azure CDN solution.</span></span> <span data-ttu-id="2eefc-124">Para obtener más información acerca de Azure Front Door Service, consulte [Documentación de Azure Front Door Service](/azure/frontdoor/).</span><span class="sxs-lookup"><span data-stu-id="2eefc-124">For more information about Azure Front Door Service, see [Azure Front Door Service Documentation](/azure/frontdoor/).</span></span>
- <span data-ttu-id="2eefc-125">**Acelerador de sitios dinámicos de Akamai**: para obtener más información, consulte [Acelerador de sitios dinámicos](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span><span class="sxs-lookup"><span data-stu-id="2eefc-125">**Akamai Dynamic Site Accelerator** – For more information, see [Dynamic Site Accelerator](https://www.akamai.com/us/en/products/performance/dynamic-site-accelerator.jsp).</span></span>

## <a name="cdn-setup"></a><span data-ttu-id="2eefc-126">Configuración de CDN</span><span class="sxs-lookup"><span data-stu-id="2eefc-126">CDN setup</span></span>

<span data-ttu-id="2eefc-127">El proceso de configuración de CDN consta de estos pasos generales:</span><span class="sxs-lookup"><span data-stu-id="2eefc-127">The CDN setup process consists of these general steps:</span></span>

1. <span data-ttu-id="2eefc-128">Agregue un host front-end.</span><span class="sxs-lookup"><span data-stu-id="2eefc-128">Add a front-end host.</span></span>
1. <span data-ttu-id="2eefc-129">Configure un grupo back-end.</span><span class="sxs-lookup"><span data-stu-id="2eefc-129">Configure a backend pool.</span></span>
1. <span data-ttu-id="2eefc-130">Configurar reglas de enrutamiento.</span><span class="sxs-lookup"><span data-stu-id="2eefc-130">Set up rules for routing.</span></span>

### <a name="add-a-front-end-host"></a><span data-ttu-id="2eefc-131">Agregar un host front-end</span><span class="sxs-lookup"><span data-stu-id="2eefc-131">Add a front-end host</span></span>

<span data-ttu-id="2eefc-132">Se puede usar cualquier servicio de CDN, pero para el ejemplo que se muestra en este tema, se usa Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="2eefc-132">Any CDN service can be used, but for the example in this topic, Azure Front Door Service is used.</span></span> 

<span data-ttu-id="2eefc-133">Para obtener información acerca de cómo configurar Azure Front Door Service, consulte [Inicio rápido: crear una puerta delantera para una aplicación web global de alta disponibilidad](/azure/frontdoor/quickstart-create-front-door).</span><span class="sxs-lookup"><span data-stu-id="2eefc-133">For information about how to set up Azure Front Door Service, see [Quickstart: Create a Front Door for a highly available global web application](/azure/frontdoor/quickstart-create-front-door).</span></span>

### <a name="configure-a-backend-pool-in-azure-front-door-service"></a><span data-ttu-id="2eefc-134">Configurar un grupo back-end en Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="2eefc-134">Configure a backend pool in Azure Front Door Service</span></span>

<span data-ttu-id="2eefc-135">Para configurar un grupo back-end en Azure Front Door Service, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2eefc-135">To configure a backend pool in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="2eefc-136">Agregue **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** a un grupo de backend como un host personalizado que tiene un encabezado de host de backend que es el mismo que **&lt;ecom-tenant-name&gt;.commerce.dynamics.com**.</span><span class="sxs-lookup"><span data-stu-id="2eefc-136">Add **&lt;ecom-tenant-name&gt;.commerce.dynamics.com** to a backend pool as a custom host that has a backend host header that is the same as **&lt;ecom-tenant-name&gt;.commerce.dynamics.com**.</span></span>
1. <span data-ttu-id="2eefc-137">En **Equilibrio de carga**, deje los valores predeterminados.</span><span class="sxs-lookup"><span data-stu-id="2eefc-137">Under **Load balancing**, leave the default values.</span></span>
1. <span data-ttu-id="2eefc-138">Inhabilite las verificaciones de estado para el grupo de backend.</span><span class="sxs-lookup"><span data-stu-id="2eefc-138">Disable health checks for the backend pool.</span></span>

<span data-ttu-id="2eefc-139">En la ilustración siguiente se muestra el cuadro de diálogo **Agregar un grupo back-end** en Azure Front Door Service con el nombre de host del back-end.</span><span class="sxs-lookup"><span data-stu-id="2eefc-139">The following illustration shows the **Add a backend** dialog box in Azure Front Door Service with the backend host name entered.</span></span>

![Cuadro de diálogo Agregar un grupo back-end](./media/CDN_BackendPool.png)

<span data-ttu-id="2eefc-141">En la ilustración siguiente se muestra el cuadro de diálogo **Agregar un grupo back-end** en Azure Front Door Service con los valores de equilibrio de carga predeterminados.</span><span class="sxs-lookup"><span data-stu-id="2eefc-141">The following illustration shows the **Add a backend pool** dialog box in Azure Front Door Service with the default load balancing values.</span></span>

![Cuadro de diálogo Agregar un grupo back-end (continuación)](./media/CDN_BackendPool_2.png)

> [!NOTE]
> <span data-ttu-id="2eefc-143">Asegúrese de deshabilitar **Sondas de salud** al configurar su propio servicio Azure Front Door para Commerce.</span><span class="sxs-lookup"><span data-stu-id="2eefc-143">Be sure to disable **Health Probes** when setting up your own Azure Front Door service for Commerce.</span></span>


### <a name="set-up-rules-in-azure-front-door-service"></a><span data-ttu-id="2eefc-144">Configurar reglas en Azure Front Door Service</span><span class="sxs-lookup"><span data-stu-id="2eefc-144">Set up rules in Azure Front Door Service</span></span>

<span data-ttu-id="2eefc-145">Para configurar una regla de ruta en Azure Front Door Service, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2eefc-145">To set up a routing rule in Azure Front Door Service, follow these steps.</span></span>

1. <span data-ttu-id="2eefc-146">Agregar una regla de ruta.</span><span class="sxs-lookup"><span data-stu-id="2eefc-146">Add a routing rule.</span></span>
1. <span data-ttu-id="2eefc-147">En el campo **Nombre**, especifique **predeterminado**.</span><span class="sxs-lookup"><span data-stu-id="2eefc-147">In the **Name** field, enter **default**.</span></span>
1. <span data-ttu-id="2eefc-148">En el campo **Protocolo aceptado**, seleccione **HTTP y HTTPS**.</span><span class="sxs-lookup"><span data-stu-id="2eefc-148">In the **Accepted protocol** field, select **HTTP and HTTPS**.</span></span>
1. <span data-ttu-id="2eefc-149">En el campo **Hosts de front-end**, especifique **dynamics-ecom-tenant-name.azurefd.net**.</span><span class="sxs-lookup"><span data-stu-id="2eefc-149">In the **Frontend hosts** field, enter **dynamics-ecom-tenant-name.azurefd.net**.</span></span>
1. <span data-ttu-id="2eefc-150">En **Patrones de coincidencia**, en el campo superior, especifique **/\***.</span><span class="sxs-lookup"><span data-stu-id="2eefc-150">Under **Patterns to match**, in the upper field, enter **/\***.</span></span>
1. <span data-ttu-id="2eefc-151">En **Detalles de ruta**, establezca la opción **Tipo de ruta** en **Reenviar**.</span><span class="sxs-lookup"><span data-stu-id="2eefc-151">Under **Route Details**, set the **Route type** option to **Forward**.</span></span>
1. <span data-ttu-id="2eefc-152">En el campo **Grupo back-end**, seleccione **ecom-backend**.</span><span class="sxs-lookup"><span data-stu-id="2eefc-152">In the **Backend pool** field, select **ecom-backend**.</span></span>
1. <span data-ttu-id="2eefc-153">En el grupo del campo **Protocolo de reenvío**, seleccione la opción **Confrontar solicitud**.</span><span class="sxs-lookup"><span data-stu-id="2eefc-153">In the **Forwarding protocol** field group, select the **Match request** option.</span></span> 
1. <span data-ttu-id="2eefc-154">Establezca la opción **URL Rewrite** en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="2eefc-154">Set the **URL rewrite** option to **Disabled**.</span></span>
1. <span data-ttu-id="2eefc-155">Establezca la opción **Memoria caché** en **Deshabilitado**.</span><span class="sxs-lookup"><span data-stu-id="2eefc-155">Set the **Caching** option to **Disabled**.</span></span>


> [!WARNING]
> <span data-ttu-id="2eefc-156">Si el dominio que usará ya está activo y en funcionamiento, cree una incidencia de soporte técnico desde el icono **Soporte técnico** en [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) para obtener asistencia para sus próximos pasos.</span><span class="sxs-lookup"><span data-stu-id="2eefc-156">If the domain that you will use is already active and live, create a support ticket from the **Support** tile in [Microsoft Dynamics Lifecycle Services](https://lcs.dynamics.com/) to get assistance for your next steps.</span></span> <span data-ttu-id="2eefc-157">Para más información, consulte [Obtener soporte técnico para aplicaciones de Finance and Operations o Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span><span class="sxs-lookup"><span data-stu-id="2eefc-157">For more information, see [Get support for Finance and Operations apps or Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md).</span></span>

<span data-ttu-id="2eefc-158">Si su dominio es nuevo y no es un dominio activo preexistente, puede agregar su dominio personalizado a la configuración de Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="2eefc-158">If your domain is new and is not a pre-existing live domain, you can add your custom domain to the configuration for Azure Front Door Service.</span></span> <span data-ttu-id="2eefc-159">Esto permitirá que el tráfico web se dirija a su sitio a través de la instancia de Azure Front Door.</span><span class="sxs-lookup"><span data-stu-id="2eefc-159">This will enable web traffic to direct to your site via the Azure Front Door instance.</span></span> <span data-ttu-id="2eefc-160">Para agregar el dominio personalizado (por ejemplo, `www.fabrikam.com`), debe configurar un nombre canónico (CNAME) para el dominio.</span><span class="sxs-lookup"><span data-stu-id="2eefc-160">To add the custom domain (for example, `www.fabrikam.com`), you must configure a Canonical Name (CNAME) for the domain.</span></span>

<span data-ttu-id="2eefc-161">En la ilustración siguiente se muestra el cuadro de diálogo **Configuración de CNAME** en Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="2eefc-161">The following illustration shows the **CNAME configuration** dialog box in Azure Front Door Service.</span></span>

![Cuadro de diálogo Configuración de CNAME](./media/CNAME_Configuration.png)

<span data-ttu-id="2eefc-163">Puede usar Azure Front Door Service para administrar el certificado o usar su propio certificado para el dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="2eefc-163">You can use Azure Front Door Service to manage the certificate, or you can use your own certificate for the custom domain.</span></span>

<span data-ttu-id="2eefc-164">En la ilustración siguiente se muestra el cuadro de diálogo **Personalizar HTTPS de dominio** en Azure Front Door Service.</span><span class="sxs-lookup"><span data-stu-id="2eefc-164">The following illustration shows the **Custom Domain HTTPS** dialog box in Azure Front Door Service.</span></span>

![Cuadro de diálogo Personalizar HTTPS de dominio](./media/Custom_Domain_HTTPS.png)

<span data-ttu-id="2eefc-166">Para obtener instrucciones detalladas sobre cómo agregar un dominio personalizado a Azure Front Door, consulte [Agregar un dominio personalizado a su instancia de Front Door](/azure/frontdoor/front-door-custom-domain).</span><span class="sxs-lookup"><span data-stu-id="2eefc-166">For detailed instructions on adding a custom domain to your Azure Front Door, see [Add a custom domain to your Front Door](/azure/frontdoor/front-door-custom-domain).</span></span>

<span data-ttu-id="2eefc-167">Su CDN debe estar ahora configurado correctamente para que se pueda usar con su sitio de Commerce.</span><span class="sxs-lookup"><span data-stu-id="2eefc-167">Your CDN should now be correctly configured so that it can be used with your Commerce site.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2eefc-168">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2eefc-168">Additional resources</span></span>

[<span data-ttu-id="2eefc-169">Opciones de implementación de la red de entrega de contenido</span><span class="sxs-lookup"><span data-stu-id="2eefc-169">Content delivery network implementation options</span></span>](cdn-options.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]