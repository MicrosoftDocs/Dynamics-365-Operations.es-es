---
title: Diseñar una configuración para generar documentos en formato de Excel
description: Este tema describe cómo diseñar un formato de informe electrónico (ER) para completar una plantilla de Excel y luego generar resultados en forma de documentos en formato Excel.
author: NickSelin
ms.date: 03/10/2021
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
ms.openlocfilehash: 1c8d939fef4fd0f9e189ca37318c2c0306511785
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893917"
---
# <a name="design-a-configuration-for-generating-documents-in-excel-format"></a>Diseñar una configuración para generar documentos en formato Excel

[!include[banner](../includes/banner.md)]

Puede diseñar una configuración de formato de [Informe electrónico (ER)](general-electronic-reporting.md) con un [componente de formato](general-electronic-reporting.md#FormatComponentOutbound) ER que puede configurar para generar un documento resultante en un formato de libro de trabajo de Microsoft Excel. Se deben usar componentes de formato ER específicos para este propósito.

Para obtener más información sobre esta función, siga los pasos del tema [Diseñar una configuración para generar informes en formato OPENXML](tasks/er-design-reports-openxml-2016-11.md).

## <a name="add-a-new-er-format"></a>Agregar un nuevo formato ER

Cuando agrega una nueva configuración de formato ER para generar un documento resultante en un formato de libro de Excel, debe seleccionar el valor **Sobresalir** para el atributo del formato **Tipo de formato** o dejar el atributo **Tipo de formato** en blanco.

- Si selecciona **Excel**, puede configurar el formato para generar un documento resultante solo en formato Excel.
- Si deja el atributo en blanco, puede configurar el formato para generar un documento saliente en cualquier formato que sea compatible con el marco ER.

Para configurar el componente de formato ER de la configuración, seleccione **Diseñador** en el panel Acciones y abra el componente de formato ER para editarlo en el diseñador de operaciones ER.

![Página Configuraciones](./media/er-excel-format-add-format.png)

## <a name="excel-file-component"></a>Componente de archivo de Excel

### <a name="manual-entry"></a>Entrada manual

Debe agregar un componente **Archivo\\Excel** al formato ER configurado para generar un documento resultante en formato Excel.

![Componente Excel\archivo](./media/er-excel-format-add-file-component.png)

Para especificar el diseño del documento resultante, adjunte un libro de Excel que tenga la extensión .xlsx al componente **Archivo\\Excel** como plantilla para documentos resultantes.

> [!NOTE]
> Cuando adjunte una plantilla manualmente, debe usar un [tipo de documento](../../../fin-ops-core/fin-ops/organization-administration/configure-document-management.md#configure-document-types) que se haya configurado para ese fin en los [parámetros ER](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents).

![Adición de un archivo adjunto al componente Excel\archivo](./media/er-excel-format-add-file-component2.png)

Para especificar cómo se rellenará la plantilla adjunta cuando ejecute el formato ER configurado, debe agregar componentes **Hoja**, **Rango** y **Celda** al componente **Archivo\\Excel**. Cada componente anidado debe estar asociado con un elemento con nombre de Excel.

### <a name="template-import"></a>Importar plantilla

Puede elegir **Importar desde Excel** en la pestaña **Importar** del panel Acciones para importar una nueva plantilla en un formato ER en blanco. En este ejemplo, se creará automáticamente un componente **Archivo\\Excel** y se le adjuntará la plantilla importada. Todos los componentes de ER necesarios también se crearán automáticamente, en función de la lista de elementos con nombre de Excel que se descubran.

![Selección de Importar desde Excel](./media/er-excel-format-import-template.png)

> [!NOTE]
> Si quiere crear el elemento opcional **Hoja** en el formato ER editable, establezca la opción **Crear elemento de formato de hoja de Excel** en **Sí**.

## <a name="sheet-component"></a>Componente de hoja

El componente **Hoja** indica una hoja de trabajo del libro de Excel adjunto que debe completarse. El nombre de la hoja de trabajo de una plantilla de Excel se define en la propiedad **Hoja** de este componente.

> [!NOTE]
> Este componente es opcional para los libros de Excel que contienen una sola hoja de trabajo.

En la pestaña **Asignación** del diseñador de operación ER, puede configurar la propiedad **Habilitado** de un componente **Hoja** para especificar si el componente debe colocarse en un documento generado:

- Si una expresión de la propiedad **Habilitado** se configura para devolver **Verdadero** en tiempo de ejecución, o si no hay ninguna expresión configurada, la hoja de trabajo apropiada se colocará en el documento generado.
- Si una expresión de la propiedad **Habilitado** está configurada para devolver **Falso** en tiempo de ejecución, el documento generado no contendrá una hoja de trabajo.

![Ejemplo de un componente de hoja](./media/er-excel-format-sheet-component.png)

## <a name="range-component"></a>Componente Rango

El componente **Rango** indica un rango de Excel que debe controlarse mediante este componente ER. El nombre del rango se define en la propiedad **Rango de Excel** de este componente.

La propiedad **Dirección de replicación** especifica si el rango se repetirá y cómo lo hará en un documento generado:

- Si la propiedad **Dirección de replicación** se establece en **Sin replicación**, el rango de Excel apropiado no se repetirá en el documento generado.
- Si la propiedad **Dirección de replicación** se establece en **Vertical**, el rango de Excel apropiado se repetirá en el documento generado. Cada rango replicado se coloca debajo del rango original en una plantilla de Excel. El número de repeticiones se define por el número de registros de un origen de datos del tipo de **Lista de registros** que está vinculado a este componente ER.
- Si la propiedad **Dirección de replicación** se establece en **Horizontal**, el rango de Excel apropiado se repetirá en el documento generado. Cada rango replicado se coloca a la derecha del rango original en una plantilla de Excel. El número de repeticiones se define por el número de registros de un origen de datos del tipo de **Lista de registros** que está vinculado a este componente ER.

Para obtener más información sobre la replicación horizontal, siga los pasos de [Usar rangos expandibles horizontalmente para agregar columnas dinámicamente en informes de Excel](tasks/er-horizontal-1.md).

El componente **Rango** puede tener otros componentes ER anidados que se usan para introducir valores en los rangos con nombre de Excel apropiados.

- Si algún componente del grupo **Texto** se usa para introducir valores, el valor se introduce en un rango de Excel como un valor de texto.

    > [!NOTE]
    > Use este patrón para formatear los valores introducidos en función de la configuración regional definida en la aplicación.

- Si el componente **Celda** del grupo **Excel** se usa para Introducir valores, el valor se introduce en un rango de Excel como un valor del tipo de datos que se define mediante el vínculo de ese componente **Celda** (por ejemplo, **Cadena**, **Real** o **Entero**).

    > [!NOTE]
    > Use este patrón para permitir que la aplicación Excel formatee los valores introducidos en función de la configuración regional del equipo local que abre el documento resultante.

En la pestaña **Asignación** del diseñador de operación ER, puede configurar la propiedad **Habilitado** de un **Rango** para especificar si el componente debe colocarse en un documento generado:

- Si una expresión de la propiedad **Habilitado** se configura para devolver **Verdadero** en tiempo de ejecución, o si no hay ninguna expresión configurada, el rango apropiado se rellenará en el documento generado.
- Si una expresión de la propiedad **Habilitado** se configura para devolver **Falso** en tiempo de ejecución, y si este rango no representa las filas o columnas completas, el rango apropiado no se rellenará en el documento generado.
- Si una expresión de la propiedad **Habilitado** se configura para devolver **Falso** en tiempo de ejecución, y si este rango representa las filas o columnas completas, el documento generado contendrá esas filas y columnas como filas y columnas ocultas.

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

![Opción Crear elemento de formato de hoja de Excel en el cuadro de diálogo Actualizar desde Excel](./media/er-excel-format-update-template.png)

Para obtener más información sobre esta función, siga los pasos de [Modificar formatos de informes electrónicos volviendo a aplicar plantillas de Excel](modify-electronic-reporting-format-reapply-excel-template.md).

## <a name="validate-an-er-format"></a>Validar un formato ER

Cuando valida un formato ER que se puede editar, se realiza una comprobación de coherencia para asegurarse de que el nombre de Excel esté presente en la plantilla de Excel que se utiliza actualmente. Se le notificará sobre cualquier incoherencia. Para algunas incoherencias, se ofrecerá la opción de solucionar problemas automáticamente.

![Mensaje de error de validación](./media/er-excel-format-validate.png)

## <a name="control-the-calculation-of-excel-formulas"></a>Controlar el cálculo de fórmulas de Excel

Cuando se genera el formato de libro de trabajo en un documento saliente en un Microsoft Excel, algunas celdas de este documento pueden contener fórmulas de Excel. Cuando la función **Habilitar el uso de la biblioteca EPPlus en el marco de informes electrónicos** está habilitada, puede controlar cuándo se calculan las fórmulas cambiando el valor del [parámetro](https://support.microsoft.com/office/change-formula-recalculation-iteration-or-precision-in-excel-73fc7dac-91cf-4d36-86e8-67124f6bcce4#ID0EAACAAA=Windows) **Opciones de cálculo** en la plantilla de Excel que se está utilizando:

- Seleccione **Automático** para volver a calcular todas las fórmulas dependientes cada vez que se agregan a un documento generado nuevos rangos, celdas, etc.
    >[!NOTE]
    > Esto puede causar un problema de rendimiento para las plantillas de Excel que contienen varias fórmulas relacionadas.
- Seleccione **Manual** para evitar el recálculo de fórmulas cuando se genera un documento.
    >[!NOTE]
    > El recálculo de fórmulas se fuerza manualmente cuando un documento generado se abre para obtener una vista previa con Excel.
    > No use esta opción si configura un destino de ER que asume el uso de un documento generado sin su vista previa en Excel (conversión de PDF, envío de correo electrónico, etc.) porque el documento generado podría no contener valores en celdas que contienen fórmulas.

## <a name="example-1-format-footer-content"></a><a name="example-1"></a>Ejemplo 1: dar formato al contenido del pie de página

1. Utilice las configuraciones de ER proporcionadas para [generar](er-generate-printable-fti-forms.md) un documento imprimible de factura de texto libre (FTI).
2. Revise el pie de página del documento generado. Observe que contiene información sobre el número de página actual y el número total de páginas del documento.

    ![Revisar el pie de página de un documento generado en formato Excel](./media/er-fillable-excel-footer-1.gif)

3. En el diseñador de formatos ER, [abra](er-generate-printable-fti-forms.md#features-that-are-implemented-in-the-sample-er-format) el formato de muestra de ER para su revisión.

    El pie de página de la hoja de cálculo **Factura** se genera en función de la configuración de dos componentes de **Cadena** que residen en el componente **Pie de página**:

    - El primer componente de **Cadena** completa los siguientes códigos de formato especiales para obligar a Excel a aplicar un formato específico:

        - **&C**: alinear el texto del pie de página en el centro.
        - **&"Segoe UI, Regular"&8**: presentar el texto del pie de página en fuente "Segoe UI Regular" con un tamaño de 8 puntos.

    - El segundo componente de **Cadena** completa el texto que contiene el número de página actual y el número total de páginas del documento actual.

    ![Revisar el componente de formato ER de pie de página en la página Diseñador de formato](./media/er-fillable-excel-footer-2.png)

4. Personalice el formato ER de ejemplo para modificar el pie de página actual:

    1. [Cree](er-quick-start2-customize-report.md#DeriveProvidedFormat) un formato ER derivado **Factura de servicios (Excel) pesonalizada** que se basa en el formato ER de ejemplo.
    2. Agregue el primer par nuevo de componentes de **Cadena** para el componente de **Pie de página** de la hoja de cálculo **Factura**:

        1. Agregue un componente de **Cadena** que alinee el nombre de la empresa a la izquierda y lo presente con fuente de 8 puntos "Segoe UI Regular" (**"&L&"Segoe UI, Regular"&8"**).
        2. Agregue un componente de **Cadena** que completa el nombre de la empresa (**model.InvoiceBase.CompanyInfo.Name**).

    3. Agregue el segundo par nuevo de componentes de **Cadena** para el componente de **Pie de página** de la hoja de cálculo **Factura**:

        1. Agregue un componente de **Cadena** que alinee la fecha de procesamiento a la derecha y lo presente con fuente de 8 puntos "Segoe UI Regular" (**"&R&"Segoe UI, Regular"&8"**).
        2. Agregue un componente de **Cadena** que completa la fecha de procesamiento en formato personalizado (**"&nbsp;"&DATEFORMAT(SESSIONTODAY(), "yyyy-MM-dd")**).

        ![Revisión del componente de formato ER de pie de página en la página Diseñador de formato](./media/er-fillable-excel-footer-3.png)

    4. [Complete](er-quick-start2-customize-report.md#CompleteDerivedFormat) la versión de borrador del formato ER derivado **Factura de servicios (Excel) personalizada**.

5. [Configure](er-generate-printable-fti-forms.md#configure-print-management) la gestión de impresión para utilizar el formato ER derivado **Factura de servicios (Excel) personalizada** en lugar del formato ER de ejemplo.
6. Genere un documento FTI imprimible y revise el pie de página del documento generado.

    ![Revisión del pie de página de un documento generado en formato Excel](./media/er-fillable-excel-footer-4.gif)

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de los informes electrónicos](general-electronic-reporting.md)

[Diseñar una configuración para generar informes en formato OPENXML](tasks\er-design-reports-openxml-2016-11.md)

[Modificar formatos de informes electrónicos al aplicar de nuevo plantillas de Excel](modify-electronic-reporting-format-reapply-excel-template.md)

[Usar rangos expandibles horizontalmente para agregar columnas dinámicamente en informes de Excel](tasks/er-horizontal-1.md)

[Insertar imágenes y formas en los documentos generados con ER](electronic-reporting-embed-images-shapes.md)

[Configurar informes electrónicos (ER) para proporcionar datos a Power BI](general-electronic-reporting-report-configuration-get-data-powerbi.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]