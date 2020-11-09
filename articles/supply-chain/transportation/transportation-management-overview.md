---
title: Visión general de la administración de transporte
description: Este tema proporciona una visión general de la funcionalidad de administración de transportes en Supply Chain Management.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSParameters,TMSRateRouteWorkbench, WHSLoadPlanningWorkbench, TMSLoadBuildTemplateApply, WHSLoadTemplate, TMSTransportationStatus, TMSLoadSeal, TMSLoadBuildProposal, TMSLoadBuildWorkbench, TMSLoadBuildStrategy, TMSLoadBuildStrategyAttributeValue
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 30251
ms.assetid: d4e3550c-bca8-469c-82df-56ac0083e4ac
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4affc5846ee329a4571d6fb3e0c42873387241ad
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016387"
---
# <a name="transportation-management-overview"></a><span data-ttu-id="0fbca-103">Visión general de la administración de transporte</span><span class="sxs-lookup"><span data-stu-id="0fbca-103">Transportation management overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0fbca-104">Este tema proporciona una visión general de la funcionalidad de administración de transportes en Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="0fbca-104">This topic gives an overview of the transportation management functionality in Supply Chain Management.</span></span>

<span data-ttu-id="0fbca-105">La Administración de transporte le permite usar el transporte de su empresa e identificar soluciones de proveedor y de ruta para los pedidos de entrada y salida.</span><span class="sxs-lookup"><span data-stu-id="0fbca-105">Transportation management lets you use your company’s transportation, and also lets you identify vendor and routing solutions for inbound and outbound orders.</span></span> <span data-ttu-id="0fbca-106">Por ejemplo, puede identificar la ruta más rápida o la tarifa menos cara para un envío.</span><span class="sxs-lookup"><span data-stu-id="0fbca-106">For example, you can identify the fastest route or the least expensive rate for a shipment.</span></span> <span data-ttu-id="0fbca-107">En la tabla siguiente se describen los escenarios principales para usar la Administración de transporte.</span><span class="sxs-lookup"><span data-stu-id="0fbca-107">The following table describes the main scenarios for using Transportation management.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0fbca-108">Situación</span><span class="sxs-lookup"><span data-stu-id="0fbca-108">Scenario</span></span></th>
<th><span data-ttu-id="0fbca-109">Cómo puede ayudar la Administración de transporte</span><span class="sxs-lookup"><span data-stu-id="0fbca-109">How Transportation management can help</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0fbca-110">Use proveedores de logística externos para las actividades de transporte.</span><span class="sxs-lookup"><span data-stu-id="0fbca-110">Use external logistics providers for transportation activities.</span></span></td>
<td><span data-ttu-id="0fbca-111">Use la gestión de transporte para el transporte de entrada y/o salida.</span><span class="sxs-lookup"><span data-stu-id="0fbca-111">Use Transportation management for inbound and/or outbound transportation.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0fbca-112">La propia flota de la empresa está disponible para entrega o recogida, y los gastos de entrega se aplican a los clientes.</span><span class="sxs-lookup"><span data-stu-id="0fbca-112">The company&#39;s own fleet is available for delivery/pickup, and delivery charges are passed on to customers.</span></span></td>
<td><span data-ttu-id="0fbca-113">Para los procesos de salida, puede usar la Administración de transporte para determinar los gastos de transporte y pasarlos a los clientes.</span><span class="sxs-lookup"><span data-stu-id="0fbca-113">For the outbound processes, you can use Transportation management to determine the transportation charges and pass them on to customers.</span></span> <span data-ttu-id="0fbca-114">Sin embargo, no es necesario el proceso de conciliación de facturas de transportista.</span><span class="sxs-lookup"><span data-stu-id="0fbca-114">However, the carrier invoice reconciliation process isn&#39;t required.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="0fbca-115">La propia flota de la empresa está disponible para entrega o recogida, pero los gastos de entrega no se aplican a los clientes, ya que los precios de productos incluyen el transporte.</span><span class="sxs-lookup"><span data-stu-id="0fbca-115">The company&#39;s own fleet is available for delivery/pickup, but delivery charges aren&#39;t passed on to customers, because product prices include transportation.</span></span></td>
<td><span data-ttu-id="0fbca-116">No se requiere gran parte la funcionalidad de la gestión de transporte.</span><span class="sxs-lookup"><span data-stu-id="0fbca-116">A lot of the Transportation management functionality isn&#39;t required.</span></span> <span data-ttu-id="0fbca-117">Sin embargo, puede usar la Administración de transporte para determinar los índices de transporte y ajustar el precio de ventas en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="0fbca-117">However, you can use Transportation management to determine the transportation rates and adjust the sales price accordingly.</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="0fbca-118">Otra entidad jurídica de la misma empresa proporciona el servicio de logística.</span><span class="sxs-lookup"><span data-stu-id="0fbca-118">Logistics service is provided by another legal entity in the same company.</span></span></td>
<td><ul>
<li><span data-ttu-id="0fbca-119">Puede usar la Administración de transporte tratando la otra entidad jurídica como cualquier otro transportista de envío.</span><span class="sxs-lookup"><span data-stu-id="0fbca-119">You can use Transportation management by treating the other legal entity like any other shipping carrier.</span></span> <span data-ttu-id="0fbca-120">No puede automatizar las transacciones económicas entre entidades jurídicas.</span><span class="sxs-lookup"><span data-stu-id="0fbca-120">You can&#39;t automate the economic transactions between legal entities.</span></span> <span data-ttu-id="0fbca-121">Por tanto, debe gestionar estas transacciones manualmente (por ejemplo, creando un pedido de compra).</span><span class="sxs-lookup"><span data-stu-id="0fbca-121">Therefore, you must handle these transactions manually (for example, by creating a purchase order).</span></span></li>
<li><span data-ttu-id="0fbca-122">En la entidad jurídica que proporciona servicios de logística, se puede usar la Administración de transporte para determinar los índices de transporte.</span><span class="sxs-lookup"><span data-stu-id="0fbca-122">In the legal entity that provides the logistics services, Transportation management can be used to determine transportation rates.</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="planning-transportation-in-supply-chain-management"></a><span data-ttu-id="0fbca-123">Planificación del transporte en Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="0fbca-123">Planning transportation in Supply Chain Management</span></span>
<span data-ttu-id="0fbca-124">En la Administración de transporte, la planificación del transporte se puede basar en órdenes o en los envíos que se crean a partir de esos pedidos.</span><span class="sxs-lookup"><span data-stu-id="0fbca-124">In Transportation management, transportation planning can be based either on orders or on the shipments that are created based on those orders.</span></span> <span data-ttu-id="0fbca-125">Los envíos siempre existen en algún punto específico pero no son necesarios para la planificación de transporte.</span><span class="sxs-lookup"><span data-stu-id="0fbca-125">The shipments always exist at some point in time but aren't required for transportation planning.</span></span> <span data-ttu-id="0fbca-126">Los pedidos de transferencia forman parte del escenario de salida y se pueden planificar junto con los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="0fbca-126">Transfer orders are part of the outbound scenario and can be planned together with sales orders.</span></span> 

![Cargar dibujo](./media/Load-drawing1-1024x477.jpg)

## <a name="inbound-transportation"></a><span data-ttu-id="0fbca-128">Transporte de entrada</span><span class="sxs-lookup"><span data-stu-id="0fbca-128">Inbound transportation</span></span>
<span data-ttu-id="0fbca-129">Cuando pide artículos a un proveedor, y los artículos se deben entregarse a su almacén, puede que desee organizar el transporte de los artículos usted mismo.</span><span class="sxs-lookup"><span data-stu-id="0fbca-129">When you order items from a vendor, and the items must be delivered to your warehouse, you might want to arrange the transport of the items yourself.</span></span> <span data-ttu-id="0fbca-130">Puede usar Supply Chain Management para planificar el transporte y la recepción de la carga de entrada.</span><span class="sxs-lookup"><span data-stu-id="0fbca-130">You can use Supply Chain Management to plan the transportation and receipt of the inbound load.</span></span> <span data-ttu-id="0fbca-131">En la siguiente ilustración se muestra el flujo del proceso empresarial para planificar el transporte de una carga de entrada.</span><span class="sxs-lookup"><span data-stu-id="0fbca-131">The following illustration shows the business process flow for planning transportation for an inbound load.</span></span> 

![Flujo del proceso empresarial para el transporte de la carga de entrada](./media/Businessprocessflowforinboundloadtransportation.jpg)

## <a name="outbound-transportation"></a><span data-ttu-id="0fbca-133">Transporte de salida</span><span class="sxs-lookup"><span data-stu-id="0fbca-133">Outbound transportation</span></span>
<span data-ttu-id="0fbca-134">Puede planificar y procesar una carga de salida para enviar artículos específicos del almacén de una empresa a un cliente.</span><span class="sxs-lookup"><span data-stu-id="0fbca-134">You can plan and process an outbound load to ship specific items from a company’s warehouse to a customer.</span></span> <span data-ttu-id="0fbca-135">Puede usar Supply Chain Management para planificar el transporte y el envío de una carga saliente.</span><span class="sxs-lookup"><span data-stu-id="0fbca-135">You can use Supply Chain Management to plan the transportation and shipping of an outbound load.</span></span> <span data-ttu-id="0fbca-136">En la siguiente ilustración se muestra el flujo del proceso empresarial para planificar y procesar las cargas de salida para su envío.</span><span class="sxs-lookup"><span data-stu-id="0fbca-136">The following illustration shows the business process flow for planning and processing outbound loads for shipping.</span></span> 

![Planificación y procesamiento de cargas de salida](./media/Planningandprocessingoutboundloads.jpg)

## <a name="load-building"></a><span data-ttu-id="0fbca-138">Planificación de carga</span><span class="sxs-lookup"><span data-stu-id="0fbca-138">Load building</span></span>
<span data-ttu-id="0fbca-139">Supply Chain Management proporciona una estrategia de planificación de carga que se denomina Estrategia de planificación de la carga basada en volumen.</span><span class="sxs-lookup"><span data-stu-id="0fbca-139">Supply Chain Management provides a load building strategy that is named the Volume-based load building strategy.</span></span> <span data-ttu-id="0fbca-140">Esta estrategia le permite usar los valores máximos que se especifican para la altura y el peso de la plantilla de carga o bien, puede reemplazar los ajustes especificando valores nuevos.</span><span class="sxs-lookup"><span data-stu-id="0fbca-140">This strategy lets you use the maximum values that are specified for height and weight in the load template, or you can override the settings by entering new values.</span></span> <span data-ttu-id="0fbca-141">Para usar esta estrategia, selecciónela en el campo **Estrategia de creación de carga** en la ficha desplegable **Programa de instalación** de la página **Banco de trabajo de creación de carga**.</span><span class="sxs-lookup"><span data-stu-id="0fbca-141">To use this strategy, select it in the **Load building strategy** field on the **Setup** FastTab on the **Load building workbench** page.</span></span> <span data-ttu-id="0fbca-142">Además, puede agregar sus propias estrategias de creación de carga creando una nueva clase en el árbol de objetos de aplicación (AOT).</span><span class="sxs-lookup"><span data-stu-id="0fbca-142">In addition, you can add your own load-building strategies by creating a new class in the Application Object Tree (AOT).</span></span>



