---
title: Visión general de recomendaciones de producto
description: En este tema se proporciona información general sobre recomendaciones de productos. Las recomendaciones de producto permiten a los clientes encontrar fácil y rápidamente los productos que desean, e incluso los productos que no pensaban comprar en un principio.
author: Moonma
manager: AnnBe
ms.date: 10/1/2019
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
ms.openlocfilehash: eb369e6d1356ba13a2310d523b671ac57b9642bf
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770056"
---
# <a name="product-recommendations-overview"></a><span data-ttu-id="064c5-104">Visión general de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="064c5-104">Product recommendations overview</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="064c5-105">Microsoft Dynamics 365 Commerce se puede utilizar para mostrar recomendaciones de productos en el dispositivo de punto de venta (PDV) y sitio web de comercio electrónico.</span><span class="sxs-lookup"><span data-stu-id="064c5-105">Microsoft Dynamics 365 Commerce can be used to show product recommendations on the e-Commerce website and point of sale (POS) device.</span></span> <span data-ttu-id="064c5-106">Las recomendaciones de productos son artículos en los que un cliente puede estar interesado.</span><span class="sxs-lookup"><span data-stu-id="064c5-106">Product recommendations are items that a customer might be interested in.</span></span> <span data-ttu-id="064c5-107">Las recomendaciones se basan en las tendencias de compras de otros clientes en tiendas físicas o en línea.</span><span class="sxs-lookup"><span data-stu-id="064c5-107">The recommendations are based on the purchase trends of other customers in online and brick-and-mortar stores.</span></span>

<span data-ttu-id="064c5-108">Las recomendaciones de productos permiten a los clientes buscar con facilidad y rapidez lo que desean a la vez que tienen una experiencia que les sirve bien.</span><span class="sxs-lookup"><span data-stu-id="064c5-108">Product recommendations let customers easily and quickly find products that they want while they have an experience that serves them well.</span></span> <span data-ttu-id="064c5-109">Las ventas cruzadas y verticales se pueden usar incluso para ayudar a clientes a encontrar productos adicionales que no se pensaron en un principio para comprar.</span><span class="sxs-lookup"><span data-stu-id="064c5-109">Cross-selling and upselling can even be used to help customers find additional products than they didn't originally intend to buy.</span></span> <span data-ttu-id="064c5-110">Cuando se usan recomendaciones para ayudar con la detección de productos, pueden crear más oportunidades de conversión, ayudan a aumentar los ingresos de ventas e incluso ayudan a mejorar la retención y la satisfacción del cliente.</span><span class="sxs-lookup"><span data-stu-id="064c5-110">When recommendations are used to help with product discovery, they can create more conversion opportunities, help increase sales revenue, and even help enhance customer satisfaction and retention.</span></span>

<span data-ttu-id="064c5-111">En Commerce, las recomendaciones de productos son impulsadas con tecnologías de aprendizaje automático de Microsoft Recommendations a gran escala.</span><span class="sxs-lookup"><span data-stu-id="064c5-111">In Commerce, product recommendations are powered by Microsoft Recommendations machine learning technologies on a large scale.</span></span>


## <a name="scenarios"></a><span data-ttu-id="064c5-112">Situaciones</span><span class="sxs-lookup"><span data-stu-id="064c5-112">Scenarios</span></span>

<span data-ttu-id="064c5-113">Las recomendaciones de productos están disponibles para los siguientes escenarios:</span><span class="sxs-lookup"><span data-stu-id="064c5-113">Product recommendations are available for the following scenarios:</span></span>

- <span data-ttu-id="064c5-114">**En cualquier página de tienda para explorar o página de aterrizaje en comercio electrónico:** si los clientes o socios de tienda visitan una página de la tienda, el motor de recomendaciones puede sugerir productos en las listas **Nuevos**, **Más vendidos** y **Tendencias**.</span><span class="sxs-lookup"><span data-stu-id="064c5-114">**On any store page for browsing or landing page in e-Commerce:** If customers or store associates visit a store page, the recommendation engine can suggest products in the **New**, **Best Selling**, and **Trending** lists.</span></span>
- <span data-ttu-id="064c5-115">**En la página Detalles de producto:** si los clientes o socios de tienda visitan una página **Detalles de producto**, el motor de recomendaciones sugiere artículos adicionales de los que también hay probabilidad que se compren.</span><span class="sxs-lookup"><span data-stu-id="064c5-115">**On the Product details page:** If customers or store associates visit a **Product details** page, the recommendation engine suggests additional items that are also likely to be purchased.</span></span> <span data-ttu-id="064c5-116">Estos artículos aparecen en la lista **A la gente también le gustó**.</span><span class="sxs-lookup"><span data-stu-id="064c5-116">These items appear in the **People also like** list.</span></span>
- <span data-ttu-id="064c5-117">**En la página Transacción o la página de finalización de compra:** el motor de recomendaciones sugiere artículos, en función de la lista completa de artículos de la cesta.</span><span class="sxs-lookup"><span data-stu-id="064c5-117">**On the Transaction page or the checkout page:** The recommendation engine suggests items, based on the whole list of items in the basket.</span></span> <span data-ttu-id="064c5-118">Estos artículos aparecen en la lista **Los usuarios que compraron esto también compraron**.</span><span class="sxs-lookup"><span data-stu-id="064c5-118">These items appear in the **Frequently bought together** list.</span></span>

## <a name="recommendation-service"></a><span data-ttu-id="064c5-119">Servicio de recomendaciones</span><span class="sxs-lookup"><span data-stu-id="064c5-119">Recommendation service</span></span>

<span data-ttu-id="064c5-120">Las recomendaciones de productos utilizan las tecnologías de aprendizaje automático de recomendaciones de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="064c5-120">Product recommendations use the Recommendations machine learning technologies in the following way:</span></span>

- <span data-ttu-id="064c5-121">Los datos en el formato requerido por el servicio de recomendaciones se extraen de la base de datos operativa de Commerce y se envían al almacén de entidades.</span><span class="sxs-lookup"><span data-stu-id="064c5-121">Data in the format that the Recommendation service requires is extracted from the Commerce operational database and sent to the Entity store.</span></span>
- <span data-ttu-id="064c5-122">El servicio de recomendaciones utiliza los datos para entrenar modelos de recomendaciones para las listas **A la gente también le gustó**, **Los usuarios que compraron esto también compraron**, **Nuevos**, **Más vendidos** y **Tendencias**.</span><span class="sxs-lookup"><span data-stu-id="064c5-122">The Recommendation service uses the data to train recommendation models for the **People also like**, **Frequently bought together**, **New**, **Best selling**, and **Trending** lists.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="064c5-123">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="064c5-123">Additional resources</span></span>

[<span data-ttu-id="064c5-124">Habilitar recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="064c5-124">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="064c5-125">Crear listas mantenidas de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="064c5-125">Create curated product recommendation lists</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="064c5-126">Administrar resultados de recomendaciones de producto basadas en AI-ML</span><span class="sxs-lookup"><span data-stu-id="064c5-126">Manage AI-ML-based product recommendation results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="064c5-127">Agregar listas de recomendaciones a páginas</span><span class="sxs-lookup"><span data-stu-id="064c5-127">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)
