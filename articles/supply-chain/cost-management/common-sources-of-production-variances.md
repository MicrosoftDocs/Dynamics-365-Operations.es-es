---
title: "Orígenes comunes de desviaciones de producción"
description: "Este artículo explica diversos orígenes de cada tipo de desviación de producción."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventCostTrans
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 79753
ms.assetid: 14ac7db4-fb40-43c1-bb0d-1d51fc91d24f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: f8eea27edaa97150ceb2c36996177395cba8bdb9
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="common-sources-of-production-variances"></a><span data-ttu-id="66035-103">Orígenes comunes de desviaciones de producción</span><span class="sxs-lookup"><span data-stu-id="66035-103">Common sources of production variances</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="66035-104">Este artículo explica diversos orígenes de cada tipo de desviación de producción.</span><span class="sxs-lookup"><span data-stu-id="66035-104">This article explains various typical sources of each type of production variance.</span></span> 

<span data-ttu-id="66035-105">Estos son algunos orígenes típicos de desviación de **tamaño de lote**:</span><span class="sxs-lookup"><span data-stu-id="66035-105">Here are some typical sources of a **lot size** variance:</span></span>

-   <span data-ttu-id="66035-106">La cantidad sin errores para un pedido de producción difiere de la cantidad de cálculo usada en el cálculo de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="66035-106">The good quantity for a production order differs from the calculation quantity that is used in the standard cost calculation.</span></span> <span data-ttu-id="66035-107">La cantidad proporciona la base para la amortización de costes constantes.</span><span class="sxs-lookup"><span data-stu-id="66035-107">The quantity provides the basis for amortizing constant costs.</span></span>
-   <span data-ttu-id="66035-108">El valor de costes constantes del pedido de producción difiere de los costes constantes usados en el cálculo de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="66035-108">The value of constant costs on the production order differs from the constant costs that are used in the standard cost calculation.</span></span> <span data-ttu-id="66035-109">Los costes constantes del pedido de producción pueden ser diferentes por varios motivos.</span><span class="sxs-lookup"><span data-stu-id="66035-109">The constant costs on the production order can differ for several reasons.</span></span> <span data-ttu-id="66035-110">Por ejemplo, los costes constantes pueden reflejar los factores siguientes:</span><span class="sxs-lookup"><span data-stu-id="66035-110">For example, the constant costs might reflect the following factors:</span></span>
    -   <span data-ttu-id="66035-111">Modificaciones efectuadas manualmente en la lista de materiales de producción (L. MAT) o en la ruta</span><span class="sxs-lookup"><span data-stu-id="66035-111">Manual changes to the production bill of materials (BOM) or route</span></span>
    -   <span data-ttu-id="66035-112">La selección de una versión de L. MAT o versión de ruta diferente al crear el pedido de producción</span><span class="sxs-lookup"><span data-stu-id="66035-112">The selection of a different BOM version or route version when you create the production order</span></span>
    -   <span data-ttu-id="66035-113">Modificaciones de ingeniería planificadas en la versión de L. MAT o de ruta asignada al artículo</span><span class="sxs-lookup"><span data-stu-id="66035-113">Planned engineering changes to the BOM version or route version that is assigned to the item</span></span>

<span data-ttu-id="66035-114">Estos son algunos orígenes típicos de una desviación de **precio de producción**:</span><span class="sxs-lookup"><span data-stu-id="66035-114">Here are some typical sources of a **production price** variance:</span></span>

-   <span data-ttu-id="66035-115">La categoría de coste (y el precio de categoría de coste) del consumo notificado de una operación de ruta difiere de la categoría de coste usada en el cálculo de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="66035-115">The cost category (and cost category price) for the reported consumption of a routing operation differs from the cost category that is used in standard cost calculation.</span></span>
-   <span data-ttu-id="66035-116">El coste activo para el precio de categoría de coste difiere del precio de categoría de coste usado en el cálculo de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="66035-116">The active cost for the cost category price differs from the cost category price that is used in standard cost calculation.</span></span>

<span data-ttu-id="66035-117">Estos son algunos orígenes típicos de una desviación de **cantidad de producción**:</span><span class="sxs-lookup"><span data-stu-id="66035-117">Here are some typical sources of a **production quantity** variance:</span></span>

-   <span data-ttu-id="66035-118">Realiza una emisión excesiva o insuficiente de un componente de material.</span><span class="sxs-lookup"><span data-stu-id="66035-118">You over-issue or under-issue a material component.</span></span>
-   <span data-ttu-id="66035-119">Especifica un tiempo de informe excesivo o insuficiente para una operación de ruta.</span><span class="sxs-lookup"><span data-stu-id="66035-119">You over-report or under-report the time for a routing operation.</span></span>
-   <span data-ttu-id="66035-120">Realiza una recepción excesiva o insuficiente de la cantidad sin errores del artículo principal, en relación con la cantidad del pedido.</span><span class="sxs-lookup"><span data-stu-id="66035-120">You over-receive or under-receive the good quantity of the parent item, relative to the order quantity.</span></span> <span data-ttu-id="66035-121">Sin embargo, emite totalmente componentes y operaciones de informes, en función de la cantidad del pedido para el pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="66035-121">However, you issue components and report operations completely, based on the order quantity for the production order.</span></span>

<span data-ttu-id="66035-122">Estos son algunos orígenes típicos de una desviación de **sustitución de producción**:</span><span class="sxs-lookup"><span data-stu-id="66035-122">Here are some typical sources of a **production substitution** variance:</span></span>

-   <span data-ttu-id="66035-123">Emite un componente de material que no se encuentra en la L. MAT de producción.</span><span class="sxs-lookup"><span data-stu-id="66035-123">You issue a material component that isn't on the production BOM.</span></span>
-   <span data-ttu-id="66035-124">Agrega manualmente un componente a la L. MAT de producción y notifica ese componente como consumido.</span><span class="sxs-lookup"><span data-stu-id="66035-124">You manually add a component to the production BOM and report that component as consumed.</span></span>
-   <span data-ttu-id="66035-125">Notifica un artículo como consumido pero sin agregarlo manualmente a la L. MAT de producción.</span><span class="sxs-lookup"><span data-stu-id="66035-125">You report an item as consumed but don't manually add it to the production BOM.</span></span>
-   <span data-ttu-id="66035-126">Agrega manualmente una operación a la ruta de producción y notifica esa operación como consumida.</span><span class="sxs-lookup"><span data-stu-id="66035-126">You manually add an operation to the production route and report that operation as consumed.</span></span>
-   <span data-ttu-id="66035-127">Al crear el pedido de producción, selecciona una versión de L. MAT difiere de la usada en el cálculo de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="66035-127">When you create the production order, you select a BOM version that differs from the BOM version that is used in the standard cost calculation.</span></span>
-   <span data-ttu-id="66035-128">Al crear el pedido de producción, selecciona una versión de ruta que difiere de la usada en el cálculo de coste estándar.</span><span class="sxs-lookup"><span data-stu-id="66035-128">When you create the production order, you select a route version that differs from the route version that is used in the standard cost calculation.</span></span>





