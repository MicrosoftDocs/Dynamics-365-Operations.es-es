--- 
title: Crear una nueva regla kanban de retirada
description: "Este procedimiento muestra la configuración necesaria para crear una regla kanban de retirada para transferir material en un entorno de producción ajustada."
author: ChristianRytt
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: KanbanRules, LeanProductionFlowActivityLookup, InventItemIdLookupSimple, UnitOfMeasureLookup, KanbanCreate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: b0c1f0f4ea3035ffb7c5a12c83c12a132cc65fd5
ms.contentlocale: es-es
ms.lasthandoff: 09/11/2018

---
# <a name="create-a-withdrawal-kanban-rule"></a><span data-ttu-id="bc6ac-103">Crear una nueva regla kanban de retirada</span><span class="sxs-lookup"><span data-stu-id="bc6ac-103">Create a withdrawal kanban rule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="bc6ac-104">Este procedimiento muestra la configuración necesaria para crear una regla kanban de retirada para transferir material en un entorno de producción ajustada.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-104">This procedure shows the setup that is needed to create a withdrawal kanban rule for transferring material in a lean environment.</span></span> <span data-ttu-id="bc6ac-105">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-105">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="bc6ac-106">Este procedimiento está pensado para el Ingeniero de procesos o el Administrador de flujo de valor, ya que preparan el reabastecimiento de material nuevo o modificado.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-106">This procedure is intended for the Process Engineer or the Value Stream Manager, as they prepare replenishment of new or modified material.</span></span>


## <a name="create-new-kanban-rule"></a><span data-ttu-id="bc6ac-107">Crear nueva regla kanban</span><span class="sxs-lookup"><span data-stu-id="bc6ac-107">Create new kanban rule</span></span>
1. <span data-ttu-id="bc6ac-108">Vaya a Reglas kanban.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-108">Go to Kanban rules.</span></span>
2. <span data-ttu-id="bc6ac-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-109">Click New.</span></span>
3. <span data-ttu-id="bc6ac-110">En el campo Tipo, seleccione "Retirada".</span><span class="sxs-lookup"><span data-stu-id="bc6ac-110">In the Type field, select 'Withdrawal'.</span></span>
    * <span data-ttu-id="bc6ac-111">El tipo Retirada se usa para que las reglas kanban transfieran material o mercancías.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-111">The Withdrawal type is used for kanban rules to transfer material or goods.</span></span>  
4. <span data-ttu-id="bc6ac-112">En el campo Actividad del primer plan, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-112">In the First plan activity field, enter or select a value.</span></span>
    * <span data-ttu-id="bc6ac-113">Seleccione ReplenishSpeakerComponents.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-113">Select ReplenishSpeakerComponents.</span></span>   <span data-ttu-id="bc6ac-114">Esta actividad se configura para mover componentes del almacén 11, ubicación 11 al almacén 12 y la ubicación 12.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-114">This activity is set up to move components from warehouse 11, location 11 to warehouse 12, and location 12.</span></span>  
5. <span data-ttu-id="bc6ac-115">En el campo Producto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-115">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="bc6ac-116">Seleccione M0007.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-116">Select M0007.</span></span>  
6. <span data-ttu-id="bc6ac-117">En el campo Plazo, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-117">In the Lead time field, enter a number.</span></span>
    * <span data-ttu-id="bc6ac-118">Por ejemplo, 60.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-118">For example, 60.</span></span>  
7. <span data-ttu-id="bc6ac-119">En el campo Unidad de medida, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-119">In the Unit of measure field, enter or select a value.</span></span>
    * <span data-ttu-id="bc6ac-120">Por ejemplo, Minutos.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-120">For example, Minutes.</span></span>  

## <a name="set-quantities-for-kanban"></a><span data-ttu-id="bc6ac-121">Establecer cantidades para kanban</span><span class="sxs-lookup"><span data-stu-id="bc6ac-121">Set quantities for kanban</span></span>
1. <span data-ttu-id="bc6ac-122">Defina la cantidad predeterminada en "5".</span><span class="sxs-lookup"><span data-stu-id="bc6ac-122">Set Default quantity to '5'.</span></span>
    * <span data-ttu-id="bc6ac-123">Esta es la cantidad que se transferirá para cada kanban.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-123">This is the quantity that will be transferred for each kanban.</span></span>  
2. <span data-ttu-id="bc6ac-124">En el campo Cantidad kanban fija, especifique "2".</span><span class="sxs-lookup"><span data-stu-id="bc6ac-124">In the Fixed kanban quantity field, enter '2'.</span></span>
    * <span data-ttu-id="bc6ac-125">Este es el importe de kanbans que deben estar activos.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-125">This is the amount of kanbans that should be active.</span></span> <span data-ttu-id="bc6ac-126">En este caso, 2 kanbans que transfieren 5 por cada uno.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-126">In this case, 2 kanbans transferring 5 each.</span></span>  
3. <span data-ttu-id="bc6ac-127">En el campo Mínimo de límite de alerta, especifique "1".</span><span class="sxs-lookup"><span data-stu-id="bc6ac-127">In the Alert boundary minimum field, enter '1'.</span></span>
    * <span data-ttu-id="bc6ac-128">Se usa para realizar el seguimiento del importe mínimo de kanbans completos que deben encontrarse en el destino.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-128">Used to keep track of the minimum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="bc6ac-129">Por ejemplo, esto se usa en la visión general de la cantidad kanban.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-129">For example, this is used on the kanban quantity overview.</span></span>  
4. <span data-ttu-id="bc6ac-130">En el campo Máximo de límite de alerta, especifique "2".</span><span class="sxs-lookup"><span data-stu-id="bc6ac-130">In the Alert boundary maximum field, enter '2'.</span></span>
    * <span data-ttu-id="bc6ac-131">Se usa para realizar el seguimiento del importe máximo de kanbans completos que deben encontrarse en el destino.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-131">Used to keep track of the maximum amount of full kanbans that should be at the destination.</span></span> <span data-ttu-id="bc6ac-132">Por ejemplo, esto se usa en la visión general de la cantidad kanban.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-132">For example, this is used on the kanban quantity overview.</span></span>  

## <a name="create-kanbans"></a><span data-ttu-id="bc6ac-133">Crear kanbans</span><span class="sxs-lookup"><span data-stu-id="bc6ac-133">Create kanbans</span></span>
1. <span data-ttu-id="bc6ac-134">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-134">Click Save.</span></span>
    * <span data-ttu-id="bc6ac-135">La regla kanban se tiene que guardar para que se puedan crear los kanbans.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-135">The kanban rule needs to be saved before kanbans can be created.</span></span>  
2. <span data-ttu-id="bc6ac-136">Haga clic en Agregar.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-136">Click Add.</span></span>
    * <span data-ttu-id="bc6ac-137">Tenga en cuenta que no hay kanbans activos porque el "Número de kanbans nuevos" es 2, lo que es igual a la "Cantidad kanban fija".</span><span class="sxs-lookup"><span data-stu-id="bc6ac-137">Note that there are no active kanbans because the suggested 'Number of new kanbans' is 2, which is equal to the 'Fixed kanban quantity'.</span></span>  
3. <span data-ttu-id="bc6ac-138">Haga clic en Crear.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-138">Click Create.</span></span>
    * <span data-ttu-id="bc6ac-139">Esto creará dos kanbans.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-139">This will create two kanbans.</span></span>  
    * <span data-ttu-id="bc6ac-140">Tenga en cuenta que se crearon 2 kanbans, para 5 cada uno, para esta regla kanban de retirada.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-140">Note that 2 kanbans, for 5 each, was created for this withdrawal kanban rule.</span></span>  <span data-ttu-id="bc6ac-141">Este es el último paso de este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="bc6ac-141">This is the last step in this procedure.</span></span>  


