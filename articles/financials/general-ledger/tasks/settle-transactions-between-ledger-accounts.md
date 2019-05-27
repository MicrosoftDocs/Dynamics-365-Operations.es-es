---
title: Liquidar transacciones entre las cuentas contables
description: Este procedimiento muestra cómo liquidar transacciones entre cuentas contables y cancelar una liquidación de contabilidad.
author: aprilolson
manager: AnnBe
ms.date: 10/03/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransSettlement, LedgerTrialBalanceListPage, LedgerTrialBalanceListPageBalanceParms, LedgerTransAccount, LedgerTransSettled
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4aff64fa1c017f295752e913de7fb320f0662ef8
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1568129"
---
# <a name="settle-transactions-between-ledger-accounts"></a><span data-ttu-id="25f51-103">Liquidar transacciones entre las cuentas contables</span><span class="sxs-lookup"><span data-stu-id="25f51-103">Settle transactions between ledger accounts</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="25f51-104">Este procedimiento muestra cómo liquidar transacciones entre cuentas contables y cancelar una liquidación de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="25f51-104">This procedure shows how to settle transactions between ledger accounts and cancel a ledger settlement.</span></span> <span data-ttu-id="25f51-105">Este procedimiento usa la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="25f51-105">This procedure uses the USMF demo data company.</span></span>


## <a name="settle-transaction-between-ledger-accounts"></a><span data-ttu-id="25f51-106">Liquidar transacción entre las cuentas contables</span><span class="sxs-lookup"><span data-stu-id="25f51-106">Settle transaction between ledger accounts</span></span>
1. <span data-ttu-id="25f51-107">Vaya a Contabilidad general > Tareas periódicas > Liquidaciones de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="25f51-107">Go to General ledger > Periodic tasks > Ledger settlements.</span></span>
2. <span data-ttu-id="25f51-108">En la lista, encuentre la transacción que desee liquidar.</span><span class="sxs-lookup"><span data-stu-id="25f51-108">In the list, find the transaction that you want to settle.</span></span>
   > [!NOTE]
   > <span data-ttu-id="25f51-109">El importe del saldo debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="25f51-109">The amount balance must be zero.</span></span>  
3. <span data-ttu-id="25f51-110">Haga clic en Incluir.</span><span class="sxs-lookup"><span data-stu-id="25f51-110">Click Include.</span></span>
4. <span data-ttu-id="25f51-111">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="25f51-111">Click Accept.</span></span>

## <a name="cancel-a-ledger-settlement"></a><span data-ttu-id="25f51-112">Cancelar una liquidación de contabilidad</span><span class="sxs-lookup"><span data-stu-id="25f51-112">Cancel a ledger settlement</span></span>

1. <span data-ttu-id="25f51-113">Vaya a Contabilidad general > Consultas e informes > Saldo de comprobación.</span><span class="sxs-lookup"><span data-stu-id="25f51-113">Go to General ledger > Inquiries and reports > Trial balance.</span></span>
2. <span data-ttu-id="25f51-114">Haga clic en Parámetros para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="25f51-114">Click Parameters to open the drop dialog.</span></span>
3. <span data-ttu-id="25f51-115">Haga clic en Actualizar.</span><span class="sxs-lookup"><span data-stu-id="25f51-115">Click Update.</span></span>
4. <span data-ttu-id="25f51-116">En la lista, encuentre la cuenta que tiene la transacción liquidada.</span><span class="sxs-lookup"><span data-stu-id="25f51-116">In the list, find the account that has the settled transaction.</span></span>
5. <span data-ttu-id="25f51-117">Haga clic en Todas las transacciones.</span><span class="sxs-lookup"><span data-stu-id="25f51-117">Click All transactions.</span></span>
6. <span data-ttu-id="25f51-118">Use un filtro para buscar fácilmente la transacción en la lista.</span><span class="sxs-lookup"><span data-stu-id="25f51-118">Use a filter to easily find the transaction in the list.</span></span>
7. <span data-ttu-id="25f51-119">Haga clic en Liquidaciones contables.</span><span class="sxs-lookup"><span data-stu-id="25f51-119">Click Ledger settlements.</span></span>
8. <span data-ttu-id="25f51-120">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="25f51-120">In the list, mark the selected row.</span></span>

