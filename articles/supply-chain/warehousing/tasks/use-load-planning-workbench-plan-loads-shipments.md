---
title: Planificar cargas y envíos mediante el área de trabajo de planificación de la carga
description: Este tema muestra cómo usar el área de trabajo de planificación de cargas para crear una carga para un pedido de ventas.
author: ShylaThompson
manager: tfehr
ms.date: 07/08/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSHistory, WHSLoadTable, WHSLoadPlanningListPage, WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f4fdff8bdc383a85d604fa6e545c625d5782241f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976822"
---
# <a name="plan-loads-and-shipments-using-the-load-planning-workbench"></a><span data-ttu-id="68521-103">Planificar cargas y envíos mediante el área de trabajo de planificación de la carga</span><span class="sxs-lookup"><span data-stu-id="68521-103">Plan loads and shipments using the Load planning workbench</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="68521-104">Este tema muestra cómo usar el área de trabajo de planificación de cargas para crear una carga para un pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="68521-104">This topic shows how to use the load planning workbench to create a load for a sales order.</span></span> <span data-ttu-id="68521-105">Es necesario crear primero el pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="68521-105">As a prerequisite we'll create the sales order first.</span></span> <span data-ttu-id="68521-106">Este procedimiento forma parte del trabajo diario del coordinador de transporte.</span><span class="sxs-lookup"><span data-stu-id="68521-106">This procedure is part of the daily work for the transportation coordinator.</span></span> <span data-ttu-id="68521-107">La empresa de datos de prueba utilizada para crear este procedimiento es USMF.</span><span class="sxs-lookup"><span data-stu-id="68521-107">The demo data company used to create this procedure is USMF.</span></span>


## <a name="create-a-sales-order"></a><span data-ttu-id="68521-108">Crear un pedido de ventas</span><span class="sxs-lookup"><span data-stu-id="68521-108">Create a sales order</span></span>
1. <span data-ttu-id="68521-109">Vaya a **panel de navegación > Módulos > Clientes > Pedidos > Todos los pedidos de vents**.</span><span class="sxs-lookup"><span data-stu-id="68521-109">Go to the **Navigation pane > Modules > Accounts receivable > Orders > All sales orders**.</span></span>
2. <span data-ttu-id="68521-110">Seleccione **Nuevo**.</span><span class="sxs-lookup"><span data-stu-id="68521-110">Select **New**.</span></span>
3. <span data-ttu-id="68521-111">En el campo **Cuenta de cliente**, seleccione el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="68521-111">In the **Customer account** field, select the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="68521-112">Seleccione la cuenta **US-004**.</span><span class="sxs-lookup"><span data-stu-id="68521-112">Select account **US-004**.</span></span>
5. <span data-ttu-id="68521-113">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="68521-113">Select **OK**.</span></span>
6. <span data-ttu-id="68521-114">En el campo **Código de artículo**, seleccione el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="68521-114">In the **Item number** field, select the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="68521-115">Seleccione el artículo **A0001**.</span><span class="sxs-lookup"><span data-stu-id="68521-115">Select item **A0001**.</span></span> <span data-ttu-id="68521-116">**A0001** está habilitado para administración del transporte.</span><span class="sxs-lookup"><span data-stu-id="68521-116">**A0001** is enabled for transportation management.</span></span>  
8. <span data-ttu-id="68521-117">En el campo **Sitio**, seleccione el botón de la lista desplegable para abrir la búsqueda y seleccione un articulo.</span><span class="sxs-lookup"><span data-stu-id="68521-117">In the **Site** field, select the drop-down button to open the lookup, then select an item.</span></span>
9. <span data-ttu-id="68521-118">En el campo **Cantidad**, especifique un número.</span><span class="sxs-lookup"><span data-stu-id="68521-118">In the **Quantity** field, enter a number.</span></span>
10. <span data-ttu-id="68521-119">En el campo **Almacén** , escriba “24" en este ejemplo.</span><span class="sxs-lookup"><span data-stu-id="68521-119">In the **Warehouse** field, type '24' for this example.</span></span> <span data-ttu-id="68521-120">Este almacén está habilitado para administrar el transporte y gestionar almacenes de forma avanzada.</span><span class="sxs-lookup"><span data-stu-id="68521-120">This warehouse is enabled for transportation management and advanced warehouse management.</span></span>  
11. <span data-ttu-id="68521-121">Seleccione **Guardar**.</span><span class="sxs-lookup"><span data-stu-id="68521-121">Select **Save**.</span></span>
12. <span data-ttu-id="68521-122">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="68521-122">Close the page.</span></span>

## <a name="create-a-new-load"></a><span data-ttu-id="68521-123">Creación de una nueva carga</span><span class="sxs-lookup"><span data-stu-id="68521-123">Create a new load</span></span>
1. <span data-ttu-id="68521-124">Vaya al **panel de navegación > Módulos > Administración de transporte > Planificación > Área de trabajo de planificación de la carga**.</span><span class="sxs-lookup"><span data-stu-id="68521-124">Go to the **Navigation pane > Modules > Transportation management > Planning > Load planning workbench**.</span></span>
2. <span data-ttu-id="68521-125">Seleccione la pestaña **Líneas de ventas**. Ahora construirá la carga para el pedido de ventas que acaba de crear.</span><span class="sxs-lookup"><span data-stu-id="68521-125">Select the **Sales lines** tab. Now you'll build the load for the sales order that you just created.</span></span> <span data-ttu-id="68521-126">Las cargas se pueden crear según la oferta y la demanda de los pedidos de compra, los pedidos de transferencia y los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="68521-126">Loads can be built based on supply and demand from purchase orders, transfer orders, and sales orders.</span></span>  
3. <span data-ttu-id="68521-127">En el panel de acciones, haga clic en **Oferta y demanda**.</span><span class="sxs-lookup"><span data-stu-id="68521-127">On the Action Pane, select **Supply and demand**.</span></span>
4. <span data-ttu-id="68521-128">Seleccione **A nueva carga**.</span><span class="sxs-lookup"><span data-stu-id="68521-128">Select **To new load**.</span></span>
5. <span data-ttu-id="68521-129">En el campo **Id. de plantilla de carga**, seleccione el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="68521-129">In the **Load template ID** field, select the drop-down button to open the lookup.</span></span> <span data-ttu-id="68521-130">La plantilla de carga define las medidas máximas para el peso y el volumen de la carga completa.</span><span class="sxs-lookup"><span data-stu-id="68521-130">The Load template defines maximum measurements for weight and volume of the entire load.</span></span> <span data-ttu-id="68521-131">Por ejemplo, la plantilla de carga puede representar el tamaño de un contenedor o de un camión.</span><span class="sxs-lookup"><span data-stu-id="68521-131">For example, the load template might represent the size of a container or truck.</span></span> <span data-ttu-id="68521-132">Seleccione un artículo.</span><span class="sxs-lookup"><span data-stu-id="68521-132">Select an item.</span></span>
6. <span data-ttu-id="68521-133">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="68521-133">Select **OK**.</span></span>

## <a name="rate-and-route-the-load"></a><span data-ttu-id="68521-134">Tasa y ruta para la carga</span><span class="sxs-lookup"><span data-stu-id="68521-134">Rate and route the load</span></span>
1. <span data-ttu-id="68521-135">Seleccione **Clasificación y ruta**.</span><span class="sxs-lookup"><span data-stu-id="68521-135">Select **Rating and routing**.</span></span>
2. <span data-ttu-id="68521-136">Seleccione **Área de trabajo índice y la ruta**.</span><span class="sxs-lookup"><span data-stu-id="68521-136">Select **Rate route workbench**.</span></span>
3. <span data-ttu-id="68521-137">Seleccione **Tienda de tasas**.</span><span class="sxs-lookup"><span data-stu-id="68521-137">Select **Rate shop**.</span></span>
4. <span data-ttu-id="68521-138">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="68521-138">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="68521-139">Seleccione **Asignar**.</span><span class="sxs-lookup"><span data-stu-id="68521-139">Select **Assign**.</span></span>
6. <span data-ttu-id="68521-140">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="68521-140">Close the page.</span></span>

