---
title: Crear una cancelación de un diario para un cliente
description: Esta guía de tarea le mostrará cómo configurar los parámetros para las cancelaciones y después cancelar transacciones desde la página Cobros, la página Facturas de cliente abiertas y la página Cliente.
author: ShivamPandey-msft
ms.date: 07/01/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CustParameters, CustPosting, DefaultDashboard, CustCollectionsPoolsListPage, CustWriteOff, LedgerJournalTable, LedgerJournalTransDaily, CustCollections, CustOpenInvoicesListPage, CustTable
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 21aaeda413e767fed1815423b0262127c6692bb6
ms.sourcegitcommit: 9740f9b41a7dcf1821c6baccb2e05b9865ac2966
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2022
ms.locfileid: "9775309"
---
# <a name="create-a-write-off-journal-for-a-customer"></a>Crear una cancelación de un diario para un cliente

[!include [banner](../../includes/banner.md)]

Esta guía de tarea le mostrará cómo configurar los parámetros para las cancelaciones y después cancelar transacciones desde la página Cobros, la página Facturas de cliente abiertas y la página Cliente. Esta tarea usa la empresa de demostración USMF.


## <a name="set-up-the-write-off-parameters"></a>Configuración de parámetros de cancelación
1. Vaya al **Panel de exploración > Módulos > Crédito y cobros > Configuración > Parámetros de clientes**.
2. Haga clic en la ficha **Cobros**.
3. Expanda o contraiga la sección **Cancelación**.
    - El **Diario de cancelaciones** es el diario general que guardará las transacciones de cancelación que cree.  
    - Puede vincular un código de motivo a cada cancelación. Puede sobrescribir este valor predeterminado al realizar la cancelación.  
    - Establezca **Impuestos independientes** en Sí si desea separar los impuestos de la transacción original en la cancelación.  
4. Cierre la página.
5. Vaya a **Crédito y cobros > Configuración > Perfiles de contabilización del cliente.** La cuenta de cancelación se usará como cuenta de gastos o ajuste de reserva en el diario general.
6. Cierre la página.

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a>Cancelación del saldo de un cliente desde la página de saldos vencidos
1. Vaya a **Crédito y cobros > Cobros > Saldos vencidos**.
2. Marque la fila del cliente que desee cancelar. Por ejemplo, marque la línea con Birch Company.
3. En el **panel de acciones**, haga clic en **Cobrar**.
4. Haga clic en **Cancelar**.
5. Haga clic en **Aceptar**.
6. Cierre la página.
7. Vaya a **Panel de exploración > Módulos > Contabilidad general > Entradas del diario > Diarios generales**.
8. Seleccione el número de lote del diario que contiene la cancelación. Se crea una línea para revertir el saldo del cliente. Se crean una o más líneas para registrar la cancelación en la cuenta de cancelación.  
9. Cierre la página.


## <a name="write-off-transactions-from-the-collections-page"></a>Cancelar transacciones desde la página de cobros
1. Vaya a **Crédito y cobros > Cobros > Saldos vencidos**.
2. Seleccione el nombre del cliente con las transacciones que desee cancelar. Por ejemplo, seleccione Cave Wholesales (US-004).
3. Marque la fila de la primera transacción.
4. Marque la fila de la segunda transacción.
5. Haga clic en **Cancelar**.
6. En el campo **Comentario de motivo**, escriba "Deudas incorrectas".
7. Haga clic en **Aceptar**.
8. Cierre la página.
9. Cierre la página.
10. Vaya a **Contabilidad general > Movimientos de diario > Diarios generales**.
11. Seleccione el número de lote del diario que contiene la cancelación. Se crea una línea para revertir el saldo del cliente. Se crean una o más líneas para registrar la cancelación en la cuenta de cancelación.  
12. Cierre la página.


## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a>Cancelación de una factura desde la página Abrir facturas de cliente
1. Vaya a **Panel de exploración >Módulos > Clientes > Facturas > Facturas de clientes abiertas**.
2. Marque la línea de una factura. Por ejemplo, marque la línea para CIV-000667.
3. En el **panel de acciones**, haga clic en **Factura**.
4. Haga clic en **Cancelar**.
5. Haga clic en **Aceptar**.
6. Cierre la página.

## <a name="write-off-a-customer-balance-from-the-customer-page"></a>Cancelación del saldo de un cliente desde la página del cliente
1. Vaya a **Clientes > Clientes > Todos los clientes**.
2. Seleccionar una cuenta de cliente. Por ejemplo, seleccione US-001 (Contoso Retail San Diego).
3. En el **panel de acciones**, haga clic en **Cobrar**.
4. Haga clic en **Cancelar**.
5. Haga clic en **Aceptar**.
6. Cierre la página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
