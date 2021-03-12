---
title: Calcular un L.MAT mediante una estructura multinivel (febrero de 2016)
description: Este procedimiento muestra cómo calcular el coste de un producto terminado mediante la expansión multinivel basada en la hoja de Gestión de costes.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog, BOMCalcTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f07bab0bab5553764982b44d9b135b4baa8310f9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987613"
---
# <a name="calculate-a-bom-by-using-a-multilevel-structure-february-2016"></a><span data-ttu-id="f263f-103">Calcular un L.MAT mediante una estructura multinivel (febrero de 2016)</span><span class="sxs-lookup"><span data-stu-id="f263f-103">Calculate a BOM by using a multilevel structure (February 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f263f-104">Este procedimiento muestra cómo calcular el coste de un producto terminado mediante la expansión multinivel basada en la hoja de Gestión de costes.</span><span class="sxs-lookup"><span data-stu-id="f263f-104">This procedure shows how to calculate the cost of a finished product by using multilevel explosion that is based in the Costing sheet.</span></span> <span data-ttu-id="f263f-105">Es la séptima tarea en las series de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="f263f-105">It is the seventh task in the BOM calculation series.</span></span> <span data-ttu-id="f263f-106">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="f263f-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="f263f-107">Vaya a Gestión de información de productos > Productos > Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="f263f-107">Go to Product information management > Products > Released products.</span></span>
2. <span data-ttu-id="f263f-108">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="f263f-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="f263f-109">Seleccione el producto BOM_1</span><span class="sxs-lookup"><span data-stu-id="f263f-109">Select product BOM_1.</span></span>  
3. <span data-ttu-id="f263f-110">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="f263f-110">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="f263f-111">Haga clic en Precio de artículo.</span><span class="sxs-lookup"><span data-stu-id="f263f-111">Click Item price.</span></span>
5. <span data-ttu-id="f263f-112">Haga clic en Calcular coste del artículo.</span><span class="sxs-lookup"><span data-stu-id="f263f-112">Click Calculate item cost.</span></span>
    * <span data-ttu-id="f263f-113">Es posible que tenga que hacer la elipsis (...) para ver esta opción en el menú superior.</span><span class="sxs-lookup"><span data-stu-id="f263f-113">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  
6. <span data-ttu-id="f263f-114">En el campo Versión de la gestión de costes, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="f263f-114">In the Costing version field, enter or select a value.</span></span>
    * <span data-ttu-id="f263f-115">Seleccione la versión de Gestión de costes 20, dado que el tipo de Coste planificado y el Modo de expansión es Multinivel.</span><span class="sxs-lookup"><span data-stu-id="f263f-115">Select Costing version 20, because it's Planned cost type and Explosion mode is Multilevel.</span></span>   <span data-ttu-id="f263f-116">El modo de expansión Multinivel es para los costes planificados y las simulaciones.</span><span class="sxs-lookup"><span data-stu-id="f263f-116">The Multilevel explosion mode is for planned costs and simulations.</span></span> <span data-ttu-id="f263f-117">No se usa para los costes estándar.</span><span class="sxs-lookup"><span data-stu-id="f263f-117">It is not used for standard cost.</span></span>  
7. <span data-ttu-id="f263f-118">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="f263f-118">Click OK.</span></span>
8. <span data-ttu-id="f263f-119">Haga clic en Ver detalles de cálculo.</span><span class="sxs-lookup"><span data-stu-id="f263f-119">Click View calculation details.</span></span>
    * <span data-ttu-id="f263f-120">Es posible que tenga que hacer la elipsis (...) para ver esta opción en el menú superior.</span><span class="sxs-lookup"><span data-stu-id="f263f-120">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  <span data-ttu-id="f263f-121">En este caso, observe cómo se ha calculado BOM_2 teniendo en cuenta en cuenta la materia prima, el proceso y los costes generales con un total de 29,40 en lugar del coste estándar de 10, que se ha activado en la Guía de tareas inicial en esta serie.</span><span class="sxs-lookup"><span data-stu-id="f263f-121">In this case, notice how BOM_2 has been calculated taking into account the raw material, process, and overhead with a total of 29,40 instead of the standard cost of 10 that was activated in the initial task guide in this series.</span></span>  
9. <span data-ttu-id="f263f-122">Haga clic en la pestaña de la hoja Gestión de costes.</span><span class="sxs-lookup"><span data-stu-id="f263f-122">Click the Costing sheet tab.</span></span>
    * <span data-ttu-id="f263f-123">Pasando a la pestaña de la hoja Gestión de costes, los totales por grupo de costes son diferentes en relación con el cálculo hecho en la guía de tareas anterior.</span><span class="sxs-lookup"><span data-stu-id="f263f-123">Moving to the Costing sheet tab, the totals per cost group are different compared to the calculation done in previous task guide.</span></span>  
10. <span data-ttu-id="f263f-124">En el campo Nivel, seleccione "Multi".</span><span class="sxs-lookup"><span data-stu-id="f263f-124">In the Level field, select 'Multi'.</span></span>
    * <span data-ttu-id="f263f-125">Al seleccionar Múltiple, los costes se clasifican según la composición de BOM_2, donde 10 se deriva del grupo de costes M1 (ITEM_C), y 15,60 se deriva de la fabricación donde L2 es el grupo de costes.</span><span class="sxs-lookup"><span data-stu-id="f263f-125">When selecting Multi, the costs are classified according to the composition of BOM_2, where 10 is derived from the M1 cost group (ITEM_C), and 15,60 is derived from its manufacturing where the cost group is L2.</span></span> <span data-ttu-id="f263f-126">Los costes indirectos también varían.</span><span class="sxs-lookup"><span data-stu-id="f263f-126">Indirect costs also vary.</span></span>  
11. <span data-ttu-id="f263f-127">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f263f-127">Close the page.</span></span>
12. <span data-ttu-id="f263f-128">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="f263f-128">Close the page.</span></span>

