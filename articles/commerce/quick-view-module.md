---
title: Módulo de vista rápida
description: En este tema se tratan los módulos de vista rápida y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-01-08
ms.dyn365.ops.version: Release 10.0.17
ms.openlocfilehash: 7e8244a06c515029b559b2061d9a25c7355e9e14
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2021
ms.locfileid: "5097061"
---
# <a name="quick-view-module"></a><span data-ttu-id="46264-103">Módulo de vista rápida</span><span class="sxs-lookup"><span data-stu-id="46264-103">Quick view module</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="46264-104">En este tema se tratan los módulos de vista rápida y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="46264-104">This topic covers quick view modules and describes how to add them to site pages in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="46264-105">El módulo de vista rápida permite a los usuarios ver rápidamente la información del producto cuando buscan productos en una página de lista, y agregar uno o más productos al carro desde la página de lista, sin tener que ir a la página de detalles del producto (PDP).</span><span class="sxs-lookup"><span data-stu-id="46264-105">The quick view module lets users quickly view product information when they browse products on a list page, and add one or more products to the cart from the list page, without having to go to the product details page (PDP).</span></span> <span data-ttu-id="46264-106">El módulo de vista rápida proporciona una descripción general de la información del producto que los usuarios necesitan para tomar la decisión de "agregar al carrito".</span><span class="sxs-lookup"><span data-stu-id="46264-106">The quick view module provides an overview of the product information that users require to make an "add to cart" decision.</span></span> <span data-ttu-id="46264-107">También proporciona un vínculo a la PDP, para que los usuarios puedan ver detalles adicionales del producto y opciones de compra.</span><span class="sxs-lookup"><span data-stu-id="46264-107">It also provides a link to the PDP, so that users can view additional product details and purchase options.</span></span>

<span data-ttu-id="46264-108">El módulo de vista rápida es compatible con los módulos de [colección de productos](product-collection-module-overview.md) y [resultados de búsqueda](search-result-module.md).</span><span class="sxs-lookup"><span data-stu-id="46264-108">The quick view module is supported by the [product collection](product-collection-module-overview.md) and [search results](search-result-module.md) modules.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="46264-109">El módulo de vista rápida está disponible a partir de la versión 10.0.17 de Commerce.</span><span class="sxs-lookup"><span data-stu-id="46264-109">The quick view module is available as of the Commerce version 10.0.17 release.</span></span>

<span data-ttu-id="46264-110">La siguiente ilustración muestra un ejemplo de un módulo de vista rápida en una página de lista de productos.</span><span class="sxs-lookup"><span data-stu-id="46264-110">The following illustration shows an example of a quick view module on a product list page.</span></span>

![Ejemplo de módulo de vista rápida en una página de lista de productos](./media/ecommerce-quickview.PNG)

## <a name="module-properties"></a><span data-ttu-id="46264-112">Propiedades del módulo</span><span class="sxs-lookup"><span data-stu-id="46264-112">Module properties</span></span>

<span data-ttu-id="46264-113">El módulo de vista rápida admite algunas de las mismas funciones que el módulo de caja de compra.</span><span class="sxs-lookup"><span data-stu-id="46264-113">The quick view module supports some of the same functions as the buy box module.</span></span> <span data-ttu-id="46264-114">Por lo tanto, las propiedades de un módulo de vista rápida se asemejan a las de un módulo de caja de compra.</span><span class="sxs-lookup"><span data-stu-id="46264-114">Therefore, the properties of a quick view module resemble the properties of a buy box module.</span></span>

| <span data-ttu-id="46264-115">Propiedad</span><span class="sxs-lookup"><span data-stu-id="46264-115">Property</span></span> | <span data-ttu-id="46264-116">Valores</span><span class="sxs-lookup"><span data-stu-id="46264-116">Values</span></span> | <span data-ttu-id="46264-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="46264-117">Description</span></span> |
|----------------|--------|-------------|
| <span data-ttu-id="46264-118">Etiqueta de título</span><span class="sxs-lookup"><span data-stu-id="46264-118">Heading tag</span></span> | <span data-ttu-id="46264-119">**H1**, **H2**, **H3**, **H4**, **H5** o **H6**</span><span class="sxs-lookup"><span data-stu-id="46264-119">**H1**, **H2**, **H3**, **H4**, **H5**, or **H6**</span></span> | <span data-ttu-id="46264-120">Esta propiedad define la etiqueta de encabezado para el título del producto.</span><span class="sxs-lookup"><span data-stu-id="46264-120">This property defines the heading tag for the product title.</span></span> <span data-ttu-id="46264-121">Si el módulo de vista rápida está en la parte superior de la página, esta propiedad debe establecerse en **H1** para cumplir los estándares de accesibilidad.</span><span class="sxs-lookup"><span data-stu-id="46264-121">If the quick view module is at the top of the page, this property should be set to **H1** to meet accessibility standards.</span></span> |
| <span data-ttu-id="46264-122">Permitir precio personalizado</span><span class="sxs-lookup"><span data-stu-id="46264-122">Allow custom price</span></span> | <span data-ttu-id="46264-123">**Verdadero** o **Falso**</span><span class="sxs-lookup"><span data-stu-id="46264-123">**True** or **False**</span></span> | <span data-ttu-id="46264-124">Si esta propiedad se establece en **Verdadero**, el usuario podrá introducir un precio personalizado.</span><span class="sxs-lookup"><span data-stu-id="46264-124">If this property is set to **True**, the user can enter a custom price.</span></span> |
| <span data-ttu-id="46264-125">Precio mínimo</span><span class="sxs-lookup"><span data-stu-id="46264-125">Minimum price</span></span> | <span data-ttu-id="46264-126">Entero</span><span class="sxs-lookup"><span data-stu-id="46264-126">Integer</span></span> | <span data-ttu-id="46264-127">Esta propiedad solo es aplicable si la propiedad **Permitir precio personalizado** está establecida en **Verdadero**.</span><span class="sxs-lookup"><span data-stu-id="46264-127">This property is applicable only if the **Allow custom price** property is set to **True**.</span></span> <span data-ttu-id="46264-128">Define el precio mínimo que el usuario puede introducir (por ejemplo, $1).</span><span class="sxs-lookup"><span data-stu-id="46264-128">It defines the minimum price that the user can enter (for example, $1).</span></span> |
| <span data-ttu-id="46264-129">Precio máximo</span><span class="sxs-lookup"><span data-stu-id="46264-129">Maximum price</span></span> | <span data-ttu-id="46264-130">Entero</span><span class="sxs-lookup"><span data-stu-id="46264-130">Integer</span></span> | <span data-ttu-id="46264-131">Esta propiedad solo es aplicable si la propiedad **Permitir precio personalizado** está establecida en **Verdadero**.</span><span class="sxs-lookup"><span data-stu-id="46264-131">This property is applicable only if the **Allow custom price** property is set to **True**.</span></span> <span data-ttu-id="46264-132">Define el precio máximo que el usuario puede introducir (por ejemplo, $1000).</span><span class="sxs-lookup"><span data-stu-id="46264-132">It defines the maximum price that the user can enter (for example, $1,000).</span></span> |

## <a name="commerce-site-builder-settings"></a><span data-ttu-id="46264-133">Configuración del generador de sitios de Commerce</span><span class="sxs-lookup"><span data-stu-id="46264-133">Commerce site builder settings</span></span>

<span data-ttu-id="46264-134">Al igual que el módulo de caja de compra, el módulo de vista rápida respeta la configuración en **Configuración del sitio \> Extensiones \> Agregar producto al carro**.</span><span class="sxs-lookup"><span data-stu-id="46264-134">Like the buy box module, the quick view module respects the settings at **Site Settings \> Extensions \> Add product to cart**.</span></span> <span data-ttu-id="46264-135">Sin embargo, se pasa por alto la opción **Navegar a la página del carro**, ya que no es coherente con el propósito del módulo de vista rápida, que es permitir a los usuarios explorar varios productos en una página de lista y agregarlos al carrito sin salir de la página de lista.</span><span class="sxs-lookup"><span data-stu-id="46264-135">However, the **Navigate to cart page** setting is ignored, because it's inconsistent with the purpose of the quick view module, which is to enable users to browse multiple products on a list page and add them to the cart without moving away from the list page.</span></span>

## <a name="add-a-quick-view-module-to-a-product-collection-module"></a><span data-ttu-id="46264-136">Agregar un módulo de vista rápida a un módulo de colección de productos</span><span class="sxs-lookup"><span data-stu-id="46264-136">Add a quick view module to a product collection module</span></span>

<span data-ttu-id="46264-137">El módulo de vista rápida se puede agregar a los módulos de colección de productos y resultados de búsqueda.</span><span class="sxs-lookup"><span data-stu-id="46264-137">A quick view module can be added to the product collection and search results modules.</span></span>

<span data-ttu-id="46264-138">Para agregar un módulo de vista rápida a un módulo de colección de productos en el generador de sitios de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="46264-138">To add a quick view module to a product collection module in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="46264-139">Vaya a **Páginas** y, a continuación, seleccione la página de inicio el sitio de Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="46264-139">Go to **Pages**, and then select the home page for the Fabrikam site.</span></span>
1. <span data-ttu-id="46264-140">Vaya a cualquier módulo **Colección de productos** en la página de inicio, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.</span><span class="sxs-lookup"><span data-stu-id="46264-140">Go to any **Product Collection** module on the homepage, select the ellipsis (**...**), and then select **Add Module**.</span></span>
1. <span data-ttu-id="46264-141">En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Vista rápida** y, a continuación, seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="46264-141">In the **Add Module** dialog box, select the **Quick View** module, and then select **OK**.</span></span>
1. <span data-ttu-id="46264-142">En el panel de propiedades del módulo **Vista rápida**, seleccione **Título**.</span><span class="sxs-lookup"><span data-stu-id="46264-142">In the properties pane of the **Quick View** module, select **Heading**.</span></span> <span data-ttu-id="46264-143">En el cuadro de diálogo **Título**, establezca el **Nivel de encabezado** en **H2** y seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="46264-143">In the **Heading** dialog box, set the **Heading Level** field to **H2**, and then select **OK**.</span></span>
1. <span data-ttu-id="46264-144">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="46264-144">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="46264-145">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="46264-145">Additional resources</span></span>

[<span data-ttu-id="46264-146">Descripción general de la biblioteca de módulos</span><span class="sxs-lookup"><span data-stu-id="46264-146">Module library overview</span></span>](starter-kit-overview.md)

[<span data-ttu-id="46264-147">Módulo de cuadro de compra</span><span class="sxs-lookup"><span data-stu-id="46264-147">Buy box module</span></span>](add-buy-box.md)

[<span data-ttu-id="46264-148">Módulo de colección de productos</span><span class="sxs-lookup"><span data-stu-id="46264-148">Product collection module</span></span>](product-collection-module-overview.md)

[<span data-ttu-id="46264-149">Módulo de resultados de búsqueda</span><span class="sxs-lookup"><span data-stu-id="46264-149">Search results module</span></span>](search-result-module.md)
