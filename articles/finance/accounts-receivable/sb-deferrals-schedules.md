---
title: Programaciones de aplazamientos de ingresos y gastos
description: Este tema describe las programaciones de aplazamientos de ingresos y gastos.
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
ms.openlocfilehash: 9135ac733496a0c5d79669c35972c273c209f81d
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8685988"
---
# <a name="deferral-schedules"></a>Programaciones de aplazamientos

Las programaciones de aplazamiento se crean después de que se haya registrado una transacción.

Puede usar la página **Todas las programaciones de aplazamiento** o **Programaciones de aplazamientos activas** para revisar los detalles sobre una programación de aplazamiento. La información que se muestra depende del tipo de programación de aplazamiento (lineal o basado en eventos) y el tipo de transacción. Incluye las líneas de programación de aplazamiento y los importes totales para la programación de aplazamiento. Puede utilizar la página para modificar la programación de aplazamiento.

## <a name="recognize-revenue"></a>Reconocer ingresos

> [!NOTE]
> - Para reconocer los ingresos de una programación de aplazamiento, comience en el paso 1.
> - Para reconocer los ingresos de varias programaciones, comience en el paso 2.

1. En la página **Todas las programaciones de aplazamiento**, en la cuadrícula **Programar líneas**, seleccione las líneas que desea reconocer y, a continuación, seleccione **Reconocer**.
2. En la página **Procesamiento de reconocimiento**, configure el campo **Acción de reconocimiento** en **Crear diario de reconocimiento**.
3. En el campo **Fecha límite**, seleccione la fecha límite. El procesamiento incluirá solo las líneas en las que la fecha de finalización sea anterior o igual a la fecha límite seleccionada.
4. Seleccione **Filtrar** y agregue filtros de datos para que la lista muestre solo el rango de registros que desea.
5. Seleccione **Ver vista previa** para ver las líneas.
6. En la lista de líneas, seleccione las líneas que no desea procesar y luego seleccione **Eliminar**.
7. Seleccione si desea resumir el movimiento de diario de reconocimiento.
8. En la sección **Fecha de Transacción**, puede anular la fecha de la transacción con una fecha específica para procesar la transacción. La fecha de la transacción se puede especificar para períodos cerrados.
9. Para realizar el procesamiento como parte de un lote, seleccione **Lote**. En el cuadro de diálogo **Procesamiento por lotes** configure los parámetros para el lote y luego seleccione **Aceptar** para volver a la página **Procesamiento de reconocimiento**. El reconocimiento de ingresos se procesará más tarde, cuando se procese el lote.
10. Seleccione **Procesar**. Si no agregó la transacción a un lote, todas las líneas se procesan inmediatamente. De lo contrario, las líneas se procesarán cuando se procese el lote.

## <a name="modify-a-schedule"></a>Modificar una programación

Para modificar una programación de facturación, siga estos pasos.

1. En la página **Todas las programaciones de aplazamiento** seleccione la programación de aplazamiento y, a continuación, seleccione **Contabilidad \> Modificar programación**.
2. En la página **Modificar programación**, edite las opciones que desea cambiar. Según la programación de aplazamiento, no podrá editar todas las opciones.
3. Seleccione **Vista previa** para revisar los cambios en la programación de aplazamiento.
4. Seleccione **Aceptar**.

### <a name="straight-line-deferral-schedules"></a>Programaciones de aplazamiento lineales

Si la programación de aplazamiento no tiene líneas reconocidas o contabilizadas externamente, puede modificar todo la programación de aplazamiento, incluida la fecha de inicio.

Si la programación de aplazamiento tiene líneas reconocidas o contabilizadas externamente, y usted modifica la programación de aplazamiento, el comportamiento resultante dla programación de aplazamiento depende de la fecha de nuevo cálculo y la fecha de finalización del aplazamiento de las líneas reconocidas. De forma predeterminada, el primer período que no se haya reconocido determina la fecha de finalización del aplazamiento.

Para usar la fecha de reconocimiento, seleccione uno de los siguientes valores en el campo **Inicio de programación**: 
- **Ponerse al día**: el importe después de volver a calcular todas las líneas reconocidas.
- **Inversión**: cualquier línea posterior a la fecha de nuevo cálculo se invierte utilizando el nombre de diario y la fecha de contabilización especificados. A continuación, se vuelve a calcular el importe posterior a la fecha de nuevo cálculo.

Si se usa una plantilla, los períodos omitidos se ignoran y la plantilla se usa solo para calcular la fecha de finalización.

### <a name="event-based-deferral-schedules"></a>Programaciones de aplazamiento basadas en eventos

Para una programación de aplazamiento basada en eventos, puede modificar todas las líneas no reconocidas.

Si la programación de aplazamiento no tiene líneas reconocidas o contabilizadas externamente, no puede modificar la plantilla ni el tipo de asignación para la programación de aplazamiento. Cuando modifica una programación de aplazamiento existente, no puede cambiar el valor del campo **Crear eventos separados por unidad**.

Si una línea se reconoce o contabiliza externamente, se selecciona la casilla **Reconocido**.

## <a name="modify-a-deferral-or-recognition-account"></a>Modificar una cuenta de aplazamiento o reconocimiento

Para modificar la cuenta de aplazamiento o reconocimiento para una programación de aplazamiento, siga estos pasos.

1. En la página **Todas las programaciones de aplazamiento** seleccione la programación de aplazamiento y, a continuación, seleccione **Contabilidad \> Modificar cuenta**.
2. En la página **Modificar cuenta**, seleccione la cuenta que desea cambiar (aplazamiento, corto plazo o reconocimiento).
3. En el campo **Nueva cuenta**, seleccione la nueva cuenta.
4. Seleccione si los cambios en la cuenta crean asientos de diario de ajuste.
5. Si establece la opción en **Sí** en el paso anterior, seleccione el nombre del diario en el campo **Nombre del diario** y especifique la fecha de la transacción en el campo **Fecha de Transacción**.
6. Seleccione **Aceptar**.

## <a name="put-a-deferral-schedule-on-hold"></a>Poner una programación de aplazamiento en espera

Para poner una programación de aplazamiento en espera, siga estos pasos.

1. En la página **Todas las programaciones de aplazamiento**, seleccione la programación de aplazamiento y, a continuación, seleccione **Retención \> Poner en retención**.
2. En la página **Poner en retención**, seleccione si desea transferir el saldo de la cuenta aplazada o de la cuenta de retención.
3. Si eligió transferir el saldo, seleccione el nombre del diario en el campo **Nombre del diario**, elija la cuenta de retención en la **Cuenta de retención** y especifique la fecha de la transacción en el campo **Fecha de Transacción**.
4. Seleccione **Aceptar**.

## <a name="remove-a-hold-from-a-deferral-schedule"></a>Eliminar una retención de una programación de aplazamiento

Para eliminar una programación de aplazamiento de una retención, siga estos pasos.

1. En la lista **Todas las programaciones de aplazamiento**, seleccione la programación de aplazamiento y, a continuación, seleccione **Retención \> Eliminar retención**.
2. En el campo **Nombre del diario**, seleccione el nombre de diario a usar.
3. En el campo **Fecha de transacción**, especifique la fecha de transacción.
4. Seleccione **Aceptar**.

## <a name="cancel-unrecognized-amounts"></a>Cancelar importes no reconocidos

> [!NOTE]
> Cualquier línea que ya haya sido reconocida o contabilizada externamente se excluye de este proceso.

Para cancelar importes no reconocidos en una programación de aplazamiento, siga estos pasos.

1. En la página **Todas las programaciones de aplazamiento** seleccione la programación de aplazamiento y, a continuación, seleccione **Cancelar \> Importes no reconocidos**.
2. En la página **Cancelar importe no reconocido**, seleccione si desea crear entradas de cancelación.
3. Si eligió crear movimientos de cancelación, seleccione el nombre del diario en el campo **Nombre del diario**, elija la cuenta de cancelación en el campo **Cuenta de cancelación** y especifique la fecha de la transacción en el campo **Fecha de transacción**.
4. Seleccione **Aceptar**.

## <a name="cancel-a-completed-schedule"></a>Cancelar una programación completada

Utilice la página **Todas las programaciones de aplazamiento** para revertir los importes reconocidos o registrados externamente y cancelar la programación de aplazamiento para evitar un mayor reconocimiento.

Para cancelar todo una programación de aplazamiento, siga estos pasos.

1. En la página **Todas las programaciones de aplazamiento**, seleccione la programación de aplazamiento y, a continuación, seleccione **Cancelar \> Programación completa**.
2. En la página **Cancelar programación completa**, seleccione si desea crear movimientos de cancelación.
3. Si eligió crear movimientos de cancelación, seleccione el nombre del diario en el campo **Nombre del diario**, elija la cuenta de cancelación en el campo **Cuenta de cancelación** y especifique la fecha de la transacción en el campo **Fecha de transacción**.
4. Seleccione **Aceptar**.

## <a name="reverse-transactions"></a>Revertir transacciones

> [!NOTE]
> - Para revertir el reconocimiento de ingresos de una programación de aplazamiento, comience en el paso 1.
> - Para revertir el reconocimiento de ingresos de varias programaciones, comience en el paso 2.

1. En la página **Todas las programaciones de aplazamiento**, en la cuadrícula **Programar líneas**, seleccione las líneas que desea dejar de reconocer y, a continuación, seleccione **Revertir**.
2. En la página **Procesamiento de reconocimiento**, configure el campo **Acción de reconocimiento** en **Revertir diario de reconocimiento**.
3. En el campo **Fecha límite**, seleccione la fecha límite. El procesamiento incluirá solo las líneas en las que la fecha de finalización sea anterior o igual a la fecha límite especificada.
4. Seleccione **Filtrar** y agregue filtros de datos para que la lista muestre solo el rango de registros que desea.
5. Seleccione **Ver vista previa** para ver las líneas.
6. En la lista de líneas, seleccione las líneas que no desea procesar y luego seleccione **Eliminar**.
7. Los campos **Nombre** y **Descripción** se actualizan automáticamente con el nombre y la descripción predeterminados del diario. Puede cambiar los valores si es necesario. También puede seleccionar si desea resumir el movimiento de diario de reconocimiento.
8. En la sección **Fecha de Transacción**, puede anular la fecha de la transacción con una fecha específica para procesar la transacción. La fecha de la transacción se puede especificar para períodos cerrados.
9. Para realizar el procesamiento como parte de un lote, seleccione **Lote**. En el cuadro de diálogo **Procesamiento por lotes** configure los parámetros para el lote y luego seleccione **Aceptar** para volver a la página **Procesamiento de reconocimiento**. La reversión del reconocimiento de ingresos se procesará más tarde, cuando se procese el lote.
10. Seleccione **Aceptar**. Si no agregó la transacción a un lote, todas las líneas se procesan inmediatamente. De lo contrario, las líneas se procesarán cuando se procese el lote.

## <a name="apply-or-unapply-a-credit-note"></a>Aplicar o no aplicar una nota de crédito

Para aplicar una nota de crédito, siga los siguientes pasos.

> [!NOTE]
> Cuando crea una nota de crédito en la página **Aplazamiento de transacciones de pedidos de ventas** y establece la opción **Ajustar la programación existente** en **Sí**, la nota de crédito se aplica automáticamente a la programación cuando se contabiliza la nota de crédito.

1. En la página **Todas las programaciones de aplazamiento**, seleccione la programación de aplazamiento.
2. En la lista **Ajustes de crédito**, seleccione una línea y, a continuación, seleccione **Aplicar**.
3. En la página **Aplicar nota de crédito (aplazamientos)**, especifique la fecha de recálculo en el campo **Fecha de recálculo** y la fecha de finalización en el campo **Fecha final**.
4. En la lista **Encabezado** seleccione el **Pedido de ventas** que tiene notas de crédito.
5. En la lista **Líneas**, seleccione la línea.
6. Seleccione **Aceptar**.
7. Seleccione **Sí**.

> [!NOTE]
> Para aplicar una nota de crédito a varios artículos individuales de diferentes facturas, debe repetir estos pasos.

Para dejar de aplicar una nota de crédito, siga los siguientes pasos.

1. En la página **Todas las programaciones de aplazamiento**, seleccione la programación de aplazamiento.
2. En la lista **Ajustes de crédito**, seleccione la factura y, a continuación, seleccione **Dejar de aplicar**.
3. Seleccione **Sí**.

## <a name="fields"></a>Campos

La página **Todas las programaciones de aplazamiento** contiene los siguientes campos.

| Campos | Description |
|--------|-------------|
| **Encabezado** | |
| **Programar** | |
| Tipo de asignación | El tipo de asignación, para aplazamientos basados en eventos: **Porcentaje** o **Importe**. |
| Fecha de reclasificación | <p>La fecha más reciente en que se procesó la reclasificación a corto plazo para una programación de aplazamiento. Esta fecha se actualiza cada vez que la **Reclasificación de eventos a corto plazo** se utiliza para la programación de aplazamiento.</p>Este campo está disponible solo cuando se utiliza el método de aplazamiento a corto plazo de períodos móviles o año fijo. |
| **Cuenta** | |
| Cuenta de aplazamiento | La cuenta que se utiliza para el importe aplazado. |
| Cuenta de reconocimiento | La cuenta que se utiliza para el importe de reconocimeinto. |
| Tipo de reconocimiento | El tipo de reconocimeinto. |
| Tipo de distribución | El tipo de distribución. |
| **Transacción**  | |
| Origen de creación | El origen desde el que se creó la transacción. |
| Tipo de transacción | El tipo de transacción. |
| Pedido de ventas | El número del pedido de ventas. |
| Factura | El número de la factura. |
| Elemento | Número de artículo. |
| **Programación de facturación** | |
| Número de programación de facturación | El número de la programación de facturación correspondiente. |
| Estado de línea de facturación | El estado del artículo de línea de la programación de facturación correspondiente. |
| Referencias externas | Información sobre referencias externas del calendario de facturación: **Externo** y **Número de línea**. |
| Totales | <p>Importes totales para el calendario de aplazamiento:</p><ul><li>**Largo plazo**: la suma de los importes aplazados a largo plazo. Este valor está disponible sólo cuando el campo **Método de aplazamiento a corto plazo** se establece en **Ninguno** en la página **Parámetros de aplazamiento de ingresos y gastos**, o la cantidad a corto plazo es mayor de 0 (cero).</li><li>**Corto plazo**: la suma de los importes aplazados a corto plazo. Este valor está disponible sólo cuando el campo **Método de aplazamiento a corto plazo** se establece en **Ninguno** en la página **Parámetros de aplazamiento de ingresos y gastos**, o la cantidad a corto plazo es mayor de 0 (cero).</li><li>**No reconocido**: la suma de los importes no reconocidos para todas las líneas.</li><li>**Extraidos**: la suma de los importes registrados externamente para todas las líneas.</li><li>**Reconocido**: la suma de los importes reconocidos para todas las líneas.</li><li>**Publicado y reconocido externamente**: la suma de los importes contabilizados y reconocidos externamente para todas las líneas.</li><li>**Importe total**: la suma de los valores para todas las líneas.</li></ul> |
| **Líneas de programación** | |
| Línea | El número de secuencia de línea. |
| Fecha de inicio de aplazamiento | La fecha inicial de la programación de aplazamiento. |
| Fecha de finalización de aplazamiento | La fecha final de la programación de aplazamiento. |
| Importe | El importe del aplazamiento. |
| Publicado externamente | Un valor que indica si la línea se ha registrado externamente. |
| Reconocida | Un valor que indica si la línea se ha reconocido externamente. |
| Número de lote de diario | El número de lote en el que se reconoció el importe. |
| Descripción del evento | Una descripción del evento. Este campo está disponible solo para programaciones de aplazamientos basadas en eventos. |
| **Ajustes de crédito** | |
| Factura | <p>El número de la factura.</p><p>El valor indica la factura del ajuste de la nota de crédito que ya se ha aplicado a la programación de aplazamiento.</p> |
| Importe aplicado | El importe del ajuste de crédito que ya se ha aplicado a la programación de aplazamiento. |
| Fecha de aplicación | La fecha en la que se aplicó el ajuste de crédito. |
| **Ajuste** | Los valores de ajuste aparecen solo si se procesó una nota de crédito para la programación de aplazamiento. Si no se procesó ninguna nota de crédito, estos valores se ocultan. |
| Importe del ajuste | El importe total del ajuste, calculado como *Importe original* - *Importe de la progración*. |
| Fecha final original | La fecha final original de la programación de aplazamiento. |
| Importe de programación original | El total de la programación de aplazamiento original. |
