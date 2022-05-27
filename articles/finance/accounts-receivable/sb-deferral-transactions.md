---
title: Transacciones aplazadas en la facturación de suscripción
description: Este tema describe las diversas transacciones que se pueden usar en las transacciones de aplazamiento como parte de los aplazamientos de ingresos y gastos en la facturación de suscripción.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 5913308d4ee9fdcb8cf2b862171078f27f651662
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8686028"
---
# <a name="deferral-default-transactions"></a>Transacciones predeterminadas aplazadas

Este tema describe las transacciones que permiten el aplazamiento de ingresos y gastos. Las programaciones de aplazamientos siempre se basan y dependen de un documento de origen o una programación de facturación. Las programaciones de aplazamientos se crean en función de los valores predeterminados, y no se pueden introducir ni crear por separado.

## <a name="sales-order-transaction-deferral"></a>Aplazamiento de transacción de pedido de ventas

Utilice la página **Aplazamientos** o **Crear nota de crédito** para introducir o editar los parámetros de aplazamiento para una línea de pedido de ventas.

> [!NOTE]
> Cuando se crea un pedido de ventas a partir de una programación de facturación, todos los valores de la página **Aplazamientos** o **Crear nota de crédito** son de solo lectura y los parámetros de aplazamiento no se pueden editar. Para editar los valores, utilice la página **Modificar programación**.

### <a name="edit-deferral-options"></a>Editar opciones de aplazamiento

Para editar las opciones de aplazamiento de una línea, siga estos pasos.

1. Cree una transacción de pedido de ventas.
2. Seleccione la línea y luego seleccione **Aplazamientos**.
3. En la página **Aplazamiento de transacciones**, la opción **Aplazado** debe estar configurada en **Sí**. Edite otros campos, según sea necesario.
4. Para obtener una vista previa de la programación de aplazamientos, seleccione **Vista previa**.
5. Si realizó algún cambio en el aplazamiento de la transacción, seleccione **Aceptar** y regrese a la página de la transacción.
6. Confirme y registre la transacción.

Después de contabilizar la transacción, abra la página **Todas la sprogramaciones de aplazamiento** página para ver la programación de aplazamientos.

### <a name="create-a-credit-note"></a>Crear una nota de crédito

Para crear una nota de abono, siga los siguientes pasos.

1. Cree una transacción de pedido de ventas.
2. En la sección **Líneas de pedidos de ventas**, seleccione el artículo para el que desea crear una nota de crédito.
3. Seleccione **Línea de pedido de ventas** \> **Nuevo** y luego seleccione **Nota de crédito**.
4. Seleccione **Aplazamientos**.
5. En la página **Aplazamiento de transacciones de pedidos de ventas**, configure la opción **Ajustar la programación existente** en **Sí** para el artículo
6. En el campo **programación ajustada**, seleccione la programación de aplazamiento al que desea aplicar la nota de crédito.
7. Actualice los campos **Recalcular fecha** y **Fecha final** según necesite.
8. Seleccione **Aceptar**.
9. Finalice el registro de la transacción del pedido de ventas.

### <a name="purchase-orders-and-purchase-invoices"></a>Pedidos de compra y facturas de compra

Si desea utilizar la funcionalidad de aplazamiento para un pedido de compra, primero genere la factura. Luego use la página **Facturas de proveedores pendientes** para editar o agregar artículos aplazados. No puede editar ni agregar aplazamientos directamente a un pedido de compra.

1. Utilice la página **Facturas de proveedores pendientes** para introducir una factura de proveedor.

    Cuando introduce una línea, el aplazamiento se establece automáticamente para el artículo o la categoría de adquisición que seleccione. Este aplazamiento se basa en la configuración de aplazamientos de la página **Valores predeterminados de aplazamiento**. Los aplazamientos se pueden editar o agregar en el nivel de distribución.

3. En la línea de compras, seleccione **Finanzas \> Distribuir importes**.
4. Para cada importe de distribución, seleccione **Aplazamientos**. Cuando se registra la factura, se crea una programación de aplazamiento para cada distribución para la que se establece un aplazamiento.

### <a name="tax"></a>Impuesto

En algunos casos, el importe del impuesto puede ser total o parcialmente no recuperable. Si el importe del impuesto de una línea aplazable contiene un importe no recuperable, el importe del impuesto no recuperable se incluye en el importe de la programación diferible cuando se registra la factura.

### <a name="variance"></a>Desviación

Si el importe de la línea de la factura del proveedor difiere del importe de la línea del pedido de compra, se crean distribuciones de desviación. Si la línea se aplaza, la cuenta contable para estas distribuciones se establece en la cuenta de aplazamiento y los importes se incluyen en el importe de la programación aplazable cuando se contabiliza la factura. Estas distribuciones se denominan **Desviación de precio** y **Desviación de coste**.

### <a name="general-journals-and-invoice-journals"></a>Diarios generales y diarios de facturas

Utilice la página **Aplazamientos** para introducir los parámetros de aplazamiento para una línea de asiento del diario. También puede obtener una vista previa del calendario de aplazamientos para los aplazamientos lineales. Cuando introduce una línea, el aplazamiento se establece automáticamente en función de la configuración de las cuentas de aplazamiento en la página **Valores predeterminados de aplazamiento**. Puede modificar manualmente las opciones de aplazamiento para cada línea. Cuando se contabiliza el asiento del diario, se crea la programación de aplazamiento.

#### <a name="post-and-transfer"></a>Registrar y transferir

Para contabilizar el asiento del diario, utilice el comando **Registrar y transferir**. Las opciones de aplazamiento seguirán la línea a la que se aplica el asiento. Para los asientos sin errores, se crea una programación de aplazamiento si se aplazan. Para los asientos con un error que se transfieren, las opciones de aplazamiento también se transfieren con ellos.

#### <a name="tax"></a>Impuesto

En algunos casos, el importe del impuesto puede ser total o parcialmente no recuperable. Si el importe del impuesto de una línea aplazable contiene un importe no recuperable, el importe del impuesto no recuperable se incluye en el importe de la programación diferible cuando se registra la factura.

## <a name="free-text-invoice-transaction-deferral"></a>Aplazamiento de transacción de factura de servicios

Utilice la página **Aplazamientos** para introducir los parámetros de aplazamiento para una distribución de línea de factura de servicios. Cuando se introduce una distribución, el aplazamiento se establece automáticamente en función de la configuración de aplazamiento en la página **Valores predeterminados de aplazamiento**.

## <a name="fields"></a>Campos

La página **Aplazamiento de transacción** contiene los siguientes campos.

| Campo | Description |
|-------|-------------|
| Aplazado | <p>Especifique si la línea es un aplazamiento:</p><ul><li>**Sí**: la línea es un aplazamiento.</li><li>**No**: la línea no es un aplazamiento.</li></ul><p>Cuando esta opción se establece en **Sí**, la opción **Ajustar la programación existente** no está disponible. Para artículos y cargos que ya están configurados como aplazados, esta opción se establece en **Sí**. Para artículos y cargos que no están configurados de forma predeterminada como aplazados, esta opción se establece en **Sí**.</p> |
| Ajustar programación existente | <p>Especifique si la línea es un ajuste de una programación de aplazamiento existente:</p><ul><li>**Sí**: la nueva línea de ventas es un ajuste de una programación de aplazamiento existente. En este caso, puede seleccionar una programación de aplazamiento en el campo **Programación ajustada**.</li><li>**No**: la nueva línea de ventas no es un ajuste de una programación de aplazamiento existente.</li></ul><p>Cuando esta opción se establece en **Sí**, la opción **Aplazado** no está disponible.</p> |
| Programación ajustada | <p>Seleccione la programación de aplazamiento que la línea está ajustando. A continuación, todos los valores de la página se actualizan con los valores de la programación de aplazamiento de origen. Estos valores no se pueden editar.</p><p>Este campo solo está disponible cuando la opción **Ajustar la programación existente** se establece en **Sí**.</p> |
| Fecha de nuevo cálculo | <p>Especifique la fecha de inicio del período desde el que desea volver a calcular el importe restante. La fecha predeterminada es la fecha del siguiente período no reconocido.</p><p>Este campo solo está disponible cuando la opción **Ajustar la programación existente** se establece en **Sí**.</p> |
| Fecha final | <p>Según el tipo de aplazamiento, la fecha de finalización puede o no actualizarse:</p><ul><li>Para un aplazamiento lineal, especifique la nueva fecha de finalización de la programación. La fecha de finalización existente de la programación de aplazamiento es el valor predeterminado.</li><li>Para un aplazamiento basado en eventos, especifique la fecha de finalización de la línea de eventos de crédito. Esta fecha puede estar en blanco.</li></ul><p>Este campo solo está disponible cuando la opción **Ajustar la programación existente** se establece en **Sí**.</p> |
| Número de programación de facturación | <p>Número de programación de facturación.</p><p>Este campo está disponible solo para programaciones de facturación de contratos periódicos.</p> |
| Método de ajuste de aplazamiento | <p>El método de ajuste aplazado. El valor coincide con el valor de la página **Procesamiento de terminación masiva** para la programación de facturación del contrato periódico.</p><p>Este campo está disponible solo para programaciones de facturación de contratos periódicos.</p> |
| **Cuentas: ingresos** | |
| Cuenta de aplazamiento | <p>La cuenta de aplazamiento, que es la cuenta de registro que aparece en la página **Pedidos de venta**.</p><p>Si la línea no se aplaza, este campo está en blanco. En este caso, la cuenta de contabilización es la cuenta de ingresos predeterminada.</p> |
| Cuenta de reconocimiento | <p>Especifique la cuenta que se utiliza cuando se reconoce un aplazamiento. Esta cuenta debe diferir de la cuenta de aplazamiento.</p><p>Cuando la opción **Aplazado** está configurada inicialmente en **Sí**, los valores de dimensión que se utilizan en la cuenta de aplazamientos se copian en la cuenta de reconocimiento. Si la dimensión de la cuenta de aplazamiento no existe para la cuenta de reconocimiento, se ignora.</p> |
| Cuenta de reconocimiento inicial | <p>Seleccione la cuenta para el reconocimiento inicial de ingresos. El valor predeterminado es el de la página **Valores predeterminados de aplazamiento**.</p><p>Este campo está disponible sólo cuando el campo **Método de publicación aplazada** se establece en **Ganancias y perdidas** en la página **Parámetros de aplazamiento de ingresos y gastos**.</p> |
| Cuenta de contrapartida de reconocimiento | <p>Seleccione la cuenta para el reconocimiento inicial de contrapartidas. El valor predeterminado es el de la página **Valores predeterminados de aplazamiento**.</p><p>Este campo está disponible sólo cuando el campo **Método de publicación aplazada** se establece en **Ganancias y perdidas** en la página **Parámetros de aplazamiento de ingresos y gastos**.</p> |
| **Cuentas: descuento** | Esta sección aparece solo para artículos aplazados. Está oculta para cargos aplazados. |
| Cuenta de aplazamiento | <p>Especifique el número de la cuenta de aplazamiento de descuento. El valor predeterminado es el de la página **Valores predeterminados de aplazamiento**.</p><p>Este campo está disponible sólo cuando el campo **Opción de aplazamiento de descuento** se establece en **Programación de descuentos independiente** en la página **Parámetros de aplazamiento de ingresos y gastos** y se aplica un descuento a la línea.</p> |
| Cuenta de reconocimiento | <p>Especifique el número de la cuenta de reconocimiento de descuento. El valor predeterminado es el de la página **Valores predeterminados de aplazamiento**.</p><p>Este campo está disponible sólo cuando el campo **Opción de aplazamiento de descuento** se establece en **Programación de descuentos independiente** en la página **Parámetros de aplazamiento de ingresos y gastos** y se aplica un descuento a la línea.</p> |
| Cuenta de reconocimiento inicial | <p>Seleccione la cuenta para el reconocimiento inicial de descuento. El valor predeterminado es el de la página **Valores predeterminados de aplazamiento**.</p><p>Este campo está disponible sólo cuando el campo **Método de aplazamiento de registro** se establece en **Ganacias y pérdidas** en la página **Parámetros de aplazamiento de ingresos y gastos** y se aplica un descuento a la línea.</p> |
| Cuenta de contrapartida de reconocimiento | <p>Seleccione la cuenta para el reconocimiento inicial de contrapartidas. El valor predeterminado es el de la página **Valores predeterminados de aplazamiento**.</p><p>Este campo está disponible sólo cuando el campo **Método de aplazamiento de registro** se establece en **Ganacias y pérdidas** en la página **Parámetros de aplazamiento de ingresos y gastos** y se aplica un descuento a la línea.</p> |
| **Cuentas: consumo** | Esta sección aparece solo para artículos aplazados. Está oculta para cargos aplazados. |
| Cuenta de aplazamiento | <p>Especifique el número de la cuenta de aplazamiento de consumo.</p><p>Para los productos estándar, se crean dos programaciones de aplazamiento:</p><ul><li>**Ventas estándar**: una programación de ingresos que tiene un saldo acreedor. En este caso, seleccione la cuenta de aplazamiento de consumo.</li><li>**Consumo**: una programación de gastos de consumo (coste de bienes vendidos \[COGS\]) que tiene un saldo deudor. En este caso, seleccione la cuenta de reconocimiento de consumo.</li></ul><p>Cuando se contabiliza la factura, el importe del consumo se contabiliza en la cuenta de aplazamiento de consumo especificada. Estos campos no están disponibles para artículos de servicio.</p> |
| Cuenta de reconocimiento | Especifique el número de la cuenta de reconocimiento de consumo. |
| Cuenta de reconocimiento inicial | <p>Especifique la cuenta para el importe de reconocimiento de consumo inicial. El valor predeterminado es el de la página **Valores predeterminados de aplazamiento**.</p><p>Este campo está disponible sólo cuando el campo **Método de publicación aplazada** se establece en **Ganancias y perdidas** en la página **Parámetros de aplazamiento de ingresos y gastos**.</p> |
| Cuenta de contrapartida de reconocimiento | <p>Especifique la cuenta para el importe de reconocimiento de consumo de contrapartida. El valor predeterminado es el de la página **Valores predeterminados de aplazamiento**.</p><p>Este campo está disponible sólo cuando el campo **Método de publicación aplazada** se establece en **Ganancias y perdidas** en la página **Parámetros de aplazamiento de ingresos y gastos**.</p> |
| **Programar** | |
| Tipo de programación | <p>Seleccione el tipo de programación de aplazamiento: **Lineal** (predeterminado) o **Basado en eventos**.</p><p>Las opciones que aparecen en la página se basan en el tipo de programación de aplazamiento que seleccione.</p><p>Si la plantilla predeterminada está configurada en la página **Valores predeterminados de aplazamiento** para la línea de transacción, el tipo de programación de aplazamiento se basa en el tipo de plantilla que se selecciona.</p> |
| **Programación: lineal** | |
| Consolidar los períodos anteriores | <p>Especifique si quiere consolidar las líneas de programación de aplazamiento para períodos anteriores:</p><ul><li>**Sí**: consolidar las líneas de programación de aplazamiento para períodos anteriores.</li><li>**No**: no consolidar las líneas de programación de aplazamiento para períodos anteriores.</li></ul><p>El valor predeterminado es el de la página **Parámetros de aplazamiento de ingresos y gastos**.</p> |
| Igual por periodo | <p>Especifique si el número de días en cada período es igual o varía según el período:</p><ul><li>**Sí**: cada período tiene el mismo número de días.</li><li>**No**: los períodos no tienen el mismo número de días.</li></ul><p>Cuando esta opción se establece en **No**, el número de días de un período se considera cuando se calcula la cantidad en cada período para una programación de aplazamiento.</p><p>El valor predeterminado es el de la página **Parámetros de aplazamiento de ingresos y gastos**.</p> |
| Programación a partir de plantilla | <p>Especifique si la programación de aplazamiento se crea en base a una plantilla o a una fecha de finalización:</p><ul><li>**Sí**: la programación de aplazamiento se crea en base a una plantilla.</li><li>**No**: la programación de aplazamiento se crea en base a una fecha de finalización.</li></ul> |
| Plantilla | Seleccione la plantilla de aplazamiento. |
| Fecha de inicio de anulación | <p>Especifique si desea reemplazar la fecha de inicio:</p><ul><li>**Sí**: reemplace la fecha de inicio con la fecha que introduzca en el campo **Fecha de inicio**.</li><li>**No**: la fecha de inicio es la regla de **Fecha de inicio de aplazamiento predeterminada** que se aplica a la fecha de la factura que se especifica en la página **Contabilización de factura**. Esta regla puede establecerse en la página **Parámetros de aplazamiento de ingresos y gastos**.</li></ul> |
| Fecha de inicio de aplazamiento | Especifique la fecha inicial del aplazamiento. La fecha de transacción es el valor predeterminado. |
| Fecha de finalización de aplazamiento | <p>La fecha final del aplazamiento.</p><p>Esta fecha se calcula automáticamente en función de la plantilla de aplazamiento. Si no se selecciona ninguna plantilla, debe introducir manualmente la fecha.</p> |
| **Programación: basada en eventos** | |
| Plantilla | <p>Seleccione la plantilla basada en eventos. Este campo es opcional.</p><p>Si selecciona una plantilla, los valores de la plantilla reemplazan todos los datos basados en eventos y las líneas de eventos.</p> |
| Tipo de asignación | <p>Seleccione el tipo de asignación para las líneas de eventos:</p><ul><li>**Importes variables**: debe introducirse un importe de asignación específico para cada línea.</li><li>**Importes iguales**: la cantidad se asigna por igual para cada línea.</li><li>**Porcentaje**: se asigna una cantidad en función del valor porcentual que se introduce para cada línea.</li><li>**Porcentaje completado**: se introduce un valor de finalización acumulativo para cada línea.</li><p>**Cantidad variable**: se introduce una cantidad de asignación específica para cada línea.</li></ul><p>**Nota:** si desea seleccionar **Porcentaje de terminación**, las fechas deben estar en orden ascendente.</p> |
| **Crear eventos independientes por unidad** | |
| Description | <p>Especifique si desea separar los eventos por unidad:</p><ul><li>**Sí**: separe las líneas de eventos para que haya una línea por cantidad.<p>Por ejemplo, hay tres líneas de eventos y la factura tiene una cantidad de cuatro. En este caso, la programación de aplazamiento resultante tiene 12 líneas.</p></li><li>**No**: no separe las líneas de evento.</li></ul> |
| Cuenta de vencimiento | <p>Seleccione la cuenta que se utiliza para las líneas vencidas reconocidas. Puede seleccionar la cuenta después de crear la programación de aplazamiento.</p><p>Si se establece una fecha de vencimiento para un evento, durante el proceso de reconocimiento, el importe del reconocimiento va a la cuenta de vencimiento en lugar de a la cuenta de reconocimiento.</p> |
| **Programación: líneas basadas en eventos** | |
| Description | Una descripción del evento. |
| Fecha de finalización de aplazamiento | <p>Seleccione la fecha final del evento.</p><p>**Nota:** si selecciona una fecha de finalización, el campo **Fecha de expiración** se borra. No puede usar una fecha de finalización y una fecha de expiración.</p> |
| Fecha de vencimiento | <p>Seleccione la fecha de expiración del evento.</p><p>**Nota:** si selecciona una fecha de finalización, el campo **Fecha de expiración** se borra. No puede usar una fecha de finalización y una fecha de expiración.</p> |
| Quantity | <p>Especifique la cantidad de asignación. El valor predeterminado para todas las líneas es **0** (cero). Si actualiza la cantidad, la cantidad total de todas las líneas debe ser igual o menor que la cantidad especificada para el artículo de línea en el pedido de ventas.</p><p>Este campo solo está disponible cuando el campo **Tipo de asignación** está establecido en **Cantidad variable**.</p><p>Si se cambia la cantidad del artículo de línea en el pedido de ventas para que sea menor que la cantidad original y se crea la factura, se crean menos líneas basadas en eventos. La cantidad total asignada no excede la cantidad que se especifica en el pedido de ventas o la programación de facturación de origen.</p> |
| Porcentaje de asignación | <p>Especifique el porcentaje de asignación. Si el campo **Tipo de asignación** se establece en **Porcentaje** o **Porcentaje de finalización**, puede introducir manualmente un porcentaje. De lo contrario, se calcula automáticamente.</p><p>Si el campo **Tipo de asignación** se establece en **Porcentaje**, el total de porcentajes debe sumar 100.</p> |
| Importe | <p>Especifique el importe de asignación. Si el campo **Tipo de asignación** se establece en **Importes variables** o **Porcentaje de finalización**, puede introducir manualmente un importe.</p><p>Si el campo **Tipo de asignación** se establece en **Porcentaje de finalización**, e introduce un importe aquí, el valor del **Porcentaje de finalización** se calcula automáticamente.</p><p>Debido al redondeo, es posible que el importe calculado no coincida exactamente con el que se introduce manualmente. Si necesita una cantidad exacta, establezca el campo **Tipo de asignación** en **Importes variables**.</p> |
| Porcentaje completado | <p>Especifique el porcentaje de finalización. El valor debe estar entre 0 (cero) y 100.</p><p>Este campo solo está disponible cuando el campo **Tipo de asignación** está establecido en **Porcentaje de terminación**.</p> |
| Importe completado | <p>El total calculado para todas las líneas en la programación de aplazamiento.</p><p>Si el campo **Tipo de asignación** se establece en **Porcentaje de finalización**, puede introducir manualmente un importe. En este caso, el valor del campo **Porcentaje de finalización** se calcula en función del importe que introduzca.</p><p>Debido al redondeo, es posible que el importe calculado no coincida exactamente con el que se introduce manualmente.</p><p>Este campo solo está disponible cuando el campo **Tipo de asignación** está establecido en **Porcentaje de terminación**.</p> |
| Reconocer al registrar | <p>Especifique si la línea se reconoce automáticamente tan pronto como se registra la transacción:</p><ul><li>**Seleccionado**: la línea se reconoce automáticamente tan pronto como se registra la transacción.</li><li>**Borrado**: la línea no se reconoce automáticamente tan pronto como se registra la transacción.</li></ul> |
| Cuenta de reconocimiento | <p>Especifique la cuenta de reconocimiento para el evento, si la cuenta difiere de la cuenta que se usa para toda la programación de aplazamiento.</p><p>Puede utilizar este campo junto con la opción **Reconocer al registrar**.</p> |
