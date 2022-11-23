---
title: Liquidar un cheque con pago diferido para un proveedor
description: Liquide un cheque con pago diferido emitido a un proveedor cuando el banco haya compensado la transacción del cheque después de que el cheque haya vencido y lo haya compensado el banco.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 3e3816a2f1c95d568a173cb07daad0473703da9c
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779511"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a>Liquidar un cheque con pago diferido para un proveedor

[!include [banner](../../includes/banner.md)]

Liquide un cheque con pago diferido emitido a un proveedor cuando el banco haya compensado la transacción del cheque después de que el cheque haya vencido y lo haya compensado el banco. 

Complete los siguientes procedimientos antes de empezar este.

1) Configuración de cheques con pago diferido

2) Registrar un cheque con pago diferido para un proveedor



El rol de este procedimiento es Tesorero. Este procedimiento usa la empresa de demostración USMF.

1. Vaya a **Proveedores > Pagos > Cheques con fecha futura de proveedor**.
2. Haga clic en **Liquidar**.
3. Haga clic en **Liquidar entidades de compensación**.
    * Liquide la cuenta de proveedor para la transacción de cheque.  
4. Cierre la página.
5. Vaya a **Contabilidad general > Movimientos de diario > Diarios generales**.
6. En el campo **Mostrar**, seleccione **Todos**.
7. Active o desactive la casilla **Mostrar solo creados por el usuario**.
8. En la lista, marque la fila seleccionada.
9. Haga clic en **Líneas**.
10. Haga clic en **Asiento**.
11. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
