---
title: Calcular un L.MAT mediante una estructura de un solo nivel (febrero de 2016)
description: Este procedimiento muestra cómo calcular el coste de un producto terminado mediante la expansión de un único nivel que se basa en la hoja de Gestión de costes.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 83a62966e343a9b1c073c2d6ec1c1b69b1daddbb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436931"
---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016"></a><span data-ttu-id="eb489-103">Calcular un L.MAT mediante una estructura de un solo nivel (febrero de 2016)</span><span class="sxs-lookup"><span data-stu-id="eb489-103">Calculate a BOM by using a single level structure (February 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="eb489-104">Este procedimiento muestra cómo calcular el coste de un producto terminado mediante la expansión de un único nivel que se basa en la hoja de Gestión de costes.</span><span class="sxs-lookup"><span data-stu-id="eb489-104">This procedure shows how to calculate the cost of a finished product by using single level explosion that is based in the Costing sheet.</span></span> <span data-ttu-id="eb489-105">Es la sexta tarea en las series de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="eb489-105">This is the sixth task in the BOM calculation series.</span></span> <span data-ttu-id="eb489-106">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="eb489-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="eb489-107">Vaya a Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="eb489-107">Go to Released products.</span></span>
2. <span data-ttu-id="eb489-108">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="eb489-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="eb489-109">Seleccione el producto BOM_1</span><span class="sxs-lookup"><span data-stu-id="eb489-109">Select product BOM_1.</span></span>  
3. <span data-ttu-id="eb489-110">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="eb489-110">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="eb489-111">Haga clic en Precio de artículo.</span><span class="sxs-lookup"><span data-stu-id="eb489-111">Click Item price.</span></span>
5. <span data-ttu-id="eb489-112">Haga clic en Calcular coste del artículo.</span><span class="sxs-lookup"><span data-stu-id="eb489-112">Click Calculate item cost.</span></span>
    * <span data-ttu-id="eb489-113">Es posible que tenga que hacer la elipsis (...) para ver esta opción en el menú superior.</span><span class="sxs-lookup"><span data-stu-id="eb489-113">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  
6. <span data-ttu-id="eb489-114">En el campo Versión de la gestión de costes, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="eb489-114">In the Costing version field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="eb489-115">Para esta demostración, seleccione 10.</span><span class="sxs-lookup"><span data-stu-id="eb489-115">For this demo, select 10.</span></span> <span data-ttu-id="eb489-116">Esta es la misma versión de gestión de costes utilizada para agregar el precio de coste a los componentes.</span><span class="sxs-lookup"><span data-stu-id="eb489-116">This is the same costing version used for adding the cost price to the components.</span></span>  
7. <span data-ttu-id="eb489-117">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="eb489-117">Click OK.</span></span>
8. <span data-ttu-id="eb489-118">Haga clic en Ver detalles de cálculo.</span><span class="sxs-lookup"><span data-stu-id="eb489-118">Click View calculation details.</span></span>
    * <span data-ttu-id="eb489-119">Es posible que tenga que hacer la elipsis (...) para ver esta opción en el menú superior.</span><span class="sxs-lookup"><span data-stu-id="eb489-119">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>    <span data-ttu-id="eb489-120">A continuación se indica la composición del coste:  \*    10 se deriva de ITEM_A, 10 de ITEM_B, 10 de BOM_2.</span><span class="sxs-lookup"><span data-stu-id="eb489-120">Here's the composition of the cost:  \*    10 is derived from ITEM_A, 10 from ITEM_B, 10 from BOM_2.</span></span> <span data-ttu-id="eb489-121">En este caso no hay detalles para BOM_2, ya que se ha especificado como coste estándar de 10 pero no mediante el cálculo.</span><span class="sxs-lookup"><span data-stu-id="eb489-121">In this case there are no details for BOM_2 because it was entered as a standard cost of 10 but not done through calculation.</span></span>  <span data-ttu-id="eb489-122">\*    7 se deriva del tiempo de configuración, que es un coste constante, y el 7 adicional se deriva de la operación de tiempo de ejecución (Proceso).</span><span class="sxs-lookup"><span data-stu-id="eb489-122">\*    7 is derived from the setup time, which is a constant cost, and additional 7 is derived from the run-time operation (Process).</span></span>  <span data-ttu-id="eb489-123">\*    También hay otros importes que corresponden a costes indirectos.</span><span class="sxs-lookup"><span data-stu-id="eb489-123">\*    There are also other amounts that correspond to indirect costs.</span></span>  
9. <span data-ttu-id="eb489-124">@SysTaskRecorder: _RequestClose</span><span class="sxs-lookup"><span data-stu-id="eb489-124">@SysTaskRecorder:_RequestClose</span></span>

