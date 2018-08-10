--- 
title: Auditar facturas y datos clave en sistema de proveedores
description: Al recibir una factura de un proveedor en concepto de bienes o servicios de un pedido de compra, es posible que los procesos comerciales requieran que los bienes o servicios se reciban antes de poder aprobar la factura para su pago.
author: saraschi2
manager: AnnBe
ms.date: 02/16/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: 5cd9448c95b7ec0c4a82aca3d21d961259dfb109
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="audit-invoices-and-key-data-in-accounts-payable"></a>Auditar facturas y datos clave en sistema de proveedores

[!include [task guide banner](../../includes/task-guide-banner.md)]

Al recibir una factura de un proveedor en concepto de bienes o servicios de un pedido de compra, es posible que los procesos comerciales requieran que los bienes o servicios se reciban antes de poder aprobar la factura para su pago. Antes de empezar, asegúrese de que la clave de configuración Conciliación de facturas esté seleccionada. 

En la página Parámetros de proveedores, asegúrese de que la opción Habilitar validación de conciliación de facturas esté seleccionada, el campo Registrar factura con discrepancias esté establecido en Requerir aprobación y el campo Directiva de conciliación de líneas esté establecido en Triple conciliación.

Este procedimiento usa la empresa de demostración USMF. El rol de administrador de proveedores o jefe de contabilidad realizaría estos pasos.


## <a name="create-a-purchase-order"></a>Crear un pedido de compra
1. Vaya a Todos los pedidos de compra.
2. Haga clic en Nuevo.
3. En el campo Cuenta de proveedor, haga clic en el botón desplegable para abrir la búsqueda.
4. En el campo Cuenta de proveedor, escriba un valor.
5. Haga clic en Aceptar
6. Haga clic en Agregar línea.
7. En el campo Código de artículo, escriba un valor.
8. En el panel de acciones, haga clic en Compra.
9. Haga clic en Confirmar.

## <a name="post-a-product-receipt"></a>Registrar una recepción de producto
1. En el panel de acciones, haga clic en Recibir.
2. Haga clic en Recepción de producto.
3. En la lista, marque la fila seleccionada.
4. En el campo Recepción de producto, escriba un valor.
5. Haga clic en Aceptar

## <a name="record-and-match-a-vendor-invoice-to-a-product-receipt"></a>Registrar y conciliar una factura de proveedor con una recepción de producto
1. En el panel de acciones, haga clic en Factura.
2. Haga clic en Factura.
3. En el campo Número, escriba un valor.
4. Haga clic en Valor predeterminado de origen: Cantidad pedida para abrir el cuadro de diálogo desplegable.
5. En el campo Cantidad predeterminada para líneas, seleccione una opción.
6. Haga clic en Aceptar
7. Haga clic en Sí.
8. Haga clic en Conciliar recepciones de producto.
9. Haga clic en Aceptar
10. En el panel de acciones, haga clic en Revisar.
11. Haga clic en Detalles coincidentes.


