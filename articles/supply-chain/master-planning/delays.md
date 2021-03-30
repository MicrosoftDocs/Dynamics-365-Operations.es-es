---
title: Retrasos
description: Este tema proporciona información acerca de fechas retrasadas en la planificación maestra. Una fecha retrasada es una fecha de vencimiento realista que una transacción recibe si la fecha de cumplimiento más temprana que la planificación maestra calcula es posterior a la fecha solicitada.
author: roxanadiaconu
manager: tfehr
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 195a966ea8baee7783af84ec5f178d7c35ee5cea
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5207096"
---
# <a name="delays"></a><span data-ttu-id="4f0d2-104">Retrasos</span><span class="sxs-lookup"><span data-stu-id="4f0d2-104">Delays</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4f0d2-105">Este tema proporciona información acerca de fechas retrasadas en la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-105">This topic provides information about delayed dates in master planning.</span></span> <span data-ttu-id="4f0d2-106">Una fecha retrasada es una fecha de vencimiento realista que una transacción recibe si la fecha de cumplimiento más temprana que la planificación maestra calcula es posterior a la fecha solicitada.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-106">A delayed date is a realistic due date that a transaction receives if the earliest fulfillment date that master planning calculates is later than the requested date.</span></span>

<span data-ttu-id="4f0d2-107">La planificación maestra puede calcular la fecha más temprana de cumplimiento para una transacción según los plazos, la disponibilidad de material, la disponibilidad de capacidad y los diferentes parámetros de planificación.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-107">Master planning can calculate the earliest fulfillment date for a transaction, based on lead times, material availability, capacity availability, and various planning parameters.</span></span> 

<span data-ttu-id="4f0d2-108">Si la planificación maestra calcula una fecha de pedido anterior a la fecha en curso, el pedido no se puede satisfacer a tiempo.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-108">If master planning calculates an order date that precedes the current date, the order can't be fulfilled on time.</span></span> <span data-ttu-id="4f0d2-109">Por tanto, se retrasa el pedido.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-109">Therefore, the order is delayed.</span></span> <span data-ttu-id="4f0d2-110">En este caso, la planificación maestra adelanta la planificación del pedido a partir de la fecha en uso e incluye plazos.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-110">In this case, master planning forward-plans the order from the current date and includes lead times.</span></span> <span data-ttu-id="4f0d2-111">Estos plazos empiezan con cualquier artículo componente de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-111">These lead times start with any lower-level component items.</span></span> <span data-ttu-id="4f0d2-112">El pedido recibe a continuación una fecha retrasada.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-112">The order then receives a delayed date.</span></span> <span data-ttu-id="4f0d2-113">La fecha retrasada es una fecha de vencimiento real en función de los datos actuales.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-113">A delayed date is a realistic due date, based on the current data.</span></span> <span data-ttu-id="4f0d2-114">La planificación maestra también calcula el número de días de retraso.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-114">Master planning also calculates the number of delay days.</span></span> 

<span data-ttu-id="4f0d2-115">En algunos casos, es posible optar por no calcular retrasos, como cuando los usuarios saben que pueden acelerar los plazos seleccionando modos de entrega alternativos.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-115">In some situations, you might choose not to calculate delays, such as when users know that they can expedite lead times by selecting alternative modes of delivery.</span></span> 

<span data-ttu-id="4f0d2-116">Puede configurar cómo calcular los retrasos para un grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-116">You can configure how delays are calculated for a coverage group.</span></span> <span data-ttu-id="4f0d2-117">Más adelante puede adjuntar el grupo de cobertura a un artículo.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-117">You can then attach the coverage group to an item later.</span></span> 

<span data-ttu-id="4f0d2-118">En la página **Parámetros de planificación maestra** puede establecer el momento de inicio para el cálculo de retrasos.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-118">On the **Master planning parameters** page, you can set the start time for the calculation of delays.</span></span> <span data-ttu-id="4f0d2-119">Si se satisface un pedido después de este momento, entonces se añade un retraso de un día a la fecha de retraso del pedido.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-119">If an order is fulfilled after this time, a delay of one day is added to the delay date of the order.</span></span> 

> [!NOTE]
> <span data-ttu-id="4f0d2-120">En versiones anteriores, los retrasos calculados se conocían como *mensajes de futuros*, la fecha retrasada como *fecha de futuros* y las transacciones retrasadas como *transacciones establecidas en una fecha futura*.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-120">In earlier versions, calculated delays were known as *futures messages*, the delayed date was known as the *futures date*, and a delayed transaction was referred to as *a transaction that was future set*.</span></span>

## <a name="limited-delays-in-production-setup-with-multiple-bom-levels"></a><span data-ttu-id="4f0d2-121">Demoras limitadas en la configuración de producción con múltiples niveles de lista de materiales</span><span class="sxs-lookup"><span data-stu-id="4f0d2-121">Limited delays in production setup with multiple BOM levels</span></span>
<span data-ttu-id="4f0d2-122">Cuando trabaja con retrasos en una configuración de producción que tiene varios niveles de lista de materiales, es importante tener en cuenta que solo los artículos directamente encima del artículo (en la estructura de la lista de materiales) que causan el retraso, se actualizarán con un retraso como parte de la ejecución de la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-122">When you work with delays in a production setup that has multiple BOM levels, it is important to note that only the items directly above the item (in the BOM structure) causing the delay, will be updated with a delay as part of the master planning run.</span></span> <span data-ttu-id="4f0d2-123">Otros elementos en la estructura de la lista de materiales no aplicarán el retraso hasta la primera ejecución de planificación maestra, cuando se apruebe o firme el pedido planificado para el nivel superior.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-123">Other items in the BOM structure will not get the delay applied until the first master planning run, when the planned order for the top level is approved or firmed.</span></span> 

<span data-ttu-id="4f0d2-124">Para evitar esta limitación conocida, las órdenes de producción en la parte superior de la estructura de la lista de materiales con demoras pueden aprobarse (o reafirmarse) antes de la próxima ejecución de planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-124">To work around this known limitation, the production orders on the top of the BOM structure with delays can be approved (or firmed) prior to the next master planning run.</span></span> <span data-ttu-id="4f0d2-125">De esta forma, se mantendrá el retraso del pedido de producción planificado aprobado retrasado y todos los componentes subyacentes se actualizarán en consecuencia.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-125">This way the delay from the delayed approved planned production order will be kept and all underlying components will be updated accordingly.</span></span>
<span data-ttu-id="4f0d2-126">Los mensajes de acción también se pueden usar para identificar órdenes planificadas que se pueden mover a una fecha posterior, debido a otros retrasos en la estructura de la lista de materiales.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-126">Action messages can also be used to identify planned orders that can be moved to a later date, due to other delays in the BOM structure.</span></span>

## <a name="desired-date"></a><span data-ttu-id="4f0d2-127">Fecha deseada</span><span class="sxs-lookup"><span data-stu-id="4f0d2-127">Desired date</span></span>

<span data-ttu-id="4f0d2-128">En la página **Pedido planificado** , en la pestaña **Retrasos** está la **Fecha deseada** para el pedido planificado.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-128">On the **Planned order** page, under the **Delays** tab is the **Desired date** for the planned order.</span></span> <span data-ttu-id="4f0d2-129">La fecha deseada de un pedido planificado es la fecha base para los retrasos, que es una fecha calculada igual a la **Fecha solicitada** calculada a partir del **Requisito neto**.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-129">The desired date of a planned order is the base date for delays, which is a computed date that equals the **Requested date** calculated from the **Net Requirement**.</span></span> <span data-ttu-id="4f0d2-130">Si el pedido planificado es una línea de L. MAT, una línea de producción o una línea kanban, la fecha deseada se basa en **Fecha de requisito** y la fecha deseada no se mostrará en la página **Pedido planificado**.</span><span class="sxs-lookup"><span data-stu-id="4f0d2-130">If the planned order is a BOM line, production line or kanban line, the desired date is based on the **Requirement date** and the desired date will not be shown on the **Planned order** page.</span></span>

<a name="additional-resources"></a><span data-ttu-id="4f0d2-131">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="4f0d2-131">Additional resources</span></span>
--------

[<span data-ttu-id="4f0d2-132">Configuración de cobertura</span><span class="sxs-lookup"><span data-stu-id="4f0d2-132">Coverage settings</span></span>](coverage-settings.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]