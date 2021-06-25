---
title: Programaciones de entrega
description: Las programaciones de entrega le permiten realizar el seguimiento de cantidad de la línea de pedido cuando está usando entregas para un pedido de ventas único, un presupuesto de ventas o un pedido de compra.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: PurchDeliverySchedule, SalesDeliverySchedule, SalesQuotationDeliverySchedule, SalesQuotationDeliverySchedule
audience: Application User
ms.reviewer: kamaybac
ms.custom: 213984
ms.assetid: 44cac104-c36c-4371-a992-9178b3fd65e9
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3dbd66d499b5d5f9f8ef21c0ce3752031a5f4672
ms.sourcegitcommit: 74e47075eab2b0b28f82b0d57f439719847ecb01
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/07/2021
ms.locfileid: "6193791"
---
# <a name="delivery-schedules"></a><span data-ttu-id="78253-103">Programaciones de entrega</span><span class="sxs-lookup"><span data-stu-id="78253-103">Delivery schedules</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="78253-104">Las programaciones de entrega le permiten realizar el seguimiento de cantidad de la línea de pedido cuando está usando entregas para un pedido de ventas único, un presupuesto de ventas o un pedido de compra.</span><span class="sxs-lookup"><span data-stu-id="78253-104">Delivery schedules allow you to track order line quantity when you are using multiple deliveries for a single sales order, sales quotation, or purchase order.</span></span>

<span data-ttu-id="78253-105">Use una programación de entrega cuando la cantidad total de una línea de pedido o presupuesto debe entregarse en varios envíos.</span><span class="sxs-lookup"><span data-stu-id="78253-105">Use a delivery schedule when the total quantity on an order or quotation line must be delivered in multiple shipments.</span></span> <span data-ttu-id="78253-106">Los envíos individuales se representan por medio las líneas de entrega.</span><span class="sxs-lookup"><span data-stu-id="78253-106">Individual shipments are represented by delivery lines.</span></span> <span data-ttu-id="78253-107">Dos o más líneas de entrega constituyen una programación de entrega.</span><span class="sxs-lookup"><span data-stu-id="78253-107">Two or more delivery lines make up one delivery schedule.</span></span> <span data-ttu-id="78253-108">Las líneas de entrega pueden tener diferentes fechas de entrega, cantidades, modos de entrega y dimensiones de almacenamiento como el sitio y el almacén.</span><span class="sxs-lookup"><span data-stu-id="78253-108">The delivery lines can have different delivery dates, quantities, modes of delivery, and storage dimensions, such as site and warehouse.</span></span>  

<span data-ttu-id="78253-109">**Ejemplo de una programación de entrega**</span><span class="sxs-lookup"><span data-stu-id="78253-109">**Example of a delivery schedule**</span></span>

| <span data-ttu-id="78253-110">Artículo</span><span class="sxs-lookup"><span data-stu-id="78253-110">Item</span></span>                              | <span data-ttu-id="78253-111">Valor</span><span class="sxs-lookup"><span data-stu-id="78253-111">Value</span></span>                                    |
|-----------------------------------|------------------------------------------|
| <span data-ttu-id="78253-112">Pedido total (línea de pedido original)</span><span class="sxs-lookup"><span data-stu-id="78253-112">Total order (original order line)</span></span> | <span data-ttu-id="78253-113">600 sillas</span><span class="sxs-lookup"><span data-stu-id="78253-113">600 chairs</span></span>                               |
| <span data-ttu-id="78253-114">Programación de entrega solicitada</span><span class="sxs-lookup"><span data-stu-id="78253-114">Requested delivery schedule</span></span>       | <span data-ttu-id="78253-115">100 sillas por mes</span><span class="sxs-lookup"><span data-stu-id="78253-115">100 chairs per month</span></span>                     |
| <span data-ttu-id="78253-116">Plazo de entrega solicitado</span><span class="sxs-lookup"><span data-stu-id="78253-116">Requested time frame for delivery</span></span> | <span data-ttu-id="78253-117">6 meses, el primer día de cada mes</span><span class="sxs-lookup"><span data-stu-id="78253-117">6 months, on the first day of each month</span></span> |

<span data-ttu-id="78253-118">En este escenario, el cliente solicita una entrega de 600 sillas en lotes de 100 sillas durante un período de seis meses.</span><span class="sxs-lookup"><span data-stu-id="78253-118">In this scenario, the customer requests delivery of 600 chairs in batches of 100 chairs over a period of six months.</span></span> <span data-ttu-id="78253-119">Para realizar un seguimiento de los requisitos de entrega, se crea una programación de entrega.</span><span class="sxs-lookup"><span data-stu-id="78253-119">To keep track of the delivery requirements, you create a delivery schedule.</span></span> <span data-ttu-id="78253-120">En la página de programación de entrega, cree seis líneas de entrega distintas.</span><span class="sxs-lookup"><span data-stu-id="78253-120">On the delivery schedule page, you create six separate delivery lines.</span></span> <span data-ttu-id="78253-121">Cada línea de entrega contiene 100 sillas e indica la fecha de entrega de esas 100 sillas.</span><span class="sxs-lookup"><span data-stu-id="78253-121">Each delivery line contains 100 chairs and indicates the delivery date for those 100 chairs.</span></span> <span data-ttu-id="78253-122">En este caso, cada línea se compensará el primer día del mes durante seis meses consecutivos.</span><span class="sxs-lookup"><span data-stu-id="78253-122">In this case, each line is offset on the first of the month for six consecutive months.</span></span>  

<span data-ttu-id="78253-123">Una vez que haya creado la programación de entrega, el tipo de la línea de pedido original se convierte automáticamente en **Línea de pedido con varias entregas**.</span><span class="sxs-lookup"><span data-stu-id="78253-123">When you create a delivery schedule, the type of the original order line is automatically changed to **Order line with multiple deliveries**.</span></span> <span data-ttu-id="78253-124">Una línea de este tipo se denomina línea comercial y está marcada mediante un icono.</span><span class="sxs-lookup"><span data-stu-id="78253-124">A line of this type is referred to as a commercial line and is marked by an icon.</span></span> <span data-ttu-id="78253-125">La línea de entrega está marcada con otro icono.</span><span class="sxs-lookup"><span data-stu-id="78253-125">The delivery line is marked by a different icon.</span></span> <span data-ttu-id="78253-126">Si cambia una cantidad en una línea de entrega, la línea comercial se actualiza a la cantidad total de la programación de entrega.</span><span class="sxs-lookup"><span data-stu-id="78253-126">If you change a quantity on a delivery line, the commercial line is updated to the total quantity of the delivery schedule.</span></span> <span data-ttu-id="78253-127">Si un acuerdo comercial ha definido un descuento total para el pedido, la programación de entrega garantiza que se pueda aplicar al pedido el descuento de pedido total, incluso cuando el pedido se divide en entregas distintas.</span><span class="sxs-lookup"><span data-stu-id="78253-127">If a trade agreement has defined a total discount for the order, the delivery schedule ensures that your order is eligible for the total order discount, even when the order is split into separate deliveries.</span></span>  

<span data-ttu-id="78253-128">Los pedidos que tengan una programación de entrega se procesan con las líneas de entrega.</span><span class="sxs-lookup"><span data-stu-id="78253-128">Orders that have a delivery schedule are processed against the delivery lines.</span></span> <span data-ttu-id="78253-129">El proceso incluye el registro de albaranes, recepciones de producto y facturación.</span><span class="sxs-lookup"><span data-stu-id="78253-129">Processing includes the posting of packing slips, product receipts, and invoicing.</span></span>  

<span data-ttu-id="78253-130">Las impresiones de documentos de pedidos y de presupuestos con una programación de entrega solo muestran las líneas de entrega.</span><span class="sxs-lookup"><span data-stu-id="78253-130">Document printouts of orders and quotations that have a delivery schedule show only the delivery lines.</span></span> <span data-ttu-id="78253-131">No muestran las líneas originales (líneas comerciales).</span><span class="sxs-lookup"><span data-stu-id="78253-131">They don't show the original lines (commercial lines).</span></span> <span data-ttu-id="78253-132">**Nota:** Además, solo se muestran las líneas de entrega cuando realiza estas acciones:</span><span class="sxs-lookup"><span data-stu-id="78253-132">**Note:** In addition, only the delivery lines are shown when you perform these actions:</span></span>

-   <span data-ttu-id="78253-133">Registrar</span><span class="sxs-lookup"><span data-stu-id="78253-133">Post</span></span>
-   <span data-ttu-id="78253-134">Copiar páginas</span><span class="sxs-lookup"><span data-stu-id="78253-134">Copy pages</span></span>
-   <span data-ttu-id="78253-135">Examinar informes y páginas de lista</span><span class="sxs-lookup"><span data-stu-id="78253-135">Browse list pages and reports</span></span>

<span data-ttu-id="78253-136">Cuando confirma los presupuestos de ventas, los pedidos de ventas resultantes muestran la programación de entrega completa, incluso las líneas de pedido con múltiples entregas.</span><span class="sxs-lookup"><span data-stu-id="78253-136">When you confirm sales quotations, the resulting sales orders show the whole delivery schedule, even the order lines that have multiple deliveries.</span></span> <span data-ttu-id="78253-137">Además, la programación de entrega completa se muestra en todas las páginas principales, como pedidos de ventas, presupuestos de ventas y pedidos de compra.</span><span class="sxs-lookup"><span data-stu-id="78253-137">In addition, the whole delivery schedule is shown on all the major pages, such as sales orders, sales quotations, and purchase orders.</span></span>





[!INCLUDE[footer-include](../../includes/footer-banner.md)]