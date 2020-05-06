---
title: Módulo de pie de página
description: En este tema se tratan los módulos de pie de página y cómo crearlos en Dynamics 365 Commerce.
author: anupamar
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
ms.author: anupamar-ms
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 51f8d26d6223dcd1f6961058cd9d772a67c69670
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269645"
---
# <a name="footer-module"></a><span data-ttu-id="86fa5-103">Módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="86fa5-103">Footer module</span></span>  


[!include [banner](includes/banner.md)]

<span data-ttu-id="86fa5-104">En este tema se tratan los módulos de pie de página y se describe cómo crearlos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="86fa5-104">This topic covers footer modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="86fa5-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="86fa5-105">Overview</span></span>

<span data-ttu-id="86fa5-106">El módulo de pie de página es un contenedor especial que se usa para hospedar los módulos que aparecen en el pie de página.</span><span class="sxs-lookup"><span data-stu-id="86fa5-106">The footer module is a special container that is used to host the modules that appear in the page footer.</span></span> <span data-ttu-id="86fa5-107">Por ejemplo, puede incluir vínculos a las diversas páginas de todo el sitio, como las páginas **Ponerse en contacto con nosotros** y **Directivas de la tienda**.</span><span class="sxs-lookup"><span data-stu-id="86fa5-107">For example, it can include links to various pages across the site, such as **Contact Us** and **Store Policies** pages.</span></span>

## <a name="footer-module-properties"></a><span data-ttu-id="86fa5-108">Propiedades del módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="86fa5-108">Footer module properties</span></span> 

<span data-ttu-id="86fa5-109">Como la mayoría de los contenedores, un módulo de pie de página admite propiedades para el encabezado y el ancho.</span><span class="sxs-lookup"><span data-stu-id="86fa5-109">Like most containers, a footer module supports properties for the heading and the width.</span></span> <span data-ttu-id="86fa5-110">También admite la adición de varios módulos de categoría de pie de página.</span><span class="sxs-lookup"><span data-stu-id="86fa5-110">It also supports the addition of multiple footer category modules.</span></span> <span data-ttu-id="86fa5-111">Cada módulo de categoría de pie de página que se agrega se representa como columna en el módulo de pie de página.</span><span class="sxs-lookup"><span data-stu-id="86fa5-111">Each footer category module that is added is rendered as a column in the footer module.</span></span>

## <a name="modules-available-in-a-footer-module"></a><span data-ttu-id="86fa5-112">Módulos disponibles en un módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="86fa5-112">Modules available in a footer module</span></span>

<span data-ttu-id="86fa5-113">**Elementos de pie de página**: un módulo de elementos de pie de página puede contener un encabezado, una imagen y un vínculo.</span><span class="sxs-lookup"><span data-stu-id="86fa5-113">**Footer items** – A footer items module can contain a heading, an image, and a link.</span></span> <span data-ttu-id="86fa5-114">El encabezado se puede usar solo o combinado con una imagen y un vínculo.</span><span class="sxs-lookup"><span data-stu-id="86fa5-114">The heading can be used either alone or in combination with an image and a link.</span></span> <span data-ttu-id="86fa5-115">Cada vínculo del pie de página se puede configurar para que tenga solo texto (por ejemplo, los vínculos “Ponerse en contacto con nosotros” y “Privacidad”), o de modo que tenga tanto texto e imagen (por ejemplo, vínculos de redes sociales).</span><span class="sxs-lookup"><span data-stu-id="86fa5-115">Every link in the footer can be configured so that it has just text (for example, "Contact Us" and "Privacy" links), or so that it has both text and an image (for example, social media links).</span></span>

<span data-ttu-id="86fa5-116">**Volver arriba**: Un módulo Volver arriba ofrece un vínculo de navegación rápida hasta la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="86fa5-116">**Back to top** – A back to top module provides a link for quick navigation to the top of the page.</span></span> <span data-ttu-id="86fa5-117">Es necesario un destino.</span><span class="sxs-lookup"><span data-stu-id="86fa5-117">A destination is required.</span></span> <span data-ttu-id="86fa5-118">El valor predeterminado de destino es #, que lleva al usuario a la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="86fa5-118">The default destination value is #, which takes the user to the top of the page.</span></span>

## <a name="author-a-footer-module"></a><span data-ttu-id="86fa5-119">Crear un módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="86fa5-119">Author a footer module</span></span>

1. <span data-ttu-id="86fa5-120">En el panel de navegación, seleccione **Fragmentos** y después seleccione **Nuevo fragmento de página**.</span><span class="sxs-lookup"><span data-stu-id="86fa5-120">In the navigation pane, select **Fragments**, and then select **New Page Fragment**.</span></span>
1. <span data-ttu-id="86fa5-121">En el cuadro de diálogo **Nuevo fragmento de página**, seleccione el módulo de pie de página, especifique un nombre para el fragmento de la página y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="86fa5-121">In the **New Page Fragment** dialog box, select the footer module, enter a name for the page fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="86fa5-122">En el árbol de esquema de la izquierda, seleccione el botón de puntos suspensivos (**...**) para el módulo de pie de página y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="86fa5-122">In the outline tree on the left, select the ellipsis button (**...**) for the footer module, and then select **Add Module**.</span></span>
1. <span data-ttu-id="86fa5-123">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo de categoría de pie de página y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="86fa5-123">In the **Add Module** dialog box, select the footer category module, and then select **OK**.</span></span>
1. <span data-ttu-id="86fa5-124">En el árbol de esquema de la izquierda, seleccione el botón de puntos suspensivos para el módulo de categoría de pie de página y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="86fa5-124">In the outline tree, select the ellipsis button for the footer category module, and then select **Add Module**.</span></span>
1. <span data-ttu-id="86fa5-125">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo de elemento de pie de página y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="86fa5-125">In the **Add Module** dialog box, select the footer item module, and then select **OK**.</span></span>
1. <span data-ttu-id="86fa5-126">En el esquema de árbol, seleccione el módulo de elemento de pie de página.</span><span class="sxs-lookup"><span data-stu-id="86fa5-126">In the outline tree, select the footer item module.</span></span> <span data-ttu-id="86fa5-127">A continuación, en el panel de propiedades de la derecha, configure el encabezado, el vínculo y el texto del vínculo, y la imagen según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="86fa5-127">Then, in the properties pane on the right, configure the heading, link and link text, and image as you require.</span></span>
1. <span data-ttu-id="86fa5-128">Para agregar más elementos de pie de página, repita los pasos del 5 al 7.</span><span class="sxs-lookup"><span data-stu-id="86fa5-128">To add more footer items, repeat steps 5 through 7.</span></span>
1. <span data-ttu-id="86fa5-129">Para agregar un vínculo "Volver arriba" a su pie de página, seleccione el botón de puntos suspensivos para el módulo de categoría de pie de página y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="86fa5-129">To add a "back to top" link to your footer, select the ellipsis button for the footer category module, and then select **Add Module**.</span></span>
1. <span data-ttu-id="86fa5-130">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo Volver arriba y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="86fa5-130">In the **Add Module** dialog box, select the back to top module, and then select **OK**.</span></span>
1. <span data-ttu-id="86fa5-131">En el esquema de árbol, seleccione el módulo Volver arriba.</span><span class="sxs-lookup"><span data-stu-id="86fa5-131">In the outline tree, select the back to top module.</span></span> <span data-ttu-id="86fa5-132">A continuación, en el panel de propiedades de la derecha, configure el módulo Volver arriba según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="86fa5-132">Then, in the properties pane on the right, configure the back to top module as you require.</span></span>
1. <span data-ttu-id="86fa5-133">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger el fragmento de página y luego seleccione **Publicar** para publicarlo.</span><span class="sxs-lookup"><span data-stu-id="86fa5-133">Select **Save**, select **Finish editing** to check in the page fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="86fa5-134">En cada plantilla de página que se ha creado para el sitio, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="86fa5-134">On every page template that has been created for the site, follow these steps.</span></span>

1. <span data-ttu-id="86fa5-135">En la franja **Principal** de la página predeterminada, en el módulo de pie de página, agregue el fragmento de pie de página que ha creado.</span><span class="sxs-lookup"><span data-stu-id="86fa5-135">In the **Main** slot of the default page, in the footer module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="86fa5-136">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="86fa5-136">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="86fa5-137">Al agregar el fragmento de página a plantillas de página, ayuda a garantizar que el pie de página se representa en cada página.</span><span class="sxs-lookup"><span data-stu-id="86fa5-137">By adding the page fragment to page templates, you help guarantee that the footer is rendered on every page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="86fa5-138">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="86fa5-138">Additional resources</span></span>

[<span data-ttu-id="86fa5-139">Visión general de kit de inicio</span><span class="sxs-lookup"><span data-stu-id="86fa5-139">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="86fa5-140">Módulo Contenedor</span><span class="sxs-lookup"><span data-stu-id="86fa5-140">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="86fa5-141">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="86fa5-141">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="86fa5-142">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="86fa5-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="86fa5-143">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="86fa5-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="86fa5-144">Módulo de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="86fa5-144">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="86fa5-145">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="86fa5-145">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="86fa5-146">Módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="86fa5-146">Footer module</span></span>](author-footer-module.md)
