---
title: "Visión general de extractos bancarios y conciliación de pagos para la UE"
description: "Este tema proporciona una visión general de la funcionalidad que puede usar para conciliar la información de pago de los bancos en los formatos que usan los países europeos."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankAccountTable, CustPaymMode, VendPaymMode
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations, Core
ms.custom: 267994
ms.search.region: Belgium, Norway, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 5e4f3fdce97cf05a8f54873cd8d80364b1505bd3
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017


---

# Visión general de extractos bancarios y conciliación de pagos para la UE
<a id="bank-statement-and-payment-reconciliation-overview-for-the-eu" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Este tema proporciona una visión general de la funcionalidad que puede usar para conciliar la información de pago de los bancos en los formatos que usan los países europeos.

En Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, puede importar transacciones desde los bancos y liquidarlas con relación a transacciones existentes. En Europa, puede hacerlo para los escenarios siguientes:

-   Importar extractos bancarios
-   Importar pagos.
-   Importar archivos de devolución.

## Extractos bancarios
<a id="bank-statements" class="xliff"></a>
Un *Extracto bancario* o *Extracto de cuenta* es un resumen de transacciones financieras que han tenido lugar durante un período determinado en una cuenta bancaria de una empresa en una institución financiera. En Finance and Operations puede importar un extracto bancario. Es importante liquidar las transacciones importadas con relación a transacciones existentes, así como verificar el saldo de apertura y el de cierre de las cuentas bancarias. La siguiente lista incluye los formatos europeos admitidos.

-   Formatos de archivos europeos para la conciliación bancaria avanzada. Para obtener más información, consulte [Visión general de conciliación bancaria avanzada](../cash-bank-management/advanced-bank-reconciliation-overview.md).
-   Formato de archivo del mensaje del extracto bancario camt.053 ISO 20022
-   Formato de archivo de extracto bancario CODA. Para obtener más información, consulte [CODA - Extracto bancario](emea-bel-coda-bank-statement-import.md).

## Mensajes de importación y devolución de pagos de cliente y proveedor
<a id="customer-and-vendor-payments-import-and-return-messages" class="xliff"></a>
Además de un extracto bancario, los bancos pueden proporcionar mensajes específicos, con información sobre los pagos del cliente y el proveedor, que pueden importarse en Finance and Operations y ser conciliados con las transacciones del cliente y proveedor. Cuando una empresa necesita recibir información acerca de transacciones de pagos entrantes del cliente desde el banco, puede usar los formatos de importación. Para empresas que usan transferencias directas de crédito y débito directo, pueden recibirse mensajes de devolución para actualizar el estado de pagos que se hubieran exportado previamente. La diferencia entre los formatos de importación y de devolución es que estas son controladas principalmente para actualizar las líneas de diario de pago ya creadas (pueden crearse al iniciarse una transferencia de crédito o de débito directo) en lugar de crearse líneas nuevas. Algunos formatos de importación complejos también pueden incluir los escenarios de devolución. El siguiente ejemplo muestra cómo debe implementarse esta división.

##### Formatos de importación
<a id="import-formats" class="xliff"></a>

-   Mensaje de notificación del banco camt.054 ISO 20022
-   [Formato de importaciones netas](emea-nor-nets-import-format.md) Funcionalidad compleja para formatos de pago noruegos
-   Importación de pagos de cliente de ESR
-   Importar formatos de pago para Suecia, formatos BankGirot Max y BankGirot OCR

##### Formatos de devolución
<a id="return-formats" class="xliff"></a>

-   Informe de estado de pago pain.002 ISO 20022
-   (DNK) BetalingsserviceBasis-returformat, formato de devolución para el formato de exportación Betalingsservice del cliente
-   [Importar formatos de pago para Suecia](emea-swe-payment-formats-import.md), devoluciones Bankgirot Autogiro
-   (SWE) devolución BankGirot, formato de devolución de pagos de proveedores, que corresponde al formato de exportación de Bankgirot



