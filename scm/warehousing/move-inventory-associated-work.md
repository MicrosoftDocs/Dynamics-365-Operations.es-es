---
title: "Movimiento de inventario con trabajo asociado en Gestión de almacenes"
description: "Este tema describe cómo configurar y aplicar la confirmación el picking de pieza desde un dispositivo móvil."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 08c38aada355583c5a6872f75b57db95d9b81786
ms.openlocfilehash: 4b8d320a6faae24fb3d8c6d3952e3263b97f52c1
ms.contentlocale: es-es
ms.lasthandoff: 07/18/2017

---

# <a name="movement-of-inventory-with-associated-work-in-warehouse-management"></a><span data-ttu-id="58da2-103">Movimiento de inventario con trabajo asociado en Gestión de almacenes</span><span class="sxs-lookup"><span data-stu-id="58da2-103">Movement of inventory with associated work in Warehouse management</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="58da2-104">Si usa el movimiento de inventario, puede decidir que trabajadores de almacén podrán mover el inventario reservado.</span><span class="sxs-lookup"><span data-stu-id="58da2-104">Using movement of inventory, you can decide which warehouse workers are allowed to move reserved inventory.</span></span> <span data-ttu-id="58da2-105">Este formulario proporciona una flexibilidad en los almacenes regulados donde puede decidir no permitir que un trabajador elija una nueva ubicación de picking para seleccionar trabajo que ya se creó.</span><span class="sxs-lookup"><span data-stu-id="58da2-105">This provides a flexibility in regulated warehouses where you can decide to not allow a worker to choose a new pick location for pick work that is already created.</span></span> <span data-ttu-id="58da2-106">También permite que un administrador de almacén controle qué capacidades deben algunos trabajadores menos experimentados.</span><span class="sxs-lookup"><span data-stu-id="58da2-106">It also allows a warehouse manager to control which capabilities some less experienced workers should have.</span></span>

<span data-ttu-id="58da2-107">La flexibilidad para administrar las operaciones diarias de trabajadores de almacén puede ser útil en escenarios como estos:</span><span class="sxs-lookup"><span data-stu-id="58da2-107">The flexibility to manage the daily operations of warehouse workers can be useful in scenarios such as these:</span></span>

## <a name="scenario-1"></a><span data-ttu-id="58da2-108">Escenario 1</span><span class="sxs-lookup"><span data-stu-id="58da2-108">Scenario 1</span></span>
<span data-ttu-id="58da2-109">Una empresa tiene un área de recepción relativamente pequeña y está congestionada con pallets y cajas que deben colocarse.</span><span class="sxs-lookup"><span data-stu-id="58da2-109">A company has a relatively small receiving area, and it’s congested with pallets and boxes awaiting put away.</span></span> <span data-ttu-id="58da2-110">Un envío grande se espera en este día, por lo que el vendedor receptor decide desalojar el área de recepción moviendo algunos pallets a una área provisional de entrada secundaria.</span><span class="sxs-lookup"><span data-stu-id="58da2-110">A large shipment is expected on the current day, so the receiving clerk decides to clear up the receiving area by moving some of the pallets to a secondary inbound staging area.</span></span>

## <a name="scenario-2"></a><span data-ttu-id="58da2-111">Escenario 2</span><span class="sxs-lookup"><span data-stu-id="58da2-111">Scenario 2</span></span>
<span data-ttu-id="58da2-112">Un trabajador experimentado de almacén ve una oportunidad en un almacén de consolidar artículos en una ubicación en lugar de dividirlos tenerlos en 3 ubicaciones próximas con menor cantidad en cada una.</span><span class="sxs-lookup"><span data-stu-id="58da2-112">An experienced warehouse worker notices an opportunity in a warehouse to consolidate items in one location instead of having them divided across 3 nearby locations with little quantity on each.</span></span> <span data-ttu-id="58da2-113">El trabajador desea consolidar la cantidad moviendo artículos desde cada una de las ubicaciones a la misma ubicación y en la misma matrícula.</span><span class="sxs-lookup"><span data-stu-id="58da2-113">The worker wants to consolidate the quantity by moving items from each of these locations into the same location and onto the same license plate.</span></span>

## <a name="scenario-3"></a><span data-ttu-id="58da2-114">Escenario 3</span><span class="sxs-lookup"><span data-stu-id="58da2-114">Scenario 3</span></span>
<span data-ttu-id="58da2-115">Un pallet está en espera de envío en una ubicación provisional, como STAGE01, que está cerca de BAYDOOR01.</span><span class="sxs-lookup"><span data-stu-id="58da2-115">A pallet is awaiting shipment in a staging location, such as STAGE01, which is near BAYDOOR01.</span></span> <span data-ttu-id="58da2-116">Sin embargo, debido a un cambio de planes el camión se programa para su llegada a BAYDOOR04.</span><span class="sxs-lookup"><span data-stu-id="58da2-116">However, due to a change of plans the truck is scheduled to arrive at BAYDOOR04.</span></span> <span data-ttu-id="58da2-117">El encargado de los envíos lo sabe y necesita garantizar que el camión no tenga que esperar para cargarse en STAGE01.</span><span class="sxs-lookup"><span data-stu-id="58da2-117">The shipping clerk is aware of this and needs to ensure that the truck does not have to wait to be loaded from STAGE01.</span></span> <span data-ttu-id="58da2-118">El encargado de los envíos decide mover los artículos en este envío desde STAGE01 a STAGE04, que está más cerca del nuevo destino.</span><span class="sxs-lookup"><span data-stu-id="58da2-118">The shipping clerk decides to move the items in that shipment from STAGE01 to STAGE04, which is closer to the new destination.</span></span>

### <a name="current-limitations"></a><span data-ttu-id="58da2-119">Limitaciones actuales</span><span class="sxs-lookup"><span data-stu-id="58da2-119">Current limitations</span></span>

<span data-ttu-id="58da2-120">Las reservas de trabajo que puede mover se limitan al pedido de ventas, emisión de pedidos de transferencia, recibo de pedidos de transferencia, pedido de compra y trabajo de reabastecimiento.</span><span class="sxs-lookup"><span data-stu-id="58da2-120">The work reservations that you can move are limited to Sales order, Transfer order issue, Transfer order receipt, Purchase order, and Replenishment work.</span></span>

<span data-ttu-id="58da2-121">Los artículos móviles se limitan para evitar la división de las líneas de trabajo.</span><span class="sxs-lookup"><span data-stu-id="58da2-121">Moving items is restricted to prevent splitting of work lines.</span></span> <span data-ttu-id="58da2-122">Esto significa que si tiene una línea de trabajo para 100 piezas de artículos A en la ubicación Loc1, no podrá mover sólo 30 piezas de artículos A de ahí a otra ubicación.</span><span class="sxs-lookup"><span data-stu-id="58da2-122">This means that if you have a work line for 100 pcs of item A from location Loc1, you won’t be able to move only 30 pcs of item A from there to another location.</span></span> <span data-ttu-id="58da2-123">Esto conduciría a una división de la línea de trabajo existente a 30 y 70, ya que las ubicaciones son ahora diferentes.</span><span class="sxs-lookup"><span data-stu-id="58da2-123">This would lead to a split of the existing work line to 30 and 70, because the locations are now different.</span></span>

<span data-ttu-id="58da2-124">Para las situaciones provisionales, donde la matrícula desde la que mueve la mercancía o la matrícula a la que mueve la mercancías se establecen como Destino LP para un pedido de trabajo, solo se perite el movimiento de LP completo para no interrumpir el Destino LP.</span><span class="sxs-lookup"><span data-stu-id="58da2-124">For staging scenarios, where the license plate you move the goods from or the license plate you move the goods to, are set as a Target LP for a work order, only movement of the entire LP is allowed, so as not to break up the Target LP.</span></span>
<span data-ttu-id="58da2-125">Solo el movimiento ad hoc se admite actualmente.</span><span class="sxs-lookup"><span data-stu-id="58da2-125">Only the ad hoc movement is currently supported.</span></span> <span data-ttu-id="58da2-126">Esto significa que no podrá mover el inventario reservado a través del movimiento por los elementos de menú del dispositivo móvil de la plantilla.</span><span class="sxs-lookup"><span data-stu-id="58da2-126">That means that you will not be able to move reserved inventory through the movement by template mobile device menu items.</span></span>

### <a name="set-up-the-permission-to-move-reserved-inventory-for-individual-workers"></a><span data-ttu-id="58da2-127">Configure el permiso para mover el inventario reservado para trabajadores individuales</span><span class="sxs-lookup"><span data-stu-id="58da2-127">Set up the permission to move reserved inventory for individual workers</span></span>

<span data-ttu-id="58da2-128">Para el trabajador tenga permitido mover el inventario reservado, seleccione la casilla de verificación **Permitir el movimiento de inventario con trabajo asociado** en **Gestión de almacenes** > **Configuración** > **Trabajador**.</span><span class="sxs-lookup"><span data-stu-id="58da2-128">For the worker who should be allowed to move reserved inventory, select the **Allow movement of inventory with work associated** check box under **Warehouse management** > **Setup** > **Worker**.</span></span>  

### <a name="backported"></a><span data-ttu-id="58da2-129">Transporte de paquetes entre versiones</span><span class="sxs-lookup"><span data-stu-id="58da2-129">Backported</span></span>

<span data-ttu-id="58da2-130">Esta función también permite el transporte de paquetes entre versiones a Microsoft Dynamics AX 2012 R3 y estará disponible como parte de CU12.</span><span class="sxs-lookup"><span data-stu-id="58da2-130">This feature has also been back-ported to Microsoft Dynamics AX 2012 R3 and will be available as part of CU12.</span></span>
<span data-ttu-id="58da2-131">También puede descargase de forma individual con el KB número 3192548.</span><span class="sxs-lookup"><span data-stu-id="58da2-131">It can also be downloaded individually through KB number 3192548.</span></span> 


