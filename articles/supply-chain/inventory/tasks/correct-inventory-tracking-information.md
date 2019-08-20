---
title: Corrección de información de seguimiento de inventario
description: Este procedimiento le muestra el proceso de crear y registrar un diario de transferencia de inventario para corregir la información de seguimiento de inventario.
author: MarkusFogelberg
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventBatchIdLookup, InventLocationIdLookup, InventDimTracking, InventTrans
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8269e5119e45522373eca6cb8fb06bfb94a37566
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845579"
---
# <a name="correct-inventory-tracking-information"></a><span data-ttu-id="0c999-103">Corrección de información de seguimiento de inventario</span><span class="sxs-lookup"><span data-stu-id="0c999-103">Correct inventory tracking information</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0c999-104">Este procedimiento le muestra el proceso de crear y registrar un diario de transferencia de inventario para corregir la información de seguimiento de inventario.</span><span class="sxs-lookup"><span data-stu-id="0c999-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to correct inventory tracking information.</span></span> <span data-ttu-id="0c999-105">En este ejemplo, actualizaremos la información de un artículo controlado por lote cambiando un lote registrado incorrectamente por otro lote.</span><span class="sxs-lookup"><span data-stu-id="0c999-105">In this example, we’ll update the information of a batch controlled item by changing an incorrectly registered batch to another batch.</span></span> <span data-ttu-id="0c999-106">Puede revisar este procedimiento con los datos de prueba de la empresa USPI o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="0c999-106">You can walk through this procedure in demo data company USPI, or using your own data.</span></span> <span data-ttu-id="0c999-107">Si utiliza sus propios datos, debe tener un artículo habilitado para lotes y no debe estar controlado por ubicación.</span><span class="sxs-lookup"><span data-stu-id="0c999-107">If you use your own data, you need to have an item that’s batch-enabled, and it must not be location-controlled.</span></span> <span data-ttu-id="0c999-108">También necesita tener configurado un nombre de diario de inventario para las transferencias de inventario.</span><span class="sxs-lookup"><span data-stu-id="0c999-108">You also need to have an inventory journal name set up for inventory transfers.</span></span> <span data-ttu-id="0c999-109">Estas tareas las realizará normalmente el empleado del almacén.</span><span class="sxs-lookup"><span data-stu-id="0c999-109">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="0c999-110">Creación de un diario de transferencias de inventario</span><span class="sxs-lookup"><span data-stu-id="0c999-110">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="0c999-111">Vaya a Transferir.</span><span class="sxs-lookup"><span data-stu-id="0c999-111">Go to Transfer.</span></span>
2. <span data-ttu-id="0c999-112">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="0c999-112">Click New.</span></span>
3. <span data-ttu-id="0c999-113">En el campo Nombre, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0c999-113">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="0c999-114">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="0c999-114">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="0c999-115">Creación de líneas de diario</span><span class="sxs-lookup"><span data-stu-id="0c999-115">Create journal lines</span></span>
1. <span data-ttu-id="0c999-116">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="0c999-116">Click New.</span></span>
2. <span data-ttu-id="0c999-117">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0c999-117">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="0c999-118">Si utiliza USPI, seleccione el artículo M5003.</span><span class="sxs-lookup"><span data-stu-id="0c999-118">If you are using USPI, select item M5003.</span></span>  
3. <span data-ttu-id="0c999-119">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="0c999-119">In the Quantity field, enter a number.</span></span>
4. <span data-ttu-id="0c999-120">Haga clic en la ficha Dimensiones de inventario.</span><span class="sxs-lookup"><span data-stu-id="0c999-120">Click the Inventory dimensions tab.</span></span>
5. <span data-ttu-id="0c999-121">En el campo Número de lote, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0c999-121">In the Batch number field, enter or select a value.</span></span>
6. <span data-ttu-id="0c999-122">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0c999-122">In the Site field, enter or select a value.</span></span>
7. <span data-ttu-id="0c999-123">En el campo Almacén, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0c999-123">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="0c999-124">En el campo Número de lote, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="0c999-124">In the Batch number field, enter or select a value.</span></span>

## <a name="post-the-journal"></a><span data-ttu-id="0c999-125">Registrar el diario</span><span class="sxs-lookup"><span data-stu-id="0c999-125">Post the journal</span></span>
1. <span data-ttu-id="0c999-126">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="0c999-126">Click Post.</span></span>
2. <span data-ttu-id="0c999-127">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="0c999-127">Click OK.</span></span>

## <a name="check-tracing-information"></a><span data-ttu-id="0c999-128">Comprobar la información de seguimiento</span><span class="sxs-lookup"><span data-stu-id="0c999-128">Check tracing information</span></span>
1. <span data-ttu-id="0c999-129">Haga clic en Inventario.</span><span class="sxs-lookup"><span data-stu-id="0c999-129">Click Inventory.</span></span>
2. <span data-ttu-id="0c999-130">Haga clic en Seguimiento.</span><span class="sxs-lookup"><span data-stu-id="0c999-130">Click Trace.</span></span>
3. <span data-ttu-id="0c999-131">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="0c999-131">Click OK.</span></span>
    * <span data-ttu-id="0c999-132">Con esta información de seguimiento puede rastrear desde qué lote corrigió el inventario.</span><span class="sxs-lookup"><span data-stu-id="0c999-132">Using this tracing information you can back trace which batch you corrected inventory from.</span></span>  <span data-ttu-id="0c999-133">También puede usar la página Seguimiento de artículos para ver esta información.</span><span class="sxs-lookup"><span data-stu-id="0c999-133">You can also use the Item tracing page to see this information.</span></span>  
4. <span data-ttu-id="0c999-134">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="0c999-134">Close the page.</span></span>

## <a name="check-inventory-transactions"></a><span data-ttu-id="0c999-135">Comprobar las transacciones del inventario</span><span class="sxs-lookup"><span data-stu-id="0c999-135">Check inventory transactions</span></span>
1. <span data-ttu-id="0c999-136">Haga clic en Inventario.</span><span class="sxs-lookup"><span data-stu-id="0c999-136">Click Inventory.</span></span>
2. <span data-ttu-id="0c999-137">Haga clic en Transacciones.</span><span class="sxs-lookup"><span data-stu-id="0c999-137">Click Transactions.</span></span>
    * <span data-ttu-id="0c999-138">Aquí puede ver las transacciones creadas al registrar el diario.</span><span class="sxs-lookup"><span data-stu-id="0c999-138">Here you can see the transactions that were created when you posted your journal.</span></span>   

