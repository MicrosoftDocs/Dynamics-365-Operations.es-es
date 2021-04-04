---
title: Corrección de información de seguimiento de inventario
description: Este procedimiento le muestra el proceso de crear y registrar un diario de transferencia de inventario para corregir la información de seguimiento de inventario.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventBatchIdLookup, InventLocationIdLookup, InventDimTracking, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 76e73f10df5bb520b6d0d787eda08053a5e33c81
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5223419"
---
# <a name="correct-inventory-tracking-information"></a><span data-ttu-id="ebd7e-103">Corrección de información de seguimiento de inventario</span><span class="sxs-lookup"><span data-stu-id="ebd7e-103">Correct inventory tracking information</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ebd7e-104">Este procedimiento le muestra el proceso de crear y registrar un diario de transferencia de inventario para corregir la información de seguimiento de inventario.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to correct inventory tracking information.</span></span> <span data-ttu-id="ebd7e-105">En este ejemplo, actualizaremos la información de un artículo controlado por lote cambiando un lote registrado incorrectamente por otro lote.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-105">In this example, we'll update the information of a batch controlled item by changing an incorrectly registered batch to another batch.</span></span> <span data-ttu-id="ebd7e-106">Puede revisar este procedimiento con los datos de prueba de la empresa USPI o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-106">You can walk through this procedure in demo data company USPI, or using your own data.</span></span> <span data-ttu-id="ebd7e-107">Si utiliza sus propios datos, debe tener un artículo habilitado para lotes y no debe estar controlado por ubicación.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-107">If you use your own data, you need to have an item that's batch-enabled, and it must not be location-controlled.</span></span> <span data-ttu-id="ebd7e-108">También necesita tener configurado un nombre de diario de inventario para las transferencias de inventario.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-108">You also need to have an inventory journal name set up for inventory transfers.</span></span> <span data-ttu-id="ebd7e-109">Estas tareas las realizará normalmente el empleado del almacén.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-109">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="ebd7e-110">Creación de un diario de transferencias de inventario</span><span class="sxs-lookup"><span data-stu-id="ebd7e-110">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="ebd7e-111">Vaya a Transferir.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-111">Go to Transfer.</span></span>
2. <span data-ttu-id="ebd7e-112">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-112">Click New.</span></span>
3. <span data-ttu-id="ebd7e-113">En el campo Nombre, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-113">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="ebd7e-114">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ebd7e-114">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="ebd7e-115">Creación de líneas de diario</span><span class="sxs-lookup"><span data-stu-id="ebd7e-115">Create journal lines</span></span>
1. <span data-ttu-id="ebd7e-116">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-116">Click New.</span></span>
2. <span data-ttu-id="ebd7e-117">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-117">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="ebd7e-118">Si utiliza USPI, seleccione el artículo M5003.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-118">If you are using USPI, select item M5003.</span></span>  
3. <span data-ttu-id="ebd7e-119">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-119">In the Quantity field, enter a number.</span></span>
4. <span data-ttu-id="ebd7e-120">Haga clic en la ficha Dimensiones de inventario.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-120">Click the Inventory dimensions tab.</span></span>
5. <span data-ttu-id="ebd7e-121">En el campo Número de lote, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-121">In the Batch number field, enter or select a value.</span></span>
6. <span data-ttu-id="ebd7e-122">En el campo Sitio, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-122">In the Site field, enter or select a value.</span></span>
7. <span data-ttu-id="ebd7e-123">En el campo Almacén, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-123">In the Warehouse field, enter or select a value.</span></span>
8. <span data-ttu-id="ebd7e-124">En el campo Número de lote, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-124">In the Batch number field, enter or select a value.</span></span>

## <a name="post-the-journal"></a><span data-ttu-id="ebd7e-125">Registrar el diario</span><span class="sxs-lookup"><span data-stu-id="ebd7e-125">Post the journal</span></span>
1. <span data-ttu-id="ebd7e-126">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-126">Click Post.</span></span>
2. <span data-ttu-id="ebd7e-127">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ebd7e-127">Click OK.</span></span>

## <a name="check-tracing-information"></a><span data-ttu-id="ebd7e-128">Comprobar la información de seguimiento</span><span class="sxs-lookup"><span data-stu-id="ebd7e-128">Check tracing information</span></span>
1. <span data-ttu-id="ebd7e-129">Haga clic en Inventario.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-129">Click Inventory.</span></span>
2. <span data-ttu-id="ebd7e-130">Haga clic en Seguimiento.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-130">Click Trace.</span></span>
3. <span data-ttu-id="ebd7e-131">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="ebd7e-131">Click OK.</span></span>
    * <span data-ttu-id="ebd7e-132">Con esta información de seguimiento puede rastrear desde qué lote corrigió el inventario.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-132">Using this tracing information you can back trace which batch you corrected inventory from.</span></span>  <span data-ttu-id="ebd7e-133">También puede usar la página Seguimiento de artículos para ver esta información.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-133">You can also use the Item tracing page to see this information.</span></span>  
4. <span data-ttu-id="ebd7e-134">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-134">Close the page.</span></span>

## <a name="check-inventory-transactions"></a><span data-ttu-id="ebd7e-135">Comprobar las transacciones del inventario</span><span class="sxs-lookup"><span data-stu-id="ebd7e-135">Check inventory transactions</span></span>
1. <span data-ttu-id="ebd7e-136">Haga clic en Inventario.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-136">Click Inventory.</span></span>
2. <span data-ttu-id="ebd7e-137">Haga clic en Transacciones.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-137">Click Transactions.</span></span>
    * <span data-ttu-id="ebd7e-138">Aquí puede ver las transacciones creadas al registrar el diario.</span><span class="sxs-lookup"><span data-stu-id="ebd7e-138">Here you can see the transactions that were created when you posted your journal.</span></span>   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]