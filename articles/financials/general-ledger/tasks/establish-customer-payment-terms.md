--- 
title: Establecer condiciones de pago de cliente
description: "Este procedimiento define una configuración de descuento por pronto pago y fecha de vencimiento."
author: aprilolson
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
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 4e0e43962bea3ff1c3adafa73da4ce3862963a51
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="establish-customer-payment-terms"></a>Establecer condiciones de pago de cliente

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento define una configuración de descuento por pronto pago y fecha de vencimiento. Esta guía de la tarea usa la empresa de demostración USMF.

1. Vaya a Clientes > Configuración de pagos > Días de pago.
    * La configuración de los términos de pago se comparte para clientes y proveedores. Si los define en un módulo, estarán disponibles en el otro módulo también. Para esta guía de la tarea, configuraré todos los términos de pago en clientes.  
2. Haga clic en Nuevo.
    * Cree un día de pago si sus condiciones de pago requieren un día concreto de la semana (lunes, martes, etc.) o de una fecha específica del mes (5, 10, etc.).  
3. En el campo de día de pago, especifique un identificador para el día de pago en el campo de día de pago.
4. En el campo Descripción, especifique una descripción del día de pago.
5. En el campo Semana/Mes, seleccione la semana o el mes.
    * Si desea especificar un día de la semana, por ejemplo, lunes, seleccione Semana. Si desea especificar una fecha del mes, por ejemplo, 10, seleccione Mes. Para este ejemplo, seleccione Mes.  
6. En el campo Día del mes, escriba una fecha.
    * La fecha se debe especificar como un número, por ejemplo, “10”, y no como “10°”.  
7. Haga clic en Guardar.
8. Cierre la página.
9. Vaya a Clientes > Configuración de pagos > Condiciones de pago.
10. Haga clic en Nuevo.
    * Las condiciones de pago se usan para definir cómo se calcularán las fechas de vencimiento. La configuración de fecha de descuento por pronto pago se define en una página independiente.  
11. En el campo Condiciones de pago, especifique un Id. en el campo de condiciones de pago.
12. En el campo Descripción, escriba una descripción.
13. Seleccione un método de pago, por ejemplo, Contra reembolso, Neto, Mes actual, etc.
    * El método de pago se usa para definir el inicio de cómo se calculará la fecha de vencimiento.  Por ejemplo, Neto se usa si la fecha de vencimiento siempre es un número fijo de meses o de días después de la fecha de la factura. Se puede usar contra reembolso cuando se requiere el pago al facturar, por lo que no calcularía una fecha de vencimiento. Seleccione el mes actual para esta guía de la tarea.  
14. Seleccione un día de pago si un día concreto de la semana o la fecha se incluye en el cálculo.
    * En función de sus condiciones de pago, puede especificar una cantidad en meses o días. O puede usar Programación de pagos o Día de pago para “agregarlo” al final del método de pago. Si la fecha de vencimiento siempre es el día 10 del mes próximo, seleccione el día de pago 10.  
15. Haga clic en Guardar.
16. Cierre la página.
17. Vaya a Clientes > Configuración de pagos > Descuentos por pronto pago.
18. Haga clic en Nuevo.
    * Esta página se usa para definir cómo se calculará la fecha de descuento por pronto pago.  
19. En el campo del descuento por pronto pago, escriba una identificación en el campo del descuento por pronto pago.
20. En el campo Descripción, escriba una descripción.
21. Si un descuento por pronto pago con niveles está disponible, seleccione el siguiente código de descuento que es relevante después de este nuevo descuento por pronto pago.
22. Especifique el número de días utilizados para calcular la fecha de descuento por pronto pago.
    * Si ha seleccionado Neto, el número de días se agregará a la fecha de factura para calcular la fecha de descuento por pronto pago.  
23. Especifique el porcentaje del descuento por pronto pago.
24. Especifique la cuenta principal en la que se registrará el descuento por pronto pago para las facturas de cliente.
25. En el campo Cuentas de contrapartida para descuentos, seleccione una opción.
    * Si selecciona “Cuentas en las líneas de factura”, el descuento por pronto pago se registrará en la misma cuenta principal de activos/gastos en las líneas de la factura de proveedor. Si selecciona “Usar cuenta principal para las facturas de proveedor” el descuento por pronto pago se registrará en la cuenta principal que se define en “Cuenta principal para las facturas de proveedor”. En este ejemplo, seleccione “Usar cuenta principal para las facturas de proveedor”.  
26. Especifique la cuenta principal en la que se registrará el descuento por pronto pago para las facturas de proveedor.
27. Haga clic en Guardar.


