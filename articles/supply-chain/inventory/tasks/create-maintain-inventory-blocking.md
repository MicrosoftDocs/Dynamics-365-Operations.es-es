---
title: "Creación y mantenimiento de un bloqueo del inventario"
description: "Este procedimiento muestra cómo impedir que se reserve inventario disponible físico a través de otros documentos de origen de salida mediante el bloqueo de inventario."
author: perlynne
manager: AnnBe
ms.date: 12/02/2015
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: d7ad19f2bba3cf0f0254d9eb4ee0ae6b1c5eac2e
ms.contentlocale: es-es
ms.lasthandoff: 01/17/2018

---
# <a name="create-and-maintain-inventory-blocking"></a><span data-ttu-id="1008f-103">Creación y mantenimiento de un bloqueo del inventario</span><span class="sxs-lookup"><span data-stu-id="1008f-103">Create and maintain inventory blocking</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="1008f-104">Este procedimiento muestra cómo impedir que se reserve inventario disponible físico a través de otros documentos de origen de salida mediante el bloqueo de inventario.</span><span class="sxs-lookup"><span data-stu-id="1008f-104">This procedure shows how to prevent physical on-hand inventory from being reserved by other outbound source documents by using the inventory blocking.</span></span> <span data-ttu-id="1008f-105">Puede ejecutar el procedimiento en la empresa de datos de demostración USMF con los valores de ejemplo que se muestran.</span><span class="sxs-lookup"><span data-stu-id="1008f-105">You can run the procedure in demo data company USMF using the example values that are shown.</span></span> <span data-ttu-id="1008f-106">Necesita tener un artículo con inventario disponible físico antes de comenzar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="1008f-106">You need to have an item with physical on-hand inventory available before you start this procedure.</span></span>


## <a name="create-an-inventory-blocking"></a><span data-ttu-id="1008f-107">Creación de un bloqueo de inventario</span><span class="sxs-lookup"><span data-stu-id="1008f-107">Create an inventory blocking</span></span>
1. <span data-ttu-id="1008f-108">Vaya a Gestión del inventario > Tareas periódicas > Bloqueo del inventario.</span><span class="sxs-lookup"><span data-stu-id="1008f-108">Go to Inventory management > Periodic tasks > Inventory blocking.</span></span>
2. <span data-ttu-id="1008f-109">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="1008f-109">Click New.</span></span>
3. <span data-ttu-id="1008f-110">En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1008f-110">In the Item number field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="1008f-111">En la lista, seleccione el artículo que desee elegir.</span><span class="sxs-lookup"><span data-stu-id="1008f-111">In the list, select the item you want to choose.</span></span>
    * <span data-ttu-id="1008f-112">Seleccione un número de artículo con inventario disponible físico que desee bloquear.</span><span class="sxs-lookup"><span data-stu-id="1008f-112">Select an item number with physical on-hand inventory that you want to block.</span></span> <span data-ttu-id="1008f-113">Si está usando USMF, puede seleccionar el artículo M9201.</span><span class="sxs-lookup"><span data-stu-id="1008f-113">If you’re using USMF you can select item M9201.</span></span>  
5. <span data-ttu-id="1008f-114">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="1008f-114">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="1008f-115">Si está usando el artículo M9201, es necesario seleccionar un valor inferior a 200.</span><span class="sxs-lookup"><span data-stu-id="1008f-115">If you’re using item M9201, you need to select less than 200.</span></span>  
6. <span data-ttu-id="1008f-116">Expanda la sección Dimensiones de inventario.</span><span class="sxs-lookup"><span data-stu-id="1008f-116">Toggle the expansion of the Inventory dimensions section.</span></span>
7. <span data-ttu-id="1008f-117">En el campo Almacén, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1008f-117">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="1008f-118">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="1008f-118">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="1008f-119">Si está usando el artículo M9201, puede seleccionar el almacén 51.</span><span class="sxs-lookup"><span data-stu-id="1008f-119">If you’re using item M9201, you can select warehouse 51.</span></span>  
9. <span data-ttu-id="1008f-120">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="1008f-120">Click Save.</span></span>

## <a name="update-the-conditions-of-the-inventory-blocking"></a><span data-ttu-id="1008f-121">Actualización de las condiciones de bloqueo de inventario</span><span class="sxs-lookup"><span data-stu-id="1008f-121">Update the conditions of the inventory blocking</span></span>
1. <span data-ttu-id="1008f-122">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="1008f-122">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="1008f-123">Actualice el campo de cantidad de inventario para reflejar la cantidad que bloquear.</span><span class="sxs-lookup"><span data-stu-id="1008f-123">Update the inventory quantity field to reflect the quantity to block.</span></span>  
2. <span data-ttu-id="1008f-124">En el campo Fecha prevista, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="1008f-124">In the Expected date field, enter a date.</span></span>
    * <span data-ttu-id="1008f-125">Es posible que desee indicar cuándo se espera que el inventario bloqueado quede disponible para reserva asignando una fecha prevista.</span><span class="sxs-lookup"><span data-stu-id="1008f-125">You might want to indicate when the blocked inventory is expected to become available for reservation by assigning an expected date.</span></span> <span data-ttu-id="1008f-126">Si la opción Recepciones previstas está seleccionada para el bloqueo de inventario, como lo está de manera predeterminada cuando se crea manualmente un bloqueo, esta fecha aparecerá en la transacción prevista.</span><span class="sxs-lookup"><span data-stu-id="1008f-126">If the Expected receipts option is selected for the inventory blocking, as it is by default when you manually create a blocking, this date will appear on the expected transaction.</span></span>  
3. <span data-ttu-id="1008f-127">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="1008f-127">Click Save.</span></span>

## <a name="remove-the-inventory-blocking"></a><span data-ttu-id="1008f-128">Eliminación del bloqueo de inventario</span><span class="sxs-lookup"><span data-stu-id="1008f-128">Remove the inventory blocking</span></span>
1. <span data-ttu-id="1008f-129">Haga clic Eliminar.</span><span class="sxs-lookup"><span data-stu-id="1008f-129">Click Delete.</span></span>
2. <span data-ttu-id="1008f-130">Haga clic en Sí.</span><span class="sxs-lookup"><span data-stu-id="1008f-130">Click Yes.</span></span>
3. <span data-ttu-id="1008f-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1008f-131">Close the page.</span></span>

