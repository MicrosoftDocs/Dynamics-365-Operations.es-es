---
title: Invertir diario de registro
description: Este tema describe capacidades que le permiten invertir los asientos de la transacción de asiento o lista de los diarios financieros.
author: MikeFalkner
manager: AnnBe
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: e3244d857a9135249130672501f8b766ff9a0680
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3980947"
---
# <a name="reverse-journal-posting"></a><span data-ttu-id="4b041-103">Invertir diario de registro</span><span class="sxs-lookup"><span data-stu-id="4b041-103">Reverse journal posting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4b041-104">Este tema describe las capacidades de Microsoft Dynamics 365 Finance que permiten que invierta el diario entero o que invierta uno o varios asientos de la transacción de asiento enumerada independientemente de su origen.</span><span class="sxs-lookup"><span data-stu-id="4b041-104">This topic describes capabilities Microsoft Dynamics 365 Finance that allows you to reverse an entire journal, or reverse one or more vouchers from the voucher transaction list, regardless of their origin.</span></span> 

## <a name="reversing-journals"></a><span data-ttu-id="4b041-105">Invertir los diarios</span><span class="sxs-lookup"><span data-stu-id="4b041-105">Reversing journals</span></span>

<span data-ttu-id="4b041-106">Puede invertir las líneas de diario de forma individual.</span><span class="sxs-lookup"><span data-stu-id="4b041-106">You can reverse journal lines individually.</span></span> <span data-ttu-id="4b041-107">Con el registro de invertir diario, también puede invertir un diario financiero completo.</span><span class="sxs-lookup"><span data-stu-id="4b041-107">With reverse journal posting, you can also reverse an entire financial journal.</span></span> <span data-ttu-id="4b041-108">Para invertir un diario:</span><span class="sxs-lookup"><span data-stu-id="4b041-108">To reverse a journal:</span></span> 

- <span data-ttu-id="4b041-109">Abra el diario y filtre según los diarios registrados.</span><span class="sxs-lookup"><span data-stu-id="4b041-109">Open the financial journal and filter on posted journals.</span></span>
- <span data-ttu-id="4b041-110">Haga clic en el menú **Invertir** en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="4b041-110">Select the **Reverse** menu at the top of the page.</span></span>
- <span data-ttu-id="4b041-111">Verá el número total de asientos y las líneas de asiento junto con el importe total de las líneas que son invertidas</span><span class="sxs-lookup"><span data-stu-id="4b041-111">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="4b041-112">Seleccione **Sí** para usar las fechas de transacción actuales o **No** para introducir una nueva.</span><span class="sxs-lookup"><span data-stu-id="4b041-112">Select **Yes** to use the existing transaction dates or **No** to enter a new one.</span></span> <span data-ttu-id="4b041-113">En algunos casos, el período de la transacción original puede estar cerrado y usted tiene que especificar una nueva fecha de transacción para la inversión.</span><span class="sxs-lookup"><span data-stu-id="4b041-113">In some cases, the period of the original transaction may be closed and you must enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="4b041-114">Si selecciona **No**, especifique una fecha de transacción para la inversión.</span><span class="sxs-lookup"><span data-stu-id="4b041-114">If you select **No**, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="4b041-115">Escriba un comentario que desee agregar a la transacción de inversión.</span><span class="sxs-lookup"><span data-stu-id="4b041-115">Enter a comment that you want added to the reversal transaction.</span></span>
- <span data-ttu-id="4b041-116">Seleccione el botón **Invertir**.</span><span class="sxs-lookup"><span data-stu-id="4b041-116">Select the **Reverse** button.</span></span>

<span data-ttu-id="4b041-117">Las transacciones se invertirán.</span><span class="sxs-lookup"><span data-stu-id="4b041-117">The transactions will be reversed.</span></span> 

<span data-ttu-id="4b041-118">Si el asiento supera las 100 líneas, el proceso de inversión se ejecuta mediante el proceso por lotes.</span><span class="sxs-lookup"><span data-stu-id="4b041-118">If the voucher contains more than 100 lines, the reversal process will run using the batch process.</span></span> <span data-ttu-id="4b041-119">Puede revisar los resultados viendo los comentarios en el trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="4b041-119">You can review the results by viewing the comments in the batch job.</span></span> <span data-ttu-id="4b041-120">Las transacciones que no se hayan podido invertir serán enumeradas en el historial de trabajos por lotes.</span><span class="sxs-lookup"><span data-stu-id="4b041-120">Any transactions that couldn't be reversed will be listed in the batch job history.</span></span>

<span data-ttu-id="4b041-121">Si el asiento es de 100 o menos líneas, el proceso de inversión se ejecutará inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="4b041-121">If the voucher contains 100 lines or fewer, the reversal process will run immediately.</span></span> <span data-ttu-id="4b041-122">Los resultados se mostrarán en un cuadro diálogo que muestra cualquier asiento que no se ha podido invertir y la razón por la que no ha podido invertirse.</span><span class="sxs-lookup"><span data-stu-id="4b041-122">The results will be presented in a dialog box that shows any voucher that could not be reversed, along with the reason why it could not be reversed.</span></span> <span data-ttu-id="4b041-123">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4b041-123">Select **OK** to close the dialog box.</span></span>

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a><span data-ttu-id="4b041-124">Invertir los asientos de la lista de la transacción de asiento.</span><span class="sxs-lookup"><span data-stu-id="4b041-124">Reversing vouchers from the voucher transaction list.</span></span> 

<span data-ttu-id="4b041-125">También puede invertir los asientos de la **Lista de la transacción de asiento** a través de todos los sublibros de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="4b041-125">You can also reverse vouchers from the **Voucher transaction list** across all subledgers.</span></span> <span data-ttu-id="4b041-126">Además, puede invertir más de un asiento al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="4b041-126">In addition, you can reverse more than one voucher at a time.</span></span> 

<span data-ttu-id="4b041-127">Para invertir uno o varios asientos:</span><span class="sxs-lookup"><span data-stu-id="4b041-127">To reverse one or more vouchers:</span></span> 

- <span data-ttu-id="4b041-128">Haga clic en el menú **Invertir** en la parte superior de la página.</span><span class="sxs-lookup"><span data-stu-id="4b041-128">Select the **Reverse** menu at the top of the page</span></span>
- <span data-ttu-id="4b041-129">Verá el número total de asientos y las líneas de asiento junto con el importe total de las líneas que son invertidas.</span><span class="sxs-lookup"><span data-stu-id="4b041-129">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed.</span></span>
- <span data-ttu-id="4b041-130">Seleccione **Sí** para usar las fechas de transacción actuales o **No** para introducir una nueva.</span><span class="sxs-lookup"><span data-stu-id="4b041-130">Select **Yes** to use the existing transaction dates or **No** to enter a new one.</span></span> <span data-ttu-id="4b041-131">En algunos casos, el período de la transacción original puede estar cerrado y usted tiene que especificar una nueva fecha de transacción para la inversión.</span><span class="sxs-lookup"><span data-stu-id="4b041-131">In some cases, the period of the original transaction may be closed and you must enter a new transaction date to reverse it.</span></span>
- <span data-ttu-id="4b041-132">Si selecciona **No**, especifique una fecha de transacción para la inversión.</span><span class="sxs-lookup"><span data-stu-id="4b041-132">If you select **No**, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="4b041-133">Escriba un comentario para describir la transacción de inversión.</span><span class="sxs-lookup"><span data-stu-id="4b041-133">Enter a comment to describe the reversal transaction.</span></span>
- <span data-ttu-id="4b041-134">Seleccione el botón **Invertir**.</span><span class="sxs-lookup"><span data-stu-id="4b041-134">Select the **Reverse** button.</span></span>

<span data-ttu-id="4b041-135">Las transacciones se invertirán.</span><span class="sxs-lookup"><span data-stu-id="4b041-135">The transactions will be reversed.</span></span> 

<span data-ttu-id="4b041-136">Si el asiento supera las 100 líneas, el proceso de inversión se ejecuta mediante el proceso por lotes.</span><span class="sxs-lookup"><span data-stu-id="4b041-136">If there are more than 100 voucher lines, the reversal process will run using the batch process.</span></span> <span data-ttu-id="4b041-137">Puede revisar los resultados viendo los comentarios en el trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="4b041-137">You can review the results by viewing the comments in the batch job.</span></span> <span data-ttu-id="4b041-138">Las transacciones que no se hayan podido invertir serán comentadas en el historial de trabajos por lotes.</span><span class="sxs-lookup"><span data-stu-id="4b041-138">Any transactions that couldn't be reversed will be noted in the batch job history.</span></span>

<span data-ttu-id="4b041-139">Si el número de líneas de asiento es 100 o menos, el proceso de inversión se ejecutará inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="4b041-139">If the number of voucher lines is 100 lines or fewer, the reversal process will run immediately.</span></span> <span data-ttu-id="4b041-140">Los resultados se mostrarán en un cuadro diálogo que muestra cualquier asiento que no se ha podido invertir y la razón por la que no ha podido invertirse.</span><span class="sxs-lookup"><span data-stu-id="4b041-140">The results will display in a dialog box that shows any voucher that couldn't be reversed, along with the reason why.</span></span> <span data-ttu-id="4b041-141">Haga clic en **Aceptar** para cerrar el cuadro de diálogo.</span><span class="sxs-lookup"><span data-stu-id="4b041-141">Select **OK** to close the dialog box.</span></span>

<span data-ttu-id="4b041-142">Las transacciones se pueden invertir solo si satisfacen las reglas empresariales para invertirlas.</span><span class="sxs-lookup"><span data-stu-id="4b041-142">Transactions can be reversed only if they meet the business rules for reversing them.</span></span> <span data-ttu-id="4b041-143">Los pagos de proveedor no se pueden invertir con la capacidad anteriormente descrita en este tema.</span><span class="sxs-lookup"><span data-stu-id="4b041-143">Vendor payments cannot be reversed using the capability described in this topic.</span></span> <span data-ttu-id="4b041-144">Los pagos de proveedor deben invertirse de acuerdo con los pasos que se describen en [Inversión de un pago de proveedor](https://docs.microsoft.com/dynamics365/finance/accounts-payable/reverse-vendor-payment).</span><span class="sxs-lookup"><span data-stu-id="4b041-144">Vendor payments must be reversed by following the steps listed in [Reverse a vendor payment](https://docs.microsoft.com/dynamics365/finance/accounts-payable/reverse-vendor-payment).</span></span>

