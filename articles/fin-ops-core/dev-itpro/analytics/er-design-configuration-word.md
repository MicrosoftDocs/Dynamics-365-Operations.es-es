---
title: Diseñar una nueva configuración de ER para generar informes en formato Word
description: Este tema explica cómo los usuarios pueden configurar un nuevo formato de informes electrónicos (ER) para generar informes como documentos de Microsoft Word.
author: NickSelin
manager: AnnBe
ms.date: 12/17/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable, EROperationDesigner,  LedgerJournalTable, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-01-01
ms.dyn365.ops.version: Version 10.0.6
ms.openlocfilehash: 535e46eb033bf2796ab8e4b0d2e29767ad0a8cdf
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094163"
---
# <a name="design-a-new-er-configuration-to-generate-reports-in-word-format"></a>Diseñar una nueva configuración de ER para generar informes en formato Word

[!include [banner](../includes/banner.md)]

Para generar informes como documentos de Microsoft Word, debe diseñar una plantilla para los informes utilizando, por ejemplo, la aplicación de escritorio Word. La siguiente ilustración muestra la plantilla de ejemplo para el informe de control que se puede generar para mostrar detalles de los pagos procesados a proveedores.

![Plantilla de ejemplo para el informe de control en la aplicación de escritorio de Word](./media/er-design-configuration-word-image1.png)

Para utilizar un documento de Word como plantilla para informes en formato Word, puede configurar una nueva [solución](er-quick-start1-new-solution.md) de [informes electrónicos (ER)](general-electronic-reporting.md). Esta solución debe incluir una [configuración](general-electronic-reporting.md#Configuration) de ER que contenga un componente de [formato](general-electronic-reporting.md#FormatComponentOutbound) ER.

> [!NOTE]
> Cuando crea una nueva configuración de formato ER para generar informes en formato Word, debe seleccionar **Word** como el tipo de formato el cuadro de diálogo desplegable **Crear configuración** o dejar el campo **Tipo de formato** en blanco.

![Crear una configuración de formato en la página Configuraciones](./media/er-design-configuration-word-image2.gif)

El componente de formato ER de la solución debe contener el elemento de formato **Excel\\Archivo**, y ese elemento de formato debe estar vinculado al documento de Word que se utilizará como plantilla para los informes generados en runtime. Para configurar el componente de formato ER, debe abrir el la versión de [borrador](general-electronic-reporting.md#component-versioning) de la configuración ER creada en el diseñador de formato ER. Después, agregue el elemento **Excel\\Archivo**, adjunte su plantilla de Word al formato ER editable y vincule esa plantilla al elemento **Excel\\Archivo** que agregó.

> [!NOTE]
> Cuando adjunte una plantilla manualmente, debe usar un [tipo de documento](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/configure-document-management#configure-document-types) que se haya [configurado](electronic-reporting-er-configure-parameters.md#parameters-to-manage-documents) previamente para almacenar las plantillas de formatos ER.

![Adjuntar una plantilla en la página del diseñador de formato](./media/er-design-configuration-word-image3.gif)

Puede agregar los elementos anidados **Excel\\Rango** y **Excel\\Celda** para el elemento **Excel\\Archivo** para especificar la estructura de los datos que se introducirán en los informes generados en runtime. Después, debe vincular esos elementos a los orígenes de datos del formato ER editable para especificar los datos reales que se introducirán en los informes generados en runtime.

![Agregar elementos anidados en la página del diseñador de formato](./media/er-design-configuration-word-image4.gif)

Cuando guarda sus cambios en el formato ER a la hora de diseñar, la estructura jerárquica del formato se almacena en la plantilla de Word adjunta como un [elemento XML personalizado](https://docs.microsoft.com/visualstudio/vsto/custom-xml-parts-overview?view=vs-2019) que se llama **Informe**. Debe acceder a la plantilla modificada, descargarla de Finance, almacenarla localmente y abrirla en la aplicación de escritorio de Word. La siguiente ilustración muestra la plantilla de ejemplo almacenada localmente para el informe de control que contiene el elemento XML personalizado **Informe**.

![Obtener una vista previa de la plantilla de informe de ejemplo en la aplicación de escritorio de Word](./media/er-design-configuration-word-image5.gif)

Cuando los enlaces de los elementos de formato **Excel\\Rango** y **Excel\\Celda** se ejecutan en runtime, los datos que entrega cada enlace entran en el documento de Word generado como un campo individual del elemento XML personalizado **Informe**. Para introducir los valores de los campos del elemento XML personalizado en un documento generado, debe agregar los [controles de contenido](https://docs.microsoft.com/office/client-developer/word/content-controls-in-word) de Word apropiados a su plantilla de Word para que sirvan como marcadores de posición para los datos que se completarán en runtime. Para especificar cómo se completan los controles de contenido, asigne cada control de contenido al campo apropiado del elemento XML personalizado **Informe**.

![Agregar y asignar controles de contenido en la aplicación de escritorio de Word](./media/er-design-configuration-word-image6.gif)

Debe reemplazar la plantilla de Word original del formato ER editable con la plantilla modificada que ahora contiene controles de contenido de Word que se asignaron a los campos del elemento XML personalizado **Informe**.

![Sustituir la plantilla en la página del diseñador de formato](./media/er-design-configuration-word-image7.gif)

Cuando ejecuta el formato ER configurado, la plantilla de Word adjunta se utiliza para generar un nuevo informe. Los datos reales se almacenan en el informe de Word como un elemento XML personalizado que se denomina **Informe**. Cuando se abre el informe generado, los controles de contenido de Word se completan con datos del elemento XML personalizado **Informe**.

## <a name="frequently-asked-questions"></a>Preguntas frecuentes

**Pregunta:** He configurado un formato ER para imprimir un documento de Word que contiene la dirección de una empresa. En la plantilla de Word para este formato ER, he insertado un control de contenido de texto enriquecido para presentar la dirección de una empresa. En Finance, introduje la dirección de la empresa como texto de varias líneas y seleccioné **Introducir** para agregar un retorno de carro para cada línea que introduje. Por lo tanto, espero que la dirección de la empresa aparezca como texto de varias líneas en los documentos generados. Sin embargo, la dirección aparece como una sola línea de texto que contiene símbolos especiales en lugar de retornos de carro. ¿Qué error hay en mi configuración?

**Respuesta:** En lugar de utilizar un control de contenido de texto enriquecido, debe utilizar un control de contenido de texto sin formato y seleccionar la casilla **Permitir retornos de carro (varios párrafos)** en las propiedades del control.

## <a name="additional-resources"></a>Recursos adicionales

- [Reutilizar las configuraciones de ER con plantillas de Excel para generar informes en formato Word](./tasks/er-design-configuration-word-2016-11.md)
- [Insertar imágenes y formas en los documentos generados con ER](electronic-reporting-embed-images-shapes.md#embed-an-image-in-a-word-document)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]