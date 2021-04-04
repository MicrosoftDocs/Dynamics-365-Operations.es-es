---
title: Módulo Compartir en redes sociales
description: En este tema se tratan los módulos de compartir en redes sociales y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.14
ms.openlocfilehash: 0e7f30686894f9cf92257e99d95cc8b00f76f899
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5234326"
---
# <a name="social-share-module"></a><span data-ttu-id="6da25-103">Módulo de compartir en redes sociales</span><span class="sxs-lookup"><span data-stu-id="6da25-103">Social share module</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="6da25-104">En este tema se tratan los módulos de compartir en redes sociales y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="6da25-104">This topic covers social share modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="6da25-105">Los módulos para compartir en redes sociales permiten a los usuarios compartir las direcciones URL de las páginas del sitio de comercio electrónico en las redes sociales, como Facebook, Twitter, Pinterest y LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="6da25-105">Social share modules allow users to share e-Commerce site page URLs on social media such as Facebook, Twitter, Pinterest, and LinkedIn.</span></span> <span data-ttu-id="6da25-106">Las direcciones URL de las páginas del sitio también se pueden compartir por correo electrónico.</span><span class="sxs-lookup"><span data-stu-id="6da25-106">Site page URLs can also be shared via email.</span></span> <span data-ttu-id="6da25-107">Los módulos para compartir en redes sociales se utilizan comúnmente en las páginas de detalles del producto (PDP) para ayudar a los usuarios a compartir información sobre el producto.</span><span class="sxs-lookup"><span data-stu-id="6da25-107">Social share modules are commonly used on product details pages (PDPs) to help users share product information.</span></span>

<span data-ttu-id="6da25-108">Cada módulo para compartir en redes sociales es un contenedor para los módulos de elementos para compartir en redes sociales.</span><span class="sxs-lookup"><span data-stu-id="6da25-108">Each social share module is a container for social share item modules.</span></span> <span data-ttu-id="6da25-109">Cada módulo de elementos para compartir en redes sociales se puede configurar para que apunte a un sitio de redes sociales específico.</span><span class="sxs-lookup"><span data-stu-id="6da25-109">Each social share item module can be configured to point to a specific social media site.</span></span> <span data-ttu-id="6da25-110">La integración con Facebook, Twitter, Pinterest, LinkedIn y el correo electrónico son compatibles desde el primer momento.</span><span class="sxs-lookup"><span data-stu-id="6da25-110">Integration with Facebook, Twitter, Pinterest, LinkedIn, and email is supported out of the box.</span></span> <span data-ttu-id="6da25-111">Cuando un usuario del sitio selecciona un símbolo de red social, se lanza un iframe HTML para el sitio de red social respectivo.</span><span class="sxs-lookup"><span data-stu-id="6da25-111">When a site user selects a social media symbol, an HTML iframe is launched for the respective social media site.</span></span> <span data-ttu-id="6da25-112">Dentro del iframe, el usuario puede iniciar sesión y publicar el contenido de la página que estaba viendo.</span><span class="sxs-lookup"><span data-stu-id="6da25-112">Within the iframe, the user can sign in and post the page content that they were viewing.</span></span>

<span data-ttu-id="6da25-113">Cada plataforma de redes sociales puede rastrear cookies, por lo que este módulo requiere que los usuarios del sitio acepten el mensaje de notificación de consentimiento de cookies.</span><span class="sxs-lookup"><span data-stu-id="6da25-113">Each social media platform may track cookies, so this module requires site users to accept the cookie consent notification message.</span></span> <span data-ttu-id="6da25-114">Cuando no se acepta el consentimiento de las cookies, el módulo se ocultará en la página.</span><span class="sxs-lookup"><span data-stu-id="6da25-114">When cookie consent is not accepted, the module will be hidden on the page.</span></span> <span data-ttu-id="6da25-115">Para obtener más información, consulte [Cumplimiento de las cookies](cookie-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="6da25-115">For more information, see [Cookie compliance](cookie-compliance.md).</span></span>

<span data-ttu-id="6da25-116">La siguiente ilustración destaca un ejemplo de un módulo para compartir en redes sociales utilizado en la página de detalles de un producto.</span><span class="sxs-lookup"><span data-stu-id="6da25-116">The following illustration highlights an example of a social share module used on a product details page.</span></span>

![Ejemplo de un módulo para compartir en redes sociales](./media/ecommerce-socialshare.png)

## <a name="social-share-module-properties"></a><span data-ttu-id="6da25-118">Propiedades del módulo Compartir en redes sociales</span><span class="sxs-lookup"><span data-stu-id="6da25-118">Social share module properties</span></span>

| <span data-ttu-id="6da25-119">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="6da25-119">Property name</span></span>             | <span data-ttu-id="6da25-120">Valor</span><span class="sxs-lookup"><span data-stu-id="6da25-120">Value</span></span>                 | <span data-ttu-id="6da25-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="6da25-121">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="6da25-122">Leyenda</span><span class="sxs-lookup"><span data-stu-id="6da25-122">Caption</span></span>                  | <span data-ttu-id="6da25-123">Texto</span><span class="sxs-lookup"><span data-stu-id="6da25-123">Text</span></span> | <span data-ttu-id="6da25-124">Esta propiedad especifica un título para el módulo.</span><span class="sxs-lookup"><span data-stu-id="6da25-124">This property specifies a caption for the module.</span></span> |
| <span data-ttu-id="6da25-125">Orientación</span><span class="sxs-lookup"><span data-stu-id="6da25-125">Orientation</span></span> | <span data-ttu-id="6da25-126">**Vertical** u **Horizontal**</span><span class="sxs-lookup"><span data-stu-id="6da25-126">**Horizontal** or **Vertical**</span></span>  | <span data-ttu-id="6da25-127">Esta propiedad define la orientación del diseño de los elementos de redes sociales.</span><span class="sxs-lookup"><span data-stu-id="6da25-127">This property defines the layout orientation for the social media items.</span></span> |

## <a name="social-share-item-module-properties"></a><span data-ttu-id="6da25-128">Propiedades del módulo del elemento Compartir en redes sociales</span><span class="sxs-lookup"><span data-stu-id="6da25-128">Social share item module properties</span></span>
| <span data-ttu-id="6da25-129">Nombre de la propiedad</span><span class="sxs-lookup"><span data-stu-id="6da25-129">Property name</span></span>             | <span data-ttu-id="6da25-130">Valor</span><span class="sxs-lookup"><span data-stu-id="6da25-130">Value</span></span>                 | <span data-ttu-id="6da25-131">Descripción</span><span class="sxs-lookup"><span data-stu-id="6da25-131">Description</span></span> |
|---------------------------|-----------------------|-------------|
| <span data-ttu-id="6da25-132">Redes sociales</span><span class="sxs-lookup"><span data-stu-id="6da25-132">Social media</span></span>              | <span data-ttu-id="6da25-133">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **Correo**</span><span class="sxs-lookup"><span data-stu-id="6da25-133">**Facebook**, **Twitter**, **Pinterest**, **LinkedIn**, **Mail**</span></span> | <span data-ttu-id="6da25-134">Un menú desplegable con una lista de plataformas de redes sociales.</span><span class="sxs-lookup"><span data-stu-id="6da25-134">A drop-down menu with a list of social media platforms.</span></span> |
| <span data-ttu-id="6da25-135">Icono</span><span class="sxs-lookup"><span data-stu-id="6da25-135">Icon</span></span> |<span data-ttu-id="6da25-136">Imagen</span><span class="sxs-lookup"><span data-stu-id="6da25-136">Image</span></span>    | <span data-ttu-id="6da25-137">Esta será la imagen que se mostrará para las respectivas redes sociales.</span><span class="sxs-lookup"><span data-stu-id="6da25-137">This will be the image that will be shown for the respective social media.</span></span> <span data-ttu-id="6da25-138">Como práctica recomendada, consulte el SDK de la plataforma de redes sociales para conocer la imagen recomendada para cada plataforma.</span><span class="sxs-lookup"><span data-stu-id="6da25-138">As a best practice, refer to the social media platform's SDK for the recommended image to use for each platform.</span></span> |

## <a name="add-a-social-share-module-to-a-buy-box-module"></a><span data-ttu-id="6da25-139">Agregar un módulo de compartir en redes sociales a un módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="6da25-139">Add a social share module to a buy box module</span></span>

<span data-ttu-id="6da25-140">Para agregar un módulo de compartir en redes sociales a un módulo de cuadro de compra, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="6da25-140">To add a social share module to a buy box module, follow these steps.</span></span>

1. <span data-ttu-id="6da25-141">En el sitio de Fabrikam, seleccione **Páginas** y luego seleccione la página **DefaultPDP** para abrir la página de detalles del producto.</span><span class="sxs-lookup"><span data-stu-id="6da25-141">In the Fabrikam site, select **Pages**, and then select the **DefaultPDP** page to open the product details page.</span></span> 
1. <span data-ttu-id="6da25-142">En el espacio **Cuadro de compra (obligatorio)**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="6da25-142">In the **Buybox (required)** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="6da25-143">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Redes sociales** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6da25-143">In the **Add Module** dialog box, select the **Social Share** module, and then select **OK**.</span></span>
1. <span data-ttu-id="6da25-144">En el espacio **Redes sociales**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="6da25-144">In the **Social Share** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="6da25-145">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Compartir en redes sociales** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6da25-145">In the **Add Module** dialog box, select the **SocialShare** module, and then select **OK**.</span></span>
1. <span data-ttu-id="6da25-146">En el panel de propiedades del módulo **Compartir en redes sociales**, **Orientación**, seleccione **Horizontal**.</span><span class="sxs-lookup"><span data-stu-id="6da25-146">In the properties pane of the **SocialShare** module, under **Orientation**, select **Horizontal**.</span></span> <span data-ttu-id="6da25-147">Agregue un título según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6da25-147">Add a caption as needed.</span></span>
1. <span data-ttu-id="6da25-148">En el espacio **Compartir en redes sociales**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="6da25-148">In the **SocialShare** slot, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="6da25-149">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Elemento para compartir en redes sociales** y, a continuación, **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6da25-149">In the **Add Module** dialog box, select the **SocialShareItem** module, and then select **OK**.</span></span>
1. <span data-ttu-id="6da25-150">En el panel de propiedades del módulo **Elemento para compartir en redes sociales**, en **Redes sociales**, seleccione **Facebook**.</span><span class="sxs-lookup"><span data-stu-id="6da25-150">In the properties pane of the **SocialShareItem** module, under **Social Media**, select **Facebook**.</span></span>
1. <span data-ttu-id="6da25-151">En el panel de propiedades del módulo **Elemento para compartir en redes sociales**, en **Icono**, seleccione **+ Agregar una imagen**.</span><span class="sxs-lookup"><span data-stu-id="6da25-151">In the properties pane of the **SocialShareItem** module, under **Icon**, select **+ Add an image**.</span></span>
1. <span data-ttu-id="6da25-152">En el cuadro de diálogo **Selector de medios**, seleccione la imagen del logotipo de Facebook y, después, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="6da25-152">In the **Media Picker** dialog box, select the Facebook logo image, and then select **OK**.</span></span> <span data-ttu-id="6da25-153">Si no está presente una imagen del logotipo de Facebook, seleccione **Cargar nuevo elemento multimedia** para cargar uno.</span><span class="sxs-lookup"><span data-stu-id="6da25-153">If no Facebook logo image is present, select **Upload new media item** to upload one.</span></span>
1. <span data-ttu-id="6da25-154">Agregar y configurar módulos adicionales de **Elemento para compartir en redes sociales** según sea necesario.</span><span class="sxs-lookup"><span data-stu-id="6da25-154">Add and configure additional **SocialShareItem** modules as needed.</span></span>
1. <span data-ttu-id="6da25-155">Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.</span><span class="sxs-lookup"><span data-stu-id="6da25-155">Select **Save**, and then select **Preview** to preview the page.</span></span> <span data-ttu-id="6da25-156">La página mostrará el módulo de compartir en redes sociales.</span><span class="sxs-lookup"><span data-stu-id="6da25-156">The page will show the social share module.</span></span>
1. <span data-ttu-id="6da25-157">Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="6da25-157">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6da25-158">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="6da25-158">Additional resources</span></span>

[<span data-ttu-id="6da25-159">Visión general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="6da25-159">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="6da25-160">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="6da25-160">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="6da25-161">Cumplimiento de cookies</span><span class="sxs-lookup"><span data-stu-id="6da25-161">Cookie compliance</span></span>](cookie-compliance.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]