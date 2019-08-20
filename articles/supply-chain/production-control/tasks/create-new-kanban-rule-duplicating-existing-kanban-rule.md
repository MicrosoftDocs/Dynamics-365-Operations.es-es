---
title: Crear una nueva regla kanban al duplicar una regla existente
description: Este procedimiento se centra en la creación de un duplicado de una regla kanban existente.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, InventItemIdLookupSimple
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3aef2725152d39e49070f33d0c56089200c94353
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1837815"
---
# <a name="create-a-new-kanban-rule-by-duplicating-an-existing-kanban-rule"></a><span data-ttu-id="25156-103">Crear una nueva regla kanban al duplicar una regla existente</span><span class="sxs-lookup"><span data-stu-id="25156-103">Create a new kanban rule by duplicating an existing kanban rule</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="25156-104">Este procedimiento se centra en la creación de un duplicado de una regla kanban existente.</span><span class="sxs-lookup"><span data-stu-id="25156-104">This procedure focuses on creating a duplicate of an existing kanban rule.</span></span> <span data-ttu-id="25156-105">Esto resulta útil si desea crear nuevas reglas kanban basadas en reglas kanban existentes.</span><span class="sxs-lookup"><span data-stu-id="25156-105">This is useful if you want to create new kanban rules based on existing kanban rules.</span></span> <span data-ttu-id="25156-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="25156-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="25156-107">Este procedimiento está pensado para el ingeniero de procesos o el administrador de flujo de valor, ya que preparan la producción para un flujo de producción cambiado o una nueva regla de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="25156-107">This procedure is intended for the process engineer or the value stream manager as they prepare production for a changed production flow or a new replenishment rule.</span></span>


## <a name="select-a-kanban-rule"></a><span data-ttu-id="25156-108">Seleccionar una regla kanban</span><span class="sxs-lookup"><span data-stu-id="25156-108">Select a kanban rule</span></span>
1. <span data-ttu-id="25156-109">Vaya a Reglas kanban.</span><span class="sxs-lookup"><span data-stu-id="25156-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="25156-110">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="25156-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="25156-111">Seleccione la regla kanban 000017 para el producto M0006.</span><span class="sxs-lookup"><span data-stu-id="25156-111">Select kanban rule 000017 for Product M0006.</span></span>  

## <a name="duplicate-a-kanban-rule"></a><span data-ttu-id="25156-112">Duplicar una regla kanban</span><span class="sxs-lookup"><span data-stu-id="25156-112">Duplicate a kanban rule</span></span>
1. <span data-ttu-id="25156-113">Haga clic en Duplicar regla kanban.</span><span class="sxs-lookup"><span data-stu-id="25156-113">Click Duplicate kanban rule.</span></span>
    * <span data-ttu-id="25156-114">Al duplicar una regla kanban, es posible cambiar el tipo, las fechas, las actividades y la selección de productos.</span><span class="sxs-lookup"><span data-stu-id="25156-114">When duplicating a kanban rule, it is possible to change type, dates, activities, and the product selection.</span></span> <span data-ttu-id="25156-115">Cambie el producto para este procedimiento en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="25156-115">Change the product for this procedure in the next step.</span></span>  
2. <span data-ttu-id="25156-116">En el campo Producto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="25156-116">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="25156-117">Seleccione M0007.</span><span class="sxs-lookup"><span data-stu-id="25156-117">Select M0007.</span></span>  
3. <span data-ttu-id="25156-118">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="25156-118">Click OK.</span></span>
    * <span data-ttu-id="25156-119">Tenga en cuenta que se ha crea un duplicado de la regla kanban 000017.</span><span class="sxs-lookup"><span data-stu-id="25156-119">Note that a duplicate of kanban rule 000017 is created.</span></span>    

