---
title: Retrasos
description: Este tema proporciona información acerca de fechas retrasadas en la planificación maestra. Una fecha retrasada es una fecha de vencimiento realista que una transacción recibe si la fecha de cumplimiento más temprana que la planificación maestra calcula es posterior a la fecha solicitada.
author: roxanadiaconu
manager: AnnBe
ms.date: 03/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c1a8c738fffda76f2a8492c20e2c67a154c68559
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2019
ms.locfileid: "1522298"
---
# <a name="delays"></a><span data-ttu-id="b5a92-104">Retrasos</span><span class="sxs-lookup"><span data-stu-id="b5a92-104">Delays</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b5a92-105">Este tema proporciona información acerca de fechas retrasadas en la planificación maestra.</span><span class="sxs-lookup"><span data-stu-id="b5a92-105">This topic provides information about delayed dates in master planning.</span></span> <span data-ttu-id="b5a92-106">Una fecha retrasada es una fecha de vencimiento realista que una transacción recibe si la fecha de cumplimiento más temprana que la planificación maestra calcula es posterior a la fecha solicitada.</span><span class="sxs-lookup"><span data-stu-id="b5a92-106">A delayed date is a realistic due date that a transaction receives if the earliest fulfillment date that master planning calculates is later than the requested date.</span></span>

<span data-ttu-id="b5a92-107">La planificación maestra puede calcular la fecha más temprana de cumplimiento para una transacción según los plazos, la disponibilidad de material, la disponibilidad de capacidad y los diferentes parámetros de planificación.</span><span class="sxs-lookup"><span data-stu-id="b5a92-107">Master planning can calculate the earliest fulfillment date for a transaction, based on lead times, material availability, capacity availability, and various planning parameters.</span></span> 

<span data-ttu-id="b5a92-108">Si la planificación maestra calcula una fecha de pedido anterior a la fecha en curso, el pedido no se puede satisfacer a tiempo.</span><span class="sxs-lookup"><span data-stu-id="b5a92-108">If master planning calculates an order date that precedes the current date, the order can't be fulfilled on time.</span></span> <span data-ttu-id="b5a92-109">Por tanto, se retrasa el pedido.</span><span class="sxs-lookup"><span data-stu-id="b5a92-109">Therefore, the order is delayed.</span></span> <span data-ttu-id="b5a92-110">En este caso, la planificación maestra adelanta la planificación del pedido a partir de la fecha en uso e incluye plazos.</span><span class="sxs-lookup"><span data-stu-id="b5a92-110">In this case, master planning forward-plans the order from the current date and includes lead times.</span></span> <span data-ttu-id="b5a92-111">Estos plazos empiezan con cualquier artículo componente de nivel inferior.</span><span class="sxs-lookup"><span data-stu-id="b5a92-111">These lead times start with any lower-level component items.</span></span> <span data-ttu-id="b5a92-112">El pedido recibe a continuación una fecha retrasada.</span><span class="sxs-lookup"><span data-stu-id="b5a92-112">The order then receives a delayed date.</span></span> <span data-ttu-id="b5a92-113">La fecha retrasada es una fecha de vencimiento real en función de los datos actuales.</span><span class="sxs-lookup"><span data-stu-id="b5a92-113">A delayed date is a realistic due date, based on the current data.</span></span> <span data-ttu-id="b5a92-114">La planificación maestra también calcula el número de días de retraso.</span><span class="sxs-lookup"><span data-stu-id="b5a92-114">Master planning also calculates the number of delay days.</span></span> 

<span data-ttu-id="b5a92-115">En algunos casos, es posible optar por no calcular retrasos, como cuando los usuarios saben que pueden acelerar los plazos seleccionando modos de entrega alternativos.</span><span class="sxs-lookup"><span data-stu-id="b5a92-115">In some situations, you might choose not to calculate delays, such as when users know that they can expedite lead times by selecting alternative modes of delivery.</span></span> 

<span data-ttu-id="b5a92-116">Puede configurar cómo calcular los retrasos para un grupo de cobertura.</span><span class="sxs-lookup"><span data-stu-id="b5a92-116">You can configure how delays are calculated for a coverage group.</span></span> <span data-ttu-id="b5a92-117">Más adelante puede adjuntar el grupo de cobertura a un artículo.</span><span class="sxs-lookup"><span data-stu-id="b5a92-117">You can then attach the coverage group to an item later.</span></span> 

<span data-ttu-id="b5a92-118">En la página **Parámetros de planificación maestra** puede establecer el momento de inicio para el cálculo de retrasos.</span><span class="sxs-lookup"><span data-stu-id="b5a92-118">On the **Master planning parameters** page, you can set the start time for the calculation of delays.</span></span> <span data-ttu-id="b5a92-119">Si se satisface un pedido después de este momento, entonces se añade un retraso de un día a la fecha de retraso del pedido.</span><span class="sxs-lookup"><span data-stu-id="b5a92-119">If an order is fulfilled after this time, a delay of one day is added to the delay date of the order.</span></span> 

> [!NOTE]
> <span data-ttu-id="b5a92-120">En versiones anteriores, los retrasos calculados se conocían como *mensajes de futuros*, la fecha retrasada como *fecha de futuros* y las transacciones retrasadas como *transacciones establecidas en una fecha futura*.</span><span class="sxs-lookup"><span data-stu-id="b5a92-120">In earlier versions, calculated delays were known as *futures messages*, the delayed date was known as the *futures date*, and a delayed transaction was referred to as *a transaction that was future set*.</span></span>

## <a name="desired-date"></a><span data-ttu-id="b5a92-121">Fecha deseada</span><span class="sxs-lookup"><span data-stu-id="b5a92-121">Desired date</span></span>

<span data-ttu-id="b5a92-122">En la página **Pedido planificado** , en la pestaña **Retrasos** está la **Fecha deseada** para el pedido planificado.</span><span class="sxs-lookup"><span data-stu-id="b5a92-122">On the **Planned order** page, under the **Delays** tab is the **Desired date** for the planned order.</span></span> <span data-ttu-id="b5a92-123">La fecha deseada de un pedido planificado es la fecha base para los retrasos, que es una fecha calculada igual a la **Fecha solicitada** calculada a partir del **Requisito neto**.</span><span class="sxs-lookup"><span data-stu-id="b5a92-123">The desired date of a planned order is the base date for delays, which is a computed date that equals the **Requested date** calculated from the **Net Requirement**.</span></span> <span data-ttu-id="b5a92-124">Si el pedido planificado es una línea de L. MAT, una línea de producción o una línea kanban, la fecha deseada se basa en **Fecha de requisito** y la fecha deseada no se mostrará en la página **Pedido planificado**.</span><span class="sxs-lookup"><span data-stu-id="b5a92-124">If the planned order is a BOM line, production line or kanban line, the desired date is based on the **Requirement date** and the desired date will not be shown on the **Planned order** page.</span></span>

<a name="additional-resources"></a><span data-ttu-id="b5a92-125">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b5a92-125">Additional resources</span></span>
--------

[<span data-ttu-id="b5a92-126">Configuración de cobertura</span><span class="sxs-lookup"><span data-stu-id="b5a92-126">Coverage settings</span></span>](coverage-settings.md)
