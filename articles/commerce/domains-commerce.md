---
title: Dominios en Dynamics 365 Commerce
description: Este tema describe cómo se manejan los dominios en Microsoft Dynamics 365 Commerce.
author: BrShoo
manager: AnnBe
ms.date: 09/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: BrShoo
ms.search.validFrom: ''
ms.dyn365.ops.version: Release 10.0.12
ms.openlocfilehash: 84becee12363ca38951ff13073d87d1b1f14b616
ms.sourcegitcommit: a47a4652a29fdb567a8ba67c4f914a8698e8c48c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/03/2020
ms.locfileid: "3765010"
---
# <a name="domains-in-dynamics-365-commerce"></a><span data-ttu-id="c0cee-103">Dominios en Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="c0cee-103">Domains in Dynamics 365 Commerce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c0cee-104">Este tema describe cómo se manejan los dominios en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c0cee-104">This topic describes how domains are handled in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="c0cee-105">Los dominios son direcciones web que se utilizan para navegar a sitios de Dynamics 365 Commerce en un explorador web.</span><span class="sxs-lookup"><span data-stu-id="c0cee-105">Domains are web addresses used to navigate to Dynamics 365 Commerce sites in a web browser.</span></span> <span data-ttu-id="c0cee-106">Usted controla la administración de su dominio con un proveedor de servidor de nombres de dominio (DNS) elegido.</span><span class="sxs-lookup"><span data-stu-id="c0cee-106">You control management of your domain with a chosen Domain Name Server (DNS) provider.</span></span> <span data-ttu-id="c0cee-107">Se hace referencia a los dominios en todo el creador de sitios de Dynamics 365 Commerce para coordinar cómo se accederá a un sitio cuando se publique.</span><span class="sxs-lookup"><span data-stu-id="c0cee-107">Domains are referenced throughout Dynamics 365 Commerce site builder to coordinate how a site will be accessed when published.</span></span> <span data-ttu-id="c0cee-108">Este tema revisa cómo se manejan y se hace referencia a los dominios a lo largo del ciclo de vida del desarrollo y lanzamiento del sitio de Commerce.</span><span class="sxs-lookup"><span data-stu-id="c0cee-108">This topic reviews how domains are handled and referenced throughout the lifecycle of the Commerce site development and launch.</span></span>

## <a name="provisioning-and-supported-host-names"></a><span data-ttu-id="c0cee-109">Aprovisionamiento y nombres de host admitidos</span><span class="sxs-lookup"><span data-stu-id="c0cee-109">Provisioning and supported host names</span></span>

<span data-ttu-id="c0cee-110">Al aprovisionar un entorno de comercio electrónico en [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/), el cuadro **Nombres de host admitidos** en la pantalla de aprovisionamiento de comercio electrónico se utiliza para especificar dominios que se asociarán con el entorno de Commerce implementado.</span><span class="sxs-lookup"><span data-stu-id="c0cee-110">When provisioning an e-Commerce environment in [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/), the **Supported host names** box on the e-Commerce provisioning screen is used to enter domains that will be associated with the deployed Commerce environment.</span></span> <span data-ttu-id="c0cee-111">Estos dominios serán los nombres del servidor de nombres de dominio (DNS) de cara al cliente donde se hospedarán los sitios web de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="c0cee-111">These domains will be the customer-facing Domain Name Server (DNS) names where e-Commerce websites will be hosted.</span></span> <span data-ttu-id="c0cee-112">Especificar un dominio en esta etapa no empieza a desviar el tráfico del dominio hacia Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c0cee-112">Entering a domain at this stage does not start diverting traffic for the domain to Dynamics 365 Commerce.</span></span> <span data-ttu-id="c0cee-113">El tráfico de un dominio solo se enrutará al punto final de Commerce cuando el registro CNAME de DNS se actualice para usar el punto final de Commerce con el dominio.</span><span class="sxs-lookup"><span data-stu-id="c0cee-113">Traffic for a domain will only be routed to the Commerce endpoint when the DNS CNAME record is updated to use the Commerce endpoint with the domain.</span></span>

> [!NOTE]
> <span data-ttu-id="c0cee-114">Se pueden especificar varios dominios en el cuadro **Nombres de host admitidos** separándolos con punto y coma.</span><span class="sxs-lookup"><span data-stu-id="c0cee-114">Multiple domains can be entered into the **Supported host names** box by separating them with semi-colons.</span></span>

<span data-ttu-id="c0cee-115">La siguiente ilustración muestra la pantalla de aprovisionamiento de comercio electrónico LCS con el cuadro **Nombres de host admitidos** resaltado.</span><span class="sxs-lookup"><span data-stu-id="c0cee-115">The following illustration shows the LCS e-Commerce provisioning screen with the **Supported host names** box highlighted.</span></span> 

![Pantalla de aprovisionamiento de comercio electrónico de LCS con el cuadro **Nombres de host admitidos** resaltado](./media/Domains_ProvisioningeCommerceScreen.png)

<span data-ttu-id="c0cee-117">Puede crear una solicitud de servicio para agregar dominios adicionales a un entorno si ya se ha realizado el aprovisionamiento.</span><span class="sxs-lookup"><span data-stu-id="c0cee-117">You can create a service request to add additional domains to an environment if provisioning has already occurred.</span></span> <span data-ttu-id="c0cee-118">Para crear una solicitud de servicio en LCS, en su entorno vaya a **Soporte \> Problemas de soporte** y seleccione **Presentar un incidente**.</span><span class="sxs-lookup"><span data-stu-id="c0cee-118">To create a service request in LCS, within your environment go to **Support \> Support issues** and select **Submit an incident**.</span></span>

## <a name="commerce-generated-urls"></a><span data-ttu-id="c0cee-119">URL generadas por Commerce</span><span class="sxs-lookup"><span data-stu-id="c0cee-119">Commerce-generated URLs</span></span>

<span data-ttu-id="c0cee-120">Al aprovisionar un entorno de comercio electrónico, Commerce generará una URL que será la dirección de trabajo para el entorno.</span><span class="sxs-lookup"><span data-stu-id="c0cee-120">When provisioning an e-Commerce environment, Commerce will generate a URL that will be the working address for the environment.</span></span> <span data-ttu-id="c0cee-121">Se hace referencia a esta URL en el enlace del sitio de comercio electrónico que se muestra en LCS después de que se aprovisiona el entorno.</span><span class="sxs-lookup"><span data-stu-id="c0cee-121">This URL is referenced in the e-Commerce site link shown in LCS after the environment is provisioned.</span></span> <span data-ttu-id="c0cee-122">Una URL generada por Commerce tiene el formato `https://<e-Commerce tenant name>.commerce.dynamics.com`, donde el nombre del inquilino de comercio electrónico es el nombre especificado en LCS para el entorno de Commerce.</span><span class="sxs-lookup"><span data-stu-id="c0cee-122">A Commerce-generated URL is in the format `https://<e-Commerce tenant name>.commerce.dynamics.com`, where the e-Commerce tenant name is the name entered in LCS for the Commerce environment.</span></span>

<span data-ttu-id="c0cee-123">También puede utilizar los nombres de host del sitio de producción en un entorno de espacio aislado.</span><span class="sxs-lookup"><span data-stu-id="c0cee-123">You can use production site host names in a sandbox environment as well.</span></span> <span data-ttu-id="c0cee-124">Esta opción es ideal cuando va a copiar un sitio desde un entorno de espacio aislado a producción.</span><span class="sxs-lookup"><span data-stu-id="c0cee-124">This option is ideal when you will be copying a site from a sandbox environment to production.</span></span>

## <a name="site-setup"></a><span data-ttu-id="c0cee-125">Configuración del sitio</span><span class="sxs-lookup"><span data-stu-id="c0cee-125">Site setup</span></span>

<span data-ttu-id="c0cee-126">Una vez que se aprovisiona su entorno de comercio electrónico, debe configurar su sitio en el creador de sitios de Commerce para asociar su sitio a la URL de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c0cee-126">After your e-Commerce environment is provisioned, you must set up your site in Commerce site builder to associate your site to the working URL.</span></span>

<span data-ttu-id="c0cee-127">Cuando configura por primera vez un sitio en el creador de sitios, el cuadro de diálogo **Configurar su sitio** aparecerá.</span><span class="sxs-lookup"><span data-stu-id="c0cee-127">When you first set up a site in site builder, the **Setup your Site** dialog box will appear.</span></span>

<span data-ttu-id="c0cee-128">La siguiente ilustración muestra el cuadro de diálogo **Configurar su sitio** para un sitio llamado "predeterminado" cuando accede al sitio por primera vez en el creador de sitios.</span><span class="sxs-lookup"><span data-stu-id="c0cee-128">The following illustration shows the **Setup your Site** dialog box for a site named "default" when you access the site for the first time in site builder.</span></span>

![Cuadro de diálogo **Configurar su sitio**](./media/Domains_SetupyoursiteScreen.png)

<span data-ttu-id="c0cee-130">El cuadro de diálogo **Seleccionar un dominio** le permite asociar uno de los nombres de host admitidos proporcionados para su sitio en LCS a su sitio en el creador de sitios.</span><span class="sxs-lookup"><span data-stu-id="c0cee-130">The **Select a domain** box allows you to associate one of the supported host names provided for your site in LCS to your site in site builder.</span></span>

<span data-ttu-id="c0cee-131">El cuadro **Ruta de acceso** se puede dejar en blanco o se puede agregar una cadena de ruta de acceso adicional que se reflejará en su URL de trabajo.</span><span class="sxs-lookup"><span data-stu-id="c0cee-131">The **Path** box can be left blank, or an additional path string can be added that will be reflected in your working URL.</span></span> <span data-ttu-id="c0cee-132">Si deja el cuadro de diálogo **Ruta de acceso** vacío, se asocia la URL base generada por Commerce con el sitio que se está configurando en el creador de sitios.</span><span class="sxs-lookup"><span data-stu-id="c0cee-132">Leaving the **Path** box blank associates the base Commerce-generated URL with the site being set up in site builder.</span></span> <span data-ttu-id="c0cee-133">Las rutas de acceso deben ser únicas para cada par de sitio/dominio.</span><span class="sxs-lookup"><span data-stu-id="c0cee-133">Paths must be unique for each site/domain pair.</span></span> <span data-ttu-id="c0cee-134">Dentro del sitio y dominio seleccionados, solo un sitio en el entorno puede usar la ruta de acceso vacía o asociarse con una cadena de ruta de acceso única.</span><span class="sxs-lookup"><span data-stu-id="c0cee-134">Within the site and domain selected, only one site in the environment can use the blank path or be associated with a unique path string.</span></span> <span data-ttu-id="c0cee-135">Cualquier cadena agregada al campo **Ruta de acceso** durante la configuración del sitio se convertirá en una ruta de acceso secundaria de la dirección URL base generada por Commerce que se utiliza para acceder al sitio en un explorador web.</span><span class="sxs-lookup"><span data-stu-id="c0cee-135">Any string added to the **Path** field during site setup will become a subpath of the base Commerce-generated URL used to access the site in a web browser.</span></span>

> [!NOTE]
> <span data-ttu-id="c0cee-136">La ruta de acceso también se conoce como la **Ruta de acceso de coincidencia** al agregar un canal en la sección de configuración **Configuración del sitio \> Canales** del creador de sitios.</span><span class="sxs-lookup"><span data-stu-id="c0cee-136">The path is also known as the **Match path** when adding a channel in the **Site Settings \> Channels** configuration section of site builder.</span></span>

<span data-ttu-id="c0cee-137">Por ejemplo, si tiene un sitio en el creador de sitios llamado "fabrikam" en un inquilino de comercio electrónico llamado "xyz", y si configura el sitio con una ruta de acceso vacía, entonces accederá al contenido del sitio publicado en un explorador web yendo directamente a la URL base generada por Commerce:</span><span class="sxs-lookup"><span data-stu-id="c0cee-137">For example, if you have a site in site builder called "fabrikam" in an e-Commerce tenant named "xyz," and if you set up the site with a blank path, then you would access the published site content in a web browser by going directly to the base Commerce-generated URL:</span></span>

`https://xyz.commerce.dynamics.com`

<span data-ttu-id="c0cee-138">Alternativamente, si hubiera agregado una ruta de "fabrikam" durante la configuración de este mismo sitio, accedería al contenido del sitio publicado en un navegador web usando la siguiente URL:</span><span class="sxs-lookup"><span data-stu-id="c0cee-138">Alternately, if you had added a path of "fabrikam" during this same site's setup, you would access the published site content in a web browser using the following URL:</span></span>

`https://xyz.commerce.dynamics.com/fabrikam`

## <a name="pages-and-urls"></a><span data-ttu-id="c0cee-139">Páginas y direcciones URL</span><span class="sxs-lookup"><span data-stu-id="c0cee-139">Pages and URLs</span></span>

<span data-ttu-id="c0cee-140">Una vez que su sitio está configurado con una ruta de acceso, todas las direcciones URL asociadas con las páginas en el creador de sitios se basarán en la dirección URL de trabajo (la dirección URL generada por Commerce o la URL generada por Commerce más la ruta de acceso) para el sitio.</span><span class="sxs-lookup"><span data-stu-id="c0cee-140">After your site is set up with a path, all URLs associated with pages in site builder will build on the working URL (the Commerce-generated URL, or the Commerce-generated URL plus the path) for the site.</span></span> <span data-ttu-id="c0cee-141">Crear una nueva dirección URL en el creador de sitios (**URLS /> +Nuevo**) seleccionando una página de la lista en el cuadro de diálogo **Dirección URL nueva** y especificar la ruta de la dirección URL para esa página asociará esa dirección URL con la página seleccionada.</span><span class="sxs-lookup"><span data-stu-id="c0cee-141">Creating a new URL in site builder (**URLS /> +New**) by selecting a page from the list in the **New URL** dialog box and entering the URL path for that page will associate that URL with the selected page.</span></span> <span data-ttu-id="c0cee-142">El valor de la ruta de acceso de la URL luego se agrega a la dirección URL de trabajo del sitio para acceder a la página, y se etiqueta como `./<URL path>` en la lista de dirección URL de la página **Direcciones URL** en el creador de sitios.</span><span class="sxs-lookup"><span data-stu-id="c0cee-142">The URL path value then appends to the site's working URL to access the page, and is labeled as `./<URL path>` in the URL list of the **URLs** page in site builder.</span></span>

<span data-ttu-id="c0cee-143">La siguiente ilustración muestra el cuadro de diálogo **Dirección URL nueva** en el creador de sitios con una ruta de la dirección URL de ejemplo resaltada.</span><span class="sxs-lookup"><span data-stu-id="c0cee-143">The following illustration shows the **New URL** dialog box in site builder with an example URL path highlighted.</span></span> 

![Cuadro de diálogo **Nueva dirección URL** en el creador de sitios](./media/Domains_PageSetup2a.png)

<span data-ttu-id="c0cee-145">La siguiente ilustración muestra la página **Direcciones URL** en el creador de sitios con una ruta de la dirección URL de ejemplo resaltada en la lista.</span><span class="sxs-lookup"><span data-stu-id="c0cee-145">The following illustration shows the **URLs** page in site builder with an example URL highlighted in the list.</span></span>

![Opción Ejecutar flujo de usuario en flujo de directiva](./media/Domains_URLsInSiteBuilder2a.png)

## <a name="domains-in-site-builder"></a><span data-ttu-id="c0cee-147">Dominios en el creador de sitios</span><span class="sxs-lookup"><span data-stu-id="c0cee-147">Domains in site builder</span></span>

<span data-ttu-id="c0cee-148">Los valores de nombres de host admitidos están disponibles para asociarse como un dominio al configurar un sitio.</span><span class="sxs-lookup"><span data-stu-id="c0cee-148">The supported host names values are available to be associated as a domain when setting up a site.</span></span> <span data-ttu-id="c0cee-149">Al seleccionar un valor de nombre de host compatible como dominio, verá el dominio elegido referenciado en todo el creador de sitios.</span><span class="sxs-lookup"><span data-stu-id="c0cee-149">When selecting a supported host name value as the domain, you will see the chosen domain referenced throughout site builder.</span></span> <span data-ttu-id="c0cee-150">Este dominio es solo una referencia dentro del entorno de Commerce, el tráfico en vivo para ese dominio aún no se reenviará a Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c0cee-150">This domain is only a reference within the Commerce environment, live traffic for that domain will not yet be forwarded to Dynamics 365 Commerce.</span></span>

<span data-ttu-id="c0cee-151">Al trabajar con sitios en el creador de sitios, si tiene dos sitios configurados con dos dominios diferentes, puede agregar el atributo **?domain=** a su dirección URL de trabajo para acceder al contenido del sitio publicado en un navegador.</span><span class="sxs-lookup"><span data-stu-id="c0cee-151">When working with sites in site builder, if you have two sites set up with two different domains, you can append the **?domain=** attribute to your working URL to access the published site content in a browser.</span></span>

<span data-ttu-id="c0cee-152">Por ejemplo, se ha aprovisionado el entorno "xyz" y se han creado y asociado dos sitios en el creador de sitios: uno con el dominio `www.fabrikam.com` y el otro con el dominio `www.constoso.com`.</span><span class="sxs-lookup"><span data-stu-id="c0cee-152">For example, environment "xyz" has been provisioned, and two sites have been created and associated in site builder: one with the domain `www.fabrikam.com` and the other with the domain `www.constoso.com`.</span></span> <span data-ttu-id="c0cee-153">Cada sitio se configuró utilizando una ruta de acceso vacía.</span><span class="sxs-lookup"><span data-stu-id="c0cee-153">Each site was set up using a blank path.</span></span> <span data-ttu-id="c0cee-154">A continuación, se puede acceder a estos dos sitios en un navegador web de la siguiente manera utilizando el atributo **?domain=**:</span><span class="sxs-lookup"><span data-stu-id="c0cee-154">These two sites could then be accessed in a web browser as follows using the **?domain=** attribute:</span></span>
- `https://xyz.commerce.dynamics.com?domain=www.fabrikam.com`
- `https://xyz.commerce.dynamics.com?domain=www.contoso.com`

<span data-ttu-id="c0cee-155">Cuando no se proporciona una cadena de consulta de dominio en un entorno con varios dominios proporcionados, Commerce utiliza el primer dominio que proporcionó.</span><span class="sxs-lookup"><span data-stu-id="c0cee-155">When a domain query string is not given in an environment with multiple domains provided, Commerce uses the first domain you provided.</span></span> <span data-ttu-id="c0cee-156">Por ejemplo, si la ruta de acceso "fabrikam" se proporcionó primero durante la configuración del sitio, la dirección URL `https://xyz.commerce.dynamics.com` podría utilizarse para acceder al contenido del sitio publicado por `www.fabrikam.com`.</span><span class="sxs-lookup"><span data-stu-id="c0cee-156">For example, if the path "fabrikam" was provided first during site setup, the URL `https://xyz.commerce.dynamics.com` could be used to access the published site content site for `www.fabrikam.com`.</span></span>

## <a name="traffic-forwarding-in-production"></a><span data-ttu-id="c0cee-157">Reenvío de tráfico en producción</span><span class="sxs-lookup"><span data-stu-id="c0cee-157">Traffic forwarding in production</span></span>

<span data-ttu-id="c0cee-158">Puede simular varios dominios utilizando parámetros de cadena de consulta de dominio en el propio punto de conexión commerce.dynamics.com.</span><span class="sxs-lookup"><span data-stu-id="c0cee-158">You can simulate multiple domains using domain query string parameters on the commerce.dynamics.com endpoint itself.</span></span> <span data-ttu-id="c0cee-159">Pero cuando necesita comenzar a funcionar en producción, debe reenviar el tráfico de su dominio personalizado al punto de conexión `<e-Commerce tenant name>.commerce.dynamics.com`.</span><span class="sxs-lookup"><span data-stu-id="c0cee-159">But when you need to go live in production, you must forward the traffic for your custom domain to the `<e-Commerce tenant name>.commerce.dynamics.com` endpoint.</span></span>

<span data-ttu-id="c0cee-160">El punto de conexión `<e-Commerce tenant name>.commerce.dynamics.com` no es compatible con Secure Sockets Layers (SSL) de dominio personalizado, por lo que debe configurar dominios personalizados mediante un servicio de puerta principal o una red de entrega de contenido (CDN).</span><span class="sxs-lookup"><span data-stu-id="c0cee-160">The `<e-Commerce tenant name>.commerce.dynamics.com` endpoint does not support custom domain Secure Sockets Layers (SSLs), so you must set up custom domains using a front door service or content delivery network (CDN).</span></span> 

<span data-ttu-id="c0cee-161">Para configurar dominios personalizados usando un servicio de puerta principal o CDN, tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="c0cee-161">To set up custom domains using a front door service or CDN, you have two options:</span></span>

- <span data-ttu-id="c0cee-162">Configure un servicio de puerta de entrada como Azure Front Door para manejar el tráfico front-end y conectarse a su entorno de Commerce.</span><span class="sxs-lookup"><span data-stu-id="c0cee-162">Set up a front door service like Azure Front Door to handle front-end traffic and connect to your Commerce environment.</span></span> <span data-ttu-id="c0cee-163">Esto proporciona un mayor control sobre la gestión de certificados y dominios y políticas de seguridad más granulares.</span><span class="sxs-lookup"><span data-stu-id="c0cee-163">This provides greater control over domain and certificate management and more granular security policies.</span></span>
- <span data-ttu-id="c0cee-164">Use la instancia de Azure Front Door proporcionada por Commerce.</span><span class="sxs-lookup"><span data-stu-id="c0cee-164">Use the Commerce-supplied Azure Front Door instance.</span></span> <span data-ttu-id="c0cee-165">Esto requiere coordinar la acción con el equipo de Dynamics 365 Commerce para la verificación del dominio y la obtención de certificados SSL para su dominio de producción.</span><span class="sxs-lookup"><span data-stu-id="c0cee-165">This requires coordinating action with the Dynamics 365 Commerce team for domain verification and obtaining SSL certificates for your production domain.</span></span>

<span data-ttu-id="c0cee-166">Para obtener información sobre cómo configurar un servicio CDN directamente, consulte [Agregar soporte para una red de entrega de contenido (CDN)](add-cdn-support.md).</span><span class="sxs-lookup"><span data-stu-id="c0cee-166">For information about how to set up a CDN service directly, see [Add support for a content delivery network (CDN)](add-cdn-support.md).</span></span>

<span data-ttu-id="c0cee-167">Para usar la instancia de Azure Front Door proporcionada por Commerce, debe crear una solicitud de servicio para la asistencia de configuración de CDN del equipo de incorporación de Commerce.</span><span class="sxs-lookup"><span data-stu-id="c0cee-167">To use the Commerce-supplied Azure Front Door instance, you must create a service request for CDN setup assistance from the Commerce onboarding team.</span></span> 

- <span data-ttu-id="c0cee-168">Deberá proporcionar el nombre de su empresa, el dominio de producción, el identificador del entorno y el nombre del inquilino de comercio electrónico de producción.</span><span class="sxs-lookup"><span data-stu-id="c0cee-168">You will need to provide your company name, the production domain, environment ID, and production e-Commerce tenant name.</span></span> 
- <span data-ttu-id="c0cee-169">Deberá confirmar si se trata de un dominio existente (utilizado para un sitio actualmente activo) o un dominio nuevo.</span><span class="sxs-lookup"><span data-stu-id="c0cee-169">You will need to confirm if this is an existing domain (used for a currently active site) or a new domain.</span></span> 
- <span data-ttu-id="c0cee-170">Para un nuevo dominio, la verificación del dominio y el certificado SSL se pueden lograr en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="c0cee-170">For a new domain, the domain verification and SSL certificate can be achieved in a single step.</span></span> 
- <span data-ttu-id="c0cee-171">Para un dominio que sirve a un sitio web existente, se requiere un proceso de varios pasos para establecer la verificación del dominio y el certificado SSL.</span><span class="sxs-lookup"><span data-stu-id="c0cee-171">For a domain serving an existing website, there is a multistep process required to establish the domain verification and SSL certificate.</span></span> <span data-ttu-id="c0cee-172">Este proceso tiene un acuerdo de nivel de servicio (SLA) de 7 días hábiles para que un dominio entre en funcionamiento, ya que incluye varios pasos secuenciales.</span><span class="sxs-lookup"><span data-stu-id="c0cee-172">This process has a 7-working-day service level agreement (SLA) for a domain to go live, because it includes multiple sequential steps.</span></span>

<span data-ttu-id="c0cee-173">Para crear una solicitud de servicio en LCS, en su entorno vaya a **Soporte \> Problemas de soporte** y seleccione **Presentar un incidente**.</span><span class="sxs-lookup"><span data-stu-id="c0cee-173">To create a service request in LCS, within your environment go to **Support \> Support issues** and select **Submit an incident**.</span></span>

> [!NOTE]
> <span data-ttu-id="c0cee-174">Los dominios personalizados con SSL solo se admiten en entornos de producción.</span><span class="sxs-lookup"><span data-stu-id="c0cee-174">Custom domains with SSL are only supported on production environments.</span></span> <span data-ttu-id="c0cee-175">Para entornos que no son de producción, como los entornos aislados y pruebas de aceptación de usuarios (UAT), use la URL generada por Commerce para acceder al contenido publicado en un navegador web.</span><span class="sxs-lookup"><span data-stu-id="c0cee-175">For non-production environments such as sandbox and user acceptance testing (UAT), use the Commerce-generated URL to access published content in a web browser.</span></span>

## <a name="ssl-certificate-process"></a><span data-ttu-id="c0cee-176">Proceso de certificado SSL</span><span class="sxs-lookup"><span data-stu-id="c0cee-176">SSL certificate process</span></span>

<span data-ttu-id="c0cee-177">Cuando se presenta una solicitud de servicio, el equipo de Commerce coordinará los siguientes pasos con usted.</span><span class="sxs-lookup"><span data-stu-id="c0cee-177">When a service request is filed, the Commerce team will coordinate the following steps with you.</span></span>

<span data-ttu-id="c0cee-178">Para nuevos dominios:</span><span class="sxs-lookup"><span data-stu-id="c0cee-178">For new domains:</span></span>
- <span data-ttu-id="c0cee-179">El equipo de Commerce configurará la instancia de Azure Front Door (hospedada en Commerce).</span><span class="sxs-lookup"><span data-stu-id="c0cee-179">The Commerce team will set up the Azure Front Door instance (Commerce-hosted).</span></span>
- <span data-ttu-id="c0cee-180">El equipo de Commerce le proporcionará el registro CNAME para señalar su dominio personalizado.</span><span class="sxs-lookup"><span data-stu-id="c0cee-180">The Commerce team will then provide the CNAME record to point your custom domain.</span></span>
- <span data-ttu-id="c0cee-181">Después de que se actualice el registro CNAME, la instancia de Azure Front Door alojada en Commerce podrá verificar la propiedad del dominio y obtener el certificado SSL.</span><span class="sxs-lookup"><span data-stu-id="c0cee-181">After the CNAME record is updated, the Commerce-hosted Azure Front Door instance will be able to verify the domain ownership and get the SSL certificate.</span></span>

<span data-ttu-id="c0cee-182">Para dominios existentes y activos:</span><span class="sxs-lookup"><span data-stu-id="c0cee-182">For existing/active domains:</span></span>
- <span data-ttu-id="c0cee-183">El equipo de Commerce le indicará que agregue un registro CNAME `afdverify.<custom-domain>` para proporcionar a su proveedor de DNS de dominio.</span><span class="sxs-lookup"><span data-stu-id="c0cee-183">The Commerce team will instruct you to add an `afdverify.<custom-domain>` CNAME record to provide to your domain DNS provider.</span></span>
- <span data-ttu-id="c0cee-184">Cuando se complete, el equipo de Commerce agregará el dominio para la instancia de Azure Front Door y proporcionará registros TXT de DNS adicionales que se agregarán al DNS del dominio.</span><span class="sxs-lookup"><span data-stu-id="c0cee-184">When complete, the Commerce team will add the domain to the Azure Front Door instance and provide additional DNS TXT records to be added to the DNS for the domain.</span></span>
- <span data-ttu-id="c0cee-185">Una vez completados los registros TXT, el equipo de Commerce completará las actualizaciones de Azure Front Door para el dominio que configurará el certificado SSL.</span><span class="sxs-lookup"><span data-stu-id="c0cee-185">After the TXT records are completed, the Commerce team will complete the Azure Front Door updates for the domain that will set up the SSL certificate.</span></span>

## <a name="apex-domains"></a><span data-ttu-id="c0cee-186">Dominios Apex</span><span class="sxs-lookup"><span data-stu-id="c0cee-186">Apex domains</span></span>

<span data-ttu-id="c0cee-187">La instancia de Azure Front Door proporcionada por Commerce no admite dominios apex (dominios raíz que no contienen subdominios).</span><span class="sxs-lookup"><span data-stu-id="c0cee-187">The Commerce-supplied Azure Front Door instance does not support apex domains (root domains that do not contain subdomains).</span></span> <span data-ttu-id="c0cee-188">Los dominios apex requieren una dirección IP para resolverse y la instancia de Azure Front Door de Commerce existe solo con puntos de conexión virtuales.</span><span class="sxs-lookup"><span data-stu-id="c0cee-188">Apex domains require an IP address to resolve, and the Commerce Azure Front Door instance exists with virtual endpoints only.</span></span> <span data-ttu-id="c0cee-189">Para usar un dominio apex, tiene dos opciones:</span><span class="sxs-lookup"><span data-stu-id="c0cee-189">To use an apex domain, you have two options:</span></span>

- <span data-ttu-id="c0cee-190">**Opción 1**: utilice su proveedor de DNS para redirigir el dominio apex a un dominio "www".</span><span class="sxs-lookup"><span data-stu-id="c0cee-190">**Option 1** - Use your DNS provider to redirect the apex domain to a "www" domain.</span></span> <span data-ttu-id="c0cee-191">Por ejemplo, fabrikam.com redirige a `www.fabrikam.com` donde `www.fabrikam.com` es el registro CNAME que apunta a la instancia de Azure Front Door hospedada en Commerce.</span><span class="sxs-lookup"><span data-stu-id="c0cee-191">For example, fabrikam.com redirects to `www.fabrikam.com` where `www.fabrikam.com` is the CNAME record that points to the Commerce-hosted Azure Front Door instance.</span></span>

- <span data-ttu-id="c0cee-192">**Opcion 2**: configure una instancia de CDN/puerta de entrada por su cuenta para hospedar el dominio apex.</span><span class="sxs-lookup"><span data-stu-id="c0cee-192">**Option 2** - Set up a CDN/front door instance on your own to host the apex domain.</span></span>

> [!NOTE]
> <span data-ttu-id="c0cee-193">Si usa Azure Front Door, también debe configurar una instancia de Azure DNS en la misma suscripción.</span><span class="sxs-lookup"><span data-stu-id="c0cee-193">If you are using Azure Front Door, you must also set up an Azure DNS in the same subscription.</span></span> <span data-ttu-id="c0cee-194">El dominio apex alojado en Azure DNS puede apuntar a su instancia Azure Front Door como un registro de alias.</span><span class="sxs-lookup"><span data-stu-id="c0cee-194">The apex domain hosted on Azure DNS can point to your Azure Front Door as an alias record.</span></span> <span data-ttu-id="c0cee-195">Esta es la única solución alternativa, ya que los dominios apex siempre deben apuntar a una dirección IP.</span><span class="sxs-lookup"><span data-stu-id="c0cee-195">This is the only work around, as apex domains must always point to an IP address.</span></span>

  ## <a name="additional-resources"></a><span data-ttu-id="c0cee-196">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c0cee-196">Additional resources</span></span>

  [<span data-ttu-id="c0cee-197">Implementar un sitio nuevo de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="c0cee-197">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

  [<span data-ttu-id="c0cee-198">Configurar un canal de la tienda en línea</span><span class="sxs-lookup"><span data-stu-id="c0cee-198">Set up an online store channel</span></span>](online-stores.md)

  [<span data-ttu-id="c0cee-199">Crear un sitio de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="c0cee-199">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

  [<span data-ttu-id="c0cee-200">Asociar un sitio en línea con un canal</span><span class="sxs-lookup"><span data-stu-id="c0cee-200">Associate an online site with a channel</span></span>](associate-site-online-store.md)

  [<span data-ttu-id="c0cee-201">Administrar archivos robots.txt</span><span class="sxs-lookup"><span data-stu-id="c0cee-201">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

  [<span data-ttu-id="c0cee-202">Subir redireccionamientos de URL en grandes cantidades</span><span class="sxs-lookup"><span data-stu-id="c0cee-202">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

  [<span data-ttu-id="c0cee-203">Configurar un inquilino B2C en Commerce</span><span class="sxs-lookup"><span data-stu-id="c0cee-203">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

  [<span data-ttu-id="c0cee-204">Configurar páginas personalizadas para inicios de sesión de usuario</span><span class="sxs-lookup"><span data-stu-id="c0cee-204">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

  [<span data-ttu-id="c0cee-205">Configurar múltiples inquilinos B2C en un entorno de Commerce</span><span class="sxs-lookup"><span data-stu-id="c0cee-205">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

  [<span data-ttu-id="c0cee-206">Agregar soporte para una red de entrega de contenido (CDN)</span><span class="sxs-lookup"><span data-stu-id="c0cee-206">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

  [<span data-ttu-id="c0cee-207">Habilitar la detección de tienda según la ubicación</span><span class="sxs-lookup"><span data-stu-id="c0cee-207">Enable location-based store detection</span></span>](enable-store-detection.md)