---
title: Las transacciones entre la liquidación de contabilidad y el cierre de fin de año
description: Este tema proporciona información sobre las mejoras que afectan las liquidaciones del libro mayor y el cierre de fin de año del Libro mayor.
author: kweekley
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-31
ms.dyn365.ops.version: 10.0.25
ms.openlocfilehash: e18f77d73239de23000b5310d9342c6db95bc524
ms.sourcegitcommit: c0f7ee7f8837fec881e97b2a3f12e7f63cf96882
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/22/2022
ms.locfileid: "8462363"
---
# <a name="awareness-between-ledger-settlement-and-year-end-close"></a>Las transacciones entre la liquidación de contabilidad y el cierre de fin de año

[!include [banner](../includes/banner.md)]


En Microsoft Dynamics 365 Finance versión 10.0.25, la característica **Conciencia entre la liquidación del libro mayor y el cierre de fin de año** está disponible en el espacio de trabajo **Gestión de características**. Esta función agrega dos mejoras principales que afectan la liquidación del libro mayor y el cierre de fin de año del libro mayor.

Durante el cierre de fin de año del libro mayor, las transacciones del libro mayor que se hayan liquidado ya no se incluirán en el saldo de apertura del próximo año fiscal. Esta mejora garantiza que solo las transacciones contables no liquidadas se incluyan en el saldo inicial. Es importante cuando se ejecuta la revaluación de moneda extranjera del libro mayor. La revaluación de moneda extranjera se ejecuta solo para transacciones contables que tienen un estado de **Sin colocar**. Sin embargo, antes de que se lanzase la característica **Conciencia entre la liquidación del libro mayor y el cierre de fin de año**, el saldo de apertura resumió tanto la transacción que tiene un estado de **Establecido** y los que tienen un estatus de **Sin colocar** y el estado del importe resumido se fijó en **Sin colocar**.

La segunda mejora le permite registrar transacciones de saldo de apertura detalladas durante el cierre de fin de año del libro mayor. Si la opción **Mantener el detalle durante el cierre de fin de año** está configurada como **Sí**, se creará un saldo de apertura independiente para cada transacción contable que no se liquide. Esta configuración se define para cada cuenta principal en la configuración de liquidación del libro mayor. Al mantener transacciones detalladas para el saldo de apertura, mejora en gran medida la capacidad de liquidar las transacciones contables no liquidadas en el próximo año fiscal.

Para respaldar las nuevas mejoras, se realizaron cambios en la liquidación del libro mayor y el cierre de fin de año.

### <a name="changes-to-ledger-settlement"></a>Cambios en la liquidación del libro mayor

- La liquidación del libro mayor debe realizarse dentro de un año fiscal.
- La liquidación del libro mayor se debe realizar para las transacciones en una sola cuenta principal. La cuenta principal ahora es un filtro obligatorio en la página **Liquidación del libro mayor**.
- La liquidación del libro mayor y la reversión de la liquidación del libro mayor no se pueden realizar para transacciones que se contabilizan dentro de un año fiscal cerrado (en otras palabras, se ha ejecutado el cierre de fin de año).

### <a name="changes-to-year-end-close"></a>Cambios en el cierre de fin de año

- Un cierre de fin de año no se puede revertir si alguna transacción de saldo de apertura se ha liquidado en el próximo año fiscal. Este cambio se aplica cuando se revierte un cierre de fin de año, o cuando se vuelve a ejecutar un cierre de fin de año y la opción **Elimine las entradas de fin de año existentes al volver a cerrar el año** está configurada como **Sí** en Parámetros del libro mayor.
- Si la opción **Mantener el detalle durante el cierre de fin de año** está configurada como **Sí** para cualquier cuenta de balance en la liquidación del libro mayor, se crearán transacciones de saldo de apertura más detalladas para esa cuenta principal.

## <a name="before-you-enable-the-feature"></a>Antes de habilitar la característica

Debido a los cambios en la funcionalidad y el modelo de datos, es importante que considere los siguientes puntos antes de habilitar la función:

- Todas las transacciones que se han marcado para liquidación pero que no se han liquidado se desmarcarán automáticamente cuando se habilite la función. Para evitar cualquier pérdida de trabajo, liquide todas las transacciones marcadas antes de habilitar la función.
- Algunas organizaciones ejecutan el cierre de fin de año varias veces para el mismo año fiscal. No habilite la función si el cierre de fin de año ya se ejecutó una vez y se ejecutará nuevamente para el mismo año fiscal. La característica debe habilitarse antes de procesar el primer cierre de fin de año o después de procesar el último cierre de fin de año para el año fiscal.

  Si desea habilitar la función, pero el cierre de fin de año ya se ejecutó una vez, debe revertir el cierre de fin de año antes de poder habilitar la función.

- Debido a que ya no se permite la liquidación entre años fiscales, le recomendamos que habilite la función antes de comenzar el proceso de cierre de fin de año. Luego, para asegurarse de que los saldos de apertura del próximo año fiscal no se vean afectados por las liquidaciones de años fiscales anteriores, la transacción del saldo de apertura debe liquidarse para el año fiscal que se está cerrando.
- Debido a que ya no se permite la liquidación entre cuentas principales, ajuste su catálogo de cuentas o procesos según sea necesario para garantizar que la liquidación del libro mayor se pueda realizar en la misma cuenta principal.
- La función no se puede habilitar si se utiliza el proceso de cierre de fin de año del sector público.

## <a name="set-up-ledger-settlement"></a>Configurar la liquidación contable

Después de habilitar la característica y antes de ejecutar el próximo cierre de fin de año, cada organización debe determinar si conservará los detalles de la transacción durante el cierre de fin de año. La elección no tiene impacto en las contabilizaciones de saldo de apertura de los procesos de cierre de fin de año anteriores.

La opción **Mantener el detalle durante el cierre de fin de año** se establece para cada cuenta principal en la página **Configuración de liquidación del libro mayor**.

1.  Vaya a **Contabilidad general** > **Configuración de contabilidad** > **Parámetros de Contabilidad general**.
2.  En la pestaña **Liquidaciones del libro mayor**, seleccione **Cuentas de liquidación del libro mayor**.

– O bien –

1.  Vaya a **Contabilidad general** > **Tareas periódicas** > **Liquidaciones de contabilidad**.
2.  Seleccione **Cuentas de liquidación del libro mayor**.

Se han añadido dos columnas a la página **Liquidaciones del libro mayor**:
    
- **Tipo de cuenta principal**: esta columna es solo para fines informativos. Muestra el tipo que se asigna a la cuenta principal.
- **Mantener el detalle durante el cierre de fin de año**: de forma predeterminada, la opción está establecida en **No**. Se puede configurar como **Sí** sólo si el valor en la columna **Tipo de cuenta principal** es **Hoja de balance**, **Activo** o **Responsabilidad**. Cuando la opción se establece en **No**, los saldos de apertura se publicarán en resumen, como es habitual durante el cierre de fin de año. Si está configurado como **Sí**, los saldos de apertura se crearán en detalle para cada transacción contable que no se liquide para la cuenta principal.

## <a name="year-end-close"></a>Cierre de fin de año

Cuando se ejecuta el cierre de fin de año yendo a **Libro mayor** > **Cierre de periodo** > **Cierre de fin de año**, el proceso crea los saldos iniciales para las cuentas principales que se definen para la liquidación del libro mayor. Los saldos de apertura se crean en resumen o en detalle, según la configuración de liquidación del libro mayor. El proceso excluye las transacciones contables que se liquidan, independientemente de si contabiliza el saldo inicial de cada cuenta principal en resumen o en detalle.

Por ejemplo, varias transacciones se registran en la cuenta principal 130100 en el año fiscal 2021.

| Número de diario | Comprobante  | Fecha       | Tipo      | Cuenta contable | Nombre de la cuenta        | Description       | Divisa | Importe en divisa de transacción | Importe  | Importe en divisa de notificación |
|----------------|----------|------------|-----------|----------------|---------------------|-------------------|----------|--------------------------------|---------|------------------------------|
| 20853          | FTV-3000 | 3/12/2021  | Operativo | 130100-001-    | Clientes | Honorarios de servicio       | USD      | 100                            | 100     | 100                          |
| 20855          | FTV-3004 | 5/12/2021  | Operativo | 130100-002-    | Clientes | Utilidades         | USD      | 175                            | 175     | 175                          |
| 20854          | CMV-4000 | 16/12/2021 | Operativo | 130100-001-    | Clientes | Devolución            | USD      | -100                           | -100    | -100                         |
| 20851          | ARP-8000 | 20/12/2021 | Operativo | 130100-002-    | Clientes |                   | USD      | -0,88                          | -0,88   | -0,88                        |
| 20853          | ARPM0004 | 20/12/2021 | Operativo | 130100-002-    | Clientes |                   | EUR      | -127,11                        | -174,12 | -174,12                      |
| 20856          | CMV-4010 | 21/12/2021 | Operativo | 130100-002-    | Clientes | Crédito en cuenta | USD      | -175                           | -175    | -175                         |
| 20857          | FTV-3011 | 28/12/2021 | Operativo | 130100-001-    | Clientes | Utilidades         | USD      | 400                            | 400     | 400                          |
| 20910          | FTV-3020 | 29/12/2021 | Operativo | 130100-002-    | Clientes | Servicio           | USD      | 300                            | 300     | 300                          |

De estas transacciones, tres se liquidan durante la liquidación del libro mayor.

Hay una factura de 175 dólares estadounidenses (USD 175). Esta factura se pagó mediante un pago en euros (EUR) y se tomó un descuento por pronto pago.

| Número de diario | Comprobante  | Fecha       | Tipo      | Cuenta contable | Nombre de la cuenta        | Description | Divisa | Importe en divisa de transacción | Importe  | Importe en divisa de notificación |
|----------------|----------|------------|-----------|----------------|---------------------|-------------|----------|--------------------------------|---------|------------------------------|
| 20855          | FTV-3004 | 5/12/2021  | Operativo | 130100-002-    | Clientes | Utilidades   | USD      | 175                            | 175     | 175                          |
| 20851          | ARP-8000 | 20/12/2021 | Operativo | 130100-002-    | Clientes |             | USD      | -0,88                          | -0,88   | -0,88                        |
| 20853          | ARPM0004 | 20/12/2021 | Operativo | 130100-002-    | Clientes |             | EUR      | -127,11                        | -174,12 | -174,12                      |

Los resultados para la cuenta principal 130100 dependen de si la función está habilitada antes de que se ejecute el cierre de fin de año. Si la función está habilitada, el resultado también depende de la configuración de la opción Conservar detalles durante el cierre de fin de año.

### <a name="the-feature-isnt-enabled"></a>La característica no está habilitada
El cierre de fin de año crea tres transacciones de saldo de apertura para la cuenta principal 130100 en 2022. La suma de las transacciones en la divisa de contabilidad es USD 525.

| Número de diario | Comprobante  | Fecha     | Tipo    | Cuenta contable | Nombre de la cuenta        | Description | Divisa | Importe en divisa de transacción | Importe  | Importe en divisa de notificación |
|----------------|----------|----------|---------|----------------|---------------------|-------------|----------|--------------------------------|---------|------------------------------|
| 20910          | YEC_2021 | 1/1/2022 | Apertura | 130100-002-    | Clientes |             | USD      | 299.12                         | 299.12  | 299.12                       |
| 20910          | YEC_2021 | 1/1/2022 | Apertura | 130100-001-    | Clientes |             | USD      | 400                            | 400     | 400                          |
| 20910          | YEC_2021 | 1/1/2022 | Apertura | 130100-002-    | Clientes |             | EUR      | -127,11                        | -174,12 | -174,12                      |

A pesar de que la transacción de pago por EUR -127,11 se liquidó en el libro mayor, la transacción sigue apareciendo como un saldo inicial.

### <a name="feature-is-enabled-and-keep-detail-during-year-end-close--no"></a>La función está habilitada y Mantener detalles durante el cierre de fin de año = No

El cierre de fin de año crea dos transacciones de saldo de apertura para la cuenta principal 130100 en 2022. La suma de las transacciones en la moneda de contabilidad sigue siendo USD 525, pero las transacciones liquidadas en el libro mayor se excluyen del saldo de apertura. El monto total de la cuenta 130100-002- es USD 125 en lugar de USD 299.12, y la transacción por EUR 127.11/USD 174.12 está totalmente excluida.

| Número de diario | Comprobante  | Fecha     | Tipo    | Cuenta contable | Nombre de la cuenta        | Description | Divisa | Importe en divisa de transacción | Importe | Importe en divisa de notificación |
|----------------|----------|----------|---------|----------------|---------------------|-------------|----------|--------------------------------|--------|------------------------------|
| 20910          | YEC_2021 | 1/1/2022 | Apertura | 130100-002-    | Clientes |             | USD      | 125                            | 125    | 125                          |
| 20910          | YEC_2021 | 1/1/2022 | Apertura | 130100-001-    | Clientes |             | USD      | 400                            | 400    | 400                          |

### <a name="feature-is-enabled-and-keep-detail-during-year-end-close--yes"></a>La función está habilitada y Mantener detalles durante el cierre de fin de año = Sí

El cierre de fin de año crea cinco transacciones de saldo de apertura para la cuenta principal 130100 en 2022. Se crea una transacción de saldo de apertura separada para cada una de las cinco transacciones que no se liquidaron. La suma de las transacciones en la divisa de contabilidad todavía es USD 525.

| Número de diario | Comprobante  | Fecha     | Tipo    | Cuenta contable | Nombre de la cuenta        | Description       | Divisa | Importe en divisa de transacción | Importe | Importe en divisa de notificación |
|----------------|----------|----------|---------|----------------|---------------------|-------------------|----------|--------------------------------|--------|------------------------------|
| 20910          | YEC_2021 | 1/1/2022 | Apertura | 130100-001-    | Clientes | Honorarios de servicio       | USD      | 100                            | 100    | 100                          |
| 20910          | YEC_2021 | 1/1/2022 | Apertura | 130100-001-    | Clientes | Devolución            | USD      | -100                           | -100   | -100                         |
| 20910          | YEC_2021 | 1/1/2022 | Apertura | 130100-002-    | Clientes | Crédito en cuenta | USD      | -175                           | -175   | -175                         |
| 20910          | YEC_2021 | 1/1/2022 | Apertura | 130100-001-    | Clientes | Utilidades         | USD      | 400                            | 400    | 400                          |
| 20910          | YEC_2021 | 1/1/2022 | Apertura | 130100-002-    | Clientes | Servicio           | USD      | 300                            | 300    | 300                          |

Cuando se conservan los detalles de la transacción, las transacciones detalladas originales no se ven afectadas. Quedan contabilizados y sin liquidar en el ejercicio que se cierra. Se crea una copia de esas transacciones para el saldo de apertura. Los valores siguientes de las transacciones originales se copian a las transaciones del saldo de apertura.

- Cuenta contable (la cuenta principal y todas las dimensiones financieras)
- Importes en las divisas de transacción, contabilidad e informe.
- Description
- Capa de registro
- Tipo de registro

   > [!NOTE]
   > A ninguna otra transacción de saldo inicial se le asigna un tipo de contabilización. Por lo tanto, el tipo de contabilización se puede utilizar para diferenciar transacciones de apertura que se adelantaron en detalle.

Algunos campos de las transacciones originales deben cambiar en las transacciones detalladas del saldo de apertura. La fecha de las transacciones de saldo de apertura es siempre el primer día del siguiente año fiscal. El número de diario debe cambiar y el número de comprobante cambia al valor que se ingresó en el cuadro de diálogo de cierre de fin de año.

La información de las transacciones originales se puede encontrar en la página **Liquidación del libro mayor**. Cada transacción de saldo de apertura detallada muestra la columna **Fecha de transacción original** en la cuadrícula. Esta columna puede ayudarle a conciliar transacciones en el nuevo año fiscal. Puede elegir **Ver bono original** para volver al comprobante original completo.

## <a name="settle-transactions"></a><a name="settle-transactions"></a>Liquidar transacciones
Para liquidar transacciones de contabilidad, siga estos pasos.

1. Vaya a **Contabilidad general** > **Tareas periódicas** > **Liquidaciones de contabilidad**.
2.  Establezca los filtros en la parte superior de la página.

    1. Seleccione un rango de fechas. Alternativamente, seleccione un código de intervalo de fechas para completar automáticamente el intervalo de fechas.

       - El rango de fechas no puede cruzar años fiscales. Si el rango de fechas cruza años fiscales, no se mostrarán transacciones cuando seleccione **Mostrar transacciones**.
       - Si el rango de fechas está en un año fiscal abierto, las transacciones se pueden liquidar y la liquidación se puede revertir. Si el intervalo de fechas se encuentra en un año fiscal cerrado, o si se completa el cierre de fin de año, se muestran las transacciones, pero no se pueden liquidar ni anular. Puede desmarcar transacciones solo en un año fiscal cerrado. Si el rango de fechas está en un año fiscal cerrado, los botones **Marcar seleccionado**, **Liquidar transacciones marcadas** y **Transacciones marcadas inversamente** no están disponibles.

    2. Seleccione la cuenta principal para para la que se mostrarán transacciones. Este campo es obligatorio. La búsqueda muestra solo las cuentas principales que están seleccionadas en la página **Liquidación del libro mayor** del plan de cuentas de la empresa.
    3. Seleccione una capa de registro. No puede liquidar transacciones que están en diferentes niveles de contabilización.
    4. Para mostrar la cuenta principal y las dimensiones en columnas por separado, seleccione un conjunto de dimensiones financieras.

3.  Seleccione **Mostrar transacciones** para mostrar todas las transacciones que coinciden con los filtros que configuró. Si cambia alguno de los filtros o los conjuntos de dimensiones, debe volver a seleccionar **Mostrar transacciones**.
4.  Seleccione las líneas de liquidación. El valor en el campo **Importe seleccionado** en la parte superior de la página aumenta o disminuye para reflejar el importe total de las líneas seleccionadas.
5.  Cuando haya terminado de seleccionar transacciones, seleccione **Marcar seleccionada**. Para cada transacción seleccionada, aparece una marca de verificación en la columna **Marcado**. Además, el valor en el campo **Importe marcado** en la parte superior de la cuadrícula aumenta o disminuye para reflejar el importe total de las líneas marcadas.
6.  Cuando el valor del campo **Importe marcado** es **0** (cero), seleccione **Liquidar transacciones marcadas**.

    - No se permite la liquidación parcial. Por ejemplo, no puede liquidar una transacción de débito $ 100 contra una transacción de crédito $ 90. La transacción de crédito $ 10 restante también debe marcarse para su inclusión en la liquidación.
    - Introducir una fecha de liquidación. La fecha debe ser igual o posterior a la última fecha de las transacciones marcadas para liquidación.

El estado de las transacciones marcadas se actualiza a **Liquidada**.

> [!IMPORTANT]
> Se liquidarán todas las transacciones que haya marcado para la liquidación de la entidad jurídica activa y la cuenta principal seleccionada. Las transacciones no tienen que aparecer en la página. Se liquidarán incluso si están ocultos debido a un filtro.

Algunos procesos, como la reversión de una transacción, liquidan automáticamente las transacciones del libro mayor. Por ejemplo, un pago y una factura se liquidan en Cuentas por cobrar y la liquidación genera una ganancia/pérdida realizada. La liquidación del pago y la factura no liquida ninguna transacción del libro mayor, como las transacciones de la cuenta del libro mayor de Cuentas por cobrar. Sin embargo, si el pago y la factura no se liquidan en Cuentas por cobrar, el asiento contable de reversión que se registró durante la reversión de la liquidación de Cuentas por cobrar hará que los asientos contables originales y de reversión se liquiden en el Libro mayor. Cuando la característica **Conciencia entre la liquidación del libro mayor y el cierre de fin de año** está habilitada, la liquidación del libro mayor de una reversión no se produce automáticamente si la fecha de reversión está en un año fiscal diferente.

## <a name="use-excel-for-ledger-settlement"></a>Utilice Excel para la liquidación del libro mayor

Las transacciones que se muestran en la página **Liquidación del libro mayor** se pueden exportar a Excel. En Excel, puede filtrar aún más las transacciones para determinar qué transacciones marcar para su liquidación.
Ambas entidades de liquidación del libro mayor exportan transacciones del libro mayor solo para la cuenta principal seleccionada en la página **Liquidación del libro mayor**. Aunque las transacciones de los años fiscales cerrados todavía se pueden marcar o desmarcar mediante Excel, no se pueden liquidar. Además, las transacciones liquidadas no se pueden revertir para ese año fiscal.

## <a name="make-transactions-easier-to-find"></a>Facilite encontrar las transacciones

La página **Liquidaciones de contabilidad** incluye capacidades que facilitan ver las transacciones que necesita para la liquidación.

•   Use el filtro **Marcado** para filtrar transacciones en función de si la casilla **Marcado** para ellas esta seleccionada.
•   Use el filtro **Estado** para filtrar las transacciones en función de su estado.
•   Seleccione **Ordenar por cantidad absoluta** para ordenar los importes por valor absoluto. De esta forma, puede agrupar débitos y créditos que tengan la misma cantidad.

## <a name="reverse-a-settlement"></a>Invertir una liquidación

Puede invertir una liquidación que se ha realizado por error.

1.  Siga los pasos 1 a 3 en la sección [Liquidar transacciones](#settle-transactions) para mostrar las transacciones que le interesan.
2.  En el campo **Estado**, seleccione **Liquidado**.
3.  Seleccione las líneas de reversión.
4.  Seleccione **Revertir transacciones marcadas**. El estado de todas las transacciones que tienen el mismo ID de liquidación se actualiza a **Sin liquidar**.

> [!IMPORTANT]
> Todas las transacciones que tengan el mismo ID de liquidación se revertirán, incluso si no están marcadas. Por ejemplo, se marcaron y asentaron cuatro líneas. Las cuatro líneas tienen el mismo ID de liquidación. Si marca una de esas cuatro líneas y luego selecciona **Transacciones marcadas inversamente**, las cuatro líneas se invertirán.






