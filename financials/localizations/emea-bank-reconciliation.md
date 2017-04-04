---
title: "Visión general de la conciliación del extracto bancario y pago para la UE"
description: "Este tema proporciona una visión general de funciones que se pueden usar para conciliar la información de pago de los bancos en los formatos que usan los países europeos."
author: ShylaThompson
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BankAccountTable, CustPaymMode, VendPaymMode
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 267994
ms.assetid: 2bfb8ecc-e850-43cb-9a96-deb11716a391
ms.search.region: Belgium, Norway, Sweden, Switzerland
ms.author: v-lenest
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: f707d45290682e79ee439ba0d504852429defa90
ms.openlocfilehash: 22d93d7b3618d4f5931c6a7e39d681173734b0b9
ms.lasthandoff: 03/31/2017


---

# <a name="bank-statement-and-payment-reconciliation-overview-for-the-eu"></a>Visión general de la conciliación del extracto bancario y pago para la UE

Este tema proporciona una visión general de funciones que se pueden usar para conciliar la información de pago de los bancos en los formatos que usan los países europeos.

En Microsoft Dynamics 365 para las operaciones, puede importar transacciones desde los bancos y liquidar estas transacciones contra las transacciones existentes. En Europa, puede hacerlo para los escenarios siguientes:

-   Importar extractos bancarios
-   Importar pagos.
-   Importar archivos de devolución.

## <a name="bank-statements"></a>Extractos bancarios
Un statement* de *bank o el statement* de *account es un resumen de transacciones financieras que han tenido lugar durante un período determinado en una cuenta bancaria mantendrán por una empresa con una institución financiera. En Dynamics 365 para las operaciones puede importar un extracto bancario. Es importante para transacciones importadas liquidar con transacciones existentes así como comprobar la apertura y el saldo de cierre de las cuentas bancarias. La siguiente lista incluye los formatos admitidos europeos.

-   Formatos de archivo avanzados de European de conciliación bancaria. Para obtener más información, consulte [visión general avanzado de conciliación bancaria (.]. /cash-bank-management/advanced-bank-reconciliation-overview.md).
-   Formato de archivo del mensaje del extracto bancario camt.053 de ISO 20022
-   Formato de archivo del extracto bancario de CODA. Para obtener más información, consulte [el extracto bancario de CODA emea-bel-coda-bank-statement-import.md] ().

## <a name="customer-and-vendor-payments-import-and-return-messages"></a>Cliente y pagos de proveedor importación y mensajes de devolución
Además de un extracto bancario, los bancos pueden proporcionar mensajes específicos, con información sobre el cliente y los pagos de proveedor, que pueden importarse en Dynamics 365 para las operaciones y ser conciliados con las transacciones del cliente y proveedor. Cuando una empresa necesita recibir información acerca de transacciones de entrada de los pagos de cliente del banco, los formatos de importación pueden usarse. Para las empresas que usan la transferencia de débito directo y crédito, los mensajes de devolución se pueden recibir para actualizar el estado de pagos que se han exportados previamente. La diferencia entre los formatos de importación y los formatos de devolución es que las devoluciones se mediante principalmente para actualizar las líneas de diario de pago ya creadas (pueden crear cuando la transferencia de débito directo o de crédito ha sido iniciada) en lugar de crear líneas nuevas. Algunos formatos de importación complejos también pueden incluir los escenarios de devolución. El siguiente ejemplo muestra cómo esta división debe ser implementada.

##### <a name="import-formats"></a>Formatos de importación

-   Mensaje de notificación del banco de camt.054 ISO 20022
-   [Formato de importación] de redes emea-nor-nets-import-format.md () - característica compleja para los formatos de pago noruegos
-   Importación de los pagos de cliente ESR
-   Importe los formatos de pago para Suecia - los formatos de Máx. de BankGirot y de OCR BankGirot

##### <a name="return-formats"></a>Devuelva los formatos

-   Informe de estado de pago de pain.002 ISO 20022
-   (DNK) BetalingsserviceBasis-returformat – formato de devolución para el formato de exportación de Betalingsservice del cliente
-   [Formatos de pago de importación para Suecia emea-swe-payment-formats-import.md] () - Bankgirot Autogiro vuelve
-   (SWE) devolución de BankGirot – formato de devolución de los pagos de proveedores, que corresponda al formato de exportación de Bankgirot

