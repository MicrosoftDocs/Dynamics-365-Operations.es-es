---
title: "Recuento de inventario en un almacén"
description: "Este procedimiento muestra el proceso para crear y registrar un diario de recuento de inventario para contar un artículo específico en una ubicación del almacén."
author: MarkusFogelberg
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 5099e82aa3f0408cbfbf816a69c38c5d48989dd2
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---
# <a name="count-inventory-in-a-warehouse"></a><span data-ttu-id="b3d88-103">Recuento de inventario en un almacén</span><span class="sxs-lookup"><span data-stu-id="b3d88-103">Count inventory in a warehouse</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b3d88-104">Este procedimiento muestra el proceso para crear y registrar un diario de recuento de inventario para contar un artículo específico en una ubicación del almacén.</span><span class="sxs-lookup"><span data-stu-id="b3d88-104">This procedure walks you through the process of creating and posting an inventory counting journal in order to count a specific item at a location in the warehouse.</span></span> <span data-ttu-id="b3d88-105">El procedimiento se aplica a la funcionalidad de “almacenamiento básico”, disponible en el módulo Gestión del inventario, no en la funcionalidad de almacenamiento que está disponible en el módulo Gestión de almacenes.</span><span class="sxs-lookup"><span data-stu-id="b3d88-105">The procedure applies to “basic warehousing” functionality, available in the Inventory management module, not to the warehousing functionality that’s available in the Warehouse management module.</span></span> <span data-ttu-id="b3d88-106">Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="b3d88-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="b3d88-107">Si usa sus propios datos, asegúrese de que tiene los productos y las ubicaciones configurados, y de que ha creado un nombre de diario de inventario para contar los diarios.</span><span class="sxs-lookup"><span data-stu-id="b3d88-107">If you’re using your own data, make sure that you have products and locations set up, and that you’ve created an inventory journal name for counting journals.</span></span> <span data-ttu-id="b3d88-108">El recuento de inventario lo lleva a cabo normalmente un empleado de almacén.</span><span class="sxs-lookup"><span data-stu-id="b3d88-108">Inventory counting is normally carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-counting-journal"></a><span data-ttu-id="b3d88-109">Crear un diario de recuento de inventario</span><span class="sxs-lookup"><span data-stu-id="b3d88-109">Create an inventory counting journal</span></span>
1. <span data-ttu-id="b3d88-110">Vaya a Gestión del inventario > Movimientos de diario > Recuento de artículos > Recuento.</span><span class="sxs-lookup"><span data-stu-id="b3d88-110">Go to Inventory management > Journal entries > Item counting > Counting.</span></span>
2. <span data-ttu-id="b3d88-111">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="b3d88-111">Click New.</span></span>
3. <span data-ttu-id="b3d88-112">En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b3d88-112">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="b3d88-113">En la lista, haga clic en el nombre de diario de recuento de inventario que desea usar.</span><span class="sxs-lookup"><span data-stu-id="b3d88-113">In the list, click on the inventory counting journal name you want to use</span></span>
    * <span data-ttu-id="b3d88-114">Algunos otros campos se rellenarán según la configuración del nombre de diario de recuento de inventario que seleccione.</span><span class="sxs-lookup"><span data-stu-id="b3d88-114">Some other fields will be populated based on the setup of the inventory counting journal name that you select.</span></span>  
5. <span data-ttu-id="b3d88-115">En el campo Trabajador, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b3d88-115">In the Worker field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="b3d88-116">En la lista, seleccione el trabajador que desee usar.</span><span class="sxs-lookup"><span data-stu-id="b3d88-116">In the list, select the worker you want to use.</span></span>
7. <span data-ttu-id="b3d88-117">Haga clic en Seleccionar.</span><span class="sxs-lookup"><span data-stu-id="b3d88-117">Click Select.</span></span>
8. <span data-ttu-id="b3d88-118">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="b3d88-118">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="b3d88-119">Creación de líneas de diario</span><span class="sxs-lookup"><span data-stu-id="b3d88-119">Create journal lines</span></span>
1. <span data-ttu-id="b3d88-120">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="b3d88-120">Click New.</span></span>
2. <span data-ttu-id="b3d88-121">En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b3d88-121">In the Item number field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="b3d88-122">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b3d88-122">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b3d88-123">Si utiliza los datos de la empresa de demostración USMF, seleccione "A0001".</span><span class="sxs-lookup"><span data-stu-id="b3d88-123">If you are using demo data company USMF, select 'A0001'.</span></span>  
4. <span data-ttu-id="b3d88-124">En el campo Sitio, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b3d88-124">In the Site field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="b3d88-125">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b3d88-125">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b3d88-126">Si utiliza los datos de la empresa de demostración USMF, seleccione el sitio "2".</span><span class="sxs-lookup"><span data-stu-id="b3d88-126">If you are using demo data company USMF, select site '2'.</span></span>  
6. <span data-ttu-id="b3d88-127">En el campo Almacén, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b3d88-127">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="b3d88-128">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b3d88-128">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b3d88-129">Si utiliza los datos de la empresa de demostración USMF, seleccione el almacén "24".</span><span class="sxs-lookup"><span data-stu-id="b3d88-129">If you are using demo data company USMF, select warehouse '24'.</span></span>  
8. <span data-ttu-id="b3d88-130">En el campo Ubicación, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="b3d88-130">In the Location field, click the drop-down button to open the lookup.</span></span>
9. <span data-ttu-id="b3d88-131">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="b3d88-131">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="b3d88-132">Si utiliza los datos de la empresa de demostración USMF, seleccione la ubicación "BULK-001".</span><span class="sxs-lookup"><span data-stu-id="b3d88-132">If you are using demo data company USMF, select location 'BULK-001'</span></span>  
10. <span data-ttu-id="b3d88-133">En el campo Contado, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="b3d88-133">In the Counted field, enter a number.</span></span>
    * <span data-ttu-id="b3d88-134">Si especifica un número contado diferente al número mostrado en el campo Disponible, el campo Cantidad se actualiza para mostrar la discrepancia.</span><span class="sxs-lookup"><span data-stu-id="b3d88-134">If you enter a counted number that’s different to the number shown in the On-hand field, the Quantity field is updated to show the discrepancy.</span></span>  
11. <span data-ttu-id="b3d88-135">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="b3d88-135">Click Save.</span></span>

## <a name="post-the-inventory-counting-journal"></a><span data-ttu-id="b3d88-136">Registrar el diario de recuento de inventario</span><span class="sxs-lookup"><span data-stu-id="b3d88-136">Post the inventory counting journal</span></span>
1. <span data-ttu-id="b3d88-137">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="b3d88-137">Click Post.</span></span>
    * <span data-ttu-id="b3d88-138">Cuando registra un diario de recuento de inventario, si el importe contado es diferente del importe que se notifica en el campo Disponible en que se registra una recepción o emisión del inventario, se modifican el nivel y el valor del inventario, y se generan las transacciones contables.</span><span class="sxs-lookup"><span data-stu-id="b3d88-138">When you post an inventory counting journal, if the counted amount differs from amount that’s reported in the On-hand field an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>  
2. <span data-ttu-id="b3d88-139">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="b3d88-139">Click OK.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="b3d88-140">Ver transacciones de inventario</span><span class="sxs-lookup"><span data-stu-id="b3d88-140">View inventory transactions</span></span>
1. <span data-ttu-id="b3d88-141">Haga clic en Inventario.</span><span class="sxs-lookup"><span data-stu-id="b3d88-141">Click Inventory.</span></span>
2. <span data-ttu-id="b3d88-142">Haga clic en Transacciones.</span><span class="sxs-lookup"><span data-stu-id="b3d88-142">Click Transactions.</span></span>
    * <span data-ttu-id="b3d88-143">Aquí puede ver las transacciones relacionadas que se creará al registrar el diario de recuento de inventario.</span><span class="sxs-lookup"><span data-stu-id="b3d88-143">Here you can see any related transactions that will be created when you post your inventory counting journal.</span></span>   

