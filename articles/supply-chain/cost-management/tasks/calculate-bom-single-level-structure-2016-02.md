---
title: Calcular un L.MAT mediante una estructura de un solo nivel (febrero de 2016)
description: Este procedimiento muestra cómo calcular el coste de un producto terminado mediante la expansión de un único nivel que se basa en la hoja de Gestión de costes.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, InventItemPrice, BOMCalcDialog
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 013eddf1ba8e8cab3c87cb1f063d9bf886b0f833
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821402"
---
# <a name="calculate-a-bom-by-using-a-single-level-structure-february-2016"></a><span data-ttu-id="94fb9-103">Calcular un L.MAT mediante una estructura de un solo nivel (febrero de 2016)</span><span class="sxs-lookup"><span data-stu-id="94fb9-103">Calculate a BOM by using a single level structure (February 2016)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="94fb9-104">Este procedimiento muestra cómo calcular el coste de un producto terminado mediante la expansión de un único nivel que se basa en la hoja de Gestión de costes.</span><span class="sxs-lookup"><span data-stu-id="94fb9-104">This procedure shows how to calculate the cost of a finished product by using single level explosion that is based in the Costing sheet.</span></span> <span data-ttu-id="94fb9-105">Es la sexta tarea en las series de cálculo BOM.</span><span class="sxs-lookup"><span data-stu-id="94fb9-105">This is the sixth task in the BOM calculation series.</span></span> <span data-ttu-id="94fb9-106">La empresa de datos de prueba utilizada para crear esta tarea es USMF.</span><span class="sxs-lookup"><span data-stu-id="94fb9-106">The demo data company used to create this task is USMF.</span></span>

1. <span data-ttu-id="94fb9-107">Vaya a Productos emitidos.</span><span class="sxs-lookup"><span data-stu-id="94fb9-107">Go to Released products.</span></span>
2. <span data-ttu-id="94fb9-108">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="94fb9-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="94fb9-109">Seleccione el producto BOM_1</span><span class="sxs-lookup"><span data-stu-id="94fb9-109">Select product BOM_1.</span></span>  
3. <span data-ttu-id="94fb9-110">En el panel de acciones, haga clic en Gestionar costes.</span><span class="sxs-lookup"><span data-stu-id="94fb9-110">On the Action Pane, click Manage costs.</span></span>
4. <span data-ttu-id="94fb9-111">Haga clic en Precio de artículo.</span><span class="sxs-lookup"><span data-stu-id="94fb9-111">Click Item price.</span></span>
5. <span data-ttu-id="94fb9-112">Haga clic en Calcular coste del artículo.</span><span class="sxs-lookup"><span data-stu-id="94fb9-112">Click Calculate item cost.</span></span>
    * <span data-ttu-id="94fb9-113">Es posible que tenga que hacer la elipsis (...) para ver esta opción en el menú superior.</span><span class="sxs-lookup"><span data-stu-id="94fb9-113">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>  
6. <span data-ttu-id="94fb9-114">En el campo Versión de la gestión de costes, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="94fb9-114">In the Costing version field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="94fb9-115">Para esta demostración, seleccione 10.</span><span class="sxs-lookup"><span data-stu-id="94fb9-115">For this demo, select 10.</span></span> <span data-ttu-id="94fb9-116">Esta es la misma versión de gestión de costes utilizada para agregar el precio de coste a los componentes.</span><span class="sxs-lookup"><span data-stu-id="94fb9-116">This is the same costing version used for adding the cost price to the components.</span></span>  
7. <span data-ttu-id="94fb9-117">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="94fb9-117">Click OK.</span></span>
8. <span data-ttu-id="94fb9-118">Haga clic en Ver detalles de cálculo.</span><span class="sxs-lookup"><span data-stu-id="94fb9-118">Click View calculation details.</span></span>
    * <span data-ttu-id="94fb9-119">Es posible que tenga que hacer la elipsis (...) para ver esta opción en el menú superior.</span><span class="sxs-lookup"><span data-stu-id="94fb9-119">You may need to click the ellipsis (...) to see this option in the top menu.</span></span>    <span data-ttu-id="94fb9-120">A continuación se indica la composición del coste:  \*    10 se deriva de ITEM_A, 10 de ITEM_B, 10 de BOM_2.</span><span class="sxs-lookup"><span data-stu-id="94fb9-120">Here's the composition of the cost:  \*    10 is derived from ITEM_A, 10 from ITEM_B, 10 from BOM_2.</span></span> <span data-ttu-id="94fb9-121">En este caso no hay detalles para BOM_2, ya que se ha especificado como coste estándar de 10 pero no mediante el cálculo.</span><span class="sxs-lookup"><span data-stu-id="94fb9-121">In this case there are no details for BOM_2 because it was entered as a standard cost of 10 but not done through calculation.</span></span>  <span data-ttu-id="94fb9-122">\*    7 se deriva del tiempo de configuración, que es un coste constante, y el 7 adicional se deriva de la operación de tiempo de ejecución (Proceso).</span><span class="sxs-lookup"><span data-stu-id="94fb9-122">\*    7 is derived from the setup time, which is a constant cost, and additional 7 is derived from the run-time operation (Process).</span></span>  <span data-ttu-id="94fb9-123">\*    También hay otros importes que corresponden a costes indirectos.</span><span class="sxs-lookup"><span data-stu-id="94fb9-123">\*    There are also other amounts that correspond to indirect costs.</span></span>  
9. <span data-ttu-id="94fb9-124">@SysTaskRecorder: _RequestClose</span><span class="sxs-lookup"><span data-stu-id="94fb9-124">@SysTaskRecorder:_RequestClose</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]