--- 
title: Liquidar un cheque con pago diferido para un proveedor
description: "Liquide un cheque con pago diferido emitido a un proveedor cuando el banco haya compensado la transacción del cheque después de que el cheque haya vencido y lo haya compensado el banco."
author: kweekley
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 76c948ba99f9b4fa9200c2541c221c4ca86414e4
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="settle-a-postdated-check-for-a-vendor"></a>Liquidar un cheque con pago diferido para un proveedor

[!include[task guide banner](../../includes/task-guide-banner.md)]

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

