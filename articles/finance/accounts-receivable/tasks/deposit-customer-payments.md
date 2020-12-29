---
title: Depositar pagos de cliente
description: Pagos de cliente en depósito.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/18/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransCustPaym, CustTableLookup
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1d903f557fbaeb720dd4a34dc1c772be0dcb56eb
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/13/2020
ms.locfileid: "4447598"
---
# <a name="deposit-customer-payments"></a>Depositar pagos de cliente

[!include [banner](../../includes/banner.md)]

Pagos de cliente en depósito. Esta tarea usa la empresa de demostración USMF.

1. Vaya a **Panel de exploración > Módulos > Clientes > Pagos > Diario de pagos**.
2. Seleccione **Nuevo**.
3. En el campo **Nombre**, seleccione **CustPay** en el menú desplegable.
4. Seleccionar **Líneas**.
5. En el campo **Cuenta**, seleccione el cliente para el que esté registrando el pago.
6. En el campo **Crédito**, especifique el importe del pago. Puede elegir dejar el importe en blanco y hacer que el sistema lo calcule seleccionando las facturas pagadas.  
7. En el campo **Referencia del pago**, escriba un valor. La referencia de pago podría ser el número de cheque para el pago que se está introduciendo. La referencia de pago es obligatoria para incluir el pago en un resguardo de depósito.  
8. Marque el cuadro Utilizar un resguardo del depósito. Si el pago debe incluirse en el depósito, cambie este ajuste a Sí.  
9. Seleccione **Nuevo**.
10. En el campo **Cuenta**, seleccione el cliente para el siguiente pago.
11. En el campo **Crédito**, especifique el importe del pago.
12. En el campo **Referencia del pago**, escriba un valor.
13. Marque el cuadro **Utilizar un resguardo del depósito**.
14. Seleccione **Registrar**. Los pagos deben registrarse para poder generar el resguardo de depósito. Esto es así para garantizar que los pagos no cambian después de generarse el resguardo de depósito.  
15. Seleccione **Funciones**.
16. Seleccione **Resguardo de depósito**.
17. Seleccione **Aceptar**. La primera página que se usa para crear el resguardo de depósito.  
18. Seleccione **Aceptar**. El segundo paso es imprimir el resguardo de depósito, si bien este paso no es obligatorio.  

