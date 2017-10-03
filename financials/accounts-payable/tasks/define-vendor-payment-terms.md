--- 
title: Definir condiciones de pagos a proveedores
description: Configurar condiciones de pago para facturas de proveedor.
author: abruer
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: cbac3b27c25377abff341c4bf259e553c14a4ae8
ms.contentlocale: es-es
ms.lasthandoff: 07/27/2017

---
# <a name="define-vendor-payment-terms"></a>Definir condiciones de pagos a proveedores

[!include[task guide banner](../../includes/task-guide-banner.md)]

Configurar condiciones de pago para facturas de proveedor. Esta tarea usa la empresa de demostración USMF.

1. Vaya a Proveedores > Configuración de pagos > Condiciones de pago.
2. Haga clic en Nuevo.
    * La página Condiciones de pago se usa para definir cómo se calculará la fecha de vencimiento. No se usa para definir cómo se calculará la fecha de descuento por pronto pago.  
3. En el campo Condiciones de pago, escriba un valor.
4. En el campo Descripción, escriba un valor.
5. En el campo Días, especifique un número.
    * El número especificado aquí se usará para agregarlo a la fecha de vencimiento, o al final del período identificado en la forma de pago. Por ejemplo, si selecciona Neto, el número se agregará a la fecha de vencimiento. Si selecciona Mes actual, para calcular la fecha de vencimiento se agregará el número al último día del mes actual.  
6. Haga clic en Guardar.
7. Cierre la página.
8. Vaya a Proveedores > Configuración de pagos > Descuentos por pronto pago.
9. Haga clic en Nuevo.
10. En el campo Descuento por pronto pago, escriba un Id.
11. En el campo Descripción, escriba un valor.
12. Si el proveedor ofrece varios niveles de descuento, seleccione el descuento por pronto pago siguiente después de vencer el actual.
13. Cierre la página.
14. En el campo Días, especifique un número.
    * La cantidad especificada en el campo Días se usará para calcular la fecha de descuento por pronto pago, en función de la opción que se haya seleccionado en el campo Neto/Actual. Si ha seleccionado Neto, la cantidad se agregará a la fecha de factura para determinar la fecha de descuento por pronto pago. Si se ha seleccionado Mes actual, la cantidad se agregará al final del mes de la divisa para determinar la fecha de descuento por pronto pago.  
15. Escriba el porcentaje de descuento por pronto pago en el campo Descuento. 
16. Especifique la cuenta principal en la que se registrará el descuento por pronto pago para las facturas de cliente.
17. Especifique la cuenta principal en la que se registrará el descuento por pronto pago para las facturas de proveedor.
    * Si Cuentas de contrapartida para descuentos está definido en Usar cuenta principal para descuentos de proveedor, se usará la cuenta principal.  Si la opción se establece en las cuentas en las líneas de factura, el descuento por pronto pago se registrará en las cuentas de activos/gastos en las líneas de la factura.  
18. Haga clic en Guardar.


