---
title: Condonar, restablecer o revertir cuotas de interés
description: Este artículo explica cómo condonar, restablecer e invertir los gastos para el interés y las cuotas.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustInterestJourList
audience: Application User
ms.reviewer: roschlom
ms.custom: 59461
ms.assetid: 25ec29f3-e3ea-4abb-bf6b-f6240873b315
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 080b46e69d9959f7a10a291552603f80071a934a
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "5003240"
---
# <a name="waive-reinstate-or-reverse-interest-fees"></a>Condonar, restablecer o revertir cuotas de interés

[!include [banner](../includes/banner.md)]

Este artículo explica cómo condonar, restablecer e invertir los gastos para el interés y las cuotas.

Puede usar los botones de la ficha **Recopilar** que se encuentra en lapágina **Todos los clientes** para condonar, invertir o restablecer cargos:

-   No se cobran los cargos condonados. Es posible que desee condonar un cargo si, por ejemplo, un cliente reclama el cargo y usted desea mantener una buena relación empresarial con ese cliente.
-   Los cargos restablecidos vuelven a ser exigibles. Puede restablecer cargos que hayan sido condonados anteriormente. Es posible que tenga que restablecer cargos si se determina que no deberían haber sido condonados.
-   Los cargos invertidos se eliminan de la cuenta de un cliente y dejan de ser exigibles. Puede revertir cargos si, por ejemplo, no se ha seleccionado el tipo de interés correcto para calcular el importe que debe pagar un cliente. Puede usar un proceso independiente para volver a calcular el interés y crear una nota de interés que contenga nuevos cargos para el cliente.

Todas estas acciones modifican una nota de interés. Una nota de interés es un documento empresarial que avisa al cliente cuando se cargan intereses o cuotas en su cuenta. Cuando se condona o se invierte un interés o cuota, se crea una nota de interés o una factura de ajuste para liquidar los cargos. Si restablece cargos condonados, se crea automáticamente una factura que tiene un importe de débito para restablecer los cargos que debe el cliente. En la siguiente tabla se describen los resultados de cada acción.

| Acción                                                                                                                                                                                                            | Resultado para el cliente                                                                                             | Procesar                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Condonar todas las notas de interés juntas con todos los intereses y cuotas que incluyen. o Seleccionar y condonar transacciones de interés o cuotas que forman parte de notas de interés.                                        | No se cobran los cargos.                                                                                           | Se crea una nota de interés, una nota de abono o una factura de ajuste. El crédito no se emplea para liquidar automáticamente la nota de interés, o las transacciones de interés o cuotas que haya seleccionado. El importe liquidado es igual a la cantidad total de los cargos, menos los pagos anteriores realizados por el cliente, y menos cualquier importe aplicado anteriormente o cancelados. Si el importe de la nota de crédito supera el importe que le debe el cliente, puede convertir la nota de crédito en una factura de proveedor. Puede proporcionar una devolución al cliente.                                                       |
| Restablecer todas las notas de interés junto con todos los intereses y cuotas que incluyen. o Seleccionar y restablecer transacciones de interés o cuotas que forman parte de notas de interés.                                | El importe condonado vuelve a ser exigible.                                                                                     | Se crea una factura que tiene un importe de débito, y el importe se liquida automáticamente con los cargos que no se aplicaron anteriormente. Las notas de interés real no se restablecen. En lugar de eso, se crea una factura en la que se muestra el importe que debe el cliente. Las notas de crédito, o facturas de ajusta, que se crearon para liquidar las notas de interés condonadas pueden seguir existiendo si no se usaron para liquidar las notas de interés. En este caso, se cancelan las notas de crédito pendientes. Las notas de crédito pendientes suelen liquidarse de forma automática al condonar notas de interés. No obstante, puede existir una nota de crédito pendiente si un cliente pagó una nota de interés incluso aunque éste reclamase los cargos. |
| Invertir todas notas de interés. o Invertir las transacciones de interés seleccionadas que forman parte de notas de interés. **Nota:** No se puede invertir una factura. Sin embargo, puede invertir una nota de interés completa que incluya una cuota. | Los cargos dejan de ser exigibles para el cliente. No obstante, los cargos vuelven a ser exigibles si se recalcula el interés. | El proceso es el mismo que el proceso para condonar notas de interés o transacciones de interés seleccionadas. Se crea una nota de interés, una nota de abono o una factura de ajuste. Esta nota de crédito se usa para liquidar automáticamente la nota de interés. Puede usar un proceso independiente para volver a calcular el interés y crear una nueva nota de interés.                                                                                                                                                                                                                                                                                                                                                                                              |

> [!NOTE] 
> Puede usar un proceso independiente para cancelar deudas incorrectas. Este proceso marca todas las transacciones del cliente para liquidación en lugar de condonar únicamente los cargos que son parte de las notas de interés.

## <a name="adjust-interest-for-invoices"></a>Ajustar el interés para facturas
Además de ajustar las notas de interés, puede eliminar los cargos del interés de facturas mediante uno de los siguientes procesos. Ambos procesos también realizan ajustes en las notas de interés relacionadas.

### <a name="correct-an-invoice-that-has-associated-interest"></a>Corregir una factura que tiene interés asociado

Puede corregir una factura registrada que haya sido incluida en una nota de interés. Este proceso copia los detalles de la factura existente en una nueva factura para realizar únicamente las correcciones que desee. Se cancela la factura y se crea una nueva factura. También se invierte el interés de la transacción en la nota de interés, si se registró la nota de interés. 

Puede realizar la corrección mediante el botón **Corregir factura** del Panel de acciones de la factura de servicios. Este botón solo está disponible si se selecciona la clave de configuración **Corrección de factura de servicios**.

### <a name="reverse-a-customer-transaction-that-has-associated-interest"></a>Invertir una transacción del cliente que tiene interés asociado

Puede invertir una transacción del cliente en una factura si se crea una factura de forma incorrecta. Si la transacción del cliente invertida tiene un interés que está incluido en una nota de interés y, si ésta ha sido registrada, también se invierte el interés de la transacción en la nota de interés. Si no ha sido registrada, se cancela la nota de interés. 

Puede invertir las transacciones de cliente mediante el botón **Invertir** en la página **Transacciones de cliente**.

## <a name="waive-or-reinstate-interest-notes"></a>Condonar o restablecer notas de interés
Puede condonar o restablecer todos los cargos de las notas de interés que seleccione. Al condonar cargos, el importe total que se va a condonar no puede superar los límites de importe que se han establecido. Sólo puede restablecer notas de interés si han sido condonadas anteriormente. 

Puede condonar o restablecer notas de interés mediante el botón **Nota de interés** en el separador **Recopilar** de la página **Cliente**.

## <a name="waive-or-reinstate-interest-transactions"></a>Condonar o restablecer transacciones de interés
Puede condonar o restablecer transacciones de interés específicas de una nota de interés en lugar de ajustar todos los cargos de esa nota de interés. Al condonar cargos, el importe total que se va a condonar no puede superar los límites de importe que se han establecido. Sólo puede restablecer transacciones de interés si han sido condonadas anteriormente. 

Puede condonar o restablecer notas de interés mediante el botón **Interés de transacción** en el separador **Recopilar** de la página **Cliente**.

## <a name="waive-or-reinstate-fees"></a>Condonar o restablecer notas cuotas
Puede condonar o restablecer cuotas específicas de una nota de interés en lugar de ajustar todos los cargos de esa nota de interés. Al condonar cargos, el importe total que se va a condonar no puede superar los límites de importe que se han establecido. Sólo puede restablecer cuotas si han sido condonadas anteriormente. 

Puede condonar o restablecer notas de interés mediante el botón **Cuota** en el separador **Recopilar** de la página **Cliente**.

## <a name="reverse-interest-notes"></a>Invertir notas de interés
Puede invertir todos los cargos de las notas del interés que seleccione. Los cargos invertidos se eliminan de la cuenta de un cliente y dejan de ser exigibles. Una vez que se haya invertido una nota de interés, puede volver a calcular el interés y crear una nueva nota de interés. 

Puede invertir notas de interés mediante el botón **Nota de interés** en el separador **Recopilar** de la página **Cliente**.

## <a name="reverse-interest-transactions"></a>Revertir transacciones de interés
Puede invertir todas las transacciones de interés que seleccione. Los cargos invertidos se eliminan de la cuenta de un cliente y dejan de ser exigibles. Una vez que se haya invertido las transacciones, puede volver a calcular el interés y crear una nueva nota de interés.

Puede invertir transacciones de interés mediante el botón **Interés de transacciones** en el separador **Recopilar** de la página **Cliente**.

## <a name="view-the-history-of-adjustments-for-charges-that-were-waived-reinstated-or-reversed"></a>Ver la historial de ajustes para obtener información acerca de los gastos que han sido condonados, restablecidos o invertidos
Puede ver el historial detallado de ajustes que se han realizado para notas de interés, como el usuario que ha especificado el ajuste, el tipo de ajuste, el importe y la fecha del ajuste. Por ejemplo, es posible que desee ver los ajustes anteriores que se especificaron para una nota de interés antes de crear una nueva. 

Puede invertir transacciones de interés mediante el botón **Historia** en el separador **Recopilar** de la página **Cliente**.



