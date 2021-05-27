---
title: La acumulación de compras que tiene un importe cero se registra para un recibo de producto de valor cero
description: Cuando se registra una recepción de producto que tiene un valor cero, el sistema crea un registro para la acumulación de compras donde el importe es 0 (cero).
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: LedgerTransVoucher
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: f8d9d857590dc788d16b01edf77600d8fd8c8444
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026897"
---
# <a name="purchase-accrual-that-has-a-zero-amount-is-posted-for-a-zero-value-product-receipt"></a><span data-ttu-id="29d88-103">La acumulación de compras que tiene un importe cero se registra para un recibo de producto de valor cero</span><span class="sxs-lookup"><span data-stu-id="29d88-103">Purchase accrual that has a zero amount is posted for a zero-value product receipt</span></span>

<span data-ttu-id="29d88-104">Número de KB: 4612588</span><span class="sxs-lookup"><span data-stu-id="29d88-104">KB number: 4612588</span></span>

## <a name="symptoms"></a><span data-ttu-id="29d88-105">Síntomas</span><span class="sxs-lookup"><span data-stu-id="29d88-105">Symptoms</span></span>

<span data-ttu-id="29d88-106">Cuando se registra una recepción de producto que tiene un valor cero, el sistema crea un registro para la acumulación de compras donde el importe es 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="29d88-106">When a product receipt that has zero value is posted, the system creates a posting to purchase accrual where the amount is 0 (zero).</span></span>

## <a name="resolution"></a><span data-ttu-id="29d88-107">Resolución</span><span class="sxs-lookup"><span data-stu-id="29d88-107">Resolution</span></span>

<span data-ttu-id="29d88-108">De forma predeterminada, para los registros contables del tipo *Compra, acumulación*, el campo `IsTransferredIndetail` siempre se establece en *Resumen* en transacciones del libro mayor auxiliar.</span><span class="sxs-lookup"><span data-stu-id="29d88-108">By default, for ledger postings of the *Purchase, accrual* type, the `IsTransferredIndetail` field is always set to *Summary* in subledger transactions.</span></span> <span data-ttu-id="29d88-109">Por lo tanto, el sistema crea una entrada de asiento relacionada incluso si el importe es 0 (cero).</span><span class="sxs-lookup"><span data-stu-id="29d88-109">Therefore, the system creates a related voucher entry even if the amount is 0 (zero).</span></span>

<span data-ttu-id="29d88-110">Para omitir este tipo de registro cuando el importe es 0 (cero), amplíe el método `subledgerJournalizer.markDoNotTransferEntries` para que incluya `ledgerPostingType = PurchPckSlpPurchaseOffsetAccount`, como se muestra en el siguiente ejemplo.</span><span class="sxs-lookup"><span data-stu-id="29d88-110">To skip this posting type when the amount is 0 (zero), extend the `subledgerJournalizer.markDoNotTransferEntries` method so that it includes `ledgerPostingType = PurchPckSlpPurchaseOffsetAccount`, as shown in the following example.</span></span>

```xpp
update_recordset existingSubledgerJournalAccountEntry
setting
    IsTransferredInDetail = TransferPolicy::DoNotTransfer
where existingSubledgerJournalAccountEntry.SubledgerJournalEntry == _subledgerJournalEntryRecId
    && (existingSubledgerJournalAccountEntry.AccountingCurrencyAmount == 0 && existingSubledgerJournalAccountEntry.ReportingCurrencyAmount == 0)
    && existingSubledgerJournalAccountEntry.PostingType == LedgerPostingType::PurchPckSlpPurchaseOffsetAccount;
```
