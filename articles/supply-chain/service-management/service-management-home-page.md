---
title: "Gestión de servicio"
description: "Use Gestión de servicio para establecer acuerdos de servicio y suscripciones de servicio, gestionar pedidos de servicio y consultas de clientes y administrar y analizar la entrega de servicios a clientes."
author: YuyuScheller
manager: AnnBe
ms.date: 05/09/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMAServiceOrderTable
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
ms.sourcegitcommit: 02cdf4615e2071f2b7de2e86b6f9e6637c6e5d8d
ms.openlocfilehash: 236ab21b2d1c5a4e82270e5381d163e97437cb7f
ms.contentlocale: es-es
ms.lasthandoff: 05/09/2018

---


# <a name="service-management"></a><span data-ttu-id="a100a-103">Gestión de servicio</span><span class="sxs-lookup"><span data-stu-id="a100a-103">Service management</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="a100a-104">Use **Gestión de servicio** para establecer acuerdos de servicio y suscripciones de servicio, gestionar pedidos de servicio y consultas de clientes y administrar y analizar la entrega de servicios a clientes.</span><span class="sxs-lookup"><span data-stu-id="a100a-104">Use **Service management** to establish service agreements and service subscriptions, handle service orders and customer inquiries, and to manage and analyze the delivery of services to customers.</span></span> <span data-ttu-id="a100a-105">Puede usar acuerdos de servicio para definir los recursos utilizados en una visita de servicio habitual.</span><span class="sxs-lookup"><span data-stu-id="a100a-105">You can use service agreements to define the resources that are used in a typical service visit.</span></span> <span data-ttu-id="a100a-106">También puede usarlos para ver cómo se facturan dichos recursos al cliente.</span><span class="sxs-lookup"><span data-stu-id="a100a-106">You can also use service agreements to view how those resources are invoiced to the customer.</span></span> <span data-ttu-id="a100a-107">Un acuerdo de servicio también puede incluir un contrato de nivel de servicio que especifique los tiempos estándar de respuesta y ofrece herramientas para registrar el tiempo real.</span><span class="sxs-lookup"><span data-stu-id="a100a-107">A service agreement can also include a service level agreement that specifies standard response times, and offers tools to record the actual time.</span></span>

<span data-ttu-id="a100a-108">Puede crear pedidos de servicio para administrar la información acerca de visitas programadas y no programadas por un técnico de servicio al sitio de un cliente.</span><span class="sxs-lookup"><span data-stu-id="a100a-108">You can create service orders to manage information about scheduled and unscheduled visits by a service technician to a customer site.</span></span> <span data-ttu-id="a100a-109">Los pedidos de servicio incluyen información como:</span><span class="sxs-lookup"><span data-stu-id="a100a-109">Service orders include information such as:</span></span>

1.  <span data-ttu-id="a100a-110">El número de horas de trabajo que realizará el técnico de servicio</span><span class="sxs-lookup"><span data-stu-id="a100a-110">The hours of work that the service technician will perform</span></span>

2.  <span data-ttu-id="a100a-111">El tipo de servicio y reparación</span><span class="sxs-lookup"><span data-stu-id="a100a-111">The type of service or repair</span></span>

3.  <span data-ttu-id="a100a-112">El artículo que se va a reparar, lo que incluye los detalles sobre los síntomas y el diagnóstico</span><span class="sxs-lookup"><span data-stu-id="a100a-112">The item to repair, including details about the symptoms and diagnosis</span></span>

4.  <span data-ttu-id="a100a-113">Los gastos y cuotas relacionados con el servicio o la reparación</span><span class="sxs-lookup"><span data-stu-id="a100a-113">Any expenses and fees related to the service or repair</span></span>

<span data-ttu-id="a100a-114">Los clientes pueden enviar sus solicitudes de servicio por Internet mediante Enterprise Portal.</span><span class="sxs-lookup"><span data-stu-id="a100a-114">Customers can submit service requests through the Internet by using the Enterprise Portal.</span></span> <span data-ttu-id="a100a-115">Puede recibir, procesar y atender dichas solicitudes.</span><span class="sxs-lookup"><span data-stu-id="a100a-115">You can receive, process, and dispatch these requests.</span></span> <span data-ttu-id="a100a-116">Una vez haya creado un pedido de servicio, puede usar las etapas de servicio para controlar el progreso y especificar las reglas que controlen las acciones que están habilitadas en cada etapa.</span><span class="sxs-lookup"><span data-stu-id="a100a-116">After you have created a service order, you can use service stages to monitor progress and specify rules that control what actions are enabled in each stage.</span></span> <span data-ttu-id="a100a-117">Una vez completado el pedido de servicio, puede aprobar el pedido para confirmar que está completo y después registrarlo para iniciar el proceso de facturación.</span><span class="sxs-lookup"><span data-stu-id="a100a-117">When a service order is complete, you can sign off on the order to confirm that it is complete, and then post the order to start the invoice process.</span></span>

<span data-ttu-id="a100a-118">Use las herramientas de informes para controlar los márgenes de pedidos de servicio y las transacciones de suscripción e imprimir descripciones y recepciones de trabajo.</span><span class="sxs-lookup"><span data-stu-id="a100a-118">Use the reporting tools to monitor service order margins and subscription transactions, and print work descriptions and work receipts.</span></span>

## <a name="business-processes"></a><span data-ttu-id="a100a-119">Procesos empresariales</span><span class="sxs-lookup"><span data-stu-id="a100a-119">Business processes</span></span>

<span data-ttu-id="a100a-120">El siguiente diagrama muestra los procesos empresariales de alto nivel para la **Gestión de servicio**, y muestra en qué lugar se integran los procesos de servicio con otros módulos de Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="a100a-120">The following diagram illustrates the high level business processes for **Service management**, and shows where service processes integrate with other modules in Microsoft Dynamics 365 for Finance and Operations.</span></span>

<span data-ttu-id="a100a-121">[![Diagrama de proceso empresarial de Gestión de servicio](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span><span class="sxs-lookup"><span data-stu-id="a100a-121">[![Service management business process diagram](./media/sm_home_page.gif)](./media/sm_home_page.gif)</span></span>

## <a name="service-management-at-a-glance"></a><span data-ttu-id="a100a-122">Panorama general de la gestión de servicio</span><span class="sxs-lookup"><span data-stu-id="a100a-122">Service management at a glance</span></span>

<table>
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p><span data-ttu-id="a100a-123">Tareas importantes</span><span class="sxs-lookup"><span data-stu-id="a100a-123">Important tasks</span></span></p></th>
<th><p><span data-ttu-id="a100a-124">Formularios principales</span><span class="sxs-lookup"><span data-stu-id="a100a-124">Primary forms</span></span></p></th>
<th><p><span data-ttu-id="a100a-125">Informes preferidos</span><span class="sxs-lookup"><span data-stu-id="a100a-125">Popular reports</span></span></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a100a-126">Cumplir con los acuerdos de servicio</span><span class="sxs-lookup"><span data-stu-id="a100a-126">Fulfill service agreements</span></span></a></p></td>
<td><p><span data-ttu-id="a100a-127"><a href="https://technet.microsoft.com/en-us/library/aa617823(v=ax.60)">Acuerdos de servicio (formulario)</a></span><span class="sxs-lookup"><span data-stu-id="a100a-127"><a href="https://technet.microsoft.com/en-us/library/aa617823(v=ax.60)">Service agreements (form)</a></span></span></p></td>
<td><p><span data-ttu-id="a100a-128"><strong>Margen de pedido de servicio</strong></span><span class="sxs-lookup"><span data-stu-id="a100a-128"><strong>Service order margin</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a100a-129">Gestionar consultas de clientes</span><span class="sxs-lookup"><span data-stu-id="a100a-129">Handle customer inquiries</span></span></a></p></td>
<td><p><span data-ttu-id="a100a-130"><a href="https://technet.microsoft.com/en-us/library/aa554361(v=ax.60)">Pedidos de servicio (formulario)</a></span><span class="sxs-lookup"><span data-stu-id="a100a-130"><a href="https://technet.microsoft.com/en-us/library/aa554361(v=ax.60)">Service orders (form)</a></span></span></p></td>
<td><p><span data-ttu-id="a100a-131"><strong>Descripción del trabajo</strong></span><span class="sxs-lookup"><span data-stu-id="a100a-131"><strong>Work description</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><span data-ttu-id="a100a-132"><a href="https://technet.microsoft.com/en-us/library/hh242789(v=ax.60)">Panel de distribución (formulario)</a></span><span class="sxs-lookup"><span data-stu-id="a100a-132"><a href="https://technet.microsoft.com/en-us/library/hh242789(v=ax.60)">Dispatch board (form)</a></span></span></p></td>
<td><p><span data-ttu-id="a100a-133"><strong>Transacción - suscripción</strong></span><span class="sxs-lookup"><span data-stu-id="a100a-133"><strong>Transaction - subscription</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p></p></td>
<td><p><span data-ttu-id="a100a-134"><strong>Transacciones de cuotas de suscripciones</strong></span><span class="sxs-lookup"><span data-stu-id="a100a-134"><strong>Subscription fee transactions</strong></span></span></p></td>
</tr>
</tbody>
</table>


## <a name="integration-of-service-management"></a><span data-ttu-id="a100a-135">Integración de la Gestión de servicio</span><span class="sxs-lookup"><span data-stu-id="a100a-135">Integration of Service management</span></span>

<span data-ttu-id="a100a-136">La gestión de servicio se puede integrar con los siguientes módulos de Microsoft Dynamics 365 for Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="a100a-136">Service management can be integrated with the following modules in Microsoft Dynamics 365 for Finance and Operations:</span></span>

  - [<span data-ttu-id="a100a-137">Ventas y marketing</span><span class="sxs-lookup"><span data-stu-id="a100a-137">Sales and marketing</span></span>](../sales-marketing/overview-sales-marketing.md)

  - [<span data-ttu-id="a100a-138">Recursos humanos</span><span class="sxs-lookup"><span data-stu-id="a100a-138">Human resources</span></span>](https://docs.microsoft.com/en-us/dynamics365/unified-operations/talent/index)

  


