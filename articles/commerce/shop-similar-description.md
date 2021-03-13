---
title: Habilitar recomendaciones de "comprar descripción similar"
description: Este tema describe cómo habilitar las recomendaciones de productos "comprar descripción similar" en Microsoft Dynamics 365 Commerce.
author: bsokolov
manager: AnnBe
ms.date: 01/13/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: b3b7abf47a3bdacaa4b91ae32b68a809a84b0b1d
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2021
ms.locfileid: "5098648"
---
# <a name="enable-shop-similar-description-recommendations"></a><span data-ttu-id="47232-103">Habilitar recomendaciones de "comprar descripción similar"</span><span class="sxs-lookup"><span data-stu-id="47232-103">Enable "shop similar description" recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="47232-104">Este tema describe cómo habilitar las recomendaciones de productos "comprar descripción similar" en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="47232-104">This topic describes how to enable "shop similar description" product recommendations in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="47232-105">La característica de recomendaciones "comprar descripción similar" de Dynamics 365 Commerce aprovecha la eficacia de la inteligencia artificial y el aprendizaje automático (AI-ML) para ofrecer a los clientes recomendaciones de productos visualmente similares.</span><span class="sxs-lookup"><span data-stu-id="47232-105">The "shop similar description" recommendations feature in Dynamics 365 Commerce uses artificial intelligence and machine learning (AI-ML) to deliver recommendations for products that have descriptions that are similar to what the customer is looking for.</span></span> <span data-ttu-id="47232-106">Al hacer que las recomendaciones de "comprar descripción similar" estén disponibles para todos los canales minoristas en Commerce, los minoristas pueden aumentar la satisfacción del cliente al ayudarle a encontrar fácilmente lo que busca.</span><span class="sxs-lookup"><span data-stu-id="47232-106">By making "shop similar description" recommendations available for all retail channels in Commerce, retailers can help customers easily find what they want.</span></span>

<span data-ttu-id="47232-107">La funcionalidad de recomendaciones de "comprar descripción similar" utiliza el nombre y la descripción del producto de productos de inicialización para encontrar y recomendar productos visualmente similares en el catálogo de productos de un minorista.</span><span class="sxs-lookup"><span data-stu-id="47232-107">The functionality for "shop similar description" recommendations uses the product name and description of seed products to find and recommend similar products in a retailer's product catalog.</span></span>

<span data-ttu-id="47232-108">Las recomendaciones de "Comprar descripción similar" están disponibles tanto en puntos de venta (PDV) como en experiencias de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="47232-108">"Shop similar description" recommendations are available in both the point of sale (POS) and e-commerce experiences.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="47232-109">Escenarios de ejemplo</span><span class="sxs-lookup"><span data-stu-id="47232-109">Example scenarios</span></span>

<span data-ttu-id="47232-110">Los siguientes escenarios de ejemplo muestran los tipos de recomendaciones que puede proporcionar la funcionalidad "Comprar descripción similar":</span><span class="sxs-lookup"><span data-stu-id="47232-110">The following example scenarios show the types of recommendations that the "shop similar description" functionality can provide:</span></span>

- <span data-ttu-id="47232-111">Un cliente ve un par de anteojos de estilo retro y recibe un conjunto de recomendaciones para otros anteojos con un diseño similar, en el contexto de la industria del minorista.</span><span class="sxs-lookup"><span data-stu-id="47232-111">A customer views a pair of retro-style horn-rimmed glasses and receives a set of recommendations for other glasses that have a similar design, in the context of the retailer's industry.</span></span>
- <span data-ttu-id="47232-112">Un cliente utiliza recomendaciones de "comprar descripción similar" para descubrir sabores de café que son similares a un sabor que compró previamente al minorista.</span><span class="sxs-lookup"><span data-stu-id="47232-112">A customer uses "shop similar description" recommendations to discover coffee flavors that are similar to a flavor that they previously purchased from the retailer.</span></span>

## <a name="set-up-shop-similar-description-recommendations"></a><span data-ttu-id="47232-113">Configurar las recomendaciones de "comprar descripción similar"</span><span class="sxs-lookup"><span data-stu-id="47232-113">Set up "shop similar description" recommendations</span></span>

<span data-ttu-id="47232-114">Las recomendaciones de productos solo se admiten para clientes de Commerce que han migrado su almacenamiento a Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="47232-114">Product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Storage Gen2.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="47232-115">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="47232-115">Prerequisites</span></span>

<span data-ttu-id="47232-116">Antes de que se puedan mostrar a los clientes las recomendaciones de "comprar descripción similar", debe completar los siguientes requisitos previos:</span><span class="sxs-lookup"><span data-stu-id="47232-116">Before "shop similar description" recommendations can be shown to customers, you must complete the following prerequisites:</span></span>

- <span data-ttu-id="47232-117">[Habilitar recomendaciones de productos](enable-product-recommendations.md) en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="47232-117">[Enable product recommendations](enable-product-recommendations.md) in Commerce headquarters.</span></span>
- <span data-ttu-id="47232-118">Confirmar que el servidor de medios admite llamadas HTTPS.</span><span class="sxs-lookup"><span data-stu-id="47232-118">Confirm that the media server supports HTTPS calls.</span></span>

### <a name="turn-on-the-shop-similar-description-recommendations-feature"></a><span data-ttu-id="47232-119">Activar la característica de recomendaciones de "comprar descripción similar"</span><span class="sxs-lookup"><span data-stu-id="47232-119">Turn on the "shop similar description" recommendations feature</span></span>

<span data-ttu-id="47232-120">Para activar la característica de recomendaciones "comprar descripción similar" en la sede central de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="47232-120">To turn on the "shop similar description" recommendations feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="47232-121">En el espacio de trabajo **Administración de características**, en la lista de características disponibles, busque y seleccione **Comprar descripción similar**.</span><span class="sxs-lookup"><span data-stu-id="47232-121">In the **Feature management** workspace, in the list of available features, search for and select **Shop similar description**.</span></span>
1. <span data-ttu-id="47232-122">En el panel derecho, seleccione **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="47232-122">In the right pane, select **Enable**.</span></span>

> [!NOTE]
> <span data-ttu-id="47232-123">Cuando activa la característica, el sistema comienza a generar listas de recomendaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="47232-123">When you turn on the feature, the system starts to generate product recommendation lists.</span></span> <span data-ttu-id="47232-124">Es posible que se requiera hasta un día antes de que estas listas estén disponibles y visibles en línea y en los terminales de PDV.</span><span class="sxs-lookup"><span data-stu-id="47232-124">It might take up to a day for those lists to become available and visible online and on POS terminals.</span></span>
>
> <span data-ttu-id="47232-125">Si desactiva la características, los otros tipos de recomendaciones de productos no se verán afectados.</span><span class="sxs-lookup"><span data-stu-id="47232-125">If you turn off the feature, other types of product recommendations aren't affected.</span></span> <span data-ttu-id="47232-126">Para obtener más información acerca de las listas de recomendaciones de productos, consulte la [Información general sobre las recomendaciones de productos](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="47232-126">For more information about product recommendations, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="add-a-shop-similar-description-button-to-product-details-pages"></a><span data-ttu-id="47232-127">Agregar un botón de comprar descripción similar a las páginas de detalles de producto</span><span class="sxs-lookup"><span data-stu-id="47232-127">Add a Shop similar description button to product details pages</span></span>

<span data-ttu-id="47232-128">Después de activar la característica de recomendaciones "comprar descripción similar" en la sede central de Commerce, puede agregar un botón **Comprar descripción similar** al cuadro de compra de cualquier página de detalles de producto (PDP).</span><span class="sxs-lookup"><span data-stu-id="47232-128">After you turn on the "shop similar description" recommendations feature in Commerce headquarters, you can add a **Shop similar description** button to the buy box on any product details page (PDP).</span></span> <span data-ttu-id="47232-129">Un cliente que seleccione este botón irá a una página **Comprar descripción similar** dedicada que muestra productos visualmente similares.</span><span class="sxs-lookup"><span data-stu-id="47232-129">A customer who selects this button is taken to a dedicated **Shop similar description** page that shows visually similar products.</span></span> <span data-ttu-id="47232-130">El cliente podrá utilizar selectores para filtrar todavía más los productos.</span><span class="sxs-lookup"><span data-stu-id="47232-130">The customer can then use selectors to further filter the products.</span></span>

<span data-ttu-id="47232-131">Para agregar un botón **Comprar descripción similar** a una PDP a través del generador de sitios de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="47232-131">To add a **Shop similar description** button to a PDP by using Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="47232-132">Abra una página de generador de sitios de comercio electrónico existente que contenga un módulo de cuadro de compra.</span><span class="sxs-lookup"><span data-stu-id="47232-132">Open an existing site builder page that contains a buy box module.</span></span>
1. <span data-ttu-id="47232-133">En el panel de navegación de la izquierda, seleccione el módulo de cuadro de compra.</span><span class="sxs-lookup"><span data-stu-id="47232-133">In the left navigation pane, select the buy box module.</span></span>
1. <span data-ttu-id="47232-134">En el panel de navegación derecho, active la casilla **Habilitar vínculo para comprar descripción similar**.</span><span class="sxs-lookup"><span data-stu-id="47232-134">In the right pane, select the **Enable Shop Similar description Link** check box.</span></span>
1. <span data-ttu-id="47232-135">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="47232-135">Select **Save**.</span></span>
1. <span data-ttu-id="47232-136">Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="47232-136">Select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> <span data-ttu-id="47232-137">Una vez publicada la página, la PDP incluirá un botón **Comprar descripción similar**.</span><span class="sxs-lookup"><span data-stu-id="47232-137">After the page is published, the PDP will include a **Shop similar description** button.</span></span>

<span data-ttu-id="47232-138">La siguiente ilustración muestra la casilla **Habilitar vínculo para comprar descripción similar** y el botón **Comprar descripción similar** en un ejemplo de PDP del generador de sitios.</span><span class="sxs-lookup"><span data-stu-id="47232-138">The following illustration shows the **Enable shop similar description Link** check box and the **Shop similar description** button on an example PDP in site builder.</span></span>

![La casilla Habilitar vínculo para comprar descripción similar y el botón Comprar descripción similar en una PDP del generador de sitios](./media/ter_site_builder_buybox_button.png)

## <a name="additional-resources"></a><span data-ttu-id="47232-140">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="47232-140">Additional resources</span></span>

[<span data-ttu-id="47232-141">Visión general de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="47232-141">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="47232-142">Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="47232-142">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="47232-143">Habilitar recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="47232-143">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="47232-144">Habilitar recomendaciones de "comprar looks similares"</span><span class="sxs-lookup"><span data-stu-id="47232-144">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="47232-145">Ajuste los resultados de las recomendaciones AI-ML</span><span class="sxs-lookup"><span data-stu-id="47232-145">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="47232-146">Crear manualmente recomendaciones curadas</span><span class="sxs-lookup"><span data-stu-id="47232-146">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="47232-147">Preguntas más frecuentes de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="47232-147">Product recommendations FAQ</span></span>](faq-recommendations.md)
