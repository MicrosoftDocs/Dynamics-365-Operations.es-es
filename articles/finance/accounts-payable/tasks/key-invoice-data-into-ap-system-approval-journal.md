---
title: Introducir datos de factura en el sistema de proveedores mediante un diario de aprobación
description: En este tema se explica cómo usar el registro de facturas para crear facturas y, después, utilizar el diario de aprobación para actualizar las cuentas de gastos.
author: abruer
ms.date: 08/08/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransInvoiceRegister, HcmWorkerLookUp, LedgerJournalTransApprove, LedgerJournalTransApproveFetchVouchers, LedgerTransVoucher
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 72b2d7a5a554f46813fb31991ffb3df30742d01bf168b4180a1096970f60998f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6722944"
---
# <a name="key-invoice-data-into-accounts-payable-using-an-approval-journal"></a>Introducir datos de factura en el sistema de proveedores mediante un diario de aprobación

[!include [banner](../../includes/banner.md)]

En este tema se explica cómo usar el registro de facturas para crear facturas y, después, utilizar el diario de aprobación para actualizar las cuentas de gastos.

## <a name="create-and-post-and-invoice"></a>Crear y registrar una factura
1. En el panel de exploración, vaya a **Módulos > Proveedores > Facturas > Registro de facturas**.
2. Seleccione **Nuevo**.
3. Seleccione el nombre del registro de facturas que desee usar.
4. Seleccione **Líneas** para abrir el registro y especificar las líneas de gastos.
5. Seleccione un proveedor. Por ejemplo, escriba o seleccione `US-104`.
6. En el campo **Factura**, escriba un valor.
7. En el campo **Descripción**, escriba un valor.
8. En el campo **Crédito**, escriba un número.
9. En el campo **Aprobado por**, seleccione un aprobador en el menú desplegable.
10. Seleccione **Registrar**.

## <a name="approve-an-invoice"></a>Aprobar una factura
1. En el panel de exploración, vaya a **Módulos > Proveedores > Facturas > Aprobación de facturas**.
2. Seleccione **Nuevo**.
3. Seleccione el nombre del diario de aprobación de facturas que desee usar.
4. Seleccione **Líneas** para mostrar una página donde podrá seleccionar las facturas que desea aprobar.
5. Seleccione **Buscar asientos** para mostrar todas las facturas que están listas para su aprobación.
6. Marque la factura que ha creado, después haga clic en **Seleccionar**. Los asientos que seleccionó arriba se mueven en esta lista después de que los seleccione.  
7. Seleccione **Aceptar**.
8. Seleccione el campo del **número de cuenta** para agregar una cuenta de gastos en la factura.
9. Especifique un número de cuenta y salga del campo con el tabulador. Por ejemplo, escriba `600120`.
10. Seleccione **Registrar**.
11. Seleccione **Asiento** para ver las entradas que se han registrado. La cuenta de factura pendiente de aprobación se anula y se reemplaza con la cuenta de gastos real.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]