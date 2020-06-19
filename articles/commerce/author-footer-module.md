---
title: Módulo de pie de página
description: En este tema se tratan los módulos de pie de página y cómo crearlos en Dynamics 365 Commerce.
author: anupamar
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: 87ffc0204019f2f7122c40dc21bdb5de012929d6
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411228"
---
# <a name="footer-module"></a><span data-ttu-id="f8564-103">Módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="f8564-103">Footer module</span></span>  

[!include [banner](includes/banner.md)]

<span data-ttu-id="f8564-104">En este tema se tratan los módulos de pie de página y se describe cómo crearlos en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f8564-104">This topic covers footer modules and describes how to create them in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="f8564-105">Visión general</span><span class="sxs-lookup"><span data-stu-id="f8564-105">Overview</span></span>

<span data-ttu-id="f8564-106">El módulo de pie de página es un contenedor especial que se usa para hospedar los módulos que aparecen en el pie de página.</span><span class="sxs-lookup"><span data-stu-id="f8564-106">The footer module is a special container that is used to host the modules that appear in the page footer.</span></span> <span data-ttu-id="f8564-107">Por ejemplo, puede incluir vínculos a las diversas páginas de todo el sitio, como las páginas **Ponerse en contacto con nosotros** y **Directivas de la tienda**.</span><span class="sxs-lookup"><span data-stu-id="f8564-107">For example, it can include links to various pages across the site, such as **Contact Us** and **Store Policies** pages.</span></span>

<span data-ttu-id="f8564-108">La siguiente imagen muestra un ejemplo de un módulo de pie de página en una página de sitio.</span><span class="sxs-lookup"><span data-stu-id="f8564-108">The following image shows an example of a footer module on a site page.</span></span>

![Ejemplo de módulo de pie de página](./media/ecommerce-footer.PNG)

## <a name="footer-module-properties"></a><span data-ttu-id="f8564-110">Propiedades del módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="f8564-110">Footer module properties</span></span> 

<span data-ttu-id="f8564-111">Como la mayoría de los contenedores, un módulo de pie de página admite propiedades para el encabezado y el ancho.</span><span class="sxs-lookup"><span data-stu-id="f8564-111">Like most containers, a footer module supports properties for the heading and the width.</span></span> <span data-ttu-id="f8564-112">También admite la adición de varios módulos de categoría de pie de página.</span><span class="sxs-lookup"><span data-stu-id="f8564-112">It also supports the addition of multiple footer category modules.</span></span> <span data-ttu-id="f8564-113">Cada módulo de categoría de pie de página que se agrega se representa como columna en el módulo de pie de página.</span><span class="sxs-lookup"><span data-stu-id="f8564-113">Each footer category module that is added is rendered as a column in the footer module.</span></span>

## <a name="modules-available-in-a-footer-module"></a><span data-ttu-id="f8564-114">Módulos disponibles en un módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="f8564-114">Modules available in a footer module</span></span>

<span data-ttu-id="f8564-115">**Elementos de pie de página**: un módulo de elementos de pie de página puede contener un encabezado, una imagen y un vínculo.</span><span class="sxs-lookup"><span data-stu-id="f8564-115">**Footer items** – A footer items module can contain a heading, an image, and a link.</span></span> <span data-ttu-id="f8564-116">El encabezado se puede usar solo o combinado con una imagen y un vínculo.</span><span class="sxs-lookup"><span data-stu-id="f8564-116">The heading can be used either alone or in combination with an image and a link.</span></span> <span data-ttu-id="f8564-117">Cada vínculo del pie de página se puede configurar para que tenga solo texto (por ejemplo, los vínculos “Ponerse en contacto con nosotros” y “Privacidad”), o de modo que tenga tanto texto e imagen (por ejemplo, vínculos de redes sociales).</span><span class="sxs-lookup"><span data-stu-id="f8564-117">Every link in the footer can be configured so that it has just text (for example, "Contact Us" and "Privacy" links), or so that it has both text and an image (for example, social media links).</span></span>

<span data-ttu-id="f8564-118">**Volver arriba**: Un módulo Volver arriba ofrece un vínculo de navegación rápida hasta la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="f8564-118">**Back to top** – A back to top module provides a link for quick navigation to the top of the page.</span></span> <span data-ttu-id="f8564-119">Es necesario un destino.</span><span class="sxs-lookup"><span data-stu-id="f8564-119">A destination is required.</span></span> <span data-ttu-id="f8564-120">El valor predeterminado de destino es \#, que lleva al usuario a la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="f8564-120">The default destination value is \#, which takes the user to the top of the page.</span></span>

## <a name="create-a-footer-module"></a><span data-ttu-id="f8564-121">Crear un módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="f8564-121">Create a footer module</span></span>

1. <span data-ttu-id="f8564-122">Vaya a **Fragmentos de página** y seleccione **Nuevo** para crear un nuevo fragmento.</span><span class="sxs-lookup"><span data-stu-id="f8564-122">Go to **Page Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="f8564-123">En el cuadro de diálogo **Nuevo fragmento de página**, seleccione el módulo **Contenedor**, especifique un nombre para el fragmento de la página y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f8564-123">In the **New Page Fragment** dialog box, select the **Container** module, enter a name for the page fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="f8564-124">En el espacio **Contenedor predeterminado**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="f8564-124">In the **Default container** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f8564-125">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Categoría de pie de página** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f8564-125">In the **Add Module** dialog box, select the **Footer category** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f8564-126">En el espacio **Categoría de pie de página**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="f8564-126">In the **Footer category** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="f8564-127">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Elemento de pie de página** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f8564-127">In the **Add Module** dialog box, select the **Footer item** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f8564-128">Seleccione el espacio **Elemento de pie de página** y luego, en el panel de propiedades de la derecha, configure el encabezado, el vínculo y el texto del vínculo, y la imagen según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f8564-128">Select the **Footer item** slot, and then, in the properties pane on the right, configure the heading, link and link text, and image as needed.</span></span>
1. <span data-ttu-id="f8564-129">Para agregar más elementos de pie de página, repita para cada uno los pasos del 5 al 7.</span><span class="sxs-lookup"><span data-stu-id="f8564-129">To add more footer items, repeat steps 5 through 7 for each.</span></span>
1. <span data-ttu-id="f8564-130">Para agregar un vínculo "Volver arriba" a su pie de página, seleccione los puntos suspensivos (**...**) en el módulo de categoría **Pie de página** y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="f8564-130">To add a "back to top" link to your footer, select the ellipsis (**...**) in the **Footer category** slot, and then select **Add Module**.</span></span>
1. <span data-ttu-id="f8564-131">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Volver arriba** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="f8564-131">In the **Add Module** dialog box, select the **Back to top** module, and then select **OK**.</span></span>
1. <span data-ttu-id="f8564-132">Seleccione el espacio **Volver arriba** y luego, en el panel de propiedades de la derecha, configure el texto y otras propiedades del módulo según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="f8564-132">Select the **Back to top** slot, and then, in the properties pane on the right, configure the text and other module properties as needed.</span></span>
1. <span data-ttu-id="f8564-133">Seleccione **Finalizar edición** para comprobar en el fragmento y luego seleccione **Publicar** para publicarlo.</span><span class="sxs-lookup"><span data-stu-id="f8564-133">Select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="f8564-134">Para ayudar a garantizar que un encabezado aparece en cada página, siga estos pasos de cada plantilla de página creada para el sitio.</span><span class="sxs-lookup"><span data-stu-id="f8564-134">To help guarantee that a header appears on every page, follow these steps on every page template that is created for the site.</span></span>

1. <span data-ttu-id="f8564-135">En el espacio **Pie de página** del módulo **Página predeterminada**, agregue el fragmento de pie de página que ha creado.</span><span class="sxs-lookup"><span data-stu-id="f8564-135">In the **Footer** slot of the **Default page** module, add the footer fragment that you created.</span></span>
1. <span data-ttu-id="f8564-136">Seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="f8564-136">Select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>

<span data-ttu-id="f8564-137">Al agregar el fragmento de página a plantillas de página, ayuda a garantizar que el pie de página se representa en cada página.</span><span class="sxs-lookup"><span data-stu-id="f8564-137">By adding the page fragment to page templates, you help guarantee that the footer is rendered on every page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="f8564-138">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="f8564-138">Additional resources</span></span>

[<span data-ttu-id="f8564-139">Visión general de kit de inicio</span><span class="sxs-lookup"><span data-stu-id="f8564-139">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="f8564-140">Módulo Contenedor</span><span class="sxs-lookup"><span data-stu-id="f8564-140">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="f8564-141">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="f8564-141">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="f8564-142">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="f8564-142">Cart module</span></span>](add-cart-module.md)

[<span data-ttu-id="f8564-143">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="f8564-143">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="f8564-144">Módulo de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="f8564-144">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="f8564-145">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="f8564-145">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="f8564-146">Módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="f8564-146">Footer module</span></span>](author-footer-module.md)
