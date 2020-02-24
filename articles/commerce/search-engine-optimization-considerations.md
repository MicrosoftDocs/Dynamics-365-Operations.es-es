---
title: Consideraciones de optimización de motor de búsqueda (SEO) para su sitio
description: Este tema trata las consideraciones de la optimización de motor de búsqueda (SEO) para su sitio desde el desarrollo hasta la producción.
author: psimolin
manager: annbe
ms.date: 10/01/2019
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
ms.openlocfilehash: 7c7afed8e4620d5fe49ead47eb6c17d97d7492ad
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3002820"
---
# <a name="search-engine-optimization-seo-considerations-for-your-site"></a><span data-ttu-id="93b64-103">Consideraciones de optimización de motor de búsqueda (SEO) para su sitio</span><span class="sxs-lookup"><span data-stu-id="93b64-103">Search engine optimization (SEO) considerations for your site</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="93b64-104">Este tema trata las consideraciones de la optimización de motor de búsqueda (SEO) para su sitio desde el desarrollo hasta la producción.</span><span class="sxs-lookup"><span data-stu-id="93b64-104">This topic covers earch engine optimization (SEO) considerations for your site from development to production.</span></span>

## <a name="a-site-that-is-under-development"></a><span data-ttu-id="93b64-105">Un sitio que se encuentra en desarrollo</span><span class="sxs-lookup"><span data-stu-id="93b64-105">A site that is under development</span></span>

<span data-ttu-id="93b64-106">Aunque un sitio esté en desarrollo, todas las páginas del sitio deben tener las etiquetas META **NOINDEX** y **NOFOLLOW**, de modo que los motores de búsqueda no indicen las páginas y las versiones de desarrollo de tienda de su sitio en su memoria caché.</span><span class="sxs-lookup"><span data-stu-id="93b64-106">While a site is under development, all site pages should have the **NOINDEX** and **NOFOLLOW** meta tags, so that search engines don't index the pages and store development versions of your site in their cache.</span></span> <span data-ttu-id="93b64-107">Para realizar esta configuración, debe agregar el módulo predeterminado de etiquetas META a la plantilla de página del sitio.</span><span class="sxs-lookup"><span data-stu-id="93b64-107">To do this configuration, you must add the default meta tags module to the site page template.</span></span> <span data-ttu-id="93b64-108">Las propiedades de etiquetas META predeterminadas estarán entonces disponibles en la sección de propiedades SEO del editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="93b64-108">The default meta tags properties will then be available in the SEO properties section in the page editor.</span></span> <span data-ttu-id="93b64-109">Puede usar estas propiedades para administrar las etiquetas META.</span><span class="sxs-lookup"><span data-stu-id="93b64-109">You can use these properties to manage the meta tags.</span></span>

## <a name="soft-launch-of-a-site"></a><span data-ttu-id="93b64-110">Lanzamiento suave de un sitio</span><span class="sxs-lookup"><span data-stu-id="93b64-110">Soft launch of a site</span></span>

<span data-ttu-id="93b64-111">Durante un “lanzamiento suave”, un sitio web se a pone a disposición de un mercado o público limitado antes de que se produzca el lanzamiento completo.</span><span class="sxs-lookup"><span data-stu-id="93b64-111">During a "soft launch," a website is made available to a limited audience or market before the full launch occurs.</span></span> <span data-ttu-id="93b64-112">Si realiza un lanzamiento suave de su sitio web, debe pensar en dejar las etiquetas META **NOINDEX** en su lugar.</span><span class="sxs-lookup"><span data-stu-id="93b64-112">If you do a soft launch of your website, you should consider leaving the **NOINDEX** meta tags in place.</span></span> <span data-ttu-id="93b64-113">De esta manera, ayuda a garantizar que el lanzamiento suave permanece restringido al público limitado al que desea llegar.</span><span class="sxs-lookup"><span data-stu-id="93b64-113">In this way, you help guarantee that the soft launch remains restricted to the limited audience that you want to reach.</span></span>

## <a name="a-site-that-is-in-production"></a><span data-ttu-id="93b64-114">Un sitio que está en producción</span><span class="sxs-lookup"><span data-stu-id="93b64-114">A site that is in production</span></span>

<span data-ttu-id="93b64-115">Cuando un sitio se encuentra en producción, debe asegurarse de que todas las páginas del sitio están etiquetadas correctamente.</span><span class="sxs-lookup"><span data-stu-id="93b64-115">When a site is in production, you should make sure that all site pages are correctly tagged.</span></span> <span data-ttu-id="93b64-116">Microsoft Dynamics 365 Commerce usa la información especificada para que una página represente toda la información de SEO en esa página.</span><span class="sxs-lookup"><span data-stu-id="93b64-116">Microsoft Dynamics 365 Commerce uses the information that is entered for a page to render all the SEO information on that page.</span></span> <span data-ttu-id="93b64-117">Los siguientes módulos ofrecen esta funcionalidad: resumen de páginas de categoría, resumen de páginas de lista y resumen de páginas de producto.</span><span class="sxs-lookup"><span data-stu-id="93b64-117">The following modules provide this functionality: category page summary, list page summary, and product page summary.</span></span>

<span data-ttu-id="93b64-118">Para optimizar la indexación del motor de búsqueda, el marco de representación usa la información de las propiedades SEO que se configuran en Dynamics 365 Commerce y la información específica del módulo.</span><span class="sxs-lookup"><span data-stu-id="93b64-118">To optimize search engine indexing, the rendering framework uses both information from the SEO properties that are configured in Dynamics 365 Commerce and module-specific information.</span></span> <span data-ttu-id="93b64-119">Para un sitio que está en la producción, debe asegurarse de que el archivo robots.txt permite la indexación de su sitio completo y que contiene vínculos al documento publicado del mapa del sitio.</span><span class="sxs-lookup"><span data-stu-id="93b64-119">For a site that is in production, you should make sure that the robots.txt file allows for indexing of your whole site, and that it contains links to your published site map document.</span></span> <span data-ttu-id="93b64-120">Debe activar la funcionalidad de generación del mapa de sitio en **Valores de configuración de sitio \> Mapas del sitio habilitados**.</span><span class="sxs-lookup"><span data-stu-id="93b64-120">You should turn on the site map generation functionality at **Site Settings \> Site maps enabled**.</span></span>

### <a name="page-seo-settings-for-internal-preview-limited-audiences-and-all-audiences"></a><span data-ttu-id="93b64-121">Configuración SEO de página para vista previa interna, públicos limitados y todas las audiencias</span><span class="sxs-lookup"><span data-stu-id="93b64-121">Page SEO settings for internal preview, limited audiences, and all audiences</span></span>

<span data-ttu-id="93b64-122">Dado que Dynamics 365 Commerce admite vistas previas autenticadas “Lo que se ve es lo que se verá" (WYSIWYG), los autores pueden preparar su contenido de páginas sin tener que preocuparse de que la información estará visible para los visitantes del sitio.</span><span class="sxs-lookup"><span data-stu-id="93b64-122">Because Dynamics 365 Commerce supports "what you see is what you get" (WYSIWYG) authenticated previews, authors can prepare their page content without having to worry that the information will become visible to site visitors.</span></span> <span data-ttu-id="93b64-123">Si se debe publicar una página, pero su exposición debe estar limitada, debe tener la etiqueta META **NOINDEX**, de modo que no se vaya a indexar por motores de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="93b64-123">If a page must be published, but its exposure must be limited, it should have the **NOINDEX** meta tag, so that it won't be indexed by search engines.</span></span> <span data-ttu-id="93b64-124">A continuación, cuando la página está lista para todos los públicos, todos los metadatos SEO básicos deben estar presentes, para maximizar la eficacia de la indexación del motor de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="93b64-124">Then, when the page is ready for all audiences, all the basic SEO metadata should be present, to maximize the efficiency of search engine indexing.</span></span> <span data-ttu-id="93b64-125">Además, se debe eliminar la etiqueta META **NOLIMIT**.</span><span class="sxs-lookup"><span data-stu-id="93b64-125">Additionally, the **NOLIMIT** meta tag should be removed.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="93b64-126">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="93b64-126">Additional resources</span></span>

[<span data-ttu-id="93b64-127">Administrar usuarios y roles de comercio electrónico</span><span class="sxs-lookup"><span data-stu-id="93b64-127">Manage e-Commerce users and roles</span></span>](manage-ecommerce-users-roles.md)

[<span data-ttu-id="93b64-128">Agregar secuencia de comandos a páginas del sitio para admitir telemetría</span><span class="sxs-lookup"><span data-stu-id="93b64-128">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)

[<span data-ttu-id="93b64-129">Gestionar la directiva de seguridad de contenido (CSP)</span><span class="sxs-lookup"><span data-stu-id="93b64-129">Manage Content Security Policy (CSP)</span></span>](manage-csp.md)
