---
title: Recuento de inventario en un almacén
description: En este tema se describe el proceso para crear y registrar un diario de recuento de inventario para contar un artículo específico en una ubicación del almacén.
author: MarkusFogelberg
ms.date: 07/09/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalCount, InventJournalCreate, HcmWorkerLookUp, InventItemIdLookupSimple, InventLocationIdLookup, WMSLocationIdLookup, InventTrans
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 24b8bc2daff2d7df6279c76f4d9a0e83244c7988
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834058"
---
# <a name="count-inventory-in-a-warehouse"></a><span data-ttu-id="fcf08-103">Recuento de inventario en un almacén</span><span class="sxs-lookup"><span data-stu-id="fcf08-103">Count inventory in a warehouse</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="fcf08-104">En este tema se describe el proceso para crear y registrar un diario de recuento de inventario para contar un artículo específico en una ubicación del almacén.</span><span class="sxs-lookup"><span data-stu-id="fcf08-104">This topic describes the process of creating and posting an inventory counting journal in order to count a specific item at a location in the warehouse.</span></span> <span data-ttu-id="fcf08-105">El procedimiento se aplica a la funcionalidad de “almacenamiento básico”, disponible en el módulo Gestión del inventario, no en la funcionalidad de almacenamiento que está disponible en el módulo Gestión de almacenes.</span><span class="sxs-lookup"><span data-stu-id="fcf08-105">The procedure applies to "basic warehousing" functionality, available in the Inventory management module, not to the warehousing functionality that's available in the Warehouse management module.</span></span> <span data-ttu-id="fcf08-106">Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="fcf08-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="fcf08-107">Si usa sus propios datos, asegúrese de que tiene los productos y las ubicaciones configurados, y de que ha creado un nombre de diario de inventario para contar los diarios.</span><span class="sxs-lookup"><span data-stu-id="fcf08-107">If you're using your own data, make sure that you have products and locations set up, and that you've created an inventory journal name for counting journals.</span></span> <span data-ttu-id="fcf08-108">El recuento de inventario lo lleva a cabo normalmente un empleado de almacén.</span><span class="sxs-lookup"><span data-stu-id="fcf08-108">Inventory counting is normally carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-counting-journal"></a><span data-ttu-id="fcf08-109">Crear un diario de recuento de inventario</span><span class="sxs-lookup"><span data-stu-id="fcf08-109">Create an inventory counting journal</span></span>
1. <span data-ttu-id="fcf08-110">Vaya a **Panel de exploración > Módulos > Gestión del inventario > Movimientos de diario > Recuento de artículos > Recuento**.</span><span class="sxs-lookup"><span data-stu-id="fcf08-110">Go to **Navigation pane > Modules > Inventory management > Journal entries > Item counting > Counting**.</span></span>
2. <span data-ttu-id="fcf08-111">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="fcf08-111">Select **New**.</span></span>
3. <span data-ttu-id="fcf08-112">En el campo **Nombre**, seleccione en la lista desplegable el nombre del diario de recuento de inventario que desea usar.</span><span class="sxs-lookup"><span data-stu-id="fcf08-112">In the **Name** field, select the inventory counting journal name you want to use from the drop-down list.</span></span> <span data-ttu-id="fcf08-113">Algunos otros campos se rellenarán según la configuración del nombre de diario de recuento de inventario que seleccione.</span><span class="sxs-lookup"><span data-stu-id="fcf08-113">Some other fields will be populated based on the setup of the inventory counting journal name that you select.</span></span>  
4. <span data-ttu-id="fcf08-114">En el campo **Trabajador**, seleccione el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="fcf08-114">In the **Worker** field, select the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="fcf08-115">En la lista, haga clic en **Seleccionar** para seleccionar el trabajador que desea usar.</span><span class="sxs-lookup"><span data-stu-id="fcf08-115">In the list, **Select** the worker you want to use.</span></span>
6. <span data-ttu-id="fcf08-116">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fcf08-116">Select **OK**.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="fcf08-117">Crear líneas de diario</span><span class="sxs-lookup"><span data-stu-id="fcf08-117">Create journal lines</span></span>
1. <span data-ttu-id="fcf08-118">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="fcf08-118">Select **New**.</span></span>
2. <span data-ttu-id="fcf08-119">En el campo **Código de artículo**, seleccione en la lista desplegable el registro que desea.</span><span class="sxs-lookup"><span data-stu-id="fcf08-119">In the **Item number** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="fcf08-120">Si va a utilizar los datos de demostración de la empresa USMF, seleccione **A0001**.</span><span class="sxs-lookup"><span data-stu-id="fcf08-120">If you are using demo data company USMF, select **A0001**.</span></span>  
3. <span data-ttu-id="fcf08-121">En el campo **Sitio**, seleccione en la lista desplegable el registro que desea.</span><span class="sxs-lookup"><span data-stu-id="fcf08-121">In the **Site** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="fcf08-122">Si utiliza los datos de la empresa de demostración USMF, seleccione el sitio **2**.</span><span class="sxs-lookup"><span data-stu-id="fcf08-122">If you are using demo data company USMF, select site **2**.</span></span>
4. <span data-ttu-id="fcf08-123">En el campo **Almacén**, seleccione en la lista desplegable el registro que desea.</span><span class="sxs-lookup"><span data-stu-id="fcf08-123">In the **Warehouse** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="fcf08-124">Si utiliza los datos de demostración de la empresa USMF, seleccione el almacén **24**.</span><span class="sxs-lookup"><span data-stu-id="fcf08-124">If you are using demo data company USMF, select warehouse **24**.</span></span>  
5. <span data-ttu-id="fcf08-125">En el campo **Ubicación**, seleccione en la lista desplegable el registro que desea.</span><span class="sxs-lookup"><span data-stu-id="fcf08-125">In the **Location** field, select the desired record from the drop-down list.</span></span> <span data-ttu-id="fcf08-126">Si utiliza los datos de demostración de la empresa USMF, seleccione la ubicación **BULK-001**.</span><span class="sxs-lookup"><span data-stu-id="fcf08-126">If you are using demo data company USMF, select location **BULK-001**.</span></span>  
6. <span data-ttu-id="fcf08-127">En el campo Contado, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="fcf08-127">In the Counted field, enter a number.</span></span> <span data-ttu-id="fcf08-128">Si especifica un número contado diferente al número mostrado en el campo **Disponible**, el campo **Cantidad** se actualiza para mostrar la discrepancia.</span><span class="sxs-lookup"><span data-stu-id="fcf08-128">If you enter a counted number that's different to the number shown in the **On-hand** field, the **Quantity** field is updated to show the discrepancy.</span></span>  
7. <span data-ttu-id="fcf08-129">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="fcf08-129">Select **Save**.</span></span>

## <a name="post-the-inventory-counting-journal"></a><span data-ttu-id="fcf08-130">Registrar el diario de recuento de inventario</span><span class="sxs-lookup"><span data-stu-id="fcf08-130">Post the inventory counting journal</span></span>
1. <span data-ttu-id="fcf08-131">Seleccione **Registrar**.</span><span class="sxs-lookup"><span data-stu-id="fcf08-131">Select **Post**.</span></span> <span data-ttu-id="fcf08-132">Cuando registra un diario de recuento de inventario, si el importe contado es diferente del importe que se notifica en el campo **Disponible** en que se registra una recepción o emisión del inventario, se modifican el nivel y el valor del inventario, y se generan las transacciones contables.</span><span class="sxs-lookup"><span data-stu-id="fcf08-132">When you post an inventory counting journal, if the counted amount differs from amount that's reported in the **On-hand** field an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>
2. <span data-ttu-id="fcf08-133">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="fcf08-133">Select **OK**.</span></span>

## <a name="view-inventory-transactions"></a><span data-ttu-id="fcf08-134">Ver transacciones de inventario</span><span class="sxs-lookup"><span data-stu-id="fcf08-134">View inventory transactions</span></span>
1. <span data-ttu-id="fcf08-135">Seleccione **Inventario**.</span><span class="sxs-lookup"><span data-stu-id="fcf08-135">Select **Inventory**.</span></span>
2. <span data-ttu-id="fcf08-136">Seleccione **Transacciones**.</span><span class="sxs-lookup"><span data-stu-id="fcf08-136">Select **Transactions**.</span></span> <span data-ttu-id="fcf08-137">Aquí puede ver las transacciones relacionadas que se creará al registrar el diario de recuento de inventario.</span><span class="sxs-lookup"><span data-stu-id="fcf08-137">Here you can see any related transactions that will be created when you post your inventory counting journal.</span></span>   



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]