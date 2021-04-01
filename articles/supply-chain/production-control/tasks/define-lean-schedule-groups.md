---
title: Definir grupos de programación lean
description: Los grupos de programación lean se definen para agrupar y distinguir productos en la programación kanban.
author: cvocph
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LeanScheduleGroup, GanttColorTableLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4e4ad3eb1f7c73d0b6671e2d1698d0647f6dbb93
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5257252"
---
# <a name="define-lean-schedule-groups"></a><span data-ttu-id="90450-103">Definir grupos de programación lean</span><span class="sxs-lookup"><span data-stu-id="90450-103">Define lean schedule groups</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="90450-104">Los grupos de programación lean se definen para agrupar y distinguir productos en la programación kanban.</span><span class="sxs-lookup"><span data-stu-id="90450-104">Lean schedule groups are defined to group and distinguish products in kanban scheduling.</span></span> <span data-ttu-id="90450-105">La agrupación se puede realizar como asociación genérica por empresa o de manera específica para una celda de trabajo.</span><span class="sxs-lookup"><span data-stu-id="90450-105">The grouping can be done as generic association per company or specific to a work cell.</span></span> <span data-ttu-id="90450-106">Cada grupo tiene un código de color asignado para indicación visual en la ListPage de programación kanban.</span><span class="sxs-lookup"><span data-stu-id="90450-106">Each group has a color code assigned for visual indication in the kanban scheduling listpage.</span></span> <span data-ttu-id="90450-107">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="90450-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="define-lean-scheduling-group"></a><span data-ttu-id="90450-108">Definir grupo de programación lean</span><span class="sxs-lookup"><span data-stu-id="90450-108">Define lean scheduling group</span></span>
1. <span data-ttu-id="90450-109">Vaya a Gestión de información de productos > Lean manufacturing > Grupos de programación lean.</span><span class="sxs-lookup"><span data-stu-id="90450-109">Go to Product information management > Lean manufacturing > Lean schedule groups.</span></span>
2. <span data-ttu-id="90450-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="90450-110">Click New.</span></span>
3. <span data-ttu-id="90450-111">En el campo Grupo de programación, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="90450-111">In the Schedule group field, type a value.</span></span>
    * <span data-ttu-id="90450-112">Un grupo de programación se puede definir como grupo global o específico de una celda de trabajo.</span><span class="sxs-lookup"><span data-stu-id="90450-112">A schedule group can be defined as global group or specific to a work cell.</span></span> <span data-ttu-id="90450-113">En este ejemplo sencillo, definimos un grupo global y la celda de trabajo se mantiene vacía.</span><span class="sxs-lookup"><span data-stu-id="90450-113">In this simple example, we define a global group, and the work cell is kept empty.</span></span> <span data-ttu-id="90450-114">La configuración de este grupo se aplica a todas las celdas de trabajo que no tienen grupos de programación específicos.</span><span class="sxs-lookup"><span data-stu-id="90450-114">The settings of this group apply to all work cells that do not have specific schedule groups.</span></span>  
4. <span data-ttu-id="90450-115">Seleccione un color en la selección del color.</span><span class="sxs-lookup"><span data-stu-id="90450-115">Select a color from the color selection.</span></span>
    * <span data-ttu-id="90450-116">Los colores se usan para resaltar los trabajos de la página de lista de programación kanban o el tablero de proceso kanban.</span><span class="sxs-lookup"><span data-stu-id="90450-116">The colors are used to highlight the jobs on the kanban schedule list page or the kanban process board.</span></span>  
5. <span data-ttu-id="90450-117">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="90450-117">In the list, mark the selected row.</span></span>
6. <span data-ttu-id="90450-118">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="90450-118">In the list, click the link in the selected row.</span></span>

## <a name="associate-product"></a><span data-ttu-id="90450-119">Asociar producto</span><span class="sxs-lookup"><span data-stu-id="90450-119">Associate product</span></span>
1. <span data-ttu-id="90450-120">Asociar un producto específico</span><span class="sxs-lookup"><span data-stu-id="90450-120">Associate a specific product</span></span>
    * <span data-ttu-id="90450-121">Hay dos formas de asociar productos a grupos de programación lean, como producto específico (Tipo de relación de artículos = artículo) o como parte de una clave de asignación de artículos (tipo de relación de artículo = grupo).</span><span class="sxs-lookup"><span data-stu-id="90450-121">There are two ways to associate products to lean schedule groups, either as a specific product (Item relation type = Item) or as part of an item allocation key (item relation type = group).</span></span>    
2. <span data-ttu-id="90450-122">En el campo Tipo de relación de artículos, seleccione Artículo.</span><span class="sxs-lookup"><span data-stu-id="90450-122">In the Item relation type field, select Item</span></span>
3. <span data-ttu-id="90450-123">En el campo Código de artículo, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="90450-123">In the Item number field, type a value.</span></span>
4. <span data-ttu-id="90450-124">En el campo Índice de capacidad de proceso, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="90450-124">In the Throughput ratio field, enter a number.</span></span>
    * <span data-ttu-id="90450-125">El índice de capacidad de proceso predeterminado es 1, lo que significa que los productos relacionados consumen exactamente la capacidad especificada en las actividades de proceso de los flujos de producción.</span><span class="sxs-lookup"><span data-stu-id="90450-125">The default Throughput ratio is 1, which means that the related products consume exactly the capacity specified in the process activites of the production flows.</span></span> <span data-ttu-id="90450-126">El índice de capacidad de proceso > 1 define un consumo superior de recursos, el índice de capacidad de proceso < 1 define un consumo menor de recursos.</span><span class="sxs-lookup"><span data-stu-id="90450-126">Throughput ratio > 1 defines a higher resource consumption, Throughput ratio < 1 defines a lower resource consumption.</span></span> <span data-ttu-id="90450-127">El índice se usa en el cálculo de costes y en el cálculo del consumo de trabajos kanban.</span><span class="sxs-lookup"><span data-stu-id="90450-127">The ratio is used in the cost calculation and in the calculation of the kanban job consumption.</span></span>  

## <a name="associate-item-allocation-key"></a><span data-ttu-id="90450-128">Asociar clave de asignación de artículos</span><span class="sxs-lookup"><span data-stu-id="90450-128">Associate item allocation key</span></span>
1. <span data-ttu-id="90450-129">Asociar una clave de asignación de artículos</span><span class="sxs-lookup"><span data-stu-id="90450-129">Associate an item allocation key</span></span>
    * <span data-ttu-id="90450-130">Agregue una asociación a una clave de asignación de artículos mediante el grupo Tipo de relación de artículos.</span><span class="sxs-lookup"><span data-stu-id="90450-130">Add an association to an item allocation key by using the Item relation type Group.</span></span>   <span data-ttu-id="90450-131">Tenga en cuenta que para este proceso necesita una clave de asignación de artículos de previsión definida en sus datos.</span><span class="sxs-lookup"><span data-stu-id="90450-131">Note that for this process, you need a forecast item alllocation key defined in your data.</span></span>  
2. <span data-ttu-id="90450-132">En el campo Tipo de relación de artículos, seleccione Grupo.</span><span class="sxs-lookup"><span data-stu-id="90450-132">In the Item relation type field, select Group</span></span>
3. <span data-ttu-id="90450-133">En el campo Clave de asignación de artículos, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="90450-133">In the Item allocation key field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="90450-134">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="90450-134">In the list, click the link in the selected row.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]