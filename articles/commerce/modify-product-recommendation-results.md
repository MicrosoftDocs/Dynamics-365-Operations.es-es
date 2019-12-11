---
title: Administrar resultados de recomendaciones de producto basadas en AI-ML
description: Este tema explica cómo ajustar los resultados de recomendaciones de productos según la inteligencia artificial-aprendizaje automático (AI-ML) para tu negocio.
author: bebeale
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
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 669b056c38614c8ac9be2d7b244a0ab0c73bc9f8
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770079"
---
# <a name="manage-ai-ml-based-product-recommendation-results"></a><span data-ttu-id="1c436-103">Administrar resultados de recomendaciones de producto basadas en AI-ML</span><span class="sxs-lookup"><span data-stu-id="1c436-103">Manage AI-ML-based product recommendation results</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="1c436-104">Este tema explica cómo ajustar los resultados de recomendaciones de productos según la inteligencia artificial-aprendizaje automático (AI-ML) para tu negocio.</span><span class="sxs-lookup"><span data-stu-id="1c436-104">This topic explains how to tailor product recommendation results based on artificial intelligence-machine learning (AI-ML) to your business.</span></span> 

<span data-ttu-id="1c436-105">Tras habilitar las recomendaciones de productos, entrarán en vigor las configuraciones predeterminadas; estos parámetros funcionarán ya que pueden funcionar para muchas necesidades.</span><span class="sxs-lookup"><span data-stu-id="1c436-105">After enabling product recommendations, the default settings will take effect; these parameters will work for may work for many needs.</span></span> <span data-ttu-id="1c436-106">Es mejor planificar pasar algún tiempo evaluando si los resultados se ajustan al movimiento de venta de los productos.</span><span class="sxs-lookup"><span data-stu-id="1c436-106">It is best to plan to spend some time evaluating whether the results fit the selling motion of products.</span></span> <span data-ttu-id="1c436-107">Sugerimos evaluar los resultados durante varios días antes de cambiar los parámetros según sea necesario antes de probar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="1c436-107">We suggest evaluating results for a few days before changing parameters as needed before testing again.</span></span> 

## <a name="understanding-recommendation-list-parameters"></a><span data-ttu-id="1c436-108">Descripción de los parámetros de la lista de recomendaciones</span><span class="sxs-lookup"><span data-stu-id="1c436-108">Understanding recommendation list parameters</span></span>

<span data-ttu-id="1c436-109">Antes de cambiar los parámetros, descubra cómo afectarán a los resultados siguientes.</span><span class="sxs-lookup"><span data-stu-id="1c436-109">Before changing the parameters, learn about how they will affect the results below.</span></span>

### <a name="trending-product-list"></a><span data-ttu-id="1c436-110">Lista de productos de tendencias</span><span class="sxs-lookup"><span data-stu-id="1c436-110">Trending product list</span></span>

<span data-ttu-id="1c436-111">La lista de producto **Tendencias** tiene dos parámetros que se puedan cambiar: ![Parámetros predeterminados de la lista Tendencias de ejemplo](./media/exampletrendingparameters.png)</span><span class="sxs-lookup"><span data-stu-id="1c436-111">The **Trending** product list has two parameters that can be changed: ![Example Trending list default parameters](./media/exampletrendingparameters.png)</span></span>
1. <span data-ttu-id="1c436-112">**Incluir nuevos productos desde los últimos X días**: los productos que se han agregado dentro del número de días especificados antes de la fecha actual se pueden usar en los candidatos de productos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="1c436-112">**Include new products from last X days** - Products that have been added within the specified number of days before the current date can be used to select product candidates.</span></span> <span data-ttu-id="1c436-113">El valor predeterminado de la imagen sugiere que los productos con una antigüedad de 180 días se pueden usar en la lista de productos de tendencias.</span><span class="sxs-lookup"><span data-stu-id="1c436-113">The default value in the picture suggests that products as old has 180 days can be used in the trending product list.</span></span>
1. <span data-ttu-id="1c436-114">**Incluir ventas de los últimos X días**: las transacciones de ventas que se han producido dentro del número de días especificados antes de la fecha actual se pueden usar para pedir productos.</span><span class="sxs-lookup"><span data-stu-id="1c436-114">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="1c436-115">El valor predeterminado anterior sugiere que todas las compras realizadas de un producto en los últimos 30 días se utilizarían para determinar la posición del producto en la lista de productos de tendencias.</span><span class="sxs-lookup"><span data-stu-id="1c436-115">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the trending product list.</span></span> 

### <a name="best-selling-product-list"></a><span data-ttu-id="1c436-116">Lista de productos Más vendidos</span><span class="sxs-lookup"><span data-stu-id="1c436-116">Best selling product list</span></span>

<span data-ttu-id="1c436-117">Según su empresa, Más vendidos puede llevar diferentes resultados a las tendencias, aunque ambos usen datos de transacción para pedir productos.</span><span class="sxs-lookup"><span data-stu-id="1c436-117">Depending on your business, Best selling can bring different results than trending, even though they both use transaction data to order products.</span></span> <span data-ttu-id="1c436-118">Dado que Más vendidos no tiene límite según la fecha de selección, Más vendidos todavía puede resaltar los productos más antiguos y muy populares que puedan haberse quitado de la lista de tendencias.</span><span class="sxs-lookup"><span data-stu-id="1c436-118">Because best selling has no cut off based on assortment date, Best selling can still highlight very popular, older products that might have been dropped from the trending list.</span></span> 

<span data-ttu-id="1c436-119">La lista de productos **Más vendidos** tiene un parámetro que se puede cambiar:</span><span class="sxs-lookup"><span data-stu-id="1c436-119">The **Best selling** product list has one parameter that can be changed:</span></span>

![Parámetro predeterminado de lista Más vendidos de ejemplo](./media/examplebestsellingparameters.PNG)
1. <span data-ttu-id="1c436-121">**Incluir ventas de los últimos X días**: las transacciones de ventas que se han producido dentro del número de días especificados antes de la fecha actual se pueden usar para pedir productos.</span><span class="sxs-lookup"><span data-stu-id="1c436-121">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="1c436-122">El valor predeterminado anterior sugiere que todas las compras realizadas de un producto en los últimos 30 días se utilizarían para determinar la posición del producto en la lista de productos Más vendidos.</span><span class="sxs-lookup"><span data-stu-id="1c436-122">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the Best selling product list.</span></span> 

## <a name="manually-add-or-remove-products-from-recommendation-lists"></a><span data-ttu-id="1c436-123">Agregar o quitar productos de listas de recomendación</span><span class="sxs-lookup"><span data-stu-id="1c436-123">Manually add or remove products from recommendation lists</span></span>

### <a name="for-new-trending-or-best-selling"></a><span data-ttu-id="1c436-124">Para Nuevos, Tendencias o Más vendidos</span><span class="sxs-lookup"><span data-stu-id="1c436-124">For New, Trending, or Best selling</span></span>

1.  <span data-ttu-id="1c436-125">Vaya a  **Retail** > **Recomendaciones de producto** > **Parámetros de recomendaciones**.</span><span class="sxs-lookup"><span data-stu-id="1c436-125">Go to **Retail** > **Product recommendations** > **Recommendation parameters**.</span></span>
1.  <span data-ttu-id="1c436-126">En la lista de parámetros compartidos comerciales, seleccione **Listas de recomendaciones**.</span><span class="sxs-lookup"><span data-stu-id="1c436-126">In the list of retail shared parameters, select **Recommendation lists**.</span></span>
1.  <span data-ttu-id="1c436-127">Seleccione la lista desde la que agregar o quitar productos.</span><span class="sxs-lookup"><span data-stu-id="1c436-127">Select the list add or remove products from.</span></span>
1.  <span data-ttu-id="1c436-128">Para agregar productos a la tabla, seleccione **Agregar línea**.</span><span class="sxs-lookup"><span data-stu-id="1c436-128">To add products to the table, select **Add line.**</span></span> 
1.  <span data-ttu-id="1c436-129">En la columna Producto, busque un producto por **Nombre** o **Número de producto**.
![Ejemplo de buscar un producto en la lista Nuevo producto](./media/examplenewlistconfiguration1.png)</span><span class="sxs-lookup"><span data-stu-id="1c436-129">Under the Product column, search for a product by **Name** or **Product number.**
![Example of searching for a product on the New product list](./media/examplenewlistconfiguration1.png)</span></span>
1.  <span data-ttu-id="1c436-130">En la columna Tipo de línea, seleccione una de dos opciones:</span><span class="sxs-lookup"><span data-stu-id="1c436-130">Under the Line type column, select one of two options:</span></span>
    -   <span data-ttu-id="1c436-131">**Incluir**: fuerza un producto a la parte delantera de la lista</span><span class="sxs-lookup"><span data-stu-id="1c436-131">**Include** – forces a product to the front of the list</span></span>
    -   <span data-ttu-id="1c436-132">**Excluir**: hace que un producto no aparezca en la lista ![Ejemplo de incluir o excluir un producto de la lista Nuevo producto](./media/examplenewlistconfiguration2.png)</span><span class="sxs-lookup"><span data-stu-id="1c436-132">**Exclude** – removes a product from appearing in the list ![Example of Including or Excluding a product from the New product list](./media/examplenewlistconfiguration2.png)</span></span>
1.  <span data-ttu-id="1c436-133">Al cambiar el **Orden de visualización** se cambiará el orden en que los productos marcados con **incluir** aparecerán en la lista.</span><span class="sxs-lookup"><span data-stu-id="1c436-133">Changing the **Display order** will change the order that products marked **include** will appear in the list.</span></span>
    - <span data-ttu-id="1c436-134">Si dos productos tienen el mismo valor de **orden de visualización**, el orden final de estos dos resultados puede ser diferente de la oficina administrativa.</span><span class="sxs-lookup"><span data-stu-id="1c436-134">If two products have the same **display order** value, then the final order of those two results may differ from the back office.</span></span>
1.  <span data-ttu-id="1c436-135">Para quitar productos de la tabla: seleccione la línea que desee quitar y seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="1c436-135">To remove products from the table: select the line to remove and select **Remove**.</span></span>


### <a name="for-people-also-like-or-frequently-bought-together-lists"></a><span data-ttu-id="1c436-136">Para la lista A la gente también le gustó o Los usuarios que compraron esto también compraron</span><span class="sxs-lookup"><span data-stu-id="1c436-136">For People also like or Frequently bought together lists</span></span>

<span data-ttu-id="1c436-137">En el contexto de las listas **Los usuarios que compraron esto también compraron** o **A la gente también le gustó**, se utiliza el aprendizaje automático para analizar patrones de compra de consumo para recomendar productos relacionados comprados habitualmente juntos para un producto único de inicialización.</span><span class="sxs-lookup"><span data-stu-id="1c436-137">In the context of **Frequently bought together** or **People also like** lists, machine learning is used to analyze consumer purchase patterns to recommend related products commonly purchased together for a unique seed product.</span></span> 
 
<span data-ttu-id="1c436-138">Un **producto de inicialización** es el producto para el que desea generar resultados.</span><span class="sxs-lookup"><span data-stu-id="1c436-138">A **seed product** is the product you want to generate results for.</span></span> <span data-ttu-id="1c436-139">En el contexto de ajustar manualmente listas de recomendaciones, agrega o elimina resultados para este producto.</span><span class="sxs-lookup"><span data-stu-id="1c436-139">In the context of manually adjusting recommendation lists, you are adding or removing results for this product.</span></span> 

<span data-ttu-id="1c436-140">Siga estos pasos para agregar o eliminar manualmente los resultados para un producto de inicialización:</span><span class="sxs-lookup"><span data-stu-id="1c436-140">Follow these steps to manually add or remove results for a seed product:</span></span>
1.  <span data-ttu-id="1c436-141">Seleccione el **Producto de inicialización**.</span><span class="sxs-lookup"><span data-stu-id="1c436-141">Select the **Seed product**.</span></span> 
1.  <span data-ttu-id="1c436-142">En la columna **Producto**, busque un producto por **Nombre** o **Número de producto.**
![Ejemplo de buscar un producto en la lista Los usuarios que compraron esto también compraron](./media/exampleFBTlistconfiguration1.png)</span><span class="sxs-lookup"><span data-stu-id="1c436-142">Under the **Product** column, search for a product by **Name** or **Product number.**
![Example of searching for a product on the Frequently bought together list](./media/exampleFBTlistconfiguration1.png)</span></span>
1. <span data-ttu-id="1c436-143">En la columna **Tipo de línea**, seleccione una de dos opciones:</span><span class="sxs-lookup"><span data-stu-id="1c436-143">Under the **Line type** column, select one of two options:</span></span>
    - <span data-ttu-id="1c436-144">**Incluir**: fuerza un producto a la parte delantera de la lista</span><span class="sxs-lookup"><span data-stu-id="1c436-144">**Include** – forces a product to the front of the list</span></span>
    - <span data-ttu-id="1c436-145">**Excluir** hace que un producto no aparezca en la lista.</span><span class="sxs-lookup"><span data-stu-id="1c436-145">**Exclude** – removes a product from appearing in the list</span></span>     
<span data-ttu-id="1c436-146">![Ejemplo de incluir o excluir un producto en la lista Los usuarios que compraron esto también compraron](./media/exampleFBTlistconfiguration2.png)</span><span class="sxs-lookup"><span data-stu-id="1c436-146">![Example of Including or Excluding a product on the Frequently bought together list](./media/exampleFBTlistconfiguration2.png)</span></span>
1.  <span data-ttu-id="1c436-147">Para quitar productos de la tabla: seleccione la línea que desee quitar y seleccione Eliminar.</span><span class="sxs-lookup"><span data-stu-id="1c436-147">To remove products from the table: select the line to remove and select Remove.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="1c436-148">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="1c436-148">Additional resources</span></span>

[<span data-ttu-id="1c436-149">Visión general de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="1c436-149">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="1c436-150">Habilitar recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="1c436-150">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="1c436-151">Agregar listas de recomendaciones a páginas</span><span class="sxs-lookup"><span data-stu-id="1c436-151">Add product recommendation lists to pages</span></span>](add-reco-list-to-page.md)
