--- 
title: Liquidar un cheque con pago diferido de un cliente
description: "Puede liquidar un cheque posfechado después de que el banco lo haya desactivado."
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
ms.openlocfilehash: 95651e602bd4f576a7fcf96379f61252cdf392f6
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---
# <a name="settle-a-postdated-check-from-a-customer"></a><span data-ttu-id="d3654-103">Liquidar un cheque con pago diferido de un cliente</span><span class="sxs-lookup"><span data-stu-id="d3654-103">Settle a postdated check from a customer</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="d3654-104">Puede liquidar un cheque posfechado después de que el banco lo haya desactivado.</span><span class="sxs-lookup"><span data-stu-id="d3654-104">You can settle a postdated check after the check has been cleared by the bank.</span></span> <span data-ttu-id="d3654-105">Esta transacción financiera también se eliminará la transacción de cuenta puente para el cheque posfechado.</span><span class="sxs-lookup"><span data-stu-id="d3654-105">This financial transaction also clears the bridge account transaction for the postdated check.</span></span> 

<span data-ttu-id="d3654-106">Las siguientes tareas se deben realizar antes de comenzar esta.</span><span class="sxs-lookup"><span data-stu-id="d3654-106">The following tasks must be complete before you start this one.</span></span>

1) <span data-ttu-id="d3654-107">Configuración de cheques con pago diferido</span><span class="sxs-lookup"><span data-stu-id="d3654-107">Set up postdated checks</span></span>

2) <span data-ttu-id="d3654-108">Registrar un cheque con pago diferido para un cliente</span><span class="sxs-lookup"><span data-stu-id="d3654-108">Register and post a postdated check for a customer</span></span> 



<span data-ttu-id="d3654-109">El rol de esta guía de tareas es Tesorero.</span><span class="sxs-lookup"><span data-stu-id="d3654-109">The role of this task guides is Treasurer.</span></span>



<span data-ttu-id="d3654-110">Este procedimiento usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="d3654-110">This procedure uses the USMF demo company.</span></span>

1. <span data-ttu-id="d3654-111">Vaya a Crédito y cobros > Consultas e informes > Pagos > Cheques con fecha futura de cliente.</span><span class="sxs-lookup"><span data-stu-id="d3654-111">Go to Credit and collections > Inquiries and reports > Payments > Customer postdated checks.</span></span>
2. <span data-ttu-id="d3654-112">Haga clic en Liquidar.</span><span class="sxs-lookup"><span data-stu-id="d3654-112">Click Settle.</span></span>
3. <span data-ttu-id="d3654-113">Haga clic en Liquidar entidades de compensación.</span><span class="sxs-lookup"><span data-stu-id="d3654-113">Click Settle clearing entries.</span></span>
    * <span data-ttu-id="d3654-114">Liquide la cuenta del cliente para la transacción de cheque.</span><span class="sxs-lookup"><span data-stu-id="d3654-114">Settle the customer account for the check transaction.</span></span>  
4. <span data-ttu-id="d3654-115">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d3654-115">Close the page.</span></span>
5. <span data-ttu-id="d3654-116">Vaya a Contabilidad general > Movimientos de diario > Diarios generales.</span><span class="sxs-lookup"><span data-stu-id="d3654-116">Go to General ledger > Journal entries > General journals.</span></span>
6. <span data-ttu-id="d3654-117">En el campo Mostrar, seleccione una opción.</span><span class="sxs-lookup"><span data-stu-id="d3654-117">In the Show field, select an option.</span></span>
7. <span data-ttu-id="d3654-118">Active o desactive la casilla Mostrar sólo creados por el usuario.</span><span class="sxs-lookup"><span data-stu-id="d3654-118">Select or clear the Show user-created only check box.</span></span>
8. <span data-ttu-id="d3654-119">En la lista, busque y seleccione el registro deseado.</span><span class="sxs-lookup"><span data-stu-id="d3654-119">In the list, find and select the desired record.</span></span>
9. <span data-ttu-id="d3654-120">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="d3654-120">Click Lines.</span></span>
10. <span data-ttu-id="d3654-121">Haga clic en Asiento.</span><span class="sxs-lookup"><span data-stu-id="d3654-121">Click Voucher.</span></span>
11. <span data-ttu-id="d3654-122">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="d3654-122">Close the page.</span></span>


