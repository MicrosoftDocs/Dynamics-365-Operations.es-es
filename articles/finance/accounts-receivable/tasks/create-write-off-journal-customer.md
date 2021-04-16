---
title: Crear una cancelación de un diario para un cliente
description: Esta guía de tarea le mostrará cómo configurar los parámetros para las cancelaciones y después cancelar transacciones desde la página Cobros, la página Facturas de cliente abiertas y la página Cliente.
author: ShivamPandey-msft
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters, CustPosting, DefaultDashboard, CustCollectionsPoolsListPage, CustWriteOff, LedgerJournalTable, LedgerJournalTransDaily, CustCollections, CustOpenInvoicesListPage, CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 857d3a224f35c4eeedbf4913aea14011091d5466
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823128"
---
# <a name="create-a-write-off-journal-for-a-customer"></a><span data-ttu-id="086c0-103">Crear una cancelación de un diario para un cliente</span><span class="sxs-lookup"><span data-stu-id="086c0-103">Create a write-off journal for a customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="086c0-104">Esta guía de tarea le mostrará cómo configurar los parámetros para las cancelaciones y después cancelar transacciones desde la página Cobros, la página Facturas de cliente abiertas y la página Cliente.</span><span class="sxs-lookup"><span data-stu-id="086c0-104">This task guide will show you how to set up the parameters for write-offs and then write off transactions from the Collections page, the Open customer invoices page, and the Customer page.</span></span> <span data-ttu-id="086c0-105">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="086c0-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-the-write-off-parameters"></a><span data-ttu-id="086c0-106">Configuración de parámetros de cancelación</span><span class="sxs-lookup"><span data-stu-id="086c0-106">Set up the write off parameters</span></span>
1. <span data-ttu-id="086c0-107">Vaya al **Panel de exploración > Módulos > Crédito y cobros > Configuración > Parámetros de clientes**.</span><span class="sxs-lookup"><span data-stu-id="086c0-107">Go to **Navigation pane > Modules > Credit and collections > Setup > Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="086c0-108">Haga clic en la ficha **Cobros**.</span><span class="sxs-lookup"><span data-stu-id="086c0-108">Click the **Collections** tab.</span></span>
3. <span data-ttu-id="086c0-109">Expanda o contraiga la sección **Cancelación**.</span><span class="sxs-lookup"><span data-stu-id="086c0-109">Expand or collapse the **Write-off** section.</span></span>
    - <span data-ttu-id="086c0-110">El **Diario de cancelaciones** es el diario general que guardará las transacciones de cancelación que cree.</span><span class="sxs-lookup"><span data-stu-id="086c0-110">The **Write-off journal** is the general journal that will hold the write-off transactions that you create.</span></span>  
    - <span data-ttu-id="086c0-111">Puede vincular un código de motivo a cada cancelación.</span><span class="sxs-lookup"><span data-stu-id="086c0-111">You can attach a reason code to every write-off.</span></span> <span data-ttu-id="086c0-112">Puede sobrescribir este valor predeterminado al realizar la cancelación.</span><span class="sxs-lookup"><span data-stu-id="086c0-112">You can override this default at the time of the write-off.</span></span>  
    - <span data-ttu-id="086c0-113">Establezca **Impuestos independientes** en Sí si desea separar los impuestos de la transacción original en la cancelación.</span><span class="sxs-lookup"><span data-stu-id="086c0-113">Set the **Separate sales tax** to Yes if you want to separate the sales tax from the original transaction in the write-off.</span></span>  
4. <span data-ttu-id="086c0-114">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="086c0-114">Close the page.</span></span>
5. <span data-ttu-id="086c0-115">Vaya a **Crédito y cobros > Configuración > Perfiles de contabilización del cliente.**</span><span class="sxs-lookup"><span data-stu-id="086c0-115">Go to **Credit and collections > Setup > Customer posting profiles**.</span></span> <span data-ttu-id="086c0-116">La cuenta de cancelación se usará como cuenta de gastos o ajuste de reserva en el diario general.</span><span class="sxs-lookup"><span data-stu-id="086c0-116">The write-off account will be used as the expense account or reserve adjustment in the general journal.</span></span>
6. <span data-ttu-id="086c0-117">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="086c0-117">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a><span data-ttu-id="086c0-118">Cancelación del saldo de un cliente desde la página de saldos vencidos</span><span class="sxs-lookup"><span data-stu-id="086c0-118">Write off a customer balance from the aged balances page</span></span>
1. <span data-ttu-id="086c0-119">Vaya a **Crédito y cobros > Cobros > Saldos vencidos**.</span><span class="sxs-lookup"><span data-stu-id="086c0-119">Go to **Credit and collections > Collections > Aged balances**.</span></span>
2. <span data-ttu-id="086c0-120">Marque la fila del cliente que desee cancelar.</span><span class="sxs-lookup"><span data-stu-id="086c0-120">Mark the row for the customer that you want to write off.</span></span> <span data-ttu-id="086c0-121">Por ejemplo, marque la línea con Birch Company.</span><span class="sxs-lookup"><span data-stu-id="086c0-121">For example, mark the line with Birch Company on it.</span></span>
3. <span data-ttu-id="086c0-122">En el **panel de acciones**, haga clic en **Cobrar**.</span><span class="sxs-lookup"><span data-stu-id="086c0-122">On the **Action Pane**, click **Collect**.</span></span>
4. <span data-ttu-id="086c0-123">Haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="086c0-123">Click **Write off**.</span></span>
5. <span data-ttu-id="086c0-124">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="086c0-124">Click **OK**.</span></span>
6. <span data-ttu-id="086c0-125">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="086c0-125">Close the page.</span></span>
7. <span data-ttu-id="086c0-126">Vaya a **Panel de exploración > Módulos > Contabilidad general > Entradas del diario > Diarios generales**.</span><span class="sxs-lookup"><span data-stu-id="086c0-126">Go to **Navigation pane > Modules > General ledger > Journal entries > General journals**.</span></span>
8. <span data-ttu-id="086c0-127">Seleccione el número de lote del diario que contiene la cancelación.</span><span class="sxs-lookup"><span data-stu-id="086c0-127">Select the journal batch number for the journal that contains your write-off.</span></span> <span data-ttu-id="086c0-128">Se crea una línea para revertir el saldo del cliente.</span><span class="sxs-lookup"><span data-stu-id="086c0-128">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="086c0-129">Se crean una o más líneas para registrar la cancelación en la cuenta de cancelación.</span><span class="sxs-lookup"><span data-stu-id="086c0-129">One or more lines are created to post the write-off to the write-off account.</span></span>  
9. <span data-ttu-id="086c0-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="086c0-130">Close the page.</span></span>
10. <span data-ttu-id="086c0-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="086c0-131">Close the page.</span></span>

## <a name="write-off-transactions-from-the-collections-form"></a><span data-ttu-id="086c0-132">Cancele transacciones desde el formulario de cobros.</span><span class="sxs-lookup"><span data-stu-id="086c0-132">Write off transactions from the collections form.</span></span>
1. <span data-ttu-id="086c0-133">Vaya a **Crédito y cobros > Cobros > Saldos vencidos**.</span><span class="sxs-lookup"><span data-stu-id="086c0-133">Go to **Credit and collections > Collections > Aged balances**.</span></span>
2. <span data-ttu-id="086c0-134">Seleccione el nombre del cliente con las transacciones que desee cancelar.</span><span class="sxs-lookup"><span data-stu-id="086c0-134">Select the name of the customer that has the transactions that you want to write off.</span></span> <span data-ttu-id="086c0-135">Por ejemplo, seleccione Cave Wholesales (US-004).</span><span class="sxs-lookup"><span data-stu-id="086c0-135">For example, select Cave Wholesales (US-004).</span></span>
3. <span data-ttu-id="086c0-136">Marque la fila de la primera transacción.</span><span class="sxs-lookup"><span data-stu-id="086c0-136">Mark the row for the first transaction.</span></span>
4. <span data-ttu-id="086c0-137">Marque la fila de la segunda transacción.</span><span class="sxs-lookup"><span data-stu-id="086c0-137">Mark the row for the second transaction.</span></span>
5. <span data-ttu-id="086c0-138">Haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="086c0-138">Click **Write off**.</span></span>
6. <span data-ttu-id="086c0-139">En el campo **Comentario de motivo**, escriba "Deudas incorrectas".</span><span class="sxs-lookup"><span data-stu-id="086c0-139">In the **Reason comment** field, type 'Bad debts'.</span></span>
7. <span data-ttu-id="086c0-140">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="086c0-140">Click **OK**.</span></span>
8. <span data-ttu-id="086c0-141">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="086c0-141">Close the page.</span></span>
9. <span data-ttu-id="086c0-142">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="086c0-142">Close the page.</span></span>
10. <span data-ttu-id="086c0-143">Vaya a **Contabilidad general > Movimientos de diario > Diarios generales**.</span><span class="sxs-lookup"><span data-stu-id="086c0-143">Go to **General ledger > Journal entries > General journals**.</span></span>
11. <span data-ttu-id="086c0-144">Seleccione el número de lote del diario que contiene la cancelación.</span><span class="sxs-lookup"><span data-stu-id="086c0-144">Select the journal batch number for the journal that contains your write-off.</span></span> <span data-ttu-id="086c0-145">Se crea una línea para revertir el saldo del cliente.</span><span class="sxs-lookup"><span data-stu-id="086c0-145">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="086c0-146">Se crean una o más líneas para registrar la cancelación en la cuenta de cancelación.</span><span class="sxs-lookup"><span data-stu-id="086c0-146">One or more lines are created to post the write-off to the write-off account.</span></span>  
12. <span data-ttu-id="086c0-147">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="086c0-147">Close the page.</span></span>
13. <span data-ttu-id="086c0-148">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="086c0-148">Close the page.</span></span>

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a><span data-ttu-id="086c0-149">Cancelación de una factura desde la página Abrir facturas de cliente</span><span class="sxs-lookup"><span data-stu-id="086c0-149">Write off an invoice from the Open customers invoices page</span></span>
1. <span data-ttu-id="086c0-150">Vaya a **Panel de exploración >Módulos > Clientes > Facturas > Facturas de clientes abiertas**.</span><span class="sxs-lookup"><span data-stu-id="086c0-150">Go to **Navigation pane > Modules > Accounts receivable > Invoices > Open customer invoices**.</span></span>
2. <span data-ttu-id="086c0-151">Marque la línea de una factura.</span><span class="sxs-lookup"><span data-stu-id="086c0-151">Mark the line for an invoice.</span></span> <span data-ttu-id="086c0-152">Por ejemplo, marque la línea para CIV-000667.</span><span class="sxs-lookup"><span data-stu-id="086c0-152">For example, mark the line for CIV-000667.</span></span>
3. <span data-ttu-id="086c0-153">En el **panel de acciones**, haga clic en **Factura**.</span><span class="sxs-lookup"><span data-stu-id="086c0-153">On the **Action Pane**, click **Invoice**.</span></span>
4. <span data-ttu-id="086c0-154">Haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="086c0-154">Click **Write off**.</span></span>
5. <span data-ttu-id="086c0-155">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="086c0-155">Click **OK**.</span></span>
6. <span data-ttu-id="086c0-156">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="086c0-156">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-customer-page"></a><span data-ttu-id="086c0-157">Cancelación del saldo de un cliente desde la página del cliente</span><span class="sxs-lookup"><span data-stu-id="086c0-157">Write off a customer balance from the customer page</span></span>
1. <span data-ttu-id="086c0-158">Vaya a **Clientes > Clientes > Todos los clientes**.</span><span class="sxs-lookup"><span data-stu-id="086c0-158">Go to **Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="086c0-159">Seleccionar una cuenta de cliente.</span><span class="sxs-lookup"><span data-stu-id="086c0-159">Select a customer account.</span></span> <span data-ttu-id="086c0-160">Por ejemplo, seleccione US-001 (Contoso Retail San Diego).</span><span class="sxs-lookup"><span data-stu-id="086c0-160">For example, select US-001 (Contoso Retail San Diego).</span></span>
3. <span data-ttu-id="086c0-161">En el **panel de acciones**, haga clic en **Cobrar**.</span><span class="sxs-lookup"><span data-stu-id="086c0-161">On the **Action Pane**, click **Collect**.</span></span>
4. <span data-ttu-id="086c0-162">Haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="086c0-162">Click **Write off**.</span></span>
5. <span data-ttu-id="086c0-163">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="086c0-163">Click **OK**.</span></span>
6. <span data-ttu-id="086c0-164">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="086c0-164">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]