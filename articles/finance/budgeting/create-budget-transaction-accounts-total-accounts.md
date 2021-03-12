---
title: Creación de un presupuesto desde cuentas de transacción y cuentas totales
description: Este artículo proporciona una visión general del proceso para crear presupuestos basados en cuentas totales. También explica cómo activar el control presupuestario para las cuentas totales, si se requiere control presupuestario.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BudgetControlConfiguration, BudgetPlanGenerate
audience: Application User
ms.reviewer: roschlom
ms.custom: 13051
ms.assetid: fb1bb2d3-445c-402f-a9a3-aa6503eed78e
ms.search.region: Global
ms.author: sigitac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2c2298a774e35bc92fafb8bc24871b288fb198d7
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003090"
---
# <a name="create-a-budget-from-transaction-accounts-and-total-accounts"></a><span data-ttu-id="de4b0-104">Creación de un presupuesto desde cuentas de transacción y cuentas totales</span><span class="sxs-lookup"><span data-stu-id="de4b0-104">Create a budget from transaction accounts and total accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="de4b0-105">Este artículo proporciona una visión general del proceso para crear presupuestos basados en cuentas totales.</span><span class="sxs-lookup"><span data-stu-id="de4b0-105">This article provides an overview of the process for creating budgets based on total accounts.</span></span> <span data-ttu-id="de4b0-106">También explica cómo activar el control presupuestario para las cuentas totales, si se requiere control presupuestario.</span><span class="sxs-lookup"><span data-stu-id="de4b0-106">It also explains how to turn on budget control for total accounts, if budget control is required.</span></span>

<span data-ttu-id="de4b0-107">Los documentos de asiento de plan y registro presupuestario permiten presupuestar en las cuentas principales que tienen un tipo de cuenta principal **Total**.</span><span class="sxs-lookup"><span data-stu-id="de4b0-107">Both budget plan and budget register entry documents allow for budgeting on main accounts that have a main account type of **Total**.</span></span> <span data-ttu-id="de4b0-108">Los datos reales solo se pueden registrar en cuentas de transacciones principales.</span><span class="sxs-lookup"><span data-stu-id="de4b0-108">Actuals can be posted only to transactional main accounts.</span></span> 

<span data-ttu-id="de4b0-109">Para el proceso periódico **Generar plan presupuestario a partir de contabilidad general**, en la ficha **Origen** puede especificar el tipo de cuenta principal **Total** como criterio.</span><span class="sxs-lookup"><span data-stu-id="de4b0-109">For the **Generate budget plan from General ledger** periodic process, on the **Source** tab, you can specify the **Total** main account type as a criterion.</span></span> <span data-ttu-id="de4b0-110">En este caso, cada cuenta principal total se incluirá en el plan presupuestario de destino, y el importe será el importe total del intervalo de cuentas principales seleccionadas.</span><span class="sxs-lookup"><span data-stu-id="de4b0-110">In this case, each total main account will be included in the target budget plan, and the amount will equal the total amount of the range of selected main accounts.</span></span> 

<span data-ttu-id="de4b0-111">Puede activar el control presupuestario para las cuentas principales del tipo **Total**.</span><span class="sxs-lookup"><span data-stu-id="de4b0-111">You can activate budget control for main accounts of the **Total** type.</span></span> <span data-ttu-id="de4b0-112">Esta función se puede usar con grupos presupuestarios.</span><span class="sxs-lookup"><span data-stu-id="de4b0-112">This functionality is supported through the use of budget groups.</span></span> <span data-ttu-id="de4b0-113">Para cada cuenta principal total, el presupuesto que se debe controlar para un grupo presupuestario debe crearse en la página **Configuración de control presupuestario**.</span><span class="sxs-lookup"><span data-stu-id="de4b0-113">For each total main account, the budget that should be controlled for a budget group must be created on the \*\*Budget control configuration \*\*page.</span></span> <span data-ttu-id="de4b0-114">Los criterios especificados deben incluir la cuenta principal total y el intervalo de cuentas.</span><span class="sxs-lookup"><span data-stu-id="de4b0-114">The criteria that you specify must include the total main account and the range of accounts.</span></span> <span data-ttu-id="de4b0-115">Para acelerar el proceso de creación de grupos presupuestarios, puede aprovecharse la entidad de datos de los grupos de control presupuestario.</span><span class="sxs-lookup"><span data-stu-id="de4b0-115">To speed up the process of creating budget groups, you can take advantage of the Budget control groups data entity.</span></span> 

<span data-ttu-id="de4b0-116">Cuando se utiliza un presupuesto en los informes, como por ejemplo en un informe financiero, el importe presupuestario de la cuenta total consta de los siguientes importes:</span><span class="sxs-lookup"><span data-stu-id="de4b0-116">When a budget is used in reporting, such as on a financial statement, the budget sum for the total account consists of the following amounts:</span></span>

-   <span data-ttu-id="de4b0-117">Los presupuestos creados a partir de cada cuenta contable de transacción en el intervalo de la cuenta total.</span><span class="sxs-lookup"><span data-stu-id="de4b0-117">The budgets that are created from each transaction ledger account in the interval of the total account.</span></span>
-   <span data-ttu-id="de4b0-118">El importe presupuestario especificado directamente en la cuenta total.</span><span class="sxs-lookup"><span data-stu-id="de4b0-118">The budget amount that is entered directly on the total account.</span></span>

<span data-ttu-id="de4b0-119">Así pues, puede crear presupuestos independientes para las cuentas de transacción más significativas en el intervalo de la cuenta total y agregar el importe presupuestario disponible a la cuenta total.</span><span class="sxs-lookup"><span data-stu-id="de4b0-119">Therefore, you can create separate budgets for the most significant transaction accounts in the interval of the total account, and then add the available budget amount to the total account.</span></span>



