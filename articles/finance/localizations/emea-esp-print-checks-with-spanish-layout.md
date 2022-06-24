---
title: Imprimir cheques con diseño español
description: Este artículo proporciona información sobre cómo imprimir cheques de acuerdo con las normas que se requieren en España.
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
ms.openlocfilehash: 004982c0777ebd90f9aae8ccc751fae1319e4506
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8870009"
---
# <a name="print-checks-by-using-the-spanish-layout"></a>Imprimir cheques con diseño español

[!include [banner](../includes/banner.md)]

Este artículo proporciona información sobre cómo imprimir cheques de acuerdo con las normas que se requieren en España.

Para utilizar la funcionalidad de cheques junto con diseño español, debe tener en cuenta los siguientes valores:

-   Para aplicar la gramática correcta al importe en letras (texto), debe seleccionar el género correcto para la divisa en la página **Divisas**. Por ejemplo, seleccione **Masculino** para el Euro (EUR) y **Femenino** para la libra esterlina (GBP).
-   Para el método de pago, use el formato de archivo de exportación **Cheque**.
-   Para la cuenta bancaria, use **Diseño de cheques para España** en la sección **Diseño de cheques** de la página **Cuenta bancaria** (**Configuración** &gt; **Diseño** &gt; **Cheque**). Además, establezca el campo **Otras divisas** en **Sí**.

Para generar cheques con diseño español, se utiliza la funcionalidad básica del diario de pagos (proveedores). Para obtener más información, consulte [Resumen de pagos del proveedor](../cash-bank-management/tasks/vendor-payment-overview.md). Después de ejecutar la función de pagos Generar y seleccionar todos los parámetros necesarios como se describe en este artículo, se generan los cheques. Si la divisa en la línea de diario de pago es distinta de la cuenta bancaria, puede generar un cheque igualmente, siempre y cuando el diseño del cheque esté configurado para poder usar otras divisas.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]
