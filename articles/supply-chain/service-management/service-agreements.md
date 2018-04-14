---
title: Contratos de servicio
description: "El acuerdo de servicio le permite definir los recursos utilizados en una visita de servicio típica y cómo se facturan dichos servicios al cliente."
author: YuyuScheller
manager: AnnBe
ms.date: 02/19/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAAgreementTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: dfb8d101c69e9bfdb918dca5cf48da1f6d2564b8
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="service-agreements"></a><span data-ttu-id="c213f-103">Contratos de servicio</span><span class="sxs-lookup"><span data-stu-id="c213f-103">Service agreements</span></span>

[!INCLUDE [banner](../includes/banner.md)]

<span data-ttu-id="c213f-104">El acuerdo de servicio le permite definir los recursos utilizados en una visita de servicio típica y cómo se facturan dichos servicios al cliente.</span><span class="sxs-lookup"><span data-stu-id="c213f-104">Service agreements let you define the resources that are used in a typical service visit and how those resources are invoiced to the customer.</span></span>

<span data-ttu-id="c213f-105">Todos los acuerdos de servicio están vinculados a proyectos mediante los cuales se registran y facturan las transacciones.</span><span class="sxs-lookup"><span data-stu-id="c213f-105">Every service agreement is attached to a project through which transactions are posted and invoiced.</span></span> <span data-ttu-id="c213f-106">No obstante, puede facturar las transacciones de pedido de servicio directamente a través del proyecto sin conectarse primero al pedido de servicio de un acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="c213f-106">However, you can also invoice service order transactions directly through the project without first having to connect the service order to a service agreement.</span></span> <span data-ttu-id="c213f-107">Esto podría resultar útil si el pedido de servicio es una visita única y la necesidad de procesar las transacciones del servicio rápidamente es más importante que la necesidad de mantener información detallada del acuerdo de servicio sobre un cliente durante un período de tiempo.</span><span class="sxs-lookup"><span data-stu-id="c213f-107">You might decide to do this if the service order is for a one-time-only service visit and the need for processing the service transactions quickly outweighs the need for maintaining detailed service-agreement information about the customer over a period of time.</span></span>

## <a name="service-agreement"></a><span data-ttu-id="c213f-108">Acuerdo de servicio</span><span class="sxs-lookup"><span data-stu-id="c213f-108">Service agreement</span></span>

<span data-ttu-id="c213f-109">En cada acuerdo de servicio, debe especificar un proyecto, un id. de acuerdo de servicio y un grupo de acuerdos de servicio.</span><span class="sxs-lookup"><span data-stu-id="c213f-109">In each service agreement, you must specify a project, a service-agreement ID, and a service-agreement group.</span></span> <span data-ttu-id="c213f-110">El grupo de acuerdos de servicio se puede utilizar para ordenar y organizar contratos de servicio.</span><span class="sxs-lookup"><span data-stu-id="c213f-110">The service-agreement group can be used to sort and organize service agreements.</span></span>

<span data-ttu-id="c213f-111">Una cabecera de acuerdo de servicio contiene los parámetros que se aplicarán a todas las líneas del acuerdo vinculadas:</span><span class="sxs-lookup"><span data-stu-id="c213f-111">A service agreement header contains settings that apply to all attached agreement lines:</span></span>

-  <span data-ttu-id="c213f-112">Si se ha suspendido el acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="c213f-112">Whether the service agreement is suspended.</span></span> <span data-ttu-id="c213f-113">Si se ha suspendido el acuerdo de servicio, no se pueden generar pedidos de servicio a partir del acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="c213f-113">If the service agreement is suspended, you cannot generate service orders from the service agreement.</span></span>
-  <span data-ttu-id="c213f-114">La duración del acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="c213f-114">The duration of the service agreement.</span></span>
-  <span data-ttu-id="c213f-115">Cómo se combinarán las líneas del pedido de servicio en los pedidos de servicio.</span><span class="sxs-lookup"><span data-stu-id="c213f-115">How service-order lines are to be combined into service orders.</span></span>
-  <span data-ttu-id="c213f-116">Si el acuerdo de servicio es una plantilla.</span><span class="sxs-lookup"><span data-stu-id="c213f-116">Whether the service agreement is a template.</span></span>

<span data-ttu-id="c213f-117">En la cabecera del acuerdo de servicio, también configurar todos los objetos de servicio y las tareas de servicio que se pueden utilizar con el acuerdo de servicio especificando las tareas o los objetos de servicio específicos que deben estar vinculados a las distintas líneas del acuerdo.</span><span class="sxs-lookup"><span data-stu-id="c213f-117">In the service-agreement header, you also set up all the service objects and service tasks that can be used with the service agreement by entering the specific service tasks or service objects that are to be attached to the various lines of the agreement.</span></span>

<span data-ttu-id="c213f-118">También puede copiar líneas del acuerdo de servicio o líneas de la plantilla de servicio en el acuerdo de servicio actual desde la cabecera del acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="c213f-118">From the service-agreement header, you can also copy service-agreement lines or service-template lines into the current service agreement.</span></span>

<span data-ttu-id="c213f-119">Se pueden suspender acuerdos de servicio y detener líneas de acuerdos de servicio individuales.</span><span class="sxs-lookup"><span data-stu-id="c213f-119">You can suspend service agreements and stop individual service agreement lines.</span></span>

<span data-ttu-id="c213f-120">Si selecciona la casilla **Suspendido** en un contrato de servicio, no podrá:</span><span class="sxs-lookup"><span data-stu-id="c213f-120">If you select the **Suspended** check box on a service agreement, you cannot:</span></span>

-    <span data-ttu-id="c213f-121">Crear automáticamente o manualmente pedidos de servicio para el acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="c213f-121">Create service orders automatically or manually from the service agreement.</span></span>

<span data-ttu-id="c213f-122">Si selecciona la casilla **Detenido** en una línea de contrato de servicio, no podrá:</span><span class="sxs-lookup"><span data-stu-id="c213f-122">If you select the **Stopped** check box on a service agreement line, you cannot:</span></span>

-    <span data-ttu-id="c213f-123">Crear automáticamente o manualmente pedidos de servicio para la línea de acuerdo de servicio.</span><span class="sxs-lookup"><span data-stu-id="c213f-123">Create service orders automatically or manually from the service agreement line.</span></span>
-    <span data-ttu-id="c213f-124">Copiar la línea de acuerdo de servicio en otro acuerdo de servicio o pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="c213f-124">Copy the service agreement line into another service agreement or service order.</span></span>


> [!NOTE]
> <span data-ttu-id="c213f-125">Si se suspende un acuerdo de servicio, se detendrán todas las líneas asociadas a dicho acuerdo independientemente de su estado individual.</span><span class="sxs-lookup"><span data-stu-id="c213f-125">If a service agreement is suspended, all the attached lines are stopped, regardless of their individual status.</span></span>

## <a name="service-agreement-lines"></a><span data-ttu-id="c213f-126">Líneas del acuerdo de servicio</span><span class="sxs-lookup"><span data-stu-id="c213f-126">Service-agreement lines</span></span>

<span data-ttu-id="c213f-127">Las líneas del acuerdo de servicio describen detalladamente el contenido del trabajo de servicio propuesto.</span><span class="sxs-lookup"><span data-stu-id="c213f-127">Each service-agreement line describes in detail the content of the proposed service work.</span></span> <span data-ttu-id="c213f-128">Estas líneas contienen los siguientes parámetros:</span><span class="sxs-lookup"><span data-stu-id="c213f-128">The lines contain the following settings:</span></span>

-  <span data-ttu-id="c213f-129">El tipo de transacción y la descripción del tipo de transacción.</span><span class="sxs-lookup"><span data-stu-id="c213f-129">The transaction type and the description of the transaction type.</span></span>
-  <span data-ttu-id="c213f-130">El empleado que realiza el trabajo de servicio.</span><span class="sxs-lookup"><span data-stu-id="c213f-130">The employee who performs the service work.</span></span>
-  <span data-ttu-id="c213f-131">Los objetos del acuerdo de servicio en los que debe llevarse a cabo el servicio.</span><span class="sxs-lookup"><span data-stu-id="c213f-131">The objects on which service must be performed for the service agreement.</span></span>
-  <span data-ttu-id="c213f-132">La frecuencia con la que se realiza el trabajo y se registran transacciones de artículos, gastos y cuotas asociadas.</span><span class="sxs-lookup"><span data-stu-id="c213f-132">The frequency with which work is performed and associated item, expense, and fee transactions are registered.</span></span>
-  <span data-ttu-id="c213f-133">La ventana de horas en la que pueden agruparse las líneas del pedido de servicio en un pedido de servicio.</span><span class="sxs-lookup"><span data-stu-id="c213f-133">The time window within which service-order lines can be grouped into a service order.</span></span>
-  <span data-ttu-id="c213f-134">Las tareas de servicio utilizadas para agrupar conjuntos de líneas del acuerdo en tareas de trabajo y para describir al técnico de servicio y a los clientes qué tarea de servicio debe proporcionarse.</span><span class="sxs-lookup"><span data-stu-id="c213f-134">The service tasks that are used to group sets of agreement lines together into work tasks and to summarize for service technicians and customers what service task is to be provided.</span></span>
-  <span data-ttu-id="c213f-135">Si se ha detenido una línea.</span><span class="sxs-lookup"><span data-stu-id="c213f-135">Whether a line is stopped.</span></span> <span data-ttu-id="c213f-136">Si se ha detenido una línea, no se pueden crear pedidos de servicio para dicha línea individual.</span><span class="sxs-lookup"><span data-stu-id="c213f-136">If a line is stopped, you cannot create service orders for that individual line.</span></span>
-  <span data-ttu-id="c213f-137">La configuración del proyecto, como la categoría y la propiedad de líneas.</span><span class="sxs-lookup"><span data-stu-id="c213f-137">Project settings, such as the category and the line property.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c213f-138">Temas relacionados</span><span class="sxs-lookup"><span data-stu-id="c213f-138">Related topics</span></span>

[<span data-ttu-id="c213f-139">Crear acuerdos de servicios</span><span class="sxs-lookup"><span data-stu-id="c213f-139">Create service agreements</span></span>](create-service-agreements.md)

