---
title: Subir imágenes
description: En este tema se describe cómo cargar imágenes en el generador de sitios de Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: f562d3376fde6a24e6a1e1a3f7f4192cf290ae90
ms.sourcegitcommit: 597476103bb695e3cbe6d9ffcd7a466400346636
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2020
ms.locfileid: "4594293"
---
# <a name="upload-images"></a><span data-ttu-id="5b7cc-103">Subir imágenes</span><span class="sxs-lookup"><span data-stu-id="5b7cc-103">Upload images</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5b7cc-104">En este tema se describe cómo cargar imágenes en el generador de sitios de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-104">This topic describes how to upload images in Microsoft Dynamics 365 Commerce site builder.</span></span>

## <a name="overview"></a><span data-ttu-id="5b7cc-105">Información general</span><span class="sxs-lookup"><span data-stu-id="5b7cc-105">Overview</span></span>

<span data-ttu-id="5b7cc-106">La Biblioteca de medios del creador de sitios de Commerce le permite cargar imágenes, ya sea individualmente o en masa, utilizando carpetas.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-106">The Commerce site builder Media Library allows you to upload images, either singly or in bulk using folders.</span></span> <span data-ttu-id="5b7cc-107">Siempre debe cargar la versión de la imagen con la mayor resolución y calidad, ya que el componente de cambio de tamaño de la imagen optimizará automáticamente la imagen para diferentes ventanas y sus puntos de interrupción.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-107">You should always upload the version of the image with highest resolution and quality, because the image resizer component will automatically optimize the image for different viewports and their breakpoints.</span></span>

### <a name="image-information-specified-during-upload"></a><span data-ttu-id="5b7cc-108">Información de imagen especificada durante la carga</span><span class="sxs-lookup"><span data-stu-id="5b7cc-108">Image information specified during upload</span></span>

<span data-ttu-id="5b7cc-109">Al cargar una imagen, se puede especificar la siguiente información.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-109">When uploading an image, the following information can be specified.</span></span>

- <span data-ttu-id="5b7cc-110">**Título, texto alternativo, descripción, palabras clave**: metadatos de la imagen o imágenes.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-110">**Title, Alt Text, Description, Keywords**: Metadata of the image or images.</span></span> <span data-ttu-id="5b7cc-111">El título y el texto alternativo son valores obligatorios.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-111">Title and alt text are required values.</span></span>
- <span data-ttu-id="5b7cc-112">**Seleccionar categoría**:</span><span class="sxs-lookup"><span data-stu-id="5b7cc-112">**Select category**:</span></span>
    - <span data-ttu-id="5b7cc-113">**Ninguno**: se utiliza para una imagen o imágenes de narración de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-113">**None**: Used for an e-Commerce storytelling image or images.</span></span>
    - <span data-ttu-id="5b7cc-114">**Producto, Categoría, Cliente, Empleado, Catálogo**: usado para imagen o imágenes omnicanal de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-114">**Product, Category, Customer, Employee, Catalog**: Used for Dynamics 365 Commerce omni-channel image or images.</span></span>
- <span data-ttu-id="5b7cc-115">**Publicar activos después de subir**: cuando esta casilla de verificación está seleccionada, la imagen o las imágenes se publican inmediatamente después de la carga.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-115">**Publish assets after upload**: When this check box is selected, the image or images are published immediately after upload.</span></span>

> [!NOTE]
> <span data-ttu-id="5b7cc-116">Los activos de imagen con una categoría asignada también se etiquetan automáticamente con la categoría como una palabra clave para ayudar a buscar activos de una categoría específica.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-116">Image assets with a category assigned are also automatically tagged with the category as a keyword to aid searching for assets of a specific category.</span></span>

### <a name="naming-conventions-for-omni-channel-images"></a><span data-ttu-id="5b7cc-117">Convenciones de nomenclatura para imágenes omnicanal</span><span class="sxs-lookup"><span data-stu-id="5b7cc-117">Naming conventions for omni-channel images</span></span> 

<span data-ttu-id="5b7cc-118">Si ha configurado la Biblioteca multimedia como el backend de imagen omnicanal, puede usar categorías de imágenes para indicar a qué categoría pertenece la imagen cargada.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-118">If you have configured the Media Library as the omni-channel image backend, you can use image categories to indicate which category the uploaded image belongs to.</span></span> <span data-ttu-id="5b7cc-119">También hay una convención de nomenclatura que debe seguirse para garantizar que las imágenes sean recuperadas correctamente por otros canales, como el punto de venta (PDV).</span><span class="sxs-lookup"><span data-stu-id="5b7cc-119">There is also a naming convention that should be followed to ensure that images are retrieved correctly by other channels, such as point of sale (POS).</span></span>

<span data-ttu-id="5b7cc-120">La convención de nomenclatura predeterminada varía según la categoría:</span><span class="sxs-lookup"><span data-stu-id="5b7cc-120">The default naming convention varies based on the category:</span></span>
- <span data-ttu-id="5b7cc-121">Las imágenes de catálogo deben llamarse "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="5b7cc-121">Catalog images should be named "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"</span></span>
- <span data-ttu-id="5b7cc-122">Las imágenes de categoría deben llamarse "**/Categories/\{CategoryName\}.png**"</span><span class="sxs-lookup"><span data-stu-id="5b7cc-122">Category images should be named "**/Categories/\{CategoryName\}.png**"</span></span>
- <span data-ttu-id="5b7cc-123">Las imágenes de los clientes deben llamarse "**/Customers/\{CustomerNumber\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="5b7cc-123">Customer images should be named "**/Customers/\{CustomerNumber\}.jpg**"</span></span>
- <span data-ttu-id="5b7cc-124">Las imágenes de los empleados deben llamarse "**/Workers/\{WorkerNumber\}.jpg**"</span><span class="sxs-lookup"><span data-stu-id="5b7cc-124">Employee images should be named "**/Workers/\{WorkerNumber\}.jpg**"</span></span>
- <span data-ttu-id="5b7cc-125">Las imágenes del producto deben llamarse "**/Products/\{ProductNumber\}_000_001.png**"</span><span class="sxs-lookup"><span data-stu-id="5b7cc-125">Product images should be named "**/Products/\{ProductNumber\}_000_001.png**"</span></span>
    - <span data-ttu-id="5b7cc-126">001 es la secuencia de la imagen y puede ser 001, 002, 003, 004 o 005</span><span class="sxs-lookup"><span data-stu-id="5b7cc-126">001 is the sequence of the image and it can be 001, 002, 003, 004 or 005</span></span>
- <span data-ttu-id="5b7cc-127">Las imágenes de variante del producto deben llamarse "**/Products/\{ProductNumber\}\_\{Size\}\_\{Color\}\_\{Style\}\_000_001.png**"</span><span class="sxs-lookup"><span data-stu-id="5b7cc-127">Product variant images should be named "**/Products/\{ProductNumber\}\_\{Size\}\_\{Color\}\_\{Style\}\_000_001.png**"</span></span>

## <a name="upload-an-image"></a><span data-ttu-id="5b7cc-128">Subir una imagen</span><span class="sxs-lookup"><span data-stu-id="5b7cc-128">Upload an image</span></span>

<span data-ttu-id="5b7cc-129">Para subir una imagen al generador de sitios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-129">To upload an image in site builder, follow these steps.</span></span>

1. <span data-ttu-id="5b7cc-130">En el panel de navegación izquierdo, seleccione **Biblioteca multimedia**.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-130">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="5b7cc-131">En la barra de comandos, seleccione **Subir \> Subir elementos multimedia**.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-131">On the command bar, select **Upload \> Upload Media Items**.</span></span>
1. <span data-ttu-id="5b7cc-132">En la ventana del Explorador de archivos, navegue y seleccione uno o más archivos de imagen para cargar, y luego seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-132">In the File Explorer window, navigate to and select one or more image files to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="5b7cc-133">En el cuadro de diálogo **Subir elemento multimedia**, introduzca el título requerido y el texto alternativo.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-133">In the **Upload Media Item** dialog box, enter the required title and alt text.</span></span>
1. <span data-ttu-id="5b7cc-134">Introduzca la descripción opcional y las palabras clave y seleccione una categoría si lo desea.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-134">Enter optional description and keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="5b7cc-135">Si quiere publicar las imágenes inmediatamente después de la carga, seleccione la casilla de verificación **Publicar elementos multimedia después de subir**.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-135">If you want to publish the image(s) immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="5b7cc-136">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-136">Select **OK**.</span></span>

## <a name="upload-a-folder-of-images"></a><span data-ttu-id="5b7cc-137">Subir una carpeta de imágenes</span><span class="sxs-lookup"><span data-stu-id="5b7cc-137">Upload a folder of images</span></span>

<span data-ttu-id="5b7cc-138">Para subir en masa una carpeta de imágenes en el generador de sitios, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-138">To bulk upload a folder of images in site builder, follow these steps.</span></span>

1. <span data-ttu-id="5b7cc-139">En el panel de navegación izquierdo, seleccione **Biblioteca multimedia**.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-139">In the left navigation pane, select **Media Library**.</span></span>
1. <span data-ttu-id="5b7cc-140">En la barra de comandos, seleccione **Subir \> Subir carpeta**.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-140">On the command bar, select **Upload \> Upload Folder**.</span></span>
1. <span data-ttu-id="5b7cc-141">En la ventana del Explorador de archivos, navegue y una carpeta para cargar, y luego seleccione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-141">In the File Explorer window, navigate to and select a folder to upload, and then select **Open**.</span></span>
1. <span data-ttu-id="5b7cc-142">En el cuadro de diálogo **Subir elementos multimedia**, introduzca palabras clave opcionales y seleccione una categoría si lo desea.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-142">In the **Upload Media Items** dialog box, enter optional keywords and select a category if desired.</span></span> 
1. <span data-ttu-id="5b7cc-143">Si quiere publicar las imágenes en la carpeta inmediatamente después de la carga, seleccione la casilla de verificación **Publicar elementos multimedia después de subir**.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-143">If you want to publish the images in the folder immediately after upload, select the **Publish media items after upload** check box.</span></span>
1. <span data-ttu-id="5b7cc-144">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="5b7cc-144">Select **OK**.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5b7cc-145">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="5b7cc-145">Additional resources</span></span>

[<span data-ttu-id="5b7cc-146">Visión general de la administración de activos digitales</span><span class="sxs-lookup"><span data-stu-id="5b7cc-146">Digital asset management overview</span></span>](dam-overview.md)

[<span data-ttu-id="5b7cc-147">Cargar vídeo</span><span class="sxs-lookup"><span data-stu-id="5b7cc-147">Upload video</span></span>](dam-upload-video.md)

[<span data-ttu-id="5b7cc-148">Subir archivos</span><span class="sxs-lookup"><span data-stu-id="5b7cc-148">Upload files</span></span>](dam-upload-files.md)

[<span data-ttu-id="5b7cc-149">Recortar imágenes</span><span class="sxs-lookup"><span data-stu-id="5b7cc-149">Crop images</span></span>](dam-crop-images.md)

[<span data-ttu-id="5b7cc-150">Personalizar puntos focales de imagen</span><span class="sxs-lookup"><span data-stu-id="5b7cc-150">Customize image focal points</span></span>](dam-custom-focal-point.md)

[<span data-ttu-id="5b7cc-151">Cargar y servir archivos estáticos</span><span class="sxs-lookup"><span data-stu-id="5b7cc-151">Upload and serve static files</span></span>](upload-serve-static-files.md)
