---
title: Creación y exportación de pagos de proveedor mediante el formato de pago de ISO20022
description: Este procedimiento muestra cómo crear líneas de pago en el diario de pago de proveedor y generar un archivo de pago de proveedor utilizando el ejemplo ISO2022 Transferencia de crédito.
author: mrolecki
ms.date: 01/17/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendPaym, SysQueryForm, VendPaymProposalEdit, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: ac84055586eff678ea489b35198b1c2dfab13658
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856478"
---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a>Creación y exportación de pagos de proveedor mediante el formato de pago de ISO20022

[!include [banner](../../includes/banner.md)]

Este artículo muestra cómo crear líneas de pago en el diario de pago de proveedor y generar un archivo de pago de proveedor utilizando el ejemplo ISO2022 Transferencia de crédito.

Este es el quinto procedimiento, de cinco, que muestra el proceso de pago del proveedor mediante las configuraciones de informes electrónicos. Use los datos de demostración de DEMF para completar este ejemplo.

## <a name="example"></a>Ejemplo

1.    Vaya a **Proveedores > Pagos > Diario de pagos**.
2.    Haga clic en **Nuevo**.
3.    En el campo **Nombre**, especifique o seleccione un valor.
4.    Haga clic en **Líneas > Propuesta de pago > Crear propuesta de pago**.
5.    Expanda la sección **Registros que incluir**.
6.    Haga clic en **Filtro.**
7.    En la lista, seleccione la fila para la **tabla Proveedores** y el **campo Cuenta de proveedor**.
8.    En el campo **Criterios**, especifique o seleccione un valor. Puede aplicar cualquier criterio para seleccionar transacciones de proveedor para pagar, por ejemplo, use DE-001 como cuenta de proveedor.
12.    Haga clic en **Aceptar**.
13.    Haga clic en **Aceptar**.
14.    Haga clic en **Crear pagos**.
15. Generación de un archivo de pago ISO20022.
    1.    Haga clic en **Generar pagos**.
    2.    En el campo **Método de pago**, especifique o seleccione un valor.
    3.    En el campo **Nombre de archivo**, escriba un valor. Para este ejemplo, debido al pago de euros, el archivo generado cumplirá con la SEPA. La transferencia de crédito ISO20022 así como los formatos de pago de otro proveedor también se pueden utilizar para generar pagos en otras divisas.
    4.    En el campo **Cuenta bancaria**, especifique o seleccione un valor.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]