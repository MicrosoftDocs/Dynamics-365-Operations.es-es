---
title: Modificar una página de sitio existente
description: En este tema se describe cómo modificar una página de sitio existente en Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: b633965e45c16cb4e5991fab67783b867223f6ec
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803738"
---
# <a name="modify-an-existing-site-page"></a><span data-ttu-id="fb63f-103">Modificar una página de sitio existente</span><span class="sxs-lookup"><span data-stu-id="fb63f-103">Modify an existing site page</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="fb63f-104">En este tema se describe cómo modificar una página de sitio existente en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="fb63f-104">This topic describes how to modify an existing site page in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="fb63f-105">Si debe modificar una página, el primer paso es abrirla en el editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="fb63f-105">When you must modify a page, the first step is to open it in the page editor.</span></span> <span data-ttu-id="fb63f-106">Vaya al sitio que contiene su página y, a continuación, en la lista de páginas, encuentre la página que desea.</span><span class="sxs-lookup"><span data-stu-id="fb63f-106">Go to the site that contains your page, and then, in the list of pages, find the page that you want.</span></span> <span data-ttu-id="fb63f-107">Si no encuentra la página, puede usar la función de búsqueda enriquecida de la herramienta de creación.</span><span class="sxs-lookup"><span data-stu-id="fb63f-107">If you can't find the page, you can use the authoring tool's rich search functionality.</span></span> <span data-ttu-id="fb63f-108">Escriba el nombre de página exacto o escriba las primeras letras y luego un asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="fb63f-108">Either type the exact page name, or type the first few letters of it and then an asterisk (\*).</span></span> <span data-ttu-id="fb63f-109">Aparece una lista filtrada de páginas.</span><span class="sxs-lookup"><span data-stu-id="fb63f-109">A filtered list of pages appears.</span></span> <span data-ttu-id="fb63f-110">Puede usar esta lista para encontrar la página que desea.</span><span class="sxs-lookup"><span data-stu-id="fb63f-110">You can use this list to find the page that you want.</span></span> <span data-ttu-id="fb63f-111">Cuando encuentre la página correcta, seleccione el nombre de la página para abrirla en el editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="fb63f-111">After you find the correct page, select the page name to open the page in the page editor.</span></span>

> [!TIP]
> <span data-ttu-id="fb63f-112">Si su página está visible en el inspector la página, puede seleccionar **Editar** y desproteger la página antes de abrirla en el editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="fb63f-112">If your page is visible in the page inspector, you can select **Edit** and check the page out before you open it in the page editor.</span></span> <span data-ttu-id="fb63f-113">De esta manera, puede desproteger varias páginas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="fb63f-113">In this way, you can check out multiple pages at the same time.</span></span>

<span data-ttu-id="fb63f-114">Una vez que se abre la página en el editor de páginas, debe asegurarse de que se ha desprotegido para usted.</span><span class="sxs-lookup"><span data-stu-id="fb63f-114">After the page is open in the page editor, you must make sure that it's checked out to you.</span></span> <span data-ttu-id="fb63f-115">La barra de comandos de la herramienta de creación es dinámica, contextual y sensible al estado.</span><span class="sxs-lookup"><span data-stu-id="fb63f-115">The command bar in the authoring tool is dynamic, context-sensitive, and state-sensitive.</span></span> <span data-ttu-id="fb63f-116">Por lo tanto, solo muestra las acciones que puede realizar actualmente en la página.</span><span class="sxs-lookup"><span data-stu-id="fb63f-116">Therefore, it shows only the actions that you can currently perform on the page.</span></span> <span data-ttu-id="fb63f-117">Por ejemplo, si la página está desprotegida para usted, los botones **Guardar** y **Terminar edición** no aparecen en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="fb63f-117">For example, if the page isn't checked out to you, the **Save** and **Finish editing** buttons don't appear on the command bar.</span></span> <span data-ttu-id="fb63f-118">El estado de la página también se muestra en el lado derecho de la ventana.</span><span class="sxs-lookup"><span data-stu-id="fb63f-118">The state of the page is also shown on the right side of the window.</span></span>

<span data-ttu-id="fb63f-119">Si la página no está ya desprotegida para usted, seleccione **Editar** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="fb63f-119">If the page isn't already checked out to you, select **Edit** on the command bar.</span></span> <span data-ttu-id="fb63f-120">La barra de comandos cambia para reflejar el nuevo estado de la página.</span><span class="sxs-lookup"><span data-stu-id="fb63f-120">The command bar changes to reflect the new state of the page.</span></span> <span data-ttu-id="fb63f-121">También recibe una notificación que indica que la página se desprotegió para usted.</span><span class="sxs-lookup"><span data-stu-id="fb63f-121">You also receive a notification that states that the page was checked out to you.</span></span>

<span data-ttu-id="fb63f-122">El siguiente paso es realizar sus cambios reales.</span><span class="sxs-lookup"><span data-stu-id="fb63f-122">The next step is to make your actual changes.</span></span> <span data-ttu-id="fb63f-123">A menudo, usará el árbol de esquema de página de la izquierda para encontrar y seleccionar el módulo que desea cambiar y, a continuación, realizará cambios en el panel de propiedades de la derecha.</span><span class="sxs-lookup"><span data-stu-id="fb63f-123">Often, you will use the page outline tree on the left to find and select the module that you want to change, and then make changes in the properties pane on the right.</span></span> 

<span data-ttu-id="fb63f-124">No obstante, su cambio puede implicar a veces la adición o eliminación de modelos o fragmentos.</span><span class="sxs-lookup"><span data-stu-id="fb63f-124">However, your change might sometimes involve adding or removing models or fragments.</span></span> <span data-ttu-id="fb63f-125">Para agregar un fragmento o un módulo, use el árbol de esquema de página para encontrar la franja a la que desea agregar el módulo o el fragmento, y seleccione el botón de puntos suspensivos (**...**) para esa franja.</span><span class="sxs-lookup"><span data-stu-id="fb63f-125">To add a fragment or module, use the page outline tree to find the slot that you want to add the module or fragment to, and then select the ellipsis button (**...**) for that slot.</span></span> <span data-ttu-id="fb63f-126">Aparece un menú que incluye comandos para agregar un módulo o un fragmento.</span><span class="sxs-lookup"><span data-stu-id="fb63f-126">A menu appears that includes commands for adding a module or fragment.</span></span> <span data-ttu-id="fb63f-127">Para eliminar un módulo o un fragmento, encuéntrelo y selecciónelo en el árbol de esquema de la página, seleccione el botón de puntos suspensivos y el comando para eliminar el módulo o el fragmento.</span><span class="sxs-lookup"><span data-stu-id="fb63f-127">To remove a module or fragment, find and select it in the page outline tree, select the ellipsis button, and then select the command to delete the module or fragment.</span></span>

> [!TIP]
> <span data-ttu-id="fb63f-128">También puede ver y editar las propiedades para cualquier módulo que esté visible en la vista previa del generador de páginas visual seleccionándolo directamente.</span><span class="sxs-lookup"><span data-stu-id="fb63f-128">You can also view and edit the properties for any module that is visible in the visual page builder preview by selecting it directly.</span></span>

<span data-ttu-id="fb63f-129">Una vez que haya terminado de realizar los cambios y de obtener una vista previa del efecto, debe proteger la página seleccionando **Terminar edición** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="fb63f-129">After you've finished making your changes and previewing their effect, you should check in the page by selecting **Finish editing** on the command bar.</span></span> 

<span data-ttu-id="fb63f-130">Para publicar sus cambios inmediatamente, seleccione **Publicar** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="fb63f-130">To publish your changes immediately, select **Publish** on the command bar.</span></span> <span data-ttu-id="fb63f-131">Se publica la última versión protegida de la página que ha modificado y se vuelve disponible para los usuarios externos que ven el sitio.</span><span class="sxs-lookup"><span data-stu-id="fb63f-131">The latest checked-in version of the page that you modified is published and becomes available to external users who view your site.</span></span> 

## <a name="example-change-the-video-on-the-home-page"></a><span data-ttu-id="fb63f-132">Ejemplo: Cambiar el vídeo de la página principal</span><span class="sxs-lookup"><span data-stu-id="fb63f-132">Example: Change the video on the home page</span></span>

<span data-ttu-id="fb63f-133">El siguiente ejemplo muestra cómo modificar la página principal cambiando el vídeo que aparece en el módulo del reproductor de vídeo.</span><span class="sxs-lookup"><span data-stu-id="fb63f-133">The following example shows how to modify the home page by changing the video that appears in the video player module.</span></span>

1. <span data-ttu-id="fb63f-134">En **Sitios**, seleccione **Fabrikam** (o el nombre del sitio).</span><span class="sxs-lookup"><span data-stu-id="fb63f-134">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="fb63f-135">En el panel de navegación de la izquierda, seleccione **Páginas**.</span><span class="sxs-lookup"><span data-stu-id="fb63f-135">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="fb63f-136">Busque y seleccione la página principal para abrirla en el editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="fb63f-136">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="fb63f-137">En la barra de comandos, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="fb63f-137">On the command bar, select **Edit**.</span></span>
1. <span data-ttu-id="fb63f-138">En el esquema de página, seleccione la franja **Principal**.</span><span class="sxs-lookup"><span data-stu-id="fb63f-138">In the page outline, select the **Main** slot.</span></span>
1. <span data-ttu-id="fb63f-139">En la franja **Principal**, expanda todos los módulos de contenedor de fluido.</span><span class="sxs-lookup"><span data-stu-id="fb63f-139">Under the **Main** slot, expand all the fluid container modules.</span></span>
1. <span data-ttu-id="fb63f-140">Encuentre y seleccione el módulo de reproductor de vídeo.</span><span class="sxs-lookup"><span data-stu-id="fb63f-140">Find and select the video player module.</span></span>
1. <span data-ttu-id="fb63f-141">En el panel de propiedades de la derecha, seleccione la propiedad **vídeo**.</span><span class="sxs-lookup"><span data-stu-id="fb63f-141">In the properties pane on the right, select the **video** property.</span></span> <span data-ttu-id="fb63f-142">Aparece el selector de activos.</span><span class="sxs-lookup"><span data-stu-id="fb63f-142">The asset picker appears.</span></span>
1. <span data-ttu-id="fb63f-143">En el selector de activos, seleccione un activo de vídeo disponible o elija **Cargar nuevo activo** para cargar un nuevo activo de vídeo.</span><span class="sxs-lookup"><span data-stu-id="fb63f-143">In the asset picker, select an available video asset, or select **Upload new asset** to upload a new video asset.</span></span>
1. <span data-ttu-id="fb63f-144">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fb63f-144">Select **OK**.</span></span>
1. <span data-ttu-id="fb63f-145">Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="fb63f-145">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="fb63f-146">En el campo **Comentarios**, especifique **Cambiar el vídeo** y, a continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fb63f-146">In the **Comments** field, enter **Changed the video**, and then select **OK**.</span></span>
1. <span data-ttu-id="fb63f-147">Seleccione **Vista previa** para obtener una vista previa de la página actualizada.</span><span class="sxs-lookup"><span data-stu-id="fb63f-147">Select **Preview** to preview the updated page.</span></span> <span data-ttu-id="fb63f-148">Cuando haya terminado, cierre la pestaña de vista previa para volver a la herramienta de creación.</span><span class="sxs-lookup"><span data-stu-id="fb63f-148">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="fb63f-149">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="fb63f-149">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="fb63f-150">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="fb63f-150">Additional resources</span></span>

[<span data-ttu-id="fb63f-151">Agregar una página de sitio nueva</span><span class="sxs-lookup"><span data-stu-id="fb63f-151">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="fb63f-152">Seleccionar diseños de página</span><span class="sxs-lookup"><span data-stu-id="fb63f-152">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="fb63f-153">Administrar metadatos de SEO</span><span class="sxs-lookup"><span data-stu-id="fb63f-153">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="fb63f-154">Guardar, obtener una vista previa y publicar una página</span><span class="sxs-lookup"><span data-stu-id="fb63f-154">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="fb63f-155">Enriquecer una página de producto</span><span class="sxs-lookup"><span data-stu-id="fb63f-155">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="fb63f-156">Enriquecer una página de aterrizaje de categoría</span><span class="sxs-lookup"><span data-stu-id="fb63f-156">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="fb63f-157">Verificar accesibilidad de contenido de página</span><span class="sxs-lookup"><span data-stu-id="fb63f-157">Verify page content accessibility</span></span>](verify-accessibility.md)

[<span data-ttu-id="fb63f-158">Crear páginas de comercio electrónico dinámicas basadas en parámetros de URL</span><span class="sxs-lookup"><span data-stu-id="fb63f-158">Create dynamic e-commerce pages based on URL parameters</span></span>](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
