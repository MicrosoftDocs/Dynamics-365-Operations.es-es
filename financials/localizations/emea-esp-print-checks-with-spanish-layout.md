---
title: "Imprimir cheques con diseño español"
description: "Este tema proporciona información sobre cómo imprimir cheques de acuerdo con las normas que se requieren en España."
author: neserovleo
manager: AnnBe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankChequeLayout, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 274753
ms.search.region: Spain
ms.author: v-lenest
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30T00:00:00.000Z
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: a313d1d7d06d9b5fa97309790091162ad6839648
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---

# <a name="print-checks-by-using-the-spanish-layout"></a>Imprimir cheques con diseño español

Este tema proporciona información sobre cómo imprimir cheques de acuerdo con las normas que se requieren en España.

Para utilizar la funcionalidad de cheques junto con diseño español, debe tener en cuenta los siguientes valores:

-   Para aplicar la gramática correcta al importe en letras (texto), debe seleccionar el género correcto para la divisa en la página **Divisas**. Por ejemplo, seleccione **Masculino** para el Euro (EUR) y **Femenino** para la libra esterlina (GBP).
-   Para el método de pago, use el formato de archivo de exportación **Cheque**.
-   Para la cuenta bancaria, use **Diseño de cheques para España** en la sección **Diseño de cheques** de la página **Cuenta bancaria** (**Configuración** &gt; **Diseño** &gt; **Cheque**). Además, establezca el campo **Otras divisas** en **Sí**.

Para generar cheques con diseño español, se utiliza la funcionalidad básica del diario de pagos (proveedores). Para obtener más información, consulte [Visión general del pago de proveedor (guía de tareas)](/dynamics365/unified-operations/financials/cash-bank-management/tasks/vendor-payment-overview). Después de ejecutar la función de pagos Generar y seleccionar todos los parámetros necesarios como se describe en este tema, se generan los cheques. Si la divisa en la línea de diario de pago es distinta de la cuenta bancaria, puede generar un cheque igualmente, siempre y cuando el diseño del cheque esté configurado para poder usar otras divisas.


