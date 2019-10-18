---
title: Invertir diario de registro
description: Este tema describe capacidades que le permiten invertir los asientos de la transacción de asiento o lista de los diarios financieros.
author: MikeFalkner
manager: AnnBe
ms.date: 08/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a5456e60f1f3cee5f83ac7f725f7e01ba5bd7a1
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248594"
---
# <a name="reverse-journal-posting"></a><span data-ttu-id="6a175-103">Invertir diario de registro</span><span class="sxs-lookup"><span data-stu-id="6a175-103">Reverse journal posting</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="6a175-104">Este tema describe las capacidades Microsoft Dynamics 365 Finance que permiten que invierta el diario entero o que invierta uno o varios asientos de la transacción de asiento enumerada independientemente de su origen.</span><span class="sxs-lookup"><span data-stu-id="6a175-104">This topic describes capabilities Microsoft Dynamics 365 Finance that allows you to reverse an entire journal or reverse one or more vouchers from the voucher transaction list regardless of their origin.</span></span> 

## <a name="reversing-journals"></a><span data-ttu-id="6a175-105">Invertir los diarios</span><span class="sxs-lookup"><span data-stu-id="6a175-105">Reversing journals</span></span>

<span data-ttu-id="6a175-106">Puede invertir las líneas de diario de forma individual.</span><span class="sxs-lookup"><span data-stu-id="6a175-106">You can reverse journal lines individually.</span></span> <span data-ttu-id="6a175-107">Con el registro de invertir diario, también puede invertir un diario financiero completo.</span><span class="sxs-lookup"><span data-stu-id="6a175-107">With reverse journal posting, you can also reverse an entire financial journal.</span></span> <span data-ttu-id="6a175-108">Para invertir un diario:</span><span class="sxs-lookup"><span data-stu-id="6a175-108">To reverse a journal:</span></span> 
- <span data-ttu-id="6a175-109">Abra el diario y filtre según los diarios registrados</span><span class="sxs-lookup"><span data-stu-id="6a175-109">Open the financial journal and filter on posted journals</span></span>
- <span data-ttu-id="6a175-110">Haga clic en el menú Invertir en la parte superior de la página</span><span class="sxs-lookup"><span data-stu-id="6a175-110">Click on the Reverse menu at the top of the page</span></span>
- <span data-ttu-id="6a175-111">Verá el número total de asientos y las líneas de asiento junto con el importe total de las líneas que son invertidas</span><span class="sxs-lookup"><span data-stu-id="6a175-111">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="6a175-112">Seleccione Sí para usar las fechas de transacción actuales o No para introducir una nueva.</span><span class="sxs-lookup"><span data-stu-id="6a175-112">Select Yes to use the existing transaction dates or No to enter a new one.</span></span> <span data-ttu-id="6a175-113">En algunos casos, el período de la transacción original estar cerrado y puede querer especificar una nueva fecha de transacción para la inversión.</span><span class="sxs-lookup"><span data-stu-id="6a175-113">In some cases, the period of the original transaction may be closed and you want to enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="6a175-114">Si ha seleccionado No, especifique una fecha de transacción para la inversión.</span><span class="sxs-lookup"><span data-stu-id="6a175-114">If you selected No, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="6a175-115">Escriba el comentario que desee agregar a la transacción de inversión</span><span class="sxs-lookup"><span data-stu-id="6a175-115">Enter a comment that you want added to the reversal transaction</span></span>
- <span data-ttu-id="6a175-116">Haga clic en el botón Invertir</span><span class="sxs-lookup"><span data-stu-id="6a175-116">Click the Reverse button</span></span>

<span data-ttu-id="6a175-117">Las transacciones se invertirán.</span><span class="sxs-lookup"><span data-stu-id="6a175-117">The transactions will be reversed.</span></span> 

<span data-ttu-id="6a175-118">Si el número de líneas de asiento supera las 100, el proceso de inversión se ejecuta mediante el proceso por lotes.</span><span class="sxs-lookup"><span data-stu-id="6a175-118">If the number of voucher lines exceeds 100 lines, the reversal process will be run using the batch process.</span></span> <span data-ttu-id="6a175-119">Puede revisar los resultados de la inversión viendo los comentarios en el trabajo por lotes que se ejecutó.</span><span class="sxs-lookup"><span data-stu-id="6a175-119">You can review the results of the reversal by viewing the comments in the batch job that was run.</span></span> <span data-ttu-id="6a175-120">Todos los errores se anotarán en el historial del trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="6a175-120">All failures will be noted in the batch job history.</span></span>

<span data-ttu-id="6a175-121">Si el número de líneas de asiento es 100 o menos, el proceso de inversión se ejecutará inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="6a175-121">If the number of voucher lines is 100 lines or less, the reversal process will run immediately.</span></span> <span data-ttu-id="6a175-122">Los resultados se mostrarán en un diálogo que muestra cualquier asiento que no se ha podido invertir y la razón por la que no ha podido invertirse.</span><span class="sxs-lookup"><span data-stu-id="6a175-122">The results will be presented in a dialog that shows any voucher that could not be reversed and the reason why it could not be reversed.</span></span> <span data-ttu-id="6a175-123">Haga clic en Aceptar para cerrar el diálogo.</span><span class="sxs-lookup"><span data-stu-id="6a175-123">Click on Ok to close the dialog.</span></span>

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a><span data-ttu-id="6a175-124">Invertir los asientos de la lista de la transacción de asiento.</span><span class="sxs-lookup"><span data-stu-id="6a175-124">Reversing vouchers from the voucher transaction list.</span></span> 

<span data-ttu-id="6a175-125">También puede invertir los asientos de la **Lista de la transacción de asiento** a través de todos los sublibros de contabilidad.</span><span class="sxs-lookup"><span data-stu-id="6a175-125">You can also reverse vouchers from the **Voucher transaction list** across all subledgers.</span></span> <span data-ttu-id="6a175-126">Además, puede invertir más de un asiento al mismo tiempo.</span><span class="sxs-lookup"><span data-stu-id="6a175-126">In addition, you can reverse more than one voucher at a time.</span></span> 

<span data-ttu-id="6a175-127">Para invertir uno o varios asientos:</span><span class="sxs-lookup"><span data-stu-id="6a175-127">To reverse one or more vouchers:</span></span> 
- <span data-ttu-id="6a175-128">Haga clic en el menú Invertir en la parte superior de la página</span><span class="sxs-lookup"><span data-stu-id="6a175-128">Click on the Reverse menu at the top of the page</span></span>
- <span data-ttu-id="6a175-129">Verá el número total de asientos y las líneas de asiento junto con el importe total de las líneas que son invertidas</span><span class="sxs-lookup"><span data-stu-id="6a175-129">You will see the total number of vouchers and voucher lines as well as the total amount of the lines being reversed</span></span>
- <span data-ttu-id="6a175-130">Seleccione Sí para usar las fechas de transacción actuales o No para introducir una nueva.</span><span class="sxs-lookup"><span data-stu-id="6a175-130">Select Yes to use the existing transaction dates or No to enter a new one.</span></span> <span data-ttu-id="6a175-131">En algunos casos, el período de la transacción original estar cerrado y puede querer especificar una nueva fecha de transacción para la inversión.</span><span class="sxs-lookup"><span data-stu-id="6a175-131">In some cases, the period of the original transaction may be closed and you want to enter a new transaction date for the reversal.</span></span>
- <span data-ttu-id="6a175-132">Si ha seleccionado No, especifique una fecha de transacción para la inversión.</span><span class="sxs-lookup"><span data-stu-id="6a175-132">If you selected No, enter a transaction date for the reversal.</span></span> 
- <span data-ttu-id="6a175-133">Escriba el comentario que desee agregar a la transacción de inversión</span><span class="sxs-lookup"><span data-stu-id="6a175-133">Enter a comment that you want added to the reversal transaction</span></span>
- <span data-ttu-id="6a175-134">Haga clic en el botón Invertir</span><span class="sxs-lookup"><span data-stu-id="6a175-134">Click the Reverse button</span></span>

<span data-ttu-id="6a175-135">Las transacciones se invertirán.</span><span class="sxs-lookup"><span data-stu-id="6a175-135">The transactions will be reversed.</span></span> 

<span data-ttu-id="6a175-136">Si el número de líneas de asiento supera las 100, el proceso de inversión se ejecuta mediante el proceso por lotes.</span><span class="sxs-lookup"><span data-stu-id="6a175-136">If the number of voucher lines exceeds 100 lines, the reversal process will be run using the batch process.</span></span> <span data-ttu-id="6a175-137">Puede revisar los resultados de la inversión viendo los comentarios en el trabajo por lotes que se ejecutó.</span><span class="sxs-lookup"><span data-stu-id="6a175-137">You can review the results of the reversal by viewing the comments in the batch job that was run.</span></span> <span data-ttu-id="6a175-138">Todos los errores se anotarán en el historial del trabajo por lotes.</span><span class="sxs-lookup"><span data-stu-id="6a175-138">All failures will be noted in the batch job history.</span></span>

<span data-ttu-id="6a175-139">Si el número de líneas de asiento es 100 o menos, el proceso de inversión se ejecutará inmediatamente.</span><span class="sxs-lookup"><span data-stu-id="6a175-139">If the number of voucher lines is 100 lines or less, the reversal process will run immediately.</span></span> <span data-ttu-id="6a175-140">Los resultados se mostrarán en un diálogo que muestra cualquier asiento que no se ha podido invertir y la razón por la que no ha podido invertirse.</span><span class="sxs-lookup"><span data-stu-id="6a175-140">The results will be presented in a dialog that shows any voucher that could not be reversed and the reason why it could not be reversed.</span></span> <span data-ttu-id="6a175-141">Haga clic en Aceptar para cerrar el diálogo.</span><span class="sxs-lookup"><span data-stu-id="6a175-141">Click on Ok to close the dialog.</span></span>

