---
title: Modificar una página de sitio existente
description: En este tema se describe cómo modificar una página de sitio existente en Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/14/2020
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
ms.openlocfilehash: 87c90ed6ee62a094fe44f549c827cf9de2bf5b2f
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "3270013"
---
# <a name="modify-an-existing-site-page"></a><span data-ttu-id="d017e-103">Modificar una página de sitio existente</span><span class="sxs-lookup"><span data-stu-id="d017e-103">Modify an existing site page</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="d017e-104">En este tema se describe cómo modificar una página de sitio existente en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="d017e-104">This topic describes how to modify an existing site page in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="d017e-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="d017e-105">Overview</span></span>

<span data-ttu-id="d017e-106">Si debe modificar una página, el primer paso es abrirla en el editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="d017e-106">When you must modify a page, the first step is to open it in the page editor.</span></span> <span data-ttu-id="d017e-107">Vaya al sitio que contiene su página y, a continuación, en la lista de páginas, encuentre la página que desea.</span><span class="sxs-lookup"><span data-stu-id="d017e-107">Go to the site that contains your page, and then, in the list of pages, find the page that you want.</span></span> <span data-ttu-id="d017e-108">Si no encuentra la página, puede usar la función de búsqueda enriquecida de la herramienta de creación.</span><span class="sxs-lookup"><span data-stu-id="d017e-108">If you can't find the page, you can use the authoring tool's rich search functionality.</span></span> <span data-ttu-id="d017e-109">Escriba el nombre de página exacto o escriba las primeras letras y luego un asterisco (\*).</span><span class="sxs-lookup"><span data-stu-id="d017e-109">Either type the exact page name, or type the first few letters of it and then an asterisk (\*).</span></span> <span data-ttu-id="d017e-110">Aparece una lista filtrada de páginas.</span><span class="sxs-lookup"><span data-stu-id="d017e-110">A filtered list of pages appears.</span></span> <span data-ttu-id="d017e-111">Puede usar esta lista para encontrar la página que desea.</span><span class="sxs-lookup"><span data-stu-id="d017e-111">You can use this list to find the page that you want.</span></span> <span data-ttu-id="d017e-112">Cuando encuentre la página correcta, seleccione el nombre de la página para abrirla en el editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="d017e-112">After you find the correct page, select the page name to open the page in the page editor.</span></span>

> [!TIP]
> <span data-ttu-id="d017e-113">Si su página está visible en el inspector la página, puede seleccionar **Editar** y desproteger la página antes de abrirla en el editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="d017e-113">If your page is visible in the page inspector, you can select **Edit** and check the page out before you open it in the page editor.</span></span> <span data-ttu-id="d017e-114">De esta manera, puede desproteger varias páginas al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="d017e-114">In this way, you can check out multiple pages at the same time.</span></span>

<span data-ttu-id="d017e-115">Una vez que se abre la página en el editor de páginas, debe asegurarse de que se ha desprotegido para usted.</span><span class="sxs-lookup"><span data-stu-id="d017e-115">After the page is open in the page editor, you must make sure that it's checked out to you.</span></span> <span data-ttu-id="d017e-116">La barra de comandos de la herramienta de creación es dinámica, contextual y sensible al estado.</span><span class="sxs-lookup"><span data-stu-id="d017e-116">The command bar in the authoring tool is dynamic, context-sensitive, and state-sensitive.</span></span> <span data-ttu-id="d017e-117">Por lo tanto, solo muestra las acciones que puede realizar actualmente en la página.</span><span class="sxs-lookup"><span data-stu-id="d017e-117">Therefore, it shows only the actions that you can currently perform on the page.</span></span> <span data-ttu-id="d017e-118">Por ejemplo, si la página está desprotegida para usted, los botones **Guardar** y **Terminar edición** no aparecen en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="d017e-118">For example, if the page isn't checked out to you, the **Save** and **Finish editing** buttons don't appear on the command bar.</span></span> <span data-ttu-id="d017e-119">El estado de la página también se muestra en el lado derecho de la ventana.</span><span class="sxs-lookup"><span data-stu-id="d017e-119">The state of the page is also shown on the right side of the window.</span></span>

<span data-ttu-id="d017e-120">Si la página no está ya desprotegida para usted, seleccione **Editar** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="d017e-120">If the page isn't already checked out to you, select **Edit** on the command bar.</span></span> <span data-ttu-id="d017e-121">La barra de comandos cambia para reflejar el nuevo estado de la página.</span><span class="sxs-lookup"><span data-stu-id="d017e-121">The command bar changes to reflect the new state of the page.</span></span> <span data-ttu-id="d017e-122">También recibe una notificación que indica que la página se desprotegió para usted.</span><span class="sxs-lookup"><span data-stu-id="d017e-122">You also receive a notification that states that the page was checked out to you.</span></span>

<span data-ttu-id="d017e-123">El siguiente paso es realizar sus cambios reales.</span><span class="sxs-lookup"><span data-stu-id="d017e-123">The next step is to make your actual changes.</span></span> <span data-ttu-id="d017e-124">A menudo, usará el árbol de esquema de página de la izquierda para encontrar y seleccionar el módulo que desea cambiar y, a continuación, realizará cambios en el panel de propiedades de la derecha.</span><span class="sxs-lookup"><span data-stu-id="d017e-124">Often, you will use the page outline tree on the left to find and select the module that you want to change, and then make changes in the properties pane on the right.</span></span> 

<span data-ttu-id="d017e-125">No obstante, su cambio puede implicar a veces la adición o eliminación de modelos o fragmentos.</span><span class="sxs-lookup"><span data-stu-id="d017e-125">However, your change might sometimes involve adding or removing models or fragments.</span></span> <span data-ttu-id="d017e-126">Para agregar un fragmento o un módulo, use el árbol de esquema de página para encontrar la franja a la que desea agregar el módulo o el fragmento, y seleccione el botón de puntos suspensivos (**...**) para esa franja.</span><span class="sxs-lookup"><span data-stu-id="d017e-126">To add a fragment or module, use the page outline tree to find the slot that you want to add the module or fragment to, and then select the ellipsis button (**...**) for that slot.</span></span> <span data-ttu-id="d017e-127">Aparece un menú que incluye comandos para agregar un módulo o un fragmento.</span><span class="sxs-lookup"><span data-stu-id="d017e-127">A menu appears that includes commands for adding a module or fragment.</span></span> <span data-ttu-id="d017e-128">Para eliminar un módulo o un fragmento, encuéntrelo y selecciónelo en el árbol de esquema de la página, seleccione el botón de puntos suspensivos y el comando para eliminar el módulo o el fragmento.</span><span class="sxs-lookup"><span data-stu-id="d017e-128">To remove a module or fragment, find and select it in the page outline tree, select the ellipsis button, and then select the command to delete the module or fragment.</span></span>

> [!TIP]
> <span data-ttu-id="d017e-129">También puede ver y editar las propiedades para cualquier módulo que esté visible en la vista previa de “Lo que se ve es lo que se verá" (WYSIWYG) seleccionándolo directamente.</span><span class="sxs-lookup"><span data-stu-id="d017e-129">You can also view and edit the properties for any module that is visible in the "what you see is what you get" (WYSIWYG) preview by selecting it directly.</span></span>

<span data-ttu-id="d017e-130">Una vez que haya terminado de realizar los cambios y de obtener una vista previa del efecto, debe proteger la página seleccionando **Terminar edición** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="d017e-130">After you've finished making your changes and previewing their effect, you should check in the page by selecting **Finish editing** on the command bar.</span></span> 

<span data-ttu-id="d017e-131">Para publicar sus cambios inmediatamente, seleccione **Publicar** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="d017e-131">To publish your changes immediately, select **Publish** on the command bar.</span></span> <span data-ttu-id="d017e-132">Se publica la última versión protegida de la página que ha modificado y se vuelve disponible para los usuarios externos que ven el sitio.</span><span class="sxs-lookup"><span data-stu-id="d017e-132">The latest checked-in version of the page that you modified is published and becomes available to external users who view your site.</span></span> 

## <a name="example-change-the-video-on-the-home-page"></a><span data-ttu-id="d017e-133">Ejemplo: Cambiar el vídeo de la página principal</span><span class="sxs-lookup"><span data-stu-id="d017e-133">Example: Change the video on the home page</span></span>

<span data-ttu-id="d017e-134">El siguiente ejemplo muestra cómo modificar la página principal cambiando el vídeo que aparece en el módulo del reproductor de vídeo.</span><span class="sxs-lookup"><span data-stu-id="d017e-134">The following example shows how to modify the home page by changing the video that appears in the video player module.</span></span>

1. <span data-ttu-id="d017e-135">En **Sitios**, seleccione **Fabrikam** (o el nombre del sitio).</span><span class="sxs-lookup"><span data-stu-id="d017e-135">Under **Sites**, select **Fabrikam** (or the name of your site).</span></span>
1. <span data-ttu-id="d017e-136">En el panel de navegación de la izquierda, seleccione **Páginas**.</span><span class="sxs-lookup"><span data-stu-id="d017e-136">In the navigation pane on the left, select **Pages**.</span></span>
1. <span data-ttu-id="d017e-137">Busque y seleccione la página principal para abrirla en el editor de páginas.</span><span class="sxs-lookup"><span data-stu-id="d017e-137">Find and select the home page to open it in the page editor.</span></span>
1. <span data-ttu-id="d017e-138">En la barra de comandos, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="d017e-138">On the command bar, select **Edit**.</span></span>
1. <span data-ttu-id="d017e-139">En el esquema de página, seleccione la franja **Principal**.</span><span class="sxs-lookup"><span data-stu-id="d017e-139">In the page outline, select the **Main** slot.</span></span>
1. <span data-ttu-id="d017e-140">En la franja **Principal**, expanda todos los módulos de contenedor de fluido.</span><span class="sxs-lookup"><span data-stu-id="d017e-140">Under the **Main** slot, expand all the fluid container modules.</span></span>
1. <span data-ttu-id="d017e-141">Encuentre y seleccione el módulo de reproductor de vídeo.</span><span class="sxs-lookup"><span data-stu-id="d017e-141">Find and select the video player module.</span></span>
1. <span data-ttu-id="d017e-142">En el panel de propiedades de la derecha, seleccione la propiedad **vídeo**.</span><span class="sxs-lookup"><span data-stu-id="d017e-142">In the properties pane on the right, select the **video** property.</span></span> <span data-ttu-id="d017e-143">Aparece el selector de activos.</span><span class="sxs-lookup"><span data-stu-id="d017e-143">The asset picker appears.</span></span>
1. <span data-ttu-id="d017e-144">En el selector de activos, seleccione un activo de vídeo disponible o elija **Cargar nuevo activo** para cargar un nuevo activo de vídeo.</span><span class="sxs-lookup"><span data-stu-id="d017e-144">In the asset picker, select an available video asset, or select **Upload new asset** to upload a new video asset.</span></span>
1. <span data-ttu-id="d017e-145">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d017e-145">Select **OK**.</span></span>
1. <span data-ttu-id="d017e-146">Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.</span><span class="sxs-lookup"><span data-stu-id="d017e-146">Select **Save**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="d017e-147">En el campo **Comentarios**, especifique **Cambiar el vídeo** y, a continuación seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d017e-147">In the **Comments** field, enter **Changed the video**, and then select **OK**.</span></span>
1. <span data-ttu-id="d017e-148">Seleccione **Vista previa** para obtener una vista previa de la página actualizada.</span><span class="sxs-lookup"><span data-stu-id="d017e-148">Select **Preview** to preview the updated page.</span></span> <span data-ttu-id="d017e-149">Cuando haya terminado, cierre la pestaña de vista previa para volver a la herramienta de creación.</span><span class="sxs-lookup"><span data-stu-id="d017e-149">When you've finished, close the preview tab to return to the authoring tool.</span></span>
1. <span data-ttu-id="d017e-150">Seleccione **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="d017e-150">Select **Publish**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d017e-151">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="d017e-151">Additional resources</span></span>

[<span data-ttu-id="d017e-152">Agregar una página de sitio nueva</span><span class="sxs-lookup"><span data-stu-id="d017e-152">Add a new site page</span></span>](add-new-page.md)

[<span data-ttu-id="d017e-153">Seleccionar diseños de página</span><span class="sxs-lookup"><span data-stu-id="d017e-153">Select page layouts</span></span>](select-page-layouts.md)

[<span data-ttu-id="d017e-154">Administrar metadatos de SEO</span><span class="sxs-lookup"><span data-stu-id="d017e-154">Manage SEO metadata</span></span>](manage-seo-metadata.md)

[<span data-ttu-id="d017e-155">Guardar, obtener una vista previa y publicar una página</span><span class="sxs-lookup"><span data-stu-id="d017e-155">Save, preview, and publish a page</span></span>](save-preview-publish-page.md)

[<span data-ttu-id="d017e-156">Enriquecer una página de producto</span><span class="sxs-lookup"><span data-stu-id="d017e-156">Enrich a product page</span></span>](enrich-product-page.md)

[<span data-ttu-id="d017e-157">Enriquecer una página de aterrizaje de categoría</span><span class="sxs-lookup"><span data-stu-id="d017e-157">Enrich a category landing page</span></span>](enrich-category-page.md)

[<span data-ttu-id="d017e-158">Verificar accesibilidad de contenido de página</span><span class="sxs-lookup"><span data-stu-id="d017e-158">Verify page content accessibility</span></span>](verify-accessibility.md)
