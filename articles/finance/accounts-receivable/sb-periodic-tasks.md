---
title: Tareas periódicas en la facturación de contratos recurrentes
description: Este tema describe las tareas periódicas que están disponibles en la facturación de contratos recurrentes.
author: JodiChristiansen
ms.date: 04/29/2022
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
ms.openlocfilehash: 80f65d82881bb000f626c4225b3eac7dd1a2a44a
ms.sourcegitcommit: 1877696fa05d66b6f51996412cf19e3a6b2e18c6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2022
ms.locfileid: "8786977"
---
# <a name="periodic-tasks-in-recurring-contract-billing"></a>Tareas periódicas en la facturación de contratos recurrentes

Este tema describe las tareas periódicas que están disponibles en la facturación de contratos recurrentes.

## <a name="generate-invoice"></a>Generar factura

Use la página **Generar factura** para crear facturas recurrentes mensuales masivas a partir de la información que configuró en las páginas **Todos los horarios de facturación** y **Ver detalles de facturación**. Cuando se crea una factura, la descripción del artículo para la línea de procesamiento de la orden de venta se actualiza con la descripción del artículo y las fechas de inicio y fin de facturación para la línea de programación que se factura.

## <a name="generate-invoice-batch-processing"></a>Generar procesamiento por lotes de facturas

Use la página **Generar procesamiento por lotes de facturas** para crear facturas recurrentes a través de un proceso por lotes recurrente. Los parámetros que están disponibles son los mismos que los parámetros en la página **Generar factura**, pero se pueden guardar en un proceso por lotes que se puede ejecutar varias veces.

## <a name="price-update"></a>Actualización del precio

Utilice la utilidad de actualización de precios para actualizar los precios de varios artículos en varios calendarios de facturación en una sola acción. Los precios se pueden actualizar en función de un porcentaje específico o una cantidad específica. La lista de líneas muestra solo los precios unitarios actuales de los artículos. No muestra los precios después de la actualización de precios.

Tenga en cuenta los siguientes puntos sobre la utilidad de actualización de precios:

- Si ya se ha creado el pedido de ventas para un año específico (es decir, los artículos se han facturado), el precio de los artículos de línea no se ve afectado.
- La utilidad de actualización de precios se puede utilizar para artículos de línea que tienen un estado de **Activo** o **En espera**. Para los artículos que están en espera, la opción **Ajustar horario** debe haberse configurado en **No** cuando se colocó la retención.
- La utilidad de actualización de precios no se puede usar para elementos de línea que son elementos de uso, que usan escalación, facturación por hitos o división de ingresos.

### <a name="price-update-example"></a>Ejemplo de actualización de precio

Se crea un programa de facturación y se agrega un elemento de renovación. El precio por unidad es de 750 $. El primer año del artículo se paga el 15 de diciembre de 2021. Se crea el programa de facturación para el período del 1 de enero al 31 de diciembre de 2022.

En el momento de la renovación, el proceso **Generar factura** crea el pedido de ventas para el año 2022. Después de ejecutar la utilidad de actualización de precios, el precio se actualiza de 750 $ a 800 $.

La orden de venta y el programa de facturación para 2022 no se ven afectados, y el precio unitario sigue siendo 750 $, porque el programa de facturación para 2022 ya se facturó. La línea del programa de facturación y el detalle de la línea para 2023 se actualizaron a 800 $, porque el programa de facturación para 2023 aún no se facturó.

### <a name="update-prices--flat-pricing-method"></a>Actualizar precios: método de fijación de precios fijos

Cuando actualiza los precios de los artículos que utilizan el método de precio fijo, puede especificar un porcentaje o una cantidad para aumentar el precio.

Para ejecutar la utilidad de actualización de precios para artículos que utilizan el método de precio fijo, siga estos pasos.

1. En la página de utilidades **Actualización de precios**, seleccione el método de precios **Fijo**.
2. En el campo **Método de aumento**, seleccione el método de aumento que se utiliza para actualizar el precio de los artículos.
3. Según el método de aumento que haya seleccionado, especifique el porcentaje en el campo **Porcentaje** o la cantidad en el campo **Cantidad**.
4. En la ficha desplegable **Registros a incluir**, use el botón **Filtrar** para agregar filtros de datos.
5. Seleccione **Ver vista previa** para ver el rango de registros.
6. Si no quiere procesar algunas de las líneas, márquelas y seleccione **Eliminar**.
7. Seleccione **Aceptar**.

### <a name="update-prices--standard-pricing-method"></a>Actualizar precios: método de fijación de precios estándar

Si el precio de un artículo ha cambiado en el registro del artículo, se puede actualizar para todas las líneas del programa de facturación si el artículo usa el método de fijación de precios estándar.

1. En la página de utilidades **Actualización de precios**, seleccione el método de precios **Estándar**.
2. En la ficha desplegable **Registros a incluir**, use el botón **Filtrar** para agregar filtros de datos.
3. Seleccione **Ver vista previa** para ver el rango de registros.
4. Si no quiere procesar algunas de las líneas, márquelas y seleccione **Eliminar**.
5. Seleccione **Aceptar**.

## <a name="mass-hold-processing"></a>Procesamiento de retención masiva

Use la página **Retención masiva** para aplicar opciones de retención a varios programas de facturación a la vez.

Para poner solo un programa de facturación o una línea del programa de facturación en espera, abra la página **Todos los programas de facturación** y seleccione **Colocar en espera**. Para eliminar una retención, utilice la página **Quitar retención**.

### <a name="put-billing-schedules-on-hold"></a>Poner la programación de facturación en espera

Para poner en espera varios programas de facturación, siga estos pasos.

1. En la página **Retención masiva**, configure el campo **Opción de proceso** en **Aplicar retención**.
2. En el campo **Código de motivo**, seleccione un código de motivo.
3. Seleccione la opción **Ajustar programación**:

    - **Sí** – Si configura la opción en **Sí**, especifique una fecha de espera en el campo **Fecha de espera**. Se eliminan todas las líneas del programa de facturación posteriores a la fecha de retención.
    - **No** – Las líneas del programa de facturación no se modifican. Solo se cambia el estado. Esta actualizado a **En espera**.

4. En la ficha desplegable **Registros a incluir**, use el botón **Filtrar** para agregar filtros de datos.
5. Seleccione **Ver vista previa** para ver el rango de registros.
6. Si no quiere procesar algunas de las líneas, márquelas y seleccione **Eliminar**.
7. Seleccione **Aceptar**.

Cuando regrese a la lista de programas de facturación, debería ver que el estado de los programas de facturación ha cambiado a **En espera**.

### <a name="remove-a-hold-from-several-billing-schedules"></a>Eliminar una retención de varios programas de facturación

1. En la página **Retención masiva**, configure el campo **Opción de proceso** a **Quitar retención**.
2. En el campo **Código de motivo**, introduzca un código de motivo.
3. En el campo **Quitar fecha**, seleccione la fecha en la que se debe quitar la retención.
4. Establezca los campos **Fecha de reanudación** y **Fecha de fraccionamiento** según necesite. La fecha de aplazamiento se agrega a todas las líneas que son aplazables.
5. En la ficha desplegable **Registros a incluir**, use el botón **Filtrar** para agregar filtros de datos.
6. Seleccione **Ver vista previa** para ver el rango de registros.
7. Si no quiere procesar algunas de las líneas, márquelas y seleccione **Eliminar**.
8. Seleccione **Aceptar**.

> [!NOTE]
> Para eliminar una retención, debe configurar el valor **Eliminar la anulación del grupo de usuarios en espera** valor en la página **Parámetros de facturación de contratos recurrentes**.

Por ejemplo, una línea de facturación tiene una fecha de inicio del 1 de febrero de 2022 y una fecha de finalización del 28 de febrero de 2022. El importe de facturación es de 200 $. El campo **Fecha de retención** está configurado para el 10 de febrero de 2022. Por lo tanto, el período de febrero se ajusta para excluir cualquier fecha posterior al 10 de febrero. El nuevo período es del 1 de febrero al 9 de febrero y el monto es 64,29 $ (mediante prorrateo diario). Se eliminan todas las líneas del programa de facturación a partir del 10 de febrero.

Si el proceso **Quitar retención** se completa y el campo **Quitar fecha** está configurado para el 10 de febrero de 2022, habrá dos períodos de facturación. El primer período de facturación es del 1 de febrero al 9 de febrero y el monto es 64,29 $. El segundo período de facturación es del 10 de febrero al 28 de febrero y el monto es 135,71 $.

## <a name="mass-termination-processing"></a>Procesamiento de finalización masiva

Use la página **Terminación masiva** para terminar las líneas del programa de facturación que se muestran actualmente especificando una fecha de terminación.

Si utiliza aplazamientos de ingresos y gastos, los programas de facturación en los que el campo **Fecha de conclusión** se establece en **Ajustar programa** en la página **Todos los programas de facturación** son elegibles para un reembolso.

Los programas de facturación que utilizan la funcionalidad de asignación de elementos múltiples (MEA) no aparecen en la página **Terminación masiva**. Todavía puede terminar un programa de facturación individual utilizando la función de terminación en el programa de facturación.

> [!NOTE]
> Líneas de programación de facturación que están incluidas actualmente en un lote de **Generar factura** no están disponibles para este proceso.

Para obtener información sobre cada campo y el proceso, consulte [Terminar los programas de facturación](terminate-billing-schedule.md).

## <a name="mass-archive-process"></a>Proceso de archivado masivo

Use la página **Archivo masivo** para archivar múltiples programaciones de facturación. Solo se pueden archivar los programas de facturación cancelados.

Después de archivar un programa de facturación, ocurren los siguientes eventos:

- El estado cambia a **Archivado**.
- Los programas de facturación están permanentemente bloqueados.
- Las líneas del programa de facturación ya no están disponibles en las páginas de consulta.

> [!NOTE]
> El archivado de un programa de facturación es una acción permanente y no se puede revertir.

Para archivar programas de facturación, siga estos pasos.

1. En la página **Archivo masivo**, en el campo **Fecha de finalización de la facturación**, especifique una fecha de finalización de facturación. Para ver todos los calendarios de facturación terminados, deje este campo en blanco.
2. Para limitar el conjunto de registros que deben incluirse en la actualización, en la ficha desplegable **Registros a incluir** use el botón **Filtrar**.
3. Seleccione **Ver vista previa**.
4. Si no quiere archivar algunas de los registros, márquelos y seleccione **Eliminar**.
5. Seleccione **Aceptar** para archivar los registros en la página.

## <a name="mass-stubbing-process"></a>Proceso de resguardo masivo

Use la página **Talones masivos** para marcar todas las líneas del programa de facturación seleccionadas como facturadas (talón) o no facturadas (talonario inverso). La creación de talones o la creación de talones inversos se realizan con mayor frecuencia en líneas de programación de facturación importadas que se facturaron previamente en otro sistema. Las líneas del programa de facturación resguardadas aparecen como resguardadas y no crearán una factura para el cliente.

### <a name="stub-records"></a>Registros de resguardo

1. En la página **Recibos masivos**, en el campo **Opciones de proceso**, seleccione **Recibo**.
2. En el campo **Fecha de corte**, establezca una fecha límite para especificar las líneas a las que desea aplicar el proceso. Solo se mostrarán los registros en los que la fecha de inicio de facturación sea igual o anterior a la fecha límite especificada.
3. Seleccione **Ver vista previa** para mostrar las líneas que desea agregar.
4. Para excluir una línea del proceso, márquela y luego seleccione **Quitar**.
5. Seleccione **Procesar** para tachar las líneas.

### <a name="reverse-stub-records"></a>Revertir resguardo de registros

1. En la página **Recibos masivos**, en el campo **Opciones de proceso**, seleccione **Invertir recibo**.
2. En el campo **Fecha de corte**, establezca una fecha límite para especificar las líneas a las que desea aplicar el proceso. Solo se mostrarán los registros en los que la fecha de inicio de facturación sea igual o anterior a la fecha límite especificada.
3. Seleccione **Ver vista previa** para mostrar las líneas que desea invertir.
4. Para excluir una línea del proceso, márquela y luego seleccione **Quitar**.
5. Seleccione **Procesar** para invertir el resguardo de las líneas.

## <a name="update-completion-date-process"></a>Actualizar proceso de fecha de finalización

Use la página **Actualizar fecha de finalización** para actualizar la fecha de finalización para elementos de hitos específicos para múltiples programaciones de facturación o usuarios. También puede actualizar el porcentaje de finalización de elementos en plantillas de hitos que utilizan el método **Porcentaje completado**.

1. En la página **Actualizar fecha de finalización**, vaya a **Procesamiento de hitos** y seleccione **Actualizar porcentaje de finalización**.
2. En el campo **Cantidad de porcentaje**, introduzca el porcentaje total que se ha completado.
3. Seleccione el número de artículo relacionado con la plantilla de hito.
4. En la ficha desplegable **Registros a incluir**, seleccione **Filtrar** para seleccionar un valor **Cuenta de usuario final**, **Número de programa de facturación**, o **Números de artículo** como criterio de filtro.
5. Seleccione **Aceptar** para procesar el cambio. Cuando se completa el procesamiento, se agrega una nueva línea a la asignación de hitos. Esta línea representa el porcentaje que se ha completado para la plantilla de hitos.

## <a name="unbilled-revenue-mass-processing"></a>Procesamiento masivo de ingresos sin facturar

Use la página **Procesamiento masivo de ingresos no facturados** para crear el asiento de diario de ingresos no facturados o el talón del asiento de diario para uno o más programas de facturación seleccionados o líneas de detalle de facturación.

- **Crear entrada de diario** – Cree asientos de diario de ingresos no facturados para varias líneas de programación de facturación. Use el botón **Filtrar** en la ficha desplegable **Registros a incluir** para seleccionar un rango de registros que aparecerán en la lista. La lista muestra solo líneas de programación de facturación para las que no se han creado asientos de diario de ingresos no facturados. Se crean los asientos de diario iniciales. Para artículos de aplazamiento, también se crean programas de aplazamiento.
- **Entrada de diario recibo** – Marque las líneas del programa de facturación para las que ya se han creado los asientos de diario no facturados. Esta opción se utiliza si el asiento de diario no facturado ya se registró en otro sistema. Marca el diario de ingresos no facturado como recibo y no registra una transacción en el libro mayor.
- **Asiento de diario de recibo inverso** – Asientos de diario de recibos inversos que han sido procesados. Si se cometió un error durante el procesamiento de la **Entrada de diario de recibo**, esta opción borrará la casilla **Marcado** para el reparto de facturación.
- **Línea de detalle de facturación de recibo** – Utilice este proceso cuando los ingresos no facturados se procesaron en un sistema externo y algunas de las líneas de detalles de facturación ya se han facturado. Este proceso garantizará que aparezca el monto correcto en las cuentas de ingresos no facturados.
- **Línea de detalle de facturación de recibo inverso** – Invierte cualquier acción de **Línea de detalle de facturación de recibo**.

El campo **Nombre de diario** se usa para publicar **Crear entrada de diario** al libro mayor.

> [!NOTE]
> El proceso de recibo no contabiliza importes en el libro mayor. El campo **Nombre de diario** no está disponible para todos los procesos de código auxiliar y de código auxiliar inverso.

### <a name="unbilled-revenue-stub-example"></a>Ejemplo de comprobante de ingresos no facturados

Se establece un calendario de facturación para un año, desde octubre de 2021 hasta septiembre de 2022. Los ingresos no facturados ya se procesaron en un sistema externo. Ya se han facturado nueve meses del calendario de facturación. El importe del período de facturación es de 250 $ por mes. Al comienzo del año, la cantidad total que se registró en los ingresos no facturados es 3000 $. Después de nueve meses, 2250 $ ya se han facturado y sigue habiendo 750 $ en ingresos no facturados.

Para configurar el programa de facturación donde solo quedan tres meses de ingresos no facturados, siga estos pasos.

1. En la página **Ver detalle de facturación**, cree un programa de facturación para el período de octubre de 2021 a septiembre de 2022, número de artículo S0001 y una cantidad de 250 $ por mes.
2. Seleccione **Crear entrada de diario** para el calendario de facturación. La cantidad de 3000 $ se registra en ingresos no facturados.
3. Seleccione **Línea de detalle de facturación de recibo** y especifique una fecha de transacción de junio de 2022 (nueve meses). Las líneas del programa de facturación no aparecerán en la vista previa. Las líneas que se ven afectadas se basan en la fecha de la transacción.
4. Seleccione **Aceptar**.

Los primeros nueve meses que han sido facturados están talados.

[![Ver líneas de detalle de facturación de recibo](./media/01_View-billing-detail-stub.png)](./media/01_View-billing-detail-stub.png)

Los 3000 $ se revierten de los ingresos no facturados y se registran los 750 $ en los ingresos no facturados que quedan. Para ver las contabilizaciones de ingresos no facturados, seleccione **Auditoría de entrada de diario de ingresos no facturados** en la pestaña **Renovaciones** de la página de detalles de la línea.

[![Auditoría de movimientos del diario de ingresos sin facturar.](./media/02_Unbilled-rev-journal-audit.png)](./media/02_Unbilled-rev-journal-audit.png)

> [!NOTE]
> El asiento de diario de ingresos no facturados se puede crear para cualquier período de renovación, siempre que se hayan facturado todas las líneas de detalles de facturación del período anterior. Por ejemplo, un reparto de facturación tiene una frecuencia de facturación mensual durante un período de 12 meses, de enero a diciembre de 2021. La línea tiene tres plazos: el plazo inicial, un segundo plazo (enero a diciembre de 2022) y un tercer plazo (enero a diciembre de 2023). Después de que se haya creado la factura para todas las líneas de detalles de facturación de los 12 meses iniciales en 2021, se puede crear el asiento de diario para los ingresos no facturados para el segundo período.
>
> Para los elementos de aplazamiento que utilizan la función de ingresos no facturados, se procesan la línea de facturación y las líneas de descuento. Para estos artículos, se crean el asiento de diario de ingresos no facturados y la programación de diferimiento para la línea de facturación y la línea de descuento.
>
> Los asientos de diario que se crean para artículos no diferibles y artículos diferibles registran un crédito en diferentes cuentas de ingresos.
