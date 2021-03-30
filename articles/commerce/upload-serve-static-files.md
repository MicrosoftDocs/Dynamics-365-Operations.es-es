---
title: Cargar y servir archivos estáticos
description: Este tema describe cómo cargar un archivo estático en el generador de sitios de Microsoft Dynamics 365 Commerce y cómo crear una URL personalizada y un nombre de archivo que se pueda usar para solicitar ese archivo.
author: StuHarg
manager: annbe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: aba9dde2ed9d5fa09e92fcdd784a53f208930eda
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211028"
---
# <a name="upload-and-serve-static-files"></a><span data-ttu-id="2dbdc-103">Cargar y servir archivos estáticos</span><span class="sxs-lookup"><span data-stu-id="2dbdc-103">Upload and serve static files</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="2dbdc-104">Este tema describe cómo cargar un archivo estático en el generador de sitios de Microsoft Dynamics 365 Commerce y cómo crear una URL personalizada y un nombre de archivo que se pueda usar para solicitar ese archivo.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-104">This topic describes how to upload a static file into Microsoft Dynamics 365 Commerce site builder, and how to create a custom URL and file name that can be used to request that file.</span></span>

<span data-ttu-id="2dbdc-105">Algunos conectores de terceros requieren que un archivo esté hospedado y servido desde el sitio de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-105">Some third-party connectors require that a file be hosted and served from the e-commerce site.</span></span> <span data-ttu-id="2dbdc-106">Estos conectores esperan que el archivo sea devuelto por solicitudes a una ruta de acceso URL de devolución de llamada y un nombre de archivo específicos.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-106">These connectors expect that the file will be returned by requests to a specific callback URL path and file name.</span></span> <span data-ttu-id="2dbdc-107">Por lo tanto, este tema explica cómo cargar y entregar un archivo estático que tiene una URL y un nombre de archivo definibles por el usuario en un sitio de comercio electrónico de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-107">Therefore, this topic explains how to upload and serve a static file that has a user-definable URL and file name on a Dynamics 365 Commerce e-commerce site.</span></span>

## <a name="create-a-site-url-that-returns-a-static-file"></a><span data-ttu-id="2dbdc-108">Crear una URL de sitio que devuelva un archivo estático</span><span class="sxs-lookup"><span data-stu-id="2dbdc-108">Create a site URL that returns a static file</span></span>

<span data-ttu-id="2dbdc-109">Para crear una URL de sitio que devuelva un archivo estático en el generador de sitios de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-109">To create a site URL that returns a static file in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="2dbdc-110">Vaya a la biblioteca de medios de su sitio y cargue el archivo que deben servir las solicitudes a la URL que definirá.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-110">Go to your site's Media library, and upload the file that should be served by requests to the URL that you will define.</span></span> <span data-ttu-id="2dbdc-111">Si ya cargó el archivo, puede omitir este paso.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-111">If you've already uploaded the file, you can skip this step.</span></span>
1. <span data-ttu-id="2dbdc-112">Vaya a las **URL** para su sitio.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-112">Go to **URLs** for your site.</span></span>
1. <span data-ttu-id="2dbdc-113">Seleccione **Nuevo \> Nueva URL**.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-113">Select **New \> New URL**.</span></span>
1. <span data-ttu-id="2dbdc-114">En el cuadro de diálogo **Nueva URL**, seleccione **Activo de la biblioteca de medios**.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-114">In the **New URL** dialog box, select **Media library asset**.</span></span>
1. <span data-ttu-id="2dbdc-115">En el campo **Ruta de acceso URL**, especifique la ruta de acceso URL.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-115">In the **URL path** field, enter the URL path.</span></span> <span data-ttu-id="2dbdc-116">Incluya el nombre del archivo en la ruta de acceso.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-116">Include the file name in the path.</span></span>
1. <span data-ttu-id="2dbdc-117">Seleccione **Siguiente**.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-117">Select **Next**.</span></span> <span data-ttu-id="2dbdc-118">La biblioteca de medios se abre y muestra todos los activos de medios del tipo de **documento** que se han subido.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-118">The Media library is opened and shows all media assets of the **document** type that have been uploaded.</span></span>
1. <span data-ttu-id="2dbdc-119">Seleccione el archivo que se debe servir para las solicitudes a la URL que definió en el paso 5.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-119">Select the file that should be served for requests to the URL that you defined in step 5.</span></span>
1. <span data-ttu-id="2dbdc-120">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-120">Select **Save**.</span></span>

<span data-ttu-id="2dbdc-121">En este punto, la dirección URL que ha creado se encuentra en un estado de borrador.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-121">At this point, the URL that you created is in a draft state.</span></span> <span data-ttu-id="2dbdc-122">El archivo al que apunta la URL no se devolverá hasta que publique la URL.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-122">The file that the URL points to won't be returned until you publish the URL.</span></span> <span data-ttu-id="2dbdc-123">Antes de publicar la URL, puede validar que devuelva los datos correctos.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-123">Before you publish the URL, you can validate that it returns the correct data.</span></span>

## <a name="validate-and-publish-a-url"></a><span data-ttu-id="2dbdc-124">Validar y publicar una URL</span><span class="sxs-lookup"><span data-stu-id="2dbdc-124">Validate and publish a URL</span></span>

<span data-ttu-id="2dbdc-125">Para validar una URL antes de publicarla, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-125">To validate an URL before you publish it, follow these steps.</span></span>

1. <span data-ttu-id="2dbdc-126">Vaya a las **URL** para su sitio y seleccione la URL de la que quiere obtener la vista previa.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-126">Go to **URLs** for your site, and select the URL to preview.</span></span>
2. <span data-ttu-id="2dbdc-127">En el panel de propiedades de la derecha, debajo del botón **Editar**, seleccione el enlace URL correcto.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-127">In the properties pane on the right, below the **Edit** button, select the correct URL link.</span></span> <span data-ttu-id="2dbdc-128">Se abre una nueva ventana del explorador y debería recibir un error 404.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-128">A new browser window is opened, and you should receive a 404 error.</span></span>
3. <span data-ttu-id="2dbdc-129">Anexe la cadena de consulta **?preview=inprogress** a la URL (por ejemplo, `https://yoursite.com/callback.html?preview=inprogress`) y vuelva a cargar la página.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-129">Append the **?preview=inprogress** query string to the URL (for example, `https://yoursite.com/callback.html?preview=inprogress`), and reload the page.</span></span> <span data-ttu-id="2dbdc-130">El archivo que cargó en la biblioteca de medios debe devolverse en la respuesta.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-130">The file that you uploaded to the Media library should be returned in the response.</span></span>

<span data-ttu-id="2dbdc-131">Una vez que haya validado la URL, puede publicarla.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-131">After you've validated the URL, you can publish it.</span></span>

1. <span data-ttu-id="2dbdc-132">Vaya a las **URL** para su sitio y seleccione la URL.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-132">Go to **URLs** for your site, and select the URL.</span></span>
2. <span data-ttu-id="2dbdc-133">Seleccione **Publicar** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-133">Select **Publish** on the command bar.</span></span>

## <a name="update-the-file-that-a-url-points-to"></a><span data-ttu-id="2dbdc-134">Actualizar el archivo al que apunta una URL</span><span class="sxs-lookup"><span data-stu-id="2dbdc-134">Update the file that a URL points to</span></span>

<span data-ttu-id="2dbdc-135">Una vez publicada una URL, puede actualizarla para que apunte a un archivo diferente.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-135">After a URL is published, you can update it so that it points to a different file.</span></span> <span data-ttu-id="2dbdc-136">Alternativamente, puede actualizar la URL para que apunte a un tipo de recurso diferente, como se describe en la siguiente sección.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-136">Alternatively, you can update the URL so that it points to a different the type of resource, as described in the next section.</span></span> <span data-ttu-id="2dbdc-137">Por ejemplo, puede apuntar la URL a una página interna o una redirección.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-137">For example, you can point the URL to an internal page or a redirect.</span></span>

<span data-ttu-id="2dbdc-138">Para actualizar el archivo al que apunta una URL, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-138">To update the file that a URL points to, follow these steps.</span></span>

1. <span data-ttu-id="2dbdc-139">Vaya a las **URL** para su sitio y seleccione la URL que quiere actualizar.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-139">Go to **URLs** for your site, and select the URL to update.</span></span>
1. <span data-ttu-id="2dbdc-140">En el panel de propiedades de la derecha, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-140">In the properties pane on the right, select **Edit**.</span></span>
1. <span data-ttu-id="2dbdc-141">En **Asignación de URL**, seleccione el cuadro **Paso 2** y luego seleccione un nuevo documento de la biblioteca de medios.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-141">Under **URL assignment**, select the **Step 2** box, and then select a new document from the Media library.</span></span>
1. <span data-ttu-id="2dbdc-142">Seleccionar **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-142">Select **Apply**.</span></span>

## <a name="update-the-asset-type-that-a-url-points-to"></a><span data-ttu-id="2dbdc-143">Actualizar el tipo de activo al que apunta una URL</span><span class="sxs-lookup"><span data-stu-id="2dbdc-143">Update the asset type that a URL points to</span></span>

<span data-ttu-id="2dbdc-144">También puede actualizar una URL para que apunte a un tipo diferente de activo (recurso), como una página interna o una redirección.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-144">You can also update a URL so that it points to a different type of asset (resource), such as an internal page or a redirect.</span></span>

<span data-ttu-id="2dbdc-145">Para actualizar el tipo de activo al que apunta una URL, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-145">To update the asset type that a URL points to, follow these steps.</span></span>

1. <span data-ttu-id="2dbdc-146">Vaya a las **URL** para su sitio y seleccione la URL que quiere actualizar.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-146">Go to **URLs** for your site, and select the URL to update.</span></span>
1. <span data-ttu-id="2dbdc-147">En el panel de propiedades de la derecha, seleccione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-147">In the properties pane on the right, select **Edit**.</span></span>
1. <span data-ttu-id="2dbdc-148">En **Asignación de URL**, en **Paso 1**, seleccione un tipo de activo diferente.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-148">Under **URL assignment**, under **Step 1**, select a different asset type.</span></span>
1. <span data-ttu-id="2dbdc-149">Selecciona el cuadro **Paso 2** y, a continuación, seleccione el nuevo activo.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-149">Select the **Step 2** box, and then select the new asset.</span></span>
1. <span data-ttu-id="2dbdc-150">Seleccionar **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-150">Select **Apply**.</span></span>

## <a name="change-the-url-path"></a><span data-ttu-id="2dbdc-151">Cambiar la ruta de acceso de la URL</span><span class="sxs-lookup"><span data-stu-id="2dbdc-151">Change the URL path</span></span>

<span data-ttu-id="2dbdc-152">Después de crear una URL, su ruta de acceso no se puede cambiar.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-152">After a URL is created, its path can't be changed.</span></span> <span data-ttu-id="2dbdc-153">Si tiene que cambiar la ruta de acceso de la URL que sirve a un archivo o cualquier otro tipo de recurso, debe crear una nueva URL, asignarla al archivo existente u otro recurso y luego anular la publicación y eliminar la URL anterior.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-153">If you must change the URL path that serves a file or any other type of resource, you have to create a new URL, map it to the existing file or other resource, and then unpublish and delete the old URL.</span></span>

<span data-ttu-id="2dbdc-154">Para cambiar la ruta de acceso de la URL siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-154">To change the URL path, follow these steps.</span></span>

1. <span data-ttu-id="2dbdc-155">Para crear una nueva URL y asignarla al archivo existente u otro recurso, siga las instrucciones en la sección [Crear una URL de sitio que devuelva un archivo estático](#create-a-site-url-that-returns-a-static-file) anteriormente en este tema.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-155">To create a new URL and map it to the existing file or another resource, follow the instructions in the [Create a site URL that returns a static file](#create-a-site-url-that-returns-a-static-file) section earlier in this topic.</span></span>
1. <span data-ttu-id="2dbdc-156">Seleccione la nueva URL y seleccione **Publicar** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-156">Select the new URL, and select **Publish** on the command bar.</span></span> <span data-ttu-id="2dbdc-157">Se publica la nueva URL.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-157">The new URL is published.</span></span>
1. <span data-ttu-id="2dbdc-158">Para anular la publicación de la URL anterior, selecciónela y luego seleccione **Anular publicación** en la barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-158">To unpublish the old URL, select it, and then select **Unpublish** on the command bar.</span></span> <span data-ttu-id="2dbdc-159">Ahora puede eliminar la URL anterior si lo desea.</span><span class="sxs-lookup"><span data-stu-id="2dbdc-159">You can now delete the old URL if you want.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="2dbdc-160">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2dbdc-160">Additional resources</span></span>

[<span data-ttu-id="2dbdc-161">Visión general de la administración de activos digitales</span><span class="sxs-lookup"><span data-stu-id="2dbdc-161">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="2dbdc-162">Cargar imágenes</span><span class="sxs-lookup"><span data-stu-id="2dbdc-162">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="2dbdc-163">Subir vídeos</span><span class="sxs-lookup"><span data-stu-id="2dbdc-163">Upload videos</span></span>](dam-upload-video.md)

[<span data-ttu-id="2dbdc-164">Cargar archivos que no sean imágenes y vídeos</span><span class="sxs-lookup"><span data-stu-id="2dbdc-164">Upload files other than images and videos</span></span>](dam-upload-files.md)

[<span data-ttu-id="2dbdc-165">Recortar imágenes</span><span class="sxs-lookup"><span data-stu-id="2dbdc-165">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="2dbdc-166">Personalizar puntos focales de imagen</span><span class="sxs-lookup"><span data-stu-id="2dbdc-166">Customize image focal points</span></span>](dam-custom-focal-point.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]