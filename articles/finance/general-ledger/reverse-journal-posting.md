---
title: Invertir diario de registro
description: Este tema describe capacidades que le permiten invertir los asientos de la transacción de asiento o lista de los diarios financieros.
author: MikeFalkner
manager: AnnBe
ms.date: 08/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerTransVoucher, LedgerJournalTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5a5456e60f1f3cee5f83ac7f725f7e01ba5bd7a1
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/30/2019
ms.locfileid: "2248594"
---
# <a name="reverse-journal-posting"></a>Invertir diario de registro

[!include [banner](../includes/banner.md)]

Este tema describe las capacidades Microsoft Dynamics 365 Finance que permiten que invierta el diario entero o que invierta uno o varios asientos de la transacción de asiento enumerada independientemente de su origen. 

## <a name="reversing-journals"></a>Invertir los diarios

Puede invertir las líneas de diario de forma individual. Con el registro de invertir diario, también puede invertir un diario financiero completo. Para invertir un diario: 
- Abra el diario y filtre según los diarios registrados
- Haga clic en el menú Invertir en la parte superior de la página
- Verá el número total de asientos y las líneas de asiento junto con el importe total de las líneas que son invertidas
- Seleccione Sí para usar las fechas de transacción actuales o No para introducir una nueva. En algunos casos, el período de la transacción original estar cerrado y puede querer especificar una nueva fecha de transacción para la inversión.
- Si ha seleccionado No, especifique una fecha de transacción para la inversión. 
- Escriba el comentario que desee agregar a la transacción de inversión
- Haga clic en el botón Invertir

Las transacciones se invertirán. 

Si el número de líneas de asiento supera las 100, el proceso de inversión se ejecuta mediante el proceso por lotes. Puede revisar los resultados de la inversión viendo los comentarios en el trabajo por lotes que se ejecutó. Todos los errores se anotarán en el historial del trabajo por lotes.

Si el número de líneas de asiento es 100 o menos, el proceso de inversión se ejecutará inmediatamente. Los resultados se mostrarán en un diálogo que muestra cualquier asiento que no se ha podido invertir y la razón por la que no ha podido invertirse. Haga clic en Aceptar para cerrar el diálogo.

## <a name="reversing-vouchers-from-the-voucher-transaction-list"></a>Invertir los asientos de la lista de la transacción de asiento. 

También puede invertir los asientos de la **Lista de la transacción de asiento** a través de todos los sublibros de contabilidad. Además, puede invertir más de un asiento al mismo tiempo. 

Para invertir uno o varios asientos: 
- Haga clic en el menú Invertir en la parte superior de la página
- Verá el número total de asientos y las líneas de asiento junto con el importe total de las líneas que son invertidas
- Seleccione Sí para usar las fechas de transacción actuales o No para introducir una nueva. En algunos casos, el período de la transacción original estar cerrado y puede querer especificar una nueva fecha de transacción para la inversión.
- Si ha seleccionado No, especifique una fecha de transacción para la inversión. 
- Escriba el comentario que desee agregar a la transacción de inversión
- Haga clic en el botón Invertir

Las transacciones se invertirán. 

Si el número de líneas de asiento supera las 100, el proceso de inversión se ejecuta mediante el proceso por lotes. Puede revisar los resultados de la inversión viendo los comentarios en el trabajo por lotes que se ejecutó. Todos los errores se anotarán en el historial del trabajo por lotes.

Si el número de líneas de asiento es 100 o menos, el proceso de inversión se ejecutará inmediatamente. Los resultados se mostrarán en un diálogo que muestra cualquier asiento que no se ha podido invertir y la razón por la que no ha podido invertirse. Haga clic en Aceptar para cerrar el diálogo.

