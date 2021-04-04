---
title: Marcado de inventario con Optimización de planificación
description: Este tema proporciona información sobre las opciones que están disponibles para marcar el inventario en pedidos firmes cuando usa Planning Optimization.
author: ChristianRytt
manager: tfehr
ms.date: 12/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: MpsIntegrationParameters, MpsFitAnalysis
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2020-12-02
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 7813f570afb0260e6740507c9504320c3e87be93
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5263359"
---
# <a name="inventory-marking-with-planning-optimization"></a><span data-ttu-id="e4104-103">Marcado de inventario con Optimización de planificación</span><span class="sxs-lookup"><span data-stu-id="e4104-103">Inventory marking with Planning Optimization</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="e4104-104">Este tema proporciona información sobre las opciones que están disponibles para marcar el inventario en pedidos firmes cuando usa Planning Optimization.</span><span class="sxs-lookup"><span data-stu-id="e4104-104">This topic provides information about the options that are available for marking inventory in firmed orders when you use Planning Optimization.</span></span>

<span data-ttu-id="e4104-105">*Calificación* se utiliza para vincular la oferta y la demanda.</span><span class="sxs-lookup"><span data-stu-id="e4104-105">*Marking* is used to link supply and demand.</span></span> <span data-ttu-id="e4104-106">Se parece a la *vinculación*, que indica cómo la planificación maestra espera cubrir la demanda.</span><span class="sxs-lookup"><span data-stu-id="e4104-106">It resembles *pegging*, which indicates how master planning expects to cover demand.</span></span> <span data-ttu-id="e4104-107">Desde el punto de vista de la planificación, la principal diferencia es que el marcado es más permanente que el pegging.</span><span class="sxs-lookup"><span data-stu-id="e4104-107">From a planning point of view, the main difference is that marking is more permanent than pegging.</span></span>

<span data-ttu-id="e4104-108">El marcado se introdujo para admitir escenarios de costos especiales para el primero en entrar, el primero en salir (FIFO) y el último en entrar, primero en salir (LIFO).</span><span class="sxs-lookup"><span data-stu-id="e4104-108">Marking was introduced to support special costing scenarios for first in, first out (FIFO) and last in, first out (LIFO).</span></span> <span data-ttu-id="e4104-109">Sin embargo, ahora también se usa para algunos escenarios sin costos.</span><span class="sxs-lookup"><span data-stu-id="e4104-109">However, it's now also used for some non-costing scenarios.</span></span> <span data-ttu-id="e4104-110">La marcación entre oferta y demanda es opcional y casi permanente.</span><span class="sxs-lookup"><span data-stu-id="e4104-110">Marking between supply and demand is optional and almost permanent.</span></span> <span data-ttu-id="e4104-111">El usuario puede eliminar manualmente la marca, o puede eliminarse ejecutando una explosión de línea de orden de venta donde **Eliminar marca** está seleccionada la opción.</span><span class="sxs-lookup"><span data-stu-id="e4104-111">Marking can be removed manually by a user, or it can be removed by running a sales order line explosion where the **Remove marking** option is selected.</span></span>

<span data-ttu-id="e4104-112">La vinculación se controla mediante la planificación maestra durante la cobertura para vincular la demanda con el suministro requerido.</span><span class="sxs-lookup"><span data-stu-id="e4104-112">Pegging is controlled by master planning during coverage to link demand with the required supply.</span></span> <span data-ttu-id="e4104-113">La trazabilidad se puede actualizar para cada ejecución de planificación para optimizar el suministro que se requiere para cubrir la demanda.</span><span class="sxs-lookup"><span data-stu-id="e4104-113">Pegging can be updated for each planning run to optimize the supply that is required to cover demand.</span></span> <span data-ttu-id="e4104-114">Cuando la planificación maestra actualiza la información de trazabilidad, respeta cualquier marca existente.</span><span class="sxs-lookup"><span data-stu-id="e4104-114">When master planning updates pegging information, it respects any existing marking.</span></span>

<span data-ttu-id="e4104-115">La vinculación comienza con la inclusión del marcado relevante, las reservas disponibles y las reservas en orden, en la siguiente secuencia:</span><span class="sxs-lookup"><span data-stu-id="e4104-115">Pegging starts by including relevant marking, on-hand reservations, and on-order reservations, in the following sequence:</span></span>

1. <span data-ttu-id="e4104-116">Marcado entre oferta y demanda</span><span class="sxs-lookup"><span data-stu-id="e4104-116">Marking between demand and supply</span></span>
1. <span data-ttu-id="e4104-117">Reservas disponibles</span><span class="sxs-lookup"><span data-stu-id="e4104-117">On-hand reservations</span></span>
1. <span data-ttu-id="e4104-118">Reservas bajo pedido</span><span class="sxs-lookup"><span data-stu-id="e4104-118">On-order reservations</span></span>

<span data-ttu-id="e4104-119">Cuando firme una orden planificada, el cuadro de diálogo **Reafirmante** proporciona un campo **Actualizar marcado** que se utiliza para configurar las opciones de marcado para los pedidos que se crean durante el endurecimiento.</span><span class="sxs-lookup"><span data-stu-id="e4104-119">When you firm a planned order, the **Firming** dialog box provides an **Update marking** field that you use to set marking options for the orders that are created during firming.</span></span> <span data-ttu-id="e4104-120">Seleccione uno de los siguientes valores:</span><span class="sxs-lookup"><span data-stu-id="e4104-120">Select one of the following values:</span></span>

- <span data-ttu-id="e4104-121">**No** - No se aplica marcado de inventario.</span><span class="sxs-lookup"><span data-stu-id="e4104-121">**No** – No inventory marking is applied.</span></span>
- <span data-ttu-id="e4104-122">**Estándar** – El marcado de inventarios se actualiza de acuerdo con el diagrama de árbol:</span><span class="sxs-lookup"><span data-stu-id="e4104-122">**Standard** – Inventory marking is updated according to the pegging.</span></span> <span data-ttu-id="e4104-123">Un pedido de requisitos (bajo demanda) está marcado en función de un pedido de entrega (suministro).</span><span class="sxs-lookup"><span data-stu-id="e4104-123">A requirement order (demand) is marked against a fulfillment order (supply).</span></span> <span data-ttu-id="e4104-124">Si queda alguna cantidad en el pedido de cumplimiento, no se marca y la información de referencia se deja en blanco.</span><span class="sxs-lookup"><span data-stu-id="e4104-124">If some quantity remains on the fulfillment order, it isn't marked, and the reference information is left blank.</span></span> <span data-ttu-id="e4104-125">Por ejemplo, si una orden de venta de 100 ea está vinculada a una orden de compra de 150 ea, la información de referencia se asignará solo a la orden de venta.</span><span class="sxs-lookup"><span data-stu-id="e4104-125">For example, if a sales order for 100 ea is pegged against a purchase order for 150 ea, reference information will be assigned only to the sales order.</span></span>
- <span data-ttu-id="e4104-126">**Extendido** – : el pedido de requisitos (demanda) y el pedido de cumplimiento (suministro) se marcan, independientemente de si queda alguna cantidad en el pedido de cumplimiento.</span><span class="sxs-lookup"><span data-stu-id="e4104-126">**Extended** – Both the requirement order (demand) and the fulfillment order (supply) are marked, regardless of any quantity that remains on the fulfillment order.</span></span> <span data-ttu-id="e4104-127">Por ejemplo, si una orden de venta de 100 ea está vinculada a una orden de compra de 150 ea, la información de referencia se asignará a la orden de venta y a la orden de compra.</span><span class="sxs-lookup"><span data-stu-id="e4104-127">For example, if a sales order for 100 ea is pegged against a purchase order for 150 ea, reference information will be assigned to both the sales order and the purchase order.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]