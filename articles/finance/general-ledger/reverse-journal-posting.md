---
title: Invertir diario de registro
description: Este tema describe capacidades que le permiten invertir los asientos de la transacción de asiento o lista de los diarios financieros.
author: MikeFalkner
manager: AnnBe
ms.date: 10/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c5d1c58463c24dc6a40b036f0bb803316bbb65c2
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2020
ms.locfileid: "3091908"
---
# <a name="reverse-journal-posting"></a>Invertir diario de registro

[!include [banner](../includes/banner.md)]

Este tema describe las capacidades de Microsoft Dynamics 365 Finance que permiten que invierta el diario entero o que invierta uno o varios asientos de la transacción de asiento enumerada independientemente de su origen. 

## <a name="reversing-journals"></a>Invertir los diarios

Puede invertir las líneas de diario de forma individual. Con el registro de invertir diario, también puede invertir un diario financiero completo. Para invertir un diario: 

- Abra el diario y filtre según los diarios registrados.
- Haga clic en el menú **Invertir** en la parte superior de la página.
- Verá el número total de asientos y las líneas de asiento junto con el importe total de las líneas que son invertidas
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

- Haga clic en el menú **Invertir** en la parte superior de la página.
- Verá el número total de asientos y las líneas de asiento junto con el importe total de las líneas que son invertidas.
- Seleccione **Sí** para usar las fechas de transacción actuales o **No** para introducir una nueva. En algunos casos, el período de la transacción original puede estar cerrado y usted tiene que especificar una nueva fecha de transacción para la inversión.
- Si selecciona **No**, especifique una fecha de transacción para la inversión. 
- Escriba un comentario para describir la transacción de inversión.
- Seleccione el botón **Invertir**.

Las transacciones se invertirán. 

Si el asiento supera las 100 líneas, el proceso de inversión se ejecuta mediante el proceso por lotes. Puede revisar los resultados viendo los comentarios en el trabajo por lotes. Las transacciones que no se hayan podido invertir serán comentadas en el historial de trabajos por lotes.

Si el número de líneas de asiento es 100 o menos, el proceso de inversión se ejecutará inmediatamente. Los resultados se mostrarán en un cuadro diálogo que muestra cualquier asiento que no se ha podido invertir y la razón por la que no ha podido invertirse. Haga clic en **Aceptar** para cerrar el cuadro de diálogo.

Las transacciones se pueden invertir solo si satisfacen las reglas empresariales para invertirlas. Los pagos de proveedor no se pueden invertir con la capacidad anteriormente descrita en este tema. Los pagos de proveedor deben invertirse de acuerdo con los pasos que se describen en [Inversión de un pago de proveedor](https://docs.microsoft.com/dynamics365/finance/accounts-payable/reverse-vendor-payment).

