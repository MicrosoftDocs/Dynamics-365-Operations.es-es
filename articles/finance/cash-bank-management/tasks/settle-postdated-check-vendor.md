---
title: Liquidar un cheque con pago diferido para un proveedor
description: Liquide un cheque con pago diferido emitido a un proveedor cuando el banco haya compensado la transacción del cheque después de que el cheque haya vencido y lo haya compensado el banco.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 89acad0c9421960ff4d07ed8eec798b9068424d5
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834581"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a><span data-ttu-id="67a83-103">Liquidar un cheque con pago diferido para un proveedor</span><span class="sxs-lookup"><span data-stu-id="67a83-103">Settle a postdated check for a vendor</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="67a83-104">Liquide un cheque con pago diferido emitido a un proveedor cuando el banco haya compensado la transacción del cheque después de que el cheque haya vencido y lo haya compensado el banco.</span><span class="sxs-lookup"><span data-stu-id="67a83-104">Settle a postdated check issued to a vendor when the bank has cleared the check transaction after the check has been overdue and cleared by the bank.</span></span> 

<span data-ttu-id="67a83-105">Complete los siguientes procedimientos antes de empezar este.</span><span class="sxs-lookup"><span data-stu-id="67a83-105">Complete the following procedures before you start this one.</span></span>

1) <span data-ttu-id="67a83-106">Configuración de cheques con pago diferido</span><span class="sxs-lookup"><span data-stu-id="67a83-106">Set up postdated checks</span></span>

2) <span data-ttu-id="67a83-107">Registrar un cheque con pago diferido para un proveedor</span><span class="sxs-lookup"><span data-stu-id="67a83-107">Register and post a postdated check for a vendor</span></span>



<span data-ttu-id="67a83-108">El rol de este procedimiento es Tesorero.</span><span class="sxs-lookup"><span data-stu-id="67a83-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="67a83-109">Este procedimiento usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="67a83-109">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="67a83-110">Vaya a Proveedores > Pagos > Cheques con fecha futura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="67a83-110">Go to Accounts payable > Payments > Vendor postdated checks.</span></span>
2. <span data-ttu-id="67a83-111">Haga clic en Liquidar.</span><span class="sxs-lookup"><span data-stu-id="67a83-111">Click Settle.</span></span>
3. <span data-ttu-id="67a83-112">Haga clic en Liquidar entidades de compensación.</span><span class="sxs-lookup"><span data-stu-id="67a83-112">Click Settle clearing entries.</span></span>
    * <span data-ttu-id="67a83-113">Liquide la cuenta de proveedor para la transacción de cheque.</span><span class="sxs-lookup"><span data-stu-id="67a83-113">Settle the vendor account for the check transaction.</span></span>  
4. <span data-ttu-id="67a83-114">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="67a83-114">Close the page.</span></span>
5. <span data-ttu-id="67a83-115">Vaya a Contabilidad general > Movimientos de diario > Diarios generales.</span><span class="sxs-lookup"><span data-stu-id="67a83-115">Go to General ledger > Journal entries > General journals.</span></span>
6. <span data-ttu-id="67a83-116">En el campo Mostrar, seleccione "Todos".</span><span class="sxs-lookup"><span data-stu-id="67a83-116">In the Show field, select 'All'.</span></span>
7. <span data-ttu-id="67a83-117">Active o desactive la casilla Mostrar sólo creados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="67a83-117">Select or clear the Show user-created only check box.</span></span>
8. <span data-ttu-id="67a83-118">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="67a83-118">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="67a83-119">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="67a83-119">Click Lines.</span></span>
10. <span data-ttu-id="67a83-120">Haga clic en Asiento.</span><span class="sxs-lookup"><span data-stu-id="67a83-120">Click Voucher.</span></span>
11. <span data-ttu-id="67a83-121">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="67a83-121">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]