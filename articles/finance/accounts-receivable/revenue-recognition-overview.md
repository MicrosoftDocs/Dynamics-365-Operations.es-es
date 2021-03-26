---
title: Introducción al reconocimiento de ingresos
description: Este tema proporciona información acerca de la función de reconocimiento de ingresos. Esta característica proporciona un marco flexible que permite definir reglas específicas de la empresa para reconocer tanto el precio como la programación de ingresos en pedidos de varios elementos.
author: kweekley
manager: aolson
ms.date: 11/11/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: b21cf04674d01df31dc3304886e7cda035bdcce2
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238265"
---
# <a name="revenue-recognition-overview"></a><span data-ttu-id="9ac60-104">Introducción al reconocimiento de ingresos</span><span class="sxs-lookup"><span data-stu-id="9ac60-104">Revenue recognition overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9ac60-105">Las empresas de sectores que venden múltiples elementos, como productos, servicios, suscripciones, etc., necesitan poder desglosar pedidos con varios elementos para poder reconocer los ingresos en función de un conjunto de directrices específicas de la empresa y del sector.</span><span class="sxs-lookup"><span data-stu-id="9ac60-105">Companies in industries that sell multiple elements, such as products, services, subscriptions, and so on, must be able to break out multi-element orders so that revenue can be recognized based on a set of company-specific and industry-specific guidelines.</span></span>

> [!NOTE]
> <span data-ttu-id="9ac60-106">La característica Reconocimiento de ingresos no se puede activar a través de Administración de características.</span><span class="sxs-lookup"><span data-stu-id="9ac60-106">The Revenue recognition feature can't be turned on through Feature management.</span></span> <span data-ttu-id="9ac60-107">Actualmente, debe utilizar las claves de configuración para activarla.</span><span class="sxs-lookup"><span data-stu-id="9ac60-107">Currently, you must use configuration keys to turn it on.</span></span>

> <span data-ttu-id="9ac60-108">Reconocimiento de ingresos, incluida la funcionalidad de agrupación de trabajos, no se admite para su uso en los canales de Commerce (comercio electrónico, PDV, centro de llamadas).</span><span class="sxs-lookup"><span data-stu-id="9ac60-108">Revenue recognition, including bundle functionality, isn't supported for use in Commerce channels (e-commerce, POS, call center).</span></span> <span data-ttu-id="9ac60-109">Los elementos configurados con reconocimiento de ingresos no deben agregarse a pedidos o transacciones creadas en los canales de Commerce.</span><span class="sxs-lookup"><span data-stu-id="9ac60-109">Items configured with revenue recognition should not be added to orders or transactions created in Commerce channels.</span></span>

<span data-ttu-id="9ac60-110">En general, el proceso de reconocimiento de ingresos se puede usar para realizar estas tareas:</span><span class="sxs-lookup"><span data-stu-id="9ac60-110">In general, the revenue recognition process can be used to perform these tasks:</span></span>

* <span data-ttu-id="9ac60-111">Asignar ingresos para ayudar a garantizar el reconocimiento del precio de ingresos adecuado, según el valor de los componentes de los pedidos con varios elementos.</span><span class="sxs-lookup"><span data-stu-id="9ac60-111">Allocate revenue, to help ensure that the appropriate revenue price is recognized, based on the value of the components on multi-element orders.</span></span>
* <span data-ttu-id="9ac60-112">Diferir los ingresos en función de una programación de ingresos que represente el marco contractual y los porcentajes para reconocer ingresos en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="9ac60-112">Defer revenue, based on a revenue schedule that represents the contractual time frame and percentages for recognizing revenue over time.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44iER]

<span data-ttu-id="9ac60-113">El vídeo [Cómo usar el reconocimiento de ingresos en Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) (se muestra arriba) se incluye en la [Lista de reproducción de Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible en YouTube.</span><span class="sxs-lookup"><span data-stu-id="9ac60-113">The [How to use revenue recognition in Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

<span data-ttu-id="9ac60-114">La característica de reconocimiento de ingresos proporciona un marco flexible que permite definir reglas específicas de la empresa para reconocer tanto el precio como la programación de ingresos.</span><span class="sxs-lookup"><span data-stu-id="9ac60-114">The Revenue recognition feature provides a flexible framework that lets you define company-specific rules for recognizing both the revenue price and the revenue schedule.</span></span>

<span data-ttu-id="9ac60-115">Se usan productos liberados para permitir el reconocimiento de ingresos en los documentos de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="9ac60-115">Released products are used to support revenue recognition on sales order documents.</span></span> <span data-ttu-id="9ac60-116">Los productos emitidos contienen la configuración necesaria para determinar el precio y la programación de ingresos.</span><span class="sxs-lookup"><span data-stu-id="9ac60-116">The released products contain the setup that is required to determine the revenue price and the revenue schedule.</span></span> <span data-ttu-id="9ac60-117">El pedido de ventas puede originarse a partir de un proyecto de tiempo y materiales.</span><span class="sxs-lookup"><span data-stu-id="9ac60-117">The sales order can originate from a Time and materials project.</span></span>

<span data-ttu-id="9ac60-118">Las empresas pueden usar la funcionalidad de programación de ingresos sin usar la funcionalidad de precio de ingresos.</span><span class="sxs-lookup"><span data-stu-id="9ac60-118">Companies can use the revenue schedule functionality without using the revenue price functionality.</span></span> <span data-ttu-id="9ac60-119">Por ello, el precio en las líneas de pedido de ventas se usará como ingresos o ingresos aplazados.</span><span class="sxs-lookup"><span data-stu-id="9ac60-119">Therefore, the price on the sales order lines will be used as either revenue or deferred revenue.</span></span> <span data-ttu-id="9ac60-120">Si existe una programación de ingresos en la línea de pedido de ventas, se aplazará el precio de la línea del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="9ac60-120">If a revenue schedule exists on the sales order line, the price on the sales order line will be deferred.</span></span> <span data-ttu-id="9ac60-121">Si una programación de ingresos no existe en la línea de pedido de ventas, se registrará el precio de la línea de pedido de ventas en una cuenta de ingresos cuando se facture.</span><span class="sxs-lookup"><span data-stu-id="9ac60-121">If a revenue schedule doesn't exist on the sales order line, the price on the sales order line will be posted to a revenue account when it's invoiced.</span></span>

<span data-ttu-id="9ac60-122">El precio de ingresos se calcula cuando se confirma el pedido de ventas o cuando se registra la factura.</span><span class="sxs-lookup"><span data-stu-id="9ac60-122">The revenue price is calculated either when the sales order is confirmed or when the invoice is posted.</span></span> <span data-ttu-id="9ac60-123">Para obtener una vista previa del precio de ingresos antes de registrar la factura, debe confirmar el pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="9ac60-123">To preview the revenue price before the invoice is posted, you must confirm the sales order.</span></span>

<span data-ttu-id="9ac60-124">Cuando se confirma el pedido de ventas, también se crea una programación de ingresos prevista si alguna línea de pedido de ventas tiene una programación de ingresos.</span><span class="sxs-lookup"><span data-stu-id="9ac60-124">When the sales order is confirmed, an expected revenue schedule is also created if any sales order line has a revenue schedule.</span></span> <span data-ttu-id="9ac60-125">Cuando se factura el pedido de ventas, se elimina la programación de ingresos prevista y se sustituye con la programación de reconocimiento de ingresos real.</span><span class="sxs-lookup"><span data-stu-id="9ac60-125">When the sales order is invoiced, the expected revenue schedule is deleted, and the expected revenue schedule is replaced with the actual revenue recognition schedule.</span></span>

<span data-ttu-id="9ac60-126">Se mantienen los detalles de la programación de reconocimiento de ingresos para cada línea de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="9ac60-126">The details of the revenue recognition schedule are maintained for each sales order line.</span></span> <span data-ttu-id="9ac60-127">Por lo tanto, el administrador de reconocimiento de ingresos puede ver los detalles y emitir líneas para ingresos cuando finalice la obligación del contrato.</span><span class="sxs-lookup"><span data-stu-id="9ac60-127">Therefore, the revenue recognition manager can view the details and can release lines to revenue when the contractual obligation has been completed.</span></span> <span data-ttu-id="9ac60-128">Al final de cada período, el administrador de reconocimiento de ingresos puede crear un diario de ingresos para emitir cualquier línea de programación que venza en la fecha que defina.</span><span class="sxs-lookup"><span data-stu-id="9ac60-128">At the end of each period, the revenue recognition manager can create a revenue journal to release any schedule lines that are due on or before a date they define.</span></span> <span data-ttu-id="9ac60-129">Este diario de ingresos no se registra inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="9ac60-129">This revenue journal isn't posted immediately.</span></span> <span data-ttu-id="9ac60-130">Así, el administrador de reconocimiento de ingresos podrá comprobar que se emiten los importes correctos de ingresos aplazados a ingresos reales.</span><span class="sxs-lookup"><span data-stu-id="9ac60-130">Therefore, the revenue recognition manager can verify that the correct amounts are being released from deferred revenue to actual revenue.</span></span>

<span data-ttu-id="9ac60-131">Si un cambio contractual hace que se agregue una nueva línea de pedido de ventas al pedido de ventas existente o a un nuevo pedido de ventas, se puede ejecutar un proceso de reasignación para corregir el precio de ingresos en todas las líneas de los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="9ac60-131">If a contractual change causes a new sales order line to be added either to the existing sales order or a new sales order, a reallocation process can be run to correct the revenue price across all lines on the sales orders.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]