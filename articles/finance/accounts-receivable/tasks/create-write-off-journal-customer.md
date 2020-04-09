---
title: Crear una cancelación de un diario para un cliente
description: Esta guía de tarea le mostrará cómo configurar los parámetros para las cancelaciones y después cancelar transacciones desde la página Cobros, la página Facturas de cliente abiertas y la página Cliente.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustParameters, CustPosting, DefaultDashboard, CustCollectionsPoolsListPage, CustWriteOff, LedgerJournalTable, LedgerJournalTransDaily, CustCollections, CustOpenInvoicesListPage, CustTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dd97f91f1ba53b56150b556fffdfed10a0c8911a
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140246"
---
# <a name="create-a-write-off-journal-for-a-customer"></a><span data-ttu-id="b148c-103">Crear una cancelación de un diario para un cliente</span><span class="sxs-lookup"><span data-stu-id="b148c-103">Create a write-off journal for a customer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="b148c-104">Esta guía de tarea le mostrará cómo configurar los parámetros para las cancelaciones y después cancelar transacciones desde la página Cobros, la página Facturas de cliente abiertas y la página Cliente.</span><span class="sxs-lookup"><span data-stu-id="b148c-104">This task guide will show you how to set up the parameters for write-offs and then write off transactions from the Collections page, the Open customer invoices page, and the Customer page.</span></span> <span data-ttu-id="b148c-105">Esta tarea usa la empresa de demostración USMF.</span><span class="sxs-lookup"><span data-stu-id="b148c-105">This task uses the USMF demo company.</span></span>


## <a name="set-up-the-write-off-parameters"></a><span data-ttu-id="b148c-106">Configuración de parámetros de cancelación</span><span class="sxs-lookup"><span data-stu-id="b148c-106">Set up the write off parameters</span></span>
1. <span data-ttu-id="b148c-107">Vaya al **Panel de exploración > Módulos > Crédito y cobros > Configuración > Parámetros de clientes**.</span><span class="sxs-lookup"><span data-stu-id="b148c-107">Go to **Navigation pane > Modules > Credit and collections > Setup > Accounts receivable parameters**.</span></span>
2. <span data-ttu-id="b148c-108">Haga clic en la ficha **Cobros**.</span><span class="sxs-lookup"><span data-stu-id="b148c-108">Click the **Collections** tab.</span></span>
3. <span data-ttu-id="b148c-109">Expanda o contraiga la sección **Cancelación**.</span><span class="sxs-lookup"><span data-stu-id="b148c-109">Expand or collapse the **Write-off** section.</span></span>
    - <span data-ttu-id="b148c-110">El **Diario de cancelaciones** es el diario general que guardará las transacciones de cancelación que cree.</span><span class="sxs-lookup"><span data-stu-id="b148c-110">The **Write-off journal** is the general journal that will hold the write-off transactions that you create.</span></span>  
    - <span data-ttu-id="b148c-111">Puede vincular un código de motivo a cada cancelación.</span><span class="sxs-lookup"><span data-stu-id="b148c-111">You can attach a reason code to every write-off.</span></span> <span data-ttu-id="b148c-112">Puede sobrescribir este valor predeterminado al realizar la cancelación.</span><span class="sxs-lookup"><span data-stu-id="b148c-112">You can override this default at the time of the write-off.</span></span>  
    - <span data-ttu-id="b148c-113">Establezca **Impuestos independientes** en Sí si desea separar los impuestos de la transacción original en la cancelación.</span><span class="sxs-lookup"><span data-stu-id="b148c-113">Set the **Separate sales tax** to Yes if you want to separate the sales tax from the original transaction in the write-off.</span></span>  
4. <span data-ttu-id="b148c-114">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b148c-114">Close the page.</span></span>
5. <span data-ttu-id="b148c-115">Vaya a **Crédito y cobros > Configuración > Perfiles de contabilización del cliente.**</span><span class="sxs-lookup"><span data-stu-id="b148c-115">Go to **Credit and collections > Setup > Customer posting profiles**.</span></span> <span data-ttu-id="b148c-116">La cuenta de cancelación se usará como cuenta de gastos o ajuste de reserva en el diario general.</span><span class="sxs-lookup"><span data-stu-id="b148c-116">The write-off account will be used as the expense account or reserve adjustment in the general journal.</span></span>
6. <span data-ttu-id="b148c-117">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b148c-117">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a><span data-ttu-id="b148c-118">Cancelación del saldo de un cliente desde la página de saldos vencidos</span><span class="sxs-lookup"><span data-stu-id="b148c-118">Write off a customer balance from the aged balances page</span></span>
1. <span data-ttu-id="b148c-119">Vaya a **Crédito y cobros > Cobros > Saldos vencidos**.</span><span class="sxs-lookup"><span data-stu-id="b148c-119">Go to **Credit and collections > Collections > Aged balances**.</span></span>
2. <span data-ttu-id="b148c-120">Marque la fila del cliente que desee cancelar.</span><span class="sxs-lookup"><span data-stu-id="b148c-120">Mark the row for the customer that you want to write off.</span></span> <span data-ttu-id="b148c-121">Por ejemplo, marque la línea con Birch Company.</span><span class="sxs-lookup"><span data-stu-id="b148c-121">For example, mark the line with Birch Company on it.</span></span>
3. <span data-ttu-id="b148c-122">En el **panel de acciones**, haga clic en **Cobrar**.</span><span class="sxs-lookup"><span data-stu-id="b148c-122">On the **Action Pane**, click **Collect**.</span></span>
4. <span data-ttu-id="b148c-123">Haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="b148c-123">Click **Write off**.</span></span>
5. <span data-ttu-id="b148c-124">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b148c-124">Click **OK**.</span></span>
6. <span data-ttu-id="b148c-125">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b148c-125">Close the page.</span></span>
7. <span data-ttu-id="b148c-126">Vaya a **Panel de exploración > Módulos > Contabilidad general > Entradas del diario > Diarios generales**.</span><span class="sxs-lookup"><span data-stu-id="b148c-126">Go to **Navigation pane > Modules > General ledger > Journal entries > General journals**.</span></span>
8. <span data-ttu-id="b148c-127">Seleccione el número de lote del diario que contiene la cancelación.</span><span class="sxs-lookup"><span data-stu-id="b148c-127">Select the journal batch number for the journal that contains your write-off.</span></span> <span data-ttu-id="b148c-128">Se crea una línea para revertir el saldo del cliente.</span><span class="sxs-lookup"><span data-stu-id="b148c-128">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="b148c-129">Se crean una o más líneas para registrar la cancelación en la cuenta de cancelación.</span><span class="sxs-lookup"><span data-stu-id="b148c-129">One or more lines are created to post the write-off to the write-off account.</span></span>  
9. <span data-ttu-id="b148c-130">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b148c-130">Close the page.</span></span>
10. <span data-ttu-id="b148c-131">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b148c-131">Close the page.</span></span>

## <a name="write-off-transactions-from-the-collections-form"></a><span data-ttu-id="b148c-132">Cancele transacciones desde el formulario de cobros.</span><span class="sxs-lookup"><span data-stu-id="b148c-132">Write off transactions from the collections form.</span></span>
1. <span data-ttu-id="b148c-133">Vaya a **Crédito y cobros > Cobros > Saldos vencidos**.</span><span class="sxs-lookup"><span data-stu-id="b148c-133">Go to **Credit and collections > Collections > Aged balances**.</span></span>
2. <span data-ttu-id="b148c-134">Seleccione el nombre del cliente con las transacciones que desee cancelar.</span><span class="sxs-lookup"><span data-stu-id="b148c-134">Select the name of the customer that has the transactions that you want to write off.</span></span> <span data-ttu-id="b148c-135">Por ejemplo, seleccione Cave Wholesales (US-004).</span><span class="sxs-lookup"><span data-stu-id="b148c-135">For example, select Cave Wholesales (US-004).</span></span>
3. <span data-ttu-id="b148c-136">Marque la fila de la primera transacción.</span><span class="sxs-lookup"><span data-stu-id="b148c-136">Mark the row for the first transaction.</span></span>
4. <span data-ttu-id="b148c-137">Marque la fila de la segunda transacción.</span><span class="sxs-lookup"><span data-stu-id="b148c-137">Mark the row for the second transaction.</span></span>
5. <span data-ttu-id="b148c-138">Haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="b148c-138">Click **Write off**.</span></span>
6. <span data-ttu-id="b148c-139">En el campo **Comentario de motivo**, escriba "Deudas incorrectas".</span><span class="sxs-lookup"><span data-stu-id="b148c-139">In the **Reason comment** field, type 'Bad debts'.</span></span>
7. <span data-ttu-id="b148c-140">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b148c-140">Click **OK**.</span></span>
8. <span data-ttu-id="b148c-141">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b148c-141">Close the page.</span></span>
9. <span data-ttu-id="b148c-142">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b148c-142">Close the page.</span></span>
10. <span data-ttu-id="b148c-143">Vaya a **Contabilidad general > Movimientos de diario > Diarios generales**.</span><span class="sxs-lookup"><span data-stu-id="b148c-143">Go to **General ledger > Journal entries > General journals**.</span></span>
11. <span data-ttu-id="b148c-144">Seleccione el número de lote del diario que contiene la cancelación.</span><span class="sxs-lookup"><span data-stu-id="b148c-144">Select the journal batch number for the journal that contains your write-off.</span></span> <span data-ttu-id="b148c-145">Se crea una línea para revertir el saldo del cliente.</span><span class="sxs-lookup"><span data-stu-id="b148c-145">One line is created to reverse the customer balance.</span></span> <span data-ttu-id="b148c-146">Se crean una o más líneas para registrar la cancelación en la cuenta de cancelación.</span><span class="sxs-lookup"><span data-stu-id="b148c-146">One or more lines are created to post the write-off to the write-off account.</span></span>  
12. <span data-ttu-id="b148c-147">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b148c-147">Close the page.</span></span>
13. <span data-ttu-id="b148c-148">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b148c-148">Close the page.</span></span>

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a><span data-ttu-id="b148c-149">Cancelación de una factura desde la página Abrir facturas de cliente</span><span class="sxs-lookup"><span data-stu-id="b148c-149">Write off an invoice from the Open customers invoices page</span></span>
1. <span data-ttu-id="b148c-150">Vaya a **Panel de exploración >Módulos > Clientes > Facturas > Facturas de clientes abiertas**.</span><span class="sxs-lookup"><span data-stu-id="b148c-150">Go to **Navigation pane > Modules > Accounts receivable > Invoices > Open customer invoices**.</span></span>
2. <span data-ttu-id="b148c-151">Marque la línea de una factura.</span><span class="sxs-lookup"><span data-stu-id="b148c-151">Mark the line for an invoice.</span></span> <span data-ttu-id="b148c-152">Por ejemplo, marque la línea para CIV-000667.</span><span class="sxs-lookup"><span data-stu-id="b148c-152">For example, mark the line for CIV-000667.</span></span>
3. <span data-ttu-id="b148c-153">En el **panel de acciones**, haga clic en **Factura**.</span><span class="sxs-lookup"><span data-stu-id="b148c-153">On the **Action Pane**, click **Invoice**.</span></span>
4. <span data-ttu-id="b148c-154">Haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="b148c-154">Click **Write off**.</span></span>
5. <span data-ttu-id="b148c-155">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b148c-155">Click **OK**.</span></span>
6. <span data-ttu-id="b148c-156">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b148c-156">Close the page.</span></span>

## <a name="write-off-a-customer-balance-from-the-customer-page"></a><span data-ttu-id="b148c-157">Cancelación del saldo de un cliente desde la página del cliente</span><span class="sxs-lookup"><span data-stu-id="b148c-157">Write off a customer balance from the customer page</span></span>
1. <span data-ttu-id="b148c-158">Vaya a **Clientes > Clientes > Todos los clientes**.</span><span class="sxs-lookup"><span data-stu-id="b148c-158">Go to **Accounts receivable > Customers > All customers**.</span></span>
2. <span data-ttu-id="b148c-159">Seleccionar una cuenta de cliente.</span><span class="sxs-lookup"><span data-stu-id="b148c-159">Select a customer account.</span></span> <span data-ttu-id="b148c-160">Por ejemplo, seleccione US-001 (Contoso Retail San Diego).</span><span class="sxs-lookup"><span data-stu-id="b148c-160">For example, select US-001 (Contoso Retail San Diego).</span></span>
3. <span data-ttu-id="b148c-161">En el **panel de acciones**, haga clic en **Cobrar**.</span><span class="sxs-lookup"><span data-stu-id="b148c-161">On the **Action Pane**, click **Collect**.</span></span>
4. <span data-ttu-id="b148c-162">Haga clic en **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="b148c-162">Click **Write off**.</span></span>
5. <span data-ttu-id="b148c-163">Haga clic en **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="b148c-163">Click **OK**.</span></span>
6. <span data-ttu-id="b148c-164">Cierre la página.</span><span class="sxs-lookup"><span data-stu-id="b148c-164">Close the page.</span></span>

