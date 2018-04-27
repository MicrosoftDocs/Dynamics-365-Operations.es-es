--- 
title: "Crear una cancelación de un diario para un cliente"
description: "Esta guía de tarea le mostrará cómo configurar los parámetros para las cancelaciones y después cancelar transacciones desde la página Cobros, la página Facturas de cliente abiertas y la página Cliente."
author: ShivamPandey-msft
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
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 19a816f04283ce4f200de7396617313e45e057db
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-write-off-journal-for-a-customer"></a>Crear una cancelación de un diario para un cliente

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Esta guía de tarea le mostrará cómo configurar los parámetros para las cancelaciones y después cancelar transacciones desde la página Cobros, la página Facturas de cliente abiertas y la página Cliente. Esta tarea usa la empresa de demostración USMF.


## <a name="set-up-the-write-off-parameters"></a>Configuración de parámetros de cancelación
1. Vaya a Crédito y cobros > Configuración > Parámetros de clientes.
2. Haga clic en la ficha Cobros.
3. Expanda o contraiga la sección Cancelación.
    * El diario de cancelación es el diario general que guardará las transacciones de cancelación que cree.  
    * Puede vincular un código de motivo a cada cancelación. Puede sobrescribir este valor predeterminado al realizar la cancelación.  
    * Defina esta opción en Sí si desea separar los impuestos de la transacción original en la cancelación.  
4. Cierre la página.
5. Vaya a Crédito y cobros > Configuración > Perfiles de contabilización del cliente.
    * La cuenta de cancelación se usará como cuenta de gastos o ajuste de reserva en el diario general.   
6. Cierre la página.

## <a name="write-off-a-customer-balance-from-the-aged-balances-page"></a>Cancelación del saldo de un cliente desde la página de saldos vencidos
1. Vaya a Crédito y cobros > Cobros > Saldos vencidos.
2. Marque la fila del cliente que desee cancelar. Por ejemplo, marque la línea con Birch Company.
3. En el panel de acciones, haga clic en Cobrar.
4. Haga clic en Cancelar.
5. Haga clic en Aceptar
6. Cierre la página.
7. Vaya a Contabilidad general > Movimientos de diario > Diarios generales.
8. Seleccione el número de lote del diario que contiene la cancelación.
    * Se crea una línea para revertir el saldo del cliente. Se crean una o más líneas para registrar la cancelación en la cuenta de cancelación.  
9. Cierre la página.
10. Cierre la página.

## <a name="write-off-transactions-from-the-collections-form"></a>Cancele transacciones desde el formulario de cobros.
1. Vaya a Crédito y cobros > Cobros > Saldos vencidos.
2. Seleccione el nombre del cliente con las transacciones que desee cancelar. Por ejemplo, seleccione Cave Wholesales (US-004).
3. Marque la fila de la primera transacción.
4. Marque la fila de la segunda transacción.
5. Haga clic en Cancelar.
6. En el campo Comentario de motivo, escriba "Deudas incorrectas".
7. Haga clic en Aceptar
8. Cierre la página.
9. Cierre la página.
10. Vaya a Contabilidad general > Movimientos de diario > Diarios generales.
11. Seleccione el número de lote del diario que contiene la cancelación.
    * Se crea una línea para revertir el saldo del cliente. Se crean una o más líneas para registrar la cancelación en la cuenta de cancelación.  
12. Cierre la página.
13. Cierre la página.

## <a name="write-off-an-invoice-from-the-open-customers-invoices-page"></a>Cancelación de una factura desde la página Abrir facturas de cliente
1. Vaya a Clientes > Facturas > Facturas de cliente abiertas.
2. Marque la línea de una factura. Por ejemplo, marque la línea para CIV-000667.
3. En el panel de acciones, haga clic en Factura.
4. Haga clic en Cancelar.
5. Haga clic en Aceptar
6. Cierre la página.

## <a name="write-off-a-customer-balance-from-the-customer-page"></a>Cancelación del saldo de un cliente desde la página del cliente
1. Vaya a Clientes > Clientes > Todos los clientes.
2. Seleccionar una cuenta de cliente. Por ejemplo, seleccione US-001 (Contoso Retail San Diego).
3. En el panel de acciones, haga clic en Cobrar.
4. Haga clic en Cancelar.
5. Haga clic en Aceptar
6. Cierre la página.


