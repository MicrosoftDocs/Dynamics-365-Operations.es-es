---
title: Diseñar las configuraciones de ER para completar las plantillas de PDF
description: Este tema proporciona información acerca de cómo diseñar un informe electrónico (ER) para completar una plantilla de PDF.
author: NickSelin
ms.date: 02/28/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: a568ddd93bfbc7d536e951a13470b3dedb796e1b
ms.sourcegitcommit: 753714ac0dabc4b7ce91509757cd19f7be4a4793
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2022
ms.locfileid: "8367865"
---
# <a name="design-er-configurations-to-fill-in-pdf-templates"></a>Diseñar las configuraciones de ER para completar las plantillas de PDF

[!include[banner](../includes/banner.md)]

Los procedimientos de este tema son los ejemplos de cómo un usuario con la función **Administrador del sistema** o el rol **Desarrollador de informe electrónico** puede configurar un formato de informe electrónico de (ER) que genere informes como archivos PDF usando documentos que se pueden completar como plantillas de informes. Estos pasos se pueden realizar en cualquier empresa de Dynamics 365 Finance o Regulatory Configuration Service (RCS).

## <a name="prerequisites"></a>Requisitos previos

Antes de empezar, debe tener uno de los siguientes tipos de acceso, en función del servicio que use para completar los procedimientos de este tema:

- Acceso a Finance para uno de los roles siguientes:

    - Desarrollador de informes electrónicos
    - Consultor funcional de informes electrónicos
    - Administrador del sistema

- Acceso a RCS para uno de los roles siguientes:

    - Desarrollador de informes electrónicos
    - Consultor funcional de informes electrónicos
    - Administrador del sistema

También debe completar el procedimiento [Crear y activar proveedores de configuración](tasks/er-configuration-provider-mark-it-active-2016-11.md).

Finalmente, descargue los archivos siguientes.

| Descripción del contenido                       | Nombre de archivo                                     |
|-------------------------------------------|-----------------------------------------------|
| Plantilla para la primera página del informe | [IntrastatReportTemplate1.pdf](https://download.microsoft.com/download/0/8/3/0832c82b-4448-4562-afbf-01e0efc8d999/IntrastatReportTemplate1.pdf)                  |
| Plantilla para las otras páginas del informe    | [IntrastatReportTemplate2.pdf](https://download.microsoft.com/download/c/7/a/c7a8a806-2192-4034-9052-e8b84b527d5e/IntrastatReportTemplate2.pdf)                  |
| Formato de ER de ejemplo - PDF                          | [Informe Intrastat (PDF).version.1.1.xm](https://download.microsoft.com/download/a/8/7/a87aea3e-3f60-404c-8899-c471d20e7ea9/IntrastatreportPDFversion1.1.xml)        |
| Formato ER de ejemplo - Excel                          | [Intrastat (importar desde Excel).version.1.1.xml](https://download.microsoft.com/download/a/2/c/a2c0c145-d989-4e55-9d47-9647c02e4ee4/IntrastatimportfromExcelversion1.1.xml) |
| Conjunto de datos de ejemplo                            | [Ejemplo instrastat data.xlsx](https://download.microsoft.com/download/9/f/1/9f1c5b96-3800-475f-8cf6-1ddd42873758/Intrastatsampledata.xlsx)                    |

## <a name="design-the-format-configuration"></a>Diseñar la configuración del formato

### <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a>Obtenga acceso a la lista de configuraciones proporcionada por Microsoft

1. Vaya a **Administración de la organización \> Espacios de trabajo \> Informes electrónicos**.
2. Asegúrese de que el proveedor **Litware, Inc.** está disponible y marcado como activo.
3. En el mosaico para el proveedor **Microsoft**, seleccione **Repositorios**.

    > [!NOTE]
    > Si existe un repositorio del tipo **LCS**, ignore los pasos restantes de este procedimiento.

4. Seleccione **Agregar**.
5. En el cuadro de diálogo desplegable, en el grupo del campo **Tipo de repositorio de configuración**, seleccione la opción **LCS** .
6. Seleccione **Crear repositorio**.
7. Seleccione **Aceptar**.

### <a name="get-the-model-configurations-provided-by-microsoft"></a>Obtenga las configuraciones del modelo proporcionadas por Microsoft

1. En el lado izquierdo de la página **Repositorios de configuración**, seleccione el botón **Mostrar los filtros** (el símbolo de embudo).
2. Agregue un filtro por un valor **LCS** en el campo **Tipo**, y utilice el operador **comienza con** .
3. Seleccionar **Aplicar**.
4. Seleccione **Abrir**.
5. En el árbol, seleccione **Modelo intrastat**.
6. En la ficha desplegable **Versiones**, seleccione la versión **1**.

    > [!NOTE]
    > Si el botón **Importar** en la ficha desplegable **Versiones** no está disponible, omita los pasos restantes de este procedimiento.

7. Seleccione **Importar**.
8. Seleccione **Sí** para confirmar la importación de la versión seleccionada de la configuración **Modelo de Intrastat** .

### <a name="create-a-new-format-configuration"></a>Creación de una configuración de formato nueva

1. En el espacio de trabajo **Informe electrónico**, seleccione el mosaico **Configuraciones de informes** .
2. En el árbol, seleccione **Modelo intrastat**.
3. Seleccionar **Crear configuración**.

    > [!NOTE]
    > Si el botón **Crear configuración** no está disponible, debe activar el modo de diseño en la página **Parámetros de informes electrónicos** que se puede abrir del espacio de trabajo **Informe electrónico** .

4. En el cuadro de diálogo, en el grupo del campo **Nuevo**, seleccione la opción **Formato basado en el modelo de datos Intrastat** .
5. En el campo **Nombre**, especifique **Informe Intrastat (PDF)**.
6. En el campo **Descripción**, especifique **Informe Intrastat en formato PDF**.

    > [!NOTE]
    > El proveedor de configuraciones activo se especifica automáticamente. Este proveedor podrá mantener esta configuración. Aunque otros proveedores podrán usar esta configuración, no podrán mantenerla.

7. Opcional: en el campo **Tipo de formato**, puede seleccionar un formato específico de documentos electrónicos. Si se selecciona **PDF**, en el tiempo de diseño, el diseñador de operaciones de ER proporcionará solamente los artículos del formato aplicables a los documentos que se generan en formato PDF (**\ Archivo PDF**, **Fusión PDF \ PDF**, etc.). Si deja este campo en blanco, un formato de documentos electrónicos se especificará en el tiempo de diseño en el diseñador de las operaciones de ER cuando se agregue el primer elemento de formato. Por ejemplo, si agrega **Excel \ archivo** como el primer elemento de formato, el diseñador de las operaciones de ER le proporcionará solamente los artículos del formato aplicables a los documentos que se generan en el formato (**Excel\ Celda**, **Excel\Intervalo**, etc.). formato.
8. Seleccionar **Crear configuración**.

Se crea una configuración de formato ER nueva. Puede usar el borrador de versión de esta configuración para almacenar el componente del formato de ER diseñada para generar documentos electrónicos en formato PDF.

### <a name="design-the-format-of-an-electronic-document"></a>Diseño del formato de un documento electrónico

A continuación, en la configuración del formato de ER que ha creado, diseñará el formato de ER que genera el informe **Control de Intrastat** en formato PDF. La primera página de este informe debe mostrar un resumen del informe y los detalles de las transacciones de comercio exterior que se notifican. Las otras páginas deben mostrar sólo los detalles de las transacciones de comercio exterior que se notifican. Dado que las páginas del informe que se generan que deben tener diseños distintos, en el formato de ER se usarán dos plantillas diferentes en formato PDF.

En cualquier visor de PDF, abra las plantillas de PDF que descargó. Observe que cada plantilla contiene varios campos que se deben completar. En cada plantilla, los detalles de las transacciones de comercio exterior se muestran como 42 filas, cada una con nueve campos. El número de la fila aparece en el final de cada nombre de campo (por ejemplo, **Fecha 1**…**Fecha 42** y **Mercancía 1**…**Mercancía 42**).

La ilustración siguiente muestra la plantilla de PDF para la primera página del informe.

![Plantilla 1.](media/rcs-ger-filloutpdf-template1.png)

La ilustración siguiente muestra la plantilla de PDF para las otras páginas del informe.

![Plantilla 2.](media/rcs-ger-filloutpdf-template2.png)

1. En la página **Configuraciones**, seleccione **Diseñador**.
2. Seleccione **Agregar raíz**.
3. En el cuadro de diálogo, en el árbol, seleccione **PDF \> Fusión PDF**.

    Al seleccionar el elemento **Fusión PDF** como el elemento raíz de formato, todos los documentos PDF que se generan en el tiempo de ejecución se combinarán en un único documento PDF final. Si sólo necesita una plantilla de PDF para generar todos los documentos necesarios usando el formato de ER que ha diseñado, puede seleccionar **Archivo PDF** como el elemento raíz.

4. En el campo **Nombre**, especifique **Salida**.
5. En el campo **Preferencias de idioma**, seleccione **Preferencia del usuario**. El informe se generará en el idioma preferido del usuario que lo ejecuta.
6. En el campo **Preferencias culturales**, seleccione **Preferencia del usuario**. Los valores y las fechas que se muestran en las páginas del informe tendrán un formato según la configuración regional preferida del usuario que ejecuta el informe.
7. Seleccione **Aceptar**.
8. En el panel de acciones, en la pestaña **Importar**, seleccione **Importar desde PDF**.

    Cuando un documento PDF que se puede rellenar se importa como plantilla para este formato de ER, todos los artículos requeridos del formato de ER (los elementos **Archivo PDF**, **Grupo de campos** y **Campo** ) se crean automáticamente en el formato que está diseñado, en función de la estructura del documento PDF que se importa.

9. Seleccione **Explorar**. Navega a y seleccione el archivo del **IntrastatReportTemplate1.pdf** que descargó anterior como requisito previo.
10. Seleccione **Aceptar**.

    El archivo seleccionado está cargado, y el campo **Plantilla** en el cuadro **Importación de PDF** se rellena.

11. Establezca la opción **Campos de grupo** en **Sí**. Si el documento PDF seleccionado contiene cualquier grupo de campos, los utilizarán para agrupar los artículos del formato de ER que se han creado. Un elemento de formato **Grupo de campo** se creará con este propósito.

    Si esta opción se establece **No**, los artículos requeridos del formato de ER se crearán como una lista plana de elementos anidados bajo el elemento de formato **Archivo PDF** que se crea.

12. Seleccione **Aceptar**.

    ![Importación del cuadro de diálogo de PDF.](media/rcs-ger-filloutpdf-importtemplate.png)

13. En el árbol, expanda **Salida**.

    Observe que el componente **Archivo PDF** se ha creado automáticamente para administrar la configuración de la primera página del informe que se genera en tiempo de ejecución.

14. En el árbol, expanda **Salida\> Archivo PDF**.

    Observe que la lista estructurada de elementos del formato se ha creado automáticamente en este formato de ER, en función de la estructura del documento PDF que se puede rellenar que importó antes.

15. En el árbol, seleccione **Salida\> Archivo PDF**.
16. En el campo **Nombre**, especifique **Página 1**.

    Este elemento del formato se utilizará para generar la primera página del informe **Control de Intrastat** . Esta página mostrará un resumen del informe y los detalles de las transacciones de comercio exterior.

    Si deja en blanco del campo **Preferencias de idioma**, la configuración **Preferencias de idioma** del elemento **Fusión PDF** principal determinará el idioma de informe que se genera mediante este artículo del formato. Puede seleccionar otro valor para anular el valor del artículo principal.

    Si deja en blanco del campo **Preferencias culturales**, la configuración **Preferencias culturales** del elemento **Fusión PDF** principal determinará la configuración regional del informe que se genera mediante este artículo del formato. La configuración regional determina el formato de valores y de fechas en las páginas del informe. Puede seleccionar otro valor para anular el valor del artículo principal.

17. En el panel de acciones, seleccione la pestaña **Importar** . Observe que el botón **Actualizar desde PDF** ha estado disponible para el elemento de formato seleccionado, **Archivo PDF**.

    Puede usar este botón para importar la plantilla PDF actualizada al formato editado. Cuando se importa la plantilla PDF actualizada, la lista de elementos del formato cambiará según corresponda:

    - Para cualquier nuevo campo de la plantilla de PDF actualizada, los nuevos elementos de formato se crean en el formato ER editado.
    - Si la plantilla actualizada PDF no incluye los campos que corresponden a cualquier elemento existente del formato en el formato de ER editado, estos elementos de formato se eliminan del formato de ER.

18. En la pestaña **Formato**, seleccione **Adjuntos**.

    Observe que el documento PDF importado está vinculado al formato de ER editado.

    ![Vista previa del PDF adjunto.](media/rcs-ger-filloutpdf-attachedtemplate.png)

19. Continúe para diseñar este formato importando la segunda plantilla de PDF, agregando las relaciones necesarias con los orígenes de los datos, y así sucesivamente.
20. Seleccione **Guardar**.
21. Cierre la página.
22. Seleccione **Eliminar**.
23. Seleccione **Sí**.

Para aprender cómo los nuevos elementos de formato **Fusión PDF**, **Archivo PDF**, **Grupo de campos** y **Campo** se pueden usar para generar documentos en formato PDF, puede importar y analizar el formato de ER de ejemplo.

### <a name="import-the-format-configuration"></a>Importar el formato de configuración

A continuación, se importará el formato de ER de ejemplo que ha descargado anteriormente para generar el informe **Control de Intrastat** en formato PDF. La primera página del informe debe mostrar un resumen del informe y los detalles de las transacciones de comercio exterior que se notifican. Las otras páginas deben mostrar sólo los detalles de las transacciones de comercio exterior que se notifican.

1. En la página **Configuraciones**, seleccione **Exchange \> Cargar del archivo XML**.
2. Seleccione **Explorar**. Navega a y seleccione el archivo del **Informe Intrastat (PDF).version.1.1.xml** que descargó anterior como requisito previo.
3. Seleccione **Aceptar**.

## <a name="analyze-the-format-configuration"></a>Analizar el formato de configuración

### <a name="format-layout"></a>Diseño de formato

1. En la página **Configuraciones**, en el árbol, seleccione **Modelo de Intrastat \> Informe Intrastat (PDF)**.
2. Seleccione **Diseñador**.
3. Seleccionar **Mostrar detalles**.
4. En el árbol, expanda **Salida: Fusión PDF**.

    Observe que este formato de ER contiene dos elementos **Archivo PDF**, que utilizan otra plantilla de PDF. Una plantilla se usa para generar la primera página del informe en formato PDF, y otra plantilla se usará para generar las otras páginas.

5. En el árbol, expanda **Salida: Fusión PDF \> Página 1: Archivo PDF (IntrastatReportTemplate1)**.
6. En el árbol, expanda **Salida: Fusión PDF \> Página N: Archivo PDF (IntrastatReportTemplate2)**.

    Observe que como los contenidos de las dos plantillas de PDF son distintos, la estructura de los elementos de formato anidados para los dos elementos del **Archivo PDF** también difieren.

### <a name="format-mapping"></a>Asignación de formato

1. En la página **Diseñador de formato**, seleccione la pestaña **Asignación** .
2. En el árbol, expanda **Paginación\> Páginas**.

    ![Página del diseñador de fórmula que donde se expande el modelo en árbol.](media/rcs-ger-filloutpdf-reviewformat.png)

    Tenga en cuenta los siguientes detalles:

    - El elemento del formato **Salida \> Página 1** del tipo **Archivo PDF** no está enlazado a ningún origen de datos y la expresión **Habilitado** del artículo de formato está vacía. Por tanto, en el tiempo de ejecución, la plantilla PDF **IntrastatReportTemplate1** será rellenada solo una vez cuando se genere un documento PDF individual.
    - El artículo del formato **Salida \> Página N** del tipo **Archivo PDF** está enlazado el origen de datos **Paging.PageN** del tipo **Lista de registro**, y la expresión **Habilitado** del artículo de formato está vacía. Por tanto, en el tiempo de ejecución, la plantilla PDF **IntrastatReportTemplate2** será rellenada para cada registro de la lista de registro vinculada cuando se genere un documento PDF individual.
    - Dado que los elementos del formato **Página 1: Archivo PDF** y **Página N: Archivo PDF** son descendientes del elemento de formato **Salida: Fusión PDF**, todos los documentos PDF completados se combinarán en un único documento PDF final.
    - Los orígenes de datos **Paging.Page1** y **Paging.PageN** se configuran como filtros de registros desde el origen de datos **Paging.Pages** . Este origen de datos se configura para dividir el conjunto completo de transacciones de comercio exterior en lotes. Cada lote contiene hasta 42 registros. La expresión siguiente del ER se usa para dividir las transacciones en lotes:

        SPLITLIST(Totals.CommodityRecord,42)

    - El origen de datos **Paging.Pages** contiene el elemento **Paging.Pages.Enumerated** que devuelve los detalles de cada registro que se incluye en un lote. Estos detalles incluyen la secuencia de registro en el lote actual (el campo **Paging.Pages.Enumerated.Number** ). El campo **Paging.Pages.Enumerated.Number** se usa en la expresión **Nombre** de los elementos del formato **Campo de PDF** para generar dinámicamente un nombre de campo que se basa en el número de transacción en un lote. El nombre de campo que se genera se usa para completar el campo correcto de PDF en la plantilla de PDF que se usa.
    - El elemento de formato **Salida \> N de la página \> Detalles 2** del tipo **Grupo de PDF** está enlazado al origen de datos **Paging.PageN.Enumerated** (o **\@.Enumerated** si se utiliza el modo vista **Ruta de acceso relativas** ) del tipo **Lista de registro** . Por tanto, en el tiempo de ejecución, los elementos anidados de este grupo de PDF se rellenarán para cada registro de la lista de registro de vinculada. De esta manera, las líneas individuales de PDF se generan virtualmente para cada Nth de 42 registros de la lista **Paging.PageN.Enumerated** y los siguientes campos PDF se rellenan: Fecha N, Dirección N, Mercancía N,, etc. Por lo tanto, en esta conexión, el comportamiento del elemento de formato **Grupo de campos** se parece al comportamiento de los elementos del formato **XML \> Secuencia** y **Texto \> Secuencia** .

3. En el árbol, expanda **Salida \> Página \> Detalles2**.
4. En el árbol, seleccione **Salida \> Página N \> Detalles 2 \> PageFooter**.

    Observe que el atributo **Nombre** del artículo de formato definido como **PageFooter**. También observe que la expresión **Nombre** del artículo del formato está vacía.

5. En el árbol, seleccione **Salida \> Página N \> Detalles 2 \> Corrección 1**.

    Observe que el atributo **Nombre** del artículo de formato definido como **Corrección 1**. También observe que la expresión **Nombre** del artículo del formato se define como **Paging.FldName (“Corrección”,\@. Número)**.

![Diseñador de formato cuando se selecciona una asignación.](media/rcs-ger-filloutpdf-reviewformat2.png)

Tenga en cuenta que el artículo del formato **Campo** se usa para completar un campo individual de un documento PDF que se puede rellenar que se define como plantilla de valor principal del formato **Archivo PDF** . La vinculación del elemento de formato **Archivo PDF** o de los elementos anidados, si tiene cualquier elemento anidado, especifica el valor especificado en los campos PDF correspondientes. Las distintas propiedades del elemento del formato **Campo** se pueden utilizar para especificar qué campo PDF se rellena para un artículo individual de formato:

- En la pestaña **Formato**, el atributo **Nombre** del elemento de formato
- En la pestaña **Asignación**, la expresión **Nombre** del elemento de formato

Dado que ambas propiedades son opcionales para un elemento de formato **Campo**, se aplican las reglas siguientes para especificar el campo PDF de destino:

- Si el atributo **Nombre** está en blanco y la expresión **Nombre** devuelve una cadena vacía en el tiempo de ejecución, se dará una excepción en el tiempo de ejecución para que notificar al usuario que un campo de PDF no se puede encontrar en la plantilla de PDF que se usa para completar el documento PDF.
- Si se define el atributo **Nombre**, y la expresión **Nombre** está en blanco, el campo de PDF con el mismo nombre que el atributo **Nombre** de artículo de formato se rellena.
- Si se define el atributo **Nombre**, y la expresión **Nombre** está configurada, el campo de PDF con el mismo nombre que el valor devuelto por la expresión **Nombre** del artículo de formato se rellena.

> [!NOTE]
> Una casilla de comprobación de PDF se puede completar de las siguientes formas:
>
> - Cuando el elemento correspondiente del formato **Campo** está enlazado a un campo del origen de datos del tipo de datos **Booleano** tiene el valor **Verdad**
> - Cuando el elemento correspondiente del formato **Campo** contiene un elemento anidado del formato **Cadena** que se ha enlazado a un campo del origen de datos con el valor de texto **1**, **Verdad**, o **Sí**

## <a name="run-the-format-configuration"></a>Ejecutar la configuración del formato

### <a name="import-the-format-configuration"></a>Importar el formato de configuración

A continuación, se cargará el formato de ER del ejemplo **Intrastat (importar desde Excel)** . Este formato está diseñado para analizar un libro de Microsoft Excel seleccionado por el usuario que simule transacciones de comercio exterior.

1. En la página **Configuraciones**, seleccione **Exchange \> Cargar del archivo XML**.
2. Seleccione **Explorar**. Navega a y seleccione el archivo del **Intrastat (importar desde Excel).version.1.1.xml** que descargó anterior como requisito previo.
3. Seleccione **Aceptar**.
4. En el árbol, seleccione **Modelo Intrastat\> Intrastat (importar desde Excel)**.
5. Seleccione **Editar**.
6. Establezca la opción **Predeterminado para la asignación de modelo** a **Sí**.

    > [!NOTE]
    > Si anteriormente se establece la opción **Predeterminado para la asignación de modelo** a **Sí** para la configuración **Modelo de Intrastat** u otra configuración que se anide bajo la configuración **Modelo de Intrastat**, defina esta opción **No**.

    Cuando la opción **Predeterminado para la asignación de modelo** se establece en **Sí**, el formato ER importado **Intrastat (importar desde Excel)** se asigna como origen de datos predeterminados para la configuración del formato **Informe Intrastat (PDF)** . A continuación, cuando se ejecute la configuración del formato **Informe Intrastat (PDF)**, el contenido del libro de Excel que es analizado por el formato ER **Intrastat (importar desde Excel)** simulará las transacciones comerciales externos que es necesario informar. En la ilustración siguiente se muestra un ejemplo de un libro de trabajo de Excel.

    ![Libro de Excel que tiene datos de ejemplo.](media/rcs-ger-filloutpdf-excelworkbook.png)

### <a name="run-the-format-configuration"></a>Ejecutar la configuración del formato

1. En la página **Configuraciones**, en el árbol, seleccione **Modelo de Intrastat \> Informe Intrastat (PDF)**.
2. Seleccione **Ejecutar**.
3. Seleccione **Explorar**. Navega a y seleccione el archivo del **Datos de ejemplo de Intrastat.pdf** que descargó anterior como requisito previo.
4. Seleccione **Aceptar**.
5. En el campo **Dirección del informe**, seleccione **Ambos** para completar todas las transacciones del libro de Excel importado en el informe de PDF que se ha generado.
6. Seleccione **Aceptar**.
7. Revisar el documento PDF que se ha generado.

La ilustración siguiente muestra un ejemplo de la primera página del informe que se ha generado.

![Primera página del informe generado.](media/rcs-ger-filloutpdf-generatedreport.png)

La ilustración siguiente muestra un ejemplo de otra página del informe que se ha generado.

![Otra página del informe generado.](media/rcs-ger-filloutpdf-generatedreport2.png)

## <a name="limitations"></a>Limitaciones

Los nombres de los campos rellenables deben ser únicos en el formulario PDF que planea usar como plantilla de informe. Para cada uno de estos campos, se crea un elemento de formato individual con el nombre correspondiente en el formato ER editable cuando se importa un formulario PDF. Si un formulario PDF contiene varios campos con el mismo nombre, se crea un elemento de formato único para los campos que no permite que se completen individualmente en tiempo de ejecución.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

### <a name="when-i-run-the-er-format-to-generate-a-report-in-pdf-format-why-do-i-get-the-following-errors--cannot-handle-iref-streams-the-current-implementation-of-pdfsharp-cannot-handle-this-pdf-feature-introduced-with-acrobat-6-and-a-pdf-name-must-start-with-a-slash-"></a>Cuando ejecuto el formato ER para generar un informe en formato PDF, ¿por qué obtengo los siguientes errores: **No se pueden manejar flujos de iref. La implementación actual de PDFSharp no puede gestionar esta característica de PDF introducida con Acrobat 6.** y **Un nombre de PDF debe comenzar con una barra inclinada (/)?**

El marco ER utiliza la versión 1.5 de la biblioteca PDFSharp para generar estos informes en PDF. Algunas características de PDF 1.5 (Adobe Reader 6.0) aún no están implementados en esta biblioteca. Por lo tanto, PDFSharp aún no puede abrir algunos archivos que están marcados como **para PDF 1.5 o superior** y puede resultar en los errores recibidos. Use uno de las soluciones siguientes para resolver el problema:

-   Cuando utilice su propia plantilla PDF: cambie la plantilla a una versión anterior de Adobe y comience a usar una nueva plantilla en su formato ER.
-   Cuando usa una plantilla de formato de ER que otro proveedor de configuración compartió con usted como parte de una solución de ER: contacte con el propietario de esta solución de ER y proporcione una descripción del problema.
-   Cuando utiliza la solución ISV que contiene una versión anterior de la biblioteca PDFSharp: contacte con el propietario de la solución y sugiera una actualización a la versión más reciente de PDFSharp.

## <a name="additional-resources"></a>Recursos adicionales

- [ER Diseña una configuración para generar informes en formato OPENXML (noviembre de 2016)](tasks/er-design-reports-openxml-2016-11.md)
- [Diseñar configuraciones de ER para generar informes en formato Word](tasks/er-design-configuration-word-2016-11.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
