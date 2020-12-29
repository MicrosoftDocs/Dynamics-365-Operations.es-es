---
title: Visión general de crédito y cobros
description: Este tema proporciona una introducción a la funcionalidad de crédito y cobros.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 67e0b3d1058e5fc085f51577ccf0b79e51546de0
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447573"
---
# <a name="credit-and-collections-overview"></a><span data-ttu-id="99330-103">Visión general de crédito y cobros</span><span class="sxs-lookup"><span data-stu-id="99330-103">Credit and collections overview</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="99330-104">Puede administrar los límites de crédito para sus clientes y realizar actividades de cobro cuando sea necesario.</span><span class="sxs-lookup"><span data-stu-id="99330-104">You can manage credit limits for your customers and perform collection activities when they become necessary.</span></span>

## <a name="credit-management"></a><span data-ttu-id="99330-105">Gestión de créditos</span><span class="sxs-lookup"><span data-stu-id="99330-105">Credit management</span></span>

<span data-ttu-id="99330-106">La administración de crédito de cliente le permite administrar los límites de crédito y controlar el flujo de pedidos de ventas mediante el proceso de registro, según las reglas de crédito que cree.</span><span class="sxs-lookup"><span data-stu-id="99330-106">Customer credit management lets you manage credit limits and control the flow of sales orders through the posting process, based on credit rules that you create.</span></span>

<span data-ttu-id="99330-107">El proceso de administración de crédito puede incluir algunos de los pasos siguientes:</span><span class="sxs-lookup"><span data-stu-id="99330-107">The credit management process can include any of the following steps:</span></span>

- <span data-ttu-id="99330-108">Actualizar los atributos de crédito para clientes, a fin de proporcionar información adicional sobre su solvencia.</span><span class="sxs-lookup"><span data-stu-id="99330-108">Update credit attributes for customers to provide additional information about their credit worthiness.</span></span>
- <span data-ttu-id="99330-109">Crear límites de crédito para clientes que utilizan ajustes de límite de crédito.</span><span class="sxs-lookup"><span data-stu-id="99330-109">Create credit limits for customers by using credit limit adjustments.</span></span>
- <span data-ttu-id="99330-110">Crear límites de crédito temporales para clientes que utilizan ajustes de límite de crédito.</span><span class="sxs-lookup"><span data-stu-id="99330-110">Create temporary credit limits for customers by using credit limit adjustments.</span></span> <span data-ttu-id="99330-111">De esta manera, puede aumentar o disminuir temporalmente los límites de crédito del cliente, según los requisitos comerciales.</span><span class="sxs-lookup"><span data-stu-id="99330-111">In this way, you can temporarily increase or decrease customer credit limits, based on business requirements.</span></span>
- <span data-ttu-id="99330-112">Agregar información que pueda afectar al límite de crédito, como información seguros y garantías.</span><span class="sxs-lookup"><span data-stu-id="99330-112">Add information that can affect the credit limit, such as information about insurance and guarantees.</span></span>
- <span data-ttu-id="99330-113">Crear grupos de crédito de clientes que vinculen a los clientes para que puedan compartir un solo límite de crédito.</span><span class="sxs-lookup"><span data-stu-id="99330-113">Create customer credit groups that link customers together so that they share a single credit limit.</span></span>
- <span data-ttu-id="99330-114">Asignar puntuaciones de riesgo a los clientes y luego usar esas puntuaciones para generar automáticamente límites de crédito para esos clientes mediante ajustes de límite de crédito.</span><span class="sxs-lookup"><span data-stu-id="99330-114">Assign risk scores to customers, and then use the scores to automatically generate credit limits for those customers through credit limit adjustments.</span></span>
- <span data-ttu-id="99330-115">Crear reglas de bloqueo que pondrán un pedido en espera durante uno o más procesos de registro en función de factores como el riesgo, las condiciones de pago, los límites de crédito, los importes vencidos y el porcentaje del límite de crédito utilizado.</span><span class="sxs-lookup"><span data-stu-id="99330-115">Create blocking rules that put an order on hold during one or more posting processes, based on factors such as risk, payment terms, credit limits, overdue amounts, and the percentage of the credit limit that has been used.</span></span>
- <span data-ttu-id="99330-116">Administrar una lista de pedidos de ventas que están en espera, revisar los motivos de la retención y mitigar los problemas.</span><span class="sxs-lookup"><span data-stu-id="99330-116">Manage a list of sales orders that are on hold, review the reasons for the hold, and mitigate issues.</span></span>
- <span data-ttu-id="99330-117">Liberar pedidos de ventas para que continúen a través del proceso de registro.</span><span class="sxs-lookup"><span data-stu-id="99330-117">Release sales orders so that they continue through the posting process.</span></span>
- <span data-ttu-id="99330-118">Configurar el flujo de trabajo para administrar la aprobación de los cambios de límite de crédito y las liberaciones de pedidos de ventas.</span><span class="sxs-lookup"><span data-stu-id="99330-118">Set up a workflow to manage the approval of credit limit changes and sales order releases.</span></span>

## <a name="collections-management"></a><span data-ttu-id="99330-119">Gestión de cobros</span><span class="sxs-lookup"><span data-stu-id="99330-119">Collections management</span></span>

<span data-ttu-id="99330-120">La página **Cobros** proporciona una vista centralizada en la que se administra información de cobros de clientes.</span><span class="sxs-lookup"><span data-stu-id="99330-120">The **Collections** page provides a centralized view where accounts receivable collections information is managed.</span></span> <span data-ttu-id="99330-121">Los administradores de cobros pueden usar esta vista centralizada para gestionar los cobros.</span><span class="sxs-lookup"><span data-stu-id="99330-121">Collections managers can use this centralized view to manage collections.</span></span> <span data-ttu-id="99330-122">Los agentes de cobros pueden comenzar el proceso de cobro por las listas de clientes que se generan mediante criterios de cobro predefinidos o por la página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="99330-122">Collections agents can begin the collections process either from customer lists that are generated by using predefined collection criteria or from the **Customers** page.</span></span>

<span data-ttu-id="99330-123">Antes de comenzar a configurar cobros o a trabajar con ellos, debe comprender los siguientes conceptos:</span><span class="sxs-lookup"><span data-stu-id="99330-123">Before you start to set up or work with collections, you should understand the following concepts:</span></span>

- <span data-ttu-id="99330-124">Las instantáneas de vencimiento de los clientes contienen información sobre saldos vencidos en un momento determinado.</span><span class="sxs-lookup"><span data-stu-id="99330-124">Customer aging snapshots contain aged balance information at a specific point in time.</span></span>
- <span data-ttu-id="99330-125">Las secciones de clientes de cobros le ayudan a organizar su trabajo.</span><span class="sxs-lookup"><span data-stu-id="99330-125">Collections customer pools help you organize your work.</span></span>
- <span data-ttu-id="99330-126">Los agentes de cobros tienen sus propias secciones de clientes.</span><span class="sxs-lookup"><span data-stu-id="99330-126">Collections agents can have their own customer pools.</span></span>
- <span data-ttu-id="99330-127">En las páginas de lista se organizan los clientes, las actividades y los casos de cobros.</span><span class="sxs-lookup"><span data-stu-id="99330-127">List pages organize collections customers, activities, and cases.</span></span>
- <span data-ttu-id="99330-128">Toda la información de cobros de un cliente se encuentra en una página, desde donde puede responder.</span><span class="sxs-lookup"><span data-stu-id="99330-128">All collections information for a customer is on one page, and you can take action from that page.</span></span>
- <span data-ttu-id="99330-129">El interés y las cuotas se pueden condonar, restablecer o invertir en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="99330-129">Interest and fees can be waived, reinstated, or reversed in one step.</span></span>
- <span data-ttu-id="99330-130">Se pueden crear transacciones de cancelación en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="99330-130">Write-off transactions can be created in one step.</span></span>
- <span data-ttu-id="99330-131">Se pueden procesar pagos de fondos insuficientes (NSF) en un solo paso.</span><span class="sxs-lookup"><span data-stu-id="99330-131">Not sufficient funds (NSF) payments can be processed in one step.</span></span>

<span data-ttu-id="99330-132">Para ver descripciones de estos conceptos, consulte [Conceptos clave de la administración de cobros](./cm-collections-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="99330-132">For descriptions of these concepts, see [Collections management key concepts](./cm-collections-concepts.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="99330-133">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="99330-133">Additional resources</span></span>

[<span data-ttu-id="99330-134">Configuración de parámetros de la administración de crédito de cliente</span><span class="sxs-lookup"><span data-stu-id="99330-134">Customer credit management parameters setup</span></span>](./cm-credit-mgmt-setup.md)

[<span data-ttu-id="99330-135">Información de configuración de la administración de crédito de cliente</span><span class="sxs-lookup"><span data-stu-id="99330-135">Customer credit management setup information</span></span>](./cm-setup-information.md)

[<span data-ttu-id="99330-136">Agregar información de administración de crédito para un cliente</span><span class="sxs-lookup"><span data-stu-id="99330-136">Add credit management information for a customer</span></span>](./cm-add-credit-mgmt-information-customer.md)

[<span data-ttu-id="99330-137">Grupos de crédito del cliente</span><span class="sxs-lookup"><span data-stu-id="99330-137">Customer credit groups</span></span>](./cm-customer-credit-groups.md)

[<span data-ttu-id="99330-138">Ajustes de límite de crédito de cliente</span><span class="sxs-lookup"><span data-stu-id="99330-138">Customer credit limit adjustments</span></span>](./cm-credit-limit-adjustments.md)

[<span data-ttu-id="99330-139">Retenciones de crédito para pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="99330-139">Credit holds for sales orders</span></span>](./cm-sales-order-credit-holds.md)

[<span data-ttu-id="99330-140">Tareas periódicas de administración de crédito de cliente</span><span class="sxs-lookup"><span data-stu-id="99330-140">Customer credit management periodic tasks</span></span>](./cm-periodic-tasks.md)
