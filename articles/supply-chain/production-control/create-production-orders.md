---
title: "Crear pedidos de producción"
description: "Al crear un pedido de producción, se inicia una solicitud para iniciar la producción de un artículo. El pedido de producción contiene información acerca de qué se producirá, qué cantidad y la fecha de finalización planificada. También contiene información relativa a qué materiales se van a consumir y qué proceso seguir para producir el artículo."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdTable, ProdTableCreate
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19741
ms.assetid: bbb6e69d-479c-45fc-a0a8-66da5df16c7f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: d962dbf5a5a4e3847252171d3631f78341640bc7
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="create-production-orders"></a><span data-ttu-id="2f1b0-105">Crear pedidos de producción</span><span class="sxs-lookup"><span data-stu-id="2f1b0-105">Create production orders</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="2f1b0-106">Al crear un pedido de producción, se inicia una solicitud para iniciar la producción de un artículo.</span><span class="sxs-lookup"><span data-stu-id="2f1b0-106">When a production order is created, a request is initiated to start producing an item.</span></span> <span data-ttu-id="2f1b0-107">El pedido de producción contiene información acerca de qué se producirá, qué cantidad y la fecha de finalización planificada.</span><span class="sxs-lookup"><span data-stu-id="2f1b0-107">The production order contains information about what will be produced, the quantity to produce, and the planned finish date.</span></span> <span data-ttu-id="2f1b0-108">También contiene información relativa a qué materiales se van a consumir y qué proceso seguir para producir el artículo.</span><span class="sxs-lookup"><span data-stu-id="2f1b0-108">It also contains information about which materials to consume and which process to follow to produce the item.</span></span>

<span data-ttu-id="2f1b0-109">Un pedido de producción pasa por las etapas del ciclo de vida de producción.</span><span class="sxs-lookup"><span data-stu-id="2f1b0-109">A production order passes through stages of the production life cycle.</span></span> <span data-ttu-id="2f1b0-110">Cuando se crea un pedido, se le asigna el estado **Creado**.</span><span class="sxs-lookup"><span data-stu-id="2f1b0-110">When an order is created, it is assigned the status **Created**.</span></span> <span data-ttu-id="2f1b0-111">Cuando se termina un pedido, se le asigna el estado **Finalizado**.</span><span class="sxs-lookup"><span data-stu-id="2f1b0-111">When an order is finished, it is assigned the status **Ended**.</span></span> <span data-ttu-id="2f1b0-112">Un parámetro en cada etapa permite al usuario configurar cada paso.</span><span class="sxs-lookup"><span data-stu-id="2f1b0-112">A parameter setting in each stage allows a user to configure each step.</span></span> <span data-ttu-id="2f1b0-113">El parámetro se puede configurar para un único usuario o para todos los usuarios.</span><span class="sxs-lookup"><span data-stu-id="2f1b0-113">The setting can be set up for a single user or for all users.</span></span>

<span data-ttu-id="2f1b0-114">La lista de materiales de producción y la ruta de producción son las entidades principales del pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="2f1b0-114">The production bill of material and the production route are the main entities of the production order.</span></span> <span data-ttu-id="2f1b0-115">Se copian en el pedido de producción según el artículo y la cantidad seleccionados que se van a producir.</span><span class="sxs-lookup"><span data-stu-id="2f1b0-115">They are copied to the production order based on the selected item and quantity that are going to be produced.</span></span> <span data-ttu-id="2f1b0-116">Antes de iniciar el pedido de producción se pueden editar la lista de materiales y la ruta de producción.</span><span class="sxs-lookup"><span data-stu-id="2f1b0-116">Before the production order is started, the production bill of material and route can be edited.</span></span>

<span data-ttu-id="2f1b0-117">El pedido de producción se puede crear en las siguientes situaciones:</span><span class="sxs-lookup"><span data-stu-id="2f1b0-117">A production order can be created in the following scenarios:</span></span>

-   <span data-ttu-id="2f1b0-118">Se crean al ejecutarse la planificación maestra según la demanda de material.</span><span class="sxs-lookup"><span data-stu-id="2f1b0-118">Created by master planning execution based on material demand.</span></span>
-   <span data-ttu-id="2f1b0-119">Se crean directamente a partir de una línea de pedido de ventas o cuando se crea y se estima un pedido de producción de alto nivel (suministro asegurado).</span><span class="sxs-lookup"><span data-stu-id="2f1b0-119">Created directly from a sales order line or when a higher-level production order is created and estimated (pegged supply).</span></span>
-   <span data-ttu-id="2f1b0-120">Se crea manualmente.</span><span class="sxs-lookup"><span data-stu-id="2f1b0-120">Created manually.</span></span>





