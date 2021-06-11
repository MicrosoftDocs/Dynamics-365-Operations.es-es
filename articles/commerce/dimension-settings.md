---
title: Aplicar la configuración de visualización para las dimensiones del producto
description: Este tema cubre la configuración de pantalla para las dimensiones del producto y describe cómo aplicarlas en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b901622bbfc8d6b3066879f6456a4ab618ca4076
ms.sourcegitcommit: 53b797ff1b524f581046b48cdde42f50b37495bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/28/2021
ms.locfileid: "6117245"
---
# <a name="apply-display-settings-for-product-dimensions"></a><span data-ttu-id="79526-103">Aplicar la configuración de visualización para las dimensiones del producto</span><span class="sxs-lookup"><span data-stu-id="79526-103">Apply display settings for product dimensions</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="79526-104">Este tema cubre la configuración de pantalla para las dimensiones del producto y describe cómo aplicarlas en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="79526-104">This topic covers the display settings for product dimensions and describes how to apply them in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="79526-105">Dynamics 365 Commerce admite el uso de dimensiones de tamaño, estilo y color para distinguir variantes de productos.</span><span class="sxs-lookup"><span data-stu-id="79526-105">Dynamics 365 Commerce supports size, style, and color dimensions to distinguish product variants.</span></span> <span data-ttu-id="79526-106">Las dimensiones se muestran normalmente como valores de texto, como "Pequeño", "Mediano" y "Grande" para los tamaños y "Negro" y "Marrón" para los colores.</span><span class="sxs-lookup"><span data-stu-id="79526-106">Dimensions are typically shown as text values, such as "Small," "Medium," and "Large" for sizes, and "Black" and "Brown" for colors.</span></span> <span data-ttu-id="79526-107">Sin embargo, si un producto admite muchas variaciones, puede ser difícil examinar variantes, porque se requieren varias selecciones para ver la imagen de cada variante.</span><span class="sxs-lookup"><span data-stu-id="79526-107">However, if a product supports many variations, it can be difficult to browse product variants, because multiple selections are required to view the image for each variant.</span></span> <span data-ttu-id="79526-108">Para facilitar la búsqueda de variantes de productos, la versión 10.0.20 de Commerce puede usar imágenes y códigos hexadecimales (hex) para mostrar las dimensiones como muestras.</span><span class="sxs-lookup"><span data-stu-id="79526-108">To make it easier to browse product variants, the version 10.0.20 release of Commerce can use images and hexadecimal (hex) codes to show dimensions as swatches.</span></span>

<span data-ttu-id="79526-109">En el creador de sitios de Commerce, la configuración del inventario se define en **Configuración del sitio \> Extensiones \> Configuración de dimensión**.</span><span class="sxs-lookup"><span data-stu-id="79526-109">In Commerce site builder, dimension settings are defined at **Site Settings \> Extensions \> Dimension Settings**.</span></span> <span data-ttu-id="79526-110">La siguiente ilustración muestra un ejemplo de configuración de dimensiones en el creador de sitios.</span><span class="sxs-lookup"><span data-stu-id="79526-110">The following illustration shows an example of dimension settings in site builder.</span></span>

![Ejemplo de configuración del sitio en el creador de sitios de Commerce](./dev-itpro/media/swatch_site_settings.PNG)

<span data-ttu-id="79526-112">Hay dos configuraciones de dimensión disponibles:</span><span class="sxs-lookup"><span data-stu-id="79526-112">Two dimension settings are available:</span></span>

- <span data-ttu-id="79526-113">**Dimensiones para mostrar como imagen**: especifique qué dimensiones deben aparecer como muestras en las páginas del sitio de comercio electrónico, como las páginas de detalles del producto (PDP) y las páginas de la lista de resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="79526-113">**Dimensions to display as image** – Specify which dimensions should appear as swatches on e-commerce site pages such as product details pages (PDPs) and search result list pages.</span></span> <span data-ttu-id="79526-114">Cualquier combinación de dimensiones de color, tamaño y estilo se puede mostrar como muestra.</span><span class="sxs-lookup"><span data-stu-id="79526-114">Any combination of color, size, and style dimensions can be shown as a swatch.</span></span> <span data-ttu-id="79526-115">Si se selecciona una dimensión para mostrarla como muestra, la representación del módulo de Commerce buscará una configuración disponible de una muestra de código hexadecimal.</span><span class="sxs-lookup"><span data-stu-id="79526-115">If a dimension is selected for display as a swatch, Commerce module rendering will look for an available configuration of a hex code swatch.</span></span> <span data-ttu-id="79526-116">Si no se configura ningún código hexadecimal, la lógica del sistema buscará una configuración de una muestra de URL de imagen.</span><span class="sxs-lookup"><span data-stu-id="79526-116">If no hex code is configured, system logic will look for a configuration of an image URL swatch.</span></span> <span data-ttu-id="79526-117">Si no se configura ni un código hexadecimal ni una URL de imagen, se mostrará texto.</span><span class="sxs-lookup"><span data-stu-id="79526-117">If neither a hex code nor an image URL is configured, text will be shown.</span></span>

    <span data-ttu-id="79526-118">La siguiente ilustración muestra un ejemplo en el que un PDP en un sitio de comercio electrónico incluye muestras de color y tamaño.</span><span class="sxs-lookup"><span data-stu-id="79526-118">The following illustration shows an example where a PDP on an e-commerce site includes color and size swatches.</span></span> <span data-ttu-id="79526-119">En este ejemplo, se configura un código hexadecimal para la dimensión de color.</span><span class="sxs-lookup"><span data-stu-id="79526-119">In this example, a hex code is configured for the color dimension.</span></span> <span data-ttu-id="79526-120">Por lo tanto, las muestras se muestran como colores.</span><span class="sxs-lookup"><span data-stu-id="79526-120">Therefore, swatches are shown as colors.</span></span> <span data-ttu-id="79526-121">Sin embargo, ni un código hexadecimal ni una URL de imagen están configurados para la dimensión de tamaño.</span><span class="sxs-lookup"><span data-stu-id="79526-121">However, neither a hex code nor an image URL is configured for the size dimension.</span></span> <span data-ttu-id="79526-122">Por tanto, se muestra texto.</span><span class="sxs-lookup"><span data-stu-id="79526-122">Therefore, text is shown.</span></span>

    ![Ejemplo de la dimensión de color que se muestra como muestras en una página de detalles de un producto de comercio electrónico](./dev-itpro/media/swatch_pdp.png)

- <span data-ttu-id="79526-124">**Dimensiones para mostrar en la ficha del producto**: especifique qué dimensiones deben aparecer en las tarjetas de productos que se muestran en las listas y en las páginas de listas.</span><span class="sxs-lookup"><span data-stu-id="79526-124">**Dimensions to display in product card** – Specify which dimensions should appear on product cards that are shown in lists and on list pages.</span></span> <span data-ttu-id="79526-125">Antes de que una dimensión pueda aparecer en una tarjeta de producto, esta configuración debe estar habilitada para esa dimensión.</span><span class="sxs-lookup"><span data-stu-id="79526-125">Before a dimension can appear on a product card, this setting must be enabled for that dimension.</span></span> <span data-ttu-id="79526-126">La configuración **Dimensiones para mostrar como imagen** también debe estar habilitada.</span><span class="sxs-lookup"><span data-stu-id="79526-126">The **Dimensions to display as image** setting should also be enabled.</span></span> <span data-ttu-id="79526-127">El comportamiento de selección de muestras en las tarjetas de productos está optimizado para la dimensión del color.</span><span class="sxs-lookup"><span data-stu-id="79526-127">The swatch selection behavior on product cards is optimized for the color dimension.</span></span> <span data-ttu-id="79526-128">Para otras dimensiones, es posible que se requiera una extensión de vista para personalizar el comportamiento de selección de muestras.</span><span class="sxs-lookup"><span data-stu-id="79526-128">For other dimensions, a view extension might be required to customize swatch selection behavior.</span></span>

    <span data-ttu-id="79526-129">La siguiente ilustración muestra un ejemplo en el que una página de lista en un sitio de comercio electrónico contiene tarjetas de productos que incluyen muestras de color.</span><span class="sxs-lookup"><span data-stu-id="79526-129">The following illustration shows an example where a list page on an e-commerce site contains product cards that include color swatches.</span></span>

    ![Ejemplo de la dimensión de color que se muestra como muestras en una página de lista de comercio electrónico](./dev-itpro/media/swatch_searchresults.PNG)

<span data-ttu-id="79526-131">Para obtener información sobre cómo configurar las dimensiones del producto para que se muestren como muestras en las páginas del sitio, consulte [Configurar los valores de las dimensiones del producto para que aparezcan como muestras](./dev-itpro/dimensions-swatch.md).</span><span class="sxs-lookup"><span data-stu-id="79526-131">For information about how to configure product dimensions so that they are shown as swatches on site pages, see [Configure product dimension values to appear as swatches](./dev-itpro/dimensions-swatch.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="79526-132">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="79526-132">Additional resources</span></span>

[<span data-ttu-id="79526-133">Descripción general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="79526-133">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="79526-134">Módulo de resultados de búsqueda</span><span class="sxs-lookup"><span data-stu-id="79526-134">Search results module</span></span>](search-result-module.md)

[<span data-ttu-id="79526-135">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="79526-135">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="79526-136">Configurar los valores de las dimensiones del producto para que aparezcan como muestras</span><span class="sxs-lookup"><span data-stu-id="79526-136">Configure product dimension values to appear as swatches</span></span>](./dev-itpro/dimensions-swatch.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
