---
title: Crear una nueva regla kanban al duplicar una regla existente
description: Este procedimiento se centra en la creación de un duplicado de una regla kanban existente.
author: ChristianRytt
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: KanbanRules, KanbanRuleDuplicate, InventItemIdLookupSimple
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 84a0093d95c2f7084c7a0ed17f8b2f86d654b5d7
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3212228"
---
# <a name="create-a-new-kanban-rule-by-duplicating-an-existing-kanban-rule"></a><span data-ttu-id="e8965-103">Crear una nueva regla kanban al duplicar una regla existente</span><span class="sxs-lookup"><span data-stu-id="e8965-103">Create a new kanban rule by duplicating an existing kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e8965-104">Este procedimiento se centra en la creación de un duplicado de una regla kanban existente.</span><span class="sxs-lookup"><span data-stu-id="e8965-104">This procedure focuses on creating a duplicate of an existing kanban rule.</span></span> <span data-ttu-id="e8965-105">Esto resulta útil si desea crear nuevas reglas kanban basadas en reglas kanban existentes.</span><span class="sxs-lookup"><span data-stu-id="e8965-105">This is useful if you want to create new kanban rules based on existing kanban rules.</span></span> <span data-ttu-id="e8965-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="e8965-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="e8965-107">Este procedimiento está pensado para el ingeniero de procesos o el administrador de flujo de valor, ya que preparan la producción para un flujo de producción cambiado o una nueva regla de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="e8965-107">This procedure is intended for the process engineer or the value stream manager as they prepare production for a changed production flow or a new replenishment rule.</span></span>


## <a name="select-a-kanban-rule"></a><span data-ttu-id="e8965-108">Seleccionar una regla kanban</span><span class="sxs-lookup"><span data-stu-id="e8965-108">Select a kanban rule</span></span>
1. <span data-ttu-id="e8965-109">Vaya a Reglas kanban.</span><span class="sxs-lookup"><span data-stu-id="e8965-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="e8965-110">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="e8965-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="e8965-111">Seleccione la regla kanban 000017 para el producto M0006.</span><span class="sxs-lookup"><span data-stu-id="e8965-111">Select kanban rule 000017 for Product M0006.</span></span>  

## <a name="duplicate-a-kanban-rule"></a><span data-ttu-id="e8965-112">Duplicar una regla kanban</span><span class="sxs-lookup"><span data-stu-id="e8965-112">Duplicate a kanban rule</span></span>
1. <span data-ttu-id="e8965-113">Haga clic en Duplicar regla kanban.</span><span class="sxs-lookup"><span data-stu-id="e8965-113">Click Duplicate kanban rule.</span></span>
    * <span data-ttu-id="e8965-114">Al duplicar una regla kanban, es posible cambiar el tipo, las fechas, las actividades y la selección de productos.</span><span class="sxs-lookup"><span data-stu-id="e8965-114">When duplicating a kanban rule, it is possible to change type, dates, activities, and the product selection.</span></span> <span data-ttu-id="e8965-115">Cambie el producto para este procedimiento en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="e8965-115">Change the product for this procedure in the next step.</span></span>  
2. <span data-ttu-id="e8965-116">En el campo Producto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="e8965-116">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="e8965-117">Seleccione M0007.</span><span class="sxs-lookup"><span data-stu-id="e8965-117">Select M0007.</span></span>  
3. <span data-ttu-id="e8965-118">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="e8965-118">Click OK.</span></span>
    * <span data-ttu-id="e8965-119">Tenga en cuenta que se ha crea un duplicado de la regla kanban 000017.</span><span class="sxs-lookup"><span data-stu-id="e8965-119">Note that a duplicate of kanban rule 000017 is created.</span></span>    

