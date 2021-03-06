---
title: Liquidar un cheque con pago diferido de un cliente
description: Puede liquidar un cheque posfechado después de que el banco lo haya desactivado.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustPostDatedChecks, SystemDate, LedgerJournalTable, LedgerJournalTransDaily, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f714e41f47a31bce16424de18878d2f5acb5028d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834558"
---
# <a name="settle-a-postdated-check-from-a-customer"></a>Liquidar un cheque con pago diferido de un cliente

[!include [banner](../../includes/banner.md)]

Puede liquidar un cheque posfechado después de que el banco lo haya desactivado. Esta transacción financiera también se eliminará la transacción de cuenta puente para el cheque posfechado. 

Las siguientes tareas se deben realizar antes de comenzar esta.

1) Configuración de cheques con pago diferido

2) Registrar un cheque con pago diferido para un cliente 



El rol de esta guía de tareas es Tesorero.



Este procedimiento usa la empresa de demostración USMF.

1. Vaya a Crédito y cobros > Consultas e informes > Pagos > Cheques con fecha futura de cliente.
2. Haga clic en Liquidar.
3. Haga clic en Liquidar entidades de compensación.
    * Liquide la cuenta del cliente para la transacción de cheque.  
4. Cierre la página.
5. Vaya a Contabilidad general > Movimientos de diario > Diarios generales.
6. En el campo Mostrar, seleccione una opción.
7. Active o desactive la casilla Mostrar sólo creados por el usuario.
8. En la lista, busque y seleccione el registro deseado.
9. Haga clic en Líneas.
10. Haga clic en Asiento.
11. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]