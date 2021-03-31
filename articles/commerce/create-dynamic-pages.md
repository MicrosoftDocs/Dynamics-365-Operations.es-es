---
title: Crear páginas de comercio electrónico dinámicas basadas en parámetros de URL
description: Este tema describe cómo configurar una página de comercio electrónico de Microsoft Dynamics 365 Commerce que puede ofrecer contenido dinámico, según los parámetros de URL.
author: StuHarg
manager: AnnBe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ROBOTS: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.author: stuharg
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: 10.0.17
ms.openlocfilehash: 8d6b4756fc81dc99786da251d5d9a575a71ccc49
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5208024"
---
# <a name="create-dynamic-e-commerce-pages-based-on-url-parameters"></a><span data-ttu-id="ba2c7-103">Crear páginas de comercio electrónico dinámicas basadas en parámetros de URL</span><span class="sxs-lookup"><span data-stu-id="ba2c7-103">Create dynamic e-commerce pages based on URL parameters</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="ba2c7-104">Este tema describe cómo configurar una página de comercio electrónico de Microsoft Dynamics 365 Commerce que puede ofrecer contenido dinámico, según los parámetros de URL.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-104">This topic describes how to set up a Microsoft Dynamics 365 Commerce e-commerce page that can serve dynamic content, based on URL parameters.</span></span>

<span data-ttu-id="ba2c7-105">Una página de comercio electrónico se puede configurar para ofrecer contenido diferente, según un segmento de la ruta de la URL.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-105">An e-commerce page can be configured to serve different content, based on a segment in the URL path.</span></span> <span data-ttu-id="ba2c7-106">Por lo tanto, la página se conoce como página dinámica.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-106">Therefore, the page is known as a dynamic page.</span></span> <span data-ttu-id="ba2c7-107">El segmento se utiliza como parámetro para recuperar el contenido de la página.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-107">The segment is used as a parameter to retrieve the page content.</span></span> <span data-ttu-id="ba2c7-108">Por ejemplo, una página que se llama **blog\_viewer** se crea y se asocia con la URL `https://fabrikam.com/blog`.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-108">For example, a page that is named **blog\_viewer** is created and associated with the URL `https://fabrikam.com/blog`.</span></span> <span data-ttu-id="ba2c7-109">Esta página se puede utilizar para mostrar contenido diferente, según el último segmento de la ruta de la URL.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-109">This page can then be used to show different content, based on the last segment in the URL path.</span></span> <span data-ttu-id="ba2c7-110">Por ejemplo, el último segmento de la URL `https://fabrikam.com/blog/article-1` es **article-1**.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-110">For example, the last segment in the URL `https://fabrikam.com/blog/article-1` is **article-1**.</span></span>

<span data-ttu-id="ba2c7-111">Las páginas personalizadas independientes que anulan la página dinámica también se pueden asociar con segmentos en la ruta de la URL.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-111">Separate custom pages that override the dynamic page can also be associated with segments in the URL path.</span></span> <span data-ttu-id="ba2c7-112">Por ejemplo, una página que se llama **blog\_summary** se crea y se asocia con la URL `https://fabrikam.com/blog/about-this-blog`.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-112">For example, a page that is named **blog\_summary** is created and associated with the URL `https://fabrikam.com/blog/about-this-blog`.</span></span> <span data-ttu-id="ba2c7-113">Cuando se solicita esta URL, se devuelve la página **blog\_summary** que está asociada con el parámetro **/about-this-blog**, en lugar de la página **blog\_viewer**.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-113">When this URL is requested, the **blog\_summary** page that is associated with the **/about-this-blog** parameter is returned instead of the **blog\_viewer** page.</span></span>

> [!NOTE]
> <span data-ttu-id="ba2c7-114">La funcionalidad para alojar, recuperar y mostrar contenido de páginas dinámicas se implementa mediante un módulo personalizado.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-114">The functionality for hosting, retrieving, and showing dynamic page content is implemented by using a custom module.</span></span> <span data-ttu-id="ba2c7-115">Para más información, vea [Extensibilidad de canales en línea](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="ba2c7-115">For more information, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

## <a name="set-up-a-dynamic-e-commerce-page"></a><span data-ttu-id="ba2c7-116">Configurar una página de comercio electrónico dinámica</span><span class="sxs-lookup"><span data-stu-id="ba2c7-116">Set up a dynamic e-commerce page</span></span>

<span data-ttu-id="ba2c7-117">Para configurar una página de comercio electrónico dinámica, debe crear la página dinámica, crear la URL base y configurar la ruta a la página dinámica.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-117">To set up a dynamic e-commerce page, you must create the dynamic page, create the base URL, and configure the route to the dynamic page.</span></span>

### <a name="create-the-page-that-will-serve-dynamic-content"></a><span data-ttu-id="ba2c7-118">Crear la página que ofrecerá contenido dinámico</span><span class="sxs-lookup"><span data-stu-id="ba2c7-118">Create the page that will serve dynamic content</span></span>

<span data-ttu-id="ba2c7-119">Para crear una página que ofrezca contenido dinámico, siga los pasos de [Agregar una nueva página de sitio](add-new-page.md).</span><span class="sxs-lookup"><span data-stu-id="ba2c7-119">To create a page that will serve dynamic content, follow the steps in [Add a new site page](add-new-page.md).</span></span> <span data-ttu-id="ba2c7-120">La página que cree requerirá la implementación de un módulo que utilice el último segmento de la ruta de la URL para recuperar contenido de un origen de datos externo.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-120">The page that you create will require implementation of a module that uses the last segment in the URL path to retrieve content from an external data source.</span></span> <span data-ttu-id="ba2c7-121">Para obtener más información sobre el desarrollo de módulos personalizados, consulte [Extensibilidad de canales en línea](e-commerce-extensibility/overview.md).</span><span class="sxs-lookup"><span data-stu-id="ba2c7-121">For more information about custom module development, see [Online channel extensibility](e-commerce-extensibility/overview.md).</span></span>

### <a name="create-the-base-url-for-the-dynamic-page"></a><span data-ttu-id="ba2c7-122">Crear la URL base para la página dinámica</span><span class="sxs-lookup"><span data-stu-id="ba2c7-122">Create the base URL for the dynamic page</span></span>

<span data-ttu-id="ba2c7-123">Para crear la URL base para la página dinámica en el creador de sitios de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-123">To create the base URL for the dynamic page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="ba2c7-124">Vaya a **URL** y seleccione **Nueva \> Nueva URL**.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-124">Go to **URLs**, and select **New \> New URL**.</span></span>
1. <span data-ttu-id="ba2c7-125">En el cuadro de diálogo **Crear nueva URL**, seleccione **Página interna**.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-125">In the **Create new URL** dialog box, select **Internal page**.</span></span> <span data-ttu-id="ba2c7-126">En **Ruta de URL**, introduzca la ruta que servirá como raíz para la página dinámica (en este ejemplo, **/blog**).</span><span class="sxs-lookup"><span data-stu-id="ba2c7-126">Under **URL path**, enter the path that will serve as the root for the dynamic page (in this example, **/blog**).</span></span> <span data-ttu-id="ba2c7-127">A continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-127">Then select **Next**.</span></span>
1. <span data-ttu-id="ba2c7-128">En el cuadro de diálogo **Seleccionar una página**, seleccione la página que ha creado para servir de página dinámica y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-128">In the **Select a page** dialog box, select the page that you created to serve as the dynamic page, and then select **Save**.</span></span>
1. <span data-ttu-id="ba2c7-129">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-129">Select **Publish**.</span></span>

### <a name="configure-the-route-to-the-dynamic-page"></a><span data-ttu-id="ba2c7-130">Configurar la ruta a la página dinámica</span><span class="sxs-lookup"><span data-stu-id="ba2c7-130">Configure the route to the dynamic page</span></span>

<span data-ttu-id="ba2c7-131">Para configurar la ruta a la página dinámica en el creador de sitios de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-131">To configure the route to the dynamic page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="ba2c7-132">Vaya a **Configuración del sitio \> Extensiones**.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-132">Go to **Site Settings \> Extensions**.</span></span>
1. <span data-ttu-id="ba2c7-133">En **Rutas de URL parametrizadas**, seleccione **Agregar** y luego introduzca la ruta de URL que introdujo al crear la URL (en este ejemplo, **/blog**).</span><span class="sxs-lookup"><span data-stu-id="ba2c7-133">Under **Parameterized URL paths**, select **Add**, and then enter the URL path that you entered when you created the URL (in this example, **/blog**).</span></span>
1. <span data-ttu-id="ba2c7-134">Seleccione **Guardar y publicar**.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-134">Select **Save and publish**.</span></span>

<span data-ttu-id="ba2c7-135">Una vez configurada la ruta, todas las solicitudes a la ruta URL parametrizada devolverán la página asociada con esa URL.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-135">After the route is configured, all requests to the parameterized URL path will return the page that is associated with that URL.</span></span> <span data-ttu-id="ba2c7-136">Si alguna solicitud contiene un segmento adicional, se devolverá la página asociada y el contenido de la página se recuperará utilizando el segmento como parámetro.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-136">If any requests contain an additional segment, the associated page will be returned, and the page content will be retrieved by using the segment as a parameter.</span></span> <span data-ttu-id="ba2c7-137">Por ejemplo,`https://fabrikam.com/blog/article-1` devolverá la página **blog\_summary** y el contenido de la página se recuperará utilizando el parámetro **/article-1**.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-137">For example, `https://fabrikam.com/blog/article-1` will return the **blog\_summary** page, and the page content will be retrieved by using the **/article-1** parameter.</span></span>

## <a name="override-a-parameterized-url-with-a-custom-page"></a><span data-ttu-id="ba2c7-138">Reemplazar una URL parametrizada con una página personalizada</span><span class="sxs-lookup"><span data-stu-id="ba2c7-138">Override a parameterized URL with a custom page</span></span>

<span data-ttu-id="ba2c7-139">Para reemplazar una URL parametrizada con una página personalizada en el creador de sitios de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-139">To override a parameterized URL with a custom page in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="ba2c7-140">Vaya a **URL** y seleccione **Nueva \> Nueva URL**.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-140">Go to **URLs**, and select **New \> New URL**.</span></span>
1. <span data-ttu-id="ba2c7-141">En el cuadro de diálogo **Crear nueva URL**, seleccione **Página interna**.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-141">In the **Create new URL** dialog box, select **Internal page**.</span></span> <span data-ttu-id="ba2c7-142">En **Ruta de URL**, introduzca la ruta que incluye el segmento a reemplazar (en este ejemplo, **/blog/about-this-blog**).</span><span class="sxs-lookup"><span data-stu-id="ba2c7-142">Under **URL path**, enter the path that includes the segment to override (in this example, **/blog/about-this-blog**).</span></span> <span data-ttu-id="ba2c7-143">A continuación, seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-143">Then select **Next**.</span></span>
1. <span data-ttu-id="ba2c7-144">En el cuadro de diálogo **Seleccionar una pagina**, seleccione la página personalizada y luego seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-144">In the **Select a page** dialog box, select the custom page, and then select **Save**.</span></span>
1. <span data-ttu-id="ba2c7-145">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-145">Select **Publish**.</span></span>
1. <span data-ttu-id="ba2c7-146">Si la página personalizada aún no se ha publicado, vaya a **Páginas**, seleccione la página personalizada y luego seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-146">If the custom page hasn't yet been published, go to **Pages**, select the custom page, and then select **Publish**.</span></span>

<span data-ttu-id="ba2c7-147">Una vez publicada la página personalizada, se publicará en lugar de la página dinámica que tiene contenido parametrizado.</span><span class="sxs-lookup"><span data-stu-id="ba2c7-147">After the custom page is published, it will be served instead of the dynamic page that has parameterized content.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ba2c7-148">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ba2c7-148">Additional resources</span></span>

[<span data-ttu-id="ba2c7-149">Modificar una página de sitio existente</span><span class="sxs-lookup"><span data-stu-id="ba2c7-149">Modify an existing site page</span></span>](modify-existing-page.md)

[<span data-ttu-id="ba2c7-150">Agregar una página de sitio nueva</span><span class="sxs-lookup"><span data-stu-id="ba2c7-150">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="ba2c7-151">Seleccionar diseños de página</span><span class="sxs-lookup"><span data-stu-id="ba2c7-151">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="ba2c7-152">Administrar metadatos de SEO</span><span class="sxs-lookup"><span data-stu-id="ba2c7-152">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="ba2c7-153">Guardar, obtener una vista previa y publicar una página</span><span class="sxs-lookup"><span data-stu-id="ba2c7-153">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="ba2c7-154">Enriquecer una página de producto</span><span class="sxs-lookup"><span data-stu-id="ba2c7-154">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="ba2c7-155">Enriquecer una página de aterrizaje de categoría</span><span class="sxs-lookup"><span data-stu-id="ba2c7-155">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="ba2c7-156">Verificar accesibilidad de contenido de página</span><span class="sxs-lookup"><span data-stu-id="ba2c7-156">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="ba2c7-157">Extensibilidad de canal en línea</span><span class="sxs-lookup"><span data-stu-id="ba2c7-157">Online channel extensibility</span></span>](e-commerce-extensibility/overview.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]