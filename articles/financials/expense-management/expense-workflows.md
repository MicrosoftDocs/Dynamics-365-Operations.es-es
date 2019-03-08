---
title: Configurar flujos de trabajo de los gastos
description: Puede configurar un proceso de flujo de trabajo que se usa para revisar y aprobar documentos de gastos y viajes.
author: ShylaThompson
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WorkflowtableListPageRnr
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8294aaa344e3cb6b79fa4f33f368258ca19c8205
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "355734"
---
# <a name="set-up-workflows-for-expense"></a><span data-ttu-id="e4fa2-103">Configurar flujos de trabajo de los gastos</span><span class="sxs-lookup"><span data-stu-id="e4fa2-103">Set up workflows for expense</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="e4fa2-104"> Puede configurar un proceso de flujo de trabajo que se usa para revisar y aprobar documentos de gastos y viajes.</span><span class="sxs-lookup"><span data-stu-id="e4fa2-104">You can set up a workflow process that is used to review and approve travel and expense documents.</span></span> <span data-ttu-id="e4fa2-105">Los documentos para los que pueden definirse los flujos de trabajo incluyen informes de gastos, pedidos de viaje y solicitudes de anticipo.</span><span class="sxs-lookup"><span data-stu-id="e4fa2-105">The documents for which workflows can be defined include expense reports, travel requisitions, and cash advance requests.</span></span>

<span data-ttu-id="e4fa2-106">Un flujo de trabajo representa un proceso empresarial.</span><span class="sxs-lookup"><span data-stu-id="e4fa2-106">A workflow represents a business process.</span></span> <span data-ttu-id="e4fa2-107">El flujo de trabajo define cómo se gestiona un documento en el sistema e indica quién debe completar una tarea o aprobar un documento.</span><span class="sxs-lookup"><span data-stu-id="e4fa2-107">It defines how a document flows through the system and indicates who must complete a task or approve a document.</span></span> <span data-ttu-id="e4fa2-108">El uso del sistema de flujo de trabajo en su organización le ofrece varias ventajas:</span><span class="sxs-lookup"><span data-stu-id="e4fa2-108">There are several benefits of using the workflow system in your organization:</span></span>

-   <span data-ttu-id="e4fa2-109">**Procesos coherentes**: puede definir el proceso de aprobación para documentos específicos como, por ejemplo, solicitudes de compra e informes de gastos.</span><span class="sxs-lookup"><span data-stu-id="e4fa2-109">**Consistent processes** — You can define the approval process for specific documents, such as purchase requisitions and expense reports.</span></span> <span data-ttu-id="e4fa2-110">El sistema de flujo de trabajo le ayuda a garantizar que los documentos se procesan y se aprueban de manera coherente y eficaz.</span><span class="sxs-lookup"><span data-stu-id="e4fa2-110">Using the workflow system helps to ensure that documents are processed and approved in a consistent and efficient manner.</span></span>

-   <span data-ttu-id="e4fa2-111">Visibilidad de procesos: puede realizar el seguimiento del estado, el historial y las medidas de rendimiento de una instancia de flujo de trabajo determinada.</span><span class="sxs-lookup"><span data-stu-id="e4fa2-111">Process visibility — You can track the status, history, and performance metrics of a specific workflow instance.</span></span> <span data-ttu-id="e4fa2-112">De este modo puede determinar si los cambios deben realizarse en el flujo de trabajo para mejorar la eficacia.</span><span class="sxs-lookup"><span data-stu-id="e4fa2-112">This helps you determine whether changes should be made to the workflow to improve efficiency.</span></span>

-   <span data-ttu-id="e4fa2-113">Lista de trabajo centralizada: los usuarios pueden ver una lista de trabajo centralizada para ver las tareas y aprobaciones de flujo de trabajo que tienen asignadas.</span><span class="sxs-lookup"><span data-stu-id="e4fa2-113">Centralized work list — Users can view a centralized work list to view the workflow tasks and approvals assigned to them.</span></span> 

<span data-ttu-id="e4fa2-114">**Tipos de flujo de trabajo que puede crear**</span><span class="sxs-lookup"><span data-stu-id="e4fa2-114">**The types of workflows you can create**</span></span>

<span data-ttu-id="e4fa2-115">En la siguiente tabla se describen los tipos de flujo de trabajo que se pueden crear en **Gastos**.</span><span class="sxs-lookup"><span data-stu-id="e4fa2-115">The following table lists the types of workflows that you can create in **Expense**.</span></span>


|              <span data-ttu-id="e4fa2-116"><strong>Tipo</strong></span><span class="sxs-lookup"><span data-stu-id="e4fa2-116"><strong>Type</strong></span></span>              |                   <span data-ttu-id="e4fa2-117"><strong>Use este tipo para</strong></span><span class="sxs-lookup"><span data-stu-id="e4fa2-117"><strong>Use this type to</strong></span></span>                   |
|-------------------------------------------------|-----------------------------------------------------------------------|
|         <span data-ttu-id="e4fa2-118"><strong>Informe de gastos</strong></span><span class="sxs-lookup"><span data-stu-id="e4fa2-118"><strong>Expense report</strong></span></span>         |            <span data-ttu-id="e4fa2-119">Cree flujos de trabajo de aprobación para los informes de gastos.</span><span class="sxs-lookup"><span data-stu-id="e4fa2-119">Create approval workflows for expense reports.</span></span>             |
|  <span data-ttu-id="e4fa2-120"><strong>Registro automático de informe de gastos</strong></span><span class="sxs-lookup"><span data-stu-id="e4fa2-120"><strong>Expense report auto posting</strong></span></span>   |        <span data-ttu-id="e4fa2-121">Cree flujos de trabajo del registro automático para los informes de gastos.</span><span class="sxs-lookup"><span data-stu-id="e4fa2-121">Create automatic posting workflows for expense reports.</span></span>        |
|       <span data-ttu-id="e4fa2-122"><strong>Elemento de línea de gastos</strong></span><span class="sxs-lookup"><span data-stu-id="e4fa2-122"><strong>Expense line item</strong></span></span>        |     <span data-ttu-id="e4fa2-123">Cree flujos de trabajo de aprobación para los artículos de línea en los informes de gastos.</span><span class="sxs-lookup"><span data-stu-id="e4fa2-123">Create approval workflows for line items on expense reports.</span></span>      |
| <span data-ttu-id="e4fa2-124"><strong>Registro automático de artículo de línea de gasto</strong></span><span class="sxs-lookup"><span data-stu-id="e4fa2-124"><strong>Expense line item auto posting</strong></span></span> | <span data-ttu-id="e4fa2-125">Cree flujos de trabajo de registro automático para los artículos de línea en los informes de gastos.</span><span class="sxs-lookup"><span data-stu-id="e4fa2-125">Create automatic posting workflows for line items on expense reports.</span></span> |
|       <span data-ttu-id="e4fa2-126"><strong>Pedido de viaje</strong></span><span class="sxs-lookup"><span data-stu-id="e4fa2-126"><strong>Travel requisition</strong></span></span>       |          <span data-ttu-id="e4fa2-127">Cree flujos de trabajo de aprobación para solicitudes de viaje.</span><span class="sxs-lookup"><span data-stu-id="e4fa2-127">Create approval workflows for travel requisitions.</span></span>           |
|      <span data-ttu-id="e4fa2-128"><strong>Solicitud de anticipo</strong></span><span class="sxs-lookup"><span data-stu-id="e4fa2-128"><strong>Cash advance request</strong></span></span>      |         <span data-ttu-id="e4fa2-129">Cree flujos de aprobación para las solicitudes de anticipo.</span><span class="sxs-lookup"><span data-stu-id="e4fa2-129">Create approval workflows for cash advance requests.</span></span>          |
|        <span data-ttu-id="e4fa2-130"><strong>Devolución de impuestos de IVA</strong></span><span class="sxs-lookup"><span data-stu-id="e4fa2-130"><strong>VAT tax recovery</strong></span></span>        | <span data-ttu-id="e4fa2-131">Cree flujos de trabajo de aprobación para la devolución del impuesto sobre el valor añadido (VAT).</span><span class="sxs-lookup"><span data-stu-id="e4fa2-131">Create approval workflows for the recovery of value-added tax (VAT).</span></span>  |

