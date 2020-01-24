---
title: Dados de demostración para recomendaciones de productos de omnicanal
description: Este documento pretende proporcionar instrucciones acerca de cómo aprovechar las recomendaciones del producto de omnicanal en entornos de un solo cuadro de nivel 1 utilizando datos de demostración personalizables y ya cumplimentados.
author: bebeale
manager: AnnBe
ms.date: 12/1/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
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
ms.search.validFrom: 2019-07-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 31aa5dbd2fa814fd572024a4ae36b9d9b46a2fb0
ms.sourcegitcommit: 398c0652acde12c953de007d06055456d6e0a516
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/02/2019
ms.locfileid: "2872335"
---
# <a name="omni-channel-product-recommendations-demo-data"></a><span data-ttu-id="2351f-103">Dados de demostración para recomendaciones de productos de omnicanal</span><span class="sxs-lookup"><span data-stu-id="2351f-103">Omni-channel product recommendations demo data</span></span>

<span data-ttu-id="2351f-104">Este documento pretende proporcionar instrucciones acerca de cómo aprovechar las recomendaciones del producto de omnicanal en entornos de un solo cuadro de nivel 1 utilizando datos de demostración personalizables y ya cumplimentados.</span><span class="sxs-lookup"><span data-stu-id="2351f-104">This document aims to provide guidance on how to leverage omni-channel product recommendations in Tier-1 single box environments using pre-populated, customizable demo data.</span></span>

<span data-ttu-id="2351f-105">Las recomendaciones de producto omnicanal proporcionan un conjunto de listas de productos ordenadas generadas por programación o de forma dirigida.</span><span class="sxs-lookup"><span data-stu-id="2351f-105">Omni-channel product recommendations provide a set of editorially curated or programmatically generated ordered list of products.</span></span> <span data-ttu-id="2351f-106">Estas listas se pueden usar en varias situaciones, en función de la necesidad empresarial.</span><span class="sxs-lookup"><span data-stu-id="2351f-106">These lists can be used in several scenarios, depending on the business need.</span></span> <span data-ttu-id="2351f-107">Para obtener más información sobre las listas de recomendaciones del producto, consulte [Información general sobre las recomendaciones del producto](../commerce/product-recommendations.md)</span><span class="sxs-lookup"><span data-stu-id="2351f-107">For more information about product recommendation lists, see [Product recommendations overview.](../commerce/product-recommendations.md)</span></span>

<span data-ttu-id="2351f-108">Para productos de entornos de Dynamics de nivel 2 y más las recomendaciones se calculan automáticamente en función de los datos del cliente.</span><span class="sxs-lookup"><span data-stu-id="2351f-108">For Tier-2 and higher Dynamics Environments product recommendations are automatically computed based on customer data.</span></span>
<span data-ttu-id="2351f-109">El uso de datos de demostración para recomendaciones de productos no deshabilita ninguna solución de recomendación de productos ya aprovisionada en el entorno ni los costes vinculados a su uso.</span><span class="sxs-lookup"><span data-stu-id="2351f-109">Using product recommendations demo data does not disable any product recommendations solution already provisioned in the environment and any costs associated with its usage.</span></span>

<span data-ttu-id="2351f-110">Para los producto de entornos de nivel 1, las recomendaciones solo se basan de datos estáticos de demostración almacenados en un archivo csv.</span><span class="sxs-lookup"><span data-stu-id="2351f-110">For Tier-1 environments product recommendations are based only off the static demo data stored in a csv file.</span></span>

## <a name="enabling-product-recommendations-demo-data-in-an-environment"></a><span data-ttu-id="2351f-111">Habilitar datos de demostración de productos en un entorno</span><span class="sxs-lookup"><span data-stu-id="2351f-111">Enabling product recommendations demo data in an environment</span></span>

<span data-ttu-id="2351f-112">Los clientes deben implementar la **Extensión de demostración de vista previa de Dynamics 365 Commerce** para entorno respectivo, que habilita automáticamente los datos de demostración para las recomendaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="2351f-112">Customers need to deploy the **Dynamics 365 Commerce Preview Demo Extension** to the respective environment, which automatically enables product recommendations demo data.</span></span>

## <a name="default-demo-data"></a><span data-ttu-id="2351f-113">Datos de demostración predeterminados</span><span class="sxs-lookup"><span data-stu-id="2351f-113">Default demo data</span></span>
<span data-ttu-id="2351f-114">Cada entorno de tipo Onebox incorpora un conjunto preinstalado de datos de demostración para recomendaciones de productos almacenado en el archivo separado comas **“reco_demo_data.csv”**, que se encuentra en la misma carpeta que este documento en Retail Server.</span><span class="sxs-lookup"><span data-stu-id="2351f-114">Each Onebox type environment comes with a preloaded set of product recommendations demo data stored in the coma separated **‘reco_demo_data.csv’** file, located in the same folder as this document on Retail Server.</span></span>

<span data-ttu-id="2351f-115">Estos datos se estructuran en las siguientes columnas</span><span class="sxs-lookup"><span data-stu-id="2351f-115">This data is structured along the following columns</span></span>

| <span data-ttu-id="2351f-116">Nombre de columna</span><span class="sxs-lookup"><span data-stu-id="2351f-116">Column name</span></span>         | <span data-ttu-id="2351f-117">Obligatorio</span><span class="sxs-lookup"><span data-stu-id="2351f-117">Mandatory</span></span>          | <span data-ttu-id="2351f-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="2351f-118">Description</span></span>                                                                                                                                 | <span data-ttu-id="2351f-119">Valores posibles</span><span class="sxs-lookup"><span data-stu-id="2351f-119">Possible Values</span></span>                                                              |
|---------------------|--------------------|---------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------|
| <span data-ttu-id="2351f-120">RecoList</span><span class="sxs-lookup"><span data-stu-id="2351f-120">RecoList</span></span>            | :heavy_check_mark: | <span data-ttu-id="2351f-122">El tipo de lista específico de recomendaciones de productos que el punto de datos de demostración va a generar.</span><span class="sxs-lookup"><span data-stu-id="2351f-122">The specific product   recommendation list type that the demo data point is to generate.</span></span>                                                    | <ul><li><span data-ttu-id="2351f-123">RecoBestSelling</span><span class="sxs-lookup"><span data-stu-id="2351f-123">RecoBestSelling</span></span></li><li><span data-ttu-id="2351f-124">RecoNew</span><span class="sxs-lookup"><span data-stu-id="2351f-124">RecoNew</span></span></li><li><span data-ttu-id="2351f-125">RecoTrending</span><span class="sxs-lookup"><span data-stu-id="2351f-125">RecoTrending</span></span></li><li><span data-ttu-id="2351f-126">RecoCart</span><span class="sxs-lookup"><span data-stu-id="2351f-126">RecoCart</span></span></li><li><span data-ttu-id="2351f-127">RecoPeopleAlsoBuy</span><span class="sxs-lookup"><span data-stu-id="2351f-127">RecoPeopleAlsoBuy</span></span></li></ul> |
| <span data-ttu-id="2351f-128">OperatingUnitNumber</span><span class="sxs-lookup"><span data-stu-id="2351f-128">OperatingUnitNumber</span></span> | :heavy_check_mark: | <span data-ttu-id="2351f-130">El número de unidad operativa específico donde se espera que aparezcan las recomendaciones de productos.</span><span class="sxs-lookup"><span data-stu-id="2351f-130">The specific   operating unit number where product recommendations are expected to be   surfaced in.</span></span>                                        |                                                                              |
| <span data-ttu-id="2351f-131">Categoría</span><span class="sxs-lookup"><span data-stu-id="2351f-131">Category</span></span>            |                    |    <span data-ttu-id="2351f-132">La categoría para la que debe devolverse la lista específica.</span><span class="sxs-lookup"><span data-stu-id="2351f-132">The category the   specific list should be returned for.</span></span> <span data-ttu-id="2351f-133">Si no se especifica ninguna categoría, la lista es solo para la los primeros elementos de la jerarquía de navegación.</span><span class="sxs-lookup"><span data-stu-id="2351f-133">If no category is specified, list is   for top of navigation hierarchy only.</span></span>    |                                                                              |
| <span data-ttu-id="2351f-134">SeedItemId</span><span class="sxs-lookup"><span data-stu-id="2351f-134">SeedItemId</span></span>          |                    |    <span data-ttu-id="2351f-135">Para las listas que requieren semilla (RecoPeopleAlsoBuy y RecoCart), el producto para el que esas listas deben mostrar productos adicionales.</span><span class="sxs-lookup"><span data-stu-id="2351f-135">For lists that   require seed (RecoPeopleAlsoBuy and RecoCart) the product those lists should   show additional products for.</span></span>            |                                                                              |
| <span data-ttu-id="2351f-136">ItemIds</span><span class="sxs-lookup"><span data-stu-id="2351f-136">ItemIds</span></span>             | :heavy_check_mark: | <span data-ttu-id="2351f-138">Uno o más productos que se devolverán como el resultado, separado por **‘;’**.</span><span class="sxs-lookup"><span data-stu-id="2351f-138">One or more products   to be returned as the result, separated by **‘;’**.</span></span>                                                                  |                                                                              |


## <a name="customize-demo-data"></a><span data-ttu-id="2351f-139">Personalizar datos de demostración</span><span class="sxs-lookup"><span data-stu-id="2351f-139">Customize demo data</span></span>
<span data-ttu-id="2351f-140">Los clientes pueden editar los datos predeterminados de prueba con cualquier información de producto y categoría que se configure en la sede.</span><span class="sxs-lookup"><span data-stu-id="2351f-140">Customers can edit the default demo data with any product and category information that is configured in HQ.</span></span> <span data-ttu-id="2351f-141">Una vez que se actualice el CSV, las recomendaciones de productos devueltas para los clientes inmediatamente reflejarán los cambios.</span><span class="sxs-lookup"><span data-stu-id="2351f-141">Once the CSV is updated, the Product Recommendations returned to customers will immediately reflect the changes.</span></span>

<span data-ttu-id="2351f-142">La extensión contiene un archivo de datos denominado RecoMockDataset.csv que permita que el cliente controle el conjunto de datos usado para activar los resultados de las recomendaciones simuladas.</span><span class="sxs-lookup"><span data-stu-id="2351f-142">The extension contains a datafile called RecoMockDataset.csv which allows the customer to control the dataset used to power the mock recommendations results.</span></span> <span data-ttu-id="2351f-143">El nombre de archivo se puede controlar con la configuración de la extensión mediante la configuración **ext.Recommendations.DemoFilePath**.</span><span class="sxs-lookup"><span data-stu-id="2351f-143">The file name can be controlled through extension configuration using the **ext.Recommendations.DemoFilePath** setting.</span></span> <span data-ttu-id="2351f-144">Esto permite a los clientes disponer de varios conjuntos de datos varios que se pueden intercambiar fácilmente entre ellos a través de la configuración.</span><span class="sxs-lookup"><span data-stu-id="2351f-144">This enables the customers to have multiple datasets available that can be switched between easily through configuration.</span></span>

```
  <settings>
    <add name="ext.Recommendations.DemoFilePath" value="RecoMockDataset.csv" />
  </settings>
```

## <a name="additional-resources"></a><span data-ttu-id="2351f-145">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2351f-145">Additional resources</span></span>

[<span data-ttu-id="2351f-146">Visión general de recomendaciones de productos</span><span class="sxs-lookup"><span data-stu-id="2351f-146">Product recommendations overview</span></span>](../commerce/product-recommendations.md)

[<span data-ttu-id="2351f-147">Planificación de entorno</span><span class="sxs-lookup"><span data-stu-id="2351f-147">Environment planning</span></span>](../fin-ops-core/fin-ops/imp-lifecycle/environment-planning.md)
