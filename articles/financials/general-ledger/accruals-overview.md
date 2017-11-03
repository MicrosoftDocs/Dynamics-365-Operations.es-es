---
title: "Visión general de Acumulaciones"
description: "Este artículo describe acumulaciones y proporciona información acerca de cómo configurarlas y crear transacciones."
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerAccuralTable
audience: Application User
ms.reviewer: robinr
ms.search.scope: Core, Operations
ms.custom: 14131
ms.assetid: 0489b59a-37a7-4a78-87bf-4b597e9efad9
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 00ecc493e6dcf59ab61e7082297c95516a248b58
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="accruals-overview"></a><span data-ttu-id="0c410-103">Visión general de Acumulaciones</span><span class="sxs-lookup"><span data-stu-id="0c410-103">Accruals overview</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="0c410-104">Este artículo describe acumulaciones y proporciona información acerca de cómo configurarlas y crear transacciones.</span><span class="sxs-lookup"><span data-stu-id="0c410-104">This article describes accruals, and provides information about how to set them up and create transactions.</span></span>

<span data-ttu-id="0c410-105">Las acumulaciones se usan en la contabilidad por devengo para realizar un seguimiento de los ingresos que se reconoce en el período en que se ha obtenido, no cuando se recibe el pago, y para realizar un seguimiento de los gastos (costes) que se reconocen cuando se producen, no cuando se realiza el pago.</span><span class="sxs-lookup"><span data-stu-id="0c410-105">Accruals are used in accrual accounting to track revenue that is recognized in the period that it's earned in, not when payment is received, and to track expenses (costs) that are recognized when they occur, not when payment is made.</span></span>

## <a name="accrual-schemes"></a><span data-ttu-id="0c410-106">Esquemas de acumulación</span><span class="sxs-lookup"><span data-stu-id="0c410-106">Accrual schemes</span></span>
<span data-ttu-id="0c410-107">Los esquemas de acumulación se usan para configurar los costes y los ingresos diferidos, y el mismo esquema de acumulación se puede usar tanto para los ingresos como para los costes.</span><span class="sxs-lookup"><span data-stu-id="0c410-107">Accrual schemes are used to set up the deferred revenue and costs, and the same accrual scheme can be used for both revenue and costs.</span></span> <span data-ttu-id="0c410-108">Las acumulaciones contables redistribuyen los costes o los ingresos de una línea de diario para que se reconozcan en los períodos adecuados</span><span class="sxs-lookup"><span data-stu-id="0c410-108">Ledger accruals redistribute the costs or revenue of a journal line so that the costs and revenues are recognized in the appropriate periods.</span></span> <span data-ttu-id="0c410-109">En la página **Esquema de acumulación**, especifique las cuentas de crédito y débito que se usarán cuando se aplique el esquema de acumulación.</span><span class="sxs-lookup"><span data-stu-id="0c410-109">On the **Accrual scheme** page, you specify the debit and the credit accounts that will be used when the accrual scheme is applied.</span></span>

-   <span data-ttu-id="0c410-110">**Débito**: la cuenta principal que defina reemplazará la cuenta principal de débito en la línea del asiento de diario.</span><span class="sxs-lookup"><span data-stu-id="0c410-110">**Debit** – The main account that you define will replace the debit main account on the journal voucher line.</span></span> <span data-ttu-id="0c410-111">Esta cuenta también se usará para la inversión del aplazamiento, en función de las transacciones de acumulaciones contables.</span><span class="sxs-lookup"><span data-stu-id="0c410-111">This account will also be used for the reversal of the deferral, based on the ledger accrual transactions.</span></span>
-   <span data-ttu-id="0c410-112">**Crédito**: la cuenta principal que defina reemplazará la cuenta principal de crédito en la línea del asiento de diario.</span><span class="sxs-lookup"><span data-stu-id="0c410-112">**Credit** – the main account that you define will replace the credit main account on the journal voucher line.</span></span> <span data-ttu-id="0c410-113">Esta cuenta también se usará para la inversión del aplazamiento, en función de las transacciones de acumulaciones contables.</span><span class="sxs-lookup"><span data-stu-id="0c410-113">This account will also be used for the reversal of the deferral, based on the ledger accrual transactions.</span></span>

<span data-ttu-id="0c410-114">Tras determinar qué cuentas se usarán, puede especificar cómo se crea el número de asiento al crearse las transacciones de acumulación.</span><span class="sxs-lookup"><span data-stu-id="0c410-114">After you determine which accounts to use, you can specify how the voucher number is created when accrual transactions are created.</span></span> <span data-ttu-id="0c410-115">También puede especificar la frecuencia con la que se producen las transacciones, el número de veces en que se crean las transacciones y cuándo se registran las transacciones.</span><span class="sxs-lookup"><span data-stu-id="0c410-115">You can also specify how often the transactions occur, the number of times that the transactions are created, and when the transactions are posted.</span></span> <span data-ttu-id="0c410-116">Tras la creación del esquema de acumulación, puede usarlo en algunos diarios a través de la función Acumulaciones contables.</span><span class="sxs-lookup"><span data-stu-id="0c410-116">After the accrual scheme has been created, you can use it in some of the journals by using the Ledger accruals function.</span></span>

## <a name="ledger-accruals"></a><span data-ttu-id="0c410-117">Acumulaciones contables</span><span class="sxs-lookup"><span data-stu-id="0c410-117">Ledger accruals</span></span>
<span data-ttu-id="0c410-118">Cuando especifique un diario, puede hacer clic en **Acumulaciones contables** en el menú **Funciones**.</span><span class="sxs-lookup"><span data-stu-id="0c410-118">When you enter a journal, you can click **Ledger accruals** on the **Functions** menu.</span></span> <span data-ttu-id="0c410-119">A continuación, al seleccionar el esquema de acumulación, verá el importe base del diario que se distribuirá por el período, según se determine por el esquema de acumulación.</span><span class="sxs-lookup"><span data-stu-id="0c410-119">Then, when you select the accrual scheme, you will see the base amount from the journal that will be spread over the period, as determined by the accrual scheme.</span></span> <span data-ttu-id="0c410-120">Por ejemplo, si paga el seguro de un empleado para todo el año en enero, y el importe es 12 000, debe reconocer dicho gasto cada mes.</span><span class="sxs-lookup"><span data-stu-id="0c410-120">For example, if you pay an employee's insurance for the whole year in January, and the amount is 12,000, you must recognize that expense each month.</span></span> <span data-ttu-id="0c410-121">Puede seleccionar la fecha inicial.</span><span class="sxs-lookup"><span data-stu-id="0c410-121">You can select the start date.</span></span> <span data-ttu-id="0c410-122">También puede especificar si el importe que se acumula se basa en la cuenta o en la cuenta de contrapartida.</span><span class="sxs-lookup"><span data-stu-id="0c410-122">You can also specify whether the amount that is accrued is based on the account or the offset account.</span></span> <span data-ttu-id="0c410-123">Después de crear sus selecciones, haga clic en **Transacciones** para ver todas las transacciones que se han creado en función del esquema de acumulación.</span><span class="sxs-lookup"><span data-stu-id="0c410-123">After you make your selections, click **Transactions** to view all the transactions that have been created based on the accrual scheme.</span></span> <span data-ttu-id="0c410-124">Por ejemplo, si distribuye el importe de 12 000 en gastos de seguros durante el año, verá 1000 para cada mes.</span><span class="sxs-lookup"><span data-stu-id="0c410-124">For example, if you spread the 12,000 in insurance expenses over the year, you will see 1,000 for each month.</span></span> <span data-ttu-id="0c410-125">Tras registrar el diario, podrá ver las transacciones con la página de consulta **Transacciones de asiento**.</span><span class="sxs-lookup"><span data-stu-id="0c410-125">After you post the journal, you can view the transactions by using the **Voucher transactions** inquiry page.</span></span> <span data-ttu-id="0c410-126">Si no se puede aplicar un esquema de acumulación (por ejemplo, cuando está implicada una factura de pedido de ventas o factura de pedido de compra), puede abonar el importe pagado por adelantado y adeudar el importe de gasto.</span><span class="sxs-lookup"><span data-stu-id="0c410-126">If an accrual scheme can't be applied (for example, when a sales order invoice or purchase order invoice is involved), you can credit the prepaid amount and debit the expense amount.</span></span> <span data-ttu-id="0c410-127">A continuación, puede seleccionar **Compensación** al aplicar el esquema de acumulación.</span><span class="sxs-lookup"><span data-stu-id="0c410-127">You can then select **Offset** when you apply the accrual scheme.</span></span>


<span data-ttu-id="0c410-128">Para obtener más información, consulte [Crear esquemas de acumulación](tasks/create-accrual-schemes.md) y [Crear transacciones de acumulaciones del libro mayor](tasks/create-ledger-accrual-transactions.md).</span><span class="sxs-lookup"><span data-stu-id="0c410-128">For more information, see [Create accrual schemes](tasks/create-accrual-schemes.md) and [Create ledger accrual transactions](tasks/create-ledger-accrual-transactions.md).</span></span>

