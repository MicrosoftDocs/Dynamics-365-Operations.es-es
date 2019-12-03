---
title: Introducción al reconocimiento de ingresos
description: Este tema proporciona información acerca de la función de reconocimiento de ingresos. Esta característica proporciona un marco flexible que permite definir reglas específicas de la empresa para reconocer tanto el precio como la programación de ingresos en pedidos de varios artículos.
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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 8743183c46463395cad3138261860442701e0178
ms.sourcegitcommit: 0138b6c108a10f2bcb90c91205da8092917160d8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2019
ms.locfileid: "2781905"
---
# <a name="revenue-recognition-overview"></a><span data-ttu-id="79436-104">Introducción al reconocimiento de ingresos</span><span class="sxs-lookup"><span data-stu-id="79436-104">Revenue recognition overview</span></span>

[!include [banner](../includes/banner.md)]

> [!NOTE]
> <span data-ttu-id="79436-105">La característica de reconocimiento de ingresos no se puede activar a través de la administración de características.</span><span class="sxs-lookup"><span data-stu-id="79436-105">The Revenue recognition feature can't be turned on through Feature management.</span></span> <span data-ttu-id="79436-106">Actualmente hay que usar las claves de configuración para activarla.</span><span class="sxs-lookup"><span data-stu-id="79436-106">Currently, you must use configuration keys to turn it on.</span></span>

<span data-ttu-id="79436-107">Las empresas de sectores que venden múltiples artículos, como productos, servicios, suscripciones, etc., necesitan realizar pedidos con varios artículos para poder reconocer el ingreso en función de un conjunto de instrucciones específicas de la empresa y del sector.</span><span class="sxs-lookup"><span data-stu-id="79436-107">Companies in industries that sell multiple elements, such as products, services, subscriptions, and so on, must be able to break out multi-element orders so that revenue can be recognized based on a set of company-specific and industry-specific guidelines.</span></span>

<span data-ttu-id="79436-108">En general, el proceso de reconocimiento de ingresos se puede usar para realizar estas tareas:</span><span class="sxs-lookup"><span data-stu-id="79436-108">In general, the revenue recognition process can be used to perform these tasks:</span></span>

* <span data-ttu-id="79436-109">Asignar ingresos para ayudar a garantizar el reconocimiento del precio de ingresos adecuado, según el valor de los componentes de los pedidos con varios artículos.</span><span class="sxs-lookup"><span data-stu-id="79436-109">Allocate revenue, to help guarantee that the appropriate revenue price is recognized, based on the value of the components on multi-element orders.</span></span>
* <span data-ttu-id="79436-110">Diferir los ingresos en función de una programación de ingresos que represente el marco contractual y los porcentajes para reconocer ingresos en el tiempo.</span><span class="sxs-lookup"><span data-stu-id="79436-110">Defer revenue, based on a revenue schedule that represents the contractual time frame and percentages for recognizing revenue over time.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE44iER]

<span data-ttu-id="79436-111">El vídeo [Cómo usar el reconocimiento de ingresos en Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) (se muestra arriba) se incluye en la [Lista de reproducción de Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible en YouTube.</span><span class="sxs-lookup"><span data-stu-id="79436-111">The [How to use revenue recognition in Dynamics 365 Finance](https://youtu.be/v3amIsiqvoo) video (shown above) is included in the [Finance and Operations playlist](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) available on YouTube.</span></span>

<span data-ttu-id="79436-112">La característica de reconocimiento de ingresos proporciona un marco flexible que permite definir reglas específicas de la empresa para reconocer tanto el precio como la programación de ingresos.</span><span class="sxs-lookup"><span data-stu-id="79436-112">The Revenue recognition feature provides a flexible framework that lets you define company-specific rules for recognizing both the revenue price and the revenue schedule.</span></span>

<span data-ttu-id="79436-113">Se usan productos liberados para permitir el reconocimiento de ingresos en los documentos de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="79436-113">Released products are used to support revenue recognition on sales order documents.</span></span> <span data-ttu-id="79436-114">Los productos emitidos contienen la configuración necesaria para determinar el precio y la programación de ingresos.</span><span class="sxs-lookup"><span data-stu-id="79436-114">The released products contain the setup that is required to determine the revenue price and the revenue schedule.</span></span> <span data-ttu-id="79436-115">El pedido de ventas puede originarse a partir de un proyecto de tiempo y materiales.</span><span class="sxs-lookup"><span data-stu-id="79436-115">The sales order can originate from a Time and materials project.</span></span>

<span data-ttu-id="79436-116">Las empresas pueden usar la funcionalidad de programación de ingresos sin usar la funcionalidad de precio de ingresos.</span><span class="sxs-lookup"><span data-stu-id="79436-116">Companies can use the revenue schedule functionality without using the revenue price functionality.</span></span> <span data-ttu-id="79436-117">Por ello, el precio en las líneas de pedido de ventas se usará como ingresos o ingresos aplazados.</span><span class="sxs-lookup"><span data-stu-id="79436-117">Therefore, the price on the sales order lines will be used as either revenue or deferred revenue.</span></span> <span data-ttu-id="79436-118">Si existe una programación de ingresos en la línea de pedido de ventas, se aplazará el precio de la línea del pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="79436-118">If a revenue schedule exists on the sales order line, the price on the sales order line will be deferred.</span></span> <span data-ttu-id="79436-119">Si una programación de ingresos no existe en la línea de pedido de ventas, se registrará el precio de la línea de pedido de ventas en una cuenta de ingresos cuando se facture.</span><span class="sxs-lookup"><span data-stu-id="79436-119">If a revenue schedule doesn't exist on the sales order line, the price on the sales order line will be posted to a revenue account when it's invoiced.</span></span>

<span data-ttu-id="79436-120">El precio de ingresos se calcula cuando se confirma el pedido de ventas o cuando se registra la factura.</span><span class="sxs-lookup"><span data-stu-id="79436-120">The revenue price is calculated either when the sales order is confirmed or when the invoice is posted.</span></span> <span data-ttu-id="79436-121">Para obtener una vista previa del precio de ingresos antes de registrar la factura, debe confirmar el pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="79436-121">To preview the revenue price before the invoice is posted, you must confirm the sales order.</span></span>

<span data-ttu-id="79436-122">Cuando se confirma el pedido de ventas, también se crea una programación de ingresos prevista si alguna línea de pedido de ventas tiene una programación de ingresos.</span><span class="sxs-lookup"><span data-stu-id="79436-122">When the sales order is confirmed, an expected revenue schedule is also created if any sales order line has a revenue schedule.</span></span> <span data-ttu-id="79436-123">Cuando se factura el pedido de ventas, se elimina la programación de ingresos prevista y se sustituye con la programación de reconocimiento de ingresos real.</span><span class="sxs-lookup"><span data-stu-id="79436-123">When the sales order is invoiced, the expected revenue schedule is deleted, and the expected revenue schedule is replaced with the actual revenue recognition schedule.</span></span>

<span data-ttu-id="79436-124">Se mantienen los detalles de la programación de reconocimiento de ingresos para cada línea de pedido de ventas.</span><span class="sxs-lookup"><span data-stu-id="79436-124">The details of the revenue recognition schedule are maintained for each sales order line.</span></span> <span data-ttu-id="79436-125">Por lo tanto, el administrador de reconocimiento de ingresos puede ver los detalles y emitir líneas para ingresos cuando finalice la obligación del contrato.</span><span class="sxs-lookup"><span data-stu-id="79436-125">Therefore, the revenue recognition manager can view the details and can release lines to revenue when the contractual obligation has been completed.</span></span> <span data-ttu-id="79436-126">Al final de cada período, el administrador de reconocimiento de ingresos puede crear un diario de ingresos para emitir cualquier línea de programación que venza en la fecha establecido por el administrador.</span><span class="sxs-lookup"><span data-stu-id="79436-126">At the end of each period, the revenue recognition manager can create a revenue journal to release any schedule lines that are due on or before a date that he or she defines.</span></span> <span data-ttu-id="79436-127">Este diario de ingresos no se registra inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="79436-127">This revenue journal isn't posted immediately.</span></span> <span data-ttu-id="79436-128">Así, el administrador de reconocimiento de ingresos podrá comprobar que se emiten los importes correctos de ingresos aplazados a ingresos reales.</span><span class="sxs-lookup"><span data-stu-id="79436-128">Therefore, the revenue recognition manager can verify that the correct amounts are being released from deferred revenue to actual revenue.</span></span>

<span data-ttu-id="79436-129">Si un cambio contractual hace que se agregue una nueva línea de pedido de ventas al pedido de ventas existente o a un nuevo pedido de ventas, se puede ejecutar un proceso de reasignación para corregir el precio de ingresos en todas las líneas de los pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="79436-129">If a contractual change causes a new sales order line to be added either to the existing sales order or a new sales order, a reallocation process can be run to correct the revenue price across all lines on the sales orders.</span></span>
