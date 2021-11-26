---
title: Invertir diario de registro
description: Este tema describe capacidades que le permiten invertir los asientos de la transacción de asiento o lista de los diarios financieros.
author: kweekley
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: roschloma
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fb1615312e9fd1786a5a0050dda3e9e9b20fe710
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/05/2021
ms.locfileid: "7753787"
---
# <a name="reverse-journal-posting"></a>Invertir diario de registro

[!include [banner](../includes/banner.md)]

Este tema describe las capacidades de Microsoft Dynamics 365 Finance que permiten que invierta el diario entero o que invierta uno o varios asientos de la transacción de asiento enumerada independientemente de su origen. 

Antes de poder usar una de las funciones que se describen en este tema, debe activarlas en su sistema. Los administradores pueden usar el espacio de trabajo **Administración de características** para verificar el estado de la característica y activarla si es necesario. Allí, la característica se enumera de la siguiente manera:
 - Módulo: Contabilidad general
 - Nombre de la función: **Reversiones masivas para varios documentos**

## <a name="reversing-journals"></a>Invertir los diarios

Puede invertir las líneas de diario de forma individual. Con el registro de invertir diario, también puede invertir un diario financiero completo. Para invertir un diario: 

- Filtre las revistas publicadas y abra la vista **Líneas** en la revista.
- Haga clic en el menú **Invertir** en la parte superior de la página.
- Verá el número total de asientos y las líneas de asiento junto con el importe total de las líneas que son invertidas.
- Seleccione **Sí** para usar las fechas de transacción actuales o **No** para introducir una nueva. En algunos casos, el período de la transacción original puede estar cerrado y usted tiene que especificar una nueva fecha de transacción para la inversión.
- Si selecciona **No**, especifique una fecha de transacción para la inversión. 
- Escriba un comentario que desee agregar a la transacción de inversión.
- Seleccione el botón **Invertir**.

Las transacciones se invertirán. 

Si el asiento supera las 100 líneas, el proceso de inversión se ejecuta mediante el proceso por lotes. Puede revisar los resultados viendo los comentarios en el trabajo por lotes. Las transacciones que no se hayan podido invertir serán enumeradas en el historial de trabajos por lotes.

Si el asiento es de 100 o menos líneas, el proceso de inversión se ejecutará inmediatamente. Los resultados se mostrarán en un cuadro diálogo que muestra cualquier asiento que no se ha podido invertir y la razón por la que no ha podido invertirse. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a>Invertir los asientos de la lista de la transacción de asiento. 

También puede invertir los asientos de la **Lista de la transacción de asiento** a través de todos los sublibros de contabilidad. Además, puede invertir más de un asiento al mismo tiempo. 

Para invertir uno o varios asientos: 

- Seleccione el menú desplegable **Invertir el diario completo** en la parte superior de la página.
- Se muestra el número total de asientos y las líneas de asiento junto con el importe total de las líneas que son invertidas.
- Seleccione **Sí** para usar las fechas de transacción actuales o **No** para introducir una nueva. En algunos casos, el período de la transacción original puede estar cerrado y usted tiene que especificar una nueva fecha de transacción para la inversión.
- Si selecciona **No**, especifique una fecha de transacción para la inversión. 
- Escriba un comentario para describir la transacción de inversión.
- Seleccione el botón **Invertir**.

Las transacciones se invertirán. 

Si el asiento supera las 100 líneas, el proceso de inversión se ejecuta mediante el proceso por lotes. Puede revisar los resultados viendo los comentarios en el trabajo por lotes. Las transacciones que no se hayan podido invertir serán comentadas en el historial de trabajos por lotes.

Si el número de líneas de asiento es 100 o menos, el proceso de inversión se ejecutará inmediatamente. Los resultados se mostrarán en un cuadro diálogo que muestra cualquier asiento que no se ha podido invertir y la razón por la que no ha podido invertirse. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

Las transacciones se pueden invertir solo si satisfacen las reglas empresariales para invertirlas. Los pagos de proveedor no se pueden invertir con la capacidad anteriormente descrita en este tema. Los pagos de proveedor deben invertirse de acuerdo con los pasos que se describen en [Inversión de un pago de proveedor](../accounts-payable/reverse-vendor-payment.md).



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
