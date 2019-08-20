---
title: Liquidar un cheque con pago diferido para un proveedor
description: Liquide un cheque con pago diferido emitido a un proveedor cuando el banco haya compensado la transacción del cheque después de que el cheque haya vencido y lo haya compensado el banco.
author: kweekley
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPostDatedChecks, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 6d935ec24d97ca76a088cbe41d57c12c6e8a6689
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/01/2019
ms.locfileid: "1841834"
---
# <a name="settle-a-postdated-check-for-a-vendor"></a>Liquidar un cheque con pago diferido para un proveedor

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

