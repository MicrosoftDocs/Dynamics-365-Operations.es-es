---
title: Crear recomendaciones con datos de demostración
description: Este tema ofrece instrucciones acerca de cómo aprovechar las recomendaciones de producto de omnicanal en entornos de un solo cuadro de nivel 1 utilizando datos de demostración personalizables y ya cumplimentados.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 59b4dd7a29af739d92a20f6fe55eff9f201fcb6d
ms.sourcegitcommit: ac47e8679fb104515f7dcca509294264bd05d2b1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/15/2020
ms.locfileid: "3454565"
---
# <a name="create-recommendations-with-demo-data"></a><span data-ttu-id="c6ca4-103">Crear recomendaciones con datos de demostración</span><span class="sxs-lookup"><span data-stu-id="c6ca4-103">Create recommendations with demo data</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="c6ca4-104">Este tema ofrece instrucciones acerca de cómo aprovechar las recomendaciones de producto de omnicanal en entornos de un solo cuadro de nivel 1 utilizando datos de demostración personalizables y ya cumplimentados.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-104">This topic provides guidance on how to leverage omni-channel product recommendations in Tier-1 single box environments using pre-populated, customizable demo data.</span></span>

<span data-ttu-id="c6ca4-105">Las recomendaciones de producto omnicanal proporcionan un conjunto de listas de productos generadas por programación o de forma dirigida.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-105">Omni-channel product recommendations provide a set of editorially curated or programmatically generated list of products.</span></span> <span data-ttu-id="c6ca4-106">Estas listas se pueden usar en varias situaciones, en función de la necesidad empresarial.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-106">These lists can be used in several scenarios, depending on the business need.</span></span> <span data-ttu-id="c6ca4-107">Para obtener más información sobre las listas de recomendaciones del producto, consulte [Información general sobre las recomendaciones del producto](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="c6ca4-107">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

<span data-ttu-id="c6ca4-108">Para entornos de Dynamics 365 de nivel 2 y superior, las recomendaciones de productos se calculan automáticamente en función de los datos del cliente.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-108">For Tier-2 and higher Dynamics 365 environments, product recommendations are automatically computed based on customer data.</span></span> <span data-ttu-id="c6ca4-109">El uso de datos de demostración para recomendaciones de productos no deshabilita ninguna solución de recomendación de productos ya aprovisionada en el entorno ni los costes vinculados a su uso.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-109">Using product recommendations demo data does not disable any product recommendations solution already provisioned in the environment and any costs associated with its usage.</span></span>

<span data-ttu-id="c6ca4-110">Para entornos de nivel 1, las recomendaciones de productos solo se basan en datos estáticos de demostración almacenados en un archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-110">For Tier-1 environments, product recommendations are based only off the static demo data stored in a .csv file.</span></span>

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a><span data-ttu-id="c6ca4-111">Habilitar datos de demostración de productos en un entorno</span><span class="sxs-lookup"><span data-stu-id="c6ca4-111">Enabling product recommendations demo data in an environment</span></span>
<span data-ttu-id="c6ca4-112">Para habilitar datos de demostración para recomendaciones de productos, tiene que implementar la Extensión de demostración de vista previa de Dynamics 365 Commerce para el entorno respectivo.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-112">To enable product recommendations demo date, you need to deploy the Dynamics 365 Commerce Preview Demo Extension to the respective environment.</span></span> <span data-ttu-id="c6ca4-113">Hacerlo automáticamente habilita los datos de demostración de recomendaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-113">Doing so automatically enables product recommendations demo data.</span></span>

## <a name="default-demo-data"></a><span data-ttu-id="c6ca4-114">Datos de demostración predeterminados</span><span class="sxs-lookup"><span data-stu-id="c6ca4-114">Default demo data</span></span>
<span data-ttu-id="c6ca4-115">Cada entorno de tipo OneBox incorpora un conjunto preinstalado de datos de demostración para recomendaciones de productos almacenado en el archivo separado por comas “reco_demo_data.csv”, que se encuentra en Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-115">Each OneBox type environment comes with a preloaded set of product recommendations demo data stored in the coma separated 'reco_demo_data.csv' file, located on the Commerce Scale Unit.</span></span>

<span data-ttu-id="c6ca4-116">Los datos se estructuran en las siguientes columnas.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-116">The data is structured along the following columns.</span></span>

| <span data-ttu-id="c6ca4-117">Nombre columna</span><span class="sxs-lookup"><span data-stu-id="c6ca4-117">Column name</span></span>         | <span data-ttu-id="c6ca4-118">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="c6ca4-118">Mandatory</span></span>          | <span data-ttu-id="c6ca4-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="c6ca4-119">Description</span></span>                                                                                                                                 | <span data-ttu-id="c6ca4-120">Valores posibles</span><span class="sxs-lookup"><span data-stu-id="c6ca4-120">Possible values</span></span>                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| <span data-ttu-id="c6ca4-121">RecoList</span><span class="sxs-lookup"><span data-stu-id="c6ca4-121">RecoList</span></span>            | :heavy_check_mark: | <span data-ttu-id="c6ca4-123">El tipo de lista específico de recomendaciones de productos que el punto de datos de demostración va a generar.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-123">The specific product recommendation list type that the demo data point is to generate.</span></span>                                                    | <ul><li><span data-ttu-id="c6ca4-124">RecoBestSelling</span><span class="sxs-lookup"><span data-stu-id="c6ca4-124">RecoBestSelling</span></span></li><li><span data-ttu-id="c6ca4-125">RecoNew</span><span class="sxs-lookup"><span data-stu-id="c6ca4-125">RecoNew</span></span></li><li><span data-ttu-id="c6ca4-126">RecoTrending</span><span class="sxs-lookup"><span data-stu-id="c6ca4-126">RecoTrending</span></span></li><li><span data-ttu-id="c6ca4-127">RecoCart</span><span class="sxs-lookup"><span data-stu-id="c6ca4-127">RecoCart</span></span></li><li><span data-ttu-id="c6ca4-128">RecoPeopleAlsoBuy</span><span class="sxs-lookup"><span data-stu-id="c6ca4-128">RecoPeopleAlsoBuy</span></span></li></ul> |
| <span data-ttu-id="c6ca4-129">OperatingUnitNumber</span><span class="sxs-lookup"><span data-stu-id="c6ca4-129">OperatingUnitNumber</span></span> | :heavy_check_mark: | <span data-ttu-id="c6ca4-131">El número de unidad operativa específico donde se espera que aparezcan las recomendaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-131">The specific operating unit number where product recommendations are expected to be   surfaced.</span></span>                                        |                                                                              |
| <span data-ttu-id="c6ca4-132">Categoría</span><span class="sxs-lookup"><span data-stu-id="c6ca4-132">Category</span></span>            |                    |    <span data-ttu-id="c6ca4-133">La categoría para la que debe devolverse la lista específica.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-133">The category the specific list should be returned for.</span></span> <span data-ttu-id="c6ca4-134">Si no se especifica ninguna categoría, la lista es solo para los primeros elementos de la jerarquía de navegación.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-134">If no category is specified, the list is for top of navigation hierarchy only.</span></span>    |                                                                              |
| <span data-ttu-id="c6ca4-135">SeedItemId</span><span class="sxs-lookup"><span data-stu-id="c6ca4-135">SeedItemId</span></span>          |                    |    <span data-ttu-id="c6ca4-136">Para las listas que requieren inicialización (RecoPeopleAlsoBuy y RecoCart), el producto para el que esas listas deben mostrar productos adicionales.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-136">For lists that require seed (RecoPeopleAlsoBuy and RecoCart), the product those lists should show additional products for.</span></span>            |                                                                              |
| <span data-ttu-id="c6ca4-137">CustomerId</span><span class="sxs-lookup"><span data-stu-id="c6ca4-137">CustomerId</span></span>          |                    |    <span data-ttu-id="c6ca4-138">Para listas que requieren un identificador de cliente (RecoPicks).</span><span class="sxs-lookup"><span data-stu-id="c6ca4-138">For lists that require a customer identifier (RecoPicks).</span></span>  <span data-ttu-id="c6ca4-139">El valor predeterminado '0' se aplica a todos los clientes.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-139">The default value '0' applies to all customers.</span></span>          |                                                                              |
| <span data-ttu-id="c6ca4-140">ItemIds</span><span class="sxs-lookup"><span data-stu-id="c6ca4-140">ItemIds</span></span>             | :heavy_check_mark: | <span data-ttu-id="c6ca4-142">Uno o más productos que se devolverán como resultado, separados por signos de punto y coma.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-142">One or more products to be returned as the result, separated by ';'.</span></span>                                                                  |                                                                              |

## <a name="customize-demo-data"></a><span data-ttu-id="c6ca4-143">Personalizar datos de demostración</span><span class="sxs-lookup"><span data-stu-id="c6ca4-143">Customize demo data</span></span>
<span data-ttu-id="c6ca4-144">Puede editar los datos predeterminados de prueba con cualquier información de producto y categoría que se configure en la sede.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-144">You can edit the default demo data with any product and category information configured in HQ.</span></span> <span data-ttu-id="c6ca4-145">Después de actualizar el .csv, las recomendaciones de productos devueltas para los clientes inmediatamente reflejarán los cambios.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-145">After you update the .csv, the product recommendations that are returned to customers will immediately reflect the changes.</span></span>

<span data-ttu-id="c6ca4-146">La extensión contiene un archivo de datos denominado "RecoMockDataset.csv", que le permite controlar el conjunto de datos usado para activar los resultados de las recomendaciones simuladas.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-146">The extension contains a datafile called 'RecoMockDataset.csv', which allows you to control the dataset used to power the mock recommendations results.</span></span> <span data-ttu-id="c6ca4-147">El nombre de archivo se puede controlar con la configuración de la extensión mediante la configuración **ext.Recommendations.DemoFilePath**.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-147">The file name can be controlled through extension configuration using the **ext.Recommendations.DemoFilePath** setting.</span></span> <span data-ttu-id="c6ca4-148">Esto le permite disponer de varios conjuntos de datos que se pueden intercambiar fácilmente entre ellos a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="c6ca4-148">This enables you to have multiple datasets available that can be switched between easily through configuration.</span></span>


```xml
<settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
</settings>
```

## <a name="additional-resources"></a><span data-ttu-id="c6ca4-149">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="c6ca4-149">Additional resources</span></span>

[<span data-ttu-id="c6ca4-150">Visión general de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="c6ca4-150">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="c6ca4-151">Habilitar Azure Data Lake Storage en un entorno Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="c6ca4-151">Enable Azure Data Lake Storage in a Dynamics 365 Commerce environment</span></span>](enable-adls-environment.md)

[<span data-ttu-id="c6ca4-152">Habilitar recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="c6ca4-152">Enable product recommendations</span></span>](enable-product-recommendations.md)

[<span data-ttu-id="c6ca4-153">Habilitar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="c6ca4-153">Enable personalized recommendations</span></span>](personalized-recommendations.md)

[<span data-ttu-id="c6ca4-154">Cancelar recomendaciones personalizadas</span><span class="sxs-lookup"><span data-stu-id="c6ca4-154">Opt out of personalized recommendations</span></span>](personalization-gdpr.md)

[<span data-ttu-id="c6ca4-155">Agregar recomendaciones de producto en PDV</span><span class="sxs-lookup"><span data-stu-id="c6ca4-155">Add product recommendations on POS</span></span>](product.md)

[<span data-ttu-id="c6ca4-156">Agregar recomendaciones a la pantalla de transacción</span><span class="sxs-lookup"><span data-stu-id="c6ca4-156">Add recommendations to the transaction screen</span></span>](add-recommendations-control-pos-screen.md)

[<span data-ttu-id="c6ca4-157">Ajuste los resultados de las recomendaciones AI-ML</span><span class="sxs-lookup"><span data-stu-id="c6ca4-157">Adjust AI-ML recommendations results</span></span>](modify-product-recommendation-results.md)

[<span data-ttu-id="c6ca4-158">Crear manualmente recomendaciones curadas</span><span class="sxs-lookup"><span data-stu-id="c6ca4-158">Manually create curated recommendations</span></span>](create-editorial-recommendation-lists.md)

[<span data-ttu-id="c6ca4-159">Preguntas más frecuentes de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="c6ca4-159">Product recommendations FAQ</span></span>](faq-recommendations.md)
