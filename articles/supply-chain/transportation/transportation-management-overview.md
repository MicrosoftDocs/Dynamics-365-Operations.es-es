---
title: "Visión general de la administración de transporte"
description: "Este tema ofrece una visión general de la funcionalidad de Administración de transporte en Microsoft Dynamics 365 for Finance and Operations."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 30251
ms.assetid: d4e3550c-bca8-469c-82df-56ac0083e4ac
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 1c71c8f6c4f94342ac18cbfb7dfbc02ddb3f9f35
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="transportation-management-overview"></a><span data-ttu-id="35482-103">Visión general de la administración de transporte</span><span class="sxs-lookup"><span data-stu-id="35482-103">Transportation management overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="35482-104">Este tema ofrece una visión general de la funcionalidad de Administración de transporte en Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="35482-104">This topic gives an overview of the transportation management functionality in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="35482-105">La Administración de transporte le permite usar el transporte de su empresa e identificar soluciones de proveedor y de ruta para los pedidos de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="35482-105">Transportation management lets you use your company’s transportation, and also lets you identify vendor and routing solutions for inbound and outbound orders.</span></span> <span data-ttu-id="35482-106">Por ejemplo, puede identificar la ruta más rápida o la tarifa menos cara para un envío.</span><span class="sxs-lookup"><span data-stu-id="35482-106">For example, you can identify the fastest route or the least expensive rate for a shipment.</span></span> <span data-ttu-id="35482-107">En la tabla siguiente se describen los escenarios principales para usar la Administración de transporte en Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="35482-107">The following table describes the main scenarios for using Transportation management in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="35482-108">Situación</span><span class="sxs-lookup"><span data-stu-id="35482-108">Scenario</span></span></th>
<th><span data-ttu-id="35482-109">Cómo puede ayudar la Administración de transporte</span><span class="sxs-lookup"><span data-stu-id="35482-109">How Transportation management can help</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="35482-110">Use proveedores de logística externos para las actividades de transporte.</span><span class="sxs-lookup"><span data-stu-id="35482-110">Use external logistics providers for transportation activities.</span></span></td>
<td><span data-ttu-id="35482-111">Use la gestión de transporte para el transporte de entrada y/o salida.</span><span class="sxs-lookup"><span data-stu-id="35482-111">Use Transportation management for inbound and/or outbound transportation.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="35482-112">La propia flota de la empresa está disponible para entrega o recogida, y los gastos de entrega se aplican a los clientes.</span><span class="sxs-lookup"><span data-stu-id="35482-112">The company's own fleet is available for delivery/pickup, and delivery charges are passed on to customers.</span></span></td>
<td><span data-ttu-id="35482-113">Para los procesos de salida, puede usar la Administración de transporte para determinar los gastos de transporte y pasarlos a los clientes.</span><span class="sxs-lookup"><span data-stu-id="35482-113">For the outbound processes, you can use Transportation management to determine the transportation charges and pass them on to customers.</span></span> <span data-ttu-id="35482-114">Sin embargo, no es necesario el proceso de conciliación de facturas de transportista.</span><span class="sxs-lookup"><span data-stu-id="35482-114">However, the carrier invoice reconciliation process isn't required.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="35482-115">La propia flota de la empresa está disponible para entrega o recogida, pero los gastos de entrega no se aplican a los clientes, ya que los precios de productos incluyen el transporte.</span><span class="sxs-lookup"><span data-stu-id="35482-115">The company's own fleet is available for delivery/pickup, but delivery charges aren't passed on to customers, because product prices include transportation.</span></span></td>
<td><span data-ttu-id="35482-116">No se requiere gran parte la funcionalidad de la gestión de transporte.</span><span class="sxs-lookup"><span data-stu-id="35482-116">A lot of the Transportation management functionality isn't required.</span></span> <span data-ttu-id="35482-117">Sin embargo, puede usar la Administración de transporte para determinar los índices de transporte y ajustar el precio de ventas en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="35482-117">However, you can use Transportation management to determine the transportation rates and adjust the sales price accordingly.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="35482-118">Otra entidad jurídica de la misma empresa proporciona el servicio de logística.</span><span class="sxs-lookup"><span data-stu-id="35482-118">Logistics service is provided by another legal entity in the same company.</span></span></td>
<td><ul>
<li><span data-ttu-id="35482-119">Puede usar la Administración de transporte tratando la otra entidad jurídica como cualquier otro transportista de envío.</span><span class="sxs-lookup"><span data-stu-id="35482-119">You can use Transportation management by treating the other legal entity like any other shipping carrier.</span></span> <span data-ttu-id="35482-120">No puede automatizar las transacciones económicas entre entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="35482-120">You can't automate the economic transactions between legal entities.</span></span> <span data-ttu-id="35482-121">Por tanto, debe gestionar estas transacciones manualmente (por ejemplo, creando un pedido de compra).</span><span class="sxs-lookup"><span data-stu-id="35482-121">Therefore, you must handle these transactions manually (for example, by creating a purchase order).</span></span></li>
<li><span data-ttu-id="35482-122">En la entidad jurídica que proporciona servicios de logística, se puede usar la Administración de transporte para determinar los índices de transporte.</span><span class="sxs-lookup"><span data-stu-id="35482-122">In the legal entity that provides the logistics services, Transportation management can be used to determine transportation rates.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="planning-transportation-in-finance-and-operations"></a><span data-ttu-id="35482-123">Planificación del transporte en Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="35482-123">Planning transportation in Finance and Operations</span></span>
<span data-ttu-id="35482-124">En la Administración de transporte, la planificación del transporte se puede basar en órdenes o en los envíos que se crean a partir de esos pedidos.</span><span class="sxs-lookup"><span data-stu-id="35482-124">In Transportation management, transportation planning can be based either on orders or on the shipments that are created based on those orders.</span></span> <span data-ttu-id="35482-125">Los envíos siempre existen en algún punto específico pero no son necesarios para la planificación de transporte.</span><span class="sxs-lookup"><span data-stu-id="35482-125">The shipments always exist at some point in time but aren't required for transportation planning.</span></span> <span data-ttu-id="35482-126">Los pedidos de transferencia forman parte del escenario de salida y se pueden planificar junto con los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="35482-126">Transfer orders are part of the outbound scenario and can be planned together with sales orders.</span></span> 

![Cargar dibujo](./media/Load-drawing1-1024x477.jpg)

## <a name="inbound-transportation"></a><span data-ttu-id="35482-128">Transporte de entrada</span><span class="sxs-lookup"><span data-stu-id="35482-128">Inbound transportation</span></span>
<span data-ttu-id="35482-129">Cuando pide artículos a un proveedor, y los artículos se deben entregarse a su almacén, puede que desee organizar el transporte de los artículos usted mismo.</span><span class="sxs-lookup"><span data-stu-id="35482-129">When you order items from a vendor, and the items must be delivered to your warehouse, you might want to arrange the transport of the items yourself.</span></span> <span data-ttu-id="35482-130">Puede usar Finance and Operations para planificar el transporte y la recepción de la carga de entrada.</span><span class="sxs-lookup"><span data-stu-id="35482-130">You can use Finance and Operations to plan the transportation and receipt of the inbound load.</span></span> <span data-ttu-id="35482-131">En la siguiente ilustración se muestra el flujo del proceso empresarial para planificar el transporte de una carga de entrada.</span><span class="sxs-lookup"><span data-stu-id="35482-131">The following illustration shows the business process flow for planning transportation for an inbound load.</span></span> 

![Flujo del proceso empresarial para el transporte de la carga de entrada](./media/Businessprocessflowforinboundloadtransportation.jpg)

## <a name="outbound-transportation"></a><span data-ttu-id="35482-133">Transporte de salida</span><span class="sxs-lookup"><span data-stu-id="35482-133">Outbound transportation</span></span>
<span data-ttu-id="35482-134">Puede planificar y procesar una carga de salida para enviar artículos específicos del almacén de una empresa a un cliente.</span><span class="sxs-lookup"><span data-stu-id="35482-134">You can plan and process an outbound load to ship specific items from a company’s warehouse to a customer.</span></span> <span data-ttu-id="35482-135">Puede usar Finance and Operations para planificar el transporte y el envío de una carga de salida.</span><span class="sxs-lookup"><span data-stu-id="35482-135">You can use Finance and Operations to plan the transportation and shipping of an outbound load.</span></span> <span data-ttu-id="35482-136">En la siguiente ilustración se muestra el flujo del proceso empresarial para planificar y procesar las cargas de salida para su envío.</span><span class="sxs-lookup"><span data-stu-id="35482-136">The following illustration shows the business process flow for planning and processing outbound loads for shipping.</span></span> 

![Planificación y procesamiento de cargas de salida](./media/Planningandprocessingoutboundloads.jpg)

## <a name="load-building"></a><span data-ttu-id="35482-138">Planificación de carga</span><span class="sxs-lookup"><span data-stu-id="35482-138">Load building</span></span>
<span data-ttu-id="35482-139">Finance and Operations proporciona una estrategia de planificación de carga que se denomina Estrategia de planificación de la carga basada en volumen.</span><span class="sxs-lookup"><span data-stu-id="35482-139">Finance and Operations provides a load building strategy that is named the Volume-based load building strategy.</span></span> <span data-ttu-id="35482-140">Esta estrategia le permite usar los valores máximos que se especifican para la altura y el peso de la plantilla de carga o bien, puede reemplazar los ajustes especificando valores nuevos.</span><span class="sxs-lookup"><span data-stu-id="35482-140">This strategy lets you use the maximum values that are specified for height and weight in the load template, or you can override the settings by entering new values.</span></span> <span data-ttu-id="35482-141">Para usar esta estrategia, selecciónela en el campo **Estrategia de creación de carga** en la ficha desplegable **Programa de instalación** de la página **Banco de trabajo de creación de carga**.</span><span class="sxs-lookup"><span data-stu-id="35482-141">To use this strategy, select it in the **Load building strategy** field on the **Setup** FastTab on the **Load building workbench** page.</span></span> <span data-ttu-id="35482-142">Además, puede agregar sus propias estrategias de creación de carga creando una nueva clase en el árbol de objetos de aplicación (AOT).</span><span class="sxs-lookup"><span data-stu-id="35482-142">In addition, you can add your own load-building strategies by creating a new class in the Application Object Tree (AOT).</span></span>




