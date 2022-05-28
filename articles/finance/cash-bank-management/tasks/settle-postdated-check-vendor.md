---
title: Liquidar un cheque con pago diferido para un proveedor
description: Liquide un cheque con pago diferido emitido a un proveedor cuando el banco haya compensado la transacción del cheque después de que el cheque haya vencido y lo haya compensado el banco.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f9564bf0ded6acbd05c7953798ea02959babbdfd
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726305"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a>Liquidar un cheque con pago diferido para un proveedor

[!include [banner](../../includes/banner.md)]

Liquide un cheque con pago diferido emitido a un proveedor cuando el banco haya compensado la transacción del cheque después de que el cheque haya vencido y lo haya compensado el banco. 

Complete los siguientes procedimientos antes de empezar este.

1) Configuración de cheques con pago diferido

2) Registrar un cheque con pago diferido para un proveedor



El rol de este procedimiento es Tesorero. Este procedimiento usa la empresa de demostración USMF.

1. Vaya a Proveedores > Pagos > Cheques con fecha futura de proveedor.
2. Haga clic en Liquidar.
3. Haga clic en Liquidar entidades de compensación.
    * Liquide la cuenta de proveedor para la transacción de cheque.  
4. Cierre la página.
5. Vaya a Contabilidad general > Movimientos de diario > Diarios generales.
6. En el campo Mostrar, seleccione "Todos".
7. Active o desactive la casilla Mostrar sólo creados por el usuario.
8. En la lista, marque la fila seleccionada.
9. Haga clic en Líneas.
10. Haga clic en Asiento.
11. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
