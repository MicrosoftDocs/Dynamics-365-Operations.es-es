---
title: Planificar cargas y envíos mediante el área de trabajo de planificación de la carga
description: Este procedimiento muestra cómo usar el área de trabajo de planificación de cargas para crear una carga para un pedido de ventas.
author: ShylaThompson
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1927cff48beb30f934bd066c32ab48dfb9d06f74
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1564814"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a><span data-ttu-id="65d8b-103">Planificar cargas y envíos mediante el área de trabajo de planificación de la carga</span><span class="sxs-lookup"><span data-stu-id="65d8b-103">Plan loads and shipments using the Load planning workbench</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="65d8b-104">Este procedimiento muestra cómo usar el área de trabajo de planificación de cargas para crear una carga para un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="65d8b-104">This procedure shows how to use the load planning workbench to create a load for a sales order.</span></span> <span data-ttu-id="65d8b-105">Es necesario crear primero el pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="65d8b-105">As a prerequisite we'll create the sales order first.</span></span> <span data-ttu-id="65d8b-106">Este procedimiento forma parte del trabajo diario del coordinador de transporte.</span><span class="sxs-lookup"><span data-stu-id="65d8b-106">This procedure is part of the daily work for the transportation coordinator.</span></span> <span data-ttu-id="65d8b-107">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="65d8b-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="65d8b-108">Crear un pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="65d8b-108">Create a sales order</span></span>
1. <span data-ttu-id="65d8b-109">Vaya a Clientes > Pedidos > Todos los pedidos de venta.</span><span class="sxs-lookup"><span data-stu-id="65d8b-109">Go to Accounts receivable > Orders > All sales orders.</span></span>
2. <span data-ttu-id="65d8b-110">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="65d8b-110">Click New.</span></span>
3. <span data-ttu-id="65d8b-111">En el campo Cuenta de cliente, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="65d8b-111">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="65d8b-112">Seleccione la cuenta US-004.</span><span class="sxs-lookup"><span data-stu-id="65d8b-112">Select account US-004.</span></span>
5. <span data-ttu-id="65d8b-113">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="65d8b-113">Click OK.</span></span>
6. <span data-ttu-id="65d8b-114">En el campo Código de artículo, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="65d8b-114">In the Item number field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="65d8b-115">Seleccione el artículo A0001.</span><span class="sxs-lookup"><span data-stu-id="65d8b-115">Select item A0001.</span></span>
    * <span data-ttu-id="65d8b-116">A0001 está habilitado para administración del transporte.</span><span class="sxs-lookup"><span data-stu-id="65d8b-116">A0001 is enabled for transportation management.</span></span>  
8. <span data-ttu-id="65d8b-117">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="65d8b-117">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="65d8b-118">En el campo Cantidad, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="65d8b-118">In the Quantity field, enter a number.</span></span>
10. <span data-ttu-id="65d8b-119">En el campo Almacén, escriba "24".</span><span class="sxs-lookup"><span data-stu-id="65d8b-119">In the Warehouse field, type '24'.</span></span>
    * <span data-ttu-id="65d8b-120">En este ejemplo, seleccione el almacén 24.</span><span class="sxs-lookup"><span data-stu-id="65d8b-120">In this example select warehouse 24.</span></span> <span data-ttu-id="65d8b-121">Este almacén está habilitado para administrar el transporte y gestionar almacenes de forma avanzada.</span><span class="sxs-lookup"><span data-stu-id="65d8b-121">This warehouse is enabled for transportation management and advanced warehouse management.</span></span>  
11. <span data-ttu-id="65d8b-122">Haga clic en Guardar.</span><span class="sxs-lookup"><span data-stu-id="65d8b-122">Click Save.</span></span>
12. <span data-ttu-id="65d8b-123">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="65d8b-123">Close the page.</span></span>

## <a name="create-a-new-load"></a><span data-ttu-id="65d8b-124">Creación de una nueva carga</span><span class="sxs-lookup"><span data-stu-id="65d8b-124">Create a new load</span></span>
1. <span data-ttu-id="65d8b-125">Vaya a Administración de transporte > Planificación > Área de trabajo de planificación de la carga.</span><span class="sxs-lookup"><span data-stu-id="65d8b-125">Go to Transportation management > Planning > Load planning workbench.</span></span>
2. <span data-ttu-id="65d8b-126">Haga clic en la ficha Líneas de ventas.</span><span class="sxs-lookup"><span data-stu-id="65d8b-126">Click the Sales lines tab.</span></span>
    * <span data-ttu-id="65d8b-127">Ahora construirá la carga para el pedido de ventas que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="65d8b-127">Now you'll build the load for the sales order that you just created.</span></span> <span data-ttu-id="65d8b-128">Las cargas se pueden crear según la oferta y la demanda de los pedidos de compra, los pedidos de transferencia y los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="65d8b-128">Loads can be built based on supply and demand from purchase orders, transfer orders, and sales orders.</span></span>  
3. <span data-ttu-id="65d8b-129">En el panel de acciones, haga clic en Oferta y demanda.</span><span class="sxs-lookup"><span data-stu-id="65d8b-129">On the Action Pane, click Supply and demand.</span></span>
4. <span data-ttu-id="65d8b-130">Haga clic en A nueva carga.</span><span class="sxs-lookup"><span data-stu-id="65d8b-130">Click To new load.</span></span>
5. <span data-ttu-id="65d8b-131">En el campo Id. de plantilla de carga, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="65d8b-131">In the Load template ID field, click the drop-down button to open the lookup.</span></span>
    * <span data-ttu-id="65d8b-132">La plantilla de carga define las medidas máximas para el peso y el volumen de la carga completa.</span><span class="sxs-lookup"><span data-stu-id="65d8b-132">The Load template defines maximum measurements for weight and volume of the entire load.</span></span> <span data-ttu-id="65d8b-133">Por ejemplo, la plantilla de carga puede representar el tamaño de un contenedor o de un camión.</span><span class="sxs-lookup"><span data-stu-id="65d8b-133">For example, the load template might represent the size of a container or truck.</span></span>  
6. <span data-ttu-id="65d8b-134">En la lista, haga clic en el vínculo de la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="65d8b-134">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="65d8b-135">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="65d8b-135">Click OK.</span></span>

## <a name="rate-and-route-the-load"></a><span data-ttu-id="65d8b-136">Tasa y ruta para la carga</span><span class="sxs-lookup"><span data-stu-id="65d8b-136">Rate and route the load</span></span>
1. <span data-ttu-id="65d8b-137">Haga clic en Clasificación y ruta.</span><span class="sxs-lookup"><span data-stu-id="65d8b-137">Click Rating and routing.</span></span>
2. <span data-ttu-id="65d8b-138">Haga clic en Área de trabajo de la ruta de la tasa.</span><span class="sxs-lookup"><span data-stu-id="65d8b-138">Click Rate route workbench.</span></span>
3. <span data-ttu-id="65d8b-139">Haga clic en Opciones de tasas.</span><span class="sxs-lookup"><span data-stu-id="65d8b-139">Click Rate shop.</span></span>
4. <span data-ttu-id="65d8b-140">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="65d8b-140">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="65d8b-141">Haga clic en Asignar.</span><span class="sxs-lookup"><span data-stu-id="65d8b-141">Click Assign.</span></span>
6. <span data-ttu-id="65d8b-142">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="65d8b-142">Close the page.</span></span>
7. <span data-ttu-id="65d8b-143">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="65d8b-143">Close the page.</span></span>

