---
title: Ajustar resultados de recomendaciones de producto basadas en AI-ML
description: Este tema explica cómo ajustar los resultados de recomendaciones de productos según la inteligencia artificial-aprendizaje automático (AI-ML) para tu negocio.
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
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 0b4228583c4a2b89d7139b51880cea0288d7fe49
ms.sourcegitcommit: fdc5dd9eb784c7d8e75692c8cdba083fe0dd87ce
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2020
ms.locfileid: "3404380"
---
# <a name="adjust-ai-ml-based-product-recommendation-results"></a><span data-ttu-id="68ce5-103">Ajustar resultados de recomendaciones de producto basadas en AI-ML</span><span class="sxs-lookup"><span data-stu-id="68ce5-103">Adjust AI-ML-based product recommendation results</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="68ce5-104">En este tema se explica cómo ajustar los resultados de recomendaciones de productos mediante técnicas de inteligencia artificial-aprendizaje automático (AI-ML) para su empresa.</span><span class="sxs-lookup"><span data-stu-id="68ce5-104">This topic explains how to adjust product recommendation results based on artificial intelligence-machine learning (AI-ML) to your business.</span></span> 

<span data-ttu-id="68ce5-105">Tras habilitar las recomendaciones de productos, entrarán en vigor las configuraciones predeterminadas; estos parámetros funcionarán ya que pueden funcionar para muchas necesidades.</span><span class="sxs-lookup"><span data-stu-id="68ce5-105">After enabling product recommendations, the default settings will take effect; these parameters will work for may work for many needs.</span></span> <span data-ttu-id="68ce5-106">Es mejor planificar pasar algún tiempo evaluando si los resultados se ajustan al movimiento de venta de los productos.</span><span class="sxs-lookup"><span data-stu-id="68ce5-106">It is best to plan to spend some time evaluating whether the results fit the selling motion of products.</span></span> <span data-ttu-id="68ce5-107">Sugerimos evaluar los resultados durante varios días antes de cambiar los parámetros según sea necesario antes de probar de nuevo.</span><span class="sxs-lookup"><span data-stu-id="68ce5-107">We suggest evaluating results for a few days before changing parameters as needed before testing again.</span></span> 

## <a name="understanding-recommendation-list-parameters"></a><span data-ttu-id="68ce5-108">Descripción de los parámetros de la lista de recomendaciones</span><span class="sxs-lookup"><span data-stu-id="68ce5-108">Understanding recommendation list parameters</span></span>

<span data-ttu-id="68ce5-109">Antes de cambiar los parámetros, descubra cómo afectarán a los resultados siguientes.</span><span class="sxs-lookup"><span data-stu-id="68ce5-109">Before changing the parameters, learn about how they will affect the results below.</span></span>

### <a name="trending-product-list"></a><span data-ttu-id="68ce5-110">Lista de productos "Tendencias"</span><span class="sxs-lookup"><span data-stu-id="68ce5-110">"Trending" product list</span></span>

<span data-ttu-id="68ce5-111">La lista de productos "Tendencias" tiene dos parámetros que se pueden cambiar:</span><span class="sxs-lookup"><span data-stu-id="68ce5-111">The "Trending" product list has two parameters that can be changed:</span></span>

![Parámetros predeterminados de lista "Tendencias" de ejemplo](./media/exampletrendingparameters.png)

1. <span data-ttu-id="68ce5-113">**Incluir nuevos productos desde los últimos X días**: los productos que se han agregado dentro del número de días especificados antes de la fecha actual se pueden usar en los candidatos de productos seleccionados.</span><span class="sxs-lookup"><span data-stu-id="68ce5-113">**Include new products from last X days** - Products that have been added within the specified number of days before the current date can be used to select product candidates.</span></span> <span data-ttu-id="68ce5-114">El valor predeterminado de la imagen sugiere que los productos con una antigüedad de 180 días se pueden usar en la lista de productos de tendencias.</span><span class="sxs-lookup"><span data-stu-id="68ce5-114">The default value in the picture suggests that products as old has 180 days can be used in the trending product list.</span></span>
1. <span data-ttu-id="68ce5-115">**Incluir ventas de los últimos X días**: las transacciones de ventas que se han producido dentro del número de días especificados antes de la fecha actual se pueden usar para pedir productos.</span><span class="sxs-lookup"><span data-stu-id="68ce5-115">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="68ce5-116">El valor predeterminado anterior sugiere que todas las compras realizadas de un producto en los últimos 30 días se utilizarían para determinar la posición del producto en la lista de productos de tendencias.</span><span class="sxs-lookup"><span data-stu-id="68ce5-116">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the trending product list.</span></span> 

### <a name="best-selling-product-list"></a><span data-ttu-id="68ce5-117">Lista de productos "Más vendidos"</span><span class="sxs-lookup"><span data-stu-id="68ce5-117">"Best selling" product list</span></span>

<span data-ttu-id="68ce5-118">Según su empresa, la lista "Más vendidos" puede llevar diferentes resultados a las tendencias, aunque ambos usen datos de transacción para pedir productos.</span><span class="sxs-lookup"><span data-stu-id="68ce5-118">Depending on your business, the "Best selling" list can bring different results than trending, even though they both use transaction data to order products.</span></span> <span data-ttu-id="68ce5-119">Dado que Más vendidos no tiene límite según la fecha de selección, Más vendidos todavía puede resaltar los productos más antiguos y muy populares que puedan haberse quitado de la lista de tendencias.</span><span class="sxs-lookup"><span data-stu-id="68ce5-119">Because best selling has no cut off based on assortment date, Best selling can still highlight very popular, older products that might have been dropped from the trending list.</span></span> 

<span data-ttu-id="68ce5-120">La lista de productos "Más vendidos" tiene un parámetro que se puede cambiar:</span><span class="sxs-lookup"><span data-stu-id="68ce5-120">The "Best selling" product list has one parameter that can be changed:</span></span>

![Parámetro predeterminado de lista Más vendidos de ejemplo](./media/examplebestsellingparameters.PNG)

1. <span data-ttu-id="68ce5-122">**Incluir ventas de los últimos X días**: las transacciones de ventas que se han producido dentro del número de días especificados antes de la fecha actual se pueden usar para pedir productos.</span><span class="sxs-lookup"><span data-stu-id="68ce5-122">**Include sales from last X days** - Sales transactions that have occurred within the specified number of days before the current date can be used to order the products.</span></span> <span data-ttu-id="68ce5-123">El valor predeterminado anterior sugiere que todas las compras realizadas de un producto en los últimos 30 días se utilizarían para determinar la posición del producto en la lista de productos Más vendidos.</span><span class="sxs-lookup"><span data-stu-id="68ce5-123">The default value above suggests that all purchases made of a product in the last 30 days would be used to determine the placement of the product in the Best selling product list.</span></span> 

## <a name="manually-add-or-remove-products-from-recommendation-lists"></a><span data-ttu-id="68ce5-124">Agregar o quitar productos de listas de recomendación</span><span class="sxs-lookup"><span data-stu-id="68ce5-124">Manually add or remove products from recommendation lists</span></span>

### <a name="for-new-trending-or-best-selling-lists"></a><span data-ttu-id="68ce5-125">Para lista "Nuevos", "Tendencias" o "Más vendidos"</span><span class="sxs-lookup"><span data-stu-id="68ce5-125">For "New," "Trending," or "Best selling" lists</span></span>

1.  <span data-ttu-id="68ce5-126">Vaya a **Retail y Commerce** > **Recomendaciones de producto** > **Parámetros de recomendaciones**.</span><span class="sxs-lookup"><span data-stu-id="68ce5-126">Go to **Retail and Commerce** > **Product recommendations** > **Recommendation parameters**.</span></span>
1.  <span data-ttu-id="68ce5-127">En la lista de parámetros compartidos, seleccione **Listas de recomendaciones**.</span><span class="sxs-lookup"><span data-stu-id="68ce5-127">In the list of shared parameters, select **Recommendation lists**.</span></span>
1.  <span data-ttu-id="68ce5-128">Seleccione la lista desde la que agregar o quitar productos.</span><span class="sxs-lookup"><span data-stu-id="68ce5-128">Select the list add or remove products from.</span></span>
1.  <span data-ttu-id="68ce5-129">Para agregar productos a la tabla, seleccione **Agregar línea**.</span><span class="sxs-lookup"><span data-stu-id="68ce5-129">To add products to the table, select **Add line.**</span></span> 
1.  <span data-ttu-id="68ce5-130">En la columna Producto, busque un producto por **Nombre** o **Número de producto**.</span><span class="sxs-lookup"><span data-stu-id="68ce5-130">Under the Product column, search for a product by **Name** or **Product number.**</span></span>

    ![Ejemplo de búsqueda de un producto en la lista Nuevo producto](./media/examplenewlistconfiguration1.png)

1.  <span data-ttu-id="68ce5-132">En la columna Tipo de línea, seleccione una de dos opciones:</span><span class="sxs-lookup"><span data-stu-id="68ce5-132">Under the Line type column, select one of two options:</span></span>
    -   <span data-ttu-id="68ce5-133">**Incluir**: fuerza un producto a la parte delantera de la lista</span><span class="sxs-lookup"><span data-stu-id="68ce5-133">**Include** – forces a product to the front of the list</span></span>
    -   <span data-ttu-id="68ce5-134">**Excluir** hace que un producto no aparezca en la lista.</span><span class="sxs-lookup"><span data-stu-id="68ce5-134">**Exclude** – removes a product from appearing in the list</span></span>
    
    ![Ejemplo de inclusión o exclusión de un producto de la lista Nuevo producto](./media/examplenewlistconfiguration2.png)

1.  <span data-ttu-id="68ce5-136">Al cambiar el **Orden de visualización** se cambiará el orden en que los productos marcados con **incluir** aparecerán en la lista.</span><span class="sxs-lookup"><span data-stu-id="68ce5-136">Changing the **Display order** will change the order that products marked **include** will appear in the list.</span></span>
    - <span data-ttu-id="68ce5-137">Si dos productos tienen el mismo valor de **orden de visualización**, el orden final de estos dos resultados puede ser diferente de la oficina administrativa.</span><span class="sxs-lookup"><span data-stu-id="68ce5-137">If two products have the same **display order** value, then the final order of those two results may differ from the back office.</span></span>
1.  <span data-ttu-id="68ce5-138">Para quitar productos de la tabla: seleccione la línea que desee quitar y seleccione **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="68ce5-138">To remove products from the table: select the line to remove and select **Remove**.</span></span>


### <a name="for-people-also-like-or-frequently-bought-together-lists"></a><span data-ttu-id="68ce5-139">Para las listas "A la gente también le gustó" o "Los usuarios que compraron esto también compraron"</span><span class="sxs-lookup"><span data-stu-id="68ce5-139">For "People also like" or "Frequently bought together" lists</span></span>

<span data-ttu-id="68ce5-140">En el contexto de las listas "Los usuarios que compraron esto también compraron" o "A la gente también le gustó", se utiliza el aprendizaje automático para analizar patrones de compra de consumo para recomendar productos relacionados comprados habitualmente juntos para un producto único de inicialización.</span><span class="sxs-lookup"><span data-stu-id="68ce5-140">In the context of "Frequently bought together" or "People also like" lists, machine learning is used to analyze consumer purchase patterns to recommend related products commonly purchased together for a unique seed product.</span></span> 
 
<span data-ttu-id="68ce5-141">Un *producto de inicialización* es el producto para el que desea generar resultados.</span><span class="sxs-lookup"><span data-stu-id="68ce5-141">A *seed product* is the product you want to generate results for.</span></span> <span data-ttu-id="68ce5-142">En el contexto de ajustar manualmente listas de recomendaciones, agrega o elimina resultados para este producto.</span><span class="sxs-lookup"><span data-stu-id="68ce5-142">In the context of manually adjusting recommendation lists, you are adding or removing results for this product.</span></span> 

<span data-ttu-id="68ce5-143">Siga estos pasos para agregar o eliminar manualmente los resultados para un producto de inicialización:</span><span class="sxs-lookup"><span data-stu-id="68ce5-143">Follow these steps to manually add or remove results for a seed product:</span></span>
1.  <span data-ttu-id="68ce5-144">Seleccione el **Producto de inicialización**.</span><span class="sxs-lookup"><span data-stu-id="68ce5-144">Select the **Seed product**.</span></span> 
1.  <span data-ttu-id="68ce5-145">En la columna **Producto**, busque un producto por **Nombre** o **Número de producto.**
![Ejemplo de buscar un producto en la lista Los usuarios que compraron esto también compraron](./media/exampleFBTlistconfiguration1.png)</span><span class="sxs-lookup"><span data-stu-id="68ce5-145">Under the **Product** column, search for a product by **Name** or **Product number.**
![Example of searching for a product on the Frequently bought together list](./media/exampleFBTlistconfiguration1.png)</span></span>
1. <span data-ttu-id="68ce5-146">En la columna **Tipo de línea**, seleccione una de dos opciones:</span><span class="sxs-lookup"><span data-stu-id="68ce5-146">Under the **Line type** column, select one of two options:</span></span>
    - <span data-ttu-id="68ce5-147">**Incluir**: fuerza un producto a la parte delantera de la lista</span><span class="sxs-lookup"><span data-stu-id="68ce5-147">**Include** – forces a product to the front of the list</span></span>
    - <span data-ttu-id="68ce5-148">**Excluir** hace que un producto no aparezca en la lista.</span><span class="sxs-lookup"><span data-stu-id="68ce5-148">**Exclude** – removes a product from appearing in the list</span></span>     
<span data-ttu-id="68ce5-149">![Ejemplo de incluir o excluir un producto en la lista Los usuarios que compraron esto también compraron](./media/exampleFBTlistconfiguration2.png)</span><span class="sxs-lookup"><span data-stu-id="68ce5-149">![Example of Including or Excluding a product on the Frequently bought together list](./media/exampleFBTlistconfiguration2.png)</span></span>
1.  <span data-ttu-id="68ce5-150">Para quitar productos de la tabla: seleccione la línea que desee quitar y seleccione Eliminar.</span><span class="sxs-lookup"><span data-stu-id="68ce5-150">To remove products from the table: select the line to remove and select Remove.</span></span>


## <a name="additional-resources"></a><span data-ttu-id="68ce5-151">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="68ce5-151">Additional resources</span></span>

[<span data-ttu-id="68ce5-152">Visión general de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="68ce5-152">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="68ce5-153">Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="68ce5-153">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="68ce5-154">Habilitar recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="68ce5-154">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="68ce5-155">Habilitar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="68ce5-155">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="68ce5-156">Cancelar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="68ce5-156">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="68ce5-157">Agregar recomendaciones de producto en PDV</span><span class="sxs-lookup"><span data-stu-id="68ce5-157">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="68ce5-158">Agregar recomendaciones a la pantalla de transacción</span><span class="sxs-lookup"><span data-stu-id="68ce5-158">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="68ce5-159">Crear manualmente recomendaciones curadas</span><span class="sxs-lookup"><span data-stu-id="68ce5-159">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="68ce5-160">Crear recomendaciones con datos de demostración</span><span class="sxs-lookup"><span data-stu-id="68ce5-160">Create recommendations with demo data</span></span>](product-recommendations-demo-data.md)

[<span data-ttu-id="68ce5-161">Preguntas más frecuentes de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="68ce5-161">Product recommendations FAQ</span></span>](faq-recommendations.md)
