---
title: Configurar un programa de continuidad para un centro de llamadas
description: "En este artículo se describe cómo configurar un programa de continuidad para un centro de llamadas."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: MCROrderParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16081
ms.assetid: 426a9be7-a931-4780-b372-e06f6083dd60
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 6f0042bf45354113b2bce22ae81365dee837824d
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="set-up-a-continuity-program-for-a-call-center"></a><span data-ttu-id="1ca7a-103">Configurar un programa de continuidad para un centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="1ca7a-103">Set up a continuity program for a call center</span></span>

[!INCLUDE [banner](includes/banner.md)]

<span data-ttu-id="1ca7a-104">En este artículo se describe cómo configurar un programa de continuidad para un centro de llamadas.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-104">This article describes how to set up a continuity program for a call center.</span></span>

<span data-ttu-id="1ca7a-105">En un programa de continuidad, también conocido como un programa de pedidos recurrentes, los clientes reciben envíos regulares de productos en función de una programación predefinida.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-105">In a continuity program, which is also known as a recurring order program, customers receive regular product shipments according to a predefined schedule.</span></span> <span data-ttu-id="1ca7a-106">Cada envío puede contener un producto diferente, como en el caso de un club del libro del mes, o se puede enviar repetidamente el mismo producto.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-106">Each shipment can contain a different product, as in the case of a book-of-the-month club, or the same product can be sent repeatedly.</span></span> <span data-ttu-id="1ca7a-107">Para configurar un programa de continuidad, debe completar las tareas siguientes:</span><span class="sxs-lookup"><span data-stu-id="1ca7a-107">To set up a continuity program, you must complete the following tasks.</span></span>

1.  <span data-ttu-id="1ca7a-108">Establecer los parámetros de continuidad en la página **Parámetros del centro de llamadas**.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-108">Set the continuity parameters on the **Call center parameters** page.</span></span>
2.  <span data-ttu-id="1ca7a-109">Cree un programa de continuidad que especifique detalles como el multivencimiento, la sincronización de los envíos, y si la facturación se realiza por adelantado.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-109">Create a continuity program that specifies details such as the payment schedule, the timing of the shipments, and whether billing is up front.</span></span> <span data-ttu-id="1ca7a-110">También debe agregar una lista de productos incluidos en el programa de continuidad.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-110">You must also add a list of products that are included in the continuity program.</span></span> <span data-ttu-id="1ca7a-111">Cada producto recibe un número de identificación de evento que se asigna de forma secuencial, empezando por 1.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-111">Each product receives an event ID number that is assigned sequentially, beginning with 1.</span></span> <span data-ttu-id="1ca7a-112">Los identificadores de evento determinan el orden en que se envían los productos.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-112">The event IDs determine the order that products are sent in.</span></span>
    -   <span data-ttu-id="1ca7a-113">Si los clientes reciben un producto diferente en cada envío, los productos se envían en orden secuencial, en función de sus identificadores de evento y comenzando por el evento actual.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-113">If customers receive a different product in each shipment, the products are sent in sequential order, based on their event IDs and beginning with the current event.</span></span>
    -   <span data-ttu-id="1ca7a-114">Si los clientes reciben el mismo producto en cada envío, la lista solo contiene un producto con un id. de evento.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-114">If customers receive the same product in each shipment, the list contains only one product that has one event ID.</span></span> <span data-ttu-id="1ca7a-115">El mismo evento se produce repetidamente.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-115">The same event occurs repeatedly.</span></span> <span data-ttu-id="1ca7a-116">Puede especificar cuántas veces se repite cada evento.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-116">You can specify how many times each event is repeated.</span></span>

3.  <span data-ttu-id="1ca7a-117">Cree un producto principal que represente el programa de continuidad que creó en la tarea 2.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-117">Create a parent product that represents the continuity program that you created in task 2.</span></span> <span data-ttu-id="1ca7a-118">Si agrega este producto a un pedido de ventas, se abre la página **Continuidad**.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-118">If you add this product to a sales order, the **Continuity** page opens.</span></span> <span data-ttu-id="1ca7a-119">Puede usar esa página para crear el pedido de continuidad real.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-119">You can then use that page to create the actual continuity order.</span></span> <span data-ttu-id="1ca7a-120">El producto principal no especifica los productos individuales que el cliente recibe en cada envío.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-120">The parent product doesn't specify the individual products that the customer receives in each shipment.</span></span>

<span data-ttu-id="1ca7a-121">Una vez haya configurado un programa de continuidad como se describe anteriormente, puede crear un pedido de continuidad para un cliente.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-121">After you've set up a continuity program as described above, you can create a continuity order for a customer.</span></span> <span data-ttu-id="1ca7a-122">Es posible que también tenga que realizar las siguientes tareas de mantenimiento adicionales.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-122">You might also have to perform the following additional maintenance tasks.</span></span>

-   <span data-ttu-id="1ca7a-123">**Actualizar el período del evento de continuidad actual**: configure un trabajo por lotes que indique al sistema cuál es el período actual del evento.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-123">**Update the current continuity event period** – Set up a batch job that tells the system what the current event period is.</span></span>
-   <span data-ttu-id="1ca7a-124">**Crear pedidos secundarios de continuidad**: cree pedidos secundarios de pedidos de continuidad principales.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-124">**Create continuity child orders** – Create child orders from the parent continuity order.</span></span>
-   <span data-ttu-id="1ca7a-125">**Procesar pagos de continuidad**: procese facturación y notificaciones para los pagos asociados a los pedidos de ventas de continuidad.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-125">**Process continuity payments** – Process billing and notifications for payments that are associated with continuity sales orders.</span></span>
-   <span data-ttu-id="1ca7a-126">**Ampliar líneas de continuidad** (si es necesario): amplíe el número de veces que un evento de continuidad se puede repetir.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-126">**Extend continuity lines** (if required) – Extend the number of times that a continuity event can be repeated.</span></span> <span data-ttu-id="1ca7a-127">La periodicidad de los envíos se puede ampliar más allá de límites que se establecieron en el campo **Umbral de repetición de continuidad** en los parámetros del centro de llamadas</span><span class="sxs-lookup"><span data-stu-id="1ca7a-127">The repetition of shipments can then extend beyond the limit that was set in the **Continuity repeat threshold** field in the call center parameters.</span></span>
-   <span data-ttu-id="1ca7a-128">**Realizar una actualización de continuidad** (si es necesario) : sincronice los cambios entre el programa de continuidad y los pedidos de ventas principales de continuidad.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-128">**Perform a continuity update** (if required) – Synchronize changes between the continuity program and the continuity parent sales orders.</span></span>
-   <span data-ttu-id="1ca7a-129">**Cerrar pedidos y líneas principales de continuidad**: cierre pedidos de continuidad.</span><span class="sxs-lookup"><span data-stu-id="1ca7a-129">**Close continuity parent lines and orders** – Close continuity orders.</span></span>





