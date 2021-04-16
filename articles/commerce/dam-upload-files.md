---
title: Subir archivos que no sean imágenes y vídeos
description: Este tema describe cómo cargar archivos binarios que no sean imágenes y vídeos en el generador de sitios de Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 380bcccd1053cbcc276e964ce97f16d1d39ea75a
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799262"
---
# <a name="upload-files-other-than-images-and-videos"></a><span data-ttu-id="0bc14-103">Cargar archivos que no sean imágenes y vídeos</span><span class="sxs-lookup"><span data-stu-id="0bc14-103">Upload files other than images and videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="0bc14-104">Este tema describe cómo cargar archivos que no sean imágenes y vídeos en el generador de sitios de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0bc14-104">This topic describes how to upload files other than images and videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="0bc14-105">La Biblioteca de medios del generador de sitios de Commerce admite la carga de activos binarios que no sean imágenes o videos.</span><span class="sxs-lookup"><span data-stu-id="0bc14-105">The Commerce site builder Media Library supports the uploading of binary assets other than images or videos.</span></span> <span data-ttu-id="0bc14-106">Por ejemplo, es posible que desee subir archivos Microsoft Excel, Microsoft Word, Microsoft PowerPoint o PDF.</span><span class="sxs-lookup"><span data-stu-id="0bc14-106">For example, you might want to upload Microsoft Excel, Microsoft Word, Microsoft PowerPoint, or PDF files.</span></span>

<span data-ttu-id="0bc14-107">Se admiten los siguientes tipos de documento:</span><span class="sxs-lookup"><span data-stu-id="0bc14-107">The following document types are supported:</span></span>
- <span data-ttu-id="0bc14-108">7Z</span><span class="sxs-lookup"><span data-stu-id="0bc14-108">7Z</span></span>
- <span data-ttu-id="0bc14-109">AVI</span><span class="sxs-lookup"><span data-stu-id="0bc14-109">AVI</span></span>
- <span data-ttu-id="0bc14-110">CS</span><span class="sxs-lookup"><span data-stu-id="0bc14-110">CS</span></span>
- <span data-ttu-id="0bc14-111">CSS</span><span class="sxs-lookup"><span data-stu-id="0bc14-111">CSS</span></span>
- <span data-ttu-id="0bc14-112">DOC</span><span class="sxs-lookup"><span data-stu-id="0bc14-112">DOC</span></span>
- <span data-ttu-id="0bc14-113">DOCX</span><span class="sxs-lookup"><span data-stu-id="0bc14-113">DOCX</span></span>
- <span data-ttu-id="0bc14-114">EPUB</span><span class="sxs-lookup"><span data-stu-id="0bc14-114">EPUB</span></span>
- <span data-ttu-id="0bc14-115">GIF</span><span class="sxs-lookup"><span data-stu-id="0bc14-115">GIF</span></span>
- <span data-ttu-id="0bc14-116">INDD</span><span class="sxs-lookup"><span data-stu-id="0bc14-116">INDD</span></span>
- <span data-ttu-id="0bc14-117">JAR</span><span class="sxs-lookup"><span data-stu-id="0bc14-117">JAR</span></span>
- <span data-ttu-id="0bc14-118">JPG</span><span class="sxs-lookup"><span data-stu-id="0bc14-118">JPG</span></span>
- <span data-ttu-id="0bc14-119">JPEG</span><span class="sxs-lookup"><span data-stu-id="0bc14-119">JPEG</span></span>
- <span data-ttu-id="0bc14-120">JS</span><span class="sxs-lookup"><span data-stu-id="0bc14-120">JS</span></span>
- <span data-ttu-id="0bc14-121">MP3</span><span class="sxs-lookup"><span data-stu-id="0bc14-121">MP3</span></span>
- <span data-ttu-id="0bc14-122">MP4</span><span class="sxs-lookup"><span data-stu-id="0bc14-122">MP4</span></span>
- <span data-ttu-id="0bc14-123">MPEG</span><span class="sxs-lookup"><span data-stu-id="0bc14-123">MPEG</span></span>
- <span data-ttu-id="0bc14-124">MPG</span><span class="sxs-lookup"><span data-stu-id="0bc14-124">MPG</span></span>
- <span data-ttu-id="0bc14-125">ODP</span><span class="sxs-lookup"><span data-stu-id="0bc14-125">ODP</span></span>
- <span data-ttu-id="0bc14-126">ODS</span><span class="sxs-lookup"><span data-stu-id="0bc14-126">ODS</span></span>
- <span data-ttu-id="0bc14-127">ODT</span><span class="sxs-lookup"><span data-stu-id="0bc14-127">ODT</span></span>
- <span data-ttu-id="0bc14-128">PDF</span><span class="sxs-lookup"><span data-stu-id="0bc14-128">PDF</span></span>
- <span data-ttu-id="0bc14-129">PNG</span><span class="sxs-lookup"><span data-stu-id="0bc14-129">PNG</span></span>
- <span data-ttu-id="0bc14-130">PPT</span><span class="sxs-lookup"><span data-stu-id="0bc14-130">PPT</span></span>
- <span data-ttu-id="0bc14-131">PPTX</span><span class="sxs-lookup"><span data-stu-id="0bc14-131">PPTX</span></span>
- <span data-ttu-id="0bc14-132">PS</span><span class="sxs-lookup"><span data-stu-id="0bc14-132">PS</span></span>
- <span data-ttu-id="0bc14-133">QXP</span><span class="sxs-lookup"><span data-stu-id="0bc14-133">QXP</span></span>
- <span data-ttu-id="0bc14-134">RAR</span><span class="sxs-lookup"><span data-stu-id="0bc14-134">RAR</span></span>
- <span data-ttu-id="0bc14-135">RTF</span><span class="sxs-lookup"><span data-stu-id="0bc14-135">RTF</span></span>
- <span data-ttu-id="0bc14-136">SVG</span><span class="sxs-lookup"><span data-stu-id="0bc14-136">SVG</span></span>
- <span data-ttu-id="0bc14-137">TAR</span><span class="sxs-lookup"><span data-stu-id="0bc14-137">TAR</span></span>
- <span data-ttu-id="0bc14-138">TGZ</span><span class="sxs-lookup"><span data-stu-id="0bc14-138">TGZ</span></span>
- <span data-ttu-id="0bc14-139">TXT</span><span class="sxs-lookup"><span data-stu-id="0bc14-139">TXT</span></span>
- <span data-ttu-id="0bc14-140">WMV</span><span class="sxs-lookup"><span data-stu-id="0bc14-140">WMV</span></span>
- <span data-ttu-id="0bc14-141">XLS</span><span class="sxs-lookup"><span data-stu-id="0bc14-141">XLS</span></span>
- <span data-ttu-id="0bc14-142">XLSX</span><span class="sxs-lookup"><span data-stu-id="0bc14-142">XLSX</span></span>
- <span data-ttu-id="0bc14-143">XML</span><span class="sxs-lookup"><span data-stu-id="0bc14-143">XML</span></span>
- <span data-ttu-id="0bc14-144">ZIP</span><span class="sxs-lookup"><span data-stu-id="0bc14-144">ZIP</span></span>

## <a name="upload-a-file"></a><span data-ttu-id="0bc14-145">Cargar un archivo</span><span class="sxs-lookup"><span data-stu-id="0bc14-145">Upload a file</span></span>

<span data-ttu-id="0bc14-146">Para subir un archivo al generador de sitios en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0bc14-146">To upload a file to Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="0bc14-147">En el panel de navegación izquierdo, seleccione **Biblioteca multimedia**.</span><span class="sxs-lookup"><span data-stu-id="0bc14-147">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="0bc14-148">En la barra de comandos, seleccione **Subir \> Subir elementos multimedia**.</span><span class="sxs-lookup"><span data-stu-id="0bc14-148">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="0bc14-149">En el Explorador de archivos, seleccione uno o más archivos y luego seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="0bc14-149">In File Explorer, select one or more files and then select **Open**.</span></span>
1. <span data-ttu-id="0bc14-150">En el cuadro de diálogo **Subir elemento multimedia**, introduzca el título, descripción y metadatos de palabras clave según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="0bc14-150">In the **Upload Media Item** dialog box, enter title, description, and keyword metadata as needed.</span></span>
1. <span data-ttu-id="0bc14-151">Para publicar los archivos inmediatamente después de la carga, seleccione la casilla de verificación **Publicar elementos multimedia después de subir**.</span><span class="sxs-lookup"><span data-stu-id="0bc14-151">To publish the file(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="0bc14-152">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0bc14-152">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0bc14-153">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="0bc14-153">Additional resources</span></span>

[<span data-ttu-id="0bc14-154">Visión general de la administración de activos digitales</span><span class="sxs-lookup"><span data-stu-id="0bc14-154">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="0bc14-155">Cargar imágenes</span><span class="sxs-lookup"><span data-stu-id="0bc14-155">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="0bc14-156">Cargar vídeo</span><span class="sxs-lookup"><span data-stu-id="0bc14-156">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="0bc14-157">Recortar imágenes</span><span class="sxs-lookup"><span data-stu-id="0bc14-157">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="0bc14-158">Personalizar puntos focales de imagen</span><span class="sxs-lookup"><span data-stu-id="0bc14-158">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="0bc14-159">Cargar y servir archivos estáticos</span><span class="sxs-lookup"><span data-stu-id="0bc14-159">Upload and serve static files</span></span>](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
