---
title: Módulo de carro
description: En este tema se tratan los módulos de carro y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 12/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: abb9909c03577763ff7e6242c9395a58159df6ca
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985988"
---
# <a name="cart-module"></a><span data-ttu-id="ca1c2-103">Módulo de carro</span><span class="sxs-lookup"><span data-stu-id="ca1c2-103">Cart module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ca1c2-104">En este tema se tratan los módulos de carro y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-104">This topic covers cart modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="ca1c2-105">Información general</span><span class="sxs-lookup"><span data-stu-id="ca1c2-105">Overview</span></span>

<span data-ttu-id="ca1c2-106">Un módulo de carro muestra los artículos que se han agregado al carro antes de que el cliente finalice la compra.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-106">A cart module shows the items that have been added to the cart before the customer proceeds to checkout.</span></span> <span data-ttu-id="ca1c2-107">El módulo también muestra un resumen del pedido y permite al cliente aplicar o quitar códigos promocionales.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-107">The module also shows an order summary and lets the customer apply or remove promotional codes.</span></span>

<span data-ttu-id="ca1c2-108">El módulo de carro permite finalizar la compra como usuario que ha iniciado sesión o como usuario invitado.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-108">The cart module supports signed-in checkout and guest checkout.</span></span> <span data-ttu-id="ca1c2-109">También admite un vínculo **Volver a la compra**.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-109">It also supports a **Back to shopping** link.</span></span> <span data-ttu-id="ca1c2-110">Puede configurar la ruta para este vínculo en **Valores de configuración de sitio \> Extensiones \> Rutas**.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-110">You can configure the route for this link at **Site Settings \> Extensions \> Routes**.</span></span>

<span data-ttu-id="ca1c2-111">El módulo de carrito procesa los datos en función de la ID del carrito, que es una cookie del navegador disponible en todo el sitio.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-111">The cart module renders data based on the cart ID, which is a browser cookie available throughout the site.</span></span> 

<span data-ttu-id="ca1c2-112">La siguiente imagen muestra un ejemplo de una página de carro en el sitio Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-112">The following image shows an example of a cart page on the Fabrikam site.</span></span>

![Ejemplo de un módulo de carrito en el sitio de Fabrikam](./media/cart2.PNG)

<span data-ttu-id="ca1c2-114">La siguiente imagen muestra un ejemplo de una página de carro en el sitio Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-114">The following image shows an example of a cart page on the Fabrikam site.</span></span> <span data-ttu-id="ca1c2-115">En este ejemplo, hay una cuota de manipulación para un artículo de línea.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-115">In this example, there is a handling fee for a line item.</span></span>

![Ejemplo de un módulo de carrito con una tarifa de manipulación para un artículo de línea](./media/ecommerce-handling-fee.png)

## <a name="cart-module-properties-and-slots"></a><span data-ttu-id="ca1c2-117">Franjas y propiedades del módulo del carro</span><span class="sxs-lookup"><span data-stu-id="ca1c2-117">Cart module properties and slots</span></span>

| <span data-ttu-id="ca1c2-118">Propiedad</span><span class="sxs-lookup"><span data-stu-id="ca1c2-118">Property</span></span> | <span data-ttu-id="ca1c2-119">Valores</span><span class="sxs-lookup"><span data-stu-id="ca1c2-119">Values</span></span> | <span data-ttu-id="ca1c2-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="ca1c2-120">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="ca1c2-121">Cabecera</span><span class="sxs-lookup"><span data-stu-id="ca1c2-121">Heading</span></span> | <span data-ttu-id="ca1c2-122">Texto de encabezado y etiqueta de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**)</span><span class="sxs-lookup"><span data-stu-id="ca1c2-122">Heading text and a heading tag (**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**)</span></span> | <span data-ttu-id="ca1c2-123">El encabezado del carro, como "Bolsa de compra" o "Artículos en el carro".</span><span class="sxs-lookup"><span data-stu-id="ca1c2-123">A heading for the cart, such as "Shopping bag" or "Items in your cart."</span></span> |
| <span data-ttu-id="ca1c2-124">Mostrar errores de existencias agotadas</span><span class="sxs-lookup"><span data-stu-id="ca1c2-124">Show out of stock errors</span></span> | <span data-ttu-id="ca1c2-125">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="ca1c2-125">**True** or **False**</span></span> | <span data-ttu-id="ca1c2-126">Si esta propiedad se establece en **Verdadero**, la página del carro mostrará errores relacionados con las existencias.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-126">If this property is set to **True**, the cart page will show stock-related errors.</span></span> <span data-ttu-id="ca1c2-127">Le recomendamos que establezca esta propiedad en **Verdadero** si se aplican controles de inventario en el sitio.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-127">We recommend that you set this property to **True** if inventory checks are applied on the site.</span></span> |
| <span data-ttu-id="ca1c2-128">Mostrar gastos de envío para artículos de línea</span><span class="sxs-lookup"><span data-stu-id="ca1c2-128">Show shipping charges for line items</span></span> | <span data-ttu-id="ca1c2-129">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="ca1c2-129">**True** or **False**</span></span> | <span data-ttu-id="ca1c2-130">Si esta propiedad se establece en **Verdadero**, las líneas de pedido del carro mostrarán los gastos de envío, si esta información está disponible.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-130">If this property is set to **True**, cart line items will show the shipping charges, if this information is available.</span></span> <span data-ttu-id="ca1c2-131">Esta característica no es compatible con el tema Fabrikam porque los usuarios seleccionan el envío solo en el flujo de finalización de compra.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-131">This feature isn't supported in the Fabrikam theme, because users select shipping only in the checkout flow.</span></span> <span data-ttu-id="ca1c2-132">Sin embargo, esta característica se puede activar en otros flujos de trabajo, si corresponde.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-132">However, this feature can be turned on in other workflows if it's applicable.</span></span> |
| <span data-ttu-id="ca1c2-133">Mostrar promociones disponibles</span><span class="sxs-lookup"><span data-stu-id="ca1c2-133">Show available promotions</span></span>| <span data-ttu-id="ca1c2-134">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="ca1c2-134">**True** or **False**</span></span> | <span data-ttu-id="ca1c2-135">Si esta propiedad se establece en **Verdadero**, el carrito muestra las promociones disponibles, según los artículos del carrito.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-135">If this property is set to **True**, the cart shows available promotions, based on items in the cart.</span></span> <span data-ttu-id="ca1c2-136">Esta capacidad solo está disponible en la versión 10.0.16 de Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-136">This capability is available in the Dynamics 365 Commerce 10.0.16 release.</span></span> |

## <a name="modules-that-can-be-used-in-a-cart-module"></a><span data-ttu-id="ca1c2-137">Módulos que se pueden usar en un módulo de carro</span><span class="sxs-lookup"><span data-stu-id="ca1c2-137">Modules that can be used in a cart module</span></span>

- <span data-ttu-id="ca1c2-138">**Bloque de texto**: este módulo admite mensajería personalizada en el módulo de carro.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-138">**Text block** – This module supports custom messaging in the cart module.</span></span> <span data-ttu-id="ca1c2-139">Los mensajes se controlan mediante el sistema de gestión de contenidos (CMS).</span><span class="sxs-lookup"><span data-stu-id="ca1c2-139">The messages are driven by the content management system (CMS).</span></span> <span data-ttu-id="ca1c2-140">Se puede agregar cualquier mensaje, como “Si hubiera algún problema con el pedido, póngase en contacto con 1-800-Fabrikam”.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-140">Any message can be added, such as "For issues with your order, contact 1-800-Fabrikam."</span></span>
- <span data-ttu-id="ca1c2-141">**Selector de tienda**: este módulo muestra una lista de las tiendas cercanas en las que un artículo está disponible para su recogida.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-141">**Store selector** – This module shows a list of nearby stores where an item is available for pickup.</span></span> <span data-ttu-id="ca1c2-142">Permite a los usuarios especificar una ubicación para encontrar tiendas cercanas.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-142">It lets users enter a location to find stores that are nearby.</span></span> <span data-ttu-id="ca1c2-143">Para obtener más información sobre este módulo, consulte [Módulo selector de tienda](store-selector.md).</span><span class="sxs-lookup"><span data-stu-id="ca1c2-143">For more information on this module, see [Store selector module](store-selector.md).</span></span>

## <a name="module-properties"></a><span data-ttu-id="ca1c2-144">Propiedades del módulo</span><span class="sxs-lookup"><span data-stu-id="ca1c2-144">Module properties</span></span>

<span data-ttu-id="ca1c2-145">Las siguientes opciones de cmódulo de carro pueden configurarse en **Configuración de sitio \> Extensiones**:</span><span class="sxs-lookup"><span data-stu-id="ca1c2-145">The following cart module settings can be configured at **Site Settings \> Extensions**:</span></span>

- <span data-ttu-id="ca1c2-146">**Cantidad máxima**: esta propiedad se usa para especificar el número máximo de cada artículo que se puede agregar al carro.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-146">**Maximum quantity** – This property is used to specify the maximum number of each item that can be added to the cart.</span></span> <span data-ttu-id="ca1c2-147">Por ejemplo, un minorista puede decidir si solo 10 de cada producto se pueden vender en una única transacción.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-147">For example, a retailer might decide that only 10 of each product can be sold in a single transaction.</span></span>
- <span data-ttu-id="ca1c2-148">**Inventario**: para obtener información sobre cómo aplicar la configuración de inventario, consulte [Aplicar configuración de inventario](inventory-settings.md).</span><span class="sxs-lookup"><span data-stu-id="ca1c2-148">**Inventory** – For information about how to apply inventory settings, see [Apply inventory settings](inventory-settings.md).</span></span>
- <span data-ttu-id="ca1c2-149">**Volver a la compra**: esta propiedad se utiliza para especificar la ruta para el vínculo **Volver a la compra**.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-149">**Back to shopping** – This property is used to specify the route for the **Back to shopping** link.</span></span> <span data-ttu-id="ca1c2-150">La ruta se puede configurar a nivel de sitio, lo que permite a los minoristas llevar al cliente de vuelta a la página de inicio o cualquier otra página del sitio.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-150">The route can be configured at the site level, allowing retailers to take the customer back to the home page or any other page on the site.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ca1c2-151">En la versión Dynamics 365 Commerce 10.0.14 y posteriores, los artículos del carro se agregan en función de la configuración definida en el perfil de funcionalidad en línea para la tienda en línea en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-151">In the Dynamics 365 Commerce 10.0.14 release and later, items in the cart are aggregated based on the settings that are defined in the online functionality profile for the online store in Commerce headquarters.</span></span> <span data-ttu-id="ca1c2-152">Para obtener más información sobre cómo crear un perfil de funcionalidad en línea y establecer las propiedades necesarias para la agregación, consulte [Crear un perfil de funcionalidad en línea](online-functionality-profile.md).</span><span class="sxs-lookup"><span data-stu-id="ca1c2-152">For more information about how to create an online functionality profile and set the properties that are required for aggregation, see [Create an online functionality profile](online-functionality-profile.md).</span></span>

## <a name="commerce-scale-unit-interaction"></a><span data-ttu-id="ca1c2-153">Interacción con Commerce Scale Unit</span><span class="sxs-lookup"><span data-stu-id="ca1c2-153">Commerce Scale Unit interaction</span></span>

<span data-ttu-id="ca1c2-154">El módulo del carro recupera la información de producto mediante las API de Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-154">The cart module retrieves product information by using Commerce Scale Unit APIs.</span></span> <span data-ttu-id="ca1c2-155">El id. del carro de la cookie del explorador se utiliza para recuperar toda la información de producto de Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-155">The cart ID from the browser cookie is used to retrieve all the product information from Commerce Scale Unit.</span></span>

## <a name="add-a-cart-module-to-a-page"></a><span data-ttu-id="ca1c2-156">Agregar un módulo de carro a una página</span><span class="sxs-lookup"><span data-stu-id="ca1c2-156">Add a cart module to a page</span></span>

<span data-ttu-id="ca1c2-157">Para agregar un módulo de carro a una página nueva y establecer las propiedades necesarias, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-157">To add a cart module to a new page and set the required properties, follow these steps.</span></span>

1. <span data-ttu-id="ca1c2-158">Vaya a **Fragmentos** y seleccione **Nuevo** para crear un nuevo fragmento.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-158">Go to **Fragments**, and select **New** to create a new fragment.</span></span>
1. <span data-ttu-id="ca1c2-159">En el cuadro de diálogo **Nuevo fragmento**, seleccione el módulo **Carrito**.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-159">In the **New fragment** dialog box, select the **Cart** module.</span></span>
1. <span data-ttu-id="ca1c2-160">En **Nombre del fragmento**, introduzca el nombre **Fragmento de carro** y luego seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-160">Under **Fragment name**, enter the name **Cart fragment**, and then select **OK**.</span></span>
1. <span data-ttu-id="ca1c2-161">Seleccione el espacio **Carro**.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-161">Select the **Cart** slot.</span></span>
1. <span data-ttu-id="ca1c2-162">En el panel de propiedades de la derecha, seleccione el símbolo del lápiz, introduzca el texto del encabezado en el campo y luego seleccione el símbolo de marca de verificación.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-162">In the properties pane on the right, select the pencil symbol, enter heading text in the field, and then select the check mark symbol.</span></span>
1. <span data-ttu-id="ca1c2-163">En el espacio **Carro**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-163">In the **Cart** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="ca1c2-164">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Selector de tienda** y elija **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-164">In the **Add Module** dialog box, select the **Store selector** module, and then select **OK**.</span></span>
1. <span data-ttu-id="ca1c2-165">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger el fragmento y luego seleccione **Publicar** para publicarlo.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-165">Select **Save**, select **Finish editing** to check in the fragment, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="ca1c2-166">Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-166">Go to **Templates**, and select **New** to create a new template.</span></span>
1. <span data-ttu-id="ca1c2-167">En el cuadro de diálogo **Nueva plantilla**, en **Nombre de plantilla**, introduzca un nombre para la plantilla.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-167">In the **New Template** dialog box, under **Template name**, enter a name for the template.</span></span>
1. <span data-ttu-id="ca1c2-168">En el árbol de esquema, seleccione el espacio **Cuerpo**, luego los puntos suspensivos (**...**) y, a continuación, **Agregar fragmento**.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-168">In the outline tree, select the **Body** slot, select the ellipsis (**...**), and then select **Add fragment**.</span></span>
1. <span data-ttu-id="ca1c2-169">En el cuadro de diálogo **Seleccionar fragmento**, seleccione el fragmento **Fragmento de carro** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-169">In the **Select fragment** dialog box, select the **Cart fragment** fragment, and then select **OK**.</span></span>
1. <span data-ttu-id="ca1c2-170">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-170">Select **Save**, select **Finish editing** to check in the template, and then select **Publish** to publish it.</span></span>
1. <span data-ttu-id="ca1c2-171">Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-171">Go to **Pages**, and select **New** to create a new page.</span></span>
1. <span data-ttu-id="ca1c2-172">En el cuadro de diálogo **Elegir una plantilla**, seleccione la plantilla creada anteriormente, introduzca un nombre de página y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-172">In the **Choose a template** dialog box, select the template that you created, enter a page name, and then select **OK**.</span></span>
1. <span data-ttu-id="ca1c2-173">Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-173">Select **Save**, and then select **Preview** to preview the page.</span></span>
1. <span data-ttu-id="ca1c2-174">Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="ca1c2-174">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ca1c2-175">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="ca1c2-175">Additional resources</span></span>

[<span data-ttu-id="ca1c2-176">Módulo de icono de carro</span><span class="sxs-lookup"><span data-stu-id="ca1c2-176">Cart icon module</span></span>](cart-icon-module.md)

[<span data-ttu-id="ca1c2-177">Módulo de finalización de compra</span><span class="sxs-lookup"><span data-stu-id="ca1c2-177">Checkout module</span></span>](add-checkout-module.md)

[<span data-ttu-id="ca1c2-178">Módulo de pago</span><span class="sxs-lookup"><span data-stu-id="ca1c2-178">Payment module</span></span>](payment-module.md)

[<span data-ttu-id="ca1c2-179">Módulo de dirección de envío</span><span class="sxs-lookup"><span data-stu-id="ca1c2-179">Shipping address module</span></span>](ship-address-module.md)

[<span data-ttu-id="ca1c2-180">Módulo de opciones de entrega</span><span class="sxs-lookup"><span data-stu-id="ca1c2-180">Delivery options module</span></span>](delivery-options-module.md)

[<span data-ttu-id="ca1c2-181">Módulo de información de recogida</span><span class="sxs-lookup"><span data-stu-id="ca1c2-181">Pickup information module</span></span>](pickup-info-module.md)

[<span data-ttu-id="ca1c2-182">Módulo de detalles del pedido</span><span class="sxs-lookup"><span data-stu-id="ca1c2-182">Order details module</span></span>](order-confirmation-module.md)

[<span data-ttu-id="ca1c2-183">Módulo de tarjeta de regalo</span><span class="sxs-lookup"><span data-stu-id="ca1c2-183">Gift card module</span></span>](add-giftcard.md)

[<span data-ttu-id="ca1c2-184">Calcular la disponibilidad de inventario para canales comerciales</span><span class="sxs-lookup"><span data-stu-id="ca1c2-184">Calculate inventory availability for retail channels</span></span>](calculated-inventory-retail-channels.md)

[<span data-ttu-id="ca1c2-185">Crear un perfil de funcionalidad en línea</span><span class="sxs-lookup"><span data-stu-id="ca1c2-185">Create an online functionality profile</span></span>](online-functionality-profile.md)
