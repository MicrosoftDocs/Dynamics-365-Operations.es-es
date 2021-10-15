---
title: Imprimir cheques con diseño español
description: Este tema proporciona información sobre cómo imprimir cheques de acuerdo con las normas que se requieren en España.
author: anasyash
ms.date: 05/31/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankChequeLayout, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.custom: 274753
ms.search.region: Spain
ms.author: anasyash
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: e36a00338384ee7b474fe872e8214f8bfc2481d9
ms.sourcegitcommit: 49f29aaa553eb105ddd5d9b42529f15b8e64007e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2021
ms.locfileid: "7592653"
---
# <a name="print-checks-by-using-the-spanish-layout"></a>Imprimir cheques con diseño español

[!include [banner](../includes/banner.md)]

Este tema proporciona información sobre cómo imprimir cheques de acuerdo con las normas que se requieren en España.

Para utilizar la funcionalidad de cheques junto con diseño español, debe tener en cuenta los siguientes valores:

-   Para aplicar la gramática correcta al importe en letras (texto), debe seleccionar el género correcto para la divisa en la página **Divisas**. Por ejemplo, seleccione **Masculino** para el Euro (EUR) y **Femenino** para la libra esterlina (GBP).
-   Para el método de pago, use el formato de archivo de exportación **Cheque**.
-   Para la cuenta bancaria, use **Diseño de cheques para España** en la sección **Diseño de cheques** de la página **Cuenta bancaria** (**Configuración** &gt; **Diseño** &gt; **Cheque**). Además, establezca el campo **Otras divisas** en **Sí**.

Para generar cheques con diseño español, se utiliza la funcionalidad básica del diario de pagos (proveedores). Para obtener más información, consulte [Resumen de pagos del proveedor](../cash-bank-management/tasks/vendor-payment-overview.md). Después de ejecutar la función de pagos Generar y seleccionar todos los parámetros necesarios como se describe en este tema, se generan los cheques. Si la divisa en la línea de diario de pago es distinta de la cuenta bancaria, puede generar un cheque igualmente, siempre y cuando el diseño del cheque esté configurado para poder usar otras divisas.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
