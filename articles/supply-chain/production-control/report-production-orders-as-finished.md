---
title: Notificar pedidos de producción como terminados
description: Notificar como terminado es una etapa de producción. En esta etapa se notifica un producto terminado y se mueve del pedido de producción al inventario.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdJournalTransJob, ProdJournalTransProd, ProdJournalTransRoute, ProdParmReportFinished, ProdRouteOprOverview
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 27061
ms.assetid: 1c2dfc54-a293-49f2-9b96-5a912ac5762c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 87e5d4f46a2ae34a2bc114a92ed4e037875dde43
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4436786"
---
# <a name="report-production-orders-as-finished"></a><span data-ttu-id="655ad-104">Notificar pedidos de producción como terminados</span><span class="sxs-lookup"><span data-stu-id="655ad-104">Report production orders as finished</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="655ad-105">Notificar como terminado es una etapa de producción.</span><span class="sxs-lookup"><span data-stu-id="655ad-105">Report as finished is a production stage.</span></span> <span data-ttu-id="655ad-106">En esta etapa se notifica un producto terminado y se mueve del pedido de producción al inventario.</span><span class="sxs-lookup"><span data-stu-id="655ad-106">At this stage, a finished product is reported and moved from the production order to the inventory.</span></span>

<span data-ttu-id="655ad-107">Cuando una cantidad de mercancías terminadas se notifica como terminada en un pedido de producción, esta se actualiza como disponible en el inventario.</span><span class="sxs-lookup"><span data-stu-id="655ad-107">When a quantity of the finished goods is reported as finished on a production order it is updated as on-hand in the inventory.</span></span> <span data-ttu-id="655ad-108">Las cantidades parciales de la cantidad de pedido planificado original se pueden notificar originalmente como terminadas.</span><span class="sxs-lookup"><span data-stu-id="655ad-108">Partial quantities of the originally planned order quantity can be reported as finished.</span></span> <span data-ttu-id="655ad-109">Al notificar cantidades como terminadas, también es posible notificar cantidades con error con su correspondiente motivo de error asociado.</span><span class="sxs-lookup"><span data-stu-id="655ad-109">It is also possible to report error quantities with an associated error reason when reporting quantities as finished.</span></span> <span data-ttu-id="655ad-110">Cuando el pedido de producción llega a la etapa Notificado como terminado, indica que no se va a notificar más cantidad en el pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="655ad-110">When the production order reach the stage Reported as finished it indicates that no more quantity is going to be reported at the production  order.</span></span>
<span data-ttu-id="655ad-111">Las siguientes características se asocian también con el proceso **Notificar como terminado**:</span><span class="sxs-lookup"><span data-stu-id="655ad-111">The following characteristics are also associated with the **Report as finished** process:</span></span>
-   <span data-ttu-id="655ad-112">Es posible configurar el consumo de materias primas y el tiempo proporcionales a la cantidad notificada (contabilización previa).</span><span class="sxs-lookup"><span data-stu-id="655ad-112">It is possible to set up consumption of raw material and time that are proportional to the reported quantity (back-flushing)</span></span>
-   <span data-ttu-id="655ad-113">Se puede generar trabajo de guardado en ubicación para artículos habilitados para los procesos de almacén.</span><span class="sxs-lookup"><span data-stu-id="655ad-113">Put-away work can be generated for items that are enabled for warehouse processes.</span></span>
-   <span data-ttu-id="655ad-114">El valor de coste estándar o planificado de los productos terminados se puede configurar para notificarse en cuentas contables.</span><span class="sxs-lookup"><span data-stu-id="655ad-114">The planned or standard cost value of the finished goods can be set up to be reported to ledger accounts.</span></span>
-   <span data-ttu-id="655ad-115">Se pueden crear pedidos de calidad para la cantidad notificada según la configuración de una asociación de calidad.</span><span class="sxs-lookup"><span data-stu-id="655ad-115">A quality order can be created for the reported quantity based on the setup of a quality association.</span></span>

<span data-ttu-id="655ad-116">La cantidad se notifica a la ubicación de salida.</span><span class="sxs-lookup"><span data-stu-id="655ad-116">The quantity is reported to the output location.</span></span> <span data-ttu-id="655ad-117">El trabajo de almacén se genera a continuación para mover la cantidad desde la ubicación de salida a su destino final según defina la directiva de ubicación para el trabajo de guardado en ubicación.</span><span class="sxs-lookup"><span data-stu-id="655ad-117">Warehouse work is then generated to move the quantity from the output location to its final destination defined by the location directive for the put-away work.</span></span>

-   <span data-ttu-id="655ad-118">Se puede crear un pedido de calidad cuando se notifica un pedido de producción como finalizado si se ha configurado una asociación de calidad.</span><span class="sxs-lookup"><span data-stu-id="655ad-118">A quality order can be created when a production order is reported as finished if a quality association has been set up.</span></span>

## <a name="set-a-production-order-to-reporting-as-finished"></a><span data-ttu-id="655ad-119">Definición de pedidos de producción para notificarse como terminados</span><span class="sxs-lookup"><span data-stu-id="655ad-119">Set a production order to Reporting as finished</span></span>
<span data-ttu-id="655ad-120">Puede establecer un pedido de producción en **Notificar como terminado** mediante la función de actualización de pedido de producción estándar, mediante los diarios de tarjeta de trabajo y de ruta o mediante el diario **Notificar como terminado**.</span><span class="sxs-lookup"><span data-stu-id="655ad-120">You can set a production order to **Report as finished** through the standard production order update function, or through the route and job card journals, or through the journal **Report as finished**.</span></span> <span data-ttu-id="655ad-121">También puede actualizar la etapa a **Notificar como terminado** a través de la terminal de la tarjeta de trabajo y las páginas del dispositivo de tarjeta de trabajo al notificar sobre el último trabajo del pedido de producción.</span><span class="sxs-lookup"><span data-stu-id="655ad-121">You can also update the stage to **Report as finished** through the job card terminal and job card device pages, when you report on the last job of the production order.</span></span> <span data-ttu-id="655ad-122">Finalmente, puede habilitar la opción **Notificar como terminado** como un proceso para la solución del dispositivo de almacén de mano.</span><span class="sxs-lookup"><span data-stu-id="655ad-122">Finally, you can enable the **Report as finished** option as a process for the handheld warehouse device solution.</span></span>  



