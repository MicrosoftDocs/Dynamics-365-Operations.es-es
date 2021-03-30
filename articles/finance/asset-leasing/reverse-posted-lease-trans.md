---
title: Revertir transacciones de arrendamiento contabilizadas
description: Este tema explica cómo revertir una transacción de arrendamiento contabilizada. Cualquier transacción que se cree mediante Arrendamiento de activos se puede revertir.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 22d8eee22221efaf5e7a715c8b95dff261bee62f
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5249734"
---
# <a name="reverse-posted-lease-transactions"></a><span data-ttu-id="0e249-104">Revertir transacciones de arrendamiento contabilizadas</span><span class="sxs-lookup"><span data-stu-id="0e249-104">Reverse posted lease transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0e249-105">Cualquier transacción que se cree mediante Arrendamiento de activos se puede revertir.</span><span class="sxs-lookup"><span data-stu-id="0e249-105">Any transaction that is created through Asset leasing can be reversed.</span></span> <span data-ttu-id="0e249-106">Las transacciones que se revierten mediante Arrendamiento de activos actualizan sus datos de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="0e249-106">Transactions that are reversed through Asset leasing update your lease data.</span></span> <span data-ttu-id="0e249-107">Por lo tanto, también actualizan los valores en libros del pasivo por arrendamiento y el activo por derecho de uso (ROU).</span><span class="sxs-lookup"><span data-stu-id="0e249-107">Therefore, they also update the carrying values of the lease liability and right-of-use (ROU) asset.</span></span>

<span data-ttu-id="0e249-108">Para crear una transacción de reversión para un arrendamiento, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0e249-108">To create a reversing transaction for a lease, follow these steps.</span></span>

1. <span data-ttu-id="0e249-109">En la página **Transacciones de activos** o en la página **Transacciones de pasivo**, seleccione la transacción y luego seleccione **Revertir transacción**.</span><span class="sxs-lookup"><span data-stu-id="0e249-109">On either the **Asset transactions** page or the **Liability transactions** page, select the transaction, and then select **Reverse transaction**.</span></span>
2. <span data-ttu-id="0e249-110">En el cuadro de diálogo que aparece, puede editar la fecha en la que se publicará la entrada inversa.</span><span class="sxs-lookup"><span data-stu-id="0e249-110">In the dialog box that appears, you can edit the date when the reversing entry will be posted.</span></span> <span data-ttu-id="0e249-111">Por defecto, el campo **Fecha** se establece en la fecha de registro de la transacción que seleccionó.</span><span class="sxs-lookup"><span data-stu-id="0e249-111">By default, the **Date** field is set to the transaction posting date of the transaction that you selected.</span></span> <span data-ttu-id="0e249-112">La entrada de reversión no se puede publicar antes de la fecha de registro original de la transacción seleccionada.</span><span class="sxs-lookup"><span data-stu-id="0e249-112">The reversing entry can't be posted earlier than the original posting date of the selected transaction.</span></span>
3. <span data-ttu-id="0e249-113">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e249-113">Select **OK**.</span></span> <span data-ttu-id="0e249-114">Se publica un movimiento de diario que invierte la entrada que seleccionó.</span><span class="sxs-lookup"><span data-stu-id="0e249-114">A journal entry is posted that reverses the entry that you selected.</span></span> <span data-ttu-id="0e249-115">La inversión se muestra en la página **Transacciones de activos** o **Transacciones de pasivo**, y se actualiza el total neto del saldo actual que se muestra en la página.</span><span class="sxs-lookup"><span data-stu-id="0e249-115">The reversal is shown on the **Asset transactions** or **Liability transactions** page, and the net total of the current balance that is shown on the page is updated.</span></span>

<span data-ttu-id="0e249-116">Cuando selecciona **Seguimiento inverso**, aparece un cuadro de diálogo que muestra tanto las transacciones originales como las transacciones revertidas, junto con un número vinculado que se conoce como *número de seguimiento*.</span><span class="sxs-lookup"><span data-stu-id="0e249-116">When you select **Reverse tracing**, a dialog box appears that shows both the original transactions and the reversed transactions, together with a linked number that is known as a *trace number*.</span></span> <span data-ttu-id="0e249-117">Para que las reversiones sean más fáciles de entender y mejorar la visibilidad, también puede realizar un seguimiento de las reversiones mediante las programaciones de arrendamiento.</span><span class="sxs-lookup"><span data-stu-id="0e249-117">To make the reversals easier to understand and to improve visibility, you can also track reversals by using the lease schedules.</span></span>

<span data-ttu-id="0e249-118">El campo **Último número de diario** de la página **Programación** muestra los números de diario de las transacciones.</span><span class="sxs-lookup"><span data-stu-id="0e249-118">The **Latest journal number** field on the **Schedule** page shows the journal numbers of transactions.</span></span> <span data-ttu-id="0e249-119">Cuando se invierte una transacción, este campo se actualiza con el número de diario de una transacción de reversión.</span><span class="sxs-lookup"><span data-stu-id="0e249-119">When a transaction is reversed, this field is updated with the journal number of a reversing transaction.</span></span> <span data-ttu-id="0e249-120">Además, la casilla **Invertido** está seleccionada para indicar que la transacción se ha invertido y el campo **Registrado** está seleccionado.</span><span class="sxs-lookup"><span data-stu-id="0e249-120">Additionally, the **Reversed** check box is selected to indicate that the transaction is reversed, and the **Posted** field is selected.</span></span>

## <a name="revoke-a-reversed-transaction"></a><span data-ttu-id="0e249-121">Revocar una transacción revertida</span><span class="sxs-lookup"><span data-stu-id="0e249-121">Revoke a reversed transaction</span></span>

<span data-ttu-id="0e249-122">Para revocar una transacción revertida, siga estos pasos.</span><span class="sxs-lookup"><span data-stu-id="0e249-122">To revoke a reversed transaction, follow these steps.</span></span>

1. <span data-ttu-id="0e249-123">En la página **Programación** o **Transacciones**, seleccione la transacción original.</span><span class="sxs-lookup"><span data-stu-id="0e249-123">On either the **Schedule** page or the **Transactions** page, select the original transaction.</span></span>
2. <span data-ttu-id="0e249-124">Siga uno de estos pasos:</span><span class="sxs-lookup"><span data-stu-id="0e249-124">Follow one of these steps:</span></span>

    - <span data-ttu-id="0e249-125">Si seleccionó la transacción en la página **Programación**, siga los pasos para crear un diario en [Crear movimientos de diario mensuales en un lote](create-monthly-journals-batch.md).</span><span class="sxs-lookup"><span data-stu-id="0e249-125">If you selected the transaction on the **Schedule** page, follow the steps for creating a journal in [Create monthly journal entries in a batch](create-monthly-journals-batch.md).</span></span> <span data-ttu-id="0e249-126">Debe registrar manualmente el diario.</span><span class="sxs-lookup"><span data-stu-id="0e249-126">You must manually post the journal.</span></span>
    - <span data-ttu-id="0e249-127">Si seleccionó la transacción en la página **Transacciones**, seleccione **Transacción inversa**.</span><span class="sxs-lookup"><span data-stu-id="0e249-127">If you selected the transaction on the **Transactions** page, select **Reverse transaction**.</span></span> <span data-ttu-id="0e249-128">Recibirá un mensaje que indica que esta revocación es una revocación de una revocación anterior y que puede editar la fecha de registro de esta revocación.</span><span class="sxs-lookup"><span data-stu-id="0e249-128">You receive a message that states that this revocation is a revocation of an earlier reversal, and that you can edit the posting date for this revocation.</span></span> <span data-ttu-id="0e249-129">Sin embargo, las validaciones comerciales generales afectan las fechas que se pueden introducir en el campo **Fecha**.</span><span class="sxs-lookup"><span data-stu-id="0e249-129">However, general business validations affect the dates that can be entered in the **Date** field.</span></span> 

3. <span data-ttu-id="0e249-130">Seleccione **Aceptar**.</span><span class="sxs-lookup"><span data-stu-id="0e249-130">Select **OK**.</span></span> <span data-ttu-id="0e249-131">Se publica un movimiento de diario que invierte la entrada que seleccionó.</span><span class="sxs-lookup"><span data-stu-id="0e249-131">A journal entry is posted that reverses the entry that you selected.</span></span> <span data-ttu-id="0e249-132">La inversión se muestra en la página **Transacciones**, y el saldo actual neto total se restaura a lo que era antes de la primera reversión.</span><span class="sxs-lookup"><span data-stu-id="0e249-132">The reversal is shown on the **Transactions** page, and the net total current balance is restored to what it was before the first reversal.</span></span> <span data-ttu-id="0e249-133">Por tanto, se niega el impacto que tuvo la reversión en los saldos.</span><span class="sxs-lookup"><span data-stu-id="0e249-133">Therefore, the impact that the reversal had on the balances is negated.</span></span>

<span data-ttu-id="0e249-134">Cuando selecciona **Seguimiento de reversiones**, aparece un cuadro de diálogo que muestra tanto las transacciones originales como las transacciones revertidas, junto con un número de seguimiento vinculado.</span><span class="sxs-lookup"><span data-stu-id="0e249-134">When you select **Reverse tracing**, a dialog box appears that shows both the original transactions and the reversed transactions, together with a linked trace number.</span></span>

<span data-ttu-id="0e249-135">También puede realizar un seguimiento de las revocaciones mediante el uso de la página **Programaciones**.</span><span class="sxs-lookup"><span data-stu-id="0e249-135">You can also track revocations by using the appropriate **Schedules** page.</span></span> <span data-ttu-id="0e249-136">El campo **Revertir** se borra, mientras que el campo **Diario registrado** se selecciona.</span><span class="sxs-lookup"><span data-stu-id="0e249-136">The **Reverse** field is cleared, whereas the **Journal posted** field is selected.</span></span> <span data-ttu-id="0e249-137">Además, el campo **Último número de diario** se actualiza con el número de diario de la transacción de revocación y el campo **Número de diario** se actualiza con el número de diario de reversión.</span><span class="sxs-lookup"><span data-stu-id="0e249-137">Additionally, the **Latest journal number** field is updated with the journal number of the revocation transaction, and the **Journal number** field is updated with the reversal journal number.</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]