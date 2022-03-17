---
title: Diseñar una configuración para generar documentos en formato de Excel
description: Este tema describe cómo diseñar un formato de informe electrónico (ER) para completar una plantilla de Excel y luego generar resultados en forma de documentos en formato Excel.
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 1b2f38aa9e5eff9366697afd57ceefd06f026096
ms.sourcegitcommit: b80692c3521dad346c9cbec8ceeb9612e4e07d64
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2022
ms.locfileid: "8388272"
---
# <a name="design-a-configuration-for-generating-documents-in-excel-format"></a>Diseñar una configuración para generar documentos en formato Excel

[!include[banner](../includes/banner.md)]

Puede diseñar una configuración de formato de [Informe electrónico (ER)](general-electronic-reporting.md) con un componente de formato ER que puede configurar para generar un documento resultante en un formato de libro de Microsoft Excel. Se deben usar componentes de formato ER específicos para este propósito.

Para obtener más información sobre esta función, siga los pasos del tema [Diseñar una configuración para generar informes en formato OPENXML](tasks/er-design-reports-openxml-2016-11.md).

## <a name="add-a-new-er-format"></a>Agregar un nuevo formato ER

Cuando agrega una nueva configuración de formato ER para generar un documento resultante en un formato de libro de Excel, debe seleccionar el valor **Sobresalir** para el atributo del formato **Tipo de formato** o dejar el atributo **Tipo de formato** en blanco.

- Si selecciona **Excel**, puede configurar el formato para generar un documento resultante solo en formato Excel.
- Si deja el atributo en blanco, puede configurar el formato para generar un documento saliente en cualquier formato que sea compatible con el marco ER.

Para configurar el componente de formato ER de la configuración, seleccione **Diseñador** en el panel Acciones y abra el componente de formato ER para editarlo en el diseñador de operaciones ER.

![Página Configuraciones.](./media/er-excel-format-add-format.png)

## <a name="excel-file-component"></a>Componente de archivo de Excel

### <a name="manual-entry"></a>Entrada manual

Debe agregar un componente **Archivo\\Excel** al formato ER configurado para generar un documento resultante en formato Excel.

![Componente Excel\archivo.](./media/er-excel-format-add-file-component.png)

Para especificar el diseño del documento resultante, adjunte un libro de Excel que tenga la extensión .xlsx al componente **Archivo\\Excel** como plantilla para documentos resultantes.

> [!NOTE]
> Cuando adjunte una plantilla manualmente, debe usar un [tipo de documento](../../../fin-ops-core/fin-ops/organization-administration/configure-document-management.md#configure-document-types) que se haya configurado para ese fin en los [parámetros ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).

![Adición de un archivo adjunto al componente Excel\archivo.](./media/er-excel-format-add-file-component2.png)

Para especificar cómo se rellenará la plantilla adjunta cuando ejecute el formato ER configurado, debe agregar componentes **Hoja**, **Rango** y **Celda** al componente **Archivo\\Excel**. Cada componente anidado debe estar asociado con un elemento con nombre de Excel.

### <a name="template-import"></a>Importar plantilla

Puede elegir **Importar desde Excel** en la pestaña **Importar** del panel Acciones para importar una nueva plantilla en un formato ER en blanco. En este ejemplo, se creará automáticamente un componente **Archivo\\Excel** y se le adjuntará la plantilla importada. Todos los componentes de ER necesarios también se crearán automáticamente, en función de la lista de elementos con nombre de Excel que se descubran.

![Selección de Importar desde Excel.](./media/er-excel-format-import-template.png)

> [!NOTE]
> Si quiere crear el elemento opcional **Hoja** en el formato ER editable, establezca la opción **Crear elemento de formato de hoja de Excel** en **Sí**.

## <a name="sheet-component"></a>Componente de hoja

El componente **Hoja** indica una hoja de trabajo del libro de Excel adjunto que debe completarse. El nombre de la hoja de trabajo de una plantilla de Excel se define en la propiedad **Hoja** de este componente.

> [!NOTE]
> Este componente es opcional para los libros de Excel que contienen una sola hoja de trabajo.

En la pestaña **Asignación** del diseñador de operación ER, puede configurar la propiedad **Habilitado** de un componente **Hoja** para especificar si el componente debe colocarse en un documento generado:

- Si una expresión de la propiedad **Habilitado** se configura para devolver **Verdadero** en tiempo de ejecución, o si no hay ninguna expresión configurada, la hoja de trabajo apropiada se colocará en el documento generado.
- Si una expresión de la propiedad **Habilitado** está configurada para devolver **Falso** en tiempo de ejecución, el documento generado no contendrá una hoja de trabajo.

![Ejemplo de un componente de hoja.](./media/er-excel-format-sheet-component.png)

## <a name="range-component"></a>Componente Rango

### <a name="nested-components"></a>Componentes anidados

#### <a name="data-typing"></a>Tipos de datos

El componente **Rango** puede tener otros componentes ER anidados que se usan para introducir valores en los rangos apropiados.

- Si algún componente del grupo **Texto** se usa para introducir valores, el valor se introduce en un rango de Excel como un valor de texto.

    > [!NOTE]
    > Use este patrón para formatear los valores introducidos en función de la configuración regional definida en la aplicación.

- Si el componente **Celda** del grupo **Excel** se usa para Introducir valores, el valor se introduce en un rango de Excel como un valor del tipo de datos que se define mediante el vínculo de ese componente **Celda**. Por ejemplo, el tipo de datos podría ser **Cadena**, **Real**, o **Entero**.

    > [!NOTE]
    > Use este patrón para permitir que la aplicación Excel formatee los valores introducidos en función de la configuración regional del equipo local que abre el documento resultante.

#### <a name="row-handling"></a>Gestión de fila

El componente **Rango** se puede configurar como replicado verticalmente, de modo que se generen varias filas en una hoja de cálculo de Excel. Las filas pueden ser generadas por el componente **Rango** principal o por sus componentes **Rango** anidados.

En la versión 10.0.26 y posteriores, puede forzar una hoja de trabajo generada para mantener las filas generadas en la misma página. En el diseñador de formato ER, configure la opción **Mantener las filas juntas** a **Sí** para el componente principal **Rango** en el formato ER editable. Luego, ER intentará mantener todo el contenido generado por ese rango en la misma página. Si la altura del contenido excede el espacio restante en la página actual, se agregará un salto de página y el contenido comenzará en la parte superior de la siguiente página nueva.

> [!NOTE]
> Le recomendamos que configure la opción **Mantener las filas juntas** solo para rangos que abarcan todo el ancho de un documento generado.
>
> La opción **Mantener las filas juntas** es aplicable sólo a componentes **Excel \> Archivo** que están configurados para usar una plantilla de libro de Excel.
>
> La opción **Mantener las filas juntas** puede usarse solo cuando la característica **Habilitar el uso de la biblioteca EPPlus en el marco de informes electrónicos** está habilitada.
>
> Esta función se puede utilizar para componentes **Rango** que residen bajo el componente **Página**. Sin embargo, no hay garantía de que los [totales de pie de página](er-paginate-excel-reports.md#add-data-sources-to-calculate-page-footer-totals) se calculen correctamente utilizando orígenes de datos de [Recopilación de datos](er-data-collection-data-sources.md) .

Para aprender a usar esta opción, siga los pasos de ejemplo en [Diseñe un formato ER para mantener las filas juntas en la misma página de Excel](er-keep-excel-rows-together.md).

### <a name="replication"></a>Réplica

La propiedad **Dirección de replicación** especifica si un rango se repetirá y cómo lo hará en un documento generado:

- **Sin replicación** – El rango de Excel adecuado no se repetirá en el documento generado.
- **Vertical** – El rango de Excel adecuado se repetirá verticalmente en el documento generado. Cada rango replicado se colocará debajo del rango original en una plantilla de Excel. El número de repeticiones se define por el número de registros de un origen de datos del tipo de **Lista de registros** que está vinculado a este componente ER.
- **Horizontal** – El rango de Excel adecuado se repetirá horizontalmente en el documento generado. Cada rango replicado se colocará a la derecha del rango original en una plantilla de Excel. El número de repeticiones se define por el número de registros de un origen de datos del tipo de **Lista de registros** que está vinculado a este componente ER.

    Para obtener más información sobre la replicación horizontal, siga los pasos de [Usar rangos expandibles horizontalmente para agregar columnas dinámicamente en informes de Excel](tasks/er-horizontal-1.md).

### <a name="enabling"></a>Habilitando

En la pestaña **Asignación** del diseñador de operación ER, puede configurar la propiedad **Habilitado** de un **Rango** para especificar si el componente debe colocarse en un documento generado:

- Si una expresión de la propiedad **Habilitado** se configura para devolver **Verdadero** en tiempo de ejecución, o si no hay ninguna expresión configurada, el rango apropiado se rellenará en el documento generado.
- Si una expresión de la propiedad **Habilitado** se configura para devolver **Falso** en tiempo de ejecución, y si este rango no representa las filas o columnas completas, el rango apropiado no se rellenará en el documento generado.
- Si una expresión de la propiedad **Habilitado** se configura para devolver **Falso** en tiempo de ejecución, y si este rango representa las filas o columnas completas, el documento generado contendrá esas filas y columnas como filas y columnas ocultas.

### <a name="resizing"></a>Cambiar tamaño

Puede configurar su plantilla de Excel para usar celdas para presentar datos textuales. Para asegurarse de que todo el texto de una celda sea visible en un documento generado, puede configurar esa celda para que ajuste automáticamente el texto dentro de ella. También puede configurar la fila que contiene esa celda para ajustar automáticamente su altura si el texto ajustado no es completamente visible. Para obtener más información, consulte la sección "Ajustar texto en una celda" en [Corregir datos que se cortan en celdas](https://support.microsoft.com/office/fix-data-that-is-cut-off-in-cells-e996e213-6514-49d8-b82a-2721cef6144e).

> [!NOTE]
> Debido a una conocida [Limitación de Excel](https://support.microsoft.com/topic/you-cannot-use-the-autofit-feature-for-rows-or-columns-that-contain-merged-cells-in-excel-34b54dd7-9bfc-6c8f-5ee3-2715d7db4353), incluso si configura celdas para ajustar el texto, y configura las filas que contienen esas celdas para ajustar automáticamente su altura para ajustarse al texto ajustado, es posible que no pueda utilizar las características **Autoajuste** y **Ajustar texto** de Excel para celdas combinadas y las filas que las contienen. 

A partir de Dynamics 365 Finance versión 10.0.23, puede forzar a ER a calcular, en un documento generado, la altura de cada fila que se configuró para ajustar automáticamente su altura al contenido de las celdas anidadas siempre que esa fila contenga al menos una celda combinada que se configuró para ajustar el texto que contiene. La altura calculada se utiliza para cambiar el tamaño de la fila y garantizar que todas las celdas de la fila sean visibles en el documento generado. Para comenzar a usar esta funcionalidad cuando ejecuta cualquier formato de ER que se configuró para usar plantillas de Excel para generar documentos salientes, siga estos pasos.

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones localizadas**, en la sección **Vínculos relacionados**, seleccione **Parámetros de informes electrónicos**.
3. En la página **Parámetros de informes electrónicos**, en la pestaña **Tiempo de ejecución**, establezca la opción **Ajustar automáticamente alto de fila** en **Sí**.

Cuando desee cambiar esta regla para un solo formato de ER, actualice la versión de borrador de ese formato siguiendo estos pasos.

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. En la página **Configuraciones de localización**, en la sección **Configuraciones**, seleccione **Configuraciones de informes**.
3. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, seleccione una configuración de ER que esté diseñada para usar una plantilla de Excel para generar documentos salientes.
4. En la ficha desplegable **Versiones**, seleccione la versión de configuración que tenga un estado de **Borrador**.
5. En el panel de acciones, haga clic en **Diseñador**.
6. En la página **Diseñador de formatos**, en el árbol de formato del panel izquierdo, seleccione el componente de Excel que está vinculado a una plantilla de Excel.
7. En la pestaña **Formato**, en el campo **Ajustar altura de fila**, seleccione un valor para especificar si se debe forzar a ER, en tiempo de ejecución, a cambiar la altura de las filas en un documento saliente generado por el formato de ER editado:

    - **Predeterminada** - Utilice la configuración general que está configurada en el campo **Ajuste automático de altura de fila** en la página **Parámetros de informes electrónicos**.
    - **Sí** - Reemplace la configuración general y cambie la altura de la fila en tiempo de ejecución.
    - **No** - Reemplace la configuración general y no cambie la altura de la fila en tiempo de ejecución.

## <a name="cell-component"></a>Componente Celda

El componente **Celda** se utiliza para rellenar celdas, formas e imágenes con nombre de Excel. Para indicar un objeto con nombre de Excel que debe rellenarse mediante un completar un componente ER **Celda**, debe especificarse el nombre de ese objeto en la propiedad **Rango de Excel** del componente **Celda**.

En la pestaña **Asignación** del diseñador de operación ER, puede configurar la propiedad **Habilitado** de un componente **Celda** para especificar si el objeto debe rellenarse en un documento generado:

- Si una expresión de la propiedad **Habilitado** se configura para devolver **Verdadero** en tiempo de ejecución, o si no hay ninguna expresión configurada, el objeto apropiado se rellenará en el documento generado. La vinculación de este componente **Celda** especifica un valor que se coloca en el objeto apropiado.
- Si una expresión de la propiedad **Habilitado** está configurada para devolver **Falso** en tiempo de ejecución, el objeto apropiado no se rellenará en el documento generado.

Cuando un componente **Celda** está configurado para Introducir un valor en una celda, puede vincularse con una fuente de datos que devuelve el valor de un tipo de datos primitivo (por ejemplo, **Cadena**, **Real** o **Entero**). En este caso, el valor se introduce en la celda como un valor del mismo tipo de datos.

Cuando un componente **Celda** está configurado para Introducir un valor en formato de Excel, puede vincularse con un origen de datos que devuelve un valor de un tipo de datos primitivo (por ejemplo, **Cadena**, **Real** o **Entero**). En este caso, el valor se introduce en la forma de Excel como texto de dicha forma. Para valores de tipos de datos que no son **Cadena**, la conversión a texto se realiza automáticamente.

> [!NOTE]
> Puedes configurar un componente **Celda** para rellenar una forma solo en los casos en que se admite una propiedad de texto de forma.

Cuando un componente **Celda** está configurado para Introducir un valor en una imagen de Excel, puede vincularse con un origen de datos que devuelve un valor del tipo de datos **Contenedor** que representa una imagen en formato binario. En este caso, el valor se introduce en la imagen de Excel como una imagen.

> [!NOTE]
> Se considera que cada imagen y forma de Excel está anclada por su esquina superior izquierda a una celda o rango específico de Excel. Si desea replicar una imagen o forma de Excel, debe configurar la celda o rango al que está anclada como una celda o rango replicados.

Para obtener más información sobre cómo incrustar imágenes y formas, consulte [Incrustar imágenes y formas en documentos que genere utilizando ER](electronic-reporting-embed-images-shapes.md).

## <a name="page-break-component"></a>Componente de salto de página

El componente **PageBreak** obliga a Excel a comenzar una nueva página. Este componente no es necesario cuando desea utilizar la paginación predeterminada de Excel, pero debe usarla cuando desea que Excel siga su formato ER para estructurar la paginación.

## <a name="page-component"></a><a name="page-component"></a>Componente de página

### <a name="overview"></a>Información general

Pueds usar el componente **Página** cuando desee que Excel siga su formato ER y estructura la paginación en un documento saliente generado. Cuando un formato ER ejecuta componentes que están en el componente **Página**, los saltos de página requeridos se agregan automáticamente. Durante este proceso, se consideran el tamaño del contenido generado, la configuración de página de la plantilla de Excel y el tamaño del papel seleccionado en la plantilla de Excel.

Si debe dividir un documento generado en diferentes secciones, cada una de las cuales tiene una paginación diferente, puede configurar varios componentes de **Página** en cada componente de [Hoja](er-fillable-excel.md#sheet-component).

### <a name="structure"></a><a name="page-component-structure"></a>Estructura

Si el primer componente del componente **Página** es un componente [Rango](er-fillable-excel.md#range-component) donde la propiedad **Dirección de replicación** está establecida en **Sin replicación**, este rango se considera el encabezado de página para la paginación que se basa en la configuración del componente **Página**. El rango de Excel que está asociado con este componente de formato se repite en la parte superior de cada página que se genera mediante el uso de la configuración del componente actual de **Página**.

> [!NOTE]
> Para una correcta paginación, si el rango [Filas a repetir en la parte superior](https://support.microsoft.com/office/repeat-specific-rows-or-columns-on-every-printed-page-0d6dac43-7ee7-4f34-8b08-ffcc8b022409) está configurado en su plantilla de Excel, la dirección de este rango de Excel debe ser igual a la dirección del rango de Excel que está asociado con el componente **Distancia** anteriormente descrito.

Si el último componente del componente **Página** es un componente **Rango** donde la propiedad **Dirección de replicación** está establecida en **Sin replicación**, este rango se considera el pie de página para la paginación que se basa en la configuración del componente **Página**. El rango de Excel que está asociado con este componente de formato se repite en la parte inferior de cada página que se genera mediante el uso de la configuración del componente actual de **Página**.

> [!NOTE]
> Para una correcta paginación, los rangos de Excel que están asociados con los componentes **Rango** no se deben cambiar de tamaño en tiempo de ejecución. No recomendamos que formatee las celdas de este rango utilizando las [Opciones](https://support.microsoft.com/office/wrap-text-in-a-cell-2a18cff5-ccc1-4bce-95e4-f0d4f3ff4e84) de Excel **Ajustar texto en una celda** y **Ajuste automático de la altura de la fila**.

Puede agregar varios otros componentes **Rango** entre los componentes opcionales de **Rango** para especificar cómo se completa un documento generado.

Si el conjunto de componentes anidados **Rango**, en el componente **Página**, no cumple con la estructura descrita anteriormente, se produce un [error](er-components-inspections.md#i17) de validación en tiempo de diseño, en el diseñador de formato ER. El mensaje de error le informa que el problema puede causar problemas en tiempo de ejecución.

> [!NOTE]
> Para generar una salida correcta, no especifique un enlace para ningún **Rango** en el componente **Página** si la propiedad **Dirección de replicación** para ese componente **Rango** está configurada en **Sin replicación** y el rango está configurado para generar encabezados o pies de página.

Si desea que la suma y el recuento relacionados con la paginación calculen los totales acumulados y los totales por página, le recomendamos que configure los orígenes de datos de [Recopilación de datos](er-data-collection-data-sources.md). Para aprender a usar el componente **Página** para paginar un documento Excel generado, complete los procedimientos de [Diseñar un formato ER para paginar un documento generado en formato Excel](er-paginate-excel-reports.md).

### <a name="limitations"></a><a name="page-component-limitations"></a>Limitaciones

Cuando usa el componente **Página** para la paginación de Excel, no sabrá el número final de páginas de un documento generado hasta que se complete la paginación. Por lo tanto, no puede calcular el número total de páginas utilizando fórmulas ER ni imprimir el número correcto de páginas de un documento generado en cualquier página antes de la última página.

> [!TIP]
> Para lograr este resultado en un encabezado o pie de página de Excel, puede usar el [formato](/office/vba/excel/concepts/workbooks-and-worksheets/formatting-and-vba-codes-for-headers-and-footers) Excel especial para encabezados y pies de página.

Los componentes **Página** configurados no se tienen en cuenta al actualizar una plantilla de Excel en formato editable en la versión 10.0.22 de Dynamics 365 Finance. Esta funcionalidad se considera para futuras versiones de Finance.

Si configura su plantilla de Excel para usar [formato condicional](/office/dev/add-ins/excel/excel-add-ins-conditional-formatting), es posible que no funcione como se esperaba en algunos casos.

### <a name="applicability"></a>Aplicabilidad

El componente **Página** funciona para el componente de formato de [archivo Excel](er-fillable-excel.md#excel-file-component) solo cuando ese componente está configurado para usar una plantilla en Excel. Si se [reemplaza](tasks/er-design-configuration-word-2016-11.md) la plantilla de Excel con una plantilla de Word y luego se ejecuta el formato ER editable, se ignorará el componente **Página**.

El componente **Página** funciona solo cuando la característica **Habilitar el uso de la biblioteca EPPlus en el marco de informes electrónicos** está habilitada. Se lanza una excepción en tiempo de ejecución si ER intenta procesar el componente **Página** mientras esta función está desactivada.

> [!NOTE]
> Se lanza una excepción en tiempo de ejecución si un formato ER procesa el componente **Página** de una plantilla de Excel que contiene al menos una fórmula que hace referencia a una celda que no es válida. Para ayudar a evitar errores en tiempo de ejecución, corrija la plantilla de Excel como se describe en [Cómo corregir un error #REF!](https://support.microsoft.com/office/how-to-correct-a-ref-error-822c8e46-e610-4d02-bf29-ec4b8c5ff4be).

## <a name="footer-component"></a>Componente de pie de página

El componente **Pie de página** se usa para completar pies de página en la parte inferior de una hoja de trabajo generada en un libro de Excel.

> [!NOTE]
> Puede agregar este componente para cada componente de **Hoja** para especificar diferentes pies de página para diferentes hojas de cálculo en un libro de Excel generado.

Cuando configura un componente de **Pie de página** individual, puede utilizar la propiedad **Apariencia del encabezado/pie de página** para especificar las páginas para las que se utiliza el componente. Los siguientes valores están disponibles:

- **Cualquiera**: ejecuta el componente configurado de **Pie de página** para cualquier página de la hoja de cálculo de Excel primaria.
- **Primera**: ejecuta el componente configurado de **Pie de página** para solo la primera página de la hoja de cálculo de Excel primaria.
- **Par**: ejecuta el componente configurado de **Pie de página** para solo las páginas pares de la hoja de cálculo de Excel primaria.
- **Impar**: ejecuta el componente configurado **Pie de página** para solo las páginas impares de la hoja de cálculo de Excel primaria.

Por un único componente de **Hoja**, puede agregar varios componentes de **Pie de página** teniendo cada uno de ellos un valor diferente para la propiedad **Apariencia del encabezado/pie de página**. De esta manera, puede generar diferentes pies de página para diferentes tipos de páginas en una hoja de cálculo de Excel.

> [!NOTE]
> Asegúrese de que cada componente de **Pie de página** que agregue a un único componente de **Pie de página** tenga un valor diferente para la propiedad **Apariencia del encabezado/pie de página**. De lo contrario, se producirá un [Error de validacion](er-components-inspections.md#i16). El mensaje de error que recibe le notifica de la incoherencia.

En el componente **Pie de página**, agregue los componentes anidados requeridos de **Texto\\Cadena**, **Texto\\Fecha y hora** u otro tipo. Configure los enlaces de esos componentes para especificar cómo se rellena el pie de página de su página.

También puede utilizar [códigos de formato](/office/vba/excel/concepts/workbooks-and-worksheets/formatting-and-vba-codes-for-headers-and-footers) especiales para formatear correctamente el contenido de un pie de página generado. Para aprender a usar este enfoque, siga los pasos del [Ejemplo 1](#example-1), más adelante en este tema.

> [!NOTE]
> Cuando configure formatos ER, asegúrese de considerar el [límite](https://support.microsoft.com/office/excel-specifications-and-limits-1672b34d-7043-467e-8e27-269d656771c3) y el número máximo de caracteres para un solo encabezado o pie de página que exista en Excel.

## <a name="header-component"></a>Componente de encabezado

El componente **Encabezado** se usa para completar encabezados en la parte superior de una hoja de trabajo generada en un libro de Excel. Se usa como el componente **Pie de página**.

## <a name="edit-an-added-er-format"></a>Editar un formato ER agregado

### <a name="update-a-template"></a>Actualizar una plantilla

Puede elegir **Actualizar desde Excel** en la pestaña **Importar** del panel Acciones para importar una plantilla actualizada en un formato ER editable. Durante este proceso, una plantilla del componente **Archivo\\Excel** se reemplazará por una nueva plantilla. El contenido del formato ER editable se sincronizará con el contenido de la plantilla ER actualizada.

- Se creará automáticamente un nuevo componente de formato ER para cada nombre de Excel si el componente de formato ER no se encuentra en el formato editable.
- Todos los componentes del formato ER se eliminarán del formato ER editable si no se encuentra su nombre de Excel apropiado.

> [!NOTE]
> Establezca la opción **Crear elemento de formato de hoja Excel** en **Sí** cuando quiera crear el elemento opcional **Hoja** en el formato ER editable.
>
> Si el formato ER editable originalmente contenía elementos **Hoja**, se recomienda que configure la opción **Crear elemento de formato de hoja de Excel** en **Sí** cuando importe una plantilla actualizada. De lo contrario, todos los elementos anidados del elemento **Hoja** original se crearán desde cero. Por lo tanto, todos los vínculos de los elementos de formato recreados se perderán en el formato ER actualizado.

![Opción Crear elemento de formato de hoja de Excel en el cuadro de diálogo Actualizar desde Excel.](./media/er-excel-format-update-template.png)

Para obtener más información sobre esta función, siga los pasos de [Modificar formatos de informes electrónicos volviendo a aplicar plantillas de Excel](modify-electronic-reporting-format-reapply-excel-template.md).

## <a name="validate-an-er-format"></a>Validar un formato ER

Cuando valida un formato ER que se puede editar, se realiza una comprobación de coherencia para asegurarse de que el nombre de Excel esté presente en la plantilla de Excel que se utiliza actualmente. Se le notificará sobre cualquier incoherencia. Para algunas incoherencias, se ofrecerá la opción de solucionar problemas automáticamente.

![Mensaje de error de validación.](./media/er-excel-format-validate.png)

## <a name="control-the-calculation-of-excel-formulas"></a>Controlar el cálculo de fórmulas de Excel

Cuando se genera el formato de libro de trabajo en un documento saliente en un Microsoft Excel, algunas celdas de este documento pueden contener fórmulas de Excel. Cuando la función **Habilitar el uso de la biblioteca EPPlus en el marco de informes electrónicos** está habilitada, puede controlar cuándo se calculan las fórmulas cambiando el valor del [parámetro](https://support.microsoft.com/office/change-formula-recalculation-iteration-or-precision-in-excel-73fc7dac-91cf-4d36-86e8-67124f6bcce4#ID0EAACAAA=Windows) **Opciones de cálculo** en la plantilla de Excel que se está utilizando:

- Seleccione **Automático** para volver a calcular todas las fórmulas dependientes cada vez que se agregan a un documento generado nuevos rangos, celdas, etc.

    > [!NOTE]
    > Esto puede causar un problema de rendimiento para las plantillas de Excel que contienen varias fórmulas relacionadas.

- Seleccione **Manual** para evitar el recálculo de fórmulas cuando se genera un documento.

    > [!NOTE]
    > El recálculo de fórmulas se fuerza manualmente cuando un documento generado se abre para obtener una vista previa con Excel.
    > No use esta opción si configura un destino de ER que asume el uso de un documento generado sin su vista previa en Excel (conversión de PDF, envío de correo electrónico, etc.) porque el documento generado podría no contener valores en celdas que contienen fórmulas.

## <a name="example-1-format-footer-content"></a><a name="example-1"></a>Ejemplo 1: dar formato al contenido del pie de página

1. Utilice las configuraciones de ER proporcionadas para [generar](er-generate-printable-fti-forms.md) un documento imprimible de factura de texto libre (FTI).
2. Revise el pie de página del documento generado. Observe que contiene información sobre el número de página actual y el número total de páginas del documento.

    ![Revisar el pie de página de un documento generado en formato Excel.](./media/er-fillable-excel-footer-1.gif)

3. En el diseñador de formatos ER, [abra](er-generate-printable-fti-forms.md#features-that-are-implemented-in-the-sample-er-format) el formato de muestra de ER para su revisión.

    El pie de página de la hoja de cálculo **Factura** se genera en función de la configuración de dos componentes de **Cadena** que residen en el componente **Pie de página**:

    - El primer componente de **Cadena** completa los siguientes códigos de formato especiales para obligar a Excel a aplicar un formato específico:

        - **&C**: alinear el texto del pie de página en el centro.
        - **&"Segoe UI, Regular"&8**: presentar el texto del pie de página en fuente "Segoe UI Regular" con un tamaño de 8 puntos.

    - El segundo componente de **Cadena** completa el texto que contiene el número de página actual y el número total de páginas del documento actual.

    ![Revisar el componente de formato ER de pie de página en la página Diseñador de formato.](./media/er-fillable-excel-footer-2.png)

4. Personalice el formato ER de ejemplo para modificar el pie de página actual:

    1. [Cree](er-quick-start2-customize-report.md#DeriveProvidedFormat) un formato ER derivado **Factura de servicios (Excel) pesonalizada** que se basa en el formato ER de ejemplo.
    2. Agregue el primer par nuevo de componentes de **Cadena** para el componente de **Pie de página** de la hoja de cálculo **Factura**:

        1. Agregue un componente de **Cadena** que alinee el nombre de la empresa a la izquierda y lo presente con fuente de 8 puntos "Segoe UI Regular" (**"&L&"Segoe UI, Regular"&8"**).
        2. Agregue un componente de **Cadena** que completa el nombre de la empresa (**model.InvoiceBase.CompanyInfo.Name**).

    3. Agregue el segundo par nuevo de componentes de **Cadena** para el componente de **Pie de página** de la hoja de cálculo **Factura**:

        1. Agregue un componente de **Cadena** que alinee la fecha de procesamiento a la derecha y lo presente con fuente de 8 puntos "Segoe UI Regular" (**"&R&"Segoe UI, Regular"&8"**).
        2. Agregue un componente de **Cadena** que completa la fecha de procesamiento en formato personalizado (**"&nbsp;"&DATEFORMAT(SESSIONTODAY(), "yyyy-MM-dd")**).

        ![Revisión del componente de formato ER de pie de página en la página Diseñador de formato.](./media/er-fillable-excel-footer-3.png)

    4. [Complete](er-quick-start2-customize-report.md#CompleteDerivedFormat) la versión de borrador del formato ER derivado **Factura de servicios (Excel) personalizada**.

5. [Configure](er-generate-printable-fti-forms.md#configure-print-management) la gestión de impresión para utilizar el formato ER derivado **Factura de servicios (Excel) personalizada** en lugar del formato ER de ejemplo.
6. Genere un documento FTI imprimible y revise el pie de página del documento generado.

    ![Revisión del pie de página de un documento generado en formato Excel.](./media/er-fillable-excel-footer-4.gif)

## <a name="example-2-fixing-the-merged-cells-epplus-issue"></a><a name="example-2"></a>Ejemplo 2: solucionar el problema de EPPlus de celdas fusionadas

Puede ejecutar un formato ER para generar un documento saliente en un formato de libro de Excel. Cuando la característica **Habilitar el uso de la biblioteca EPPlus en el marco de informes electrónicos** está habilitada en el espacio de trabajo **Administración de características**, la [biblioteca EPPlus](https://www.nuget.org/packages/epplus/4.5.2.1) se utiliza para generar resultados en Excel. Sin embargo, debido al [comportamiento de Excel](https://answers.microsoft.com/msoffice/forum/all/deleting-a-range-of-cells-that-includes-merged/8601462c-4e2c-48e0-bd23-848eecb872a9) conocido y una limitación de la biblioteca EPPlus, es posible que encuentre la siguiente excepción: "No se pueden eliminar/sobrescribir las celdas combinadas. Un rango se fusiona parcialmente con el otro rango combinado". Para saber qué tipo de plantillas de Excel pueden causar esta excepción y cómo puede solucionar el problema, complete el siguiente ejemplo.

1. En la aplicación de escritorio de Excel, cree un nuevo libro de Excel.
2. En la hoja de trabajo **Hoja1**, agregue el nombre **ReportTitle** a la celda **A2**.
3. Combine las celdas **A1** y **A2**.

    ![Revise los resultados de la combinación de las celdas A1 y A2 en el libro de Excel diseñado en la aplicación de escritorio de Excel.](./media/er-fillable-excel-example2-1.png)

3. En la página **Configuraciones**, [agregue un nuevo formato de ER](er-fillable-excel.md#add-a-new-er-format) para generar un documento saliente en formato de libro de Excel.
4. En la página **Diseñador de formato**, [importe](er-fillable-excel.md#template-import) el libro de Excel diseñado en el formato ER agregado como una nueva plantilla para documentos salientes.
5. En la pestaña **Asignación**, configure el enlace para el componente **ReportTitle** componente del tipo [Celda](er-fillable-excel.md#cell-component).
6. Ejecute el formato ER configurado. Observe que se lanza la siguiente excepción: "No se pueden eliminar/sobrescribir las celdas combinadas. Un rango se fusiona parcialmente con el otro rango combinado".

    ![Revise los resultados de ejecutar el formato ER configurado en la página del diseñador de formatos.](./media/er-fillable-excel-example2-2.png)

Puede solucionar el problema de una de las siguientes formas:

- **Más fácil pero no recomendada:** en el espacio de trabajo **Administración de características**, desactive la característica **Habilitar el uso de la biblioteca EPPlus en el marco de informes electrónicos**. Aunque este enfoque es más fácil, es posible que experimente otros problemas si lo usa, porque algunas funciones de ER solo son compatibles cuando la característica **Habilitar el uso de la biblioteca EPPlus en el marco de informes electrónicos** está habilitada.
- **Recomendada:** siga estos pasos:

    1. En la aplicación de escritorio de Excel, modifique el libro de Excel de una de las siguientes formas:

        - En la hoja de trabajo **Hoja1**, separe las celdas **A1** y **A2**.
        - Cambie la referencia por el nombre **ReportTitle** de **=Sheet1!$A$2** a **=Sheet1!$A$1**.

        ![Revise los resultados del cambio de la referencias en el libro de Excel diseñado en la aplicación de escritorio de Excel.](./media/er-fillable-excel-example2-3.png)

    2. En la página **Diseñador de formato**, [importe](er-fillable-excel.md#template-import) el libro de Excel modificado en el formato ER editable para actualizar la plantilla existente.
    3. Ejecute el formato de ER modificado.

        ![Revise el documento generado en la aplicación de escritorio de Excel.](./media/er-fillable-excel-example2-4.png)

## <a name="limitations"></a>Limitaciones

### <a name="known-epplus-library-limitations"></a>Limitaciones conocidas de la biblioteca EPPlus

#### <a name="external-data-sources"></a>Orígenes de datos externos

Si una de sus plantillas contiene una tabla dinámica basada en un modelo de PowerPivot que se refiere a una [fuente de datos externa](https://support.microsoft.com/office/create-a-pivottable-with-an-external-data-source-db50d01d-2e1c-43bd-bfb5-b76a818a927b) y **Habilitar el uso de la biblioteca EPPlus en el marco de informes electrónicos** está habilitado, recibe el siguiente mensaje de error cuando ejecuta un formato ER que usa esa plantilla para generar un documento saliente en formato Excel: "La fuente de caché no es una hoja de cálculo". Para solucionar este problema, tiene las siguientes opciones:

- **Recomendado:** Rediseñe la solución de Excel que está utilizando:

    1. Aísle la parte que contiene pivotes en un libro de Excel separado (libro de trabajo A). 
    2. Utilice ER para generar un segundo libro de Excel (libro de trabajo B) de Finanzas que tenga los detalles requeridos. 
    3. Consulte el libro de trabajo B en el libro de trabajo A tan pronto como se genere el libro de trabajo B.

- Desactive la característica **Habilitar el uso de la biblioteca EPPlus en el marco de informes electrónicos** para usar una opción que no sea EPPlus. 

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los informes electrónicos](general-electronic-reporting.md)

[Diseñar una configuración para generar informes en formato OPENXML](tasks\er-design-reports-openxml-2016-11.md)

[Modificar formatos de informes electrónicos al aplicar de nuevo plantillas de Excel](modify-electronic-reporting-format-reapply-excel-template.md)

[Usar rangos expandibles horizontalmente para agregar columnas dinámicamente en informes de Excel](tasks/er-horizontal-1.md)

[Insertar imágenes y formas en los documentos generados con ER](electronic-reporting-embed-images-shapes.md)

[Configurar informes electrónicos (ER) para proporcionar datos a Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
