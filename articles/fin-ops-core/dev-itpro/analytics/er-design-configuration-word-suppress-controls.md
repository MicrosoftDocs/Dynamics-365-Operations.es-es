---
title: Suprimir los controles de contenido de Word en los informes generados
description: Este artículo explica cómo configurar un formato de informes electrónicos (ER) para generar informes como archivos de Microsoft Word donde se suprimen los controles de contenido.
author: NickSelin
ms.date: 02/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: e11b697b78c89a1758fa9e81c901bd29fe281539
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882124"
---
# <a name="suppress-word-content-controls-in-generated-reports"></a>Suprimir los controles de contenido de Word en los informes generados

[!include [banner](../includes/banner.md)]

Para generar informes como documentos de Microsoft Word, debe diseñar una plantilla para los informes como documento de Word. Esta plantilla debe contener controles de contenido de Word como marcadores de posición para los datos que se completarán en tiempo de ejecución. Para utilizar un documento de Word creado como plantilla para sus informes, puede [configurar](er-design-configuration-word.md) una nueva [solución](er-quick-start1-new-solution.md) de [Informes electrónicos (ER)](general-electronic-reporting.md). La solución debe incluir una [configuración](general-electronic-reporting.md#Configuration) de ER que contenga un componente de formato de ER. Este formato de ER debe configurarse para utilizar la plantilla diseñada para la generación de informes.

En la versión 10.0.6 y posteriores de Dynamics 365 Finance, puede configurar fórmulas en su formato ER para suprimir algunos controles de contenido de Word en los documentos generados.

Los siguientes pasos explican cómo un usuario asignado a la función de administrador del sistema o consultor funcional de informes electrónicos puede configurar un formato ER que genera informes como archivos de Word y suprime algunos de los controles de contenido en los informes generados que se han configurado mediante una plantilla de Word.

Estos pasos se pueden llevar a cabo en la empresa GBSI.

## <a name="prerequisites"></a>Requisitos previos

Para completar estos pasos, primero debe completar los pasos de las siguientes guías de tarea:

- [Diseñar una configuración para generar informes en formato OPENXML](./tasks/er-design-reports-openxml-2016-11.md)
- [Reutilizar configuraciones de ER con plantillas de Excel para generar informes en formato Word](./tasks/er-design-configuration-word-2016-11.md)

Cuando complete los pasos de estas guías de tareas, se preparan los siguientes elementos:

- Un formato ER **Informe de hoja de trabajo de muestra** que está configurado para generar un documento en formato Word
- Una versión en [borrador](general-electronic-reporting.md#component-versioning) del formato ER **Informe de hoja de trabajo de muestra** marcada como **Ejecutable**
- Un método de pago **Electrónico** que está configurado para utilizar el formato ER **Informe de hoja de trabajo de muestra** para el procesamiento de pagos de proveedores

También debe descargar y guardar la siguiente plantilla siguientes para el informe de ejemplo:

- [Plantilla enlazada 2 de informes de pago (SampleVendPaymDocReportBounded2.docx)](https://download.microsoft.com/download/1/9/b/19b36e39-861a-414e-9150-9880d9d2487c/SampleVendPaymDocReportBounded2.docx)

## <a name="review-the-downloaded-word-template"></a><a id="tag-control"></a>Revisar la plantilla de Word descargada

1. En la aplicación de escritorio de Word, abra el archivo de plantilla **SampleVendPaymDocReportBounded2.docx** que descargó anteriormente.
2. Verifique que el archivo de plantilla contenga una sección de resumen que muestre los importes de pago totales para cada código de divisa que se haya cumplido en los pagos procesados.

    - La sección de resumen reside en una tabla separada del documento de Word.
    - La primera fila de esta tabla contiene los encabezados de las columnas de la tabla como encabezado de sección.
    - La segunda fila de esta tabla contiene el control de contenido repetido como detalles de la sección.
    - Este control de contenido se asigna al campo **SummaryLines** de la parte XML personalizada del **Informe** .
    - Según esta asignación, el control de contenido se asocia con el elemento **SummaryLines** del formato ER editable.

    > [!NOTE]
    > El control de contenido repetido está etiquetado con la clave **SummaryLines** que coincide con el campo de la parte XML personalizada a la que se ha asignado.

    ![Diseño de plantilla de Word.](./media/er-design-configuration-word-suppress-controls-image1.gif)

## <a name="select-the-existing-er-report-configuration"></a>Seleccione la configuración existente del informe ER

Para los siguientes pasos, reutilizará la configuración de ER existente que configuró cuando completó los pasos en las guías de tareas mencionadas anteriormente.

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos**.
2. Seleccione **Configuraciones de informes**.
3. En la página **Configuraciones**, en el árbol de configuraciones, expanda **Modelo de pago** y seleccione **Informe de hoja de cálculo de muestra**.
4. Seleccione **Diseñador** para editar la versión preliminar del formato ER seleccionado.

## <a name="replace-the-current-template-with-the-new-template"></a>Sustituya la plantilla actual por la nueva plantilla

Actualmente, el archivo SampleVendPaymDocReportBounded.docx se utiliza como plantilla para producir la salida en formato de Word. En los pasos siguientes, sustituirá esta plantilla de Word con la nueva plantilla de Word SampleVendPaymDocReportBounded2.docx que descargó anteriormente.

1. En la página **Diseñador de formato**, seleccione **Archivos adjuntos**.
2. En la página **Archivos adjuntos**, seleccione **Eliminar** para eliminar la plantilla existente.
3. Seleccione **Sí** para confirmar el borrado.
4. Seleccione **Nuevo** \> **Archivo**.
5. Seleccione **Examinar** y luego busque y seleccione el archivo **SSampleVendPaymDocReportBounded2.docx** que descargó anteriormente.
6. Seleccione **Aceptar**.
7. Cierre la página **Archivos adjuntos**.
8. En la página **Diseñador de formatos**, en el campo **Plantilla**, introduzca o seleccione el archivo **SampleVendPaymDocReportBounded2.docx**.

## <a name="run-the-format-to-create-word-output"></a>Ejecutar el formato para crear una salida en Word

1. Vaya a **Proveedores** \> **Pagos** \> **Diario de pagos**.
2. En la página **Pagos a proveedores**, en la pestaña **Lista**, seleccione todos los pagos.
3. Seleccione **Estado de pago** \> **Ninguno**.
4. Seleccione **Generar pagos**.
5. En el campo **Método de pago**, seleccione **Electrónico**.
6. En el campo **Cuenta bancaria**, seleccione **GBSI OPER**.
7. Seleccione **Aceptar**.
8. En el cuadro de diálogo **Parámetros de informes electrónicos**, seleccione **Aceptar** y analice la salida generada.

    ![Pagos para procesar en la página Pagos a proveedores.](./media/er-design-configuration-word-suppress-controls-image2.gif)

    La salida se presenta en formato Word y contiene la sección de resumen.

## <a name="configure-the-editable-format-to-suppress-the-summary-section"></a><a id="configure-to-suppress-control"></a>Configure el formato editable para suprimir la sección de resumen

Si desea suprimir la sección de resumen en un documento generado, según la solicitud de un usuario que ejecuta este formato ER, debe modificar el formato ER editable.

1. Vaya a **Administración de la organización** \> **Espacios de trabajo** \> **Informes electrónicos** y abra la versión de borrador el formato ER para editarla.
2. Seleccione **Configuraciones de informes**. 
3. En la página **Configuraciones**, en el árbol de configuraciones, expanda **Modelo de pago** \> **Informe de hoja de cálculo de muestra**.
4. Seleccione **Diseñador**.
5. En la página **Diseñador de formatos**, expanda **Word** y seleccione **SummaryLines**.
6. En la pestaña **Cartografía**, agregue una nueva fuente de datos para preguntar al usuario, en tiempo de ejecución, si la sección de resumen debe suprimirse:

    1. Seleccione **Agregar raíz**.
    2. En el cuadro de diálogo **Agregar origen de datos**, seleccione **Parámetro de entrada general\de usuario** para abrir el cuadro de diálogo **Propiedades del origen de datos del 'Parámetro de entrada del usuario'**.
    3. En el campo **Nombre**, especifique **uipSuppress**.
    4. En el campo **Etiqueta**, introduzca **Suprimir la sección de resumen**.
    5. En el campo **Nombre del tipo de datos de operaciones**, seleccione o introduzca **NoYes**.
    6. Seleccione **Aceptar**.

7. Agregue un nuevo origen de datos de tipo **NoYes** de enumeración de aplicaciones:

    1. Seleccione **Agregar raíz**.
    2. En el cuadro de diálogo **Agregar origen de datos**, seleccione **Dynamics 365 for Operations\Enumeración** para abrir el cuadro de diálogo **Propiedades del origen de datos 'Enumeración'**.
    3. En el campo **Nombre**, especifique **enumNoYes**.
    4. En el campo **Etiqueta**, introduzca **Opciones de supresión**.
    5. En el campo **Nombre del tipo de datos de operaciones**, seleccione o introduzca **NoYes**.
    6. Seleccione **Aceptar**.

8. Para el elemento de formato seleccionado **SummaryLines**, configure la fórmula para especificar cuándo se debe suprimir el control de contenido de Word asociado con el elemento de formato seleccionado:

    1. En la pestaña **Cartografía**, en la sección **Eliminado**, seleccione **Editar** para abrir la página **[Diseñador de fórmulas](general-electronic-reporting-formula-designer.md)**.
    2. En el campo **Fórmula**, introduzca la fórmula `uipSuppress = enumNoYes.Yes`.
    3. Seleccione **Guardar** y cierre la página **Diseñador de fórmula**.

        > [!NOTE]
        > Esta fórmula se aplicará a un documento generado **después de ejecutarse todos los demás elementos de formato**. Para aplicar esta fórmula, un control de contenido de Word etiquetado como elemento de formato para el que está configurada la fórmula (**SummaryLines** en este caso) se encuentra en un documento generado. Luego, ese control de contenido se elimina por completo, junto con la fila de la tabla de Word que lo contiene. La fila de detalles de la sección de resumen se elimina del documento generado.
        >
        > En tiempo de diseño, puede configurar la fórmula **Eliminado** para un elemento de formato, aunque ningún control de contenido en la plantilla de Word que está utilizando tenga una etiqueta que coincide con el nombre de un elemento de formato para el que la propiedad **Remoto** está configurada. Cuando valida el formato en el momento del diseño, recibe una [advertencia](er-components-inspections.md#i14) sobre esta incoherencia.
        >
        > En tiempo de ejecución, se lanza una excepción si ningún control de contenido en la plantilla de Word que está usando tiene una etiqueta que coincide con el nombre de un elemento de formato para el que está configurada la propiedad **Eliminado**.

    4. En la pestaña **Asignación**, en la sección **Eliminado**, establezca la opción **Con primario** en **Sí**.

        > [!NOTE]
        > Debe configurar esta opción en **Sí** para eliminar toda la tabla de Word como objeto principal de la fila que contiene los detalles de la sección de resumen. Si configura esta opción en **No**, la fila del encabezado de la sección permanece en el documento generado.

9. Seleccione **Guardar** para guardar los cambios del formato editable.

    ![Salida generada en formato Word.](./media/er-design-configuration-word-suppress-controls-image3.gif)

## <a name="run-the-modified-format-to-create-word-output"></a>Ejecutar el formato modificado para crear una salida en Word

1. Vaya a **Proveedores** \> **Pagos** \> **Diario de pagos**.
2. Seleccione el diario de pagos que creó y luego seleccione **Líneas**.
3. En la página **Pagos a proveedores**, seleccione todas las filas y luego seleccione **Estado de pago** \> **Ninguno**.
4. Seleccione **Generar pagos**.
5. En el campo **Método de pago**, seleccione **Electrónico**.
6. En el campo **Cuenta bancaria**, seleccione **GBSI OPER**.
7. Seleccione **Aceptar**.
8. En el cuadro de diálogo **Parámetros de informes electrónicos**, en el campo **Suprimir la sección de resumen**, seleccione **Sí**.
9. Seleccione **Aceptar** y analice la salida generada.

    ![Salida generada en formato Word.](./media/er-design-configuration-word-suppress-controls-image4.gif)

    Observe que la salida no contiene la sección de resumen, porque se ha suprimido.

## <a name="additional-resources"></a>Recursos adicionales

- [Diseñar una configuración para generar informes en formato OPENXML](./tasks/er-design-reports-openxml-2016-11.md)
- [Diseñar una nueva configuración de ER para generar informes en formato Word](er-design-configuration-word.md)
- [Reutilizar configuraciones de ER con plantillas de Excel para generar informes en formato Word](./tasks/er-design-configuration-word-2016-11.md)
- [Inspeccionar el componente ER configurado para evitar problemas de runtime](er-components-inspections.md#i14)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
