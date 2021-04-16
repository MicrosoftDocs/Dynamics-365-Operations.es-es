---
title: Reutilizar las configuraciones de ER con plantillas de Excel para generar informes en formato Word
description: Este tema describe cómo los formatos de informe que fueron diseñados para generar informes como libros de Excel pueden configurarse para generar informes como documentos de Word.
author: NickSelin
ms.date: 01/11/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner, LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 728984678d78cf626e2b30222f1d1e603e05d117
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5755067"
---
# <a name="reuse-er-configurations-with-excel-templates-to-generate-reports-in-word-format"></a>Reutilizar las configuraciones de ER con plantillas de Excel para generar informes en formato Word

[!include [banner](../../includes/banner.md)]

Para generar informes como documentos de Microsoft Word, puede [configurar](../er-design-configuration-word.md) un nuevo [formato](../general-electronic-reporting.md#FormatComponentOutbound) de [informes electrónicos (ER)](../general-electronic-reporting.md). También puede reutilizar un formato ER que se diseñara originalmente para generar informes como libros de Excel. En este caso, debe reemplazar la plantilla de Excel con una plantilla de Word.

Los siguientes procedimientos muestran cómo un usuario con el rol de administrador del sistema o el rol de desarrollador de informes electrónicos puede configurar un formato ER para generar informes como archivos de Word reutilizando un formato ER que fue diseñado para generar informes como archivos de Excel.

Estos procedimientos se pueden llevar a cabo en la empresa GBSI.

## <a name="prerequisites"></a>Requisitos previos

Para completar estos procedimientos, primero debe seguir los pasos en [Diseñar una configuración de ER para generar informes en formato OPENXML](er-design-reports-openxml-2016-11.md).

También debe descargar y guardar de forma local las plantillas siguientes para el informe de ejemplo:

- [Plantilla de informe de pago (SampleVendPaymDocReport.docx)](https://go.microsoft.com/fwlink/?linkid=862266)
- [Plantilla enlazada de pago (SampleVendPaymDocReportBounded.docx)](https://go.microsoft.com/fwlink/?linkid=862266)

Estos procedimientos son para una característica que se agregó en la versión 1611 (noviembre de 2016) de Dynamics 365 for Operations.

## <a name="select-the-existing-er-report-configuration"></a>Seleccione la configuración existente del informe ER

1. En Dynamics 365 Finance vaya a **Administración de la organización** \> **Espacioes de trabajo** \> **Informes electrónicos**.
2. Asegúrese de que el proveedor de la configuración **Litware, Inc.** está marcado como **Activo**. Si no es así, siga los pasos de la guía de tareas [Crear proveedores de configuración y marcarlos como activos](er-configuration-provider-mark-it-active-2016-11.md).
3. Seleccione **Configuraciones de informes**. Reutilizará la configuración actual de ER que se diseñó para generar la salida de informes en formato de OPENXML.
4. En la página **Configuraciones**, en el árbol de configuraciones del panel izquierdo, expanda **Modelo de pago** y seleccione **Informe de hoja de cálculo de muestra**.

    > [!NOTE]
    > La versión en borrador del formato ER seleccionado se puede editar en la ficha desplegable **Versiones**.

5. Seleccione **Diseñador**.
6. En la página **Diseñador de formatos**, observe que el título del elemento de formato raíz indica que se está utilizando actualmente una plantilla de Excel.

![Seleccionar la configuración existente](../media/er-design-configuration-word-2016-11-image01.gif)

## <a name="review-the-downloaded-word-template"></a>Revisar la plantilla de Word descargada

1. En la aplicación de escritorio de Word, abra el archivo de plantilla **SampleVendPaymDocReport.docx** que descargó anteriormente.
2. Verifique que la plantilla solo contiene el diseño del documento que desea generar como ER de salida.

![El diseño de la plantilla de Word en la aplicación de escritorio](../media/er-design-configuration-word-2016-11-image02.png)

## <a name="replace-the-excel-template-with-the-word-template-and-add-a-custom-xml-part"></a>Reemplazar la plantilla de Excel con la plantilla de Word y agregar un elemento XML personalizado

Actualmente, el documento de Excel se utiliza como plantilla para producir un resultado en formato de OPENXML. Sustituirá esta plantilla con el archivo de plantilla de Word SampleVendPaymDocReport.docx que se descargó anteriormente. También extenderá la plantilla de Word agregando un elemento XML personalizado.

1. En Finance, en la página **Diseñador de formato**, en la pestaña **Formato**, seleccione **Archivos adjuntos**.
2. En la página **Archivos adjuntos**, seleccione **Eliminar** para eliminar la plantilla de Excel existente. Seleccione **Sí** para confirmar el cambio.
3. Seleccione **Nuevo** \> **Archivo**.

    > [!NOTE]
    > Debe seleccionar un tipo de documento que se haya [configurado](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) en los parámetros de ER para almacenar plantillas de formatos ER.

4. Seleccione **Examinar** y luego busque y seleccione el archivo **SampleVendPaymDocReport.docx** que descargó anteriormente.
5. Seleccione **Aceptar**.
6. Cierre la página **Archivos adjuntos**.
7. En la página **Diseñador de formato**, en el campo **Plantilla**, introduzca o seleccione el archivo **SampleVendPaymDocReport.docx** para usar esa plantilla de Word en lugar de la plantilla de Excel que se usó anteriormente.
8. Seleccione **Guardar**.

    Además de almacenar cambios de configuración, la acción **Guardar** actualiza la plantilla de Word adjunta. La estructura jerárquica del formato diseñado se agrega al documento de Word adjunto como un nuevo elemento XML personalizado con el nombre **Informe**. La plantilla de Word adjunta contiene el diseño del documento que se generará como salida de ER y la estructura de datos que el ER introducirá en esta plantilla en runtime.

9. Observe que el título del elemento de formato raíz indica que se está utilizando actualmente una plantilla de Word.

    ![Reemplazar la plantilla de Excel con la plantilla de Word y agregar un elemento XML personalizado](../media/er-design-configuration-word-2016-11-image03.gif)

10. En la pestaña **Formato**, seleccione **Adjuntos**.

Ahora puede asignar los elementos del elemento XML personalizado **Informe** a los controles de contenido del documento de Word.

Si está familiarizado con el proceso de diseñar documentos de Word como formularios que contienen [controles de contenido](https://docs.microsoft.com/office/client-developer/word/content-controls-in-word) asignados a elementos de [elementos XML personalizados](https://docs.microsoft.com/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019), complete todos los pasos en el siguiente procedimiento para crear el documento. Para obtener más información, consulte [Crear formularios que los usuarios pueden rellenar o imprimir en Word](https://support.office.com/article/Create-forms-that-users-complete-or-print-in-Word-040c5cc1-e309-445b-94ac-542f732c8c8b). En caso contrario, omita el siguiente procedimiento.

## <a name="get-a-word-document-that-has-a-custom-xml-part-and-do-data-mapping"></a><a id='get-word-doc'></a>Obtener un documento de Word que tenga un elemento XML personalizado y realizar la asignación de datos

1. En Finance, en la página **Archivos adjuntos**, seleccione **Abrir** para descargar la plantilla seleccionada de Finance y almacenarla localmente como un documento de Word.
3. En la aplicación de escritorio de Word, abra el documento que acaba de descargar.
4. En la pestaña **Desarrollador**, seleccione **Panel de asignación XML**.

    > [!NOTE]
    > Si la pestaña **Desarrollador** no aparece en la cinta de opciones, personalícela para agregarla.

5. En el panel **Asignación XML**, en el campo **Elemento XML personalizado**, seleccione el elemento XML personalizado **Informe**.
6. Asigne los elementos del elemento XML personalizado **Informe** seleccionado y los controles de contenido del documento de Word.
7. Guarde el documento de Word actualizado localmente como **SampleVendPaymDocReportBounded.docx**.

## <a name="review-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a>Revisar la plantilla de Word donde el elemento XML personalizado se asigna a los controles de contenido

1. En la aplicación de escritorio de Word, abra el archivo de plantilla **SampleVendPaymDocReportBounded.docx**.
2. Verifique que la plantilla contiene el diseño del documento que desea generar como ER de salida. Los controles de contenido que se utilizan como marcadores de posición para los datos que ER introducirá en esta plantilla en runtime se basan en las asignaciones que se configuran entre los elementos del elemento XML personalizado **Informe** y los controles de contenido del documento de Word.

![Vista previa de la plantilla de Word en la aplicación de escritorio](../media/er-design-configuration-word-2016-11-image04.png)

## <a name="upload-the-word-template-where-the-custom-xml-part-is-mapped-to-content-controls"></a>Cargar la plantilla de Word donde el elemento XML personalizado se asigna a los controles de contenido

1. En Finance, en la página **Archivos adjuntos**, seleccione **Eliminar** para eliminar la plantilla de Word que no tiene asignaciones entre los elementos del elemento XML personalizado **Informe** y los controles de contenido. Seleccione **Sí** para confirmar el cambio.
2. Seleccione **Nuevo** \> **Archivo** para agregar un nuevo archivo de plantilla que contiene asignaciones entre elementos del elemento XML personalizado **Informe** y los controles de contenido.

    > [!NOTE]
    > Debe seleccionar un tipo de documento que se haya [configurado](../electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) en los parámetros de ER para almacenar plantillas de formatos ER.

3. Seleccione **Examinar** y luego busque y seleccione el archivo **SampleVendPaymDocReportBounded.docx** que descargó o preparó completando el procedimiento en la sección [Obtener un Word que tenga un elemento XML personalizado y realizar la asignación de datos](#get-word-doc).
4. Seleccione **Aceptar**.
5. Cierre la página **Archivos adjuntos**.
6. En la página **Diseñador de formato**, en el campo **Plantilla**, seleccione el documento que acaba de descargar.
7. Seleccione **Guardar**.
8. Cierre la página **Diseñador de formato**.

## <a name="mark-the-configured-format-as-runnable"></a>Marcar el formato configurado como ejecutable

Para ejecutar la versión de borrador del formato editable, debe hacerlo [ejecutable](../er-quick-start2-customize-report.md#MarkFormatRunnable).

1. En Finance, en la página **Configuraciones**, en el panel de acciones, en la pestaña **Configuraciones**, en el grupo **Configuración avanzada**, seleccione **Parámetros de usuario**.
2. En el cuadro de diálogo **Parámetros de usuario**, establezca la opción **Ejecutar configuración** en **Sí** y luego seleccione **Aceptar**.
3. Seleccione **Editar** para hacer que la página actual sea editable, según sea necesario.
4. Para la configuración **Informe de hoja de cálculo de muestra** seleccionada actualmente, establezca la opción **Ejecutar borrador** en **Sí**.
5. Seleccione **Guardar**.

## <a name="run-the-format-to-create-output-in-word-format"></a>Ejecutar el formato para crear una salida en formato Word

1. En Finance, vaya a **Proveedores** \> **Pagos** \> **Diario de pagos**.
2. En un diario de pagos que introdujera anteriormente, seleccione **Líneas**.
3. En la página **Pagos a proveedores**, seleccione todas las filas de la cuadrícula.
4. Seleccione **Estado de pago** \> **Ninguno**.

    ![Pagos para procesar en la página Pagos a proveedores](../media/er-design-configuration-word-2016-11-image05.png)

5. En el panel de acciones, seleccione **Generar pagos**.
6. En el cuadro de diálogo que aparece, siga estos pasos:

    1. En el campo **Método de pago**, seleccione **Electrónico**.
    2. En el campo **Cuenta bancaria**, seleccione **GBSI OPER**.
    3. Seleccione **Aceptar**.

7. En el cuadro de diálogo **Parámetros de informes electrónicos**, seleccione **Aceptar**.
8. La salida creada se presenta en formato de Word y contiene los detalles de los pagos procesados. Analice la salida generada.

    ![Salida generada en formato Word](../media/er-design-configuration-word-2016-11-image06.png)

## <a name="additional-resources"></a>Recursos adicionales

- [Diseñar una nueva configuración de ER para generar informes en formato Word](../er-design-configuration-word.md)
- [Insertar imágenes y formas en los documentos generados con ER](../electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]