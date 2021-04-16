---
title: Registrar un cheque con pago diferido para un proveedor
description: Puede registrar detalles de un cheque posfechado antes de emitir el cheque a un proveedor utilizando un asiento del asiento de diario.
author: kweekley
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cb7f9935b20d042551b0ce77fd6bdbf55e9f9669
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/01/2021
ms.locfileid: "5834677"
---
# <a name="register-and-post-a-postdated-check-for-a-vendor"></a>Registrar un cheque con pago diferido para un proveedor

[!include [banner](../../includes/banner.md)]

Puede registrar detalles de un cheque posfechado antes de emitir el cheque a un proveedor utilizando un asiento del asiento de diario. También puede registrar los cheques con fecha futura y generar transacciones financieras. Antes de registrar y enviar un cheque posfechado de un proveedor, complete las siguiente tarea: 

Establezca cheques posfechados en la página de gestión de efectivo y bancos. 



El rol de esta guía de tareas es Tesorero. Esta tarea usa la empresa de demostración USMF.

1. Vaya a Proveedores > Pagos > Diario de pagos.
2. Haga clic en Nuevo.
3. En el campo Nombre, escriba "VendPay".
4. Haga clic en Líneas.
5. En el campo Cuenta, especifique los valores deseados.
6. En la lista, marque la fila seleccionada.
7. En el campo Débito, escriba un número.
8. En el campo Forma de pago, haga clic en el botón desplegable para abrir la búsqueda.
    * Seleccione la forma de pago del cheque con fecha futura.  
9. En la lista, busque y seleccione el registro deseado.
10. En la lista, haga clic en el vínculo de la fila seleccionada.
11. Haga clic en la ficha Cheques con fecha futura.
12. En el campo Número de cheque, escriba un valor.
    * Especifique o modifique el número del cheque posfechado.  
13. En el campo Nombre del banco emisor, escriba un valor.
    * Escriba los detalles bancarios para el banco emisor.  
14. Haga clic en la ficha Lista.
15. Haga clic en Registrar.
16. Cierre la página.
17. Haga clic en la ficha Cheques con fecha futura.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]