--- 
title: Liquidar un cheque con pago diferido para un proveedor
description: "Liquide un cheque con pago diferido emitido a un proveedor cuando el banco haya compensado la transacción del cheque después de que el cheque haya vencido y lo haya compensado el banco."
author: kweekley
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: c2facae3de31b0a9a1d426b49c9ea5778adca8e6
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="settle-a-postdated-check-for-a-vendor"></a><span data-ttu-id="07848-103">Liquidar un cheque con pago diferido para un proveedor</span><span class="sxs-lookup"><span data-stu-id="07848-103">Settle a postdated check for a vendor</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="07848-104">Liquide un cheque con pago diferido emitido a un proveedor cuando el banco haya compensado la transacción del cheque después de que el cheque haya vencido y lo haya compensado el banco.</span><span class="sxs-lookup"><span data-stu-id="07848-104">Settle a postdated check issued to a vendor when the bank has cleared the check transaction after the check has been overdue and cleared by the bank.</span></span> 

<span data-ttu-id="07848-105">Complete los siguientes procedimientos antes de empezar este.</span><span class="sxs-lookup"><span data-stu-id="07848-105">Complete the following procedures before you start this one.</span></span>

1) <span data-ttu-id="07848-106">Configuración de cheques con pago diferido</span><span class="sxs-lookup"><span data-stu-id="07848-106">Set up postdated checks</span></span>

2) <span data-ttu-id="07848-107">Registrar un cheque con pago diferido para un proveedor</span><span class="sxs-lookup"><span data-stu-id="07848-107">Register and post a postdated check for a vendor</span></span>



<span data-ttu-id="07848-108">El rol de este procedimiento es Tesorero.</span><span class="sxs-lookup"><span data-stu-id="07848-108">The role of this procedure is Treasurer.</span></span> <span data-ttu-id="07848-109">Este procedimiento usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="07848-109">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="07848-110">Vaya a Proveedores > Pagos > Cheques con fecha futura de proveedor.</span><span class="sxs-lookup"><span data-stu-id="07848-110">Go to Accounts payable > Payments > Vendor postdated checks.</span></span>
2. <span data-ttu-id="07848-111">Haga clic en Liquidar.</span><span class="sxs-lookup"><span data-stu-id="07848-111">Click Settle.</span></span>
3. <span data-ttu-id="07848-112">Haga clic en Liquidar entidades de compensación.</span><span class="sxs-lookup"><span data-stu-id="07848-112">Click Settle clearing entries.</span></span>
    * <span data-ttu-id="07848-113">Liquide la cuenta de proveedor para la transacción de cheque.</span><span class="sxs-lookup"><span data-stu-id="07848-113">Settle the vendor account for the check transaction.</span></span>  
4. <span data-ttu-id="07848-114">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="07848-114">Close the page.</span></span>
5. <span data-ttu-id="07848-115">Vaya a Contabilidad general > Movimientos de diario > Diarios generales.</span><span class="sxs-lookup"><span data-stu-id="07848-115">Go to General ledger > Journal entries > General journals.</span></span>
6. <span data-ttu-id="07848-116">En el campo Mostrar, seleccione "Todos".</span><span class="sxs-lookup"><span data-stu-id="07848-116">In the Show field, select 'All'.</span></span>
7. <span data-ttu-id="07848-117">Active o desactive la casilla Mostrar sólo creados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="07848-117">Select or clear the Show user-created only check box.</span></span>
8. <span data-ttu-id="07848-118">En la lista, marque la fila seleccionada.</span><span class="sxs-lookup"><span data-stu-id="07848-118">In the list, mark the selected row.</span></span>
9. <span data-ttu-id="07848-119">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="07848-119">Click Lines.</span></span>
10. <span data-ttu-id="07848-120">Haga clic en Asiento.</span><span class="sxs-lookup"><span data-stu-id="07848-120">Click Voucher.</span></span>
11. <span data-ttu-id="07848-121">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="07848-121">Close the page.</span></span>


