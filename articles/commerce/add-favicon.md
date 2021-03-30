---
title: Agregar un icono de favoritos
description: En este tema se explica cómo agregar un icono de favoritos al sitio.
author: bicyclingfool
manager: annbe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 786ba02c312b7cdb3cf7f0689737084887d536bc
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5206352"
---
# <a name="add-a-favicon"></a><span data-ttu-id="9d04b-103">Agregar un icono de favoritos</span><span class="sxs-lookup"><span data-stu-id="9d04b-103">Add a favicon</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="9d04b-104">En este tema se explica cómo agregar un icono de favoritos al sitio.</span><span class="sxs-lookup"><span data-stu-id="9d04b-104">This topic explains how to add a favicon to your site.</span></span>

## <a name="overview"></a><span data-ttu-id="9d04b-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="9d04b-105">Overview</span></span>

<span data-ttu-id="9d04b-106">Un icono de favoritos es un pequeño archivo gráfico que se muestra en una pestaña del explorador web, en la barra de direcciones, en el historial de exploración, y en marcadores o favoritos, entre otros lugares.</span><span class="sxs-lookup"><span data-stu-id="9d04b-106">A favicon is a small graphics file that is shown on a web browser tab, in the Address bar, in the browsing history, and in bookmarks or favorites, among other places.</span></span> <span data-ttu-id="9d04b-107">Recomendamos que agregue un icono de favoritos al sitio, ya que representa y refuerza su marca, y ayuda a diferenciar el sitio de otros que los clientes visitan.</span><span class="sxs-lookup"><span data-stu-id="9d04b-107">We recommend that you add a favicon to your site, because it represents and reinforces your brand, and helps distinguish your site from other sites that your customers visit.</span></span>

<span data-ttu-id="9d04b-108">Aunque puede agregar varios iconos favoritos de diversos tamaños y tipos de archivos al sitio, este tema muestra cómo agregar un icono favorito único.</span><span class="sxs-lookup"><span data-stu-id="9d04b-108">Although you can add multiple favicons of various sizes and file types to your site, this topic shows how to add a single favicon.</span></span> <span data-ttu-id="9d04b-109">Sin embargo, se utilizan el mismo proceso y ubicación para agregar más iconos favoritos.</span><span class="sxs-lookup"><span data-stu-id="9d04b-109">However, the same process and location are used to add more favicons.</span></span>

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a><span data-ttu-id="9d04b-110">Cargue un icono favorito en la colección de activos del sitio</span><span class="sxs-lookup"><span data-stu-id="9d04b-110">Upload a favicon to your site's asset collection</span></span>

<span data-ttu-id="9d04b-111">Para cargar un icono favorito en la colección de activos del sitio, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9d04b-111">To upload a favicon to your site's asset collection, follow these steps.</span></span>

1. <span data-ttu-id="9d04b-112">En el panel de navegación izquierdo, seleccione **Biblioteca multimedia**.</span><span class="sxs-lookup"><span data-stu-id="9d04b-112">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="9d04b-113">En la barra de comandos, seleccione **Subir \> Subir elementos multimedia**.</span><span class="sxs-lookup"><span data-stu-id="9d04b-113">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="9d04b-114">En la ventana del Explorador de archivos, busque el archivo de imagen de icono favorito que desea cargar, selecciónelo y luego seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="9d04b-114">In the File Explorer window, browse to the favicon image file that you want to upload, select it, and then select **Open**.</span></span>
1. <span data-ttu-id="9d04b-115">En el cuadro de diálogo **Subir elemento multimedia**, introduzca el título requerido y el texto alternativo.</span><span class="sxs-lookup"><span data-stu-id="9d04b-115">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="9d04b-116">Si quiere publicar la imagen inmediatamente después de la carga, seleccione la casilla de verificación **Publicar elementos multimedia después de subir**.</span><span class="sxs-lookup"><span data-stu-id="9d04b-116">If you want to publish the image immediately after upload, select the **Publish media items after upload** check box.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9d04b-117">Si no selecciona la casilla **Publicar elementos multimedia tras la carga**, debe volver a la página **Elementos multimedia** y publicar manualmente el icono favorito posteriormente.</span><span class="sxs-lookup"><span data-stu-id="9d04b-117">If you don't select the **Publish media items after upload** check box, you must return to **Media items** page and manually publish the favicon later.</span></span>

1. <span data-ttu-id="9d04b-118">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9d04b-118">Select **OK**.</span></span>
1. <span data-ttu-id="9d04b-119">En el panel de propiedades de la derecha, copie la dirección URL pública del icono favorito.</span><span class="sxs-lookup"><span data-stu-id="9d04b-119">In the property pane on the right, copy the public URL of the favicon.</span></span> <span data-ttu-id="9d04b-120">Usará esta URL más tarde.</span><span class="sxs-lookup"><span data-stu-id="9d04b-120">You will use this URL later.</span></span>

## <a name="create-the-html-for-your-favicon"></a><span data-ttu-id="9d04b-121">Crear el HTML para el icono favorito</span><span class="sxs-lookup"><span data-stu-id="9d04b-121">Create the HTML for your favicon</span></span>

<span data-ttu-id="9d04b-122">Para crear el HTML para el icono favorito, use el siguiente código HTML.</span><span class="sxs-lookup"><span data-stu-id="9d04b-122">To create the HTML for the favicon, use the following HTML string.</span></span> <span data-ttu-id="9d04b-123">Para el atributo **href**, reemplace **"URL\_pública\_para\_su\_icono favorito"** por la dirección URL pública que ha copiado antes.</span><span class="sxs-lookup"><span data-stu-id="9d04b-123">For the **href** attribute, replace **Public\_URL\_for\_your\_favicon** with the public URL that you copied earlier.</span></span>

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="create-a-fragment-that-contains-a-metatag-for-your-favicon"></a><span data-ttu-id="9d04b-124">Crear un fragmento que contenga una metaetiqueta para el favicon</span><span class="sxs-lookup"><span data-stu-id="9d04b-124">Create a fragment that contains a metatag for your favicon</span></span>

<span data-ttu-id="9d04b-125">Para crear un fragmento que contenga una metaetiqueta para el icono favorito, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9d04b-125">To create a fragment that contains a metatag for your favicon, follow these steps.</span></span>

1. <span data-ttu-id="9d04b-126">Vaya a **Fragmentos** y después **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="9d04b-126">Go to **Fragments**, and select **New**.</span></span>
1. <span data-ttu-id="9d04b-127">En el cuadro de diálogo **Nuevo fragmento**, seleccione **Metaetiquetas** como módulo en el que se basa el fragmento.</span><span class="sxs-lookup"><span data-stu-id="9d04b-127">In the **New fragment** dialog box, select **Metatags** as the module that the fragment is based on.</span></span>
1. <span data-ttu-id="9d04b-128">Especifique un nombre para el fragmento y después seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9d04b-128">Enter a name for the fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="9d04b-129">En el árbol de jerarquía de fragmentos, seleccione el elemento secundario **Metaetiquetas predeterminadas**.</span><span class="sxs-lookup"><span data-stu-id="9d04b-129">In the fragment hierarchy tree, select the **Default metatags** child.</span></span>
1. <span data-ttu-id="9d04b-130">En el panel derecho, en **Metaetiquetas**, seleccione **Añadir** y luego introduzca la cadena HTML que creó anteriormente para el icono favorito.</span><span class="sxs-lookup"><span data-stu-id="9d04b-130">In the right pane, under **Meta Tags**, select **Add**, and then enter the HTML string that you created earlier for the favicon.</span></span> 
1. <span data-ttu-id="9d04b-131">Seleccione **Finalizar edición** y luego seleccione **Publicar** para publicar el fragmento.</span><span class="sxs-lookup"><span data-stu-id="9d04b-131">Select **Finish editing**, and then select **Publish** to publish the fragment.</span></span>

## <a name="add-the-metatag-fragment-to-the-html-head-section-of-your-pages"></a><span data-ttu-id="9d04b-132">Agregar el fragmento de metaetiqueta a la sección de encabezado HTML de las páginas</span><span class="sxs-lookup"><span data-stu-id="9d04b-132">Add the metatag fragment to the HTML head section of your pages</span></span>

<span data-ttu-id="9d04b-133">Para agregar el fragmento de metaetiqueta a la sección **encabezado** de las páginas, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="9d04b-133">To add the metatag fragment to the HTML **head** section of your pages, follow these steps.</span></span>

1. <span data-ttu-id="9d04b-134">Vaya a **Plantillas**, abra la plantilla para las páginas en las que desea agregar el icono favorito y luego seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9d04b-134">Go to **Templates**, open the template for the pages that you want to add your favicon to, and then select **Edit**.</span></span>
1. <span data-ttu-id="9d04b-135">En el árbol de jerarquía de plantilla, seleccione el botón de puntos suspensivos (**...**) a la derecha del contenedor **Cabeza HTML** y luego seleccione **Añadir fragmento**.</span><span class="sxs-lookup"><span data-stu-id="9d04b-135">In the template hierarchy tree, select the ellipsis (**...**) button to the right of the **HTML head** container, and then select **Add fragment**.</span></span>
1. <span data-ttu-id="9d04b-136">En el cuadro de diálogo **Seleccionar fragmento**, seleccione el fragmento de metaetiqueta creado anteriormente y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="9d04b-136">In the **Select fragment** dialog box, select the metatag fragment that you created earlier, and then select **OK**.</span></span>
1. <span data-ttu-id="9d04b-137">Seleccione **Finalizar edición** y luego seleccione **Publicar** para publicar la plantilla.</span><span class="sxs-lookup"><span data-stu-id="9d04b-137">Select **Finish editing**, and then select **Publish** to publish the template.</span></span>

> [!NOTE]
> <span data-ttu-id="9d04b-138">Si su sitio utiliza más de una plantilla, debe agregar el fragmento de metaetiquetas a todas ellas.</span><span class="sxs-lookup"><span data-stu-id="9d04b-138">If your site uses more than one template, you must add the metatags fragment to all of them.</span></span>

<span data-ttu-id="9d04b-139">Cuando obtenga una vista previa de las páginas que se basan en la plantilla a la que agregó el fragmento de metaetiquetas, ahora debería ver el icono favorito en la pestaña del navegador.</span><span class="sxs-lookup"><span data-stu-id="9d04b-139">When you preview pages that are based on the template that you added the metatags fragment to, you should now see the favicon on the browser tab.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9d04b-140">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="9d04b-140">Additional resources</span></span>

[<span data-ttu-id="9d04b-141">Agregar un logotipo</span><span class="sxs-lookup"><span data-stu-id="9d04b-141">Add a logo</span></span>](add-logo.md)

[<span data-ttu-id="9d04b-142">Seleccionar un tema de sitio</span><span class="sxs-lookup"><span data-stu-id="9d04b-142">Select a site theme</span></span>](select-site-theme.md)

[<span data-ttu-id="9d04b-143">Trabajar con archivos de invalidaciones CSS</span><span class="sxs-lookup"><span data-stu-id="9d04b-143">Work with CSS override files</span></span>](css-override-files.md)

[<span data-ttu-id="9d04b-144">Agregar un mensaje de bienvenida</span><span class="sxs-lookup"><span data-stu-id="9d04b-144">Add a welcome message</span></span>](add-welcome-message.md)

[<span data-ttu-id="9d04b-145">Agregar un aviso de derechos de autor</span><span class="sxs-lookup"><span data-stu-id="9d04b-145">Add a copyright notice</span></span>](add-copyright-notice.md)

[<span data-ttu-id="9d04b-146">Agregar idiomas al sitio</span><span class="sxs-lookup"><span data-stu-id="9d04b-146">Add languages to your site</span></span>](add-languages-to-site.md)

[<span data-ttu-id="9d04b-147">Agregar secuencia de comandos a páginas del sitio para admitir telemetría</span><span class="sxs-lookup"><span data-stu-id="9d04b-147">Add script code to site pages to support telemetry</span></span>](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]