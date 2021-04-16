---
title: Cargar imágenes
description: En este tema se describe cómo subir imágenes en el generador de sitios de Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 2a0a2fdb275cbeb65c06c01128e90ba660f98c9b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5799238"
---
# <a name="upload-images"></a><span data-ttu-id="ca677-103">Cargar imágenes</span><span class="sxs-lookup"><span data-stu-id="ca677-103">Upload images</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ca677-104">En este tema se describe cómo subir imágenes en el generador de sitios de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ca677-104">This topic describes how to upload images in Microsoft Dynamics 365 Commerce site builder.</span></span>

<span data-ttu-id="ca677-105">La Biblioteca de medios del creador de sitios de Commerce le permite cargar imágenes, ya sea individualmente o en masa, utilizando carpetas.</span><span class="sxs-lookup"><span data-stu-id="ca677-105">The Commerce site builder Media Library allows you to upload images, either singly or in bulk using folders.</span></span> <span data-ttu-id="ca677-106">Siempre debe cargar la versión de la imagen con la mayor resolución y calidad, ya que el componente de cambio de tamaño de la imagen optimizará automáticamente la imagen para diferentes ventanas y sus puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="ca677-106">You should always upload the version of the image with highest resolution and quality, because the image resizer component will automatically optimize the image for different viewports and their breakpoints.</span></span>

### <a name="image-information-specified-during-upload"></a><span data-ttu-id="ca677-107">Información de imagen especificada durante la carga</span><span class="sxs-lookup"><span data-stu-id="ca677-107">Image information specified during upload</span></span>

<span data-ttu-id="ca677-108">Al cargar una imagen, se puede especificar la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="ca677-108">When uploading an image, the following information can be specified.</span></span>

- <span data-ttu-id="ca677-109">**Título, texto alternativo, descripción, palabras clave**: metadatos de la imagen o imágenes.</span><span class="sxs-lookup"><span data-stu-id="ca677-109">**Title, Alt Text, Description, Keywords**: Metadata of the image or images.</span></span> <span data-ttu-id="ca677-110">El título y el texto alternativo son valores obligatorios.</span><span class="sxs-lookup"><span data-stu-id="ca677-110">Title and alt text are required values.</span></span>
- <span data-ttu-id="ca677-111">**Seleccionar categoría**:</span><span class="sxs-lookup"><span data-stu-id="ca677-111">**Select category**:</span></span>
    - <span data-ttu-id="ca677-112">**Ninguno**: se utiliza para una imagen o imágenes de narración de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="ca677-112">**None**: Used for an e-Commerce storytelling image or images.</span></span>
    - <span data-ttu-id="ca677-113">**Producto, Categoría, Cliente, Empleado, Catálogo**: usado para imagen o imágenes omnicanal de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ca677-113">**Product, Category, Customer, Employee, Catalog**: Used for Dynamics 365 Commerce omni-channel image or images.</span></span>
- <span data-ttu-id="ca677-114">**Publicar activos después de subir**: cuando esta casilla de verificación está seleccionada, la imagen o las imágenes se publican inmediatamente después de la carga.</span><span class="sxs-lookup"><span data-stu-id="ca677-114">**Publish assets after upload**: When this check box is selected, the image or images are published immediately after upload.</span></span>

> [!NOTE]
> <span data-ttu-id="ca677-115">Los activos de imagen con una categoría asignada también se etiquetan automáticamente con la categoría como una palabra clave para ayudar a buscar activos de una categoría específica.</span><span class="sxs-lookup"><span data-stu-id="ca677-115">Image assets with a category assigned are also automatically tagged with the category as a keyword to aid searching for assets of a specific category.</span></span>

### <a name="naming-conventions-for-omni-channel-images"></a><span data-ttu-id="ca677-116">Convenciones de nomenclatura para imágenes omnicanal</span><span class="sxs-lookup"><span data-stu-id="ca677-116">Naming conventions for omni-channel images</span></span> 

<span data-ttu-id="ca677-117">Si ha configurado la Biblioteca multimedia como el backend de imagen omnicanal, puede usar categorías de imágenes para indicar a qué categoría pertenece la imagen cargada.</span><span class="sxs-lookup"><span data-stu-id="ca677-117">If you have configured the Media Library as the omni-channel image backend, you can use image categories to indicate which category the uploaded image belongs to.</span></span> <span data-ttu-id="ca677-118">También hay una convención de nomenclatura que debe seguirse para garantizar que las imágenes sean recuperadas correctamente por otros canales, como el punto de venta (PDV).</span><span class="sxs-lookup"><span data-stu-id="ca677-118">There is also a naming convention that should be followed to ensure that images are retrieved correctly by other channels, such as point of sale (POS).</span></span>

<span data-ttu-id="ca677-119">La convención de nomenclatura predeterminada varía según la categoría:</span><span class="sxs-lookup"><span data-stu-id="ca677-119">The default naming convention varies based on the category:</span></span>
- <span data-ttu-id="ca677-120">Las imágenes de catálogo deben llamarse "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="ca677-120">Catalog images should be named "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"</span></span>
- <span data-ttu-id="ca677-121">Las imágenes de categoría deben llamarse "**/Categories/\{CategoryName\}.png**"</span><span class="sxs-lookup"><span data-stu-id="ca677-121">Category images should be named "**/Categories/\{CategoryName\}.png**"</span></span>
- <span data-ttu-id="ca677-122">Las imágenes de los clientes deben llamarse "**/Customers/\{CustomerNumber\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="ca677-122">Customer images should be named "**/Customers/\{CustomerNumber\}.jpg**"</span></span>
- <span data-ttu-id="ca677-123">Las imágenes de los empleados deben llamarse "**/Workers/\{WorkerNumber\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="ca677-123">Employee images should be named "**/Workers/\{WorkerNumber\}.jpg**"</span></span>
- <span data-ttu-id="ca677-124">Las imágenes del producto deben llamarse "**/Products/\{ProductNumber\}_000_001.png**"</span><span class="sxs-lookup"><span data-stu-id="ca677-124">Product images should be named "**/Products/\{ProductNumber\}_000_001.png**"</span></span>
    - <span data-ttu-id="ca677-125">001 es la secuencia de la imagen y puede ser 001, 002, 003, 004 o 005</span><span class="sxs-lookup"><span data-stu-id="ca677-125">001 is the sequence of the image and it can be 001, 002, 003, 004 or 005</span></span>
- <span data-ttu-id="ca677-126">Las imágenes de variante del producto deben llamarse "**/Products/\{ProductNumber\} \^ \{Style\} \^ \{Size\} \^ \{Color\} \^\_000_001.png**"</span><span class="sxs-lookup"><span data-stu-id="ca677-126">Product variant images should be named "**/Products/\{ProductNumber\} \^ \{Style\} \^ \{Size\} \^ \{Color\} \^\_000_001.png**"</span></span>
    - <span data-ttu-id="ca677-127">Por ejemplo: 93039 \^ \^ 2 \^ Black \^_000_001.png</span><span class="sxs-lookup"><span data-stu-id="ca677-127">For example: 93039 \^ \^ 2 \^ Black \^_000_001.png</span></span>

## <a name="upload-an-image"></a><span data-ttu-id="ca677-128">Subir una imagen</span><span class="sxs-lookup"><span data-stu-id="ca677-128">Upload an image</span></span>

<span data-ttu-id="ca677-129">Para subir una imagen al generador de sitios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ca677-129">To upload an image in site builder, follow these steps.</span></span>

1. <span data-ttu-id="ca677-130">En el panel de navegación izquierdo, seleccione **Biblioteca multimedia**.</span><span class="sxs-lookup"><span data-stu-id="ca677-130">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="ca677-131">En la barra de comandos, seleccione **Subir \> Subir elementos multimedia**.</span><span class="sxs-lookup"><span data-stu-id="ca677-131">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="ca677-132">En la ventana del Explorador de archivos, navegue y seleccione uno o más archivos de imagen para cargar, y luego seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="ca677-132">In the File Explorer window, navigate to and select one or more image files to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="ca677-133">En el cuadro de diálogo **Subir elemento multimedia**, introduzca el título requerido y el texto alternativo.</span><span class="sxs-lookup"><span data-stu-id="ca677-133">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="ca677-134">Introduzca la descripción opcional y las palabras clave y seleccione una categoría si lo desea.</span><span class="sxs-lookup"><span data-stu-id="ca677-134">Enter optional description and keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="ca677-135">Si quiere publicar las imágenes inmediatamente después de la carga, seleccione la casilla de verificación **Publicar elementos multimedia después de subir**.</span><span class="sxs-lookup"><span data-stu-id="ca677-135">If you want to publish the image(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="ca677-136">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ca677-136">Select **OK**.</span></span>

## <a name="upload-a-folder-of-images"></a><span data-ttu-id="ca677-137">Subir una carpeta de imágenes</span><span class="sxs-lookup"><span data-stu-id="ca677-137">Upload a folder of images</span></span>

<span data-ttu-id="ca677-138">Para subir en masa una carpeta de imágenes en el generador de sitios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ca677-138">To bulk upload a folder of images in site builder, follow these steps.</span></span>

1. <span data-ttu-id="ca677-139">En el panel de navegación izquierdo, seleccione **Biblioteca multimedia**.</span><span class="sxs-lookup"><span data-stu-id="ca677-139">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="ca677-140">En la barra de comandos, seleccione **Subir \> Subir carpeta**.</span><span class="sxs-lookup"><span data-stu-id="ca677-140">On the command bar, select **Upload \> Upload Folder**.</span></span>
1. <span data-ttu-id="ca677-141">En la ventana del Explorador de archivos, navegue y una carpeta para cargar, y luego seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="ca677-141">In the File Explorer window, navigate to and select a folder to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="ca677-142">En el cuadro de diálogo **Subir elementos multimedia**, introduzca palabras clave opcionales y seleccione una categoría si lo desea.</span><span class="sxs-lookup"><span data-stu-id="ca677-142">In the **Upload Media Items** dialog box, enter optional keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="ca677-143">Si quiere publicar las imágenes en la carpeta inmediatamente después de la carga, seleccione la casilla de verificación **Publicar elementos multimedia después de subir**.</span><span class="sxs-lookup"><span data-stu-id="ca677-143">If you want to publish the images in the folder immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="ca677-144">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ca677-144">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ca677-145">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ca677-145">Additional resources</span></span>

[<span data-ttu-id="ca677-146">Visión general de la administración de activos digitales</span><span class="sxs-lookup"><span data-stu-id="ca677-146">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="ca677-147">Cargar vídeo</span><span class="sxs-lookup"><span data-stu-id="ca677-147">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="ca677-148">Subir archivos</span><span class="sxs-lookup"><span data-stu-id="ca677-148">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="ca677-149">Recortar imágenes</span><span class="sxs-lookup"><span data-stu-id="ca677-149">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="ca677-150">Personalizar puntos focales de imagen</span><span class="sxs-lookup"><span data-stu-id="ca677-150">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="ca677-151">Cargar y servir archivos estáticos</span><span class="sxs-lookup"><span data-stu-id="ca677-151">Upload and serve static files</span></span>](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
