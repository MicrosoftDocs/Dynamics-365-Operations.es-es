---
title: Módulo de consentimiento de cookies
description: En este tema se tratan los módulos consentimiento de cookies y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 57c8876f1faf08ce965ccd796551996a8651e2eb
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5213947"
---
# <a name="cookie-consent-module"></a><span data-ttu-id="4e484-103">Módulo de consentimiento de cookies</span><span class="sxs-lookup"><span data-stu-id="4e484-103">Cookie consent module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4e484-104">En este tema se tratan los módulos consentimiento de cookies y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4e484-104">This topic covers cookie consent modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="4e484-105">El módulo de consentimiento de cookies solicita a los usuarios del sitio que brinden consentimiento explícito para permitir cookies para cualquier característica o módulo que rastree las cookies del navegador.</span><span class="sxs-lookup"><span data-stu-id="4e484-105">The cookie consent module prompts site users to explicitly provide consent to allow cookies for any feature or module that tracks browser cookies.</span></span> <span data-ttu-id="4e484-106">Se requiere el consentimiento la primera vez que un usuario del sitio navega por un sitio en una nueva sesión de navegador.</span><span class="sxs-lookup"><span data-stu-id="4e484-106">The consent is required the first time a site user browses a site in a new browser session.</span></span> <span data-ttu-id="4e484-107">Cuando se recibe el consentimiento, se realiza un seguimiento y no se volverá a solicitar el consentimiento al usuario del sitio.</span><span class="sxs-lookup"><span data-stu-id="4e484-107">When consent is received, it is tracked and the site user will not be prompted for consent again.</span></span> <span data-ttu-id="4e484-108">Para obtener más información, consulte [Cumplimiento de las cookies](cookie-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="4e484-108">For more information, see [Cookie compliance](cookie-compliance.md).</span></span>

<span data-ttu-id="4e484-109">Si no se recibe el consentimiento de las cookies del usuario del sitio, las funciones o módulos que requieran el consentimiento de las cookies no se mostrarán en la página.</span><span class="sxs-lookup"><span data-stu-id="4e484-109">If site user cookie consent is not received, any features or modules that require cookie consent will not be rendered on the page.</span></span> <span data-ttu-id="4e484-110">Por ejemplo, el módulo de pago, el módulo para compartir en redes sociales y la función de tienda preferida requieren el consentimiento de las cookies y no se mostrarán si no se recibe el consentimiento del usuario del sitio.</span><span class="sxs-lookup"><span data-stu-id="4e484-110">For example, the checkout module, social share module, and preferred store feature all require cookie consent and will not be rendered if site user consent is not received.</span></span> 

<span data-ttu-id="4e484-111">Se puede configurar un módulo de consentimiento de cookies en el fragmento de encabezado de una página para que se pueda hacer cumplir cuando se carga la página.</span><span class="sxs-lookup"><span data-stu-id="4e484-111">A cookie consent module can be configured on a page's header fragment so that it can be enforced when the page loads.</span></span> <span data-ttu-id="4e484-112">El módulo de consentimiento de cookies debe tener un mensaje claro que informe al usuario del sitio sobre el uso de cookies en el sitio y debe proporcionar un enlace a la página de privacidad del sitio.</span><span class="sxs-lookup"><span data-stu-id="4e484-112">The cookie consent module should have a clear message informing the site user about cookie usage on the site and should provide a link to the site's privacy page.</span></span>

<span data-ttu-id="4e484-113">La siguiente ilustración destaca un ejemplo de un mensaje de consentimiento de cookies con un enlace a la página de política de privacidad del sitio que se muestra en el encabezado de una página del sitio.</span><span class="sxs-lookup"><span data-stu-id="4e484-113">The following illustration highlights an example of a cookie consent message with a link to the site's privacy policy page displayed on the header of a site page.</span></span>
<span data-ttu-id="4e484-114">![Ejemplo de un módulo de consentimiento de cookies](./media/ecommerce-cookieconsent.png)</span><span class="sxs-lookup"><span data-stu-id="4e484-114">![Example of a cookie consent module](./media/ecommerce-cookieconsent.png)</span></span>

## <a name="cookie-consent-module-properties"></a><span data-ttu-id="4e484-115">Propiedades del módulo de consentimiento de cookies</span><span class="sxs-lookup"><span data-stu-id="4e484-115">Cookie consent module properties</span></span>

| <span data-ttu-id="4e484-116">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="4e484-116">Property name</span></span>             | <span data-ttu-id="4e484-117">Valor</span><span class="sxs-lookup"><span data-stu-id="4e484-117">Value</span></span>                 | <span data-ttu-id="4e484-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="4e484-118">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="4e484-119">Texto enriquecido</span><span class="sxs-lookup"><span data-stu-id="4e484-119">Rich Text</span></span>                  | <span data-ttu-id="4e484-120">Texto enriquecido</span><span class="sxs-lookup"><span data-stu-id="4e484-120">Rich Text</span></span> | <span data-ttu-id="4e484-121">Especifica una notificación de texto enriquecido para los usuarios del sitio de que el sitio utiliza cookies del navegador y que los usuarios deben aceptar el uso de cookies para que el sitio sea completamente funcional.</span><span class="sxs-lookup"><span data-stu-id="4e484-121">Specifies a Rich Text notification to site users that the site uses browser cookies and that users should accept the use of cookies for the site to be fully functional.</span></span> |
| <span data-ttu-id="4e484-122">Vínculos</span><span class="sxs-lookup"><span data-stu-id="4e484-122">Links</span></span> | <span data-ttu-id="4e484-123">URL</span><span class="sxs-lookup"><span data-stu-id="4e484-123">URL</span></span> | <span data-ttu-id="4e484-124">Se pueden agregar uno o más vínculos a la página de privacidad de un sitio que describe los tipos de cookies que se rastrean en el sitio.</span><span class="sxs-lookup"><span data-stu-id="4e484-124">One or more links can be added to a site's privacy page that describes the types of cookies that are tracked on the site.</span></span> |

## <a name="add-a-cookie-consent-module-to-site-pages"></a><span data-ttu-id="4e484-125">Agregar un módulo de consentimiento de cookies a las páginas del sitio</span><span class="sxs-lookup"><span data-stu-id="4e484-125">Add a cookie consent module to site pages</span></span>

<span data-ttu-id="4e484-126">Para agregar de manera eficiente un módulo de consentimiento de cookies a varias páginas del sitio, se puede agregar a un fragmento de encabezado de página compartida.</span><span class="sxs-lookup"><span data-stu-id="4e484-126">To efficiently add a cookie consent module to multiple site pages, it can be added to a shared page header fragment.</span></span> <span data-ttu-id="4e484-127">Una vez que se agrega el fragmento de encabezado a todas las páginas del sitio, se presentará automáticamente una notificación de consentimiento de cookies la primera vez que un usuario del sitio navegue a cualquier página del sitio.</span><span class="sxs-lookup"><span data-stu-id="4e484-127">After the header fragment is added to all site pages, a cookie consent notification will automatically be rendered the first time a site user navigates to any site page.</span></span>

<span data-ttu-id="4e484-128">Para obtener más información sobre módulos y fragmentos de encabezado, consulte [Módulo de encabezado](author-header-module.md).</span><span class="sxs-lookup"><span data-stu-id="4e484-128">For more information about header fragments and modules, see [Header module](author-header-module.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="4e484-129">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4e484-129">Additional resources</span></span>

[<span data-ttu-id="4e484-130">Visión general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="4e484-130">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="4e484-131">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="4e484-131">Header module</span></span>](author-header-module.md) 

[<span data-ttu-id="4e484-132">Cumplimiento de cookies</span><span class="sxs-lookup"><span data-stu-id="4e484-132">Cookie compliance</span></span>](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]