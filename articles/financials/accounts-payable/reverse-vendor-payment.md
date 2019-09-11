---
title: Inversión de un pago de proveedor
description: Este artículo describe las diferencias entre la inversión, la eliminación, la anulación y el rechazo de un pago. Además, explica los dos métodos para invertir una comprobación de proveedor.
author: abruer
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankChequeTable, LedgerJournalTransBankChequeReversal, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14361
ms.assetid: 9f0a1883-cbe0-4cc7-b9f3-dd12fb85ebe8
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: db9208c8e76d963d5b8f6bee6b7c73268af68734
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/08/2019
ms.locfileid: "1867759"
---
# <a name="reverse-a-vendor-payment"></a>Inversión de un pago de proveedor

[!include [banner](../includes/banner.md)]

Este artículo describe las diferencias entre la inversión, la eliminación, la anulación y el rechazo de un pago. Además, explica los dos métodos para invertir una comprobación de proveedor. 

En ocasiones, después de que se haya registrado un pago de proveedor, el pago debe invertir. La inversión es diferente de la eliminación, la anulación o el rechazo de un pago. Es posible eliminar un pago solo si su estado es **Creado**. Este estado indica que se ha creado el pago, pero aún no se ha generado. Esta limitación se aplica siempre, independientemente del método de pago. Puede anular los cheques no registrados después de que se han generado, pero antes de registrarlos. Si el pago generado se realiza como transferencia electrónica de fondos (EFT), puede rechazar el pago antes de registrarlo. Para rechazar un pago, cambie el valor **Estado de pago**. Un pago que se ha anulado o se ha rechazado, se puede regenerar después de volver a cambiar el valor de **Estado de pago** a **Ninguno**. 

Una vez registrado un pago, se usan las inversiones. Los pagos que se realizan electrónicamente no pueden invertirse después de que se hayan registrado. En su lugar, debe crearse una nueva transacción por el importe de pago para devolver el pasivo a la cuenta del proveedor. Existen dos métodos para invertir los cheques registrados. En un método, las inversiones se registran inmediatamente al hacer clic en **Inversión del pago** en la página **Cheque**. En el otro método, al hacer clic en el botón **Inversión del pago** de la página **Cheque**, la inversión se envía primero al diario de inversión de cheques en Gestión de efectivo y bancos, donde un revisor podrá registrarla o rechazarla. 

Para saber qué método usa la organización, vea la página **Parámetros de gestión de efectivo y bancos**. Si la opción **Usar proceso de revisión para inversiones de pago** está establecida en **Sí**, las inversiones se envían al diario de inversiones de cheques para su revisión. La tabla siguiente se describe cómo difieren los métodos de inversión de cheques.

| Si su organización no revisa la inversiones de cheques antes del registro                                                                                                                                  | Si su organización revisa las inversiones de cheques antes del registro                                                                                                                                                                                                                                                                                                                                                                     |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| El cheque se invierte inmediatamente al hacer clic en **Aceptar** en la página **Cheque**.                                                                                                                      | El cheque no se invierte inmediatamente. Un diario de inversión de cheques se crea para su revisión. Si se elimina el diario de inversión de cheques, el cheque se puede invertir de nuevo.                                                                                                                                                                                                                                                                |
| Los asientos contables del cheque original se invierten.                                                                                                                                         | La cuenta contable del asiento contable del cheque original podría no estar registrada. Las dimensiones financieras del diario del cheque original se usan como dimensiones financieras predeterminadas en el diario de inversión de cheques. Es posible cambiar estos valores predeterminados. Cuando se registra el diario de inversiones de cheques, las cuentas principales para proveedores se especifican automáticamente desde los perfiles de contabilización, lo que puede haber cambiado. |
| Las estructuras contables que se usaron cuando el cheque original se registró se usan para invertir el cheque, incluso si se ha cambiado la estructura contable. La combinación de cuenta no está validada. | Si una estructura contable se modificó después de registrar el cheque original, puede que una nueva dimensión financiera se requiera para la inversión del cheque. Esta dimensión financiera no se puede especificar automáticamente desde el diario de pago original. La combinación de cuenta se valida cuando se registra la inversión de cheques.                                                                                                        |
| Las dimensiones fijas no se aplican a la inversión para ayudar a garantizar que las mismas cuentas contables se invertirán.                                                                                      | Las dimensiones fijas se aplican al diario de inversiones de cheques durante el registro. El valor de la dimensión financiera puede que no exista en el asiento contable del cheque original, en función de si la dimensión fija se ha definido.                                                                                                                                                                                                     |

## <a name="reverse-posted-checks-without-reviewing-them"></a>Invertir cheques registrados sin revisarlos
Si su organización desea registrar las inversiones de cheques inmediatamente al hacer clic en **Inversión del pago** en la página **Cheques**. En la página **Parámetros de gestión de efectivo y bancos** establezca la opción **Usar proceso de revisión para inversiones de pago** en **No**. En la página **Cheques**, puede seleccionar el cheque para invertir y seleccionar **Inversión del pago**. Después puede indicar la fecha y seleccionar un motivo para la inversión.

## <a name="reverse-posted-checks-after-they-are-reviewed-in-the-check-reversal-journal"></a>Invertir los cheques registrados después de revisarlos en el diario de inversiones de cheques
Si su organización desea revisar las inversiones de cheques antes de registrarlas, cree un diario de inversiones de cheques para su revisión y, en la página **Parámetros de gestión de efectivo y bancos**, establezca la opción **Usar proceso de revisión para inversiones de pago** en **Sí**. En la página **Cheques**, puede seleccionar el cheque para invertir y seleccionar **Inversión del pago**. Después puede indicar la fecha y seleccionar un motivo para la inversión. El motivo financiero se debe configurar para los tipos Banco y Proveedor. También debe seleccionar un nombre de diario para crear un diario en el diario de inversión de cheques.

### <a name="review-a-reversal"></a>Revisar una inversión

Si es un usuario que debe revisar inversiones, puede aprobar y registrar el diario, o rechazar la inversión si elimina el diario. En la página **Diario de inversiones de cheques**, puede seleccionar el diario de inversión para revisarlo y, después, hacer clic en **Líneas**. Puede revisar el cheque invertido y, a continuación, seleccionar una de las opciones de aprobación siguientes:

-   Para aprobar y registrar el diario de inversión, haga clic en **Registrar** o en **Registrar y transferir**.
-   Para rechazar la inversión, elimine el diario de cheques de inversión.

> [!NOTE]
> Si elimina el diario, se quita la inversión del sistema, pero el cheque original permanece en la página **Cheque**. El estado del cheque dejará de ser **Cancelación pendiente**.

## <a name="results-of-posting-a-reversal"></a>Resultados del registro de una inversión
Al registrar la inversión de un cheque, ocurren los eventos siguientes:

-   El estado del cheque se actualiza a **Cancelación**.
-   Si la opción **Conciliar** está activada en la página de inversión durante la inversión, el cheque se conciliará (la opción **Conciliado** está seleccionada) y no aparece en la página **Conciliación de cuentas**.
-   El asiento de inversión se registra en la cuenta bancaria para la que se había emitido el cheque, para aumentar el saldo de la cuenta bancaria.
-   El asiento se registra en Contabilidad general.
-   Los detalles de la modificación se actualizan en el grupo de campos **Historial** de la página **Cheque**.

> [!NOTE] 
> Al invertir un cheque emitido para una transacción comercial de empresas vinculadas, las entradas de compensación proceden de la configuración de la contabilidad del comercio entre empresas vinculadas, no de la transacción original. Si el cheque invertido se ha emitido para un pago de proveedor, también ocurrirán los eventos siguientes:

-   No se aplicará el pago original de la factura para la que se había liquidado el cheque (se invierte la liquidación).
-   Se registrará una transacción contra la cuenta de proveedor para la inversión del pago y el pago invertido se liquidará contra el pago original. El campo **Último asiento de liquidación** de la página **Transacciones de proveedor** del pago original del proveedor se actualizará para reflejar el número de asiento de la transacción invertida.

Si el cheque invertido se había emitido para una devolución de cliente, también ocurrirán los eventos siguientes:

-   Se registrará una transacción contra la cuenta de cliente para la inversión de pago, y la liquidación entre el pago original y el documento contra el que se había liquidado el pago originalmente se invertirá (se crea un pago negativo).
-   Se aplica una inversión de pago al pago original. El campo **Último asiento de liquidación** de la página **Transacciones de cliente** del pago original del proveedor se actualizará para reflejar el número de asiento de la transacción invertida.




