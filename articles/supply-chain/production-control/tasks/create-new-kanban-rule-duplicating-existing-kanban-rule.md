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
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3b89fca4e55aa852bd127eb9b1bda07c0e5bcdc0
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5255142"
---
# <a name="create-a-new-kanban-rule-by-duplicating-an-existing-kanban-rule"></a><span data-ttu-id="ea5ce-103">Crear una nueva regla kanban al duplicar una regla existente</span><span class="sxs-lookup"><span data-stu-id="ea5ce-103">Create a new kanban rule by duplicating an existing kanban rule</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ea5ce-104">Este procedimiento se centra en la creación de un duplicado de una regla kanban existente.</span><span class="sxs-lookup"><span data-stu-id="ea5ce-104">This procedure focuses on creating a duplicate of an existing kanban rule.</span></span> <span data-ttu-id="ea5ce-105">Esto resulta útil si desea crear nuevas reglas kanban basadas en reglas kanban existentes.</span><span class="sxs-lookup"><span data-stu-id="ea5ce-105">This is useful if you want to create new kanban rules based on existing kanban rules.</span></span> <span data-ttu-id="ea5ce-106">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="ea5ce-106">The demo data company used to create this procedure is USMF.</span></span> <span data-ttu-id="ea5ce-107">Este procedimiento está pensado para el ingeniero de procesos o el administrador de flujo de valor, ya que preparan la producción para un flujo de producción cambiado o una nueva regla de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="ea5ce-107">This procedure is intended for the process engineer or the value stream manager as they prepare production for a changed production flow or a new replenishment rule.</span></span>


## <a name="select-a-kanban-rule"></a><span data-ttu-id="ea5ce-108">Seleccionar una regla kanban</span><span class="sxs-lookup"><span data-stu-id="ea5ce-108">Select a kanban rule</span></span>
1. <span data-ttu-id="ea5ce-109">Vaya a Reglas kanban.</span><span class="sxs-lookup"><span data-stu-id="ea5ce-109">Go to Kanban rules.</span></span>
2. <span data-ttu-id="ea5ce-110">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="ea5ce-110">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="ea5ce-111">Seleccione la regla kanban 000017 para el producto M0006.</span><span class="sxs-lookup"><span data-stu-id="ea5ce-111">Select kanban rule 000017 for Product M0006.</span></span>  

## <a name="duplicate-a-kanban-rule"></a><span data-ttu-id="ea5ce-112">Duplicar una regla kanban</span><span class="sxs-lookup"><span data-stu-id="ea5ce-112">Duplicate a kanban rule</span></span>
1. <span data-ttu-id="ea5ce-113">Haga clic en Duplicar regla kanban.</span><span class="sxs-lookup"><span data-stu-id="ea5ce-113">Click Duplicate kanban rule.</span></span>
    * <span data-ttu-id="ea5ce-114">Al duplicar una regla kanban, es posible cambiar el tipo, las fechas, las actividades y la selección de productos.</span><span class="sxs-lookup"><span data-stu-id="ea5ce-114">When duplicating a kanban rule, it is possible to change type, dates, activities, and the product selection.</span></span> <span data-ttu-id="ea5ce-115">Cambie el producto para este procedimiento en el paso siguiente.</span><span class="sxs-lookup"><span data-stu-id="ea5ce-115">Change the product for this procedure in the next step.</span></span>  
2. <span data-ttu-id="ea5ce-116">En el campo Producto, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ea5ce-116">In the Product field, enter or select a value.</span></span>
    * <span data-ttu-id="ea5ce-117">Seleccione M0007.</span><span class="sxs-lookup"><span data-stu-id="ea5ce-117">Select M0007.</span></span>  
3. <span data-ttu-id="ea5ce-118">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ea5ce-118">Click OK.</span></span>
    * <span data-ttu-id="ea5ce-119">Tenga en cuenta que se ha crea un duplicado de la regla kanban 000017.</span><span class="sxs-lookup"><span data-stu-id="ea5ce-119">Note that a duplicate of kanban rule 000017 is created.</span></span>    



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]