---
title: Ingresos sin facturar
description: Este tema explica cómo configurar artículos y cuentas y usar la característica de ingresos no facturados en la facturación de suscripción.
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
ms.openlocfilehash: 4a5bd016649957d90876d4eb50c358cd9d6fba80
ms.sourcegitcommit: 836695c0e95d366ba993f34eee30f57191f356d8
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/21/2022
ms.locfileid: "8629459"
---
# <a name="unbilled-revenue"></a>Ingresos sin facturar

Este tema describe la característica de ingresos no facturados que le permite incluir los importes de las programaciones de facturación completas en el balance general. Estos importes se incluyen en una cuenta de ingresos no facturados y en una cuenta de contrapartida de ingresos no facturados, y el contrato se factura a plazos.

## <a name="set-up-unbilled-revenue"></a>Configurar ingresos sin facturar

Para configurar ingresos sin facturar, siga estos pasos.

- En la página **Parámetros de facturación periódica del contrato**, establezca los campos de la sección **Ingresos sin facturar**.
- La característica de ingresos no facturados se puede utilizar para artículos donde el campo **Tipo de artículo** se establezca como **Estándar**. También se puede utilizar para artículos aplazados. Para utilizar los ingresos no facturados con la funcionalidad a corto plazo, configure las opciones a corto plazo en la página **Parámetros de facturación periódica del contrato**.

Para configurar artículos para utilizar ingresos sin facturar, siga estos pasos.

1. En la página **Configuración de ingresos sin facturar**, en la pestaña **Artículos**, seleccione **Agregar**.
2. En la nueva línea, en el **Código de artículo**, seleccione el código del artículo.
3. En el campo **Relación de artículo**, seleccione la relación de artículo.
4. Repita estos pasos para agregar más líneas.
5. Seleccione **Guardar**.

Para configurar artículos y las cuentas de ingresos sin facturar, siga estos pasos.

1. En la página **Configuración de ingresos sin facturar**, en la pestaña **Cuentas**, seleccione **Agregar**.
2. En la nueva línea, en el **Código de artículo**, seleccione el código del artículo.
3. En el campo **Relación de artículo**, seleccione la relación de artículo.
4. Seleccione las cuentas para ingresos no facturados, descuento sin facturar y contrapartida de ingresos sin facturar. Para utilizar las cuentas a corto plazo, debe configurar el campo **Método de no facturado a corto plazo** a **Períodos de propagación** o **Año fijo** en la página **Parámetros de facturación periódica del contrato**.
5. Repita estos pasos para agregar más líneas.
6. Seleccione **Guardar**.

## <a name="use-unbilled-revenue"></a>Utilizar ingresos sin facturar

1. En la página **Todas las programaciones de facturación**, cree una programación de facturación.
2. Si el artículo aún no está configurado para usar ingresos sin facturar, seleccione la casilla **Ingresos no facturados** en la línea de programación de facturación.
3. Establezca la opción **Ingresos sin facturar** en **Sí**. A continuación, revise y edite las cuentas de ingresos no facturados, descuentos y contrapartida de ingresos sin facturar si es necesario.
4. En la programación de facturación, en **Procesamiento de ingresos sin facturar**, seleccione **Crear movimiento de diario** para crear el movimiento del diario inicial para ingresos sin facturar. Este paso debe completarse antes de que se facture la programación de facturación.
5. Después de crear el movimiento de diario inicial, seleccione **Generar factura** para crear pedidos de venta y registrar las facturas para las programaciones de facturación.
6. Después de registrar las facturas, puede revisar la información de auditoría en la pestaña **Renovaciones** de la página **Todas las programaciones de facturación**.

### <a name="milestone-billing"></a>Facturación por hitos

La facturación por hitos funciona con ingresos no facturados en las siguientes condiciones:

- Si el artículo principal del hito no está facturado (la casilla **Ingresos sin facturar** está seleccionada) y se facturan artículo secundarios del hito (la casilla **Ingresos sin facturar** está desactivada), se deben especificar las fechas de inicio y finalización del artículo principal. Estas fechas se utilizan para crear el movimiento de diario inicial.
- Si el artículo principal del hito no está facturado (la casilla **Ingresos sin facturar** está desactivada) y se facturan artículos secundarios del hito (la casilla **Ingresos sin facturar** está activada), se debe especificar la fechas de finalización solo para los artículos secundarios para los que dese crear el movimiento de diario inicial.

Cada artículo secundario del hito se puede procesar por separado. Las fechas de finalización se pueden especificar cuando esté listo para crear el movimiento de diario inicial.

> [!NOTE]
> Si ya se ha creado el movimiento de diario inicial para el artículo principal o los artículos secundarios del hito, o si se ha creado una factura, las fechas de inicio y finalización no se pueden editar.

### <a name="unbilled-revenue-with-straight-line-deferrals"></a>Ingresos no facturados con aplazamientos lineales

Para usar ingresos no facturados con programaciones de aplazamiento lineales, siga estos pasos.

1. En la página **Todas las programaciones de facturación**, cree una programación de facturación.
2. Agregue un artículo a las líneas a la programación de facturación.
3. Seleccione **Aplazamientos** para la línea.
4. En la página **Aplazamiento de transacción**, siga estos pasos:

    1. Establezca la opción **Aplazado** en **Sí**.
    2. Cambie las cuentas según necesite.
    3. En la sección **Programación**, seleccione **Lineal** y edite otros valores según sus necesidades.
    4. Seleccione **Aceptar**.

5. Seleccione **Ingresos sin facturar** para la línea y luego siga estos pasos:

    1. Establezca la opción **Ingresos sin facturar** en **Sí**.
    2. Seleccione las cuentas que desea usar para los ingresos, descuentos y contrapartida de ingresos.

6. En la programación de facturación, en **Procesamiento de ingresos sin facturar**, seleccione **Crear movimiento de diario**. Como alternativa, utilice la página **Procesamiento masivo de ingresos sin facturar** para crear el movimiento de diario.
7. Se crea la programación de aplazamiento. Puede revisar los detalles en la página **Todas las programaciones de aplazamiento**. Después de crear la programación de aplazamiento, puede editar varios valores para el artículo de línea de la programación de facturación. Por ejemplo, puede editar el precio unitario, la cantidad o las fechas.

### <a name="unbilled-revenue-with-event-based-deferrals"></a>Ingresos sin facturar con aplazamientos basados en eventos

Para usar ingresos no facturados con programaciones de aplazamiento basadas en eventos, siga estos pasos.

1. En la página **Todas las programaciones de facturación**, cree una programación de facturación.
2. Agregue un artículo a las líneas a la programación de facturación.
3. Seleccione **Aplazamientos** para la línea.
4. En la página **Aplazamiento de transacción**, siga estos pasos:

    1. Establezca la opción **Aplazado** en **Sí**.
    2. Cambie las cuentas según necesite.
    3. En la sección **Programación**, seleccione **Basada en eventos**, **Plantilla**, **Tipo de asignación** y **Cuenta de vencimiento**.
    4. Seleccione **Aceptar**.

5. Seleccione **Ingresos sin facturar** para la línea y luego siga estos pasos:

    - Establezca la opción **Ingresos sin facturar** en **Sí**.
    - Seleccione las cuentas que desea usar para los ingresos, descuentos y contrapartida de ingresos.

6. En la programación de facturación, en **Procesamiento de ingresos sin facturar**, seleccione **Crear movimiento de diario**. Como alternativa, utilice la página **Procesamiento masivo de ingresos sin facturar** para crear el movimiento de diario.
7. Se crea la programación de aplazamiento. Puede revisar los detalles en la página **Todas las programaciones de aplazamiento**. Después de crear la programación de aplazamiento, puede editar varios valores para el artículo de línea de la programación de facturación. Por ejemplo, puede editar el precio unitario, la cantidad o las fechas. La programación de aplazamiento se vuelve a calcular en función de los nuevos valores.

Las distribuciones se recalculan en función del tipo de asignación seleccionado (**Porcentaje**, **Porcentaje de finalización** o **Iguales importes**). Para el tipo de asignación **Importes variables**, la distribución se recalcula en función del porcentaje equivalente al valor inicial del evento. Por ejemplo, el precio unitario original es 100,00 $ y el porcentaje del valor inicial es 55,00 $ (55 por ciento). Si el precio unitario cambia a 200,00 $, la cantidad variable del evento se convierte en 110,00 $ (sigue siendo el 55 por ciento).

> [!NOTE]
> Si se han reconocido líneas de programación aplazadas, el artículo de línea de la programación de facturación no se puede editar. Para editar el artículoi de línea, primero debe invertir las líneas reconocidas. Entonces podrá actualizarse la línea de programación de facturación.

### <a name="unbilled-revenue-and-top-billing"></a>Ingresos sin facturar y facturación principal

Se ingresa una programación de facturación para tres años y las facturas se facturan anualmente durante un período de tres años. El importe del contrato total se registra en la cuenta de ingresos no facturados a partir de la cual se crean las facturas anuales. La cuenta de contrapartida es la cuenta de ingresos o de ingresos diferidos.

Tenga en cuenta que la facturación principal y los ingresos sin facturar no funcionan juntos, porque pueden ocurrir problemas de conciliación en contabilidad general. Por ejemplo, en la página **Configuración del grupo de artículos**, el grupo de artículos A está configurado para que el campo **Número de líneas superiores** se establezca en **2**. En la página **Programaciones de facturación** se agregan tres artículos. Los tres artículos pertenecen al grupo de artículos A. Cuando se crea el movimiento de diario inicial para la función de ingresos no facturados, el importe de los tres artículos se procesa en la cuenta no facturada. Cuando se crea la factura para la programación de facturación, solo se incluyen los importes de los dos artículos principales. Por tanto, el importe de la factura no coincide con el importe que se procesó en la cuenta de ingresos no facturados y se producen problemas de conciliación en la contabilidad general.

Si desea utilizar los ingresos no facturados, deje la página **Configuración del grupo de artículos** en blanco, o configure todos los grupos de artículos para que el campo **Número de líneas superiores** se establezca en **0** (cero). Si desea utilizar la facturación superior, no hay acciones de ingresos sin facturar disponibles.

### <a name="examples"></a>Ejemplo

A partir de la versión 10.0.27, se introduce una nueva cuenta cuando se utilizan ingresos sin facturar. Cuando se registra el proceso inicial **Crear movimiento de diario**, el crédito se realiza en una nueva cuenta de contrapartida de ingresos sin facturar. Esta cuenta se usa en lugar de la cuenta de ingresos, porque el mismo valor debe revertirse cuando se factura la programación de facturación. Si se producen diferencias de tipo de cambio o de redondeo, los importes que se calculan durante el proceso **Generar factura** pueden ser diferentes. Este comportamiento garantiza que el importe neto de las cuentas sea 0 (cero).

Este ejemplo muestra cómo utilizar los ingresos sin facturar para reconocer el importe total de un contrato en el balance general como ingresos no facturados. El otro lado del movimiento es la contrapartida de ingresos sin facturar. Cuando usted factura al cliente, los ingresos sin facturar y la contrapartida de ingresos sin facturar se invierten. El reconocimiento de ingresos ocurrirá en el momento de la facturación o de acuerdo con la programación de reconocimiento de aplazamiento que se configuró.

#### <a name="assumptions"></a>Supuestos

- El 1 de enero del año en curso, un cliente firma un contrato de tres años por 390 $.
- El contrato incluye dos partes: licencias y un contrato de mantenimiento.
- El precio de venta de la licencia es 300 $, y se facturarán al cliente 100 $ el 1 de enero de cada año de contrato. El precio de la licencia de 300 $ se tomará como ingresos cuando se firme el contrato.
- El precio de venta de la cuota de mantenimiento es 90 $, y se facturarán al cliente 30 $ el 1 de enero de cada año de contrato. La cuota de mantenimiento de 90 $ se aplazará y se reconocerán 2,50 $ cada mes de la vigencia del contrato.
- Se facturarán al cliente 130 $ al inicio (1 de enero) de cada uno de los tres años del contrato.

#### <a name="steps"></a>Pasos

1. Configure los dos artículos despachados como artículos sin facturar. Utilice la página **Configuración de ingresos sin facturar** para configurar los artículos y las cuentas que usan ingresos sin facturar.
2. En este ejemplo, la cuota de mantenimiento es aplazada. El artículo requiere una plantilla de aplazamiento, que se configura en la página **Plantillas de aplazamientos**. La plantilla tiene una frecuencia del período **Mensual** y una duración del período de reconocimiento de 36 meses. Por lo tanto, los ingresos mensuales son 2,50 $.
3. En la página **Artículos aplazados de forma predeterminada**, configure el campo **Cuota de mantenimiento** como **Artículo aplazable**. Este paso y el siguiente harán que el artículo de la cuota de mantenimiento se aplace cuando se venda o se incluya en una programación de facturación.
4. Seleccione **Valores predeterminados de aplazamiento** \> **Plantilla** y agregue el artículo para la cuota de mantenimiento y la plantilla lineal del paso 2. El artículo de cuota de mantenimiento estará ligada a una programación de aplazamiento de 36 meses.
5. Cree una programación de facturación que incluya los dos artículos no facturados. La programación de facturación para el contrato se configura con los artículos siguientes:

    | Elemento | Fecha inicial | Fecha final | Importe | Frecuencia de facturación | Artículo de aplazamiento | Ingresos sin facturar | Description |
    |---|---|---|---|---|---|---|---|
    | Licencia | 1 de enero, CY | 31 de diciembre CY+2 | 100,00 $ | Anual | No | Sí | Se facturarán al cliente 100,00 $ anuales. El total de 300,00 $ se registrará por adelantado como ingresos no facturados en el balance de situación y como ingresos en pérdidas y ganancias. Cada factura reducirá el importe sin facturar. |
    | Mantenimiento | 1 de enero, CY | 31 de diciembre CY+2 | 30,00 $ | Anual | Sí | Sí | Se facturarán al cliente 30,00 $ anuales. El total de 90,00 $ se registrará por adelantado como ingresos no facturados e ingresos aplazados en pérdidas y ganancias. Cada factura reducirá el importe sin facturar. Los ingresos aplazados se reconocerán mensualmente durante 36 meses. |

6. En la página **Todas las programaciones de facturación**, utilice el proceso **Crear movimiento de diario** para registrar el valor del contrato en el balance de situación como ingresos no facturados.

Se crean dos asientos de diario, uno para cada línea en la programación de facturación.

| Cuenta de ingresos sin facturar | Cuenta de contrapartida de ingresos sin facturar | Importe de débito | Importe de crédito |
|---|---|---|---|
| Cuenta de ingresos sin facturar | | 300,00 $ | |
| | Cuenta de contrapartida de ingresos sin facturar | | 300,00 $ |

| Cuenta de ingresos sin facturar | Ingresos diferidos | Importe de débito | Importe de crédito |
|---|---|---|---|
| Cuenta de ingresos sin facturar | | 90,00 $ | |
| |Ingresos de mantenimiento diferidos | | 90,00 $ |

El primer asiento de diario se registra en una cuenta de contrapartida de ingresos sin facturar y el segundo se registra en una cuenta de ingresos diferidos. Si la línea de facturación tiene ingresos sin facturar e ingresos diferidos, se utiliza la cuenta de ingresos diferidos, no la contrapartida de ingresos sin facturar. El contrato requiere que la factura para el cliente se cree al comienzo de cada año. Utilice el proceso **Generar factura** para crear la factura. Cuando se crea la factura, se crean los siguientes asientos de diario.

| Cuenta principal | Cuenta de ingresos sin facturar | Importe de débito | Importe de crédito |
|---|---|---|---|
| Contrapartida de ingresos sin facturar | | 100,00 $ | |
| | Cuenta de ingresos sin facturar | | 100,00 $ |
| Clientes | | 100,00 $ | |
| | Cuenta de ingresos | | 100,00 $ |

| Cuenta principal | Cuenta de ingresos sin facturar | Importe de débito | Importe de crédito |
|---|---|---|---|
| Cuenta de ingresos de mantenimiento aplazados | | 30,00 $ | |
| | Cuenta de ingresos sin facturar | | 30,00 $ |
| Clientes | | 30,00 $ | |
| | Cuenta de ingresos de mantenimiento aplazados | | 30,00 $ |

Este mismo asiento de diario se creará con las facturas que se registren al comienzo de los próximos dos años. El importe neto de la cuenta de ingresos diferidos será 0 (cero), ya que no existen redondeos ni diferencias de tipo de cambio. Los ingresos diferidos deben revertirse exactamente como se abonaron durante el proceso **Crear movimiento de diario**. Dado que los ingresos siguen siendo diferidos y se reconocerán más adelante, el abono a la cuenta de ingresos diferidos se vuelve a realizar.

En el último paso, se crea el movimiento de diario de reconocimiento cada mes para reconocer los ingresos de la cuota de mantenimiento diferidos. El movimiento de diario se puede crear utilizando la página **Procesamiento de reconocimiento**. Alternativamente, se puede crear seleccionando **Reconocer** para las líneas en las páginas **Programación de aplazamientos**.

| Cuenta de ingresos aplazados | Cuenta de ingresos | Importe de débito | Importe de crédito |
|---|---|---|---|
| Ingresos de mantenimiento diferidos | | 2,50 $ | |
| | Ingresos de mantenimiento | | 2,50 $ |

Este movimiento de diario se creará cada vez que se ejecute el proceso de reconocimiento para este artículo diferido (un total de 36 veces).

#### <a name="short-term-fixed-year"></a>A corto plazo: Año fijo

Pude utilizar los ingresos no facturados junto con la funcionalidad a corto plazo configurando el campo **Método de no facturado a corto plazo** en la página **Parámetros de facturación periódica del contrato**. El siguiente ejemplo muestra los cálculos que se realizan cuando los ingresos sin facturar se utilizan junto con el método de no facturado a corto plazo **Año fijo**.

Se crea una programación de facturación que tiene los siguientes criterios:

- **Fecha de inicio:** 1 de junio de 2020
- **Fecha de finalización:** 31 de diciembre de 2021
- **Precio unitario:** 100 $
- **Frecuencia:** Mensual

En la página **Todas las programaciones de facturación**, se crea el movimiento de diario inicial con el proceso **Crear movimiento de diario**. Los importes actuales a corto y largo plazo se calculan de la siguiente manera:

- **Importe actual de ingresos no facturados a corto plazo:** 700 $
- **Importe actual de ingresos no facturados a largo plazo:** 1200 $

La factura se crea para el período de facturación del 1 de junio de 2020 al 30 de noviembre de 2020. Los importes actuales a corto y largo plazo se calculan de la siguiente manera:

- **Importe actual de ingresos no facturados a corto plazo:** 100 $
- **Importe actual de ingresos no facturados a largo plazo:** 1200 $

La factura se crea para el período de facturación del 1 de diciembre de 2020 al 31 de diciembre de 2020. Los importes actuales a corto y largo plazo se calculan de la siguiente manera:

- **Importe actual de ingresos no facturados a corto plazo:** 1200 $
- **Importe actual de ingresos no facturados a largo plazo:** 0 $

#### <a name="short-term-rolling-periods"></a>Corto plazo: Períodos móviles

Pude utilizar los ingresos no facturados junto con la funcionalidad a corto plazo configurando el método de no facturado a corto plazo en la página **Parámetros de facturación periódica del contrato**. El siguiente ejemplo muestra los cálculos que se realizan cuando los ingresos sin facturar se utilizan junto con el método de no facturado a corto plazo **Periodos móviles**.

Se crea una programación de facturación que tiene los siguientes criterios:

- **Fecha de inicio:** 1 de junio de 2020
- **Fecha de finalización:** 31 de diciembre de 2021
- **Precio unitario:** 100 $
- **Frecuencia:** Mensual

En la página **Todas las programaciones de facturación**, se crea el movimiento de diario inicial con el proceso **Crear movimiento de diario**. Los importes actuales a corto y largo plazo se calculan de la siguiente manera:

- **Importe actual de ingresos no facturados a corto plazo:** 1200 $
- **Importe actual de ingresos no facturados a largo plazo:** 700 $

La factura se crea para el período de facturación del 1 de junio de 2020 al 30 de noviembre de 2020. Los importes actuales a corto y largo plazo se calculan de la siguiente manera:

- **Importe actual de ingresos no facturados a corto plazo:** 1200 $
- **Importe actual de ingresos no facturados a largo plazo:** 100 $

La factura se crea para el período de facturación del 1 de diciembre de 2020 al 31 de diciembre de 2020. Los importes actuales a corto y largo plazo se calculan de la siguiente manera:

- **Importe actual de ingresos no facturados a corto plazo:** 1200 $
- **Importe actual de ingresos no facturados a largo plazo:** 0 $

### <a name="items-with-revenue-allocation"></a>Artículos con asignación de ingresos

Dos artículos que tienen diferentes frecuencias de facturación se agregan a un programa de facturación. Ambos utilizan ingresos no facturados y son artículos aplazables.

- **Número de artículo 1000:** Surface Pro 128GB

    - **Frecuencia de facturación:** Una vez
    - **Precio unitario:** 1500 $
    - **Precio de venta individual:** 1600 $
    - **Ingresos del contrato:** 1465,26 $

- **Número de artículo S0021:** Seguro que se vende junto con el artículo número 1000

    - **Frecuencia de facturación:** Mensual durante 12 meses
    - **Precio unitario:** 20 $ por mes
    - **Precio de venta individual:** 25 $
    - **Ingresos del contrato:** 264,74 $

Dado que ambos artículos usan ingresos sin facturar y asignación de ingresos, el importe total del contrato en la línea de renovación es 0 (cero). La columna **Ingresos del contrato** se agrega la columna y muestra el importe de ingresos del contrato.

La siguiente tabla muestra el movimiento de diario inicial para los artículos y la factura.

| Cuenta de ingresos sin facturar | Cuenta de ingresos aplazados | Importe de débito | Importe de crédito |
|---|---|---|---|
| **Movimiento de diario del artículo 1000** | | | |
| Cuenta de ingresos sin facturar de débito (401250) | | 1465,26 $ | |
| | Cuenta de ingresos aplazados de crédito (250600) | | 1465,26 $ |
| **Movimiento de diario del artículo 0021** | | | |
| Cuenta de ingresos sin facturar de débito (401250) | | 274,74 $ | |
| | Cuenta de ingresos aplazados de crédito (250600) | | 274,74 $ |
| **Factura** | | | |
| | Cuenta de ingresos sin facturar de crédito | | 1465,26 $ |
| | Cuenta de ingresos sin facturar de crédito | | 274,74 $ |
| Cuenta de débito de clientes (130100) | | 1488,16 $ | |

#### <a name="changes-to-the-billing-schedule-line-billing-detail-line-or-revenue-allocation"></a>Cambios en la línea de programación de facturación, la línea de detalle de facturación o la asignación de ingresos

Cuando se cambia el precio unitario o la cantidad, se debe actualizar el importe de ingresos del contrato para cada artículo que forma parte de la asignación de ingresos. Por lo tanto, se vuelve a calcular el movimiento de diario.

Por ejemplo, el precio unitario del artículo 1000 cambia de 1500 $a 1600 $. En este caso, el importe de ingresos del contrato se recalcula automáticamente como 1549,47 $. Los ingresos del contrato para el artículo S0021 se recalculan como 290,53 $.

Cuando se confirma el cambio, los movimientos de diario iniciales para ambos artículos se revierten y se crean nuevos movimientos de diario:

- **Artículo 1000:** Se revierte el movimiento de diario inicial original de 1465,26 $. Se crea un nuevo movimiento de diario por 1549,47 $.
- **Artículo S0021:** Se revierte el movimiento de diario inicial original de 274,74 $. Se crea un nuevo movimiento de diario por 290,53 $.

#### <a name="termination"></a>Finalización

El artículo S0021 tiene una fecha de inicio en enero de 2020 y una fecha de finalización en diciembre de 2020, pero finaliza en junio de 2020. El importe de ingresos del contrato para ambos artículos debe recalcularse:

- **Artículo 1000:** Los ingresos del contrato se recalculan como 1567,67 $.
- **Artículo S0021:** Los ingresos del contrato se recalculan como 124,00 $.

Se crea un movimiento de diario de ajuste para la línea que se termina. El moviento de diario de la línea que pertenece al mismo número de disposición de varios elementos (MEA) se invierte y se crea un nuevo movimiento de diario:

- **Artículo 1000:** Se revierte el movimiento de diario inicial original de 1465,26 $. Se crea un movimiento de diario de ajuste por 1549,47 $.
- **Artículo S0021:** Se revierte el movimiento de diario inicial original de 274,74 $. Se crea un nuevo movimiento de diario por 124,00 $.
