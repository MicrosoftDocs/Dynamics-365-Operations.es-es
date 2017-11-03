---
title: Retrasos
description: "Este artículo proporciona información acerca de fechas retrasadas en la planificación maestra. Una fecha retrasada es una fecha de vencimiento realista que una transacción recibe si la fecha de cumplimiento más temprana que la planificación maestra calcula es posterior a la fecha solicitada."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: ed0df1abbf4f70ea70046eff7b91a25fdd59016c
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="delays"></a><span data-ttu-id="c9298-104">Retrasos</span><span class="sxs-lookup"><span data-stu-id="c9298-104">Delays</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="c9298-105">Este artículo proporciona información acerca de fechas retrasadas en la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="c9298-105">This article provides information about delayed dates in master planning.</span></span> <span data-ttu-id="c9298-106">Una fecha retrasada es una fecha de vencimiento realista que una transacción recibe si la fecha de cumplimiento más temprana que la planificación maestra calcula es posterior a la fecha solicitada.</span><span class="sxs-lookup"><span data-stu-id="c9298-106">A delayed date is a realistic due date that a transaction receives if the earliest fulfillment date that master planning calculates is later than the requested date.</span></span>

<span data-ttu-id="c9298-107">La planificación maestra puede calcular la fecha más temprana de cumplimiento para una transacción según los plazos, la disponibilidad de material, la disponibilidad de capacidad y los diferentes parámetros de planificación.</span><span class="sxs-lookup"><span data-stu-id="c9298-107">Master planning can calculate the earliest fulfillment date for a transaction, based on lead times, material availability, capacity availability, and various planning parameters.</span></span> 

<span data-ttu-id="c9298-108">Si la planificación maestra calcula una fecha de pedido anterior a la fecha en curso, el pedido no se puede satisfacer a tiempo.</span><span class="sxs-lookup"><span data-stu-id="c9298-108">If master planning calculates an order date that precedes the current date, the order can't be fulfilled on time.</span></span> <span data-ttu-id="c9298-109">Por tanto, se retrasa el pedido.</span><span class="sxs-lookup"><span data-stu-id="c9298-109">Therefore, the order is delayed.</span></span> <span data-ttu-id="c9298-110">En este caso, la planificación maestra adelanta la planificación del pedido a partir de la fecha en uso e incluye plazos.</span><span class="sxs-lookup"><span data-stu-id="c9298-110">In this case, master planning forward-plans the order from the current date and includes lead times.</span></span> <span data-ttu-id="c9298-111">Estos plazos empiezan con cualquier artículo componente de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="c9298-111">These lead times start with any lower-level component items.</span></span> <span data-ttu-id="c9298-112">El pedido recibe a continuación una fecha retrasada.</span><span class="sxs-lookup"><span data-stu-id="c9298-112">The order then receives a delayed date.</span></span> <span data-ttu-id="c9298-113">La fecha retrasada es una fecha de vencimiento real en función de los datos actuales.</span><span class="sxs-lookup"><span data-stu-id="c9298-113">A delayed date is a realistic due date, based on the current data.</span></span> <span data-ttu-id="c9298-114">La planificación maestra también calcula el número de días de retraso.</span><span class="sxs-lookup"><span data-stu-id="c9298-114">Master planning also calculates the number of delay days.</span></span> 

<span data-ttu-id="c9298-115">En algunos casos, es posible optar por no calcular retrasos, como cuando los usuarios saben que pueden acelerar los plazos seleccionando modos de entrega alternativos.</span><span class="sxs-lookup"><span data-stu-id="c9298-115">In some situations, you might choose not to calculate delays, such as when users know that they can expedite lead times by selecting alternative modes of delivery.</span></span> 

<span data-ttu-id="c9298-116">Puede configurar cómo calcular los retrasos para un grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="c9298-116">You can configure how delays are calculated for a coverage group.</span></span> <span data-ttu-id="c9298-117">Más adelante puede adjuntar el grupo de cobertura a un artículo.</span><span class="sxs-lookup"><span data-stu-id="c9298-117">You can then attach the coverage group to an item later.</span></span> 

<span data-ttu-id="c9298-118">En la página **Parámetros de planificación maestra** puede establecer el momento de inicio para el cálculo de retrasos.</span><span class="sxs-lookup"><span data-stu-id="c9298-118">On the **Master planning parameters** page, you can set the start time for the calculation of delays.</span></span> <span data-ttu-id="c9298-119">Si se satisface un pedido después de este momento, entonces se añade un retraso de un día a la fecha de retraso del pedido.</span><span class="sxs-lookup"><span data-stu-id="c9298-119">If an order is fulfilled after this time, a delay of one day is added to the delay date of the order.</span></span> 

<span data-ttu-id="c9298-120">**Nota:** en versiones anteriores, los retrasos calculados se conocían como *mensajes de futuros*, la fecha retrasada como *fecha de futuros* y las transacciones retrasadas como *transacciones establecidas en una fecha futura*.</span><span class="sxs-lookup"><span data-stu-id="c9298-120">**Note:** In earlier versions, calculated delays were known as *futures messages*, the delayed date was known as the *futures date*, and a delayed transaction was referred to as *a transaction that was future set*.</span></span>

<a name="see-also"></a><span data-ttu-id="c9298-121">Consulte también</span><span class="sxs-lookup"><span data-stu-id="c9298-121">See also</span></span>
--------

[<span data-ttu-id="c9298-122">Configuración de cobertura</span><span class="sxs-lookup"><span data-stu-id="c9298-122">Coverage settings</span></span>](coverage-settings.md)




