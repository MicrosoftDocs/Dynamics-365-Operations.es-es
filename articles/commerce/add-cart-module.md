---
title: Módulo de carro
description: En este tema se tratan los módulos de carro y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3ba46fd90507a9cf8da92598c8449a2e553da352
ms.sourcegitcommit: b52477b7d0d52102a7ca2fb95f4ebfa30ecd9f54
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/29/2020
ms.locfileid: "3411282"
---
# <a name="cart-module"></a><span data-ttu-id="ff754-103">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="ff754-103">Cart module</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="ff754-104">En este tema se tratan los módulos de carro y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ff754-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ff754-105">Información general</span><span class="sxs-lookup"><span data-stu-id="ff754-105">Overview</span></span>

<span data-ttu-id="ff754-106">Un módulo de carro muestra los artículos que se han agregado al carro antes de que el cliente finalice la compra.</span><span class="sxs-lookup"><span data-stu-id="ff754-106">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="ff754-107">El módulo también muestra un resumen del pedido y permite al cliente aplicar o quitar códigos promocionales.</span><span class="sxs-lookup"><span data-stu-id="ff754-107">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="ff754-108">El módulo de carro permite finalizar la compra como usuario que ha iniciado sesión o como usuario invitado.</span><span class="sxs-lookup"><span data-stu-id="ff754-108">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="ff754-109">También admite un vínculo **Volver a la compra**.</span><span class="sxs-lookup"><span data-stu-id="ff754-109">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="ff754-110">Puede configurar la ruta para este vínculo en **Valores de configuración de sitio \> Extensiones \> Rutas**.</span><span class="sxs-lookup"><span data-stu-id="ff754-110">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="ff754-111">El módulo de carrito procesa los datos en función de la ID del carrito, que es una cookie del navegador disponible en todo el sitio.</span><span class="sxs-lookup"><span data-stu-id="ff754-111">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span> 

<span data-ttu-id="ff754-112">La siguiente imagen muestra un ejemplo de una página de carro en el sitio Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="ff754-112">The following image shows an example of a cart page on the Fabrikam site.</span></span>

![Ejemplo de un módulo de carro](./media/cart2.PNG)

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="ff754-114">Franjas y propiedades del módulo del carro</span><span class="sxs-lookup"><span data-stu-id="ff754-114">Cart module properties and slots</span></span>

<span data-ttu-id="ff754-115">El módulo de carro tiene una propiedad **Encabezado** que se puede establecer en valores como **Cesta de la compra** y **Artículos del carro**.</span><span class="sxs-lookup"><span data-stu-id="ff754-115">The cart module has a **Heading** property that can be set to values such as **Shopping bag** and **Items in your cart**.</span></span> 

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="ff754-116">Módulos que se pueden usar en un módulo de carro</span><span class="sxs-lookup"><span data-stu-id="ff754-116">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="ff754-117">**Bloque de texto**: este módulo admite mensajería personalizada en el módulo de carro.</span><span class="sxs-lookup"><span data-stu-id="ff754-117">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="ff754-118">Los mensajes se controlan mediante el sistema de gestión de contenidos (CMS).</span><span class="sxs-lookup"><span data-stu-id="ff754-118">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="ff754-119">Se puede agregar cualquier mensaje, como “Si hubiera algún problema con el pedido, póngase en contacto con 1-800-Fabrikam”.</span><span class="sxs-lookup"><span data-stu-id="ff754-119">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="ff754-120">**Selector de tienda**: este módulo muestra una lista de las tiendas cercanas en las que un artículo está disponible para su recogida.</span><span class="sxs-lookup"><span data-stu-id="ff754-120">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="ff754-121">Permite a los usuarios especificar una ubicación para encontrar tiendas cercanas.</span><span class="sxs-lookup"><span data-stu-id="ff754-121">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="ff754-122">Para obtener más información sobre este módulo, consulte [Módulo selector de tienda](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="ff754-122">For more information on this module, see [Store selector module](store-selector.md).</span></span>

## <a name="module-properties"></a><span data-ttu-id="ff754-123">Propiedades del módulo</span><span class="sxs-lookup"><span data-stu-id="ff754-123">Module properties</span></span>

<span data-ttu-id="ff754-124">Las siguientes opciones de cmódulo de carro pueden configurarse en **Configuración de sitio \> Extensiones**:</span><span class="sxs-lookup"><span data-stu-id="ff754-124">The following cart module settings can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="ff754-125">**Cantidad máxima**: esta propiedad se usa para especificar el número máximo de cada artículo que se puede agregar al carro.</span><span class="sxs-lookup"><span data-stu-id="ff754-125">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="ff754-126">Por ejemplo, un minorista puede decidir si solo 10 de cada producto se pueden vender en una única transacción.</span><span class="sxs-lookup"><span data-stu-id="ff754-126">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="ff754-127">**Inventario**: para obtener información sobre cómo aplicar la configuración de inventario, consulte [Aplicar configuración de inventario](inventory-settings.md).</span><span class="sxs-lookup"><span data-stu-id="ff754-127">**Inventory** – For information about how to apply inventory settings, see [Apply inventory settings](inventory-settings.md).</span></span>
- <span data-ttu-id="ff754-128">**Volver a la compra**: esta propiedad se utiliza para especificar la ruta para el vínculo **Volver a la compra**.</span><span class="sxs-lookup"><span data-stu-id="ff754-128">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="ff754-129">La ruta se puede configurar a nivel de sitio, lo que permite a los minoristas llevar al cliente de vuelta a la página de inicio o cualquier otra página del sitio.</span><span class="sxs-lookup"><span data-stu-id="ff754-129">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="ff754-130">Interacción con Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="ff754-130">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="ff754-131">El módulo del carro recupera la información de producto mediante las API de Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="ff754-131">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="ff754-132">El id. del carro de la cookie del explorador se utiliza para recuperar toda la información de producto de Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="ff754-132">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="ff754-133">Agregar un módulo de carro a una página</span><span class="sxs-lookup"><span data-stu-id="ff754-133">Add a cart module to a page</span></span>

<span data-ttu-id="ff754-134">Para agregar un módulo de carro a una página nueva y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ff754-134">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="ff754-135">Vaya a **Fragmentos de página** y seleccione **Nuevo** para crear un nuevo fragmento.</span><span class="sxs-lookup"><span data-stu-id="ff754-135">Go to **Page Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="ff754-136">En el cuadro de diálogo, **Nuevo fragmento de página**, seleccione el módulo **Carro**.</span><span class="sxs-lookup"><span data-stu-id="ff754-136">In the **New Page Fragment** dialog box, select the **Cart** module.</span></span>
1. <span data-ttu-id="ff754-137">En **Nombre del fragmento de página**, introduzca el nombre **Fragmento de carro** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff754-137">Under **Page Fragment Name**, enter the name **Cart fragment**, and then select **OK**.</span></span>
1. <span data-ttu-id="ff754-138">Seleccione el espacio **Carro**.</span><span class="sxs-lookup"><span data-stu-id="ff754-138">Select the **Cart** slot.</span></span>
1. <span data-ttu-id="ff754-139">En el panel de propiedades de la derecha, seleccione el símbolo del lápiz, introduzca el texto del encabezado en el campo y luego seleccione el símbolo de marca de verificación.</span><span class="sxs-lookup"><span data-stu-id="ff754-139">In the properties pane on the right, select the pencil symbol, enter heading text in the field, and then select the check mark symbol.</span></span>
1. <span data-ttu-id="ff754-140">En el espacio **Carro**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="ff754-140">In the **Cart** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="ff754-141">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Selector de tienda** y elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff754-141">In the **Add Module** dialog box, select the **Store selector** module, and then select **OK**.</span></span>
1. <span data-ttu-id="ff754-142">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger el fragmento y luego seleccione **Publicar** para publicarlo.</span><span class="sxs-lookup"><span data-stu-id="ff754-142">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="ff754-143">Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="ff754-143">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="ff754-144">En el cuadro de diálogo **Nueva plantilla**, en **Nombre de plantilla**, introduzca un nombre para la plantilla.</span><span class="sxs-lookup"><span data-stu-id="ff754-144">In the **New Template** dialog box, under **Template name**, enter a name for the template.</span></span>
1. <span data-ttu-id="ff754-145">En el árbol de esquema, seleccione el espacio **Cuerpo**, luego los puntos suspensivos (**...**) y, a continuación, **Agregar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="ff754-145">In the outline tree, select the **Body** slot, select the ellipsis (**...**), and then select **Add Fragment**.</span></span>
1. <span data-ttu-id="ff754-146">En el cuadro de diálogo **Seleccionar fragmento de página**, seleccione el fragmento **Fragmento de carro** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff754-146">In the **Select Page Fragment** dialog box, select the **Cart fragment** fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="ff754-147">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="ff754-147">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="ff754-148">Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.</span><span class="sxs-lookup"><span data-stu-id="ff754-148">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="ff754-149">En el cuadro de diálogo **Elegir una plantilla**, seleccione la plantilla creada anteriormente, introduzca un nombre de página y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ff754-149">In the **Choose a template** dialog box, select the template that you created, enter a page name, and then select **OK**.</span></span>
1. <span data-ttu-id="ff754-150">Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.</span><span class="sxs-lookup"><span data-stu-id="ff754-150">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="ff754-151">Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="ff754-151">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ff754-152">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ff754-152">Additional resources</span></span>

[<span data-ttu-id="ff754-153">Visión general del kit de inicio</span><span class="sxs-lookup"><span data-stu-id="ff754-153">Starter kit overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="ff754-154">Módulo Contenedor</span><span class="sxs-lookup"><span data-stu-id="ff754-154">Container module</span></span>](add-container-module.md)

[<span data-ttu-id="ff754-155">Módulo de selector de tienda</span><span class="sxs-lookup"><span data-stu-id="ff754-155">Store selector module</span></span>](store-selector.md)

[<span data-ttu-id="ff754-156">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="ff754-156">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="ff754-157">Módulo de icono de carrito</span><span class="sxs-lookup"><span data-stu-id="ff754-157">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="ff754-158">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="ff754-158">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="ff754-159">Módulo de confirmación de pedido</span><span class="sxs-lookup"><span data-stu-id="ff754-159">Order confirmation module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="ff754-160">Módulo de encabezado</span><span class="sxs-lookup"><span data-stu-id="ff754-160">Header module</span></span>](author-header-module.md)

[<span data-ttu-id="ff754-161">Módulo de pie de página</span><span class="sxs-lookup"><span data-stu-id="ff754-161">Footer module</span></span>](author-footer-module.md)

[<span data-ttu-id="ff754-162">Calcular la disponibilidad de inventario para canales comerciales</span><span class="sxs-lookup"><span data-stu-id="ff754-162">Calculate inventory availability for retail channels</span></span>](calculated-inventory-retail-channels.md)
