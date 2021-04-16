---
title: Liquidar transacciones entre las cuentas contables
description: Este procedimiento muestra cómo liquidar transacciones entre cuentas contables y cancelar una liquidación de contabilidad.
author: aprilolson
ms.date: 10/03/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransSettlement, LedgerTrialBalanceListPage, LedgerTrialBalanceListPageBalanceParms, LedgerTransAccount, LedgerTransSettled
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b2594b90ed58a1e7f12c8a94d3c48266faef557f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5817062"
---
# <a name="settle-transactions-between-ledger-accounts"></a>Liquidar transacciones entre las cuentas contables

[!include [banner](../../includes/banner.md)]

Este procedimiento muestra cómo liquidar transacciones entre cuentas contables y cancelar una liquidación de contabilidad. Este procedimiento usa la empresa de datos de demostración USMF.


## <a name="settle-transaction-between-ledger-accounts"></a>Liquidar transacción entre las cuentas contables
1. Vaya a Contabilidad general > Tareas periódicas > Liquidaciones de contabilidad.
2. En la lista, encuentre la transacción que desee liquidar.
   > [!NOTE]
   > El importe del saldo debe ser cero.  
3. Haga clic en Incluir.
4. Haga clic en Aceptar.

## <a name="cancel-a-ledger-settlement"></a>Cancelar una liquidación de contabilidad

1. Vaya a Contabilidad general > Consultas e informes > Saldo de comprobación.
2. Haga clic en Parámetros para abrir el cuadro de diálogo desplegable.
3. Haga clic en Actualizar.
4. En la lista, encuentre la cuenta que tiene la transacción liquidada.
5. Haga clic en Todas las transacciones.
6. Use un filtro para buscar fácilmente la transacción en la lista.
7. Haga clic en Liquidaciones contables.
8. En la lista, marque la fila seleccionada.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]