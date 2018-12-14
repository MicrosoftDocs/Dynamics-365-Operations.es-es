--- 
title: Auditar facturas y datos clave en sistema de proveedores
description: Al recibir una factura de un proveedor en concepto de bienes o servicios de un pedido de compra, es posible que los procesos comerciales requieran que los bienes o servicios se reciban antes de poder aprobar la factura para su pago.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: PurchTable, PurchCreateOrder, PurchEditLines, VendEditInvoice, VendEditInvoiceDefaultQuantityForLinesDropDialog,  VendJournalMatch_PackingSlip, VendInvoiceMatchingDetails
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: cc995b474e86272b49629f97e1b4d4b4fb597b9d
ms.openlocfilehash: 946076d682a10becdc2c4a8baff7f52de7893119
ms.contentlocale: es-es
ms.lasthandoff: 12/04/2018

---
# <a name="audit-invoices-and-key-data-in-ap-system"></a>Auditar facturas y datos clave en sistema de proveedores

[!include [task guide banner](../../includes/task-guide-banner.md)]

Al recibir una factura de un proveedor en concepto de bienes o servicios de un pedido de compra, es posible que los procesos comerciales requieran que los bienes o servicios se reciban antes de poder aprobar la factura para su pago. Antes de empezar, asegúrese de que la clave de configuración Conciliación de facturas esté seleccionada. 

En la página Parámetros de proveedores, asegúrese de que la opción Habilitar validación de conciliación de facturas esté seleccionada, el campo Registrar factura con discrepancias esté establecido en Requerir aprobación y el campo Directiva de conciliación de líneas esté establecido en Triple conciliación.

Este procedimiento usa la empresa de demostración USMF. El rol de administrador de proveedores o jefe de contabilidad realizaría estos pasos.


## <a name="create-a-purchase-order"></a>Crear un pedido de compra
1. Vaya a **Todos los pedidos de compra.**
2. Haga clic en **Nuevo**.
3. En el campo **Cuenta de proveedor**, escriba un valor.
4. Haga clic en **Aceptar**.
5. Haga clic en **Agregar línea.**
6. En el campo **Código de artículo**, escriba un valor.
7. En el panel de acciones, haga clic en **Compra.**
8. Haga clic en **Confirmar**.

## <a name="post-a-product-receipt"></a>Registrar una recepción de producto
1. En el panel de acciones, haga clic en **Recibir.**
2. Haga clic en **Recepción de producto.**
3. En el campo **Recepción de producto**, escriba un valor.
4. Haga clic en **Aceptar**.

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>Registrar y conciliar una factura de proveedor con una recepción de producto
1. En el panel de acciones, haga clic en **Factura > Factura**.
2. En el campo **Número**, escriba un valor.
3. Haga clic en **Valor predeterminado de origen: Cantidad pedida** para abrir el cuadro de diálogo desplegable.
4. En el campo **Cantidad predeterminada para líneas**, seleccione una opción.
5. Haga clic en **Aceptar**.
6. Haga clic en **Sí**.
7. Haga clic en **Conciliar recepciones de producto**.
8. Haga clic en **Aceptar**.
9. En el panel de acciones, haga clic en **Revisar**.
10. Haga clic en **Detalles coincidentes**.


