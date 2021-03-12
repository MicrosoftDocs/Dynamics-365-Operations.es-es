---
title: Subir archivos que no sean imágenes y vídeos
description: Este tema describe cómo cargar archivos binarios que no sean imágenes y vídeos en el generador de sitios de Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 03/03/2020
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 3392f5f36d04e8cb0a9d6e6b7db31ff62c987649
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4995779"
---
# <a name="upload-files-other-than-images-and-videos"></a><span data-ttu-id="94d2e-103">Subir archivos que no sean imágenes y vídeos</span><span class="sxs-lookup"><span data-stu-id="94d2e-103">Upload files other than images and videos</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="94d2e-104">Este tema describe cómo cargar archivos que no sean imágenes y videos en el generador de sitios de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="94d2e-104">This topic describes how to upload files other than images and videos in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="94d2e-105">Información general</span><span class="sxs-lookup"><span data-stu-id="94d2e-105">Overview</span></span>

<span data-ttu-id="94d2e-106">La Biblioteca de medios del generador de sitios de Commerce admite la carga de activos binarios que no sean imágenes o videos.</span><span class="sxs-lookup"><span data-stu-id="94d2e-106">The Commerce site builder Media Library supports the uploading of binary assets other than images or videos.</span></span> <span data-ttu-id="94d2e-107">Por ejemplo, es posible que desee subir archivos Microsoft Excel, Microsoft Word, Microsoft PowerPoint o PDF.</span><span class="sxs-lookup"><span data-stu-id="94d2e-107">For example, you might want to upload Microsoft Excel, Microsoft Word, Microsoft PowerPoint, or PDF files.</span></span>

<span data-ttu-id="94d2e-108">Se admiten los siguientes tipos de documento:</span><span class="sxs-lookup"><span data-stu-id="94d2e-108">The following document types are supported:</span></span>
- <span data-ttu-id="94d2e-109">7Z</span><span class="sxs-lookup"><span data-stu-id="94d2e-109">7Z</span></span>
- <span data-ttu-id="94d2e-110">AVI</span><span class="sxs-lookup"><span data-stu-id="94d2e-110">AVI</span></span>
- <span data-ttu-id="94d2e-111">CS</span><span class="sxs-lookup"><span data-stu-id="94d2e-111">CS</span></span>
- <span data-ttu-id="94d2e-112">CSS</span><span class="sxs-lookup"><span data-stu-id="94d2e-112">CSS</span></span>
- <span data-ttu-id="94d2e-113">DOC</span><span class="sxs-lookup"><span data-stu-id="94d2e-113">DOC</span></span>
- <span data-ttu-id="94d2e-114">DOCX</span><span class="sxs-lookup"><span data-stu-id="94d2e-114">DOCX</span></span>
- <span data-ttu-id="94d2e-115">EPUB</span><span class="sxs-lookup"><span data-stu-id="94d2e-115">EPUB</span></span>
- <span data-ttu-id="94d2e-116">GIF</span><span class="sxs-lookup"><span data-stu-id="94d2e-116">GIF</span></span>
- <span data-ttu-id="94d2e-117">INDD</span><span class="sxs-lookup"><span data-stu-id="94d2e-117">INDD</span></span>
- <span data-ttu-id="94d2e-118">JAR</span><span class="sxs-lookup"><span data-stu-id="94d2e-118">JAR</span></span>
- <span data-ttu-id="94d2e-119">JPG</span><span class="sxs-lookup"><span data-stu-id="94d2e-119">JPG</span></span>
- <span data-ttu-id="94d2e-120">JPEG</span><span class="sxs-lookup"><span data-stu-id="94d2e-120">JPEG</span></span>
- <span data-ttu-id="94d2e-121">JS</span><span class="sxs-lookup"><span data-stu-id="94d2e-121">JS</span></span>
- <span data-ttu-id="94d2e-122">MP3</span><span class="sxs-lookup"><span data-stu-id="94d2e-122">MP3</span></span>
- <span data-ttu-id="94d2e-123">MP4</span><span class="sxs-lookup"><span data-stu-id="94d2e-123">MP4</span></span>
- <span data-ttu-id="94d2e-124">MPEG</span><span class="sxs-lookup"><span data-stu-id="94d2e-124">MPEG</span></span>
- <span data-ttu-id="94d2e-125">MPG</span><span class="sxs-lookup"><span data-stu-id="94d2e-125">MPG</span></span>
- <span data-ttu-id="94d2e-126">ODP</span><span class="sxs-lookup"><span data-stu-id="94d2e-126">ODP</span></span>
- <span data-ttu-id="94d2e-127">ODS</span><span class="sxs-lookup"><span data-stu-id="94d2e-127">ODS</span></span>
- <span data-ttu-id="94d2e-128">ODT</span><span class="sxs-lookup"><span data-stu-id="94d2e-128">ODT</span></span>
- <span data-ttu-id="94d2e-129">PDF</span><span class="sxs-lookup"><span data-stu-id="94d2e-129">PDF</span></span>
- <span data-ttu-id="94d2e-130">PNG</span><span class="sxs-lookup"><span data-stu-id="94d2e-130">PNG</span></span>
- <span data-ttu-id="94d2e-131">PPT</span><span class="sxs-lookup"><span data-stu-id="94d2e-131">PPT</span></span>
- <span data-ttu-id="94d2e-132">PPTX</span><span class="sxs-lookup"><span data-stu-id="94d2e-132">PPTX</span></span>
- <span data-ttu-id="94d2e-133">PS</span><span class="sxs-lookup"><span data-stu-id="94d2e-133">PS</span></span>
- <span data-ttu-id="94d2e-134">QXP</span><span class="sxs-lookup"><span data-stu-id="94d2e-134">QXP</span></span>
- <span data-ttu-id="94d2e-135">RAR</span><span class="sxs-lookup"><span data-stu-id="94d2e-135">RAR</span></span>
- <span data-ttu-id="94d2e-136">RTF</span><span class="sxs-lookup"><span data-stu-id="94d2e-136">RTF</span></span>
- <span data-ttu-id="94d2e-137">SVG</span><span class="sxs-lookup"><span data-stu-id="94d2e-137">SVG</span></span>
- <span data-ttu-id="94d2e-138">TAR</span><span class="sxs-lookup"><span data-stu-id="94d2e-138">TAR</span></span>
- <span data-ttu-id="94d2e-139">TGZ</span><span class="sxs-lookup"><span data-stu-id="94d2e-139">TGZ</span></span>
- <span data-ttu-id="94d2e-140">TXT</span><span class="sxs-lookup"><span data-stu-id="94d2e-140">TXT</span></span>
- <span data-ttu-id="94d2e-141">WMV</span><span class="sxs-lookup"><span data-stu-id="94d2e-141">WMV</span></span>
- <span data-ttu-id="94d2e-142">XLS</span><span class="sxs-lookup"><span data-stu-id="94d2e-142">XLS</span></span>
- <span data-ttu-id="94d2e-143">XLSX</span><span class="sxs-lookup"><span data-stu-id="94d2e-143">XLSX</span></span>
- <span data-ttu-id="94d2e-144">XML</span><span class="sxs-lookup"><span data-stu-id="94d2e-144">XML</span></span>
- <span data-ttu-id="94d2e-145">ZIP</span><span class="sxs-lookup"><span data-stu-id="94d2e-145">ZIP</span></span>

## <a name="upload-a-file"></a><span data-ttu-id="94d2e-146">Cargar un archivo</span><span class="sxs-lookup"><span data-stu-id="94d2e-146">Upload a file</span></span>

<span data-ttu-id="94d2e-147">Para subir un archivo al generador de sitios en Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="94d2e-147">To upload a file to Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="94d2e-148">En el panel de navegación izquierdo, seleccione **Biblioteca multimedia**.</span><span class="sxs-lookup"><span data-stu-id="94d2e-148">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="94d2e-149">En la barra de comandos, seleccione **Subir \> Subir elementos multimedia**.</span><span class="sxs-lookup"><span data-stu-id="94d2e-149">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="94d2e-150">En el Explorador de archivos, seleccione uno o más archivos y luego seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="94d2e-150">In File Explorer, select one or more files and then select **Open**.</span></span>
1. <span data-ttu-id="94d2e-151">En el cuadro de diálogo **Subir elemento multimedia**, introduzca el título, descripción y metadatos de palabras clave según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="94d2e-151">In the **Upload Media Item** dialog box, enter title, description, and keyword metadata as needed.</span></span>
1. <span data-ttu-id="94d2e-152">Para publicar los archivos inmediatamente después de la carga, seleccione la casilla de verificación **Publicar elementos multimedia después de subir**.</span><span class="sxs-lookup"><span data-stu-id="94d2e-152">To publish the file(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="94d2e-153">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="94d2e-153">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="94d2e-154">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="94d2e-154">Additional resources</span></span>

[<span data-ttu-id="94d2e-155">Visión general de la administración de activos digitales</span><span class="sxs-lookup"><span data-stu-id="94d2e-155">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="94d2e-156">Cargar imágenes</span><span class="sxs-lookup"><span data-stu-id="94d2e-156">Upload images</span></span>](dam-upload-images.md)

[<span data-ttu-id="94d2e-157">Cargar vídeo</span><span class="sxs-lookup"><span data-stu-id="94d2e-157">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="94d2e-158">Recortar imágenes</span><span class="sxs-lookup"><span data-stu-id="94d2e-158">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="94d2e-159">Personalizar puntos focales de imagen</span><span class="sxs-lookup"><span data-stu-id="94d2e-159">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="94d2e-160">Cargar y servir archivos estáticos</span><span class="sxs-lookup"><span data-stu-id="94d2e-160">Upload and serve static files</span></span>](upload-serve-static-files.md)
