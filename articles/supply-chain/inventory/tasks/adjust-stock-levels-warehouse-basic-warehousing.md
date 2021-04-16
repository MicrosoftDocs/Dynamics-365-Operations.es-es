---
title: Ajuste de niveles de existencias en el almacén (almacenaje básico)
description: Este procedimiento muestra el proceso para crear y registrar un diario de ajuste de inventario para ajustar niveles de existencias de productos en el almacén.
author: MarkusFogelberg
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventJournalCreate, InventLocationIdLookup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0bba1df70cd23a29ddffad96a4a581154619dc74
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834154"
---
# <a name="adjust-stock-levels-in-the-warehouse-basic-warehousing"></a><span data-ttu-id="1756a-103">Ajuste de niveles de existencias en el almacén (almacenaje básico)</span><span class="sxs-lookup"><span data-stu-id="1756a-103">Adjust stock levels in the warehouse (basic warehousing)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1756a-104">Este procedimiento muestra el proceso para crear y registrar un diario de ajuste de inventario para ajustar niveles de existencias de productos en el almacén.</span><span class="sxs-lookup"><span data-stu-id="1756a-104">This procedure walks you through the process of creating and posting an inventory adjustment journal in order to adjust stock levels of products in the warehouse.</span></span> <span data-ttu-id="1756a-105">Antes de comenzar, necesita tener configurado un nombre de diario de inventario para los ajustes de inventario.</span><span class="sxs-lookup"><span data-stu-id="1756a-105">You need to have an inventory journal name set up for inventory adjustments before you start this.</span></span> <span data-ttu-id="1756a-106">Puede revisar este procedimiento con los datos de prueba de la empresa USMF o utilizar sus propios datos.</span><span class="sxs-lookup"><span data-stu-id="1756a-106">You can walk through this procedure in demo data company USMF, or using your own data.</span></span> <span data-ttu-id="1756a-107">Estas tareas las realizará normalmente el empleado del almacén.</span><span class="sxs-lookup"><span data-stu-id="1756a-107">These tasks would normally be carried out by a warehouse employee.</span></span>


## <a name="create-an-inventory-adjustment-journal"></a><span data-ttu-id="1756a-108">Creación de un diario de ajuste de inventario</span><span class="sxs-lookup"><span data-stu-id="1756a-108">Create an inventory adjustment journal</span></span>
1. <span data-ttu-id="1756a-109">Vaya a Gestión del inventario > Movimientos de diario > Artículos > Ajuste de inventario.</span><span class="sxs-lookup"><span data-stu-id="1756a-109">Go to Inventory management > Journal entries > Items > Inventory adjustment.</span></span>
2. <span data-ttu-id="1756a-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="1756a-110">Click New.</span></span>
3. <span data-ttu-id="1756a-111">En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1756a-111">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="1756a-112">En la lista, haga clic en el nombre del diario de ajuste de inventario que desea usar.</span><span class="sxs-lookup"><span data-stu-id="1756a-112">In the list, click on the inventory adjustment journal name you want to use.</span></span>
    * <span data-ttu-id="1756a-113">Algunos otros campos se rellenarán según la configuración del nombre de diario de ajuste de inventario que seleccione.</span><span class="sxs-lookup"><span data-stu-id="1756a-113">Some other fields will be populated based on the setup of the inventory adjustment journal name you select.</span></span>  
5. <span data-ttu-id="1756a-114">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="1756a-114">Click OK.</span></span>

## <a name="create-journal-lines"></a><span data-ttu-id="1756a-115">Creación de líneas de diario</span><span class="sxs-lookup"><span data-stu-id="1756a-115">Create journal lines</span></span>
1. <span data-ttu-id="1756a-116">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="1756a-116">Click New.</span></span>
2. <span data-ttu-id="1756a-117">En la lista, marque el campo con el número de artículo.</span><span class="sxs-lookup"><span data-stu-id="1756a-117">In the list, mark the item number field.</span></span>
3. <span data-ttu-id="1756a-118">En el campo Número de artículo, seleccione un artículo.</span><span class="sxs-lookup"><span data-stu-id="1756a-118">In the Item number field, Select an item.</span></span> <span data-ttu-id="1756a-119">Si utiliza los datos de la empresa de demostración USMF, escriba "D0001".</span><span class="sxs-lookup"><span data-stu-id="1756a-119">If you are using demo data company USMF, type 'D0001'.</span></span>
4. <span data-ttu-id="1756a-120">En el campo Sitio, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1756a-120">In the Site field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="1756a-121">Seleccione un sitio en la lista.</span><span class="sxs-lookup"><span data-stu-id="1756a-121">In the list, select a site.</span></span>
6. <span data-ttu-id="1756a-122">En el campo Almacén, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="1756a-122">In the Warehouse field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="1756a-123">Seleccione un almacén en la lista.</span><span class="sxs-lookup"><span data-stu-id="1756a-123">In the list, select a warehouse.</span></span>
    * <span data-ttu-id="1756a-124">Si ha seleccionado un artículo con Ubicación como dimensión obligatoria, tendrá que especificar la ubicación aquí.</span><span class="sxs-lookup"><span data-stu-id="1756a-124">If you have selected an item with Location as a mandatory dimension, you would have to specify the location here.</span></span>  
8. <span data-ttu-id="1756a-125">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="1756a-125">In the Quantity field, enter a number.</span></span>
    * <span data-ttu-id="1756a-126">El campo de precio de coste especifica el coste por unidad para recepciones de inventario.</span><span class="sxs-lookup"><span data-stu-id="1756a-126">The cost price field specifies the cost per unit for inventory receipts.</span></span> <span data-ttu-id="1756a-127">Si no se especifica el coste del número de artículo, o si deseara cambiarlo manualmente, lo haría aquí.</span><span class="sxs-lookup"><span data-stu-id="1756a-127">If the cost is not specified for the item number or if you wanted to change it manually, you would do this here.</span></span>  

## <a name="validate-and-post-the-inventory-adjustment-journal"></a><span data-ttu-id="1756a-128">Validación y registro del diario de ajuste de inventario</span><span class="sxs-lookup"><span data-stu-id="1756a-128">Validate and post the inventory adjustment journal</span></span>
1. <span data-ttu-id="1756a-129">Haga clic en Validar.</span><span class="sxs-lookup"><span data-stu-id="1756a-129">Click Validate.</span></span>
2. <span data-ttu-id="1756a-130">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="1756a-130">Click OK.</span></span>
3. <span data-ttu-id="1756a-131">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="1756a-131">Click Post.</span></span>
    * <span data-ttu-id="1756a-132">Al registrar este tipo de diario, se registra una recepción o emisión del inventario, se modifican el valor y el nivel del inventario y se generan transacciones contables.</span><span class="sxs-lookup"><span data-stu-id="1756a-132">When you post this kind of journal, an inventory receipt or issue is posted, the inventory level and value are changed, and ledger transactions are generated.</span></span>  
4. <span data-ttu-id="1756a-133">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="1756a-133">Click OK.</span></span>
5. <span data-ttu-id="1756a-134">Cierre el formulario.</span><span class="sxs-lookup"><span data-stu-id="1756a-134">Close the form.</span></span>
6. <span data-ttu-id="1756a-135">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="1756a-135">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]