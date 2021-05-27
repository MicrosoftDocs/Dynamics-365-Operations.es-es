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
# <a name="purchase-accrual-that-has-a-zero-amount-is-posted-for-a-zero-value-product-receipt"></a>La acumulación de compras que tiene un importe cero se registra para un recibo de producto de valor cero

Número de KB: 4612588

## <a name="symptoms"></a>Síntomas

Cuando se registra una recepción de producto que tiene un valor cero, el sistema crea un registro para la acumulación de compras donde el importe es 0 (cero).

## <a name="resolution"></a>Resolución

De forma predeterminada, para los registros contables del tipo *Compra, acumulación*, el campo `IsTransferredIndetail` siempre se establece en *Resumen* en transacciones del libro mayor auxiliar. Por lo tanto, el sistema crea una entrada de asiento relacionada incluso si el importe es 0 (cero).

Para omitir este tipo de registro cuando el importe es 0 (cero), amplíe el método `subledgerJournalizer.markDoNotTransferEntries` para que incluya `ledgerPostingType = PurchPckSlpPurchaseOffsetAccount`, como se muestra en el siguiente ejemplo.

```xpp
update_recordset existingSubledgerJournalAccountEntry
setting
    IsTransferredInDetail = TransferPolicy::DoNotTransfer
where existingSubledgerJournalAccountEntry.SubledgerJournalEntry == _subledgerJournalEntryRecId
    && (existingSubledgerJournalAccountEntry.AccountingCurrencyAmount == 0 && existingSubledgerJournalAccountEntry.ReportingCurrencyAmount == 0)
    && existingSubledgerJournalAccountEntry.PostingType == LedgerPostingType::PurchPckSlpPurchaseOffsetAccount;
```
