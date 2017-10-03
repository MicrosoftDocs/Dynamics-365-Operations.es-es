--- 
title: Depositar pagos de cliente
description: "Pagos de cliente en depósito."
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
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: a2e5509ec4f763b8fd195f95257bdb085286920b
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="deposit-customer-payments"></a>Depositar pagos de cliente

[!include[task guide banner](../../includes/task-guide-banner.md)]

Pagos de cliente en depósito. Esta tarea usa la empresa de demostración USMF.

1. Vaya a Clientes > Pagos > Diario de pagos.
2. Haga clic en Nuevo.
3. En el campo Nombre, haga clic en el botón desplegable para abrir la búsqueda.
4. Seleccione el diario de pago. 
5. Haga clic en Líneas.
6. En el campo Cuenta, seleccione el cliente para el que esté registrando el pago.
7. En el campo Crédito, especifique el importe del pago.
    * Puede elegir dejar el importe en blanco y hacer que el sistema lo calcule seleccionando las facturas pagadas.  
8. En el campo Referencia del pago, escriba un valor.
    * La referencia de pago podría ser el número de cheque para el pago que se está introduciendo. La referencia de pago es obligatoria para incluir el pago en un resguardo de depósito.  
9. Marque el cuadro Utilizar un resguardo del depósito.
    * Si el pago debe incluirse en el depósito, cambie este ajuste a Sí.  
10. Haga clic en Nuevo.
11. En el campo Cuenta, seleccione el cliente para el siguiente pago.
12. En el campo Crédito, especifique el importe del pago.
13. En el campo Referencia del pago, escriba un valor.
14. Marque el cuadro Utilizar un resguardo del depósito.
15. Haga clic en Registrar.
    * Los pagos deben registrarse para poder generar el resguardo de depósito. Esto es así para garantizar que los pagos no cambian después de generarse el resguardo de depósito.  
16. Haga clic en Funciones.
17. Haga clic en Resguardo de depósito.
18. Haga clic en Aceptar
    * La primera página que se usa para crear el resguardo de depósito.  
19. Haga clic en Aceptar
    * El segundo paso es imprimir el resguardo de depósito, si bien este paso no es obligatorio.  


