---
title: Aplazamientos de ingresos y gastos en la facturación de suscripción
description: Este tema explica cómo configurar los aplazamientos de ingresos y gastos en la facturación de suscripción.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: 5ff8d2f4663c53bf6dece1ef9af6609d5f0c5b50
ms.sourcegitcommit: cf7d4af11bf85638ee831a28ea5ee1a1e041a675
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/04/2022
ms.locfileid: "8544536"
---
# <a name="revenue-and-expense-deferrals-in-subscription-billing"></a>Aplazamientos de ingresos y gastos en la facturación de suscripción

Este tema explica cómo configurar y usar los aplazamientos de ingresos y gastos en la facturación de suscripción. Las programaciones de aplazamientos siempre se basan y dependen de un documento de origen subyacente o una programación de facturación. Debido a que se crean en función de los valores predeterminados, no se pueden introducir ni crear por separado.

El proceso de configuración y uso de aplazamientos de ingresos y gastos ocurre en varias páginas:

- En la página **Parámetros de aplazamiento de ingresos y gastos**, puede definir las preferencias de la empresa.
- En la página **Valores predeterminados de aplazamiento**, puede configurar las cuentas y plantillas predeterminadas que se utilizan para los programas de aplazamiento.
- En las páginas **Plantillas de aplazamiento** y **Plantillas de aplazamiento basadas en eventos**, puede definir las plantillas que se utilizan para las programaciones de aplazamiento.
- En la página **Todas las programaciones de aplazamiento**, puede ver y editar cualquier programación de aplazamiento.

Los aplazamientos de ingresos y gastos se pueden utilizar junto con la facturación de contratos periódicos.

## <a name="revenue-and-expense-deferral-parameters"></a>Parámetros de aplazamientos de ingresos y gastos

La página **Parámetros de aplazamiento de ingresos y gastos** contiene los siguientes campos.

| Campo | Description |
|---|---| 
| Pestaña **Programación** | |
| Igual por periodo | <p>Especifique si se utiliza el número de días de un período cuando se calcula el importe por período para una programación de aplazamiento:</p><ul><li>**Sí**: el importe de cada período es el mismo, independientemente del número de días del período. Los períodos parciales (como los períodos al principio o al final de una programación de aplazamiento) se prorratearán.</li><li>**No**: el importe se calcula en función del número de días de cada periodo.</li></ul><p>Puede anular esta configuración en el nivel de transacción.</p> |
| Opción de aplazamiento de descuento de ventas | <p>Especifique si se crean programaciones de aplazamiento separadas para el descuento y los importes de la orden de venta:</p><ul><li>**Programación independiente de descuento**: el importe del descuento se mantiene separado del importe de los ingresos.<p>En este caso, se crean dos programaciones de aplazamiento cuando se crea y luego se registra un pedido de ventas. Los importes de descuento e ingresos se contabilizarán en diferentes cuentas de aplazamiento.</p></li><li>**Combinar descuento con ingresos**: el importe del descuento se combina con el importe de los ingresos. Se crea una programación de aplazamiento y tanto el importe del descuento como el importe de los ingresos se contabilizan en la misma cuenta de aplazamiento.<p>En este caso, se crea una programación de aplazamiento cuando se crea y luego se registra un pedido de ventas. El importe del descuento y el importe de los ingresos se contabilizan en la misma cuenta de aplazamiento.</p></li></ul><p>**Nota:** para aplicar descuentos a artículos que utilizan la función de ingresos no facturados, seleccione la opción **Programación independiente para descuento**. Los descuentos se pueden aplicar a todos los artículos, independientemente de si se utiliza la función de ingresos no facturados. Si está seleccionada la opción **Combinar descuentos con ingresos**, los descuentos no se pueden aplicar a los artículos que utilizan la función de ingresos no facturados.</p> |
| Opción de aplazamiento de descuento de compra | <p>Seleccione si se crean programaciones de aplazamiento separadas para los importes de descuento y pedidos de ventas:</p><ul><li>**Programación independiente de descuento**: el importe del descuento se mantiene separado del importe de los gastos.<p>En este caso, se crean dos programaciones de aplazamiento cuando se crea y luego se registra un pedido de compra. Los importes de descuento y gasto se contabilizarán en diferentes cuentas de aplazamiento.</p></li><li>**Combinar descuento con ingresos**: el importe del descuento se combina con el importe de los gastos. Se crea una programación de aplazamiento y tanto el importe del descuento como el importe de los gastos se contabilizan en la misma cuenta de aplazamiento.<p>En este caso, se crea una programación de aplazamiento cuando se crea y luego se registra un pedido de compra. El importe del descuento y el importe de los gastos se contabilizan en la misma cuenta de aplazamiento.</p></li></ul> |
| Consolidar los períodos anteriores | <p>Especifique si se consolidan los repartos de aplazamiento de períodos anteriores:</p><ul><li>**Sí**: si la fecha de inicio del aplazamiento se encuentra en un período anterior a la fecha de la transacción, todos los importes hasta el período de la fecha de la transacción se combinan en una única línea de programación de aplazamiento.</li><li>**No**: los importes de todos los períodos se mantienen en líneas de aplazamiento separadas.<p>Si la fecha de inicio del aplazamiento se encuentra en el mismo período o en un período posterior a la fecha de la transacción, esta opción no tiene efecto.</p></li></ul><p>Esta configuración se puede actualizar en el nivel de transacción.</p> |
| Fecha predeterminada de inicio de aplazamiento | <p>Seleccione la regla que se utiliza para determinar la fecha de inicio de la programación de aplazamiento:</p><ul><li>**Fecha de transacción**: use la fecha de transacción como fecha de inicio.</li><li>**Comienzo del mes actual**: use el primer día del mes actual como fecha de inicio. Si la fecha de la transacción es el primer día de cualquier mes, el primer día del mes actual es la fecha de inicio.</li><li>**Comienzo del próximo mes**: use el primer día del próximo mes como fecha de inicio. La fecha de la transacción es el primer día, se usa la fecha de transacción. De lo contrario, se utiliza el primer día del mes siguiente.</li><li>**Regla de 15**: si la fecha de la transacción está entre el primero y el quince, utilice el primer día del mes actual como fecha de inicio. Si la fecha de la transacción es el decimosexto día o posterior del próximo mes, use el primer día del próximo mes como fecha de inicio.</li></ul><p>Puede actualizar esta configuración en el nivel de transacción.</p> |
| Método de aplazamiento a corto plazo | <p>Seleccione el método de aplazamiento a corto plazo: **Ninguno**, **Períodos móviles** o **Año fijo**.</p><p>|
| Método de registro de aplazamiento | <p>Seleccione el método utilizado para crear transacciones aplazadas:</p><ul><li>**Balance de situación**: use el método de registro en el balance de situación para crear transacciones de aplazamiento.</li><li>**Ganancias y pérdidas**: use el método de registro de pérdidas y ganancias para crear transacciones de aplazamiento. Cuando se contabilizan las transacciones, puede revisar el asiento de la factura para ver las entradas adicionales que equilibran el reconocimiento inicial y los importes de compensación del reconocimiento.</li></ul> |
| Revertir ganancias y pérdidas en crédito | <p>**Nota:** este campo está disponible solo cuando el campo **Método de registro de aplazamiento** está configurado en **Ganancias y pérdidas**.</p><p>Especifique si los importes de ganancias y pérdidas se revierten cuando se aplica una reversión, rescisión o reembolso a una programación de facturación o un pedido de ventas:</p><ul><li>**Sí**: revierta los importes de pérdidas y ganancias y aplique un importe de ajuste de crédito a la programación de aplazamiento.<p>Si la reversión ocurre a la mitad de un período de facturación, los importes se prorratean.</p></li><li>**No**: no se crea una transacción de reversión para ganancias y pérdidas cuando se aplica una reversión, rescisión o reembolso a una programación de facturación o un pedido de ventas.</li></ul> |
| Pestaña **Reconocimiento** | |
| Registrar automáticamente los diarios generales | <p>Especifique si los asientos de diario creados por aplazamientos de ingresos y gastos se registran automáticamente:</p><ul><li>**Sí**: registre automáticamente los asientos de diario creados por aplazamientos de ingresos y gastos.<p>**Consejo:** seleccionando **Sí**, puede ayudar a evitar las incoherencias contables causadas por cambios manuales en los asientos.</p></li><li>**No**: no registre automáticamente los asientos de diario creados por aplazamientos de ingresos y gastos. Debe registrar manualmente todos los diarios.</li></ul> |
| Resumir diario de reconocimientos | <p>Especifique si los asientos de reconocimiento se consolidan de forma predeterminada:</p><ul><li>**Sí**: cree un único comprobante para todas las líneas de reconocimiento que tengan la misma fecha. Todas las líneas de un comprobante que tienen la misma cuenta se consolidan en una sola línea.</li><li>**No**: cree un asiento para cada línea de reconocimiento.</li></ul><p>Puede actualizar esta configuración en la página **Procesamiento de reconocimiento**.</p> |
| Nombre predeterminado de diario | Seleccione el nombre del diario para los diarios que se crean a partir de procesos de aplazamiento de ingresos y gastos, como el procesamiento de reconocimiento. |
| Descripción de línea de diario de reconocimiento | <p>Seleccione la descripción que aparece en la descripción de la línea del asiento del diario:</p><ul><li>**Programar fechas de línea**: muestre las fechas de línea de programación en la descripción de la línea de diario.</li><li>**Detalles de la transacción de origen**: mostrar la información de la transacción de origen en la descripción de la línea del diario.<p>**Ejemplo:** USMF-0001, CIV-00839, Ingresos de software</p></li></ul> |
| Pestaña **Secuencias numéricas** | Utilice esta pestaña para establecer los valores predeterminados para las secuencias de números de arrendamiento. El asistente de generación de secuencias numéricas se utiliza para generar y asignar automáticamente secuencias numéricas. No tiene que cambiar la secuencia numérica a menos que desee realizar cambios manuales en las secuencias numéricas generadas. |
| Número de programación | El número que usa la secuencia para programaciones de aplazamiento. |

## <a name="deferral-templates"></a>Plantillas de aplazamientos

Utilice la página **Plantillas de aplazamiento** para definir plantillas lineales que se utilizan para programaciones de aplazamiento.

Estas son algunas de las ventajas de usar una plantilla:

* La duración del aplazamiento se calcula automáticamente.
* Permite programaciones de aplazamiento que tienen períodos en los que se omite el reconocimiento.
* Puede automatizar los aplazamientos asignando la plantilla a un producto, un grupo de productos, una categoría de productos, clientes o un grupo de clientes. La asignación de plantillas se realiza desde la página **Valores predeterminados de aplazamiento**.

Hay varias frecuencias de períodos disponibles para las plantillas: períodos diarios, mensuales o fiscales.

Las líneas de plantilla constan de un tipo (**Reconocido** u **Omitido**) y la duración del período. Las líneas omitidas tienen una cantidad de 0 (cero) en las líneas de programación de aplazamiento. Este comportamiento puede resultar útil si no desea reconocer los ingresos en todos los períodos.

### <a name="create-a-deferral-template"></a>Crear una plantilla de aplazamiento

Para crear una plantilla de aplazamiento, siga estos pasos.

1. En la página **Plantillas de aplazamiento**, seleccione **Nueva**.
2. En el campo **Plantilla**, introduzca un nombre.
3. En el campo **Descripción**, escriba una descripción.
4. En el campo **Frecuencia del período**, seleccione al frecuencia del período.
5. Seleccione **Agregar** para agregar una línea a la parte superior de la lista de líneas, o seleccione **Anexar** para agregar una línea al final de la lista.
6. En el campo **Tipo**, seleccione el tipo de periodo.
7. En el campo **Duración del período**, escriba la duración del período.
8. Repita los pasos del 5 al 7 para cada línea adicional que necesite.
9. Seleccione **Guardar**.

## <a name="deferral-defaults"></a>Valores predeterminados de aplazamiento

Utilice la página **Valores predeterminados de aplazamientos** para configurar cuentas de aplazamiento predeterminadas para artículos y para asignar plantillas predeterminadas a artículos aplazables. También puede configurar cuentas de aplazamientos para cargos y asignar plantillas a los cargos aplazables.

**Aplazar por artículo**

Para las transacciones que tienen un artículo (por ejemplo, pedidos de ventas), puede asignar cuentas y plantillas a artículos y clientes específicos. Estos ajustes se utilizarán como valores predeterminados cuando se aplace una transacción. Para que la transacción sea aplazable de forma predeterminada, debe configurar los artículos en la página **Elementos aplazables**.

**Aplazar por cuenta**

Para las transacciones que no tienen artículos (por ejemplo, diarios generales), puede especificar las cuentas de aplazamiento. Cuando estas cuentas se utilizan en una línea de transacción, la transacción se marca automáticamente como aplazada. La plantilla correspondiente y la cuenta de reconocimiento se asignarán a la línea de transacción.

**Todos los tipos de transacciones (por ejemplo, en las pestañas Pedido de ventas, Compras y Diario general)**

Las cuentas de la página son las cuentas principales que no tienen dimensiones financieras. Las dimensiones financieras de la cuenta de reconocimiento son del cliente o artículo, según su organización.

Cada línea de plantilla debe tener una plantilla lineal o una plantilla basada en eventos. No puede tener ambas.

### <a name="for-sales-orders"></a>Para pedidos de ventas

Para especificar los valores predeterminados de aplazamiento para pedidos de ventas, siga estos pasos.

1. En la pestaña **Pedido de ventas**, seleccione el tipo de aplazamiento.
2. Seleccione **Agregar** para agregar una línea.
3. En el campo **Código de artículo**, seleccione el código de artículo. El código de artículo determina cómo se aplican los valores predeterminados de aplazamiento.
4. Especifique cómo se aplica el código de artículo:

    * Si el campo **Código de artículo** está establecido en **Tabla** o **Grupo**, seleccione una relación de artículo en el campo **Relación de artículo**.
    * Si el campo **Código de artículo** está establecido en **Categoría**, seleccione la relación de categoría en **Relación de categoría**.
    * Si el campo **Código de artículo** está establecido en **Todos**, los valores predeterminados se aplican a todos los registros aplicables.

5. Especifique cómo se aplica el código de cuenta:

    * Si el campo **Código de cuenta** está establecido en **Tabla** o **Grupo**, seleccione una relación de cuenta en el campo **Relación de cuenta**.
    * Si el campo **Código de cuenta** está establecido en **Todos**, la cuenta se aplica a todos los registros.

6. En el campo **Cuenta principal**, seleccione la cuenta principal para el aplazamiento.
7. Si el campo **Método de publicación aplazada** está establecido en **Ganancias y perdidas**, seleccione la cuenta de ingresos inicial en el campo **Cuenta de ingresos inicial** y la cuenta de contrapartida de ingresos en el campo **Cuenta de contrapartida de ingresos**.
8. Si el campo **Método de aplazamiento a corto plazo** está establecido en **Períodos móviles** o **Año fijo**, seleccione la cuenta de aplazamiento a corto plazo en el campo **Cuenta de aplazamiento a corto plazo**.
9. Para una plantilla, puede seleccionar **Agregar** para agregar una línea.
10. En el campo **Código de artículo**, seleccione el código de artículo.
11. Especifique cómo se aplica el código de artículo:

    * Si el campo **Código de artículo** está establecido en **Tabla** o **Grupo**, seleccione una relación de artículo en el campo **Relación de artículo**.
    * Si el campo **Código de artículo** está establecido en **Categoría**, seleccione la relación de categoría en el campo **Relación de categoría**.
    * Si el campo **Código de artículo** está establecido en **Todos**, los valores predeterminados se aplican a todos los registros aplicables.

12. Especifique cómo se aplica el código de cuenta:

    * Si el campo **Código de cuenta** está establecido en **Tabla** o **Grupo**, seleccione una relación de cuenta en el campo **Relación de cuenta**.
    * Si el campo **Código de cuenta** está establecido en **Todos**, la cuenta se aplica a todos los registros aplicables.
    * Seleccione la plantilla lineal en el campo **Plantilla de línea recta** o la plantilla basada en eventos en el campo **Plantilla basada en eventos**.

13. Seleccione **Guardar**.

### <a name="for-purchase-orders"></a>Para pedidos de compra

Para especificar los valores predeterminados para los pedidos de compra, siga estos pasos.

1. En la pestaña **Compras**, seleccione el tipo de aplazamiento.
2. Seleccione **Agregar** para agregar una línea.
3. En el campo **Código de artículo**, seleccione el código de artículo.
4. Especifique cómo se aplica el código de artículo:

    * Si el campo **Código de artículo** está establecido en **Tabla** o **Grupo**, seleccione una relación de artículo en el campo **Relación de artículo**.
    * Si el campo **Código de artículo** está establecido en **Categoría**, seleccione la relación de categoría en el campo **Relación de categoría**.
    * Si el campo **Código de artículo** está establecido en **Todos**, los valores predeterminados se aplican a todos los registros aplicables.

5. Especifique cómo se aplica el código de cuenta:

    * Si el campo **Código de cuenta** está establecido en **Tabla** o **Grupo**, seleccione una relación de cuenta en el campo **Relación de cuenta**.
    * Si el campo **Código de cuenta** está establecido en **Todos**, la cuenta se aplica a todos los registros aplicables.

6. En el campo **Cuenta principal**, seleccione la cuenta principal para el aplazamiento.
7. Si el campo **Método de publicación aplazada** está establecido en **Ganancias y perdidas**, seleccione la cuenta de ingresos inicial en el campo **Cuenta de ingresos inicial** y la cuenta de contrapartida de ingresos en el campo **Cuenta de contrapartida de ingresos**.
8. Si el campo **Método de aplazamiento a corto plazo** está establecido en **Períodos móviles** o **Año fijo**, seleccione la cuenta de aplazamiento a corto plazo en el campo **Cuenta de aplazamiento a corto plazo**.
9. Para una plantilla, seleccione **Agregar** para agregar una línea. 
10. En el campo **Código de artículo**, seleccione el código de artículo.
11. Especifique cómo se aplica el código de artículo:

    * Si el campo **Código de artículo** está establecido en **Tabla** o **Grupo**, seleccione una relación de artículo en el campo **Relación de artículo**.
    * Si el campo **Código de artículo** está establecido en **Categoría**, seleccione la relación de categoría en el campo **Relación de categoría**.
    * Si el campo **Código de artículo** está establecido en **Todos**, los valores predeterminados se aplican a todos los registros aplicables.

12. Especifique cómo se aplica el código de cuenta:

    * Si el campo **Código de cuenta** está establecido en **Tabla** o **Grupo**, seleccione una relación de cuenta en **Relación de cuenta**.
    * Si el campo **Código de cuenta** está establecido en **Todos**, la cuenta se aplica a todos los registros aplicables.
    * Seleccione la plantilla lineal en el campo **Plantilla de línea recta** o la plantilla basada en eventos en el campo **Plantilla basada en eventos**.

13. Seleccione **Guardar**.

### <a name="for-general-journals"></a>Para diarios generales

Para especificar los valores predeterminados para las entradas de diarios generales, siga estos pasos.

1. Seleccione la pestaña **Diario general**.
2. Para un aplazamiento, seleccione **Agregar** para agregar una línea.
3. Si el campo **Método de aplazamiento a corto plazo** está establecido en **Períodos móviles** o **Año fijo**, seleccione la cuenta de aplazamiento a corto plazo en el campo **Cuenta de aplazamiento a corto plazo**.
4. En el campo **Cuenta de aplazamiento**, seleccione la cuenta de aplazamiento.
5. En el campo **Cuenta de reconocimiento**, seleccione la cuenta de reconocimiento.
6. Si el campo **Método de publicación aplazada** está establecido en **Ganancias y perdidas**, seleccione la cuenta de ingresos inicial en el campo **Cuenta de ingresos inicial** y la cuenta de contrapartida de ingresos en el campo **Cuenta de contrapartida de ingresos**.
7. Seleccione la plantilla lineal en el campo **Plantilla de línea recta** o la plantilla basada en eventos en el campo **Plantilla basada en eventos**.
8. Seleccione **Guardar**.

### <a name="for-free-text-invoices"></a>Para facturas de servicios

Para especificar los valores predeterminados de aplazamiento para facturas de servicios, siga estos pasos.

1. Seleccione la pestaña **Factura de servicios**.
2. Para un aplazamiento, seleccione **Agregar** para agregar una línea.
3. Especifique cómo se aplica el código de cuenta:

    * Si el campo **Código de cuenta** está establecido en **Tabla** o **Grupo**, seleccione una relación de cuenta en el campo **Relación de cuenta**.
    * Si el campo **Código de cuenta** está establecido en **Todos**, el código de cuenta se aplica a todos los registros aplicables.

4. En el campo **Cuenta de aplazamiento**, seleccione la cuenta de aplazamiento.
5. Si el campo **Método de aplazamiento a corto plazo** está establecido en **Períodos móviles** o **Año fijo**, seleccione la cuenta de aplazamiento a corto plazo en el campo **Cuenta de aplazamiento a corto plazo**.
6. En el campo **Cuenta de reconocimiento**, seleccione la cuenta de reconocimiento.
7. Si el campo **Método de publicación aplazada** está establecido en **Ganancias y perdidas**, seleccione la cuenta de ingresos inicial en el campo **Cuenta de ingresos inicial** y la cuenta de contrapartida de ingresos en el campo **Cuenta de contrapartida de ingresos**.
8. Seleccione la plantilla lineal en el campo **Plantilla de línea recta** o la plantilla basada en eventos en el campo **Plantilla basada en eventos**.
9. Seleccione **Guardar**.

### <a name="for-invoice-journals"></a>Para diarios de facturas

Para especificar los valores predeterminados para las entradas de diarios de facturas, siga estos pasos.

1. Seleccione la pestala **Diario de facturas**.
2. Para un aplazamiento, seleccione **Agregar** para agregar una línea.
3. Especifique cómo se aplica el código de cuenta:

    * Si el campo **Código de cuenta** está establecido en **Tabla** o **Grupo**, seleccione una relación de cuenta en el campo **Relación de cuenta**.
    * Si el campo **Código de cuenta** está establecido en **Todos**, el código de cuenta se aplica a todos los registros aplicables.

4. En el campo **Cuenta de aplazamiento**, seleccione la cuenta de aplazamiento.
5. Si el campo **Método de aplazamiento a corto plazo** está establecido en **Períodos móviles** o **Año fijo**, seleccione la cuenta de aplazamiento a corto plazo en el campo **Cuenta de aplazamiento a corto plazo**.
6. En el campo **Cuenta de reconocimiento**, seleccione la cuenta de reconocimiento.
7. Si el campo **Método de publicación aplazada** está establecido en **Ganancias y perdidas**, seleccione la cuenta de ingresos inicial en el campo **Cuenta de ingresos inicial** y la cuenta de contrapartida de ingresos en el campo **Cuenta de contrapartida de ingresos**.
8. Seleccione la plantilla lineal en el campo **Plantilla de línea recta** o la plantilla basada en eventos en el campo **Plantilla basada en eventos**.
9. Seleccione **Guardar**.

### <a name="items-that-are-deferred-by-default"></a>Elementos que se aplazan de forma predeterminada

Utilice la página **Elementos aplazados de forma predeterminada** para definir qué elementos se aplazan de forma predeterminada. Puede configurar los tipos de transacciones para las que se aplazarán los artículos. Puede especificar si se difiere un solo artículo o un grupo o categoría de artículos completos.

Al configurar artículos como aplazados, seleccione las cuentas y plantillas predeterminadas en la página **Valores predeterminados de aplazamiento**. Si no se seleccionan las cuentas y las plantillas, las líneas de transacción donde se ingresan esos elementos no se aplazarán.

Para los artículos que se aplazan según la categoría de ventas o compras a la que están asociados, la configuración de aplazamiento se basa en la categoría. Sin embargo, si la categoría no está seleccionada en el campo **Relación de categoría** se utiliza la configuración de aplazamiento de la categoría que tiene un rango más alto. Por ejemplo, puede agregar una categoría de ventas **Vídeo casero** pero no una categoría de ventas **Televisión**. Cuando agrega un elemento de aplazamiento que está asociado con la categoría **Televisión** categoría, la configuración de aplazamiento de **Vídeo casero** se utiliza para el artículo.

### <a name="set-up-deferred-items"></a>Configurar artículos aplazados

Para configurar artículos que se aplazan de forma predeterminada, siga estos pasos.

1. En la página **Artículos aplazados por defecto**, seleccione la pestaña que desee: **Pedido de ventas** o **Compras**.
2. Seleccione **Agregar** para agregar una línea.
3. En el campo **Código de artículo**, seleccione el código de artículo.
4. Especifique cómo se aplica el código de artículo:

    * Si el campo **Código de artículo** está establecido en **Grupo** o **Tabla**, seleccione una relación de artículo en el campo **Relación de artículo**.
    * Si el campo **Código de artículo** está establecido en **Categoría**, seleccione la relación de categoría en el campo **Relación de categoría**.

5. Repita los pasos del 2 al 4 para cada línea adicional que necesite.
6. Seleccione **Guardar**.

## <a name="deferred-charges"></a>Cargos aplazados

Utilice la página **Cargos aplazados** para definir qué cargos se aplazan de forma predeterminada.

> [!NOTE]
> * Actualmente, los cargos aplazables están disponibles solo para pedidos de venta.
> * Los cargos se pueden aplazar solo en el nivel de líneas. Para aplazar un cargo en el nivel de encabezado de pedido de ventas, puede configurar el cargo como un artículo aplazado en una línea separada del pedido de ventas.
> * Para aplazar un cargo de una factura de servicios, debe ingresar el cargo como una línea de factura aplazada separada.
> * Esta funcionalidad no está disponible para los cargos de soporte y la funcionalidad de división de ingresos.

### <a name="set-up-deferred-charges"></a>Configurar los cargos aplazados

Para configurar cargos aplazados, siga estos pasos.

1. En la página **Cargos aplazados**, seleccione **Agregar** para agregar una línea.
2. En el campo **Código de cargo**, seleccione el código de cargo.
3. En el campo **Relación de cargo**, seleccione la relación de cargo.
4. Repita los pasos del 1 al 3 para cada línea adicional que necesite.
5. Seleccione **Guardar**.

## <a name="event-based-deferral-templates"></a>Plantillas de aplazamiento basadas en eventos

Utilice la página **Plantillas de aplazamiento basadas en eventos** para definir plantillas de aplazamiento basadas en eventos que puede usar en transacciones de aplazamiento y asignarlas en la página **Valores predeterminados de aplazamiento**.

### <a name="create-an-event-based-template"></a>Crear una plantilla basada en eventos

Para crear una plantilla basada en eventos, siga estos pasos.

1. En la página **Plantillas de aplazamiento basadas en eventos**, seleccione **Nueva**.
2. En el campo **Plantilla**, especifique un nombre único para la plantilla.
3. En el campo **Descripción**, escriba una descripción.
4. En el campo **Tipo de asignación**, seleccione el tipo de asignación.

    * **Importe variable**: asigne un importe específico para cada línea que se introduce.
    * **Importe igual**: asigne el mismo importe para cada línea que se introduce. 
    * **Porcentaje**: asigne una cantidad que se base en el valor porcentual que se introduce para cada línea.
    * **Porcentaje completado**: asigne un valor de finalización acumulativo para cada línea que se introduce.
    * **Cantidad variable**: asigne una cantidad específica para cada línea que se introduce.

5. Establezca la opción **Crear eventos separados por unidad** en **Sí** si desea que cada línea de evento se divida equitativamente entre el número de unidades en la transacción de la factura. Establézcala en **No** si no desea dividir las líneas de eventos.
6. En el campo **Cuenta de expiración**, seleccione la cuenta de expiración.
7. Seleccione **Agregar** para agregar una línea a la parte superior de la lista de líneas, o seleccione **Anexar** para agregar una línea al final de la lista.
8. En el campo **Descripción**, introduzca una descripción del evento.
9. Si se estableció el **Tipo de asignación** en **Porcentaje**, especifique el porcentaje de asignación en el campo **Porcentaje de asignación**. El porcentaje debe estar entre 0 (cero) y 100. Si deja el campo **Porcentaje de asignación** en blanco, el porcentaje se considera 0. La suma de todos los porcentajes que se muestra en el campo **Porcentaje total** de la parte inferior de la página debe ser igual a 100.
10. En el campo **Meses hasta el vencimiento** especifique el número de meses en que el evento es válido. La fecha de vencimiento del aplazamiento de la transacción se introduce automáticamente en función de este valor.
11. Seleccione la casilla **Reconocer al registrar** para reconocer automáticamente los ingresos cuando se registra la transacción. Si deja la casilla sin marcar, los ingresos deben reconocerse manualmente.
12. En el campo **Cuenta de reconocimiento**, seleccione la cuenta de reconocimiento para el evento, si el evento usa una cuenta diferente a la programación de aplazamientos completa. Este campo se utiliza junto con la casilla **Reconocer al registrar**.
13. Repita los pasos del 7 al 12 para cada línea adicional que necesite.
14. Seleccione **Guardar**.
