---
title: Información general de pagos de cliente
description: Este procedimiento le muestra los distintos métodos para introducir pagos de cliente.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, CustPaymEntry, CustTableLookup, LedgerJournalTransCustPaym, CustOpenTrans, BankAccountTableLookUp
audience: Application User
ms.reviewer: twheeloc
ms.custom: intro-internal
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7b90b7f200133cfb0d30b335aca20c328856fba5
ms.sourcegitcommit: 9c4638c4bb5b5f8adc7508542a0a2c3e1de5190c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2022
ms.locfileid: "9778132"
---
# <a name="customer-payment-overview"></a>Información general de pagos de cliente

[!include [banner](../../includes/banner.md)]

Este procedimiento le muestra los distintos métodos para introducir pagos de cliente. Esta tarea usa la empresa de demostración USMF.

1. Vaya a **Panel de exploración > Módulos > Clientes > Pagos > Diario de pagos**.
2. Haga clic en **Nuevo**.
3. Seleccione el diario de pagos donde se van a guardar los pagos de cliente.
4. Seleccione el diario o especifíquelo manualmente.
5. En el **panel de acciones**, haga clic en **Introducir pagos de cliente**. Introducir pagos de cliente se usa para registrar un pago de cliente cada vez. Se especifica la información de pago en la parte superior y, a continuación, se pueden marcar las facturas pagadas con el pago, todo desde la misma página.  
6. Especifique el cliente de quien recibió el pago. Si no conoce al cliente pero sabe que se pagó una transacción, puede usar el campo **Transacción** para especificar el pago. Especifique o seleccione la factura en el campo **Transacción**. De forma predeterminada, el cliente se incluirá automáticamente al seleccionar la transacción.
7. En el campo **Referencia del pago**, especifique una referencia para el pago. La referencia de pago podría ser el número de cheque del cliente o una referencia del pago electrónico del cliente. La referencia de pago solo es obligatoria si se especifica incluir el pago en un resguardo de depósito.  
8. En el campo **Resguardo de depósito**, seleccione si el pago se incluirá en un resguardo de depósito. 
9. En el campo **Importe**, especifique el importe del pago al cliente. El importe de pago no se especificará en un valor predeterminado. Se debe especificar manualmente. 
10. Marque las facturas pagadas por el cliente. Si el pago es un anticipo, no es necesario marcar ninguna factura para su liquidación. El pago se puede guardar y registrar. La liquidación de una factura puede producirse en otro momento.
11. Especifique el importe del pago que se liquidará en la factura marcada. Este campo se puede usar cuando el pago corresponde a un pago parcial. Si no especifica un importe, el importe que liquidar se determina automáticamente.
12. Haga clic en **Guardar en diario**. Antes de guardar el pago en el diario, asegúrese de que se haya definido la cuenta de contrapartida. **Guardar en diario** guardará el pago y lo pasará al diario. A continuación, podrá continuar especificando el siguiente pago.
13. Cierre la página.
14. En **Panel de acciones**, haga clic en **Líneas**. Al abrir **Líneas** verá los pagos registrados en la página **Introducir pagos de cliente** y también almacenados en el diario. También puede usar esta página para introducir nuevos pagos de clientes o editar pagos de clientes existentes antes de registrarlos.
15. Haga clic en **Nuevo** para crear otro pago. 
16. Seleccione el cliente de quien recibió el pago. Si no sabe quién es el cliente pero sabe qué factura desembolsa el pago, use el campo **Factura** para especificar o seleccionar manualmente la factura. El cliente se incluirá de forma predeterminada una vez se seleccione la factura.  
17. Haga clic en **Liquidar transacciones** para marcar las facturas pagadas. No es necesario liquidar el pago en ninguna factura. Si es un anticipo o si no sabe qué factura se ha pagado, puede introducir y registrar el pago. El pago se podrá liquidar en una factura más adelante.  
18. Marque las facturas desembolsadas en el pago. 
19. En el campo **Importe**, especifique el importe del pago que se liquidará en la factura.
20. Haga clic en **Aceptar**.
21. En el campo **Referencia del pago**, especifique una referencia para el pago. La referencia de pago solo es obligatoria si se especifica incluir el pago en un resguardo de depósito.  
22. En el **panel de acciones**, haga clic en **Registrar** para registrar los pagos del cliente. 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
