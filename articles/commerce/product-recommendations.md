---
title: Visión general de recomendaciones de producto
description: En este tema se proporciona información general sobre recomendaciones de productos. Las recomendaciones de producto permiten a los clientes encontrar fácil y rápidamente los productos que desean, e incluso los productos que no pensaban comprar en un principio.
author: Moonma
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5aa7db8e53906f9e1416b912fe2c3b70d5430258
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415408"
---
# <a name="product-recommendations-overview"></a><span data-ttu-id="b088d-104">Visión general de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="b088d-104">Product recommendations overview</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="b088d-105">Microsoft Dynamics 365 Commerce se puede utilizar para mostrar recomendaciones de productos en el dispositivo de punto de venta (PDV) y sitio web de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="b088d-105">Microsoft Dynamics 365 Commerce can be used to show product recommendations on the e-Commerce website and point of sale (POS) device.</span></span> <span data-ttu-id="b088d-106">Las recomendaciones de productos son artículos en los que un cliente puede estar interesado.</span><span class="sxs-lookup"><span data-stu-id="b088d-106">Product recommendations are items that a customer might be interested in.</span></span> <span data-ttu-id="b088d-107">Las recomendaciones se basan en las tendencias de compras de otros clientes en tiendas físicas o en línea.</span><span class="sxs-lookup"><span data-stu-id="b088d-107">The recommendations are based on the purchase trends of other customers in online and brick-and-mortar stores.</span></span>

<span data-ttu-id="b088d-108">Las recomendaciones de productos permiten a los clientes buscar con facilidad y rapidez lo que desean a la vez que tienen una experiencia que les sirve bien.</span><span class="sxs-lookup"><span data-stu-id="b088d-108">Product recommendations allow customers to easily and quickly find products that they want while they have an experience that serves them well.</span></span> <span data-ttu-id="b088d-109">Las ventas cruzadas y verticales se pueden usar incluso para ayudar a clientes a encontrar productos adicionales que no se pensaron en un principio para comprar.</span><span class="sxs-lookup"><span data-stu-id="b088d-109">Cross-selling and upselling can even be used to assist customers find additional products that they didn't originally intend to buy.</span></span> <span data-ttu-id="b088d-110">Cuando se usan recomendaciones para mejorar la detección de productos, pueden crear más oportunidades de conversión, ayudan a aumentar los ingresos de ventas e incluso ayudan a amplificar la retención y la satisfacción del cliente.</span><span class="sxs-lookup"><span data-stu-id="b088d-110">When recommendations are used to enhance product discovery, they create more conversion opportunities, help increase sales revenue, and even amplify customer satisfaction and retention.</span></span>

<span data-ttu-id="b088d-111">En el comercio electrónico, las recomendaciones de productos son impulsadas con tecnologías de aprendizaje automático de Microsoft Recommendations a gran escala.</span><span class="sxs-lookup"><span data-stu-id="b088d-111">In e-Commerce, product recommendations are powered by Microsoft Recommendations machine learning technologies on a large scale.</span></span>

## <a name="recommendation-service"></a><span data-ttu-id="b088d-112">Servicio de recomendaciones</span><span class="sxs-lookup"><span data-stu-id="b088d-112">Recommendation service</span></span>

<span data-ttu-id="b088d-113">El servicio de recomendaciones de productos utiliza tecnologías de inteligencia artificial y aprendizaje automático (AI-ML) de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="b088d-113">The product recommendations service utilizes artificial intelligence and machine learning (AI-ML) technologies in the following way:</span></span>

- <span data-ttu-id="b088d-114">Los datos en el formato requerido por el servicio de recomendaciones se extraen de la base de datos operativa de Commerce y se envían a Azure Data Lake Storage o al almacén de entidades.</span><span class="sxs-lookup"><span data-stu-id="b088d-114">Data in the format that the Recommendation service requires is extracted from the Commerce operational database and sent to Azure Data Lake Storage or Entity store.</span></span>
- <span data-ttu-id="b088d-115">El servicio de recomendaciones utiliza los datos almacenados para entrenar modelos de recomendaciones para las listas **A la gente también le gustó**, **Los usuarios que compraron esto también compraron**, **Nuevos**, **Más vendidos** y **Tendencias**.</span><span class="sxs-lookup"><span data-stu-id="b088d-115">The recommendations service uses the stored data to train recommendation models for the **People also like**, **Frequently bought together**, **New**, **Best selling**, and **Trending** lists.</span></span>

## <a name="scenarios"></a><span data-ttu-id="b088d-116">Situaciones</span><span class="sxs-lookup"><span data-stu-id="b088d-116">Scenarios</span></span>

<span data-ttu-id="b088d-117">Las recomendaciones de productos están disponibles para los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="b088d-117">Product recommendations are available for the following scenarios:</span></span>

- <span data-ttu-id="b088d-118">**En cualquier página de tienda para explorar o página de aterrizaje en comercio electrónico:** si los clientes o socios de tienda visitan una página de la tienda, el motor de recomendaciones puede sugerir productos en las listas **Nuevos**, **Más vendidos** y **Tendencias**.</span><span class="sxs-lookup"><span data-stu-id="b088d-118">**On any store page for browsing or landing page in e-Commerce:** If customers or store associates visit a store page, the recommendation engine can suggest products in the **New**, **Best Selling**, and **Trending** lists.</span></span>
- <span data-ttu-id="b088d-119">**En la página Detalles de producto:** si los clientes o socios de tienda visitan una página **Detalles de producto**, el motor de recomendaciones sugiere artículos adicionales de los que también hay probabilidad que se compren.</span><span class="sxs-lookup"><span data-stu-id="b088d-119">**On the Product details page:** If customers or store associates visit a **Product details** page, the recommendation engine suggests additional items that are also likely to be purchased.</span></span> <span data-ttu-id="b088d-120">Estos artículos aparecen en la lista **A la gente también le gustó**.</span><span class="sxs-lookup"><span data-stu-id="b088d-120">These items appear in the **People also like** list.</span></span>
- <span data-ttu-id="b088d-121">**En la página Transacción o la página de finalización de compra:** el motor de recomendaciones sugiere artículos, en función de la lista completa de artículos de la cesta.</span><span class="sxs-lookup"><span data-stu-id="b088d-121">**On the Transaction page or the checkout page:** The recommendation engine suggests items, based on the whole list of items in the basket.</span></span> <span data-ttu-id="b088d-122">Estos artículos aparecen en la lista **Los usuarios que compraron esto también compraron**.</span><span class="sxs-lookup"><span data-stu-id="b088d-122">These items appear in the **Frequently bought together** list.</span></span>
- <span data-ttu-id="b088d-123">**Recomendaciones personalizadas**: los comerciantes pueden proporcionar a los clientes que han iniciado una lista de **Picking para usted** personalizada, además de la nueva funcionalidad que permite personalizar los escenarios de lista existentes en función de ese cliente.</span><span class="sxs-lookup"><span data-stu-id="b088d-123">**Personalized recommendations:** Merchandizers can provide signed-in customers a personalized **picks for you** list, in addition to new functionality that allows for existing list scenarios to be personalized based on that customer.</span></span> <span data-ttu-id="b088d-124">Para obtener más información, consulte [Habilitar recomendaciones personalizadas](personalized-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="b088d-124">To learn more, see [Enable personalized recommendations.](personalized-recommendations.md).</span></span>

### <a name="types-of-product-recommendations"></a><span data-ttu-id="b088d-125">Tipos de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="b088d-125">Types of product recommendations</span></span>

<span data-ttu-id="b088d-126">En la tabla siguiente se describen varios tipos de recomendaciones automáticas de productos disponibles que los minoristas pueden implementar en su solución de Dynamics 365 Commerce a través del [módulo de colección de productos](product-collection-module-overview.md).</span><span class="sxs-lookup"><span data-stu-id="b088d-126">The following table describes various types of automated product recommendations available for retailers to implement in their Dynamics 365 Commerce solution via the [product collection module](product-collection-module-overview.md).</span></span> <span data-ttu-id="b088d-127">Los comercios minoristas también pueden mostrar resultados personalizados para un usuario que ha iniciado sesión si el autor del sitio elige esa opción.</span><span class="sxs-lookup"><span data-stu-id="b088d-127">Retailers can also show personalized results for a signed-in user if the site author chooses that option.</span></span>

| <span data-ttu-id="b088d-128">Módulo de colección de productos</span><span class="sxs-lookup"><span data-stu-id="b088d-128">Product collection module</span></span>  | <span data-ttu-id="b088d-129">Tipo</span><span class="sxs-lookup"><span data-stu-id="b088d-129">Type</span></span> | <span data-ttu-id="b088d-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="b088d-130">Description</span></span> |
|----------------------------|------|-------------|
| <span data-ttu-id="b088d-131">Nuevas</span><span class="sxs-lookup"><span data-stu-id="b088d-131">New</span></span>                        | <span data-ttu-id="b088d-132">Algorítmico</span><span class="sxs-lookup"><span data-stu-id="b088d-132">Algorithmic</span></span> | <span data-ttu-id="b088d-133">Este módulo muestra una lista de los productos que se han surtido recientemente a canales y catálogos.</span><span class="sxs-lookup"><span data-stu-id="b088d-133">This module shows a list of the newest products that have been recently assorted to channels and catalogs.</span></span> |
| <span data-ttu-id="b088d-134">Más vendidos</span><span class="sxs-lookup"><span data-stu-id="b088d-134">Best selling</span></span>               | <span data-ttu-id="b088d-135">Algorítmico</span><span class="sxs-lookup"><span data-stu-id="b088d-135">Algorithmic</span></span> | <span data-ttu-id="b088d-136">Este módulo muestra una lista de productos que están clasificados por el número máximo de ventas.</span><span class="sxs-lookup"><span data-stu-id="b088d-136">This module shows a list of products that are ranked by the highest number of sales.</span></span> |
| <span data-ttu-id="b088d-137">Tendencias</span><span class="sxs-lookup"><span data-stu-id="b088d-137">Trending</span></span>                   | <span data-ttu-id="b088d-138">Algorítmico</span><span class="sxs-lookup"><span data-stu-id="b088d-138">Algorithmic</span></span> | <span data-ttu-id="b088d-139">Este módulo muestra una lista de los productos con el máximo rendimiento para un período determinado, clasificados por la mayor cantidad de ventas.</span><span class="sxs-lookup"><span data-stu-id="b088d-139">This module shows a list of the highest-performing products for a given period, ranked by highest number of sales.</span></span>  |
| <span data-ttu-id="b088d-140">Los usuarios que compraron este artículo también compraron</span><span class="sxs-lookup"><span data-stu-id="b088d-140">Frequently bought together</span></span> | <span data-ttu-id="b088d-141">AI-ML</span><span class="sxs-lookup"><span data-stu-id="b088d-141">AI-ML</span></span> | <span data-ttu-id="b088d-142">Este módulo recomienda una lista de productos que se suelen comprar a la vez que el contenido del carro actual del consumidor.</span><span class="sxs-lookup"><span data-stu-id="b088d-142">This module recommends a list of products that are commonly purchased together with the contents of the consumers current cart.</span></span> |
| <span data-ttu-id="b088d-143">A la gente también le gustó</span><span class="sxs-lookup"><span data-stu-id="b088d-143">People also like</span></span>           | <span data-ttu-id="b088d-144">AI-ML</span><span class="sxs-lookup"><span data-stu-id="b088d-144">AI-ML</span></span> | <span data-ttu-id="b088d-145">Este módulo recomienda productos para un producto de inicialización determinado según los patrones de compra del consumidor.</span><span class="sxs-lookup"><span data-stu-id="b088d-145">This module recommends products for a given seed product based on consumer purchase patterns.</span></span> |
| <span data-ttu-id="b088d-146">Picking para usted</span><span class="sxs-lookup"><span data-stu-id="b088d-146">Picks for you</span></span>              | <span data-ttu-id="b088d-147">AI-ML</span><span class="sxs-lookup"><span data-stu-id="b088d-147">AI-ML</span></span> | <span data-ttu-id="b088d-148">Este módulo recomienda una lista personalizada de productos basada en los patrones de compra del usuario que inició sesión.</span><span class="sxs-lookup"><span data-stu-id="b088d-148">This module recommends a personalized list of products based on purchase patterns of the signed-in user.</span></span> <span data-ttu-id="b088d-149">Para un usuario invitado, esta lista se contraerá.</span><span class="sxs-lookup"><span data-stu-id="b088d-149">For a guest user, this list will be collapsed.</span></span> |

## <a name="additional-resources"></a><span data-ttu-id="b088d-150">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b088d-150">Additional resources</span></span>

[<span data-ttu-id="b088d-151">Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="b088d-151">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="b088d-152">Habilitar recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="b088d-152">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="b088d-153">Habilitar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="b088d-153">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="b088d-154">Cancelar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="b088d-154">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="b088d-155">Habilitar recomendaciones de "comprar looks similares"</span><span class="sxs-lookup"><span data-stu-id="b088d-155">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="b088d-156">Agregar recomendaciones de producto en PDV</span><span class="sxs-lookup"><span data-stu-id="b088d-156">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="b088d-157">Agregar recomendaciones a la pantalla de transacción</span><span class="sxs-lookup"><span data-stu-id="b088d-157">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="b088d-158">Ajuste los resultados de las recomendaciones AI-ML</span><span class="sxs-lookup"><span data-stu-id="b088d-158">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="b088d-159">Crear manualmente recomendaciones curadas</span><span class="sxs-lookup"><span data-stu-id="b088d-159">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="b088d-160">Crear recomendaciones con datos de demostración</span><span class="sxs-lookup"><span data-stu-id="b088d-160">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="b088d-161">Preguntas más frecuentes de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="b088d-161">Product recommendations FAQ</span></span>](faq-recommendations.md)
