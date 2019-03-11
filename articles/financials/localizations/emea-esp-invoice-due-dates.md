---
title: Calcular las fechas de vencimiento y el informe en el período medio de pagos (España)
description: Este tema proporciona información acerca de las fechas de vencimiento y el período medio de pagos para España.
author: ShylaThompson
manager: AnnBe
ms.date: 09/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Spain
ms.author: anasyash
ms.dyn365.ops.version: Version 1611
ms.search.validFrom: 2016-11-30
ms.openlocfilehash: 6231be8dc847542d4fc0ef0d596cd6b1bc35ac03
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "370426"
---
# <a name="calculate-due-dates-and-report-on-the-average-period-of-payments-spain"></a>Calcular las fechas de vencimiento y el informe en el período medio de pagos (España)

[!include[banner](../includes/banner.md)]

## <a name="using-delivery-dates-to-calculate-invoice-due-dates"></a>Uso de fechas de entrega para calcular fechas de vencimiento de la factura

Las fechas de vencimiento de las facturas de venta, facturas de compra y las facturas de proyecto se calculan en función de las fechas de entrega o de las fechas de recepción de artículos y servicios. Las empresas privadas y las empresas de administración pública pueden especificar el número máximo de días en los que deben realizarse los pagos de factura. Este número máximo de días para el pago de facturas se conoce como fecha límite de vencimiento. Puede especificar límites de fecha de vencimiento en la página **Límites de fecha de vencimiento**.

Si una fecha límite de vencimiento se especifica en la página **Condiciones de pago** y la página **Grupos de artículos**, la fecha de vencimiento de la factura que se calcula se comprueba contra la fecha límite de vencimiento efectiva. La fecha de vencimiento de la factura se ajusta, si se requiere el ajuste, para que cumpla con el límite de fecha de vencimiento efectivo.

Para usar fechas de entrega y calcular las fechas de vencimiento de las facturas de ventas y de compra, establezca la opción **Use la fecha de entrega para calcular la fecha de vencimiento de pago** en **Sí** en la página **Condiciones de pago**, en la ficha desplegable **Configuración**.

Para las facturas de ventas, la fecha que se especifica en el campo **Fecha de recepción confirmada** en la ficha desplegable **Cabecera de pedido de ventas** en la página **pedido de ventas** se usa como la fecha de entrega.

Para las facturas de compra, la fecha de entrega es la fecha en la que se registra el albarán. Si hay varios albaranes disponibles para una factura de compra, la fecha de registro más temprana del albarán se usa como la fecha de entrega. Si no hay albarán disponible, la fecha de entrega especificada en el campo **Fecha de entrega** de la ficha desplegable **Encabezado del pedido de compra** en la página **Pedido de compra** se usa como la fecha de entrega para la factura.

> [!NOTE] 
> Los valores de los campos **Fecha de recepción confirmada** y **Fecha de entrega** para las líneas de pedido de ventas y las líneas de pedido de compra no se usan para los cálculos de fecha de vencimiento.

Las fechas de entrega de los pedidos de ventas del proyecto y los pedidos de compra del proyecto se determinan del mismo modo que las fechas de entrega de las facturas de ventas y compra normales. Para los tipos de transacción **Hora**, **gasto**, **Artículo**, **Cuota** y **A cuenta**, la fecha de transacción se usa como la fecha de entrega.

### <a name="calculate-invoice-due-dates-for-sales-and-purchase-invoices-based-on-delivery-dates-and-due-date-limits"></a>Calcular las fechas de vencimiento de la factura para las facturas de ventas y compra en función de las fechas de entrega y los límites de fecha de vencimiento

Para usar fechas de entrega para calcular las fechas de vencimiento de las facturas, en la página de **Condiciones de pago**, en la pestaña **Configuración**, establezca la opción **Use la fecha de entrega para calcular la fecha de vencimiento de pago** en **Sí**.

El siguiente ejemplo muestra qué parece la fecha de vencimiento de pago calculada para las condiciones de pago seleccionadas, si la opción **Use la fecha de entrega para calcular la fecha de vencimiento del pago** se establece en **Sí**.

| Condiciones de pago        | Fecha de entrega | Límite de fecha de vencimiento | Fecha de vencimiento calculada de la factura |Fecha de vencimiento de factura ajustada |
|-------------------------|---------------|----------------|-----------------------------|--------------------------|
| Mes actual + 15 días | 9 de junio de 2018  | 30 días        | 15 días después de finales de junio, o 15 de julio de 2018. Sin embargo, el período transcurrido entre 9 de junio y 15 de julio tiene 36 días. Por lo tanto, supera la fecha límite de vencimiento de 30 días. | 9 de julio de 2018 |

Si hay varios albaranes disponibles para una factura de compra, la fecha de registro más temprana del albarán se usa como la fecha de entrega. Por ejemplo, los albaranes de un pedido de compra se registran el 12 de junio de 2018, el 15 de junio de 2018, y el 18 de junio de 2018. En este caso, se utiliza el 12 de junio de 2018 como la fecha de entrega.

Si a una factura se aplica más de un límite de fecha de vencimiento, se usa el límite de fecha de vencimiento con el número de días más bajo para calcular la fecha de vencimiento de la factura. Por ejemplo, los límites de fecha de vencimiento se configuran para 30 días y 45 días. En este caso, la fecha límite de vencimiento que se usa para calcular la fecha de vencimiento de la factura es de 30 días, independientemente de dónde se configure la fecha límite de vencimiento.

## <a name="set-up-due-date-limits-to-calculate-invoice-due-dates"></a>Configurar límites de fecha de vencimiento para calcular las fechas de vencimiento de la factura
Use la página **Límites de fecha de vencimiento** para crear los límites de fecha de vencimiento que especifican el número máximo de días en que los pagos de facturas deben realizarse.

1. Seleccione **proveedores \> Configuración > pago \> Límites de fecha de vencimiento**.

     - O bien -

    Seleccione **Clientes \> Configuración \> Pago \> Límites de fecha de vencimiento**.

2. Haga clic en **Nuevo** para crear un límite de fecha de vencimiento.
3. En el campo **Límite de fecha de vencimiento**, escriba un nombre para la nueva fecha límite de vencimiento. En el campo **Descripción**, escriba una descripción.
4. En la pestaña **General**, haga clic en **Añadir** para agregar una línea.
5. En el campo **Intervalo del período**, seleccione el tipo de intervalo del período.

    - **Días**: el límite de fecha de vencimiento corresponde al número de días que indica en el campo **Número de unidades**.
    - **Meses**: el límite de fecha de vencimiento corresponde al número de meses que indica en el campo **Número de unidades**.

6. En el campo **Número de unidades**, especifique el número de días o meses para el límite de fecha de vencimiento.

## <a name="assign-due-date-limits-to-terms-of-payment-to-calculate-invoice-due-dates"></a>Asignar límites de fecha de vencimiento a los términos de pago para calcular las fechas de vencimiento de la factura

Al crear y registrar facturas de ventas o facturas de compra, la fecha de vencimiento de la factura se calcula según las condiciones de pago que se especifican para las facturas. La fecha de vencimiento de la factura que se calcula se comprueba contra el límite de fecha de vencimiento. La fecha de vencimiento de la factura se ajusta, si se requiere el ajuste, para que cumpla con el límite de fecha de vencimiento. Si no se especifica ningún límite de fecha de vencimiento, la fecha de vencimiento de la factura que se calcula se usará como la fecha de vencimiento final de la factura.

Use la página **Condiciones de pago** para especificar un límite de fecha de vencimiento, con el fin de asegurarse de que la fecha de vencimiento de la factura que se calcula se encuentre en el límite especificado de la fecha de vencimiento.

1. Seleccione **Proveedores \> Configuración \> Pago \> Condiciones de pago**.

     - O bien - 

    Seleccione **Clientes \> Configuración \> Pago \> Condiciones de pago**.

2. Presione el botón **Nuevo** para crear condiciones de pago o seleccione una línea de condiciones de pago.
3. En la ficha desplegable **Configuración**, establezca la opción **Use la fecha de entrega para calcular la fecha de vencimiento de pago** en **Sí** para calcular la fecha de vencimiento aplicando las condiciones de pago a la fecha de entrega en vez de aplicarlas a la fecha de la factura.
4. En el campo **Límite de fecha de vencimiento**, seleccione un límite de fecha de vencimiento.

## <a name="calculate-invoice-due-dates-based-on-the-payment-schedule-and-the-payment-day"></a>Calcular las fechas de vencimiento de la factura en función de los multivencimientos y el día de pago

Puede especificar la programación de pago y el día de pago de una factura de cliente, una factura de servicios, una factura de proveedor, o una factura de proyecto antes de generar la factura. En Microsoft Dynamics 365 for Finance and Operations, las fechas de vencimiento del pago de facturas de proveedor y de las facturas del proyecto se calculan basándose en las fechas de entrega de artículos y servicios. Para las facturas de cliente, las fechas de vencimiento se calculan basándose en las fechas de recepción de la factura de cliente.

En la página **Límites de fecha de vencimiento**, puede especificar el número de días del período de gracia, en el que se debe realizar el pago de factura. Puede establecer la opción **Use la fecha de entrega para calcular la fecha de vencimiento de pago** en **Sí** en la página **Condiciones de pago** para usar la fecha de entrega para calcular las fechas de vencimiento de la factura.

Debe especificar una fecha de vencimiento de pago anterior al límite de fecha de vencimiento para una factura. Puede establecer los multivencimientos y el día de pago de una factura y luego calcular manualmente la fecha de vencimiento de la factura. Si esa fecha de vencimiento es posterior a la fecha límite de vencimiento que se establece en la página **Límites de fecha de vencimiento**, debe corregir la fecha de vencimiento.

## <a name="generate-the-information-on-average-period-of-payments-to-suppliers-report"></a>Generar el informe de información del período medio de pago a los proveedores
Puede generar el informe **Información sobre el periodo medio de pago a proveedores**. Este informe estadístico contiene información acerca de las facturas pagadas durante un período que especifique. El informe muestra los importes pagados basados en las condiciones de pago. También muestra los importes pagados fuera de las condiciones de pago. El informe incluye los importes que se pagaron mediante diarios de pagos y pagarés.

Para generar el informe siga los pasos siguientes.

1. Seleccione **contabilidad general \> Consultas e informes \> Informes de contabilidad \> Información sobre el periodo medio de pago a proveedores**.
2. En el grupo de campos **Período actual**, seleccione las fechas inicial y final del período para el que va a generar el informe.
3. En el grupo de campos **Período comparativo**, seleccione las fechas inicial y final del período comparativo. Por ejemplo, puede seleccionar las fechas inicial y final del período fiscal anterior.
4. En el grupo de campos **Cálculo**, en el campo **Método de cálculo**, seleccione el método de cálculo (**Fecha de factura** o **Fecha de vencimiento**).
5. En la ficha desplegable **Registro para incluir**, especifique los criterios que deben emplearse para seleccionar las transacciones del proveedor, como facturas, pagos y diarios de pagarés. (Use **Filtrar** para especificar los criterios).
6. Haga clic en **Aceptar** para generar el informe.
