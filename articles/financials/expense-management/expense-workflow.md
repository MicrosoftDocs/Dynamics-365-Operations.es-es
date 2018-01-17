---
title: Flujo de trabajo de gastos
description: "En este tema se explica cómo puede usar el sistema de flujo de trabajo en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, para configurar un proceso de revisión de los informes de gastos en Gestión de gastos."
author: saraschi2
manager: AnnBe
ms.date: 09/13/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom:
- month/year of release that feature was introduced in
- in format yyyy-mm-dd
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: 58361d605080acd2c26bd021e50f9749ecccc517
ms.contentlocale: es-es
ms.lasthandoff: 01/17/2018

---

# <a name="expense-workflow"></a><span data-ttu-id="e2eb5-103">Flujo de trabajo de gastos</span><span class="sxs-lookup"><span data-stu-id="e2eb5-103">Expense workflow</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="e2eb5-104">Puede usar el sistema de flujo de trabajo en Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, para configurar un proceso de revisión de los informes de gastos en Gestión de gastos.</span><span class="sxs-lookup"><span data-stu-id="e2eb5-104">You can use the workflow system in Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, to set up a review process for expense reports in Expense management.</span></span> <span data-ttu-id="e2eb5-105">Puede configurar un flujo de trabajo que use los siguientes criterios para determinar quién aprueba los informes de gastos:</span><span class="sxs-lookup"><span data-stu-id="e2eb5-105">You can set up a workflow that uses the following criteria to determine who approves expense reports:</span></span>

- <span data-ttu-id="e2eb5-106">El empleado que notifica la jerarquía y los límites de aprobación predeterminados</span><span class="sxs-lookup"><span data-stu-id="e2eb5-106">The employee reporting hierarchy and predefined approval limits</span></span>
- <span data-ttu-id="e2eb5-107">Aprobación de varios niveles que admite aprobadores provisionales y un aprobador final</span><span class="sxs-lookup"><span data-stu-id="e2eb5-107">Multi-level approval that supports interim approvers and a final approver</span></span>
- <span data-ttu-id="e2eb5-108">Las dimensiones financieras y la responsabilidad del proyecto</span><span class="sxs-lookup"><span data-stu-id="e2eb5-108">Financial dimensions and project responsibility</span></span>
- <span data-ttu-id="e2eb5-109">La asignación a usuarios o grupos de usuarios específicos</span><span class="sxs-lookup"><span data-stu-id="e2eb5-109">Assignment to specific users or user groups</span></span>

<span data-ttu-id="e2eb5-110">Las aprobaciones de flujo de trabajo se pueden crear para los informes de gastos, las solicitudes de viaje, los anticipos y la recuperación del impuesto sobre el valor añadido (IVA).</span><span class="sxs-lookup"><span data-stu-id="e2eb5-110">Workflow approvals can be created for expense reports, travel requisitions, cash advances, and value-added tax (VAT) recovery.</span></span>

<span data-ttu-id="e2eb5-111">**Ejemplo**</span><span class="sxs-lookup"><span data-stu-id="e2eb5-111">**Example**</span></span>

<span data-ttu-id="e2eb5-112">El siguiente proceso muestra un ejemplo del flujo de trabajo de gestión de gastos para un informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="e2eb5-112">The following process is an example of the expense management workflow for an expense report.</span></span>

1. <span data-ttu-id="e2eb5-113">Un empleado crea y guarda un informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="e2eb5-113">An employee creates and saves an expense report.</span></span>
2. <span data-ttu-id="e2eb5-114">El empleado envía el informe de gastos para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="e2eb5-114">The employee submits the expense report for approval.</span></span> <span data-ttu-id="e2eb5-115">Se identifica al aprobador según las reglas definidas cuando se configuró el flujo de trabajo.</span><span class="sxs-lookup"><span data-stu-id="e2eb5-115">The approver is identified based on the rules that were defined when the workflow was set up.</span></span>
3. <span data-ttu-id="e2eb5-116">El aprobador recibe una notificación de que el informe de gastos está listo para su aprobación.</span><span class="sxs-lookup"><span data-stu-id="e2eb5-116">The approver receives a notification that an expense report is ready for approval.</span></span> <span data-ttu-id="e2eb5-117">El aprobador revisa el informe de gastos y comprueba que las siguientes condiciones se cumplan:</span><span class="sxs-lookup"><span data-stu-id="e2eb5-117">The approver reviews the expense report and verifies that the following conditions are met:</span></span>

    - <span data-ttu-id="e2eb5-118">Que los gastos no infrinjan ninguna directiva de gastos.</span><span class="sxs-lookup"><span data-stu-id="e2eb5-118">The expenses don't violate any expense policies.</span></span> <span data-ttu-id="e2eb5-119">Si un gasto infringe una directiva, el aprobador comprueba que se incluye una justificación comercial válida en el informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="e2eb5-119">If an expense violates a policy, the approver verifies that the expense report includes a valid business justification.</span></span>
    - <span data-ttu-id="e2eb5-120">Se vinculan recibos electrónicos al informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="e2eb5-120">Electronic receipts are attached to the expense report.</span></span>

4. <span data-ttu-id="e2eb5-121">El aprobador aprueba el informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="e2eb5-121">The approver approves the expense report.</span></span>
5. <span data-ttu-id="e2eb5-122">El informe de gastos se asigna a un coordinador de proveedores para que proceda a su registro.</span><span class="sxs-lookup"><span data-stu-id="e2eb5-122">The expense report is assigned to the Accounts payable coordinator for posting.</span></span>
6. <span data-ttu-id="e2eb5-123">Deberá realizar uno de los siguientes pasos, en función de si el registro automático está configurado:</span><span class="sxs-lookup"><span data-stu-id="e2eb5-123">One of the following steps occurs, depending on whether automatic posting is configured:</span></span>

    - <span data-ttu-id="e2eb5-124">Si se configura el registro automático, el informe de gastos se procesa para el pago y el estado del informe de gastos se actualiza.</span><span class="sxs-lookup"><span data-stu-id="e2eb5-124">If automatic posting is configured, the expense report is processed for payment, and the status of the expense report is updated.</span></span>
    - <span data-ttu-id="e2eb5-125">Si el registro automático no se configura, el coordinador de proveedores comprueba que se han enviado todos los recibos originales, y que los recibos corresponden a los gastos incluidos en el informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="e2eb5-125">If automatic posting isn't configured, the Accounts payable coordinator verifies that all original receipts have been submitted, and that the receipts are aligned with the expenses on the expense report.</span></span> <span data-ttu-id="e2eb5-126">Todos los códigos de impuestos especificados en el informe de gastos también se deben comprobar como correctos.</span><span class="sxs-lookup"><span data-stu-id="e2eb5-126">All tax codes that are entered on the expense report must also be verified as correct.</span></span>

<span data-ttu-id="e2eb5-127">Una vez comprobados estos requisitos, se registra el informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="e2eb5-127">After these requirements are verified, the expense report is posted.</span></span>

<span data-ttu-id="e2eb5-128">Después de que se registre el informe de gastos, se autoriza el pago para el informe de gastos y se reembolsa al empleado.</span><span class="sxs-lookup"><span data-stu-id="e2eb5-128">After the expense report is posted, payment is authorized for the expense report, and the employee is reimbursed.</span></span>

