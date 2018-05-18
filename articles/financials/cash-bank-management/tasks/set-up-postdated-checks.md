--- 
title: "Configuración de cheques con pago diferido"
description: "En este tema se explica cómo especificar si desea registrar entradas de diario para cheques con fecha futura y qué diarios de registro desea usar para liquidar entradas y pagos de proveedor."
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
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: d83713f9d54b396a10894995024ac1c8dd47a6f1
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="set-up-postdated-checks"></a>Configuración de cheques con pago diferido

[!include [task guide banner](../../includes/task-guide-banner.md)]

En este tema se explica cómo especificar si desea registrar entradas de diario para cheques con fecha futura y qué diarios de registro desea usar para liquidar entradas y pagos de proveedor. También puede especificar cuentas de compensación para cheques emitidos, cheques recibidos y retención de impuestos. Cheques con fecha futura que se emiten con el fin de realizar y recibir pagos en una fecha futura. Puede especificar si el cheque debe reflejarse en los libros financieros antes de la fecha de vencimiento.



El rol de este procedimiento es Tesorero. Este procedimiento usa la empresa de demostración USMF.


## <a name="set-up-postdated-checks"></a>Configuración de cheques con pago diferido
1. Vaya a Gestión de efectivo y bancos > Configurar > Parámetros de gestión de efectivo y bancos.
2. Haga clic en la ficha Cheques con fecha futura.
3. Active o desactive la casilla Habilitar cheques con fecha futura.
4. Active o desactive las entradas del diario de registro para la casilla de cheques con fecha futura.
5. En el campo Cuenta de compensación para cheques emitidos, especifique los valores que le interesen.
6. En el campo Cuenta de compensación para cheques recibidos, especifique los valores que le interesen.
7. En el campo Diario general para entidades de compensación, escriba un valor.
8. En el campo Transferir cheques con fecha futura a este diario de pagos de proveedor, escriba un valor.
9. En el campo Cuenta de compensación de retención de impuestos, especifique los valores que le interesen.
10. Haga clic en Guardar.
11. Cierre la página.
12. Vaya a Proveedores > Configuración de pagos > Formas de pago.
13. Haga clic en Nuevo.
14. En el campo Forma de pago, escriba un valor.
15. Seleccione la opción Registro de compensación de cheques con fecha futura para indicar que el importe del cheque se registra en una cuenta de compensación.
16. En el campo Tipo de cuenta, seleccione Banco.
    * La cuenta de contrapartida del método de pago será un banco.  
17. En el campo Cuenta de pago, especifique los valores deseados.
    * Seleccione la cuenta bancaria que se utiliza para deducir el importe de la factura.  
18. Cierre la página.
19. Vaya a Clientes > Configuración de pagos > Formas de pago.
20. Haga clic en Nuevo.
21. En el campo Forma de pago, escriba un valor.
22. Seleccione la opción Registro de compensación de cheques con fecha futura para indicar que el importe del cheque se registra en una cuenta de compensación.
23. En el campo Tipo de cuenta, seleccione Banco.
    * La cuenta de contrapartida del método de pago será un banco.  
24. En el campo Cuenta de pago, especifique los valores deseados.
    * Seleccione la cuenta bancaria que se utiliza para deducir el importe de la factura.  
25. Cierre la página.


