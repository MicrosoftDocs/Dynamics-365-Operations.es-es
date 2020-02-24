---
title: Administración de crédito de clientes
description: ''
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
ms.author: mfalkner
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 11da8b7fb59bc8f3e2568ada27db753cc815b9c2
ms.sourcegitcommit: 6a70f9ac296158edd065d52a12703b3ce85ce5ee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/03/2020
ms.locfileid: "3015383"
---
# <a name="customer-credit-management-overview"></a><span data-ttu-id="2b6b3-102">Información general sobre la administración de crédito de clientes</span><span class="sxs-lookup"><span data-stu-id="2b6b3-102">Customer credit management overview</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

<span data-ttu-id="2b6b3-103">La administración del crédito de clientes le permite administrar los límites de crédito y controlar el flujo de pedidos de ventas mediante el proceso de contabilización según las reglas de crédito que cree.</span><span class="sxs-lookup"><span data-stu-id="2b6b3-103">Customer credit management allows you to manage credit limits and control the flow of sales orders through the posting process based on credit rules that you create.</span></span> 

<span data-ttu-id="2b6b3-104">El proceso para usar la administración de crédito puede incluir algunos de los pasos siguientes (o todos ellos):</span><span class="sxs-lookup"><span data-stu-id="2b6b3-104">The process for using credit management can include some or all of the following steps:</span></span>
- <span data-ttu-id="2b6b3-105">Actualizar clientes con atributos de crédito que proporcionen información adicional sobre su solvencia</span><span class="sxs-lookup"><span data-stu-id="2b6b3-105">Update customers with credit attributes that provide additional information about their credit worthiness</span></span> 
- <span data-ttu-id="2b6b3-106">Crear límites de crédito para clientes que utilizan ajustes de límite de crédito</span><span class="sxs-lookup"><span data-stu-id="2b6b3-106">Create credit limits for customers using credit limit adjustments</span></span>
- <span data-ttu-id="2b6b3-107">Crear límites de crédito temporales para los clientes que usen ajustes de límite de crédito cuando desee aumentar o disminuir su límite de crédito temporalmente en función de las necesidades comerciales</span><span class="sxs-lookup"><span data-stu-id="2b6b3-107">Create temporary credit limits for customers using credit limit adjustments when you want to increase or decrease their credit limit temporarily based on business needs</span></span>
- <span data-ttu-id="2b6b3-108">Agregar información adicional que pueda afectar el límite de crédito, como seguros y garantías.</span><span class="sxs-lookup"><span data-stu-id="2b6b3-108">Add additional information that can affect the credit limit such as insurance and guarantees</span></span>
- <span data-ttu-id="2b6b3-109">Crear grupos de crédito de clientes que vinculen a los clientes para que puedan compartir un solo límite de crédito</span><span class="sxs-lookup"><span data-stu-id="2b6b3-109">Create customer credit groups that link customers together so they can share a single credit limit</span></span>
- <span data-ttu-id="2b6b3-110">Asignar puntuaciones de riesgo a los clientes y luego usar esos puntuaciones para generar automáticamente límites de crédito para los clientes mediante ajustes de límite de crédito</span><span class="sxs-lookup"><span data-stu-id="2b6b3-110">Assign risk scores to customers and then use those scores to automatically generate credit limits for customers using credit limit adjustments</span></span>
- <span data-ttu-id="2b6b3-111">Crear reglas de bloqueo que pondrán un pedido en espera durante uno o más procesos de contabilización en función de factores como el riesgo, las condiciones de pago, los límites de crédito, los importes vencidos y el porcentaje del límite de crédito utilizado.</span><span class="sxs-lookup"><span data-stu-id="2b6b3-111">Create blocking rules that will place an order on hold during one or more posting processes based on factors such as risk, payment terms, credit limits, overdue amounts, and percentage of credit limit used</span></span>
- <span data-ttu-id="2b6b3-112">Administrar una lista de pedidos de ventas que están en espera, revisar los motivos de la retención y mitigar los problemas</span><span class="sxs-lookup"><span data-stu-id="2b6b3-112">Manage a list of sales orders that are on hold, review the reasons for the hold, and mitigate the issues</span></span>
- <span data-ttu-id="2b6b3-113">Liberar pedidos de ventas y permitir que continúen a través del proceso de contabilización</span><span class="sxs-lookup"><span data-stu-id="2b6b3-113">Release sales orders and allow it to continue through the posting process</span></span>
- <span data-ttu-id="2b6b3-114">Configurar el flujo de trabajo para administrar la aprobación de los cambios de límite de crédito y las liberaciones de pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="2b6b3-114">Set up workflow to manage the approval of credit limit changes and sales order releases</span></span>


<a name="additional-resources"></a><span data-ttu-id="2b6b3-115">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="2b6b3-115">Additional resources</span></span>
--------
[<span data-ttu-id="2b6b3-116">Configuración de parámetros de la administración de crédito de cliente</span><span class="sxs-lookup"><span data-stu-id="2b6b3-116">Customer credit management parameters setup</span></span>](./cm-credit-mgmt-setup.md)

[<span data-ttu-id="2b6b3-117">Información de configuración de la administración de crédito de cliente</span><span class="sxs-lookup"><span data-stu-id="2b6b3-117">Customer credit management setup information</span></span>](./cm-setup-information.md)

[<span data-ttu-id="2b6b3-118">Agregar información de administración de crédito para un cliente</span><span class="sxs-lookup"><span data-stu-id="2b6b3-118">Add credit management information for a customer</span></span>](./cm-add-credit-mgmt-information-customer.md)

[<span data-ttu-id="2b6b3-119">Grupos de crédito del cliente</span><span class="sxs-lookup"><span data-stu-id="2b6b3-119">Customer credit groups</span></span>](./cm-customer-credit-groups.md)

[<span data-ttu-id="2b6b3-120">Ajustes de límite de crédito de cliente</span><span class="sxs-lookup"><span data-stu-id="2b6b3-120">Customer credit limit adjustments</span></span>](./cm-credit-limit-adjustments.md)

[<span data-ttu-id="2b6b3-121">Retenciones de crédito para pedidos de ventas</span><span class="sxs-lookup"><span data-stu-id="2b6b3-121">Credit holds for sales orders</span></span>](./cm-sales-order-credit-holds.md)

[<span data-ttu-id="2b6b3-122">Tareas periódicas de administración de crédito de cliente</span><span class="sxs-lookup"><span data-stu-id="2b6b3-122">Customer credit management periodic tasks</span></span>](./cm-periodic-tasks.md)


