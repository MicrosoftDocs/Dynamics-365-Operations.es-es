---
title: Agregar un icono de favoritos
description: En este tema se explica cómo agregar un icono de favoritos al sitio.
author: bicyclingfool
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 9268bc74a4131256f5a2e88df833104db271b56a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5797728"
---
# <a name="add-a-favicon"></a><span data-ttu-id="2e0e1-103">Agregar un icono favorito</span><span class="sxs-lookup"><span data-stu-id="2e0e1-103">Add a favicon</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2e0e1-104">En este tema se explica cómo agregar un icono de favoritos al sitio.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-104">This topic explains how to add a favicon to your site.</span></span>

<span data-ttu-id="2e0e1-105">Un icono de favoritos es un pequeño archivo gráfico que se muestra en una pestaña del explorador web, en la barra de direcciones, en el historial de exploración, y en marcadores o favoritos, entre otros lugares.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-105">A favicon is a small graphics file that is shown on a web browser tab, in the Address bar, in the browsing history, and in bookmarks or favorites, among other places.</span></span> <span data-ttu-id="2e0e1-106">Recomendamos que agregue un icono de favoritos al sitio, ya que representa y refuerza su marca, y ayuda a diferenciar el sitio de otros que los clientes visitan.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-106">We recommend that you add a favicon to your site, because it represents and reinforces your brand, and helps distinguish your site from other sites that your customers visit.</span></span>

<span data-ttu-id="2e0e1-107">Aunque puede agregar varios iconos favoritos de diversos tamaños y tipos de archivos al sitio, este tema muestra cómo agregar un icono favorito único.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-107">Although you can add multiple favicons of various sizes and file types to your site, this topic shows how to add a single favicon.</span></span> <span data-ttu-id="2e0e1-108">Sin embargo, se utilizan el mismo proceso y ubicación para agregar más iconos favoritos.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-108">However, the same process and location are used to add more favicons.</span></span>

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a><span data-ttu-id="2e0e1-109">Cargue un icono favorito en la colección de activos del sitio</span><span class="sxs-lookup"><span data-stu-id="2e0e1-109">Upload a favicon to your site's asset collection</span></span>

<span data-ttu-id="2e0e1-110">Para cargar un icono favorito en la colección de activos del sitio, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-110">To upload a favicon to your site's asset collection, follow these steps.</span></span>

1. <span data-ttu-id="2e0e1-111">En el panel de navegación izquierdo, seleccione **Biblioteca multimedia**.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-111">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="2e0e1-112">En la barra de comandos, seleccione **Subir \> Subir elementos multimedia**.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-112">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="2e0e1-113">En la ventana del Explorador de archivos, busque el archivo de imagen de icono favorito que desea cargar, selecciónelo y luego seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-113">In the File Explorer window, browse to the favicon image file that you want to upload, select it, and then select **Open**.</span></span>
1. <span data-ttu-id="2e0e1-114">En el cuadro de diálogo **Subir elemento multimedia**, introduzca el título requerido y el texto alternativo.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-114">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="2e0e1-115">Si quiere publicar la imagen inmediatamente después de la carga, seleccione la casilla de verificación **Publicar elementos multimedia después de subir**.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-115">If you want to publish the image immediately after upload, select the **Publish media items after upload** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2e0e1-116">Si no selecciona la casilla **Publicar elementos multimedia tras la carga**, debe volver a la página **Elementos multimedia** y publicar manualmente el icono favorito posteriormente.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-116">If you don't select the **Publish media items after upload** check box, you must return to **Media items** page and manually publish the favicon later.</span></span>

1. <span data-ttu-id="2e0e1-117">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-117">Select **OK**.</span></span>
1. <span data-ttu-id="2e0e1-118">En el panel de propiedades de la derecha, copie la dirección URL pública del icono favorito.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-118">In the property pane on the right, copy the public URL of the favicon.</span></span> <span data-ttu-id="2e0e1-119">Usará esta URL más tarde.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-119">You will use this URL later.</span></span>

## <a name="create-the-html-for-your-favicon"></a><span data-ttu-id="2e0e1-120">Crear el HTML para el icono favorito</span><span class="sxs-lookup"><span data-stu-id="2e0e1-120">Create the HTML for your favicon</span></span>

<span data-ttu-id="2e0e1-121">Para crear el HTML para el icono favorito, use el siguiente código HTML.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-121">To create the HTML for the favicon, use the following HTML string.</span></span> <span data-ttu-id="2e0e1-122">Para el atributo **href**, reemplace **"URL\_pública\_para\_su\_icono favorito"** por la dirección URL pública que ha copiado antes.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-122">For the **href** attribute, replace **Public\_URL\_for\_your\_favicon** with the public URL that you copied earlier.</span></span>

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="create-a-fragment-that-contains-a-metatag-for-your-favicon"></a><span data-ttu-id="2e0e1-123">Crear un fragmento que contenga una metaetiqueta para el favicon</span><span class="sxs-lookup"><span data-stu-id="2e0e1-123">Create a fragment that contains a metatag for your favicon</span></span>

<span data-ttu-id="2e0e1-124">Para crear un fragmento que contenga una metaetiqueta para el icono favorito, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-124">To create a fragment that contains a metatag for your favicon, follow these steps.</span></span>

1. <span data-ttu-id="2e0e1-125">Vaya a **Fragmentos** y después **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-125">Go to **Fragments**, and select **New**.</span></span>
1. <span data-ttu-id="2e0e1-126">En el cuadro de diálogo **Nuevo fragmento**, seleccione **Metaetiquetas** como módulo en el que se basa el fragmento.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-126">In the **New fragment** dialog box, select **Metatags** as the module that the fragment is based on.</span></span>
1. <span data-ttu-id="2e0e1-127">Especifique un nombre para el fragmento y después seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-127">Enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="2e0e1-128">En el árbol de jerarquía de fragmentos, seleccione el elemento secundario **Metaetiquetas predeterminadas**.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-128">In the fragment hierarchy tree, select the **Default metatags** child.</span></span>
1. <span data-ttu-id="2e0e1-129">En el panel derecho, en **Metaetiquetas**, seleccione **Añadir** y luego introduzca la cadena HTML que creó anteriormente para el icono favorito.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-129">In the right pane, under **Meta Tags**, select **Add**, and then enter the HTML string that you created earlier for the favicon.</span></span> 
1. <span data-ttu-id="2e0e1-130">Seleccione **Finalizar edición** y luego seleccione **Publicar** para publicar el fragmento.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-130">Select **Finish editing**, and then select **Publish** to publish the fragment.</span></span>

## <a name="add-the-metatag-fragment-to-the-html-head-section-of-your-pages"></a><span data-ttu-id="2e0e1-131">Agregar el fragmento de metaetiqueta a la sección de encabezado HTML de las páginas</span><span class="sxs-lookup"><span data-stu-id="2e0e1-131">Add the metatag fragment to the HTML head section of your pages</span></span>

<span data-ttu-id="2e0e1-132">Para agregar el fragmento de metaetiqueta a la sección **encabezado** de las páginas, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-132">To add the metatag fragment to the HTML **head** section of your pages, follow these steps.</span></span>

1. <span data-ttu-id="2e0e1-133">Vaya a **Plantillas**, abra la plantilla para las páginas en las que desea agregar el icono favorito y luego seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-133">Go to **Templates**, open the template for the pages that you want to add your favicon to, and then select **Edit**.</span></span>
1. <span data-ttu-id="2e0e1-134">En el árbol de jerarquía de plantilla, seleccione el botón de puntos suspensivos (**...**) a la derecha del contenedor **Cabeza HTML** y luego seleccione **Añadir fragmento**.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-134">In the template hierarchy tree, select the ellipsis (**...**) button to the right of the **HTML head** container, and then select **Add fragment**.</span></span>
1. <span data-ttu-id="2e0e1-135">En el cuadro de diálogo **Seleccionar fragmento**, seleccione el fragmento de metaetiqueta creado anteriormente y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-135">In the **Select fragment** dialog box, select the metatag fragment that you created earlier, and then select **OK**.</span></span>
1. <span data-ttu-id="2e0e1-136">Seleccione **Finalizar edición** y luego seleccione **Publicar** para publicar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-136">Select **Finish editing**, and then select **Publish** to publish the template.</span></span>

> [!NOTE]
> <span data-ttu-id="2e0e1-137">Si su sitio utiliza más de una plantilla, debe agregar el fragmento de metaetiquetas a todas ellas.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-137">If your site uses more than one template, you must add the metatags fragment to all of them.</span></span>

<span data-ttu-id="2e0e1-138">Cuando obtenga una vista previa de las páginas que se basan en la plantilla a la que agregó el fragmento de metaetiquetas, ahora debería ver el icono favorito en la pestaña del navegador.</span><span class="sxs-lookup"><span data-stu-id="2e0e1-138">When you preview pages that are based on the template that you added the metatags fragment to, you should now see the favicon on the browser tab.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2e0e1-139">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2e0e1-139">Additional resources</span></span>

[<span data-ttu-id="2e0e1-140">Agregar un logotipo</span><span class="sxs-lookup"><span data-stu-id="2e0e1-140">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="2e0e1-141">Seleccionar un tema de sitio</span><span class="sxs-lookup"><span data-stu-id="2e0e1-141">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="2e0e1-142">Trabajar con archivos de invalidaciones CSS</span><span class="sxs-lookup"><span data-stu-id="2e0e1-142">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="2e0e1-143">Agregar un mensaje de bienvenida</span><span class="sxs-lookup"><span data-stu-id="2e0e1-143">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="2e0e1-144">Agregar un aviso de derechos de autor</span><span class="sxs-lookup"><span data-stu-id="2e0e1-144">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="2e0e1-145">Agregar idiomas al sitio</span><span class="sxs-lookup"><span data-stu-id="2e0e1-145">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="2e0e1-146">Agregar secuencia de comandos a páginas del sitio para admitir telemetría</span><span class="sxs-lookup"><span data-stu-id="2e0e1-146">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
