---
title: Tipos de datos compuestos admitidos para fórmulas de informes electrónicos
description: Este artículo proporciona información sobre las entidades de datos compuestas que son compatibles con las fórmulas de informes electrónicos (ER).
author: NickSelin
ms.date: 06/02/2021
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dc3fbe695d79eb0ec9796d471c4d2bb0bb7ab99d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8869326"
---
# <a name="supported-composite-data-types-for-electronic-reporting-formulas"></a>Tipos de datos compuestos admitidos para fórmulas de informes electrónicos

[!include [banner](../includes/banner.md)]

Este artículo proporciona información sobre las entidades de datos compuestas que son compatibles con las expresiones de [informes electrónicos (ER)](general-electronic-reporting.md). Las entidades de datos compuestas son [clase](#class), [contenedor](#container), [registro](#record), [lista de registro](#record-list) y [objeto](#object).

## <a name="class"></a><a name="class"></a>Clase

El tipo de datos *clase* se refiere a una clase de aplicación pública. En ER, se representa como un [*registro*](#record) que contiene un campo separado para cada método público de la clase referenciada. Cuando se parametriza la llamada al método, también debe especificar los argumentos requeridos de los tipos apropiados en una expresión ER que está configurada para llamar al método.

En los componentes asignación y formato de ER, puede agregar la fuente de datos **Clase** que se presenta como una fuente de datos y que devuelve un valor de tipo *clase*. Esta fuente de datos expone métodos públicos de la clase que se pueden llamar en tiempo de ejecución.

> [!NOTE]
> Solo los métodos que devuelven un valor se pueden llamar desde expresiones ER.
>
> Solo los métodos que tienen un rango de cero a ocho argumentos se pueden llamar desde expresiones ER.

El valor predeterminado de una *clase* es **nulo**.

La siguiente ilustración muestra cómo la fuente de datos **Información del sistema (xInfo)** del tipo **Clase** se agrega para hacer la instancia de la clase de aplicación **xInfo** y llamar a su método **productName()** para recibir el nombre de la aplicación actual. El nombre de la aplicación actual se obtiene en tiempo de ejecución mediante la ejecución del enlace `xInfo.productName` que se configuró para el campo **Nombre del software (SoftwareName)** del modelo de datos ER. Este enlace llama al método `productName()` de la clase de aplicación **xInfo** que se representa en la asignación del modelo actual como la fuente de datos **Información del sistema (xInfo)**.

[![Configurar un origen de datos de Clase en el diseño de asignación del modelo ER.](./media/er-formula-supported-data-types-composite-class1.gif)](./media/er-formula-supported-data-types-composite-class1.gif)

La siguiente ilustración muestra cómo se configura el formato ER para colocar el nombre de la aplicación proporcionada en los documentos generados. El campo **Nombre del software (SoftwareName)** del modelo de datos utilizado estaba vinculado al componente **Cadena** que está anidado bajo el elemento XML **softwareUsed** del formato ER. Por lo tanto, el nombre de la aplicación actual se coloca en tiempo de ejecución en el elemento XML **softwareUsed** de un documento generado en formato XML.

[![Configurar la estructura de un documento saliente electrónico en el diseñador de formato ER.](./media/er-formula-supported-data-types-composite-class2.png)](./media/er-formula-supported-data-types-composite-class2.png)

## <a name="container"></a><a name="container"></a>Contenedor

El tipo de datos *contenedor* contiene contenido binario. Un valor *Contenedor* se puede utilizar para pasar información específica del almacenamiento a un documento generado. En el marco de ER, este tipo de datos se utiliza con frecuencia para incluir contenido multimedia, como el logotipo de una empresa, en los documentos generados.

> [!NOTE]
> Aunque cada elemento multimedia se puede representar como un valor de *contenedor*, no todos los valores *contenedor* representan un elemento multimedia. Por lo tanto, si configura un formato ER para que utilice un *contenedor* para poner una imagen en los documentos generados, pero la referencia *contenedor* no devuelve contenido multimedia, se podría generar una excepción similar al siguiente ejemplo: "Error al ejecutar el código: Binario (objeto), método constructFromContainer llamado con parámetros no válidos".

El valor predeterminado de un *contenedor* es **nulo**.

La siguiente ilustración muestra cómo el campo **Bitmap(Image)** del tipo *Contenedor* está vinculado al campo de modelo de datos **Logo** del tipo **Contenedor** en la asignación de modelo de **Factura de ventas**. Este enlace hace que el logotipo de la empresa esté disponible para cualquier formato de ER que esté diseñado para la definición de raíz de **SalesInvoice** y que utiliza esta asignación de modelo en tiempo de ejecución.

[![Enlace a un campo del tipo de contenedor en el diseño de asignación del modelo ER.](./media/er-formula-supported-data-types-composite-container.png)](./media/er-formula-supported-data-types-composite-container.png)

## <a name="record"></a><a name="record"></a>Grabar

Un *registro* es una colección de campos con nombre, cada uno de los cuales está asociado con un valor de un tipo de datos [primitivos](er-formula-supported-data-types-primitive.md) o un tipo de datos compuestos. Por lo general, un *registro* se utiliza para representar un solo registro de una lista de registros. En este caso, cada elemento representa campos, métodos y relaciones individuales.

El valor predeterminado de un *registro* es **vacío**.

> [!NOTE]
> Cuando obtiene el valor de un campo de un *registro* vacío, se devuelve el valor predeterminado del tipo de datos apropiado.

Un *registro* se puede obtener utilizando las siguientes funciones:

- [PRIMERA](er-functions-list-first.md)
- [FIRSTORNULL](er-functions-list-firstornull.md)
- [EMPTYRECORD](er-functions-record-emptyrecord.md)
- [NULLCONTAINER](er-functions-record-nullcontainer.md)

Para obtener más información sobre la transformación de valores de *registro*, consule [Lista de funciones de ER en la categoría de lista](er-functions-category-list.md).

## <a name="record-list"></a><a name="record-list"></a>Lista de registros

Una *lista de registros* es una lista de elementos del tipo *registro*. Por lo general, una *lista de registros* se utiliza para representar la lista de registros que se ha obtenido de una tabla de base de datos.

De forma predeterminada, se accede a los registros de una *lista de registros* de forma secuencial. Para acceder a un registro específico, puede utilizar la función [INDEX](er-functions-list-index.md) y especificar el índice *entero*.

El valor predeterminado de una *lista de registro* es **vacío**. Puedes usar la función [ISEMPTY](er-functions-list-isempty.md) para evaluar si una *lista de registros* esta vacía.

> [!NOTE]
> Si una *lista de registros* está vacía, cualquier intento de obtener un valor de campo para un *registro* en él hace que se lance una excepción en tiempo de ejecución. Para saber cómo puede ayudar a prevenir excepciones de tiempo de ejecución de este tipo, consulte [Consideración de casos de lista vacía](er-components-inspections.md#i9).

Una *lista de registro* se puede iniciar utilizando las siguientes funciones:

- [ALLITEMS](er-functions-list-allitems.md)
- [ALLITEMSQUERY](er-functions-list-allitemsquery.md)
- [EMPTYLIST](er-functions-list-emptylist.md)
- [LIST](er-functions-list-list.md)
- [LISTDISTINCT](er-functions-list-listdistinct.md)

Para obtener más información sobre la transformación de valores de *lista de registro*, consule [Lista de funciones de ER en la categoría de lista](er-functions-category-list.md). Para aprender a introducir los elementos de la *lista de registros*, rellénelos con datos de la aplicación y luego utilice los datos para generar documentos comerciales, consulte [Diseño de una nueva solución de ER para imprimir un informe personalizado](er-quick-start1-new-solution.md).

## <a name="object"></a><a name="object"></a>Objeto

Un *objeto* se refiere a una instancia con estado de una *clase*. Por lo general, un *objeto* se inicia en el código fuente. Luego se pasa a una asignación de modelo ER y proporciona detalles del contexto de ejecución.

El valor predeterminado de un *objeto* es **nulo**.

La siguiente ilustración muestra cómo la fuente de datos **ReportDataContract** del tipo *Objeto* se agrega para pasar información sobre una factura generada desde el código fuente a la asignación de modelo de **Factura de proyecto**. Por ejemplo, el texto de la instancia de factura se pasa como parte del contexto de ejecución. Este texto se toma del código fuente en tiempo de ejecución mediante la ejecución del enlace `ReportDataContract.parmInvoiceInstanceText` que se configuró para el campo **Nota** del modelo de datos ER. Este enlace llama al método `parmInvoiceInstanceText()` de la clase de aplicación **PSAProjInvoiceContract** que se representa en la asignación del modelo actual como la fuente de datos **ReportDataContract**.

[![Configurar un origen de datos de Objeto en el diseño de asignación del modelo ER.](./media/er-formula-supported-data-types-composite-object.gif)](./media/er-formula-supported-data-types-composite-object.gif)

Para aprender a pasar detalles del contexto de ejecución desde el código fuente a la solución ER en ejecución, consulte [Desarrollar artefactos de aplicación para llamar al informe diseñado](er-quick-start1-new-solution.md#DevelopCustomCode).

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general de los informes electrónicos](general-electronic-reporting.md)
- [Idioma de fórmulas en los informes electrónicos](er-formula-language.md)
- [Tipos de datos primitivos admitidos](er-formula-supported-data-types-primitive.md)
