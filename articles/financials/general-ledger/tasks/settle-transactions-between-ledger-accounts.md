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
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6ed76f82532d43a3c05b60b12176fe851e327956
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846232"
---
# <a name="settle-transactions-between-ledger-accounts"></a><span data-ttu-id="49aec-103">Liquidar transacciones entre las cuentas contables</span><span class="sxs-lookup"><span data-stu-id="49aec-103">Settle transactions between ledger accounts</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="49aec-104">Este procedimiento muestra cómo liquidar transacciones entre cuentas contables y cancelar una liquidación de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="49aec-104">This procedure shows how to settle transactions between ledger accounts and cancel a ledger settlement.</span></span> <span data-ttu-id="49aec-105">Este procedimiento usa la empresa de datos de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="49aec-105">This procedure uses the USMF demo data company.</span></span>


## <a name="settle-transaction-between-ledger-accounts"></a><span data-ttu-id="49aec-106">Liquidar transacción entre las cuentas contables</span><span class="sxs-lookup"><span data-stu-id="49aec-106">Settle transaction between ledger accounts</span></span>
1. <span data-ttu-id="49aec-107">Vaya a Contabilidad general > Tareas periódicas > Liquidaciones de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="49aec-107">Go to General ledger > Periodic tasks > Ledger settlements.</span></span>
2. <span data-ttu-id="49aec-108">En la lista, encuentre la transacción que desee liquidar.</span><span class="sxs-lookup"><span data-stu-id="49aec-108">In the list, find the transaction that you want to settle.</span></span>
   > [!NOTE]
   > <span data-ttu-id="49aec-109">El importe del saldo debe ser cero.</span><span class="sxs-lookup"><span data-stu-id="49aec-109">The amount balance must be zero.</span></span>  
3. <span data-ttu-id="49aec-110">Haga clic en Incluir.</span><span class="sxs-lookup"><span data-stu-id="49aec-110">Click Include.</span></span>
4. <span data-ttu-id="49aec-111">Haga clic en Aceptar.</span><span class="sxs-lookup"><span data-stu-id="49aec-111">Click Accept.</span></span>

## <a name="cancel-a-ledger-settlement"></a><span data-ttu-id="49aec-112">Cancelar una liquidación de contabilidad</span><span class="sxs-lookup"><span data-stu-id="49aec-112">Cancel a ledger settlement</span></span>

1. <span data-ttu-id="49aec-113">Vaya a Contabilidad general > Consultas e informes > Saldo de comprobación.</span><span class="sxs-lookup"><span data-stu-id="49aec-113">Go to General ledger > Inquiries and reports > Trial balance.</span></span>
2. <span data-ttu-id="49aec-114">Haga clic en Parámetros para abrir el cuadro de diálogo desplegable.</span><span class="sxs-lookup"><span data-stu-id="49aec-114">Click Parameters to open the drop dialog.</span></span>
3. <span data-ttu-id="49aec-115">Haga clic en Actualizar.</span><span class="sxs-lookup"><span data-stu-id="49aec-115">Click Update.</span></span>
4. <span data-ttu-id="49aec-116">En la lista, encuentre la cuenta que tiene la transacción liquidada.</span><span class="sxs-lookup"><span data-stu-id="49aec-116">In the list, find the account that has the settled transaction.</span></span>
5. <span data-ttu-id="49aec-117">Haga clic en Todas las transacciones.</span><span class="sxs-lookup"><span data-stu-id="49aec-117">Click All transactions.</span></span>
6. <span data-ttu-id="49aec-118">Use un filtro para buscar fácilmente la transacción en la lista.</span><span class="sxs-lookup"><span data-stu-id="49aec-118">Use a filter to easily find the transaction in the list.</span></span>
7. <span data-ttu-id="49aec-119">Haga clic en Liquidaciones contables.</span><span class="sxs-lookup"><span data-stu-id="49aec-119">Click Ledger settlements.</span></span>
8. <span data-ttu-id="49aec-120">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="49aec-120">In the list, mark the selected row.</span></span>

