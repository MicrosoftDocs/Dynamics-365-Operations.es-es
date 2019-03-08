---
title: Depositar pagos de cliente
description: Pagos de cliente en depósito.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f58cebce20e8516dc918e0bad1e020ffd7f791ee
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "313391"
---
# <a name="deposit-customer-payments"></a><span data-ttu-id="9c9aa-103">Depositar pagos de cliente</span><span class="sxs-lookup"><span data-stu-id="9c9aa-103">Deposit customer payments</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="9c9aa-104">Pagos de cliente en depósito.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-104">Deposit customer payments.</span></span> <span data-ttu-id="9c9aa-105">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-105">This task uses the USMF demo company.</span></span>

1. <span data-ttu-id="9c9aa-106">Vaya a Clientes > Pagos > Diario de pagos.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-106">Go to Accounts receivable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="9c9aa-107">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-107">Click New.</span></span>
3. <span data-ttu-id="9c9aa-108">En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-108">In the Name field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="9c9aa-109">Seleccione el diario de pago.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-109">Select the payment journal.</span></span> 
5. <span data-ttu-id="9c9aa-110">Haga clic en Líneas.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-110">Click Lines.</span></span>
6. <span data-ttu-id="9c9aa-111">En el campo Cuenta, seleccione el cliente para el que esté registrando el pago.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-111">In the Account field, select the Customer for whom you are recording the payment.</span></span>
7. <span data-ttu-id="9c9aa-112">En el campo Crédito, especifique el importe del pago.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-112">In the Credit field, enter the amount of the payment.</span></span>
    * <span data-ttu-id="9c9aa-113">Puede elegir dejar el importe en blanco y hacer que el sistema lo calcule seleccionando las facturas pagadas.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-113">You can choose to leave the amount blank, and have the system calculate it by selecting the invoices which were paid.</span></span>  
8. <span data-ttu-id="9c9aa-114">En el campo Referencia del pago, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-114">In the Payment reference field, type a value.</span></span>
    * <span data-ttu-id="9c9aa-115">La referencia de pago podría ser el número de cheque para el pago que se está introduciendo.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-115">The payment reference could be the check number for the payment you are entering.</span></span> <span data-ttu-id="9c9aa-116">La referencia de pago es obligatoria para incluir el pago en un resguardo de depósito.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-116">The payment reference is required in order to include the payment on a deposit slip.</span></span>  
9. <span data-ttu-id="9c9aa-117">Marque el cuadro Utilizar un resguardo del depósito.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-117">Mark the box Use a deposit slip.</span></span>
    * <span data-ttu-id="9c9aa-118">Si el pago debe incluirse en el depósito, cambie este ajuste a Sí.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-118">If the payment should be included in the deposit, change this setting to Yes.</span></span>  
10. <span data-ttu-id="9c9aa-119">Haga clic en Nuevo.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-119">Click New.</span></span>
11. <span data-ttu-id="9c9aa-120">En el campo Cuenta, seleccione el cliente para el siguiente pago.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-120">In the Account field, select the Customer for the next payment.</span></span>
12. <span data-ttu-id="9c9aa-121">En el campo Crédito, especifique el importe del pago.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-121">In the Credit field, enter the payment amount.</span></span>
13. <span data-ttu-id="9c9aa-122">En el campo Referencia del pago, escriba un valor.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-122">In the Payment reference field, type a value.</span></span>
14. <span data-ttu-id="9c9aa-123">Marque el cuadro Utilizar un resguardo del depósito.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-123">Mark the box Use a deposit slip.</span></span>
15. <span data-ttu-id="9c9aa-124">Haga clic en Registrar.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-124">Click Post.</span></span>
    * <span data-ttu-id="9c9aa-125">Los pagos deben registrarse para poder generar el resguardo de depósito.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-125">Payments must be posted before the deposit slip can be generated.</span></span> <span data-ttu-id="9c9aa-126">Esto es así para garantizar que los pagos no cambian después de generarse el resguardo de depósito.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-126">This is to ensure that the payments don't change after the deposit slip is generated.</span></span>  
16. <span data-ttu-id="9c9aa-127">Haga clic en Funciones.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-127">Click Functions.</span></span>
17. <span data-ttu-id="9c9aa-128">Haga clic en Resguardo de depósito.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-128">Click Deposit slip.</span></span>
18. <span data-ttu-id="9c9aa-129">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="9c9aa-129">Click OK.</span></span>
    * <span data-ttu-id="9c9aa-130">La primera página que se usa para crear el resguardo de depósito.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-130">The first page is used to create the deposit slip.</span></span>  
19. <span data-ttu-id="9c9aa-131">Haga clic en Aceptar</span><span class="sxs-lookup"><span data-stu-id="9c9aa-131">Click OK.</span></span>
    * <span data-ttu-id="9c9aa-132">El segundo paso es imprimir el resguardo de depósito, si bien este paso no es obligatorio.</span><span class="sxs-lookup"><span data-stu-id="9c9aa-132">The second step is to print the deposit slip, but this step is not required.</span></span>  

