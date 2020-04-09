---
title: Registro de artículos habilitados para almacenamiento básico mediante un diario de recepción de artículos
description: Este procedimiento muestra cómo registrar artículos mediante el diario de recepción de artículos cuando se usa el "almacenamiento básico" en el módulo de gestión del inventario.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchCreateOrder, WMSJournalTable, WMSJournalCreate, PurchEditLines
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 537418a78f7cc9d1375188076264e38b790e081b
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3145994"
---
# <a name="register-items-for-a-basic-warehousing-enabled-item-using-an-item-an-item-arrival-journal"></a><span data-ttu-id="a4a81-103">Registro de artículos habilitados para almacenamiento básico mediante un diario de recepción de artículos</span><span class="sxs-lookup"><span data-stu-id="a4a81-103">Register items for a basic warehousing enabled item using an item an item arrival journal</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a4a81-104">Este procedimiento muestra cómo registrar artículos mediante el diario de recepción de artículos cuando se usa el "almacenamiento básico" en el módulo de gestión del inventario.</span><span class="sxs-lookup"><span data-stu-id="a4a81-104">This procedure shows you how to register items using the item arrival journal when you are using "basic warehousing" in the Inventory management module.</span></span> <span data-ttu-id="a4a81-105">Esto lo realiza normalmente un empleado de recepción.</span><span class="sxs-lookup"><span data-stu-id="a4a81-105">This would usually be done by a receiving clerk.</span></span> <span data-ttu-id="a4a81-106">Puede ejecutar este procedimiento en la empresa de datos de demostración USMF con los valores de ejemplo que se muestran.</span><span class="sxs-lookup"><span data-stu-id="a4a81-106">You can run this procedure in demo data company USMF with the example values that are shown.</span></span>  <span data-ttu-id="a4a81-107">Si no está utilizando USMF, necesita tener un pedido de compra confirmado con una línea de pedido de compra abierta antes de comenzar esta guía.</span><span class="sxs-lookup"><span data-stu-id="a4a81-107">If you are not using USMF, you need to have a confirmed purchase order with an open purchase order line before you start this guide.</span></span> <span data-ttu-id="a4a81-108">El artículo de la línea debe mantenerse en existencias.</span><span class="sxs-lookup"><span data-stu-id="a4a81-108">The item on the line must be stocked.</span></span> <span data-ttu-id="a4a81-109">El artículo debe estar asociado con un grupo de dimensiones de almacenamiento, donde estén activos el sitio y el almacén.</span><span class="sxs-lookup"><span data-stu-id="a4a81-109">And the item needs to be associated with a storage dimension group, where site and warehouse are active.</span></span>


## <a name="create-item-arrival-journal-header"></a><span data-ttu-id="a4a81-110">Creación del encabezado del diario de recepción de artículos</span><span class="sxs-lookup"><span data-stu-id="a4a81-110">Create item arrival journal header</span></span>
1. <span data-ttu-id="a4a81-111">Vaya a Gestión del inventario > Movimientos de diario > Recepción de artículos > Recepción de artículos.</span><span class="sxs-lookup"><span data-stu-id="a4a81-111">Go to Inventory management > Journal entries > Item arrival > Item arrival.</span></span>
2. <span data-ttu-id="a4a81-112">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="a4a81-112">Click New.</span></span>
3. <span data-ttu-id="a4a81-113">En el campo Nombre, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a4a81-113">In the Name field, type a value.</span></span>
    * <span data-ttu-id="a4a81-114">Si está usando USMF, puede escribir WHS.</span><span class="sxs-lookup"><span data-stu-id="a4a81-114">If you are using USMF, you can type WHS.</span></span> <span data-ttu-id="a4a81-115">Si está usando otros datos, el diario cuyo nombre elija tiene que tener las siguientes propiedades: Comprobar ubicación de picking debe estar definida en No, y Gestión de cuarentena debe estar definida en No.</span><span class="sxs-lookup"><span data-stu-id="a4a81-115">If you're using other data, the journal whose name you choose has to have the following properties: cheque picking location must be set to No, and Quarantine management must be set to No.</span></span>  
4. <span data-ttu-id="a4a81-116">En el campo Albarán, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="a4a81-116">In the Packing slip field, type a value.</span></span>
    * <span data-ttu-id="a4a81-117">Esta es el identificador del albarán emitido por el proveedor.</span><span class="sxs-lookup"><span data-stu-id="a4a81-117">This is the packing slip ID from the packing slip issued by the vendor.</span></span> <span data-ttu-id="a4a81-118">Agregue un número único.</span><span class="sxs-lookup"><span data-stu-id="a4a81-118">Add a unique number.</span></span>  
5. <span data-ttu-id="a4a81-119">En el campo Número, seleccione el pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="a4a81-119">In the Number field, In the Number field, select the purchase order..</span></span>
6. <span data-ttu-id="a4a81-120">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a4a81-120">Click OK.</span></span>

## <a name="add-lines-to-item-arrival-journal"></a><span data-ttu-id="a4a81-121">Adición de líneas al diario de recepción de artículos</span><span class="sxs-lookup"><span data-stu-id="a4a81-121">Add lines to item arrival journal</span></span>
1. <span data-ttu-id="a4a81-122">Haga clic en Funciones.</span><span class="sxs-lookup"><span data-stu-id="a4a81-122">Click Functions.</span></span>
2. <span data-ttu-id="a4a81-123">Haga clic en Crear líneas.</span><span class="sxs-lookup"><span data-stu-id="a4a81-123">Click Create lines.</span></span>
    * <span data-ttu-id="a4a81-124">Las líneas se pueden especificar manualmente en este diario o se pueden crear automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a4a81-124">The lines can be entered manually into this journal or created automatically.</span></span> <span data-ttu-id="a4a81-125">Aquí se le mostrará cómo crearlas automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a4a81-125">This will show you how to create this automatically.</span></span>  
3. <span data-ttu-id="a4a81-126">Active o desactive la casilla Inicializar cantidad.</span><span class="sxs-lookup"><span data-stu-id="a4a81-126">Check or uncheck the Initialize quantity checkbox.</span></span>
    * <span data-ttu-id="a4a81-127">Esto inicializará la cantidad en las líneas de diario con la cantidad no registrada desde línea de pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="a4a81-127">This will initialize the quantity on the journal lines with the quantity not registered from the purchase order line.</span></span>  
4. <span data-ttu-id="a4a81-128">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a4a81-128">Click OK.</span></span>

## <a name="post-the-journal"></a><span data-ttu-id="a4a81-129">Registrar el diario</span><span class="sxs-lookup"><span data-stu-id="a4a81-129">Post the journal</span></span>
1. <span data-ttu-id="a4a81-130">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="a4a81-130">Click Post.</span></span>
2. <span data-ttu-id="a4a81-131">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a4a81-131">Click OK.</span></span>

## <a name="generate-the-product-receipt"></a><span data-ttu-id="a4a81-132">Generación de la recepción del producto</span><span class="sxs-lookup"><span data-stu-id="a4a81-132">Generate the product receipt</span></span>
1. <span data-ttu-id="a4a81-133">Haga clic en Funciones.</span><span class="sxs-lookup"><span data-stu-id="a4a81-133">Click Functions.</span></span>
2. <span data-ttu-id="a4a81-134">Haga clic en Recepción de producto.</span><span class="sxs-lookup"><span data-stu-id="a4a81-134">Click Product receipt.</span></span>
3. <span data-ttu-id="a4a81-135">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="a4a81-135">Click OK.</span></span>

