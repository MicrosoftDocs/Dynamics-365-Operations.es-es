---
title: Obtener recomendaciones de producto mediante datos de prueba
description: Este documento ofrece instrucciones acerca de cómo aprovechar las recomendaciones de producto de omnicanal en entornos de un solo cuadro de nivel 1 utilizando datos de demostración personalizables y ya cumplimentados.
author: bebeale
manager: AnnBe
ms.date: 10/01/19
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
ms.openlocfilehash: 6abac72b7530dc7b82c8e95faebdce791cf7dbd1
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3003243"
---
# <a name="get-product-recommendations-using-demo-data"></a><span data-ttu-id="55939-103">Obtener recomendaciones de producto mediante datos de prueba</span><span class="sxs-lookup"><span data-stu-id="55939-103">Get product recommendations using demo data</span></span>
<span data-ttu-id="55939-104">Este documento ofrece instrucciones acerca de cómo aprovechar las recomendaciones de producto de omnicanal en entornos de un solo cuadro de nivel 1 utilizando datos de demostración personalizables y ya cumplimentados.</span><span class="sxs-lookup"><span data-stu-id="55939-104">This document provides guidance on how to leverage omni-channel product recommendations in Tier-1 single box environments using pre-populated, customizable demo data.</span></span>

<span data-ttu-id="55939-105">Las recomendaciones de producto omnicanal proporcionan un conjunto de listas de productos generadas por programación o de forma dirigida.</span><span class="sxs-lookup"><span data-stu-id="55939-105">Omni-channel product recommendations provide a set of editorially curated or programmatically generated list of products.</span></span> <span data-ttu-id="55939-106">Estas listas se pueden usar en varias situaciones, en función de la necesidad empresarial.</span><span class="sxs-lookup"><span data-stu-id="55939-106">These lists can be used in several scenarios, depending on the business need.</span></span> <span data-ttu-id="55939-107">Para obtener más información sobre las listas de recomendaciones del producto, consulte [Información general sobre las recomendaciones del producto](product-recommendations.md).</span><span class="sxs-lookup"><span data-stu-id="55939-107">For more information about product recommendation lists, see [Product recommendations overview](product-recommendations.md).</span></span>

<span data-ttu-id="55939-108">Para entornos de Dynamics 365 de nivel 2 y superior, las recomendaciones de productos se calculan automáticamente en función de los datos del cliente.</span><span class="sxs-lookup"><span data-stu-id="55939-108">For Tier-2 and higher Dynamics 365 environments, product recommendations are automatically computed based on customer data.</span></span> <span data-ttu-id="55939-109">El uso de datos de demostración para recomendaciones de productos no deshabilita ninguna solución de recomendación de productos ya aprovisionada en el entorno ni los costes vinculados a su uso.</span><span class="sxs-lookup"><span data-stu-id="55939-109">Using product recommendations demo data does not disable any product recommendations solution already provisioned in the environment and any costs associated with its usage.</span></span>

<span data-ttu-id="55939-110">Para entornos de nivel 1, las recomendaciones de productos solo se basan en datos estáticos de demostración almacenados en un archivo .csv.</span><span class="sxs-lookup"><span data-stu-id="55939-110">For Tier-1 environments, product recommendations are based only off the static demo data stored in a .csv file.</span></span>

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a><span data-ttu-id="55939-111">Habilitar datos de demostración de productos en un entorno</span><span class="sxs-lookup"><span data-stu-id="55939-111">Enabling product recommendations demo data in an environment</span></span>
<span data-ttu-id="55939-112">Para habilitar datos de demostración para recomendaciones de productos, tiene que implementar la Extensión de demostración de vista previa de Dynamics 365 Commerce para el entorno respectivo.</span><span class="sxs-lookup"><span data-stu-id="55939-112">To enable product recommensations demo date, you need to deploy the Dynamics 365 Commerce Preview Demo Extension to the respective environment.</span></span> <span data-ttu-id="55939-113">Hacerlo automáticamente habilita los datos de demostración de recomendaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="55939-113">Doing so automatically enables product recommendations demo data.</span></span>

## <a name="default-demo-data"></a><span data-ttu-id="55939-114">Datos de demostración predeterminados</span><span class="sxs-lookup"><span data-stu-id="55939-114">Default demo data</span></span>
<span data-ttu-id="55939-115">Cada entorno de tipo Onebox incorpora un conjunto preinstalado de datos de demostración para recomendaciones de productos almacenado en el archivo separado por comas “reco_demo_data.csv”, que se encuentra en Commerce Scale Unit.</span><span class="sxs-lookup"><span data-stu-id="55939-115">Each Onebox type environment comes with a preloaded set of product recommendations demo data stored in the coma separated ‘reco_demo_data.csv’ file, located on the Commerce Scale Unit.</span></span>

<span data-ttu-id="55939-116">Los datos se estructuran en las siguientes columnas.</span><span class="sxs-lookup"><span data-stu-id="55939-116">The data is structured along the following columns.</span></span>

| <span data-ttu-id="55939-117">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="55939-117">Column name</span></span>         | <span data-ttu-id="55939-118">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="55939-118">Mandatory</span></span>          | <span data-ttu-id="55939-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="55939-119">Description</span></span>                                                                                                                                 | <span data-ttu-id="55939-120">Valores posibles</span><span class="sxs-lookup"><span data-stu-id="55939-120">Possible Values</span></span>                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| <span data-ttu-id="55939-121">RecoList</span><span class="sxs-lookup"><span data-stu-id="55939-121">RecoList</span></span>            | :heavy_check_mark: | <span data-ttu-id="55939-123">El tipo de lista específico de recomendaciones de productos que el punto de datos de demostración va a generar.</span><span class="sxs-lookup"><span data-stu-id="55939-123">The specific product recommendation list type that the demo data point is to generate.</span></span>                                                    | <ul><li><span data-ttu-id="55939-124">RecoBestSelling</span><span class="sxs-lookup"><span data-stu-id="55939-124">RecoBestSelling</span></span></li><li><span data-ttu-id="55939-125">RecoNew</span><span class="sxs-lookup"><span data-stu-id="55939-125">RecoNew</span></span></li><li><span data-ttu-id="55939-126">RecoTrending</span><span class="sxs-lookup"><span data-stu-id="55939-126">RecoTrending</span></span></li><li><span data-ttu-id="55939-127">RecoCart</span><span class="sxs-lookup"><span data-stu-id="55939-127">RecoCart</span></span></li><li><span data-ttu-id="55939-128">RecoPeopleAlsoBuy</span><span class="sxs-lookup"><span data-stu-id="55939-128">RecoPeopleAlsoBuy</span></span></li></ul> |
| <span data-ttu-id="55939-129">OperatingUnitNumber</span><span class="sxs-lookup"><span data-stu-id="55939-129">OperatingUnitNumber</span></span> | :heavy_check_mark: | <span data-ttu-id="55939-131">El número de unidad operativa específico donde se espera que aparezcan las recomendaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="55939-131">The specific operating unit number where product recommendations are expected to be   surfaced.</span></span>                                        |                                                                              |
| <span data-ttu-id="55939-132">Categoría</span><span class="sxs-lookup"><span data-stu-id="55939-132">Category</span></span>            |                    |    <span data-ttu-id="55939-133">La categoría para la que debe devolverse la lista específica.</span><span class="sxs-lookup"><span data-stu-id="55939-133">The category the specific list should be returned for.</span></span> <span data-ttu-id="55939-134">Si no se especifica ninguna categoría, la lista es solo para los primeros elementos de la jerarquía de navegación.</span><span class="sxs-lookup"><span data-stu-id="55939-134">If no category is specified, the list is for top of navigation hierarchy only.</span></span>    |                                                                              |
| <span data-ttu-id="55939-135">SeedItemId</span><span class="sxs-lookup"><span data-stu-id="55939-135">SeedItemId</span></span>          |                    |    <span data-ttu-id="55939-136">Para las listas que requieren inicialización (RecoPeopleAlsoBuy y RecoCart), el producto para el que esas listas deben mostrar productos adicionales.</span><span class="sxs-lookup"><span data-stu-id="55939-136">For lists that require seed (RecoPeopleAlsoBuy and RecoCart), the product those lists should show additional products for.</span></span>            |                                                                              |
| <span data-ttu-id="55939-137">ItemIds</span><span class="sxs-lookup"><span data-stu-id="55939-137">ItemIds</span></span>             | :heavy_check_mark: | <span data-ttu-id="55939-139">Uno o más productos que se devolverán como el resultado, separado por ‘;’.</span><span class="sxs-lookup"><span data-stu-id="55939-139">One or more products to be returned as the result, separated by ‘;’.</span></span>                                                                  |                                                                              |

## <a name="customize-demo-data"></a><span data-ttu-id="55939-140">Personalizar datos de demostración</span><span class="sxs-lookup"><span data-stu-id="55939-140">Customize demo data</span></span>
<span data-ttu-id="55939-141">Puede editar los datos predeterminados de prueba con cualquier información de producto y categoría que se configure en la sede.</span><span class="sxs-lookup"><span data-stu-id="55939-141">You can edit the default demo data with any product and category information configured in HQ.</span></span> <span data-ttu-id="55939-142">Una vez que se actualice el .csv, las recomendaciones de productos devueltas para los clientes inmediatamente reflejarán los cambios.</span><span class="sxs-lookup"><span data-stu-id="55939-142">Once you update the .csv, the product recommendations that are returned to customers will immediately reflect the changes.</span></span>

<span data-ttu-id="55939-143">La extensión contiene un archivo de datos denominado 'RecoMockDataset.csv' que le permite controlar el conjunto de datos usado para activar los resultados de las recomendaciones simuladas.</span><span class="sxs-lookup"><span data-stu-id="55939-143">The extension contains a datafile called 'RecoMockDataset.csv' which allows you to control the dataset used to power the mock recommendations results.</span></span> <span data-ttu-id="55939-144">El nombre de archivo se puede controlar con la configuración de la extensión mediante la configuración **ext.Recommendations.DemoFilePath**.</span><span class="sxs-lookup"><span data-stu-id="55939-144">The file name can be controlled through extension configuration using the **ext.Recommendations.DemoFilePath** setting.</span></span> <span data-ttu-id="55939-145">Esto le permite disponer de varios conjuntos de datos que se pueden intercambiar fácilmente entre ellos a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="55939-145">This enables you to have multiple datasets available that can be switched between easily through configuration.</span></span>


```
  <settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
  </settings>
```

## <a name="additional-resources"></a><span data-ttu-id="55939-146">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="55939-146">Additional Resources</span></span>

[<span data-ttu-id="55939-147">Visión general de recomendaciones de producto</span><span class="sxs-lookup"><span data-stu-id="55939-147">Product recommendations overview</span></span>](product-recommendations.md)

[<span data-ttu-id="55939-148">Planificación de entorno</span><span class="sxs-lookup"><span data-stu-id="55939-148">Environment planning</span></span>](../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)
