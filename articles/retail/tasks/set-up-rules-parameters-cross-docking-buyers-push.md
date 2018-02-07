--- 
title: "Configurar las reglas y los parámetros para el tránsito directo y la estrategia de presión"
description: Este procedimiento muestra los pasos para crear Reglas de reabastecimiento.
author: josaw1
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ea07d8e91c94d9fdad4c2d05533981e254420188
ms.openlocfilehash: f3a20b7bf476cae854c7f7c86d89d73e44b6749b
ms.contentlocale: es-es
ms.lasthandoff: 02/07/2018

---
# <a name="set-up-rules-and-parameters-for-cross-docking-and-buyers-push"></a><span data-ttu-id="3a14f-103">Configurar las reglas y los parámetros para el tránsito directo y la estrategia de presión</span><span class="sxs-lookup"><span data-stu-id="3a14f-103">Set up rules and parameters for cross docking and buyer's push</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="3a14f-104">Este procedimiento muestra los pasos para crear Reglas de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="3a14f-104">This procedure demonstrates the steps to create Replenishment rules.</span></span> <span data-ttu-id="3a14f-105">Las reglas de reabastecimiento se pueden usar para controlar la manera en que los productos se distribuyen a los almacenes al usar tránsito directo y estrategia de presión.</span><span class="sxs-lookup"><span data-stu-id="3a14f-105">Replenishment rules can be used to control how products are distributed to stores when using Cross-docking and Buyer´s push.</span></span> <span data-ttu-id="3a14f-106">Las reglas de reabastecimiento se pueden configurar para tiendas o grupos de tiendas.</span><span class="sxs-lookup"><span data-stu-id="3a14f-106">Replenishment rules can be set up for stores or store groups.</span></span> <span data-ttu-id="3a14f-107">El peso definido para cada línea en una regla controlará la manera en que las cantidades de productos se distribuirán entre almacenes al usar reglas de reabastecimiento como el método de distribución en tránsito directo o estrategia de presión.</span><span class="sxs-lookup"><span data-stu-id="3a14f-107">The weight defined for each line in a rule will control how the quantities of products will get distributed between the stores when using Replenishment rules as the distribution method in Cross-docking or Buyer´s push.</span></span> <span data-ttu-id="3a14f-108">Este procedimiento usa la empresa de prueba USRT.</span><span class="sxs-lookup"><span data-stu-id="3a14f-108">This procedure uses the USRT demo company.</span></span>

1. <span data-ttu-id="3a14f-109">Vaya a Reglas de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="3a14f-109">Go to Replenishment rules.</span></span>
2. <span data-ttu-id="3a14f-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="3a14f-110">Click New.</span></span>
3. <span data-ttu-id="3a14f-111">En el campo Regla de reabastecimiento, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3a14f-111">In the Replenishment rule field, type a value.</span></span>
4. <span data-ttu-id="3a14f-112">En el campo Descripción, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="3a14f-112">In the Description field, type a value.</span></span>
5. <span data-ttu-id="3a14f-113">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3a14f-113">Click Save.</span></span>
6. <span data-ttu-id="3a14f-114">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="3a14f-114">Click Add.</span></span>
7. <span data-ttu-id="3a14f-115">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3a14f-115">In the list, mark the selected row.</span></span>
    * <span data-ttu-id="3a14f-116">Puede elegir Jerarquía de reabastecimiento o Canal para el tipo.</span><span class="sxs-lookup"><span data-stu-id="3a14f-116">You can choose Replenishment hierarchy or Channel for the type.</span></span> <span data-ttu-id="3a14f-117">El valor controla si la selección en Nombre será una jerarquía de canales o un canal específico.</span><span class="sxs-lookup"><span data-stu-id="3a14f-117">The value controls whether the selection in Name will be a hierarchy of channels or a specific channel.</span></span>  <span data-ttu-id="3a14f-118">Para este ejemplo, déjelo establecido como una Jerarquía de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="3a14f-118">For this example, leave it set as Replenishment hierarchy.</span></span>  
8. <span data-ttu-id="3a14f-119">En el campo Nombre, seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3a14f-119">In the Name field, select a value.</span></span>
    * <span data-ttu-id="3a14f-120">El valor del peso predeterminado se rellena con el peso definido en el almacén.</span><span class="sxs-lookup"><span data-stu-id="3a14f-120">The default weight value is populated from the weight defined on the warehouse.</span></span>  <span data-ttu-id="3a14f-121">Este peso se puede usar para la Regla de reabastecimiento o puede especificar un nuevo peso en el campo Peso.</span><span class="sxs-lookup"><span data-stu-id="3a14f-121">This weight can be used for the Replenishment rule or you can enter a new weight in the Weight field.</span></span>  
9. <span data-ttu-id="3a14f-122">En el campo Peso, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="3a14f-122">In the Weight field, enter a number.</span></span>
10. <span data-ttu-id="3a14f-123">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="3a14f-123">Click Add.</span></span>
11. <span data-ttu-id="3a14f-124">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="3a14f-124">In the list, mark the selected row.</span></span>
12. <span data-ttu-id="3a14f-125">En el campo Tipo, seleccione "Canal".</span><span class="sxs-lookup"><span data-stu-id="3a14f-125">In the Type field, select 'Channel'.</span></span>
13. <span data-ttu-id="3a14f-126">En el campo Nombre, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="3a14f-126">In the Name field, enter or select a value.</span></span>
14. <span data-ttu-id="3a14f-127">En el campo Peso, escriba un número.</span><span class="sxs-lookup"><span data-stu-id="3a14f-127">In the Weight field, enter a number.</span></span>
15. <span data-ttu-id="3a14f-128">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="3a14f-128">Click Save.</span></span>


