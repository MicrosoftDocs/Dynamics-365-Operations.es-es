---
title: Comprobar la accesibilidad de contenido de página
description: En este tema se describe cómo comprobar la accesibilidad del contenido de página en Microsoft Dynamics 365 Commerce.
author: josaw1
manager: annbe
ms.date: 01/08/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: josaw
ms.search.validFrom: 2019-12-19
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 7690f3bb17a56b9a16b6e818b675064b1979948e
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2021
ms.locfileid: "5097374"
---
# <a name="verify-page-content-accessibility"></a><span data-ttu-id="7d9fb-103">Comprobar la accesibilidad de contenido de página</span><span class="sxs-lookup"><span data-stu-id="7d9fb-103">Verify page content accessibility</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="7d9fb-104">En este tema se describe cómo comprobar la accesibilidad del contenido de página en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7d9fb-104">This topic describes how to verify the accessibility of page content in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="7d9fb-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="7d9fb-105">Overview</span></span>

<span data-ttu-id="7d9fb-106">Cuando haya terminado de modificar una página debe asegurarse de que el contenido sea accesible para todos en la web.</span><span class="sxs-lookup"><span data-stu-id="7d9fb-106">When you've finished changing a page, you should make sure that the content is accessible to everyone on the web.</span></span> <span data-ttu-id="7d9fb-107">En las herramientas de creación de Commerce, puede comprobar fácilmente la accesibilidad del contenido de página mediante el servicio [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integrado.</span><span class="sxs-lookup"><span data-stu-id="7d9fb-107">In the Commerce authoring tools, you can easily verify the accessibility of page content by using the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service.</span></span> <span data-ttu-id="7d9fb-108">Este servicio comprueba el contenido de su página siguiendo las directrices más recientes de [Accesibilidad del World Wide Web Consortium (W3C)](https://www.w3.org/standards/webdesign/accessibility).</span><span class="sxs-lookup"><span data-stu-id="7d9fb-108">This service verifies your page content against the latest [World Wide Web Consortium (W3C) accessibility](https://www.w3.org/standards/webdesign/accessibility) guidelines.</span></span>

<span data-ttu-id="7d9fb-109">La integración de [Microsoft Accessibility Insights](https://accessibilityinsights.io/) debe estar activada a nivel de suscriptor o sitio antes de poder usarla.</span><span class="sxs-lookup"><span data-stu-id="7d9fb-109">The [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration must be turned on at the tenant or site level before you can use it.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-all-the-sites-in-your-tenant"></a><span data-ttu-id="7d9fb-110">Active Microsoft Accessibility Insights para todos los sitios de su suscriptor</span><span class="sxs-lookup"><span data-stu-id="7d9fb-110">Turn on Microsoft Accessibility Insights for all the sites in your tenant</span></span>

<span data-ttu-id="7d9fb-111">Para activar la integración de [Microsoft Accessibility Insights](https://accessibilityinsights.io/) para todos los sitios de Commerce en su suscriptor, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="7d9fb-111">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for all the Commerce sites in your tenant, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="7d9fb-112">Para acceder a la configuración del suscriptor debe iniciar sesión en Commerce como administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="7d9fb-112">To access tenant settings, you must be signed in to Commerce as a system admin.</span></span>

1. <span data-ttu-id="7d9fb-113">Inicie sesión en Commerce como administrador del sistema.</span><span class="sxs-lookup"><span data-stu-id="7d9fb-113">Sign in to Commerce as a system admin.</span></span>
1. <span data-ttu-id="7d9fb-114">En el panel de navegación izquierdo, seleccione **Configuración del suscriptor** (junto al símbolo de engranaje) para expandirlo.</span><span class="sxs-lookup"><span data-stu-id="7d9fb-114">In the left navigation pane, select **Tenant Settings** (next to the gear symbol) to expand it.</span></span>
1. <span data-ttu-id="7d9fb-115">En **Configuración del suscriptor**, seleccione **Características**.</span><span class="sxs-lookup"><span data-stu-id="7d9fb-115">Under **Tenant Settings**, select **Features**.</span></span>
1. <span data-ttu-id="7d9fb-116">Establezca la opción **Comprobación de accesibilidad** en **Activada**.</span><span class="sxs-lookup"><span data-stu-id="7d9fb-116">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="turn-on-microsoft-accessibility-insights-for-a-single-site"></a><span data-ttu-id="7d9fb-117">Active Microsoft Accessibility Insights para un solo sitio</span><span class="sxs-lookup"><span data-stu-id="7d9fb-117">Turn on Microsoft Accessibility Insights for a single site</span></span>

<span data-ttu-id="7d9fb-118">Para activar la integración de [Microsoft Accessibility Insights](https://accessibilityinsights.io/) para un solo sitio de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="7d9fb-118">To turn on the [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integration for a single Commerce site, follow these steps.</span></span>

1. <span data-ttu-id="7d9fb-119">En **Sitios**, seleccione **Fabrikam** (o el nombre del sitio).</span><span class="sxs-lookup"><span data-stu-id="7d9fb-119">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="7d9fb-120">En el panel de navegación izquierdo, seleccione **Valores de configuración del sitio** para expandirlo</span><span class="sxs-lookup"><span data-stu-id="7d9fb-120">In the left navigation pane, select **Site Settings** to expand it.</span></span>
1. <span data-ttu-id="7d9fb-121">En **Valor de configuración del sitio**, seleccione **Características**.</span><span class="sxs-lookup"><span data-stu-id="7d9fb-121">Under **Site Settings**, select **Features**.</span></span>
1. <span data-ttu-id="7d9fb-122">Establezca la opción **Comprobación de accesibilidad** en **Activada**.</span><span class="sxs-lookup"><span data-stu-id="7d9fb-122">Set the **Accessibility Check** option to **On**.</span></span>

## <a name="verify-the-accessibility-of-the-content-on-the-home-page"></a><span data-ttu-id="7d9fb-123">Compruebe la accesibilidad del contenido en la página de inicio</span><span class="sxs-lookup"><span data-stu-id="7d9fb-123">Verify the accessibility of the content on the home page</span></span>

<span data-ttu-id="7d9fb-124">Para utilizar el servicio [Microsoft Accessibility Insights](https://accessibilityinsights.io/) integrado para escanear y comprobar el contenido de su página de inicio en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="7d9fb-124">To use the integrated [Microsoft Accessibility Insights](https://accessibilityinsights.io/) service to scan and verify the content of your home page in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="7d9fb-125">En **Sitios**, seleccione **Fabrikam** (o el nombre del sitio).</span><span class="sxs-lookup"><span data-stu-id="7d9fb-125">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="7d9fb-126">En el panel de navegación izquierdo, seleccione **Páginas**.</span><span class="sxs-lookup"><span data-stu-id="7d9fb-126">In the left navigation pane, select **Pages**.</span></span>
1. <span data-ttu-id="7d9fb-127">Busque y seleccione la página principal para abrirla en el editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="7d9fb-127">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="7d9fb-128">En la barra de comandos, seleccione **Comprobar accesibilidad**.</span><span class="sxs-lookup"><span data-stu-id="7d9fb-128">On the command bar, select **Check accessibility**.</span></span> <span data-ttu-id="7d9fb-129">Se abre la página **Comprobar accesibilidad**.</span><span class="sxs-lookup"><span data-stu-id="7d9fb-129">The **Check Accessibility** page appears.</span></span>
1. <span data-ttu-id="7d9fb-130">Una vez completado el escaneo, revise el contenido del informe.</span><span class="sxs-lookup"><span data-stu-id="7d9fb-130">After the scan is completed, review the contents of the report.</span></span>
1. <span data-ttu-id="7d9fb-131">En caso de error de alguna comprobación, marque el elemento para expandirlo y ver más detalles.</span><span class="sxs-lookup"><span data-stu-id="7d9fb-131">If any checks failed, select each failed check item to expand it so that you can view more details.</span></span>
1. <span data-ttu-id="7d9fb-132">Para cerrar el informe una vez que haya terminado de revisarlo, desplácese hasta la parte inferior de la página **Comprobar accesibilidad** y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="7d9fb-132">To close the report after you've finished reviewing it, scroll to the bottom of the **Check Accessibility** page, and select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7d9fb-133">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="7d9fb-133">Additional resources</span></span>

[<span data-ttu-id="7d9fb-134">Modificar una página de sitio existente</span><span class="sxs-lookup"><span data-stu-id="7d9fb-134">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="7d9fb-135">Agregar una página de sitio nueva</span><span class="sxs-lookup"><span data-stu-id="7d9fb-135">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="7d9fb-136">Seleccionar diseños de página</span><span class="sxs-lookup"><span data-stu-id="7d9fb-136">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="7d9fb-137">Administrar metadatos de SEO</span><span class="sxs-lookup"><span data-stu-id="7d9fb-137">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="7d9fb-138">Guardar, obtener una vista previa y publicar una página</span><span class="sxs-lookup"><span data-stu-id="7d9fb-138">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="7d9fb-139">Enriquecer una página de producto</span><span class="sxs-lookup"><span data-stu-id="7d9fb-139">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="7d9fb-140">Enriquecer una página de aterrizaje de categoría</span><span class="sxs-lookup"><span data-stu-id="7d9fb-140">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="7d9fb-141">Crear páginas de comercio electrónico dinámicas basadas en parámetros de URL</span><span class="sxs-lookup"><span data-stu-id="7d9fb-141">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)
