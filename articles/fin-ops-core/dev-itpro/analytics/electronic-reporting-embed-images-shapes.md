---
title: Insertar imágenes y formas en los documentos generados con ER
description: Este artículo explica cómo utilizar la herramienta de informes electrónicos (ER) para generar documentos comerciales que tienen imágenes y formas incrustadas.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EROperationDesigner, ERParameters
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: fe0e6d6def50670566f44cfb5cd6bb4abe5faf15
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8851059"
---
# <a name="embed-images-and-shapes-in-documents-that-you-generate-by-using-er"></a>Insertar imágenes y formas en los documentos generados con ER

[!include [banner](../includes/banner.md)]

Puede utilizar la herramienta de informes electrónicos (ER) para diseñar informes que puede ejecutar para generar los documentos electrónicos necesarios. Puedes usar documentos de Microsoft Excel o Microsoft Word para especificar el diseño de un informe. El diseñador de operaciones de ER le permite adjuntar un documento de Excel o Word como plantilla para el informe. Los elementos con nombre en la plantilla adjunta están asociados con los elementos de formato del informe ER. Los elementos de formato del informe están vinculados a orígenes de datos. Estos elementos especifican los datos que se ingresarán, en tiempo de ejecución, en los documentos generados.

Esta nueva funcionalidad va más allá de las capacidades de ER existentes para crear documentos en formatos de Microsoft Office. Para obtener más información, reproduzca las siguientes guías de tareas: Puede encontrar estas guías de tareas en el proceso de negocio 7.5.4.3 Adquirir / Desarrollar servicios / componentes de soluciones (10677).

- ER Diseñar una configuración para generar informes en formato OPENXML
- ER Diseñar una configuración para generar informes en formato de Microsoft WORD

## <a name="embed-an-image-in-an-excel-document"></a>Insertar una imagen en un documento de Excel

### <a name="embed-an-image-in-an-excel-worksheet"></a>Insertar una imagen en una hoja de trabajo de Excel

Primero, debe agregar un marcador de posición para la imagen en un documento de Excel. Abra un libro de Excel y agregue una imagen como marcador de posición para la imagen que agregará más adelante. Luego, use la herramienta ER para agregar una nueva configuración de formato ER para incluir el informe que está diseñando. Adjunte el libro de trabajo de Excel como plantilla para el formato del informe y luego importe el contenido del libro de trabajo al formato ER. La definición de formato se creará automáticamente. El marcador de posición de imagen que agregó se incluirá en la definición del formato ER como un **CELDA**.

> [!NOTE]
> Puede especificar manualmente la definición de formato en lugar de importarla. Cuando guarde sus cambios, se validará el formato.

A continuación, une el elemento **CELDA** del formato ER al campo de la fuente de datos del formato que proporciona los datos de la imagen en formato binario en tiempo de ejecución. Cuando se utiliza un modelo de datos ER como fuente de datos de un formato, el tipo de datos del campo debe ser [Contenedor](er-formula-supported-data-types-composite.md#container). Actualmente, un campo de modelo de datos ER que tiene el tipo de datos [Contenedor](er-formula-supported-data-types-composite.md#container) se puede vincular a varios tipos de fuentes de datos que devuelven imágenes en formato binario. Puede acceder a un campo en una tabla de datos y un archivo que se adjunta al registro de la tabla de datos mediante el marco de gestión de documentos.

> [!IMPORTANT]
> - Si desea completar el marcador de posición de la imagen en el documento que está creando utilizando la plantilla de Excel, el formato ER debe contener el elemento **CELDA** que se refiere al elemento de imagen nombrado en la plantilla de Excel. De lo contrario, no aparecerá ningún marcador de posición de imagen en la salida del informe. Si la unión de un elemento **CELDA** no devuelve datos en tiempo de ejecución, el documento que se genera mostrará el marcador de posición de imagen de la plantilla. Para ocultar una imagen en el documento que está generando, defina un elemento **CELDA** y especifique que la expresión **Habilitar** debe devolver un valor **FALSO**.
> - En la plantilla de Excel, use un nombre único para cada elemento. Estos elementos incluyen imágenes y celdas. Si duplica el nombre de un elemento, el contenido del informe que se genera será ambiguo y confuso.

### <a name="embed-images-in-the-header-and-footer-of-an-excel-worksheet"></a>Insertar imágenes en el encabezado y pie de página de una hoja de cálculo de Excel

Utilice el documento del libro de Excel como plantilla para especificar el diseño de un informe. El libro de trabajo puede contener varias hojas de trabajo, cada una de las cuales puede diseñarse para que tenga un encabezado y un pie de página. Excel admite hasta tres imágenes en el encabezado y pie de página de cada hoja de trabajo. Las imágenes se pueden alinear a la izquierda, a la derecha o al centro.

En la versión 10.0.21 de Finance, puede administrar las imágenes de encabezado y pie de página que genera una solución de ER que tiene una plantilla de Excel.

Si desea que aparezca una imagen predeterminada en el encabezado o pie de página de un documento generado, puede agregar una imagen al encabezado o pie de página de una hoja de trabajo de una plantilla de ER. Para acceder a esta imagen en su formato ER, debe agregar el componente **Imagen** bajo el componente [Encabezamiento](er-fillable-excel.md#header-component) o [Pie de página](er-fillable-excel.md#footer-component) del formato. Configure la alineación del componente **Imagen** según corresponda. 

También puede utilizar el componente **Imagen** para colocar una imagen en el encabezado o pie de página de un documento generado en tiempo de ejecución, incluso si la plantilla no contiene una imagen predeterminada. Para especificar el contenido multimedia que se debe colocar en el encabezado o pie de página de un documento generado como una nueva imagen o un reemplazo de una imagen predeterminada, debe enlazar el componente **Imagen** a una fuente de datos del tipo [Contenedor](er-formula-supported-data-types-composite.md#container) que representa una imagen en formato binario.

Cada componente **Encabezamiento** o **Pie de página** puede contener un componente **Imagen** para cada alineación admitida: **Izquierda**, **Centrar** y **Derecha**.

La propiedad **Escala la altura** del componente **Imagen** le permite usar el enlace configurado para controlar el tamaño de una imagen:

- Seleccione **Original** para mantener el tamaño inicial de la imagen.
- Seleccione **Relativo** para escalar la altura de la imagen en proporción a la altura del encabezado o pie de página que contiene esa imagen.

    - En este caso, la altura de la imagen debe definirse como un porcentaje del encabezado o pie de página principal.
    - Si el valor de escala supera el 100 por ciento, la imagen puede superponerse al área de datos de la hoja de trabajo correspondiente.
    - Si se cambia la altura de la imagen cuando se aplica la escala, el ancho también se cambia para mantener la relación de aspecto original de la imagen.

- Seleccione **Absoluto** para cambiar el tamaño de la imagen de acuerdo con los valores de alto y ancho (en píxeles) que se proporcionan en el momento del diseño.

    - Si la altura especificada excede la altura del encabezado o pie de página principal, la imagen puede superponerse al área de datos de la hoja de trabajo correspondiente.

También puede utilizar la propiedad **Activado** del componente **Imagen** para controlar la visibilidad de una imagen que se coloca en un documento generado mediante el uso de este componente.

> [!NOTE]
> Debe utilizar el diseñador de formato ER para agregar un componente **Imagen** al formato ER editable. No puede agregar el componente cuando usa el espacio de trabajo [Gestión de documentos comerciales](er-business-document-management.md) para editar la plantilla de un documento comercial.

Para obtener más información sobre esta funcionalidad, siga los pasos en [Diseñe un formato ER para generar un informe en formato Excel con imágenes incrustadas en encabezados o pies de página](er-embed-images-header-footer-excel-reports.md).

## <a name="embed-a-shape-in-an-excel-document"></a>Insertar una forma en un documento de Excel

Primero, debe agregar un marcador de posición para la forma en un documento de Excel. Abra un libro de Excel y seleccione **Forma**, **Cuadro de texto** o **WordArt** como marcador de posición para la forma. Luego, use la herramienta ER para agregar una nueva configuración de formato ER para incluir el informe que está diseñando. Adjunte el libro de trabajo de Excel como plantilla para el formato del informe y luego importe el contenido del libro de trabajo al formato ER. La definición de formato se creará automáticamente. El marcador de posición de forma que agregó se incluirá en la definición del formato ER como un elemento **CELDA** que hace referencia al elemento de forma de Excel con nombre.

> [!NOTE]
> Puede especificar manualmente la definición de formato en lugar de importarla. Cuando guarde sus cambios, se validará el formato.

A continuación, une el elemento **CELDA** en el formato ER al campo de la fuente de datos del formato que proporciona los datos en tiempo de ejecución. Estos datos se pueden convertir en una cadena de texto. Cuando el elemento **CELDA** en el formato ER se refiere a un elemento de forma en la plantilla de Excel que admite texto, el texto que se proporciona a través de este enlace en tiempo de ejecución se mostrará en una forma en el documento que se genera.

> [!IMPORTANT]
> - Si desea utilizar la plantilla de Excel que incluye el marcador de posición de forma para generar un nuevo documento, el formato ER debe contener un elemento **CELDA** que hace referencia al elemento de forma de Excel. De lo contrario, no aparecerá ningún marcador de posición de forma en la salida del informe. Si la unión de un elemento **CELDA** que se refiere al elemento de forma de Excel con nombre no devuelve datos en tiempo de ejecución, el documento que se genera mostrará el texto del marcador de posición de forma de la plantilla de Excel. Para ocultar una forma en el documento que está generando, defina un elemento **CELDA** que hace referencia al elemento de forma de Excel con nombre y especifique que la expresión **Habilitar** debe devolver un valor **FALSO**.
> - En la plantilla de Excel, use un nombre único para cada elemento. Estos elementos incluyen formas y celdas. Si duplica el nombre de un elemento, el contenido del informe que se genera será ambiguo y confuso.

## <a name="embed-an-image-in-a-word-document"></a>Insertar una imagen en un documento de Word
> [!IMPORTANT]
> Puede reutilizar el formato ER que usa una plantilla de Excel para crear documentos que incluyen imágenes incrustadas. En el formato ER, asegúrese de que se especifique un nombre para el elemento **CELDA** que hace referencia a un elemento de imagen con nombre en Excel, y que está vinculado a una fuente de datos que devuelve una imagen en tiempo de ejecución.

Primero, debe configurar el diseño del documento de Word. Utilizar el control **Contenido de la imagen** para crear un marcador de posición para la imagen incrustada. Para acceder a este control, primero debe realizar la pestaña **Desarrollador** visible en la cinta de Word.

A continuación, elimine la plantilla de Excel del formato ER y adjunte el documento de plantilla de Word. Actualice la referencia a la plantilla y guarde sus cambios. La estructura del formato ER actual se guarda en la plantilla de Word como un nuevo elemento XML personalizado con el nombre **Informe**.

A continuación, guarde la plantilla de Word para el formato actual de ER en su computadora local. Abra la plantilla y abra el panel **Mapeo XML**. Busque la parte XML personalizada que se denomina **Informe** y luego apunte al elemento **CELDA** en el informe de ER que está vinculado a una fuente de datos que devuelve una imagen en formato binario. Asigne el elemento de esta parte XML al control seleccionado **Contenido de la imagen** y guarde los cambios.

[![incrustar imágenes.](./media/embed-images-shapes-01.png)](./media/embed-images-shapes-01.png)

Finalmente, elimine la plantilla de Word del formato ER y adjunte el documento de Word que incluye las partes XML personalizadas asignadas. Actualice la referencia de formato a la plantilla y guarde los cambios que realizó en este formato de ER.

## <a name="more-information"></a>Más información
Para familiarizarse con los detalles de esta función, reproduzca el conjunto de guías de tareas, **ER Realice informes en formatos de MS Office con imágenes incrustadas**. Estas guías de tareas muestran cómo puede incrustar las imágenes del logotipo de una empresa y la firma de una persona autorizada en los cheques de pago que se generan mediante el uso de la herramienta ER en documentos de Excel y Word.

La siguiente tabla enumera los archivos necesarios para completar la guías de tareas **ER Realice informes en formatos de MS Office con imágenes incrustadas**. Descargue y guarde los archivos en el equipo local.

| Descripción                                          | Nombre de archivo                   |
|------------------------------------------------------|-----------------------------|
| Configuración del modelo datos de ER                          | [Model for cheques.xml](https://download.microsoft.com/download/6/e/a/6ea166fd-1382-4fdb-8dcb-0f13379f9c8e/Modelforcheques.xml)       |
| Configuración del formato de ER                              | [Cheques printing format.xml](https://download.microsoft.com/download/1/7/c/17c301e3-c4ee-4886-ae75-440fcc002c8c/Chequesprintingformat.xml) |
| Imagen del logotipo de la empresa                                   | [Company logo.png](https://download.microsoft.com/download/8/2/e/82e6bd81-caac-4e9a-bfce-1392ce7c8616/Companylogo.png)            |
| Imagen de firma                                      | [Signature image.png](https://download.microsoft.com/download/5/0/9/509151b3-06fc-4870-9408-7c9a43b72771/Signatureimage.png)         |
| Imagen de firma alternativa                          | [Signature image 2.png](https://download.microsoft.com/download/3/0/0/30045bf1-0ff6-4215-9162-b77c2f5dcc7c/Signatureimage2.png)       |
| Plantilla de Microsoft Word para imprimir cheques de pago  | [Consultar plantilla Word.docx](https://download.microsoft.com/download/4/4/d/44d9d255-9ad1-42fe-87db-23f319fd8e89/ChequetemplateWord.docx)   |
| Plantilla de Microsoft Excel para imprimir cheques de pago | [Cheque template.xlsx](https://download.microsoft.com/download/1/f/6/1f671963-73aa-48d5-ae69-45f21fe7dfb4/Cheque%20template.xlsx)        |

El siguiente gráfico proporciona un ejemplo de la impresión de prueba para un cheque de pago que se genera a partir de la plantilla de Excel.

[![Impresión de prueba de cheque de pago.](./media/embed-images-shapes-02.png)](./media/embed-images-shapes-02.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
