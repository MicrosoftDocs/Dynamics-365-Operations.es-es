--- 
title: "Crear una nueva regla kanban de sustitución"
description: "Este procedimiento se centra en el reemplazo de una regla kanban existente por una nueva regla kanban en una fecha específica."
author: ChristianRytt
manager: AnnBe
ms.date: 06/20/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 12df41f14973628063b11f20f7368f47b2ad3488
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="create-a-replacement-kanban-rule"></a><span data-ttu-id="4fcb0-103">Crear una nueva regla kanban de sustitución</span><span class="sxs-lookup"><span data-stu-id="4fcb0-103">Create a replacement kanban rule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="4fcb0-104">Este procedimiento se centra en el reemplazo de una regla kanban existente por una nueva regla kanban en una fecha específica.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-104">This procedure focuses on replacing an existing kanban rule with a new kanban rule on a specific date.</span></span> <span data-ttu-id="4fcb0-105">Esto es útil cuando los cambios del flujo de producción o las reglas de reabastecimiento necesitan coordinarse y programarse.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-105">This is useful when changes in the production flow or replenishment rules need to be coordinated and scheduled.</span></span> <span data-ttu-id="4fcb0-106">La empresa de datos de demostración usada para crear el procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-106">The demo data company used to create procedure is USMF.</span></span> <span data-ttu-id="4fcb0-107">Este procedimiento está pensado para el ingeniero de procesos o el administrador de flujo de valor cuando preparan la producción para un flujo de producción cambiado o una nueva regla de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-107">This procedure is intended for the process engineer or the value stream manager when they prepare production for a changed production flow or a new replenishment rule.</span></span> <span data-ttu-id="4fcb0-108">Esta tarea reemplaza la regla kanban 000022 por una nueva regla y aumenta la cantidad máxima de 48 a 100 para la nueva regla.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-108">This task replaces kanban rule 000022 with a new rule and increases the maximum quantity from 48 to 100 for the new rule.</span></span>


## <a name="select-a-kanban-rule-to-replace"></a><span data-ttu-id="4fcb0-109">Seleccionar una regla kanban para reemplazar</span><span class="sxs-lookup"><span data-stu-id="4fcb0-109">Select a kanban rule to replace</span></span>
1. <span data-ttu-id="4fcb0-110">Vaya a Reglas kanban.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-110">Go to Kanban rules.</span></span>
2. <span data-ttu-id="4fcb0-111">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-111">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="4fcb0-112">Seleccione una regla 000022.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-112">Select kanban rule 000022.</span></span>  

## <a name="create-a-replacement-kanban-rule"></a><span data-ttu-id="4fcb0-113">Crear una nueva regla kanban de sustitución</span><span class="sxs-lookup"><span data-stu-id="4fcb0-113">Create a replacement kanban rule</span></span>
1. <span data-ttu-id="4fcb0-114">Haga clic en Reemplazar regla kanban.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-114">Click Replace kanban rule.</span></span>
2. <span data-ttu-id="4fcb0-115">En el campo Fecha de vigencia, especifique una fecha y una hora.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-115">In the Effective date field, enter a date and time.</span></span>
    * <span data-ttu-id="4fcb0-116">Seleccione una fecha en el futuro, por ejemplo, una semana desde ahora.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-116">Select a date in the future, such as one week from now.</span></span> <span data-ttu-id="4fcb0-117">Esta es la fecha y la hora en la que la nueva regla kanban se convierte en activa y reemplaza la regla kanban anterior.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-117">This is the date and time when the new kanban rule becomes active and replaces the old kanban rule.</span></span>  
    * <span data-ttu-id="4fcb0-118">Si la regla kanban cambia la ruta en el flujo de producción, se puede seleccionar otra actividad.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-118">If the kanban rule changes the path in the production flow,  another activity can be selected.</span></span>  <span data-ttu-id="4fcb0-119">En este procedimiento, mantendremos la actividad sin tocar.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-119">In this procedure, we will keep the activity untouched.</span></span>  
3. <span data-ttu-id="4fcb0-120">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="4fcb0-120">Click OK.</span></span>
    * <span data-ttu-id="4fcb0-121">Observe que se crea una nueva regla kanban para reemplazar la regla kanban 000022.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-121">Notice that a new kanban rule is created to replace kanban rule 000022.</span></span>  
    * <span data-ttu-id="4fcb0-122">La fecha de vigencia se establece en función de la fecha elegida cuando reemplaza la regla kanban.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-122">The effective date is set according to the date chosen when you replace the kanban rule.</span></span>  
4. <span data-ttu-id="4fcb0-123">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-123">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="4fcb0-124">Seleccione la regla kanban reemplazada 000022.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-124">Select the replaced kanban rule 000022.</span></span>  
    * <span data-ttu-id="4fcb0-125">Observe que la regla kanban reemplazada tiene la misma fecha que la fecha de vencimiento ya que es la fecha de cuándo expirará.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-125">Notice that the replaced kanban rule has the same date as the Expiration date because this is the date when it will expire.</span></span>  
5. <span data-ttu-id="4fcb0-126">En la lista, seleccione la fila 1.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-126">In the list, select row 1.</span></span>
    * <span data-ttu-id="4fcb0-127">Seleccione la nueva regla kanban en la parte superior de la lista.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-127">Select the new kanban rule on top of the list.</span></span> <span data-ttu-id="4fcb0-128">Esta es la regla kanban con el número regla kanban mayor.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-128">This is the kanban rule with the highest kanban rule number.</span></span>  
6. <span data-ttu-id="4fcb0-129">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-129">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="4fcb0-130">Haga clic en el número de la regla kanban para abrir la regla kanban.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-130">Click the kanban rule number to open the kanban rule.</span></span>  

## <a name="modify-maximum-quantity-for-the-replacement-kanban-rule"></a><span data-ttu-id="4fcb0-131">Modificar la cantidad máxima para la regla kanban de sustitución</span><span class="sxs-lookup"><span data-stu-id="4fcb0-131">Modify maximum quantity for the replacement kanban rule</span></span>
1. <span data-ttu-id="4fcb0-132">Defina la cantidad máxima en "100".</span><span class="sxs-lookup"><span data-stu-id="4fcb0-132">Set Maximum quantity to '100'.</span></span>
    * <span data-ttu-id="4fcb0-133">Expanda la ficha desplegable Cantidades para ver el campo Cantidad máxima.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-133">Expand the Quantities FastTab to see the Maximum quantity field.</span></span> <span data-ttu-id="4fcb0-134">El cambio de la cantidad máxima a 100 le permitirá que se procesen hasta 100 kanbans.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-134">Changing the maximum quantity to 100 will allow up to 100 kanbans to be processed.</span></span>    <span data-ttu-id="4fcb0-135">Este es el último paso de esta tarea.</span><span class="sxs-lookup"><span data-stu-id="4fcb0-135">This is the last step in this task.</span></span>  


