---
title: Trabajar con la funcionalidad de mensajes electrónicos
description: Este artículo proporciona información sobre cómo trabajar con la funcionalidad de mensajes electrónicos (EM).
author: liza-golub
ms.date: 07/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: elgolu
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.21
ms.openlocfilehash: b61c119a06e1a7281d3adb67e043d2f7002cbea1
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8880712"
---
# <a name="work-with-the-electronic-messages-functionality"></a>Trabajo con la funcionalidad de mensajes electrónicos

[!include [banner](../includes/banner.md)]

Si trabaja en el nivel de mensaje, la página **Mensajes electrónicos** (**Impuestos** \> **Consultas e informes** \> **Mensajes electrónicos** \> **Mensajes electrónicos**) es más útil. Si trabaja en el nivel de recopilación de datos o elemento de mensaje, la página **Elementos de mensaje electrónico** (**Impuestos** \> **Consultas e informes** \> **Mensajes electrónicos** \> **elementos de mensaje electrónico**) es más útil.

## <a name="electronic-messages"></a>Mensajes electrónicos

La página **Mensajes electrónicos** muestra el proceso que tiene disponible para el usuario en función de su rol. Los roles de seguridad están asociados al procesamiento en la configuración de dicho procesamiento. Para cada proceso que el usuario tiene disponible, la página muestra mensajes electrónicos e información relacionada con ellos.

La ficha desplegable **Mensajes** muestra mensajes electrónicos para el procesamiento seleccionado. En función del estado del mensaje seleccionado y del procesamiento predefinido, puede ejecutar algunas acciones usando los botones sobre la cuadrícula:

- **Nuevo** Este botón está asociado a las acciones del tipo **Crear mensaje**.
- **Eliminar** Este botón está disponible si la casilla de verificación **Permitir la cancelación** está seleccionada para el estado actual del mensaje seleccionado.
- **Recopilar datos** - Este botón está asociado con acciones del tipo **Rellenar registros**.
- **Generar informe** Este botón está asociado a acciones del tipo **Mensaje de exportación de informes electrónicos**.
- **Enviar informe** Este botón está asociado a acciones del tipo **Servicio web**.
- **Importar respuesta** - Este botón está asociado a acciones del tipo **Importar informes electrónicos**.
- **Actualizar estado** Este botón está asociado a las acciones del tipo **Procesamiento de usuario de nivel de mensaje**.
- **Elementos de mensaje** Abre la página **Elementos del mensaje electrónico**.

La ficha desplegable **Registro de acción** muestra información acerca de todas las acciones que se han ejecutado para el mensaje seleccionado. Si una acción causa un error, la información acerca del error se vinculará a la línea relacionada en la cuadrícula. Para revisar la información acerca del error, seleccione la línea de la cuadrícula y seleccione el botón **Adjuntos** (el símbolo de clip de papel) en la esquina superior derecha de la página.

La ficha desplegable **Campos adicionales de mensaje** muestra todos los campos adicionales que se han definido para los mensajes en la configuración de procesamiento. La ficha desplegabla también incluye los valores de estos campos adicionales.

La ficha desplegable **Elementos de mensaje** muestra todos los elementos de mensaje relacionados con el mensaje seleccionado. En función del estado del mensaje seleccionado y del elemento, puede ejecutar algunas acciones usando los botones sobre la cuadrícula:

- **Eliminar** Este botón está disponible si la casilla de verificación **Permitir la cancelación** está seleccionada para el estado actual del elemento de mensaje seleccionado.
- **Actualizar estado** Este botón está asociado a las acciones del tipo **Procesamiento de usuario**.
- **Documento original** - Abre una página que muestra el documento original para el elemento de mensaje seleccionado.

Los informes que ya se han generado y se han recibido para un mensaje se adjuntan a dicho mensaje. Para revisar los adjuntos relacionados con un mensaje, seleccione el mensaje y después seleccione el botón **Adjuntos** (el símbolo de clip de papel) en la esquina superior derecha de la página.

![Botón de datos adjuntos](media/attachment-icon.png)

La página **Adjuntos** muestra los datos adjuntos relacionados con el mensaje seleccionado. Para ver un archivo, selecciónelo en la lista de la izquierda y, después, seleccione **Abrir** en el panel de acciones.

![Botón Abrir](media/open-button.png)

Puede revisar los datos adjuntos relacionadas con una acción específico que se ejecutó anteriormente para un mensaje. En la página **Mensajes electronicos**, en la ficha desplegable **Mensajes**, seleccione el mensaje. En la ficha desplegable **Registro de acción**, seleccione la acción y, a continuación, seleccione el botón **Adjunto archivo** (símbolo de clip de papel) en la esquina superior derecha de la página.

Puede ejecutar el procesamiento entero o solo un acción específica seleccionando **Ejecutar procesamiento** en el panel de acciones.

## <a name="electronic-message-items"></a>Elementos de mensaje electrónico

La página **Elementos del mensaje electrónico** muestra todos los elementos de mensaje y un registro de las acciones que se han ejecutado para cada elemento de mensaje. La página también muestra los campos adicionales que se han definido para los elementos de mensaje, y los valores de estos campos adicionales.

En la tabla siguiente se describen los campos en la pestaña **Elementos de mensaje**.

<table>
<thead>
<tr>
<th>Campo</th>
<th>Descripción</th>
</tr>
</thead>
<tbody>
<tr>
<td>En procesamiento</td>
<td>El nombre del procesamiento usado para crear el elemento de mensaje.</td>
</tr>
<tr>
<td>Elemento de mensaje</td>
<td>Identificador del elemento de mensaje. Este identificador se asigna automáticamente, en función de la secuencia numérica del <b>elemento de mensaje</b> que se define en la página <b>Parámetros de contabilidad general</b>.</td>
</tr>
<tr>
<td>Fecha de elemento de mensaje</td>
<td>La fecha de creación del elemento de mensaje.</td>
</tr>
<tr>
<td>Tipo de elemento de mensaje</td>
<td>El tipo de elemento de mensaje. Se pueden configurar varios tipos de elementos de mensaje para el mismo procesamiento (por ejemplo, <b>Facturas de entrada</b> y <b>Facturas salientes</b>). Este campo se puede establecer automáticamente solo si una factura se agrega a la tabla de elementos de mensaje.</td>
</tr>
<tr>
<td>Estado de elemento de mensaje</td>
<td><p>El estado real del elemento de mensaje. Los estados disponibles varían, en función del tipo de elemento de mensaje. A continuación se incluyen algunos ejemplos:</p>
<ul>
<li><b>Rellenado</b> – Un registro se ha agregado a la tabla de elementos de mensaje.</li>
<li><b>Evaluado</b> – Los atributos adicionales se calcularon para el elemento de mensaje.</li>
<li><b>Notificado</b> – El elemento de mensaje se ha agregado correctamente a un informe.</li>
<li><b>Excluido</b> – Este estado es útil si se deben excluir algunos elementos de mensaje del informe antes de que se exporte.</li>
</ul>
</td>
</tr>
<tr>
<td>Fecha de transmisión</td>
<td>Para el procesamiento que transmite automáticamente un informe generado fuera del sistema, la fecha en la que el elemento de mensaje se transmite.</td>
</tr>
<tr>
<td>Número de documento</td>
<td>Este campo se establece automáticamente en función de la configuración de la acción de llenar registros. Este campo se puede establecer automáticamente solo si una factura se agrega a la tabla de elementos de mensaje.</td>
</tr>
<tr>
<td>Número de cuenta</td>
<td>El número de cuenta de un cliente o proveedor (u otro valor de campo, en función del campo que se define en la acción rellenar registros). Este campo se puede establecer automáticamente solo si una factura se agrega a la tabla de elementos de mensaje.</td>
</tr>
<tr>
<td>Mensaje</td>
<td>El número del mensaje. Este número se asigna automáticamente, en función de la secuencia numérica del <b>mensaje</b> que se define en la página <b>Parámetros de contabilidad general</b>.</td>
</tr>
<tr>
<td>Estado del mensaje</td>
<td>El estado real del mensaje electrónico.</td>
</tr>
<tr>
<td>Acción siguiente</td>
<td>Los siguientes acciones que se pueden iniciar para el estado actual del elemento de mensaje.</td>
</tr>
</tbody>
</table>

La pestaña **Campos adicionales** muestra los campos adicionales del emento del mensaje seleccionado, y sus valores.

### <a name="run-processing"></a>Ejecutar procesamiento

En el panel de acciones, seleccione **Ejecutar procesamiento** para ejecutar el procesamiento para los elementos de mensaje. Para ejecutar una acción específica, en el cuadro de diálogo **Ejecutar procesamiento** establezca la opción **Elegir acción** en **Sí**, y después seleccione una acción. Para ejecutar el procesamiento entero, deje la opción **Elegir acción** en **No**.

### <a name="generate-report"></a>Generar informe

En el panel de acciones, seleccione **Generar informe**. Este botón está asociado a acciones del tipo **exportación de informes electrónicos**.

### <a name="update-status"></a>Actualizar estado

En el panel de acciones, seleccione **Actualizar estado** para actualizar el estado de uno o más elementos de mensaje. En el cuadro **Actualizar estado** , use la ficha desplegable **Registros para incluir** para seleccionar los elementos de mensaje a actualizar. Asegúrese de que se definan correctamente los criterios de selección, porque se actualizarán los estados del elemento de mensaje en función de estos criterios, el estado inicial de la acción seleccionada y el valor que especifique en el campo **Nuevo estado**. Tras realizar una actualización del estado, es difícil determinar qué elementos se han actualizado. Por lo tanto, es difícil revertir las actualizaciones de estado.

### <a name="electronic-messages"></a>Mensajes electrónicos

En el panel de acciones, seleccione **Mensajes electrónicos** para revisar un mensaje electrónico que esté relacionado con el elemento del mensaje seleccionado.

También puede revisar los archivos relacionados a un elemento de mensaje específico. Seleccione el campo **Mensaje** para el elemento de mensaje, o seleccione **Mensajes electrónicos** en el panel de acciones. En la página **Mensaje electrónico**, seleccione el mensaje del que se revisarán archivos y después seleccione el botón **Adjuntos** (el símbolo de clip de papel) en la esquina superior derecha de la página.

La página **Datos adjuntos** muestra los datos adjuntos relacionados con el mensaje. Para ver un archivo, selecciónelo en la lista de la izquierda, y después seleccione **Abrir** en el panel de acciones.

### <a name="original-document"></a>Documento original

En el panel de acciones, seleccione **Documento original** para abrir el documento original para el elemento del mensaje seleccionado.
