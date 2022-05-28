---
title: Crear programaciones de facturación
description: Este tema explica cómo crear, eliminar y editar programaciones de facturación.
author: JodiChristiansen
ms.date: 02/09/2022
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
ms.openlocfilehash: ed31dd96b0115610cfb74aed69f1acc1055bfe56
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "8690456"
---
# <a name="create-billing-schedules"></a>Crear programaciones de facturación

[!include [banner](../includes/banner.md)]

En la página **Programación de facturación**, puede crear, eliminar o editar programaciones de facturación. También puede revisar la lista de programaciones de facturación. Cuando crea una programación de facturación, los valores predeterminados para la misma están determinados por el grupo de facturación que tiene asociado. La información adicional se establece en la página **Parámetros de facturación de contratos recurrentes**.

## <a name="create-a-billing-schedule"></a>Crear una programación de facturación

Para crear una programación de facturación, siga estos pasos.

1. En la página **Programación de facturación**, seleccione **Nuevo**.
2. En el cuadro de diálogo **Crear programación de facturación**, en el campo **Grupo de programación de facturación**, seleccione un grupo de programación de facturación.
3. En el campo **Cuenta de cliente**, seleccione una cuenta de cliente.
4. En el campo **Fecha de inicio**, seleccione la fecha de inicio y, a continuación, en el campo **Número de períodos**, introduzca el número de períodos. El campo **Fecha final** se actualiza en función del número de períodos que introduzca. Si actualiza el campo **Fecha final de la facturación**, el campo **Número de períodos** se actualiza a **0** (cero).
5. Seleccione **Aceptar**.
6. En la página **Programación de facturación**, en la pestaña **General**, en el campo **Descripción**, introduzca una descripción de la programación de facturación.
7. En el campo **Plantilla del hito**, seleccione una plantilla de hito para **Facturación por hitos**.

Los campos como **Xuenta de factura** y **Código de divisa** se actualizan con información del cliente.

Los campos **Frecuencia de facturación** e **Intervalo de facturación** se configuran automáticamente, según el grupo de programación de facturación seleccionado.

8. Para crear facturas separadas, configure la opción **Facturar por separado** a **Sí**.
9. Para renovar automáticamente una programación de facturación después del período de facturación final, configure la opción **Renovar automáticamente** a **Sí** y luego configure el campo **Líneas a agregar por renovación**.

Los campos de **Parámetros** se configuran automáticamente en función de los valores de la página **Parámetros de facturación de contratos recurrentes**.

10. Para prorratear el importe de una programación de facturación, establezca la opción **Prorratear periodos parciales** a **Sí**.
11. Para alinear las líneas de detalle de la programación de facturación con el final de un mes, configure la opción **Alinear al mes** a **Sí**.
12. En los campos **Fecha de inicio del contrato** y **Fecha final del contrato**, introduzca las fechas de inicio y finalización del contrato. Estas fechas se usan solo con fines informativos.

El campo **Pago** muestra la información de pago del cliente del cliente. Cuando una línea de pedido está retenida o rescindida, la información de pago no se puede cambiar.

> [!NOTE]
> Cuando consolida facturas por artículo, el valor de los campos **Condiciones de pago**, **Método** y **Programación de facturación** deben coincidir. De lo contrario, las facturas no se pueden consolidar.

13. En la pestaña **Dirección**, puede revisar y actualizar los campos **Dirección de entrega** y **Dirección de facturación**.
14. En la pestaña **Información de contacto**, puede asociar una cuenta de usuario final con la programación de facturación.
15. En los campos de **Información de contacto**, puede introducir un contacto, una dirección de correo electrónico y una dirección de internet.
16. Para realizar un seguimiento de la información de la comisión del socio, configure los campos **Cuenta de socio** y **Tasa de comisión de socios**. Estos campos se usan solo con fines informativos.
17. En el pestaña **Total**, puede ver los diversos totales que se han calculado para la programación de facturación.
18. En la pestaña **Retención**, puede ver información de auditoría sobre cuándo se puso en espera la programación de facturación cuando se eliminó la retención.
19. En la pestaña **Finalización**, puede ver un historial de las finalizaciones que se aplicaron o eliminaron de la programación de facturación.
20. Seleccione **Guardar**.
21. En la ficha desplegable **Líneas de programación de facturación**, seleccione **Agregar línea**.
22. En el campo **Número de artículo**, seleccione el número de artículo. Si el artículo que se agrega es un artículo principal en una división de ingresos, las líneas se actualizan automáticamente con los artículos secundarios. Solo puede editar el artículo principal en una división de ingresos. Todos los elementos secundarios se actualizan en consecuencia.
23. En el campo **Tipo de artículo**, seleccione el tipo de artículo.
24. Actualice las fechas de inicio y finalización.
25. Antes de que se creen las facturas, puede cambiar la frecuencia de facturación actualizando el campo **Frecuencia de facturación**. Después de que se cree la primera factura para la programación de facturación, la frecuencia de facturación no se puede cambiar.
26. En el campo **Unidad**, seleccione la unidad de medida para el artículo.
27. En el campo **Método de cálculo de precios**, seleccione el método de cálculo de precios para el artículo.

El campo **Precio unitario** se establece automáticamente desde el inventario. Sin embargo, puede actualizarlo si cambia el método de cálculo de precios a **Fijo**.

## <a name="remove-a-line-item"></a>Quitar un artículo de línea

Para eliminar un artículo de una programación de facturación, siga estos pasos.

1. En la página **Programación de facturación**, en el campo **Número de programación**, seleccione el número de la programación de facturación para editar.
2. En la ficha desplegable **Líneas de programación de facturación**, seleccione la línea para eliminar y luego seleccione **Eliminar**.
3. Seleccione **Guardar**.

El resto de este tema describe las acciones y los detalles que están disponibles para las líneas en la pestaña desplegable **Líneas de programación de facturación**.

## <a name="billing-schedule-line-actions"></a>Acciones de línea de programación de facturación

Los botones en la pestaña de programación **Líneas de programación de facturación** le permiten aplicar acciones a líneas individuales.

| Botón | Description |
|--------|-------------|
| Agregar línea | Agregue una línea a la programación de facturación. |
| Agregar desde la lista de artículos | Agregue varios artículos a una programación de facturación seleccionándolos en una lista. |
| Eliminar | <p>Elimine la línea seleccionada de la programación de facturación.</p><p>Para los artículos que forman parte de una división de ingresos, solo puede eliminar el artículo principal. Todos los elementos secundarios asociados se eliminan automáticamente.</p> |
| Ver detalle de facturación | Vea los detalles de facturación. |
| Baja | <p>Finalizar las líneas seleccionadas. Este botón está disponible solo cuando las líneas seleccionadas tienen un estado de **Activa**.</p><p>Para los artículos que forman parte de una división de ingresos, solo puede finalizar el artículo principal.</p> |
| Eliminar la finalización | <p>Elimine la finalización de las líneas seleccionadas. Este botón está disponible solo cuando las líneas seleccionadas tienen un estado de **Finalizada**.</p><p>Para los artículos que forman parte de una división de ingresos, solo puede eliminar la finalización del artículo principal.</p> |
| Colocar retención | <p>Seleccione los detalles para poner la línea seleccionada en espera.</p><p>Para los artículos que forman parte de una división de ingresos, solo puede poner en espera el artículo principal.</p> |
| Eliminar retención | <p>Eliminar la retención de la línea seleccionada.</p><p>Para los artículos que forman parte de una división de ingresos, solo puede eliminar la retención del artículo principal.</p> |
| Remisión a una instancia superior y descuento | Este botón no está disponible para los artículos que forman parte de una división de ingresos, excepto los artículos principales en los que la división de ingresos usa el método de asignación **Importe cero**. |
| Aplazamientos | <p>Introduzca las opciones de aplazamiento para la línea seleccionada.</p><p>Este botón no está disponible para artículos principales en una división de ingresos.</p> |
| Asignación por hitos | <p>Revise y actualice la información de asignación de hitos para la línea seleccionada.</p><p>Este botón está disponible solo cuando el elemento de línea de la programación de facturación es un elemento de hito.</p> |
| Soporte y renovación | <p>Revise y actualice la información de soporte y renovación para la línea seleccionada.</p><p>Este botón está disponible solo cuando el elemento de línea de la programación de facturación es un elemento de soporte y renovación.</p> |
| Mostrar dimensiones | Muestre u oculte las columnas de dimensión que aparecen en la cuadrícula **Líneas de programación de facturación**. |
| Calcular precio unitario | <p>Calcule el precio unitario del artículo para que el cliente pueda pagar el importe del contrato en cuotas (por ejemplo, diaria, mensual, trimestral, semestral o anual). Puede seleccionar el precio del contrato y la frecuencia de precios.</p><p>Puede ver un registro de auditoría de los cambios: el precio y la frecuencia del contrato anterior, el precio y la frecuencia del contrato nuevo, el usuario que realizó el cambio y la fecha y hora del cambio.</p> |
| Fecha de alineación | <p>Especifique la fecha de alineación para los elementos de renovación.</p><p>Si selecciona un grupo de artículos en el campo **Grupo de artículos**, todos los artículos usan la fecha de alineación del primer artículo en el grupo de artículos en la programación de facturación. Si el campo **Grupo de artículos** está en blanco, puede especificar una fecha de alineación para usar con todos los artículos.</p><p>Este botón solo está disponible cuando el campo **Frecuencia de facturación** está establecido en **Anual**.</p> |
| Ingresos sin facturar | <p>Configure el artículo para usar la característica de ingresos no facturados. A continuación, puede especificar los ingresos no facturados y las cuentas de descuento no facturadas para el artículo.</p><p>Este botón está disponible solo para elementos en los que el campo **Tipo de artículo** se establece en **Estándar**. No está disponible para las programaciones de facturación existentes ni para las líneas de la programación de facturación en las que ya se ha creado la factura.</p> |
| Agregar elemento secundario de división de ingresos | <p>Seleccione un artículo secundario para agregarlo al pedido de ventas.</p><p>Este botón solo está disponible para artículos principales en una división de ingresos.</p> |
| Opciones de cálculos de precios avanzados | Edite las opciones de precios de un artículo. |

## <a name="billing-schedule-line-details"></a>Detalle de línea de programación de facturación

Cuando seleccione una línea en la ficha desplegable **Líneas de programación de facturación**, puede ver detalles específicos para esa línea. Esos detalles se dividen en diferentes pestañas.

### <a name="general-tab"></a>Pestaña General

La siguiente información está disponible en la pestaña **General**.

| Campo o sección | Description |
|------------------|-------------|
| Uso | <p>Esta sección ofrece información sobre artículos de uso. Contiene los siguientes campos:</p><ul><li>**Identificador de uso**: el identificador del contador o artículo de uso.</li><li>**Opción de lectura**: la opción de lectura de uso: **Lectura** o **Consumo**.</li><li>**Consumo estimado**: especifique el consumo estimado para un artículo de uso que tiene períodos en los que no se ha creado la factura. En la página **Detalle de facturación**, puede revisar las líneas de detalle de facturación para el consumo estimado.</li></ul> |
| Referencias externas\* | Esta sección contiene los campos **Externo** y **Número de línea**, donde puede especificar información de referencia externa. |
| Hito | <p>Esta sección ofrece información sobre artículos de hito. Contiene el campo **Fecha de finalización prevista**, que muestra la fecha de finalización del elemento.</li></ul> |
| Texto | Un comentario para la línea. El texto se traduce al idioma predeterminado del cliente o entidad jurídica. |
| Grupo de artículos | El grupo de artículo para el artículo de línea. |
| Fecha de alineación | La fecha de alineación para la programación de facturación. |

\* Cuando consolida facturas por artículo en la página **Generar factura**, los campos de **Referencia externa** deben coincidir. Si incluso un carácter es diferente, los artículos no se consolidarán en la factura. No se realizan comprobaciones de validación en ninguno de los campos de la sección **Referencia externa** y el valor en el campo **Número de línea** debe ser un entero positivo.

### <a name="address-tab"></a>Pestaña Dirección

La siguiente información está disponible en la pestaña **Dirección**.

| Campo | Description |
|-------|-------------|
| Dirección de entrega | <p>Seleccione la dirección de entrega para el artículo de línea. La dirección de entrega predeterminada es la dirección de entrega principal de la ficha desplegable **Dirección**.</p><p>Cuando cambia la dirección, puede seleccionar las siguientes opciones de dirección:</p><ul><li>**Direcciones**: seleccione una dirección para el cliente actual.</li><li>**En uso**: seleccione una dirección que se utilice actualmente para el cliente actual.</li><li>**Otra dirección**: seleccione una dirección para cualquier registro de cliente.</li></ul><p>Para los artículos que utilizan la división de ingresos, solo se puede editar la dirección del artículo principal. La dirección de los elementos secundarios coincide con la dirección del principal y no se puede editar por separado.</p> |
| Dirección de facturación | <p>Seleccione la dirección de facturación para el artículo de línea. La dirección de entrega predeterminada es la dirección de entrega principal de la ficha desplegable **Dirección**. Puede cambiar la dirección según lo requiera, según el propósito de las direcciones disponibles:</p><ul><li>Si ninguna de las direcciones tiene un propósito de **Factura**, la dirección de facturación predeterminada es la dirección principal del cliente, independientemente del propósito.</li><li>Si una o más de las direcciones tienen un propósito de **Factura**, la dirección de facturación predeterminada es la dirección que se introdujo más recientemente.</li><li>Si una o más de las direcciones tienen un propósito de **Factura** y una de las direcciones de facturación se establece como la dirección principal, la dirección de facturación predeterminada es la dirección que tiene el propósito de **Factura** y se establece como la dirección principal.</li><li>Para los artículos que utilizan la división de ingresos, solo se puede editar la dirección del artículo principal. La dirección de los elementos secundarios coincide con la dirección del principal y no se puede editar por separado.</li></ul> |

### <a name="product-tab"></a>Pestaña de producto

La siguiente información está disponible en la pestaña **Producto**.

| Campo o sección | Description |
|------------------|-------------|
| Dimensiones de almacenamiento | <p>Esta sección muestra la información de almacenamiento del artículo. Contiene el campo **Número de serie**, que muestra el número de serie del artículo.</p><p>El número de serie se copia del pedido de venta inicial durante el proceso de soporte y renovación. Para los artículos que utilizan la división de ingresos, el número de serie del artículo principal se copia en todos los artículos secundarios. El número de serie se copia cuando la opción **Copiar número de serie** está configurada en **Sí** en la página **Parámetros de facturación de contratos recurrentes**.</li></ul> |
| Dimensiones de producto | Los detalles del producto para el artículo y los valores se actualizan automáticamente según el valor **Número de variante** seleccionado para la línea de programación de facturación. |

### <a name="account-tab"></a>Pestaña Cuenta

La siguiente información está disponible en la pestaña **Cuenta**.

| Campo | Description |
|-------|-------------|
| Cuenta principal | La cuenta principal que se crea en la línea de ventas. El valor predeterminado es del pedido de venta. Este campo puede estar en blanco. |
| Dimensiones financieras del artículo | <p>Los valores predeterminados de la dimensión financiera, basados en el registro del cliente y del artículo.</p><p>Para los artículos que usan la división de ingresos, los artículos secundarios usan los valores de dimensión financiera de los registros del cliente y del artículo, como se describió anteriormente. Si debe actualizar los valores de la dimensión financiera de los elementos secundarios, puede importar la entidad de datos.</p> |

### <a name="renewals-tab"></a>Pestaña de renovaciones

La siguiente información está disponible en la pestaña **Renovaciones**.

| Campo | Description |
|-------|-------------|
| Renovar automáticamente | <p>Un valor que indica si la línea de programación de facturación se renueva automáticamente para el próximo período de facturación:</p><ul><li>**Sí**: la línea de programación de facturación se renueva automáticamente para el próximo período de facturación cuando crea una factura.</li><li>**No**: la línea de programación de facturación no se renueva automáticamente. Debe renovar manualmente la programación de facturación.</li></ul> |
| Líneas a agregar por renovación | La cantidad de líneas para agregar a una renovación de la programación de facturación. |

Además, los siguientes botones están disponibles en la pestaña **Renovaciones**.

| Botón | Description |
|--------|-------------|
| Auditoría de movimientos del diario de ingresos sin facturar | Vea todos los cambios de los artículos que utilizan la característica de ingresos no facturados. |
| Agregar plazo de renovación | Agregue un plazo de renovación para el artículo. La fecha de inicio del nuevo plazo de renovación es la fecha siguiente a la fecha final del plazo anterior. Los campos **Fecha final de la renovación**, **Fecha de inicio del aplazamiento**, **Fecha final del aplazamiento**, **Cantidad de objetos** y **Precio unitario** se pueden actualizar. |
| Modificar período de renovación | <p>Modifique un plazo de renovación. Para el plazo inicial, puede cambiar las fechas de inicio y finalización del aplazamiento antes de que se cree el asiento de diario inicial. Para plazos posteriores, la fecha de inicio no se puede cambiar. Siempre es la fecha siguiente al final del período anterior.</p><p>Si existe un plazo de renovación después del plazo que está modificando, las fechas del plazo no se pueden cambiar. En este caso, solo los campos **Cantidad** y **Precio unitario** para el elemento de renovación se pueden actualizar.</p><p>Por ejemplo, existen tres plazos. <ul><li>El primer plazo no se puede cambiar porque ya ha comenzado.</li><li>Para el segundo plazo, solo se puede cambiar la cantidad y el precio unitario.</li><li>Para el tercer plazo, se pueden cambiar todos los valores excepto la fecha de inicio. Además, la opción **Programar desde plantilla** le permite crear una programación de aplazamiento que se basa en la plantilla para el elemento de ingresos no facturados. Cuando esta opción se establece en **Sí**, seleccione la plantilla de aplazamiento en el campo **Plantilla** y cambie las fechas de inicio y finalización del aplazamiento según lo requiera. Los plazos de renovación siguientes utilizan la misma plantilla de aplazamiento. Sin embargo, la plantilla de aplazamiento se puede cambiar.</p></li></ul> |

### <a name="termination-tab"></a>Pestaña Finalización

La siguiente información está disponible en la pestaña **Finalización**.

| Campo | Description |
|-------|-------------|
| Fecha de finalización | La fecha en la que la línea de la programación de facturación finaliza. El valor predeterminado es del campo **Fecha de finalización** en el encabezado. Puede cambiar el valor si es necesario. |
| Tipo de finalización | El tipo de finalización. El valor predeterminado es del campo **Tipo de finalización** en el encabezado. |

### <a name="hold-tab"></a>Pestaña Retención

Si se utilizan aplazamientos de ingresos y gastos, la pestaña **Retención** muestra la fecha de aplazamiento.

### <a name="escalation-and-discount-tab"></a>Pestaña de escalación y descuento

La siguiente información está disponible en la pestaña **Escalación y descuento**.

| Campo | Description |
|-------|-------------|
| Remisión a una instancia superior | <p>Seleccione si se permiten escalaciones para la línea de programación de facturación. Cualquier línea de escalación del encabezado se aplica cuando se crea la línea de programación de facturación.</p><ul><li>**Sí**: las escalaciones se pueden aplicar a la línea. Cuando se selecciona esta opción, puede configurar las escalaciones para las líneas de programación de facturación en la página **Escalación y descuento**.</li><li>**No**: las escalaciones no se pueden aplicar a la línea.</li></ul><p>La configuración predeterminada se basa en el **Grupo de programación de facturación** seleccionado.</p> |

### <a name="price-changes-tab"></a>Pestaña de cambios de precios

Para las líneas que se cambian de precio **Estándar** a precio **Fijo**, la cuadrícula en la pestaña **Cambios de precio** incluye las siguientes columnas:

- Modificar fecha
- Cambiado por el usuario
- Precio estándar
- Precio fijo
- Actualización del precio
