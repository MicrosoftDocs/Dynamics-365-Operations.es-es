---
title: Crear un URL de página
description: En este tema se tratan los conceptos básicos y los procedimientos para crear una dirección URL de página en el sitio.
author: bicyclingfool
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
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: ab7325dd4060392ed43e59c1ad48069d294d81c0
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697557"
---
# <a name="create-a-page-url"></a><span data-ttu-id="6f1dd-103">Crear un URL de página</span><span class="sxs-lookup"><span data-stu-id="6f1dd-103">Create a page URL</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="6f1dd-104">En este tema se tratan los conceptos básicos y los procedimientos para crear una dirección URL de página en el sitio.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-104">This topic covers the basic concepts and procedures for creating a page URL on your site.</span></span>

## <a name="overview"></a><span data-ttu-id="6f1dd-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="6f1dd-105">Overview</span></span>

<span data-ttu-id="6f1dd-106">La dirección URL completa, o absoluta, que apunta a una página en el sitio consta de distintas partes.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-106">The full, or absolute, URL that points to a page on your site consists of distinct parts.</span></span> <span data-ttu-id="6f1dd-107">Por ejemplo, la dirección URL `https://www.contoso.com/en-us/contactus` tiene las siguientes partes:</span><span class="sxs-lookup"><span data-stu-id="6f1dd-107">For example, the URL `https://www.contoso.com/en-us/contactus` has the following parts:</span></span>

- <span data-ttu-id="6f1dd-108">`https://www.contoso.com`: el protocolo HTTP y el dominio del sitio.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-108">`https://www.contoso.com` – The HTTP protocol and the site's domain.</span></span>
- <span data-ttu-id="6f1dd-109">`/en-us`: la ruta de acceso del idioma del sitio.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-109">`/en-us` – The site's language path.</span></span>
- <span data-ttu-id="6f1dd-110">`/contactus`: la dirección URL relativa para la página **Ponerse en contacto con nosotros**.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-110">`/contactus` – The relative URL for the **Contact Us** page.</span></span> <span data-ttu-id="6f1dd-111">Una dirección URL relativa también se conoce como *slug* de URL.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-111">A relative URL is also known as a URL *slug*.</span></span>

<span data-ttu-id="6f1dd-112">Establezca el dominio del sitio y la ruta de acceso de idioma opcional al configurar el sitio.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-112">You establish your site's domain and optional language path when you set up the site.</span></span> <span data-ttu-id="6f1dd-113">Puede agregar más dominios y rutas de acceso de idioma al sitio a través de la página de tiendas en línea en la configuración del sitio.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-113">You can add more domains and language paths to your site through the online stores page in the site's settings.</span></span>

<span data-ttu-id="6f1dd-114">El slug de URL para una página existe como entidad independiente en el entorno de creación del sitio.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-114">The URL slug for a page exists as a standalone entity in the site authoring environment.</span></span> <span data-ttu-id="6f1dd-115">Una dirección URL de página consta de dos partes: un nombre que representa el slug de URL, y un puntero a una página en el sitio o un sitio externo.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-115">A page URL consists of two parts: a name that represents the URL slug, and a pointer to a page on either your site or an external site.</span></span> <span data-ttu-id="6f1dd-116">Una dirección URL de página también se puede configurar para actuar como una redirección en su sitio o un sitio externo.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-116">A page URL can also be configured to act as a redirect to another page on either your site or an external site.</span></span>

## <a name="create-a-page-url"></a><span data-ttu-id="6f1dd-117">Crear un URL de página</span><span class="sxs-lookup"><span data-stu-id="6f1dd-117">Create a page URL</span></span>

<span data-ttu-id="6f1dd-118">Hay dos maneras de crear direcciones URL de página:</span><span class="sxs-lookup"><span data-stu-id="6f1dd-118">There are two ways to create page URLs:</span></span>

- <span data-ttu-id="6f1dd-119">Automáticamente, al crear una página</span><span class="sxs-lookup"><span data-stu-id="6f1dd-119">Automatically, when you create a page</span></span>
- <span data-ttu-id="6f1dd-120">Manualmente, desde la página **Direcciones URL**</span><span class="sxs-lookup"><span data-stu-id="6f1dd-120">Manually, from the **URLs** page</span></span>

### <a name="create-a-page-url-when-you-create-a-page"></a><span data-ttu-id="6f1dd-121">Crear una dirección URL de página al crear una página</span><span class="sxs-lookup"><span data-stu-id="6f1dd-121">Create a page URL when you create a page</span></span>

<span data-ttu-id="6f1dd-122">Si proporciona un nombre en el campo **Dirección URL** al crear una nueva página, se crea automáticamente una dirección URL que apunta a esa página en la página **Direcciones URL**.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-122">If you provide a name in the **URL** field when you create a new page, a page URL that points to that page is automatically created on the **URLs** page.</span></span> <span data-ttu-id="6f1dd-123">Tras publicar la dirección URL y la página a la que apunta, los usuarios del sitio (sus clientes) pueden tener acceso a la página que está asociada a la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-123">After you publish the URL and the page that it points to, site users (your customers) can access the page that is associated with the URL.</span></span>

> [!NOTE]
> <span data-ttu-id="6f1dd-124">Si publica una dirección URL sin publicar la página a la que apunta, los usuarios del sitio reciben un error 404 al intentar tener acceso a la página.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-124">If you publish a URL without publishing the page that it points to, site users receive a 404 error when they try to access the page.</span></span> <span data-ttu-id="6f1dd-125">Si publica una página sin publicar la dirección URL a la que apunta, no se podrá tener acceso a la página con una dirección URL.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-125">If you publish a page without publishing the URL that points to it, the page can't be accessed by using a URL.</span></span>

### <a name="manually-create-a-page-url"></a><span data-ttu-id="6f1dd-126">Crear manualmente una URL de página</span><span class="sxs-lookup"><span data-stu-id="6f1dd-126">Manually create a page URL</span></span>

<span data-ttu-id="6f1dd-127">Al crear páginas nuevas, no es necesario especificar una dirección URL de página.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-127">When you create new pages, you aren't required to specify a page URL.</span></span> <span data-ttu-id="6f1dd-128">Si dejas en blanco el campo de la dirección URL, la página se crea en un estado desvinculado.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-128">If you leave the URL field blank, the page is created in an unlinked state.</span></span> <span data-ttu-id="6f1dd-129">En este caso, los clientes no podrán tener acceso a la página, aunque se publique.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-129">In this case, customers won't be able to access the page, even if it's published.</span></span> <span data-ttu-id="6f1dd-130">Para que la página sea accesible, debe crear manualmente la dirección URL y vincularla a la página.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-130">To make the page accessible, you must manually create the URL and link it to the page.</span></span>

<span data-ttu-id="6f1dd-131">Para crear manualmente la dirección URL de página para una página, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-131">To manually create the page URL for a page, follow these steps.</span></span>

1. <span data-ttu-id="6f1dd-132">En la página **Direcciones URL**, seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-132">On the **URLs** page, select **New**.</span></span>
1. <span data-ttu-id="6f1dd-133">Seleccione la página del sitio a la que desea asociar la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-133">Select the site page to associate with the URL.</span></span>
1. <span data-ttu-id="6f1dd-134">Especifique el slug de URL y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-134">Enter the URL slug, and then select **OK**.</span></span>

<span data-ttu-id="6f1dd-135">En este punto, la dirección URL se encuentra en un estado de borrador.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-135">At this point, the URL is in a draft state.</span></span> <span data-ttu-id="6f1dd-136">Debe estar publicada antes de que los usuarios del sitio puedan tener acceso a la página asociada.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-136">It must be published before site users can access the associated page.</span></span>

## <a name="update-a-page-url"></a><span data-ttu-id="6f1dd-137">Actualizar una URL de página</span><span class="sxs-lookup"><span data-stu-id="6f1dd-137">Update a page URL</span></span>

<span data-ttu-id="6f1dd-138">Para actualizar la página de destino de una dirección URL de página, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-138">To update the target page of a page URL, follow these steps.</span></span>

1. <span data-ttu-id="6f1dd-139">En la página **Direcciones URL**, seleccione la URL que se actualizará.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-139">On the **URLs** page, select the URL to update.</span></span>
1. <span data-ttu-id="6f1dd-140">En el panel de propiedades de la derecha, seleccione los puntos suspensivos (**...**) situados junto al campo de página de destino.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-140">In the property pane on the right, select the ellipsis button (**...**) next to the target page field.</span></span>
1. <span data-ttu-id="6f1dd-141">En el cuadro de diálogo, seleccione una página diferente y **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-141">In the dialog box, select a different page, and then select **OK**.</span></span>
1. <span data-ttu-id="6f1dd-142">Guarde y publique la URL.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-142">Save and publish the URL.</span></span>

## <a name="redirect-a-page-url"></a><span data-ttu-id="6f1dd-143">Redireccionar una URL de página</span><span class="sxs-lookup"><span data-stu-id="6f1dd-143">Redirect a page URL</span></span>

<span data-ttu-id="6f1dd-144">A veces, es posible que desee que los clientes ver una página diferente al solicitar una dirección URL específica.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-144">Sometimes, you might want your customers to view a different page when they request a specific URL.</span></span> <span data-ttu-id="6f1dd-145">En estos casos, el mejor enfoque, y el más sencillo, es a menudo cambiar la página a la que apunta la dirección URL de página.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-145">In these cases, the best and easiest approach is often to change the page that the page URL points to.</span></span> <span data-ttu-id="6f1dd-146">Sin embargo, puede que tenga motivos legítimos para usar redirecciones HTTP 301 o 3023 para redirigir las solicitudes para una dirección URL a otra dirección URL.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-146">However, you might have legitimate reasons for using HTTP 301 or 3023 redirects to redirect requests for a URL to a different URL.</span></span>

<span data-ttu-id="6f1dd-147">Para redirigir una dirección URL a otra dirección URL, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-147">To redirect a URL to a different URL, follow these steps.</span></span>

1. <span data-ttu-id="6f1dd-148">En la página **Direcciones URL**, seleccione la URL que se actualizará.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-148">On the **URLs** page, select the URL to update.</span></span>
1. <span data-ttu-id="6f1dd-149">En el panel de propiedades de la derecha, seleccione **Redirigir**.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-149">In the property pane on the right, select **Redirect**.</span></span>
1. <span data-ttu-id="6f1dd-150">Seleccione un destino para la redirección.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-150">Select a destination for the redirect:</span></span>

    - <span data-ttu-id="6f1dd-151">Para apuntar a otra página del sitio, seleccione **Dirección URL interna**, seleccione los puntos suspensivos (**...**) y, a continuación, la URL a la que redirigir.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-151">To point to another page on your site, select **Internal URL**, select the ellipsis button (**...**), and then select the URL to redirect to.</span></span>
    - <span data-ttu-id="6f1dd-152">Para apuntar a una página de un sitio externo, seleccione **Dirección URL externa** y, a continuación, indique la URL completa de esa página.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-152">To point to a page on an external site, select **External URL**, and then enter the full URL for that page.</span></span> <span data-ttu-id="6f1dd-153">Asegúrese de incluir el protocolo.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-153">Be sure to include the protocol.</span></span> <span data-ttu-id="6f1dd-154">Por ejemplo, escriba `https://domain.com/new/page`.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-154">For example, enter `https://domain.com/new/page`.</span></span> <span data-ttu-id="6f1dd-155">Si la dirección URL redirige a una dirección URL interna, debe seleccionar **Borrar selección** para poder especificar una dirección URL externa.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-155">If the URL already redirects to an internal URL, you must select **Clear selection** before you can enter an external URL.</span></span>

1. <span data-ttu-id="6f1dd-156">Seleccione un tipo de redirección:</span><span class="sxs-lookup"><span data-stu-id="6f1dd-156">Select a redirect type:</span></span>

    - <span data-ttu-id="6f1dd-157">**Redirección permanente (301)**: seleccione esta opción cuando sepa que su contenido se está moviendo permanentemente y que no revertirá a su dirección URL anterior.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-157">**Permanent redirect (301)** – Select this option when you know that your content is moving permanently and won't revert to its previous URL.</span></span> <span data-ttu-id="6f1dd-158">Los motores de búsqueda asignarán el valor de la optimización de motor de búsqueda (SEO) de la dirección URL de redireccionamiento a la dirección URL a la que se está redirigiendo y actualizará su registro para mostrar la nueva dirección URL.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-158">Search engines will assign the search engine optimization (SEO) value of the redirecting URL to the URL that is being redirected to and update their record to show the new URL.</span></span> 
    - <span data-ttu-id="6f1dd-159">**Redirección temporal (302)**: seleccione esta opción para redirigir tráfico sin actualizar motores de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-159">**Temporary redirect (302)** – Select this option to redirect traffic without updating search engines.</span></span> <span data-ttu-id="6f1dd-160">Este enfoque se suele usar si el contenido se revertirá pronto a su dirección URL anterior.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-160">This approach is typically used if the content will soon revert to its previous URL.</span></span>

1. <span data-ttu-id="6f1dd-161">Cuando esté listo para implementar la redirección, guarde y publique la dirección URL.</span><span class="sxs-lookup"><span data-stu-id="6f1dd-161">When you're ready to implement the redirect, save and publish the URL.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6f1dd-162">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="6f1dd-162">Additional resources</span></span>

[<span data-ttu-id="6f1dd-163">Personalizar navegación del sitio</span><span class="sxs-lookup"><span data-stu-id="6f1dd-163">Customize site navigation</span></span>](customize-site-navigation.md)

[<span data-ttu-id="6f1dd-164">Agregar una página de sitio nueva</span><span class="sxs-lookup"><span data-stu-id="6f1dd-164">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="6f1dd-165">Configurar su nombre de dominio</span><span class="sxs-lookup"><span data-stu-id="6f1dd-165">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="6f1dd-166">Agregar idiomas al sitio</span><span class="sxs-lookup"><span data-stu-id="6f1dd-166">Add languages to your site</span></span>](add-languages-to-site.md)
