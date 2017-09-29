---
title: "Transferencia del inventario físico en el almacén"
description: "Este procedimiento le muestra el proceso para crear y enviar un diario de transferencia de inventario para registrar el movimiento de un artículo desde una ubicación de un almacén a otra."
author: MarkusFogelberg
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: bfba69731a4897906d08ff9fb9ce69e79121efeb
ms.contentlocale: es-es
ms.lasthandoff: 09/12/2017

---
# <a name="transfer-physical-inventory-within-the-warehouse"></a><span data-ttu-id="efcfd-103">Transferencia del inventario físico en el almacén</span><span class="sxs-lookup"><span data-stu-id="efcfd-103">Transfer physical inventory within the warehouse</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="efcfd-104">Este procedimiento le muestra el proceso para crear y enviar un diario de transferencia de inventario para registrar el movimiento de un artículo desde una ubicación de un almacén a otra.</span><span class="sxs-lookup"><span data-stu-id="efcfd-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to register movement of an item from one location in a warehouse to another.</span></span> <span data-ttu-id="efcfd-105">Antes de comenzar, necesita tener configurado un nombre de diario de inventario para las transferencias de inventario.</span><span class="sxs-lookup"><span data-stu-id="efcfd-105">You need to have an inventory journal name set up for inventory transfers before you start this.</span></span> <span data-ttu-id="efcfd-106">Puede revisar este procedimiento en la empresa de demostración USMF con los valores de ejemplo mostrados o puede usar sus propios datos si tiene productos y ubicaciones configurados.</span><span class="sxs-lookup"><span data-stu-id="efcfd-106">You can walk through this procedure in demo data company USMF using the example values that are shown, or using you can use your own data if you have products and locations set up.</span></span> <span data-ttu-id="efcfd-107">Estas tareas las realizará normalmente el empleado del almacén.</span><span class="sxs-lookup"><span data-stu-id="efcfd-107">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="efcfd-108">Creación de un diario de transferencias de inventario</span><span class="sxs-lookup"><span data-stu-id="efcfd-108">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="efcfd-109">Vaya a Transferir.</span><span class="sxs-lookup"><span data-stu-id="efcfd-109">Go to Transfer.</span></span>
2. <span data-ttu-id="efcfd-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="efcfd-110">Click New.</span></span>
3. <span data-ttu-id="efcfd-111">En el campo Nombre, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="efcfd-111">In the Name field, enter or select a value.</span></span>
4. <span data-ttu-id="efcfd-112">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="efcfd-112">Click OK.</span></span>
    * <span data-ttu-id="efcfd-113">Existe la opción de especificar las dimensiones "De" y "A" para cada línea de diario.</span><span class="sxs-lookup"><span data-stu-id="efcfd-113">There is the option to specify 'From' and 'To' dimensions for each journal line.</span></span> <span data-ttu-id="efcfd-114">Estas son esenciales para este tipo de diario.</span><span class="sxs-lookup"><span data-stu-id="efcfd-114">These are essential for this journal type.</span></span> <span data-ttu-id="efcfd-115">Puede transferir los artículos a las ubicaciones mediante distintas reglas.</span><span class="sxs-lookup"><span data-stu-id="efcfd-115">You can transfer items to locations using different rules.</span></span> <span data-ttu-id="efcfd-116">En este ejemplo transferiremos un artículo dentro del mismo almacén, de una ubicación controlada mediante matrícula de entidad de almacén a una ubicación que no se controla mediante matrículas de entidad de almacén.</span><span class="sxs-lookup"><span data-stu-id="efcfd-116">In this example we’ll transfer an item within the same warehouse, from a license plate controlled location to a location that is not license plate controlled.</span></span>   

## <a name="create-journal-lines"></a><span data-ttu-id="efcfd-117">Creación de líneas de diario</span><span class="sxs-lookup"><span data-stu-id="efcfd-117">Create journal lines</span></span>
1. <span data-ttu-id="efcfd-118">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="efcfd-118">Click New.</span></span>
2. <span data-ttu-id="efcfd-119">En el campo Número de artículo, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="efcfd-119">In the Item number field, enter or select a value.</span></span>
    * <span data-ttu-id="efcfd-120">Si está usando USMF, puede seleccionar "A0001".</span><span class="sxs-lookup"><span data-stu-id="efcfd-120">If you are using USMF, you can select 'A0001'.</span></span>  
3. <span data-ttu-id="efcfd-121">En el campo Sitio de origen, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="efcfd-121">In the From site field, enter or select a value.</span></span>
    * <span data-ttu-id="efcfd-122">Si está usando USMF, puede seleccionar "2".</span><span class="sxs-lookup"><span data-stu-id="efcfd-122">If you are using USMF, you can select '2'.</span></span>  
4. <span data-ttu-id="efcfd-123">En el campo Sitio de destino, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="efcfd-123">In the To site field, enter or select a value.</span></span>
    * <span data-ttu-id="efcfd-124">Si está usando USMF, puede seleccionar "2".</span><span class="sxs-lookup"><span data-stu-id="efcfd-124">If you are using USMF, you can select '2'.</span></span>  
5. <span data-ttu-id="efcfd-125">En el campo Desde almacén, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="efcfd-125">In the From warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="efcfd-126">Si está usando USMF, puede seleccionar "24".</span><span class="sxs-lookup"><span data-stu-id="efcfd-126">If you are using USMF, you can select '24'.</span></span>  
6. <span data-ttu-id="efcfd-127">En el campo Hasta almacén, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="efcfd-127">In the To warehouse field, enter or select a value.</span></span>
    * <span data-ttu-id="efcfd-128">Si está usando USMF, puede seleccionar "24".</span><span class="sxs-lookup"><span data-stu-id="efcfd-128">If you are using USMF, you can select '24'.</span></span>  
7. <span data-ttu-id="efcfd-129">En el campo Desde ubicación, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="efcfd-129">In the From location field, enter or select a value.</span></span>
    * <span data-ttu-id="efcfd-130">Si está usando USMF, puede seleccionar "FL-001".</span><span class="sxs-lookup"><span data-stu-id="efcfd-130">If you are using USMF, you can select 'FL-001'.</span></span>  
8. <span data-ttu-id="efcfd-131">En el campo Ubicación de destino, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="efcfd-131">In the To location field, enter or select a value.</span></span>
    * <span data-ttu-id="efcfd-132">Si está usando USMF, puede seleccionar "BULK-001".</span><span class="sxs-lookup"><span data-stu-id="efcfd-132">If you are using USMF, you can select 'BULK-001'.</span></span>  
9. <span data-ttu-id="efcfd-133">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="efcfd-133">In the Quantity field, enter a number.</span></span>
10. <span data-ttu-id="efcfd-134">Haga clic en la ficha Dimensiones de inventario.</span><span class="sxs-lookup"><span data-stu-id="efcfd-134">Click the Inventory dimensions tab.</span></span>
11. <span data-ttu-id="efcfd-135">En el campo Número de licencia, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="efcfd-135">In the License plate field, enter or select a value.</span></span>
    * <span data-ttu-id="efcfd-136">Si está usando USMF, puede seleccionar "24".</span><span class="sxs-lookup"><span data-stu-id="efcfd-136">If you are using USMF, you can select '24'.</span></span>  
12. <span data-ttu-id="efcfd-137">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="efcfd-137">Click Save.</span></span>

## <a name="post-the-inventory-transfer-journal"></a><span data-ttu-id="efcfd-138">Registrar el diario de transferencias de inventario</span><span class="sxs-lookup"><span data-stu-id="efcfd-138">Post the inventory transfer journal</span></span>
1. <span data-ttu-id="efcfd-139">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="efcfd-139">Click Post.</span></span>
2. <span data-ttu-id="efcfd-140">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="efcfd-140">Click OK.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="efcfd-141">Ver transacciones de inventario</span><span class="sxs-lookup"><span data-stu-id="efcfd-141">View inventory transactions</span></span>
1. <span data-ttu-id="efcfd-142">Haga clic en Inventario.</span><span class="sxs-lookup"><span data-stu-id="efcfd-142">Click Inventory.</span></span>
2. <span data-ttu-id="efcfd-143">Haga clic en Transacciones.</span><span class="sxs-lookup"><span data-stu-id="efcfd-143">Click Transactions.</span></span>
    * <span data-ttu-id="efcfd-144">Aquí puede ver las transacciones creadas al registrar el diario.</span><span class="sxs-lookup"><span data-stu-id="efcfd-144">Here you can see the transactions that were created when you posted your journal.</span></span>  

