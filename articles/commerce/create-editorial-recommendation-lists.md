---
title: Crear manualmente recomendaciones curadas
description: Este tema explica de qué manera los distribuidores pueden crear y administrar manualmente listas de productos para los clientes de Microsoft Dynamics 365 Commerce.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, eCommerce
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 9826785700dcc1a35e6199b7aeff4e06b6d9da39
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415537"
---
# <a name="manually-create-curated-recommendations"></a><span data-ttu-id="43337-103">Crear manualmente recomendaciones curadas</span><span class="sxs-lookup"><span data-stu-id="43337-103">Manually create curated recommendations</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="43337-104">Este tema explica de qué manera los distribuidores pueden crear y administrar manualmente recomendaciones de productos para los clientes de Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="43337-104">This topic explains how merchandizers can manually create and manage product recommendations lists for Microsoft Dynamics 365 Commerce customers.</span></span>

<span data-ttu-id="43337-105">Las listas mantenidas son colecciones de contenido individual creadas y mantenidas por las personas.</span><span class="sxs-lookup"><span data-stu-id="43337-105">Curated lists are collections of individual content, created and curated by people.</span></span>  

## <a name="create-a-new-list"></a><span data-ttu-id="43337-106">Crear una lista nueva</span><span class="sxs-lookup"><span data-stu-id="43337-106">Create a new list</span></span>

<span data-ttu-id="43337-107">Para crear una lista de recomendaciones de productos mantenida, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="43337-107">To create a curated product recommendation list, follow these steps.</span></span>

1. <span data-ttu-id="43337-108">Vaya a **Retail y Commerce &gt; Recomendaciones de producto &gt; Listas de recomendaciones**.</span><span class="sxs-lookup"><span data-stu-id="43337-108">Go to **Retail and Commerce &gt; Product recommendations &gt; Recommendation lists**.</span></span>
1. <span data-ttu-id="43337-109">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="43337-109">Select **New**.</span></span>
1. <span data-ttu-id="43337-110">En el campo **Id. de lista**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="43337-110">In the **List Id** field, enter a value.</span></span>
1. <span data-ttu-id="43337-111">En el campo **Nombre de la lista**, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="43337-111">In the **List name** field, enter a value.</span></span>
    - <span data-ttu-id="43337-112">El **Nombre de la lista** es el título de la lista que aparecerá en la sección de listas mantenidas del módulo **Colección de productos**.</span><span class="sxs-lookup"><span data-stu-id="43337-112">The **List name** is the title of the list that will appear in the curated lists section of the **Product collection** module.</span></span>
1. <span data-ttu-id="43337-113">Para agregar productos a la lista, seleccione **Agregar productos**.</span><span class="sxs-lookup"><span data-stu-id="43337-113">To add products to the list, select **Add products**.</span></span>
1. <span data-ttu-id="43337-114">Para cambiar el orden de los productos de la lista, especifique un valor en la columna **Orden de visualización**.</span><span class="sxs-lookup"><span data-stu-id="43337-114">To change the order of the products in the list, enter a value in the **Display order** column.</span></span>
    - <span data-ttu-id="43337-115">Si dos productos tienen el mismo valor de orden de visualización, el orden final de estos dos resultados puede ser diferente de la oficina administrativa.</span><span class="sxs-lookup"><span data-stu-id="43337-115">If two products have the same display order value, then the final order of those two results may differ from the back office.</span></span>
1. <span data-ttu-id="43337-116">Seleccione **Guardar** para guardar la lista.</span><span class="sxs-lookup"><span data-stu-id="43337-116">Select **Save** to save the list.</span></span>

## <a name="example-list"></a><span data-ttu-id="43337-117">Lista de ejemplos</span><span class="sxs-lookup"><span data-stu-id="43337-117">Example List</span></span>

![Lista mantenida de ejemplos en oficina administrativa](./media/examplecuratedrecolist.png)

## <a name="additional-resources"></a><span data-ttu-id="43337-119">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="43337-119">Additional resources</span></span>

[<span data-ttu-id="43337-120">Visión general de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="43337-120">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="43337-121">Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="43337-121">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="43337-122">Habilitar recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="43337-122">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="43337-123">Habilitar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="43337-123">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="43337-124">Cancelar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="43337-124">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="43337-125">Habilitar recomendaciones de "comprar looks similares"</span><span class="sxs-lookup"><span data-stu-id="43337-125">Enable "shop similar looks" recommendations</span></span>](shop-similar-looks.md)

[<span data-ttu-id="43337-126">Agregar recomendaciones de producto en PDV</span><span class="sxs-lookup"><span data-stu-id="43337-126">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="43337-127">Agregar recomendaciones a la pantalla de transacción</span><span class="sxs-lookup"><span data-stu-id="43337-127">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="43337-128">Ajuste los resultados de las recomendaciones AI-ML</span><span class="sxs-lookup"><span data-stu-id="43337-128">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="43337-129">Crear recomendaciones con datos de demostración</span><span class="sxs-lookup"><span data-stu-id="43337-129">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="43337-130">Preguntas más frecuentes de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="43337-130">Product recommendations FAQ</span></span>](faq-recommendations.md)
