---
title: Planificación de empresas vinculadas
description: Este tema describe la planificación de empresas vinculadas y explica cómo configurar la planificación de empresas vinculadas con Planning Optimization en Microsoft Dynamics 365 Supply Chain Management.
author: ChristianRytt
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 5c9ab724034a9bb40cfe155b748a0c7e25978add
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833362"
---
# <a name="intercompany-planning"></a><span data-ttu-id="d6513-103">Planificación de empresas vinculadas</span><span class="sxs-lookup"><span data-stu-id="d6513-103">Intercompany planning</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d6513-104">Para algunas organizaciones, las operaciones de logística dependen de otras entidades legales (empresas) en la organización.</span><span class="sxs-lookup"><span data-stu-id="d6513-104">For some organizations, logistics operations depend on other legal entities (companies) in the organization.</span></span> <span data-ttu-id="d6513-105">Estas operaciones se manejan mediante compras y ventas entre empresas, porque cada entidad jurídica tiene un plan de cuentas independiente.</span><span class="sxs-lookup"><span data-stu-id="d6513-105">These operations are handled by using intercompany sales and purchases, because each legal entity has a separate chart of accounts.</span></span>

<span data-ttu-id="d6513-106">Este tema describe la planificación de empresas vinculadas y explica cómo configurar la planificación de empresas vinculadas con Planning Optimization en Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="d6513-106">This topic describes intercompany planning and explains how to configure intercompany planning with Planning Optimization in Microsoft Dynamics 365 Supply Chain Management.</span></span>

<span data-ttu-id="d6513-107">Este tema utiliza los siguientes términos importantes de empresas vinculadas:</span><span class="sxs-lookup"><span data-stu-id="d6513-107">This topic uses the following important intercompany terms:</span></span>

- <span data-ttu-id="d6513-108">**Río arriba** - Una referencia relativa en una empresa o cadena de suministro.</span><span class="sxs-lookup"><span data-stu-id="d6513-108">**Upstream** – A relative reference in a firm or supply chain.</span></span> <span data-ttu-id="d6513-109">Indica movimiento en la dirección del proveedor de materia prima.</span><span class="sxs-lookup"><span data-stu-id="d6513-109">It indicates movement in the direction of the raw material supplier.</span></span>
- <span data-ttu-id="d6513-110">**Flujo descendente** - Una referencia relativa en una empresa o cadena de suministro.</span><span class="sxs-lookup"><span data-stu-id="d6513-110">**Downstream** – A relative reference in a firm or supply chain.</span></span> <span data-ttu-id="d6513-111">Indica movimiento en la dirección del cliente.</span><span class="sxs-lookup"><span data-stu-id="d6513-111">It indicates movement in the direction of the customer.</span></span>
- <span data-ttu-id="d6513-112">**Demanda intercompañía planificada** - Demanda planificada de un producto en una empresa, basada en la demanda planificada del producto de una empresa downstream.</span><span class="sxs-lookup"><span data-stu-id="d6513-112">**Planned intercompany demand** – Planned demand for a product in a company, based on planned demand for the product from a downstream company.</span></span>

<span data-ttu-id="d6513-113">En la planificación maestra, un plan en una empresa puede incluir la demanda intercompañía planificada que está relacionada con los pedidos planificados de un plan en otra empresa.</span><span class="sxs-lookup"><span data-stu-id="d6513-113">In master planning, a plan in one company can include planned intercompany demand that is related to planned orders from a plan in another company.</span></span> <span data-ttu-id="d6513-114">Esta capacidad es útil porque proporciona una visibilidad completa de los pedidos planificados en todas las empresas.</span><span class="sxs-lookup"><span data-stu-id="d6513-114">This capability is useful, because it provides full visibility into planned orders across companies.</span></span> <span data-ttu-id="d6513-115">También garantiza que se creen todas las órdenes de suministro planificadas necesarias, pero sin requerir que las órdenes planificadas se firmen para la demanda de empresas vinculadas.</span><span class="sxs-lookup"><span data-stu-id="d6513-115">It also ensures that all required planned supply orders are created, but without requiring that planned orders be firmed for the intercompany demand.</span></span>

<span data-ttu-id="d6513-116">Si ejecuta la planificación maestra desde un plan maestro que incluye la demanda posterior planificada, las órdenes de compra planificadas de los proveedores de empresas vinculadas relacionados se incluirán en el plan como demanda.</span><span class="sxs-lookup"><span data-stu-id="d6513-116">If you run master planning from a master plan that includes planned downstream demand, planned purchase orders from the related intercompany vendors will be included in the plan as demand.</span></span>

## <a name="required-setup"></a><span data-ttu-id="d6513-117">Configuración necesaria</span><span class="sxs-lookup"><span data-stu-id="d6513-117">Required setup</span></span>

<span data-ttu-id="d6513-118">Para utilizar la planificación de empresas vinculadas, debe preparar su sistema de la siguiente manera:</span><span class="sxs-lookup"><span data-stu-id="d6513-118">To use intercompany planning, you must prepare your system in the following way:</span></span>

1. <span data-ttu-id="d6513-119">Los productos relevantes deben ser lanzados en todas las empresas relevantes.</span><span class="sxs-lookup"><span data-stu-id="d6513-119">The relevant products must be released in all the relevant companies.</span></span> <span data-ttu-id="d6513-120">Para obtener más información, consulte [Configurar y usar el comercio de empresas vinculadas en Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) en Microsoft Learn.</span><span class="sxs-lookup"><span data-stu-id="d6513-120">For more information, see [Configure and use intercompany trade in Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) on Microsoft Learn.</span></span>
1. <span data-ttu-id="d6513-121">La demanda aguas abajo debe cubrirse mediante compras a un proveedor que tenga una relación intercompañía con la compañía aguas arriba y dimensiones de inventario predeterminadas relevantes (sitio y almacén) en el cliente.</span><span class="sxs-lookup"><span data-stu-id="d6513-121">Downstream demand must be covered by purchases from a vendor that has an intercompany relation to the upstream company and relevant default inventory dimensions (site and warehouse) on the customer.</span></span> <span data-ttu-id="d6513-122">Para obtener más información, consulte [Configurar y usar el comercio de empresas vinculadas en Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) en Microsoft Learn.</span><span class="sxs-lookup"><span data-stu-id="d6513-122">For more information, see [Configure and use intercompany trade in Dynamics 365 Supply Chain Management ](https://docs.microsoft.com/learn/modules/configure-use-intercompany-trade-dyn365-supply-chain-mgmt/) on Microsoft Learn.</span></span>
1. <span data-ttu-id="d6513-123">El plan maestro en la empresa aguas arriba debe incluir la demanda aguas abajo planificada, y la compañía relevante y el plan maestro deben especificarse en los planes aguas abajo.</span><span class="sxs-lookup"><span data-stu-id="d6513-123">The master plan in the upstream company must include planned downstream demand, and the relevant company and master plan must be specified in the downstream plans.</span></span>

## <a name="include-planned-downstream-demand"></a><span data-ttu-id="d6513-124">Incluir demanda planificada descendente</span><span class="sxs-lookup"><span data-stu-id="d6513-124">Include planned downstream demand</span></span>

<span data-ttu-id="d6513-125">Siga estos pasos para configurar su plan maestro de modo que incluya la demanda descendente planificada.</span><span class="sxs-lookup"><span data-stu-id="d6513-125">Follow these steps to configure your master plan so that it includes planned downstream demand.</span></span>

1. <span data-ttu-id="d6513-126">Vaya a **Planificación maestra \> Configurar \> Planes \> Planes maestros**.</span><span class="sxs-lookup"><span data-stu-id="d6513-126">Go to **Master planning \> Setup \> Plans \> Master plans**.</span></span>
1. <span data-ttu-id="d6513-127">Seleccionar o crear un plan maestro.</span><span class="sxs-lookup"><span data-stu-id="d6513-127">Select or create a master plan.</span></span>
1. <span data-ttu-id="d6513-128">En la ficha desplegable **Planificación de empresas vinculadas**, establezca los siguientes campos:</span><span class="sxs-lookup"><span data-stu-id="d6513-128">On the **Intercompany planning** FastTab, set the following fields:</span></span>

    - <span data-ttu-id="d6513-129">**Incluya la demanda aguas abajo planificada** - Establezca esta opción en *Sí* para habilitar la planificación entre empresas para el plan maestro.</span><span class="sxs-lookup"><span data-stu-id="d6513-129">**Include planned downstream demand** – Set this option to *Yes* to enable intercompany planning for the master plan.</span></span>
    - <span data-ttu-id="d6513-130">**Planes descendentes** - Si configura la opción **Incluya la demanda aguas abajo planificada** en *Sí*, use la barra de herramientas y la cuadrícula para agregar los planes maestros deseados de otras empresas.</span><span class="sxs-lookup"><span data-stu-id="d6513-130">**Downstream plans** – If you set the **Include planned downstream demand** option to *Yes*, use the toolbar and grid to add the desired master plans from other companies.</span></span>

## <a name="peg-across-companies-by-using-multilevel-pegging"></a><span data-ttu-id="d6513-131">Vinculación entre empresas mediante vinculación multinivel</span><span class="sxs-lookup"><span data-stu-id="d6513-131">Peg across companies by using multilevel pegging</span></span>

<span data-ttu-id="d6513-132">En la vinculación multinivel, puede ver la vinculación entre empresas para ver la fuente inicial de demanda que está siendo cubierta por una oferta.</span><span class="sxs-lookup"><span data-stu-id="d6513-132">In multilevel pegging, you can view pegging across companies to see the initial source of demand that is being covered by a supply.</span></span>

<span data-ttu-id="d6513-133">Para ver información de trazabilidad multinivel, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="d6513-133">To view multilevel pegging information, follow these steps.</span></span>

1. <span data-ttu-id="d6513-134">Vaya a **Planificación maestra \> Planificación maestra \> Pedidos planificados**.</span><span class="sxs-lookup"><span data-stu-id="d6513-134">Go to **Master planning \> Master planning \> Planned orders**.</span></span>
1. <span data-ttu-id="d6513-135">Seleccione o abra un pedido planificado.</span><span class="sxs-lookup"><span data-stu-id="d6513-135">Select or open a planned order.</span></span>
1. <span data-ttu-id="d6513-136">En el panel de acciones, en la ficha **Ver**, en el grupo **Requisitos**, seleccione **Diagrama de árbol multinivel**.</span><span class="sxs-lookup"><span data-stu-id="d6513-136">On the Action Pane, on the **View** tab, in the **Requirements** group, select **Multilevel pegging**.</span></span>

### <a name="intercompany-example-that-involves-two-companies"></a><span data-ttu-id="d6513-137">Ejemplo de intercompañía que involucra a dos empresas</span><span class="sxs-lookup"><span data-stu-id="d6513-137">Intercompany example that involves two companies</span></span>

<span data-ttu-id="d6513-138">Para este ejemplo, se crea una orden de producción planificada en la empresa USMF para cubrir una orden de venta en la empresa DEMF.</span><span class="sxs-lookup"><span data-stu-id="d6513-138">For this example, a planned production order is created in the USMF company to cover a sales order in the DEMF company.</span></span> <span data-ttu-id="d6513-139">En USMF, la demanda directa es la demanda intercompañía planificada.</span><span class="sxs-lookup"><span data-stu-id="d6513-139">In USMF, the direct demand is planned intercompany demand.</span></span> <span data-ttu-id="d6513-140">Para que esta demanda aparezca en USMF, la planificación maestra se ejecuta primero en DEMF y luego en USMF.</span><span class="sxs-lookup"><span data-stu-id="d6513-140">To make this demand appear in USMF, master planning is run first in DEMF and then in USMF.</span></span>

<span data-ttu-id="d6513-141">La siguiente ilustración muestra cómo podría aparecer este ejemplo en la página **Vinculación multinivel** de la orden de producción planificada.</span><span class="sxs-lookup"><span data-stu-id="d6513-141">The following illustration shows how this example might appear on the **Multilevel pegging** page for the planned production order.</span></span>

![Ejemplo de intercompañía que involucra a dos empresas](media/IntercompanyPlanning1.png)

### <a name="intercompany-example-that-involves-three-companies"></a><span data-ttu-id="d6513-143">Ejemplo de intercompañía que involucra a tres empresas</span><span class="sxs-lookup"><span data-stu-id="d6513-143">Intercompany example that involves three companies</span></span>

<span data-ttu-id="d6513-144">Para este ejemplo, se crea una orden de compra planificada en la empresa USMF para cubrir una orden de venta en la empresa FRRT.</span><span class="sxs-lookup"><span data-stu-id="d6513-144">For this example, a planned purchase order is created in the USMF company to cover a sales order in the FRRT company.</span></span> <span data-ttu-id="d6513-145">En las empresas DEMF y USMF, la demanda directa es la demanda intercompañía planificada.</span><span class="sxs-lookup"><span data-stu-id="d6513-145">In the DEMF and USMF companies, the direct demand is planned intercompany demand.</span></span> <span data-ttu-id="d6513-146">Para que esta demanda aparezca en USMF, la planificación maestra se ejecuta primero en FRRT y finalmente en DEMF.</span><span class="sxs-lookup"><span data-stu-id="d6513-146">To make this demand appear in USMF, master planning is run first in FRRT, then in DEMF, and finally in USMF.</span></span>

<span data-ttu-id="d6513-147">La siguiente ilustración muestra cómo podría aparecer este ejemplo en la página **Vinculación multinivel** de la orden de producción planificada.</span><span class="sxs-lookup"><span data-stu-id="d6513-147">The following illustration shows how this example might appear on the **Multilevel pegging** page for the planned production order.</span></span>

![Ejemplo de intercompañía que involucra a tres empresas](media/IntercompanyPlanning2.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]