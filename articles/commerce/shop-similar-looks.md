---
title: Habilitar recomendaciones de "comprar looks similares"
description: Este tema describe cómo habilitar las recomendaciones de productos "comprar looks similares" en Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 08/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: da957850072e233a41a042d5857f81ddbf178f7a
ms.sourcegitcommit: 97ceb24f191161ca601e0889a539df665834ac3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2020
ms.locfileid: "3818383"
---
# <a name="enable-shop-similar-looks-recommendations"></a><span data-ttu-id="c49a8-103">Habilitar recomendaciones de "comprar looks similares"</span><span class="sxs-lookup"><span data-stu-id="c49a8-103">Enable "shop similar looks" recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c49a8-104">Este tema describe cómo habilitar las recomendaciones de productos "comprar looks similares" en Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c49a8-104">This topic describes how to enable "shop similar looks" product recommendations in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c49a8-105">Información general</span><span class="sxs-lookup"><span data-stu-id="c49a8-105">Overview</span></span>

<span data-ttu-id="c49a8-106">La característica de recomendaciones "comprar looks similares" de Dynamics 365 Commerce utiliza el poder de la inteligencia artificial y el aprendizaje automático (AI-ML) para ofrecer a los clientes recomendaciones de productos visualmente similares.</span><span class="sxs-lookup"><span data-stu-id="c49a8-106">The "shop similar looks" recommendations feature in Dynamics 365 Commerce uses the power of artificial intelligence and machine learning (AI-ML) to deliver recommendations for visually similar products to customers.</span></span> <span data-ttu-id="c49a8-107">Al hacer que las recomendaciones de "comprar looks similares" estén disponibles para todos los canales minoristas en Commerce, los minoristas pueden aumentar la satisfacción del cliente al ayudarlos a encontrar fácilmente lo que buscan.</span><span class="sxs-lookup"><span data-stu-id="c49a8-107">By making "shop similar looks" recommendations available for all retail channels in Commerce, retailers can increase customer satisfaction by helping customers easily find what they want.</span></span>

<span data-ttu-id="c49a8-108">La funcionalidad para recomendaciones de "comprar looks similares" utiliza imágenes de productos de variantes de productos de inicialización para encontrar y recomendar productos visualmente similares en el catálogo de productos de un minorista.</span><span class="sxs-lookup"><span data-stu-id="c49a8-108">The functionality for "shop similar looks" recommendations uses product images of seed product variants to find and recommend visually similar products in a retailer's product catalog.</span></span> 

<span data-ttu-id="c49a8-109">Las recomendaciones de "Comprar looks similares" están disponibles tanto en puntos de venta (PDV) como en experiencias de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="c49a8-109">"Shop similar looks" recommendations are available in both the point of sale (POS) and e-Commerce experiences.</span></span>

### <a name="example-scenarios"></a><span data-ttu-id="c49a8-110">Escenarios de ejemplo</span><span class="sxs-lookup"><span data-stu-id="c49a8-110">Example scenarios</span></span>

- <span data-ttu-id="c49a8-111">Un cliente ve un suéter de rayas negras y recibe una recomendación para un suéter similar de color rojo.</span><span class="sxs-lookup"><span data-stu-id="c49a8-111">A customer views a black striped sweater and receives a recommendation for a similar sweater in red.</span></span> <span data-ttu-id="c49a8-112">El cliente selecciona el producto recomendado en lugar del producto visto originalmente y luego recibe recomendaciones de productos similares en rojo.</span><span class="sxs-lookup"><span data-stu-id="c49a8-112">The customer selects the recommended product instead of the originally viewed product and then receives recommendations for similar products in red.</span></span> 
- <span data-ttu-id="c49a8-113">Un cliente utiliza las recomendaciones de "comprar looks similares" para descubrir pendientes a juego para un anillo que el cliente está interesado en comprar.</span><span class="sxs-lookup"><span data-stu-id="c49a8-113">A customer uses "shop similar looks" recommendations to discover matching earrings for a ring that the customer is interested in buying.</span></span>

## <a name="enable-shop-similar-looks-recommendations-in-commerce-headquarters"></a><span data-ttu-id="c49a8-114">Habilitar recomendaciones de "comprar looks similares" en la sede de Commerce</span><span class="sxs-lookup"><span data-stu-id="c49a8-114">Enable "shop similar looks" recommendations in Commerce headquarters</span></span>

<span data-ttu-id="c49a8-115">Las recomendaciones de productos solo se admiten para clientes de Commerce que han migrado su almacenamiento para usar Azure Data Lake Gen2.</span><span class="sxs-lookup"><span data-stu-id="c49a8-115">Product recommendations are supported only for Commerce users who have migrated their storage to Azure Data Lake Gen2.</span></span>

### <a name="prerequisites"></a><span data-ttu-id="c49a8-116">Requisitos previos</span><span class="sxs-lookup"><span data-stu-id="c49a8-116">Prerequisites</span></span>

<span data-ttu-id="c49a8-117">Antes de que los minoristas puedan comenzar a mostrar recomendaciones de "comprar looks similares" a los clientes, hay dos pasos previos:</span><span class="sxs-lookup"><span data-stu-id="c49a8-117">Before retailers can begin to show "shop similar looks" recommendations to customers, there are two prerequisite steps:</span></span>

- <span data-ttu-id="c49a8-118">[Habilitar recomendaciones de productos](enable-product-recommendations.md) en la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="c49a8-118">[Enable product recommendations](enable-product-recommendations.md) in Commerce headquarters.</span></span>
- <span data-ttu-id="c49a8-119">Confirmar que el servidor de medios admite llamadas HTTPS.</span><span class="sxs-lookup"><span data-stu-id="c49a8-119">Confirm that the media server supports HTTPS calls.</span></span>

<span data-ttu-id="c49a8-120">Para que el motor de recomendaciones acceda a las imágenes del producto, los minoristas deben generar las direcciones URL del producto.</span><span class="sxs-lookup"><span data-stu-id="c49a8-120">For the recommendations engine to access the product images, retailers must generate the product URLs.</span></span> <span data-ttu-id="c49a8-121">Para generar direcciones URL de producto en la sede de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="c49a8-121">To generate product URLs in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="c49a8-122">Vaya a **Imágenes de productos**.</span><span class="sxs-lookup"><span data-stu-id="c49a8-122">Go to **Product images**.</span></span>
1. <span data-ttu-id="c49a8-123">En el panel de acciones, seleccione **Definir plantilla de medios**.</span><span class="sxs-lookup"><span data-stu-id="c49a8-123">On the Action Pane, select **Define media template**.</span></span>
1. <span data-ttu-id="c49a8-124">En el panel de propiedades **Definir plantilla de medios**, en **Direcciones URL de medios**, seleccione **Generar direcciones URL**.</span><span class="sxs-lookup"><span data-stu-id="c49a8-124">In the **Define media template** properties pane, under **Media URLs**, select **Generate URLs**.</span></span>

> [!NOTE]
> <span data-ttu-id="c49a8-125">Al habilitar la característica de recomendaciones "comprar looks similares", comienza el proceso de generar listas de recomendaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="c49a8-125">When you enable the "shop similar looks" recommendations feature, the process of generating product recommendation lists begins.</span></span> <span data-ttu-id="c49a8-126">Es posible que se requiera hasta un día antes de que estas listas estén disponibles y visibles en línea y en los terminales de PDV.</span><span class="sxs-lookup"><span data-stu-id="c49a8-126">Up to a day might be required before those lists are available and visible online and on POS terminals.</span></span>

<span data-ttu-id="c49a8-127">Para habilitar la características de recomendaciones "comprar looks similares" en la sede de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="c49a8-127">To enable the "shop similar looks" recommendations feature in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="c49a8-128">Vaya a **Administración de características**.</span><span class="sxs-lookup"><span data-stu-id="c49a8-128">Go to **Feature management**.</span></span>
1. <span data-ttu-id="c49a8-129">En la lista de características disponibles, busque y seleccione **Comprar looks similares**.</span><span class="sxs-lookup"><span data-stu-id="c49a8-129">In the list of available features, search for and select **Shop similar looks**.</span></span>
1. <span data-ttu-id="c49a8-130">En el panel derecho, seleccione **Habilitar** para activar el servicio.</span><span class="sxs-lookup"><span data-stu-id="c49a8-130">In the right pane, select **Enable** to turn on the service.</span></span>

<span data-ttu-id="c49a8-131">La siguiente ilustración muestra la característica **Comprar looks similares** en la página **Administración de características** de la sede de Commerce.</span><span class="sxs-lookup"><span data-stu-id="c49a8-131">The following illustration shows the **Shop similar looks** feature on the **Feature management** page in Commerce headquarters.</span></span>

![La característica Comprar looks similares en la página de Administración de características de la sede de Commerce](./media/enableshopsimilarlooks.png)

<span data-ttu-id="c49a8-133">Una vez completadas las tareas anteriores, los terminales de PDV se mejoran automáticamente con un panel **Comprar productos similares** contextual.</span><span class="sxs-lookup"><span data-stu-id="c49a8-133">After the preceding tasks been completed, POS terminals are automatically enhanced with a contextual **Shop similar products** panel.</span></span> <span data-ttu-id="c49a8-134">Si selecciona **Ver más**, se puede llevar a los usuarios de terminales de PDV a una página "comprar looks similares" dedicada que se puede filtrar más.</span><span class="sxs-lookup"><span data-stu-id="c49a8-134">By selecting **See more**, POS terminal users can be taken to a dedicated "shop similar looks" page that can be filtered further.</span></span>

> [!NOTE]
> <span data-ttu-id="c49a8-135">Si desactiva la característica de recomendaciones "comprar looks similares", no se verá afectado ningún otro tipo de recomendaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="c49a8-135">If you turn off the "shop similar looks" recommendations feature, no other types of product recommendations are affected.</span></span> <span data-ttu-id="c49a8-136">Para obtener más información acerca de las listas de recomendaciones de productos, consulte la [Información general sobre las recomendaciones de productos](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="c49a8-136">For more information about product recommendations, see [Product recommendations overview](product-recommendations.md).</span></span>

## <a name="add-a-shop-similar-looks-button-to-product-details-pages-by-using-commerce-site-builder"></a><span data-ttu-id="c49a8-137">Agregar un botón Comprar looks similares a las páginas de detalles del producto a través del generador de sitios de Commerce</span><span class="sxs-lookup"><span data-stu-id="c49a8-137">Add a Shop similar looks button to product details pages by using Commerce site builder</span></span>

<span data-ttu-id="c49a8-138">Después de habilitar la característica de recomendaciones "comprar looks similares" en la sede de Commerce, una opción del generador de sitios de Commerce permite a los minoristas agregar un botón **Comprar looks similares** al cuadro de compra en cualquier página de detalles del producto (PDP).</span><span class="sxs-lookup"><span data-stu-id="c49a8-138">After you enable the "shop similar looks" recommendations feature in Commerce headquarters, an option in Commerce site builder lets retailers to add a **Shop similar looks** button to the buy box on any product details page (PDP).</span></span> <span data-ttu-id="c49a8-139">Un cliente que seleccione este botón irá a una página dedicada a "comprar looks similares" que muestra productos visualmente similares.</span><span class="sxs-lookup"><span data-stu-id="c49a8-139">A customer who selects this button is taken to a dedicated "shop similar looks" page that returns visually similar products.</span></span> <span data-ttu-id="c49a8-140">Allí, el cliente puede utilizar selectores para filtrar todavía más los productos.</span><span class="sxs-lookup"><span data-stu-id="c49a8-140">There, the customer can use selectors to further filter the products.</span></span>

<span data-ttu-id="c49a8-141">Para agregar un botón **Comprar looks similares** a un PDP a través del generador de sitios de Commerce, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="c49a8-141">To add a **Shop similar looks** button to a PDP by using Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="c49a8-142">Abra una página de generador de sitios de comercio electrónico existente que contenga un módulo de cuadro de compra.</span><span class="sxs-lookup"><span data-stu-id="c49a8-142">Open an existing site builder page that contains a buy box module.</span></span>
1. <span data-ttu-id="c49a8-143">En el panel de navegación de la izquierda, seleccione el módulo de cuadro de compra.</span><span class="sxs-lookup"><span data-stu-id="c49a8-143">In the left navigation pane, select the buy box module.</span></span>
1. <span data-ttu-id="c49a8-144">En el panel de navegación derecho, active la casilla **Habilitar vínculo para comprar looks similares**.</span><span class="sxs-lookup"><span data-stu-id="c49a8-144">In the right navigation pane, select the **Enable Shop Similar Looks Link** check box.</span></span>
1. <span data-ttu-id="c49a8-145">Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.</span><span class="sxs-lookup"><span data-stu-id="c49a8-145">Select **Save**, select **Finish editing** to check in the page, and then select **Publish** to publish it.</span></span> <span data-ttu-id="c49a8-146">Una vez publicada la página, el PDP incluirá un botón **Comprar looks similares**.</span><span class="sxs-lookup"><span data-stu-id="c49a8-146">After the page is published, the PDP will include a **Shop similar looks** button.</span></span>

<span data-ttu-id="c49a8-147">La siguiente ilustración muestra la casilla **Habilitar vínculo para comprar looks similares** y **Comprar looks similares** en un ejemplo de PDP en el generador de sitios.</span><span class="sxs-lookup"><span data-stu-id="c49a8-147">The following illustration shows the **Enable Shop Similar Looks Link** check box and **Shop similar looks** button on an example PDP in site builder.</span></span>

![La casilla Habilitar vínculo para comprar looks similares y el botón Comprar looks similares en un PDP en el generador de sitios](./media/SSLecomtooling.png)

## <a name="additional-resources"></a><span data-ttu-id="c49a8-149">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c49a8-149">Additional resources</span></span>

[<span data-ttu-id="c49a8-150">Visión general de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="c49a8-150">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="c49a8-151">Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="c49a8-151">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="c49a8-152">Habilitar recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="c49a8-152">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="c49a8-153">Cancelar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="c49a8-153">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="c49a8-154">Agregar recomendaciones de producto en PDV</span><span class="sxs-lookup"><span data-stu-id="c49a8-154">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="c49a8-155">Agregar recomendaciones a la pantalla de transacción</span><span class="sxs-lookup"><span data-stu-id="c49a8-155">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="c49a8-156">Ajuste los resultados de las recomendaciones AI-ML</span><span class="sxs-lookup"><span data-stu-id="c49a8-156">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="c49a8-157">Crear manualmente recomendaciones curadas</span><span class="sxs-lookup"><span data-stu-id="c49a8-157">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="c49a8-158">Crear recomendaciones con datos de demostración</span><span class="sxs-lookup"><span data-stu-id="c49a8-158">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="c49a8-159">Preguntas más frecuentes de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="c49a8-159">Product recommendations FAQ</span></span>](faq-recommendations.md)
