---
title: Visión general de la gestión de servicio
description: Use Gestión de servicio para establecer acuerdos de servicio y suscripciones de servicio, gestionar pedidos de servicio y consultas de clientes y administrar y analizar la entrega de servicios a clientes.
author: ShylaThompson
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dd2f27c5797fbd34674e39013ed3e0e40cdb28b2
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251141"
---
# <a name="service-management-overview"></a><span data-ttu-id="ae38c-103">Visión general de la gestión de servicio</span><span class="sxs-lookup"><span data-stu-id="ae38c-103">Service management overview</span></span>

[!include [banner](../includes/banner.md)]


<span data-ttu-id="ae38c-104">Use **Gestión de servicio** para establecer acuerdos de servicio y suscripciones de servicio, gestionar pedidos de servicio y consultas de clientes y administrar y analizar la entrega de servicios a clientes.</span><span class="sxs-lookup"><span data-stu-id="ae38c-104">Use **Service management** to establish service agreements and service subscriptions, handle service orders and customer inquiries, and to manage and analyze the delivery of services to customers.</span></span> <span data-ttu-id="ae38c-105">Puede usar acuerdos de servicio para definir los recursos utilizados en una visita de servicio habitual.</span><span class="sxs-lookup"><span data-stu-id="ae38c-105">You can use service agreements to define the resources that are used in a typical service visit.</span></span> <span data-ttu-id="ae38c-106">También puede usarlos para ver cómo se facturan dichos recursos al cliente.</span><span class="sxs-lookup"><span data-stu-id="ae38c-106">You can also use service agreements to view how those resources are invoiced to the customer.</span></span> <span data-ttu-id="ae38c-107">Un acuerdo de servicio también puede incluir un contrato de nivel de servicio que especifique los tiempos estándar de respuesta y ofrece herramientas para registrar el tiempo real.</span><span class="sxs-lookup"><span data-stu-id="ae38c-107">A service agreement can also include a service level agreement that specifies standard response times, and offers tools to record the actual time.</span></span>

<span data-ttu-id="ae38c-108">Puede crear pedidos de servicio para administrar la información acerca de visitas programadas y no programadas por un técnico de servicio al sitio de un cliente.</span><span class="sxs-lookup"><span data-stu-id="ae38c-108">You can create service orders to manage information about scheduled and unscheduled visits by a service technician to a customer site.</span></span> <span data-ttu-id="ae38c-109">Los pedidos de servicio incluyen información como:</span><span class="sxs-lookup"><span data-stu-id="ae38c-109">Service orders include information such as:</span></span>

1.  <span data-ttu-id="ae38c-110">El número de horas de trabajo que realizará el técnico de servicio</span><span class="sxs-lookup"><span data-stu-id="ae38c-110">The hours of work that the service technician will perform</span></span>

2.  <span data-ttu-id="ae38c-111">El tipo de servicio y reparación</span><span class="sxs-lookup"><span data-stu-id="ae38c-111">The type of service or repair</span></span>

3.  <span data-ttu-id="ae38c-112">El artículo que se va a reparar, lo que incluye los detalles sobre los síntomas y el diagnóstico</span><span class="sxs-lookup"><span data-stu-id="ae38c-112">The item to repair, including details about the symptoms and diagnosis</span></span>

4.  <span data-ttu-id="ae38c-113">Los gastos y cuotas relacionados con el servicio o la reparación</span><span class="sxs-lookup"><span data-stu-id="ae38c-113">Any expenses and fees related to the service or repair</span></span>

<span data-ttu-id="ae38c-114">Puede recibir, procesar y atender solicitudes de servicio.</span><span class="sxs-lookup"><span data-stu-id="ae38c-114">You can receive, process, and dispatch service requests.</span></span> <span data-ttu-id="ae38c-115">Una vez haya creado un pedido de servicio, puede usar las etapas de servicio para controlar el progreso y especificar las reglas que controlen las acciones que están habilitadas en cada etapa.</span><span class="sxs-lookup"><span data-stu-id="ae38c-115">After you have created a service order, you can use service stages to monitor progress and specify rules that control what actions are enabled in each stage.</span></span> <span data-ttu-id="ae38c-116">Una vez completado el pedido de servicio, puede aprobar el pedido para confirmar que está completo y después registrarlo para iniciar el proceso de facturación.</span><span class="sxs-lookup"><span data-stu-id="ae38c-116">When a service order is complete, you can sign off on the order to confirm that it is complete, and then post the order to start the invoice process.</span></span>

<span data-ttu-id="ae38c-117">Use las herramientas de informes para controlar los márgenes de pedidos de servicio y las transacciones de suscripción e imprimir descripciones y recepciones de trabajo.</span><span class="sxs-lookup"><span data-stu-id="ae38c-117">Use the reporting tools to monitor service order margins and subscription transactions, and print work descriptions and work receipts.</span></span>

## <a name="business-processes"></a><span data-ttu-id="ae38c-118">Procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="ae38c-118">Business processes</span></span>

<span data-ttu-id="ae38c-119">El siguiente diagrama muestra los procesos empresariales de alto nivel para la **Gestión de servicio** y muestra en qué lugar se integran los procesos de servicio con otros módulos.</span><span class="sxs-lookup"><span data-stu-id="ae38c-119">The following diagram illustrates the high level business processes for **Service management**, and shows where service processes integrate with other modules.</span></span>

<span data-ttu-id="ae38c-120">[![Diagrama de proceso empresarial de Gestión de servicio](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span><span class="sxs-lookup"><span data-stu-id="ae38c-120">[![Service management business process diagram](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span></span>

## <a name="service-management-at-a-glance"></a><span data-ttu-id="ae38c-121">Panorama general de la gestión de servicio</span><span class="sxs-lookup"><span data-stu-id="ae38c-121">Service management at a glance</span></span>

|<span data-ttu-id="ae38c-122">Tareas importantes</span><span class="sxs-lookup"><span data-stu-id="ae38c-122">Important tasks</span></span>           | <span data-ttu-id="ae38c-123">Páginas principales</span><span class="sxs-lookup"><span data-stu-id="ae38c-123">Primary pages</span></span>                         |<span data-ttu-id="ae38c-124">Informes preferidos</span><span class="sxs-lookup"><span data-stu-id="ae38c-124">Popular reports</span></span>              |
|--------------------------|---------------------------------------|-----------------------------|
|<span data-ttu-id="ae38c-125">Cumplir con los acuerdos de servicio</span><span class="sxs-lookup"><span data-stu-id="ae38c-125">Fulfill service agreements</span></span>|<span data-ttu-id="ae38c-126">Contratos de servicio</span><span class="sxs-lookup"><span data-stu-id="ae38c-126">Service agreements</span></span>                     |<span data-ttu-id="ae38c-127">Margen de pedido de servicio</span><span class="sxs-lookup"><span data-stu-id="ae38c-127">Service order margin</span></span>         |
|<span data-ttu-id="ae38c-128">Gestionar consultas de clientes</span><span class="sxs-lookup"><span data-stu-id="ae38c-128">Handle customer inquiries</span></span> |<span data-ttu-id="ae38c-129">Pedidos de servicio</span><span class="sxs-lookup"><span data-stu-id="ae38c-129">Service orders</span></span>                         |<span data-ttu-id="ae38c-130">Descripción del trabajo</span><span class="sxs-lookup"><span data-stu-id="ae38c-130">Work description</span></span>             |
|                          |<span data-ttu-id="ae38c-131">Panel de distribución</span><span class="sxs-lookup"><span data-stu-id="ae38c-131">Dispatch board</span></span>                         |<span data-ttu-id="ae38c-132">Transacción - suscripción</span><span class="sxs-lookup"><span data-stu-id="ae38c-132">Transaction - subscription</span></span>   |
|                          |                                       |<span data-ttu-id="ae38c-133">Transacciones de cuotas de suscripciones</span><span class="sxs-lookup"><span data-stu-id="ae38c-133">Subscription fee transactions</span></span>|


## <a name="integration-of-service-management"></a><span data-ttu-id="ae38c-134">Integración de la Gestión de servicio</span><span class="sxs-lookup"><span data-stu-id="ae38c-134">Integration of Service management</span></span>

<span data-ttu-id="ae38c-135">La gestión de servicio puede estar integrada con los siguientes módulos:</span><span class="sxs-lookup"><span data-stu-id="ae38c-135">Service management can be integrated with the following modules:</span></span>

  - [<span data-ttu-id="ae38c-136">Ventas y marketing</span><span class="sxs-lookup"><span data-stu-id="ae38c-136">Sales and marketing</span></span>](../sales-marketing/overview-sales-marketing.md)
  - [<span data-ttu-id="ae38c-137">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="ae38c-137">Human resources</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/index)

  

