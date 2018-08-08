---
title: "Planificar cargas mediante la consolidación de concentrador"
description: "En este artículo se describe la característica de consolidación de envíos en un concentrador al entregar mercancías desde almacenes diferentes al mismo cliente, o cuando recibe mercancías de varios proveedores en el mismo almacén."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WHSLoadPlanningWorkbench
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 92273
ms.assetid: d27b0926-a534-4caf-a2a3-acbc7c440bca
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 6743338819da3821cde18ec34a9c79290036ca23
ms.contentlocale: es-es
ms.lasthandoff: 08/07/2018

---

# <a name="plan-loads-using-hub-consolidation"></a><span data-ttu-id="ace15-103">Planificar cargas mediante la consolidación de concentrador</span><span class="sxs-lookup"><span data-stu-id="ace15-103">Plan loads using hub consolidation</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ace15-104">En este artículo se describe la característica de consolidación de envíos en un concentrador al entregar mercancías desde almacenes diferentes al mismo cliente, o cuando recibe mercancías de varios proveedores en el mismo almacén.</span><span class="sxs-lookup"><span data-stu-id="ace15-104">This article describes the feature for consolidating shipments in a hub when you deliver goods from different warehouses to the same customer, or when you receive goods from multiple vendors in the same warehouse.</span></span>

<span data-ttu-id="ace15-105">Puede ser útil consolidar envíos en un concentrador al entregar mercancías desde almacenes diferentes al mismo cliente, o cuando se entregan mercancías de varios proveedores al mismo almacén.</span><span class="sxs-lookup"><span data-stu-id="ace15-105">It can be useful to consolidate shipments in a hub when you deliver goods from different warehouses to the same customer, or when goods are delivered from multiple vendors to the same warehouse.</span></span>

## <a name="building-loads"></a><span data-ttu-id="ace15-106">Creación de cargas</span><span class="sxs-lookup"><span data-stu-id="ace15-106">Building loads</span></span>
<span data-ttu-id="ace15-107">Para poder usar la consolidación de concentrador, debe habilitar la opción **Planificación de elementos en tránsito** en la página **Parámetros de administración de transporte**.</span><span class="sxs-lookup"><span data-stu-id="ace15-107">Before you can use hub consolidation, you must enable the **In transit planning** option on the **Transportation management parameters** page.</span></span> <span data-ttu-id="ace15-108">También debe crear los concentradores donde se producirá la consolidación.</span><span class="sxs-lookup"><span data-stu-id="ace15-108">You must also create the hubs where consolidation will occur.</span></span> <span data-ttu-id="ace15-109">El siguiente diagrama muestra un ejemplo de consolidación de concentrador.</span><span class="sxs-lookup"><span data-stu-id="ace15-109">The following diagram shows an example of hub consolidation.</span></span> <span data-ttu-id="ace15-110">En este caso, los pedidos de ventas de diferentes almacenes van al mismo cliente.</span><span class="sxs-lookup"><span data-stu-id="ace15-110">In this case, sales orders from different warehouses are going to the same customer.</span></span> <span data-ttu-id="ace15-111">Las cargas básicas se crean en función de los pedidos de ventas de la forma habitual, usando la página **Área de trabajo de planificación de la carga**.</span><span class="sxs-lookup"><span data-stu-id="ace15-111">The basic loads are created based on sales orders in the usual way, by using the **Load planning workbench** page.</span></span> <span data-ttu-id="ace15-112">Para consolidar las dos cargas en un concentrador antes de entregarse al cliente, en la página **Área de trabajo de planificación de la carga**, en el campo **Transporte**, seleccione **Consolidación de centros**.</span><span class="sxs-lookup"><span data-stu-id="ace15-112">To consolidate the two loads in a hub before they are delivered to the customer, on the **Load planning workbench** page, in the **Transportation** field, select **Hub consolidation**.</span></span> <span data-ttu-id="ace15-113">Cuando selecciona el concentrador correcto para cada carga, las cargas tendrán el concentrador como el destino de "entrega".</span><span class="sxs-lookup"><span data-stu-id="ace15-113">When you select the correct hub for each load, the loads will have the hub as the “drop off” destination.</span></span> <span data-ttu-id="ace15-114">También tendrá dos "líneas de solicitud de transporte" en la sección **Oferta y demanda** de la página **Área de trabajo de planificación de la carga**.</span><span class="sxs-lookup"><span data-stu-id="ace15-114">You will also have two “transportation request lines” in the **Supply and Demand** section on the **Load planning workbench** page.</span></span> <span data-ttu-id="ace15-115">A continuación, puede agregar estas dos líneas a una nueva carga.</span><span class="sxs-lookup"><span data-stu-id="ace15-115">You can then add these two lines to a new load.</span></span> <span data-ttu-id="ace15-116">Esta nueva carga tendrá ambas líneas de pedido de ventas y también tendrá el concentrador como la dirección de "recogida" y el cliente A como el destino de "entrega".</span><span class="sxs-lookup"><span data-stu-id="ace15-116">This new load will have both sales order lines, and will also have the hub as the “pick up” address and customer A as the “drop off” destination.</span></span> <span data-ttu-id="ace15-117">Las tres cargas estarán listas entonces para clasificarse y enrutarse como cualquier otra carga.</span><span class="sxs-lookup"><span data-stu-id="ace15-117">The three loads are then ready to be rated and routed like any other load.</span></span> <span data-ttu-id="ace15-118">Puede seleccionar cualquier transportista de envío que el sistema sugiera para cada carga.</span><span class="sxs-lookup"><span data-stu-id="ace15-118">You can select whatever shipping carrier the system suggests for each load.</span></span> <span data-ttu-id="ace15-119">[![Consolidación de centros](./media/hubconsol.jpg)](./media/hubconsol.jpg) También puede utilizar el mismo método para consolidar cargas para varios pedidos de transferencia.</span><span class="sxs-lookup"><span data-stu-id="ace15-119">[![Hub consolidation](./media/hubconsol.jpg)](./media/hubconsol.jpg) You can also use the same method to consolidate loads for multiple transfer orders.</span></span> <span data-ttu-id="ace15-120">En este caso, el cliente A del diagrama anterior es un almacén.</span><span class="sxs-lookup"><span data-stu-id="ace15-120">In this case, customer A in the preceding diagram is a warehouse.</span></span> <span data-ttu-id="ace15-121">De forma alternativa, puede consolidar cargas para varios pedidos de compra, donde se entregan las cargas de diferentes proveedores al mismo almacén.</span><span class="sxs-lookup"><span data-stu-id="ace15-121">Alternatively, you can consolidate loads for multiple purchase orders, where the loads are delivered from different vendors to the same warehouse.</span></span> <span data-ttu-id="ace15-122">Puede tener más de un concentrador de consolidación y consolidar en varios concentradores para más cargas que procedan de diferentes almacenes.</span><span class="sxs-lookup"><span data-stu-id="ace15-122">You can have more than one consolidation hub, and can consolidate in multiple hubs for more loads that come from different warehouses.</span></span> <span data-ttu-id="ace15-123">Tras crear las cargas básicas y utilizar la opción de consolidación de concentrador, crea las cargas nuevas mediante las líneas de solicitud de transporte consolidadas.</span><span class="sxs-lookup"><span data-stu-id="ace15-123">After you build your basic loads and use the hub consolidation option, you build the new loads by using the consolidated transportation request lines.</span></span> <span data-ttu-id="ace15-124">A continuación, clasifica y enruta las cargas.</span><span class="sxs-lookup"><span data-stu-id="ace15-124">You then rate and route your loads.</span></span>




