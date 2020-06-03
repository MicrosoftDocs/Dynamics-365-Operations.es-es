---
title: Creación y mantenimiento de un bloqueo del inventario
description: Este procedimiento muestra cómo impedir que se reserve inventario disponible físico a través de otros documentos de origen de salida mediante el bloqueo de inventario.
author: perlynne
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventBlocking, InventItemIdLookupSimple, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 12c6e047e15aaab157e6de70f4a09f500af2965f
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383467"
---
# <a name="create-and-maintain-an-inventory-blocking"></a><span data-ttu-id="056dc-103">Creación y mantenimiento de un bloqueo del inventario</span><span class="sxs-lookup"><span data-stu-id="056dc-103">Create and maintain an inventory blocking</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="056dc-104">Este procedimiento muestra cómo impedir que se reserve inventario disponible físico a través de otros documentos de origen de salida mediante el bloqueo de inventario.</span><span class="sxs-lookup"><span data-stu-id="056dc-104">This procedure shows how to prevent physical on-hand inventory from being reserved by other outbound source documents by using the inventory blocking.</span></span> <span data-ttu-id="056dc-105">Puede ejecutar el procedimiento en la empresa de datos de demostración USMF con los valores de ejemplo que se muestran.</span><span class="sxs-lookup"><span data-stu-id="056dc-105">You can run the procedure in demo data company USMF using the example values that are shown.</span></span> <span data-ttu-id="056dc-106">Necesita tener un artículo con inventario disponible físico antes de comenzar este procedimiento.</span><span class="sxs-lookup"><span data-stu-id="056dc-106">You need to have an item with physical on-hand inventory available before you start this procedure.</span></span>


## <a name="create-an-inventory-blocking"></a><span data-ttu-id="056dc-107">Creación de un bloqueo de inventario</span><span class="sxs-lookup"><span data-stu-id="056dc-107">Create an inventory blocking</span></span>
1. <span data-ttu-id="056dc-108">En el **Panel de exploración**, vaya a **Módulos > Gestión de inventario > Tareas periódicas > Bloqueo del inventario**.</span><span class="sxs-lookup"><span data-stu-id="056dc-108">In the **Navigation pane**, go to **Modules > Inventory management > Periodic tasks > Inventory blocking**.</span></span>
2. <span data-ttu-id="056dc-109">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="056dc-109">Click **New**.</span></span>
3. <span data-ttu-id="056dc-110">En el campo **Código de artículo**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="056dc-110">In the **Item number** field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="056dc-111">En la lista, seleccione el artículo que desee elegir.</span><span class="sxs-lookup"><span data-stu-id="056dc-111">In the list, select the item you want to choose.</span></span> <span data-ttu-id="056dc-112">Seleccione un número de artículo con inventario disponible físico que desee bloquear.</span><span class="sxs-lookup"><span data-stu-id="056dc-112">Select an item number with physical on-hand inventory that you want to block.</span></span> <span data-ttu-id="056dc-113">Si está usando USMF, puede seleccionar el artículo M9201.</span><span class="sxs-lookup"><span data-stu-id="056dc-113">If you're using USMF you can select item M9201.</span></span>  
5. <span data-ttu-id="056dc-114">En el campo **Cantidad**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="056dc-114">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="056dc-115">Si está usando el artículo M9201, es necesario seleccionar un valor inferior a 200.</span><span class="sxs-lookup"><span data-stu-id="056dc-115">If you're using item M9201, you need to select less than 200.</span></span>
6. <span data-ttu-id="056dc-116">Expanda la ficha desplegable **Dimensiones de inventario**.</span><span class="sxs-lookup"><span data-stu-id="056dc-116">Expand the **Inventory dimensions** fastTab.</span></span>
7. <span data-ttu-id="056dc-117">En el campo **Almacén**, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="056dc-117">In the **Warehouse** field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="056dc-118">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="056dc-118">In the list, find and select the desired record.</span></span> <span data-ttu-id="056dc-119">Si está usando el artículo M9201, puede seleccionar el almacén 51.</span><span class="sxs-lookup"><span data-stu-id="056dc-119">If you're using item M9201, you can select warehouse 51.</span></span>  
9. <span data-ttu-id="056dc-120">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="056dc-120">Click **Save**.</span></span>

## <a name="update-the-conditions-of-the-inventory-blocking"></a><span data-ttu-id="056dc-121">Actualización de las condiciones de bloqueo de inventario</span><span class="sxs-lookup"><span data-stu-id="056dc-121">Update the conditions of the inventory blocking</span></span>
1. <span data-ttu-id="056dc-122">En la ficha desplegable **General**, en el campo **Cantidad**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="056dc-122">In the **General** fastTab, in the **Quantity** field, enter a number.</span></span> <span data-ttu-id="056dc-123">Actualice el campo de cantidad de inventario para reflejar la cantidad que bloquear.</span><span class="sxs-lookup"><span data-stu-id="056dc-123">Update the inventory quantity field to reflect the quantity to block.</span></span>  
2. <span data-ttu-id="056dc-124">En el campo **Fecha prevista**, especifique una fecha.</span><span class="sxs-lookup"><span data-stu-id="056dc-124">In the **Expected date** field, enter a date.</span></span> <span data-ttu-id="056dc-125">Es posible que desee indicar cuándo se espera que el inventario bloqueado quede disponible para reserva asignando una fecha prevista.</span><span class="sxs-lookup"><span data-stu-id="056dc-125">You might want to indicate when the blocked inventory is expected to become available for reservation by assigning an expected date.</span></span> <span data-ttu-id="056dc-126">Si la opción Recepciones previstas está seleccionada para el bloqueo de inventario, como lo está de manera predeterminada cuando se crea manualmente un bloqueo, esta fecha aparecerá en la transacción prevista.</span><span class="sxs-lookup"><span data-stu-id="056dc-126">If the Expected receipts option is selected for the inventory blocking, as it is by default when you manually create a blocking, this date will appear on the expected transaction.</span></span>  
3. <span data-ttu-id="056dc-127">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="056dc-127">Click **Save**.</span></span>

## <a name="remove-the-inventory-blocking"></a><span data-ttu-id="056dc-128">Eliminación del bloqueo de inventario</span><span class="sxs-lookup"><span data-stu-id="056dc-128">Remove the inventory blocking</span></span>
1. <span data-ttu-id="056dc-129">En el **Panel Acciones**, haga clic en **Eliminar**.</span><span class="sxs-lookup"><span data-stu-id="056dc-129">On the **Action Pane**, click **Delete**.</span></span>
2. <span data-ttu-id="056dc-130">Haga clic en **Sí**.</span><span class="sxs-lookup"><span data-stu-id="056dc-130">Click **Yes**.</span></span>
3. <span data-ttu-id="056dc-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="056dc-131">Close the page.</span></span>

