---
title: Liquidar transacciones entre las cuentas contables
description: Este procedimiento muestra cómo liquidar transacciones entre cuentas contables y cancelar una liquidación de contabilidad.
author: aprilolson
manager: AnnBe
ms.date: 10/03/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransSettlement, LedgerTrialBalanceListPage, LedgerTrialBalanceListPageBalanceParms, LedgerTransAccount, LedgerTransSettled
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8220bacc8d683163e97956ec59a5af929b04319c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994424"
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