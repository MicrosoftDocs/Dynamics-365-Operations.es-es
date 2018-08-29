--- 
title: "Insertar productos de los centros de distribución en tiendas mediante estrategia de presión"
description: "Este procedimiento le guía por los pasos para crear y procesar una estrategia de presión para distribuir productos desde una ubicación a una o varias tiendas."
author: rubencdelgado
manager: AnnBe
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 5098fb3339403b6f2779dfe3bb7ef5c4ca78051f
ms.openlocfilehash: ed47b4f052dab99dec058910e4b8558481b34e59
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---
# <a name="push-products-from-distribution-centers-to-stores-via-buyers-push"></a><span data-ttu-id="59732-103">Insertar productos de los centros de distribución en tiendas mediante estrategia de presión</span><span class="sxs-lookup"><span data-stu-id="59732-103">Push products from distribution centers to stores via buyer's push</span></span>

[!include [task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="59732-104">Este procedimiento le guía por los pasos para crear y procesar una estrategia de presión para distribuir productos desde una ubicación a una o varias tiendas.</span><span class="sxs-lookup"><span data-stu-id="59732-104">This procedure walks through the steps to create and process a Buyer's push to distribute products from one location to one or many stores.</span></span> <span data-ttu-id="59732-105">El usuario puede definir varias configuraciones y hacer que el sistema sugiera cómo distribuir los productos, o especificar manualmente a dónde se distribuyen los productos y qué cantidad se distribuye a cada almacén.</span><span class="sxs-lookup"><span data-stu-id="59732-105">The user can define multiple configurations and have the system suggest how to distribute the products, or manually enter where the products are distributed to and how much gets distributed to each store.</span></span> <span data-ttu-id="59732-106">Este procedimiento no incluye la configuración de datos que se puede usar en la estrategia de presión, como reglas de reabastecimiento, jerarquías organizativas y pesos de tiendas.</span><span class="sxs-lookup"><span data-stu-id="59732-106">This procedure doesn't include setup of data that can be used in the Buyer's push, such as replenishment rules, organizational hierarchies, and store weights.</span></span> <span data-ttu-id="59732-107">Este procedimiento usa la empresa de prueba USRT.</span><span class="sxs-lookup"><span data-stu-id="59732-107">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="59732-108">Vaya a Estrategia de presión.</span><span class="sxs-lookup"><span data-stu-id="59732-108">Go to Buyer's push.</span></span>
2. <span data-ttu-id="59732-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="59732-109">Click New.</span></span>
3. <span data-ttu-id="59732-110">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="59732-110">In the Description field, type a value.</span></span>
4. <span data-ttu-id="59732-111">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="59732-111">In the Site field, enter or select a value.</span></span>
5. <span data-ttu-id="59732-112">En el campo Almacén, especifique o seleccione un almacén que tenga productos con cantidades disponibles.</span><span class="sxs-lookup"><span data-stu-id="59732-112">In the Warehouse field, enter or select a warehouse that has products with on-hand quantities.</span></span>
6. <span data-ttu-id="59732-113">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="59732-113">Click Add.</span></span>
7. <span data-ttu-id="59732-114">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="59732-114">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="59732-115">En el campo Número de artículo, especifique o seleccione un producto.</span><span class="sxs-lookup"><span data-stu-id="59732-115">In the Item number field, enter or select a product.</span></span>
9. <span data-ttu-id="59732-116">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="59732-116">Click Add.</span></span>
10. <span data-ttu-id="59732-117">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="59732-117">In the list, mark the selected row.</span></span>
11. <span data-ttu-id="59732-118">En el campo Número de artículo, especifique o seleccione un producto de variante.</span><span class="sxs-lookup"><span data-stu-id="59732-118">In the Item number field, enter or select a variant product.</span></span>
    * <span data-ttu-id="59732-119">Al especificar un producto de variante, se crearán líneas para cada variante.</span><span class="sxs-lookup"><span data-stu-id="59732-119">When entering a variant product, lines will be created for each variant.</span></span>  
12. <span data-ttu-id="59732-120">En la lista, marque una fila.</span><span class="sxs-lookup"><span data-stu-id="59732-120">In the list, mark a row.</span></span>
13. <span data-ttu-id="59732-121">En el campo Cantidad insertada, escriba cuánto del producto seleccionado desea distribuir.</span><span class="sxs-lookup"><span data-stu-id="59732-121">In the Pushed quantity field, type how many of the selected product you want to distribute.</span></span>
14. <span data-ttu-id="59732-122">En el campo Cantidad adicional a la que aplicar la estrategia de presión, especifique la cantidad de los productos que tienen cantidad disponible para distribuir.</span><span class="sxs-lookup"><span data-stu-id="59732-122">In the Additional quantity to push field, enter the quantity of the products that have available quantity to distribute.</span></span>
15. <span data-ttu-id="59732-123">En el campo Distribución, especifique el “Peso en la ubicación”.</span><span class="sxs-lookup"><span data-stu-id="59732-123">In the Distribution field, enter 'Location weight'.</span></span>
    * <span data-ttu-id="59732-124">Puede seleccionar los demás tipos para usar otras reglas para la distribución.</span><span class="sxs-lookup"><span data-stu-id="59732-124">You can select the other types to use other rules for the distribution.</span></span>  
16. <span data-ttu-id="59732-125">En el campo Jerarquía de reabastecimiento, seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="59732-125">In the Replenishment hierarchy field, select a value.</span></span>
17. <span data-ttu-id="59732-126">Seleccione Sí en el campo Respetar selecciones.</span><span class="sxs-lookup"><span data-stu-id="59732-126">Select Yes in the Respect assortments field.</span></span>
18. <span data-ttu-id="59732-127">Haga clic en Calcular cantidades y revise las cantidades que se agregan a las filas en la sección Almacén.</span><span class="sxs-lookup"><span data-stu-id="59732-127">Click Calculate quantities and review the quantities that are added to the rows in the Warehouse section.</span></span>
19. <span data-ttu-id="59732-128">Haga clic en Crear pedido.</span><span class="sxs-lookup"><span data-stu-id="59732-128">Click Create order.</span></span>
20. <span data-ttu-id="59732-129">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="59732-129">Click Yes.</span></span>


