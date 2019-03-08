---
title: Informes de gastos y varios aprobadores
description: En este tema se proporciona información sobre los informes de gastos que requieren la aprobación de más de una persona.
author: saraschi2
manager: AnnBe
ms.date: 02/23/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TrvExpensesReportList
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1483de5405895d60f0cb302ab622758b2b05d2ca
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "362427"
---
# <a name="expense-reports-and-multiple-approvers"></a><span data-ttu-id="0eb48-103">Informes de gastos y varios aprobadores</span><span class="sxs-lookup"><span data-stu-id="0eb48-103">Expense reports and multiple approvers</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0eb48-104">En función de las directivas de aprobación de gastos de su organización, puede que más de una persona tenga que aprobar un informe de gastos que haya enviado un empleado.</span><span class="sxs-lookup"><span data-stu-id="0eb48-104">Depending on your organization's expense approval policies, more than one person might have to approve an expense report that is submitted by an employee.</span></span> <span data-ttu-id="0eb48-105">Cuando configura el proceso de flujo de trabajo para la aprobación del informe de gastos, puede agregar elementos de flujo de trabajo que incluyan las tareas o los pasos para uno o varios aprobadores del informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="0eb48-105">When you set up the workflow process for expense report approval, you can add workflow elements that include tasks or steps for one or more expense report approvers.</span></span> <span data-ttu-id="0eb48-106">Por ejemplo, puede solicitar que todos los informes de gastos los apruebe en primer lugar el director del empleado que envió el informe y, a continuación, el coordinador de proveedores.</span><span class="sxs-lookup"><span data-stu-id="0eb48-106">For example, you might require that all expense reports be approved first by the manager of the employee who submitted the report and then by the Accounts payable coordinator.</span></span>

<span data-ttu-id="0eb48-107">Si decide solicitar varios aprobadores del informe de gastos, puede agregar elementos de flujo de trabajo de una de las siguientes formas:</span><span class="sxs-lookup"><span data-stu-id="0eb48-107">If you decide to require multiple expense report approvers, you can add the workflow elements in any of the following ways:</span></span>

- <span data-ttu-id="0eb48-108">Agregue un elemento de aprobación que tenga un paso.</span><span class="sxs-lookup"><span data-stu-id="0eb48-108">Add one approval element that has one step.</span></span> <span data-ttu-id="0eb48-109">Por ejemplo, el paso puede requerir que un informe de gastos se asigne a un grupo de usuarios y que lo apruebe el 50 por ciento de los miembros del grupo de usuarios.</span><span class="sxs-lookup"><span data-stu-id="0eb48-109">For example, the step might require that an expense report be assigned to a user group, and that it be approved by 50 percent of the user group's members.</span></span>
- <span data-ttu-id="0eb48-110">Agregue un elemento de aprobación que tenga varios pasos.</span><span class="sxs-lookup"><span data-stu-id="0eb48-110">Add one approval element that has multiple steps.</span></span> <span data-ttu-id="0eb48-111">Por ejemplo, el elemento de aprobación puede tener los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="0eb48-111">For example, the approval element might have the following steps:</span></span>

    1. <span data-ttu-id="0eb48-112">El director del empleado que envió el informe de gastos lo aprueba.</span><span class="sxs-lookup"><span data-stu-id="0eb48-112">The manager of the employee who submitted the expense report approves it.</span></span>
    2. <span data-ttu-id="0eb48-113">El funcionario de proveedores comprueba las recepciones y los artículos del informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="0eb48-113">The Accounts payable clerk verifies the receipts and the expense report items.</span></span>
    3. <span data-ttu-id="0eb48-114">El propietario de presupuesto aprueba el informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="0eb48-114">The budget owner approves the expense report.</span></span>

- <span data-ttu-id="0eb48-115">Agregue varios elementos de aprobación, cada uno que tenga un paso.</span><span class="sxs-lookup"><span data-stu-id="0eb48-115">Add multiple approval elements, each of which has one step.</span></span> <span data-ttu-id="0eb48-116">Por ejemplo, puede agregar un elemento de aprobación individual para cada uno de los siguientes pasos:</span><span class="sxs-lookup"><span data-stu-id="0eb48-116">For example, you might add a separate approval element for each of the following steps:</span></span>

    1. <span data-ttu-id="0eb48-117">El director del empleado aprueba el informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="0eb48-117">The employee's manager approves the expense report.</span></span>
    2. <span data-ttu-id="0eb48-118">El propietario de presupuesto aprueba el informe de gastos.</span><span class="sxs-lookup"><span data-stu-id="0eb48-118">The budget owner approves the expense report.</span></span>
