---
title: Transferencia del inventario físico en el almacén
description: Este procedimiento le muestra el proceso para crear y enviar un diario de transferencia de inventario para registrar el movimiento de un artículo desde una ubicación de un almacén a otra.
author: MarkusFogelberg
manager: tfehr
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalTransfer, InventJournalCreate, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b745308aca2503b31d7d24d7cac693bb803fc6ab
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5244264"
---
# <a name="transfer-physical-inventory-within-the-warehouse"></a><span data-ttu-id="d0cf0-103">Transferencia del inventario físico en el almacén</span><span class="sxs-lookup"><span data-stu-id="d0cf0-103">Transfer physical inventory within the warehouse</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d0cf0-104">Este procedimiento le muestra el proceso para crear y enviar un diario de transferencia de inventario para registrar el movimiento de un artículo desde una ubicación de un almacén a otra.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-104">This procedure walks you through the process of creating and posting an inventory transfer journal in order to register movement of an item from one location in a warehouse to another.</span></span> <span data-ttu-id="d0cf0-105">Antes de comenzar, necesita tener configurado un nombre de diario de inventario para las transferencias de inventario.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-105">You need to have an inventory journal name set up for inventory transfers before you start this.</span></span> <span data-ttu-id="d0cf0-106">Puede revisar este procedimiento en la empresa de demostración USMF con los valores de ejemplo mostrados o puede usar sus propios datos si tiene productos y ubicaciones configurados.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-106">You can walk through this procedure in demo data company USMF using the example values that are shown, or using you can use your own data if you have products and locations set up.</span></span> <span data-ttu-id="d0cf0-107">Estas tareas las realizará normalmente el empleado del almacén.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-107">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-transfer-journal"></a><span data-ttu-id="d0cf0-108">Creación de un diario de transferencias de inventario</span><span class="sxs-lookup"><span data-stu-id="d0cf0-108">Create an inventory transfer journal</span></span>
1. <span data-ttu-id="d0cf0-109">En el **Panel de exploración**, vaya a **Gestión de inventarios > Movimientos del diario > Artículos > Transferencia**.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-109">In the **Navigation pane**, go to **Inventory management > Journal entries > Items > Transfer**.</span></span>
2. <span data-ttu-id="d0cf0-110">Haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-110">Click **New**.</span></span>
3. <span data-ttu-id="d0cf0-111">En el campo **Nombre**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-111">In the **Name** field, enter or select a value.</span></span>
4. <span data-ttu-id="d0cf0-112">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-112">Click **OK**.</span></span> <span data-ttu-id="d0cf0-113">Existe la opción de especificar las dimensiones "De" y "A" para cada línea de diario.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-113">There is the option to specify 'From' and 'To' dimensions for each journal line.</span></span> <span data-ttu-id="d0cf0-114">Estas son esenciales para este tipo de diario.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-114">These are essential for this journal type.</span></span> <span data-ttu-id="d0cf0-115">Puede transferir los artículos a las ubicaciones mediante distintas reglas.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-115">You can transfer items to locations using different rules.</span></span> <span data-ttu-id="d0cf0-116">En este ejemplo transferiremos un artículo dentro del mismo almacén, de una ubicación controlada mediante matrícula de entidad de almacén a una ubicación que no se controla mediante matrículas de entidad de almacén.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-116">In this example we'll transfer an item within the same warehouse, from a license plate controlled location to a location that is not license plate controlled.</span></span>   

## <a name="create-journal-lines"></a><span data-ttu-id="d0cf0-117">Crear líneas de diario</span><span class="sxs-lookup"><span data-stu-id="d0cf0-117">Create journal lines</span></span>
1. <span data-ttu-id="d0cf0-118">En la **Ficha desplegable Líneas de diario**, haga clic en **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-118">Int the **Journal lines fastTab**, click **New**.</span></span>
2. <span data-ttu-id="d0cf0-119">En el campo **Número de artículo**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-119">In the **Item number** field, enter or select a value.</span></span> <span data-ttu-id="d0cf0-120">Si está usando USMF, puede seleccionar "A0001".</span><span class="sxs-lookup"><span data-stu-id="d0cf0-120">If you are using USMF, you can select 'A0001'.</span></span>  
3. <span data-ttu-id="d0cf0-121">En el campo **Sitio de origen**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-121">In the **From site** field, enter or select a value.</span></span> <span data-ttu-id="d0cf0-122">Si está usando USMF, puede seleccionar "2".</span><span class="sxs-lookup"><span data-stu-id="d0cf0-122">If you are using USMF, you can select '2'.</span></span>  
4. <span data-ttu-id="d0cf0-123">En el campo **Sitio de destino**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-123">In the **To site** field, enter or select a value.</span></span> <span data-ttu-id="d0cf0-124">Si está usando USMF, puede seleccionar "2".</span><span class="sxs-lookup"><span data-stu-id="d0cf0-124">If you are using USMF, you can select '2'.</span></span>  
5. <span data-ttu-id="d0cf0-125">En el campo **Almacén de origen**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-125">In the **From warehouse** field, enter or select a value.</span></span> <span data-ttu-id="d0cf0-126">Si está usando USMF, puede seleccionar "24".</span><span class="sxs-lookup"><span data-stu-id="d0cf0-126">If you are using USMF, you can select '24'.</span></span>  
6. <span data-ttu-id="d0cf0-127">En el campo **Almacén de destino**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-127">In the **To warehouse** field, enter or select a value.</span></span> <span data-ttu-id="d0cf0-128">Si está usando USMF, puede seleccionar "24".</span><span class="sxs-lookup"><span data-stu-id="d0cf0-128">If you are using USMF, you can select '24'.</span></span>  
7. <span data-ttu-id="d0cf0-129">En el campo **Ubicación de origen**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-129">In the **From location** field, enter or select a value.</span></span> <span data-ttu-id="d0cf0-130">Si está usando USMF, puede seleccionar "FL-001".</span><span class="sxs-lookup"><span data-stu-id="d0cf0-130">If you are using USMF, you can select 'FL-001'.</span></span>  
8. <span data-ttu-id="d0cf0-131">En el campo **Ubicación de destino**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-131">In the **To location** field, enter or select a value.</span></span> <span data-ttu-id="d0cf0-132">Si está usando USMF, puede seleccionar "BULK-001".</span><span class="sxs-lookup"><span data-stu-id="d0cf0-132">If you are using USMF, you can select 'BULK-001'.</span></span>  
9. <span data-ttu-id="d0cf0-133">En el campo **Cantidad**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-133">In the **Quantity** field, enter a number.</span></span>
10. <span data-ttu-id="d0cf0-134">En la ficha desplegable **Detalles de línea**, haga clic en la pestaña **Dimensiones de inventario**.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-134">In the **Line details** fastTab, click the **Inventory dimensions** tab.</span></span>
11. <span data-ttu-id="d0cf0-135">En **Desde dimensiones de inventario**, en el campo **Matrícula**, especifique o seleccione un valor.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-135">In **From inventory dimensions**, in the **License plate** field, enter or select a value.</span></span> <span data-ttu-id="d0cf0-136">Si está usando USMF, puede seleccionar "24".</span><span class="sxs-lookup"><span data-stu-id="d0cf0-136">If you are using USMF, you can select '24'.</span></span>  
12. <span data-ttu-id="d0cf0-137">Haga clic en **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-137">Click **Save**.</span></span>

## <a name="post-the-inventory-transfer-journal"></a><span data-ttu-id="d0cf0-138">Registrar el diario de transferencias de inventario</span><span class="sxs-lookup"><span data-stu-id="d0cf0-138">Post the inventory transfer journal</span></span>
1. <span data-ttu-id="d0cf0-139">En el **Panel Acciones**, haga clic en **Publicar**.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-139">On the **Action Pane**, click **Post**.</span></span>
2. <span data-ttu-id="d0cf0-140">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-140">Click **OK**.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="d0cf0-141">Ver transacciones de inventario</span><span class="sxs-lookup"><span data-stu-id="d0cf0-141">View inventory transactions</span></span>
1. <span data-ttu-id="d0cf0-142">Haga clic en **Inventario**.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-142">Click **Inventory**.</span></span>
2. <span data-ttu-id="d0cf0-143">Haga clic en **Transacciones**.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-143">Click **Transactions**.</span></span> <span data-ttu-id="d0cf0-144">Aquí puede ver las transacciones creadas al registrar el diario.</span><span class="sxs-lookup"><span data-stu-id="d0cf0-144">Here you can see the transactions that were created when you posted your journal.</span></span>  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]