---
title: Establecer condiciones de pago de cliente
description: Este procedimiento define una configuración de descuento por pronto pago y fecha de vencimiento.
author: aprilolson
ms.date: 08/29/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: PaymDay, PaymTerm, CashDisc
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 9b2ae5e63a2efb4bc913efa4d88c65a70133a2d9
ms.sourcegitcommit: f96e5dec5a808d9819d2a23b8e15ce00aeff475b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/10/2022
ms.locfileid: "9752786"
---
# <a name="establish-customer-payment-terms"></a>Establecer condiciones de pago de cliente

[!include [banner](../../includes/banner.md)]

Este procedimiento define una configuración de descuento por pronto pago y fecha de vencimiento. Esta guía de la tarea usa la empresa de demostración USMF.

1. Vaya a **Panel de exploración > Módulos > Clientes > Configuración de pagos > Días de pago**. La configuración de los **términos de pago** se comparte para **clientes** y **proveedores**. Si los define en un módulo, estarán disponibles en el otro módulo también. Para esta guía de la tarea, se configuraran todos los términos de pago en **Clientes**.
2. Haga clic en **Nuevo**. Cree un día de pago si sus condiciones de pago requieren un día concreto de la semana (lunes, martes, etc.) o de una fecha específica del mes (5, 10, etc.). 
3. En el campo **Día de pago**, escriba un identificador.
4. En el campo **Descripción**, especifique una descripción del día de pago.
5. En el campo **Semana/Mes**, seleccione la semana o el mes. Si desea especificar un día de la semana, por ejemplo, lunes, seleccione Semana. Si desea especificar una fecha del mes, por ejemplo, 10, seleccione Mes. Para este ejemplo, seleccione Mes. 
6. En el campo **Día del mes**, escriba una fecha. La fecha se debe especificar como un número, por ejemplo, “10”, y no como “10°”. 
7. Haga clic en **Guardar**.
8. Cierre la página.
9. Vaya a **Panel de exploración > Módulos > Clientes > Configuración de pagos > Condiciones de pago**. 

>[!NOTE] 
>Si las **Condiciones de pago** son **Dinero**, el campo **Pago en efectivo** en la página **Condiciones de pago** debe ser **No**.

10. Haga clic en **Nuevo**. **Condiciones de pago** se usa para definir cómo se calcularán las fechas de vencimiento. La configuración de fecha de descuento por pronto pago se define en una página independiente. 
11. En el campo **Condiciones de pago**, escriba un identificador.
12. En el campo **Descripción**, escriba una descripción.
13. Seleccione un **Método de pago** como **Contra reembolso**, **Neto**, **Mes actual**, etc. El **Método de pago** se usa para definir el inicio de cómo se calculará la deuda. Por ejemplo, **Neto** se usa si la fecha de vencimiento siempre es un número fijo de meses o de días después de la fecha de la factura. Se puede usar **Contra reembolso** cuando se requiere el pago al facturar, por lo que no calcularía una fecha de vencimiento. Seleccione **Mes actual** para esta guía de tareas.  
14. Seleccione un **día de pago** si un día concreto de la semana o la fecha se incluye en el cálculo. En función de sus condiciones de pago, puede especificar una cantidad en meses o días. O puede usar **Programación de pagos** o **Día de pago** para “agregarlo” al final del **Método de pago**. Si la fecha de vencimiento siempre es el día 10 del mes próximo, seleccione el **día de pago** 10. Si está usando un **Calendario de pago**, puede definir cómo se determina la fecha de vencimiento cuando la fecha calculada corresponde a un día no laborable. La fecha de vencimiento inicial se calcula utilizando días naturales. Si la fecha calculada corresponde a un día no laborable, puede ajustar la fecha de vencimiento calculada a la siguiente fecha laborable o al día laborable anterior.
15. Haga clic en **Guardar**.
16. Cierre la página.
17. Vaya a **Clientes > Configuración de pagos > Descuentos por pronto pago**.
18. Haga clic en **Nuevo**. Esta página se usa para definir cómo se calculará la fecha de descuento por pronto pago. 
19. En el campo **Descuento por pronto pago**, escriba un identificador.
20. En el campo **Descripción**, escriba una descripción.
21. Si un descuento por pronto pago con niveles está disponible, seleccione el **Código de descuento siguiente** que es relevante después de este nuevo descuento por pronto pago.
22. En el campo **Días**, especifique el número de días utilizados para calcular la fecha de descuento por pronto pago. Si ha seleccionado **Neto**, el número de días se agregará a la fecha de factura para calcular la fecha de descuento por pronto pago.  
23. En el campo **Porcentaje de descuento**, escriba el porcentaje de descuento por pronto pago.
24. En **Cuenta principal para descuentos de cliente**, especifique la cuenta principal en la que se contabilizará el descuento por pronto pago de las facturas de cliente.
25. En el campo **Cuentas de contrapartida para descuentos**, seleccione una opción. Si selecciona “Cuentas en las líneas de factura”, el descuento por pronto pago se registrará en la misma cuenta principal de activos/gastos en las líneas de la factura de proveedor. Si selecciona **Usar cuenta principal para las facturas de proveedor** el descuento por pronto pago se registrará en la cuenta principal que se define en **Cuenta principal para las facturas de proveedor**. En este ejemplo, seleccione **Usar cuenta principal para las facturas de proveedor**. 
26. En **Cuenta principal para descuentos de proveedor**, especifique la cuenta principal en la que se contabilizará el descuento por pronto pago de las facturas de proveedor.
27. Haga clic en **Guardar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
