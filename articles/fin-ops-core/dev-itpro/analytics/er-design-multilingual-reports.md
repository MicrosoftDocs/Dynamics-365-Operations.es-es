---
title: Diseñar informes multilingües en informes electrónicos
description: Este tema explica cómo puede usar las etiquetas de informes electrónicos (ER) para diseñar y generar informes multilingües.
author: NickSelin
ms.date: 09/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERModelMappingDesigner, EROperationDesigner, ERExpressionDesignerFormula
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f5a2e8cca441189020e6274248a48c5e9dd80e00
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5753561"
---
# <a name="design-multilingual-reports-in-electronic-reporting"></a>Diseñar informes multilingües en informes electrónicos

[!include[banner](../includes/banner.md)]

## <a name="overview"></a>Información general

En calidad de usuario empresarial, puede usar usan el marco [Informes electrónicos (ER)](general-electronic-reporting.md) para configurar formatos para documentos de salida que se deben generar con arreglo a los requisitos legales de diversos países o regiones. Cuando estos requisitos exigen que los documentos salientes se generen en diferentes idiomas para diferentes países o regiones, puede configurar un único [formato](general-electronic-reporting.md#FormatComponentOutbound) de ER que contenga recursos dependientes del idioma. De esa manera, puede reutilizar el formato para generar documentos salientes para varios países o regiones. También es posible que desee utilizar un único formato de ER para generar un documento saliente en diferentes idiomas para los clientes, proveedores, subsidiarias o cualquier otra parte correspondiente.

Puede configurar modelos de datos de ER y asignaciones de modelos como los orígenes de datos de los formatos de ER configurados para definir el flujo de datos que especifica qué datos de la aplicación se colocan en los documentos generados. Como [proveedor](general-electronic-reporting.md#Provider) de configuraciones de ER, usted puede [publicar](tasks/er-upload-configuration-into-lifecycle-services.md#upload-a-configuration-into-lcs) [modelos de datos](general-electronic-reporting.md#data-model-and-model-mapping-components) configurados, [asignaciones de modelos](general-electronic-reporting.md#data-model-and-model-mapping-components) y [formatos](general-electronic-reporting.md#FormatComponentOutbound) como componentes de una solución ER para generar documentos salientes específicos. También puede permitir que los clientes [carguen](general-electronic-reporting-manage-configuration-lifecycle.md) la solución ER publicada para que pueda usarse y personalizarse. Si espera que los clientes hablen otros idiomas, puede configurar los componentes de ER para que contengan recursos que dependen del idioma. De esa manera, el contenido de un componente ER editable se puede presentar en el lenguaje preferido por el usuario del cliente en el momento del diseño.

Puede configurar recursos dependientes del idioma como etiquetas ER. Luego puede usar esas etiquetas para configurar los componentes de ER para los siguientes propósitos:

- En tiempo de diseño:

    - Presente el contenido de los componentes de ER configurados en el idioma preferido por el usuario.

- En tiempo de ejecución:

    - Genere contenido dependiente del idioma para documentos salientes.
    - Proporcione mensajes de advertencia y error en el idioma preferido por el usuario.
    - Solicite los campos obligatorios en el idioma preferido por el usuario.

Las etiquetas de ER se pueden configurar en cada [configuración](general-electronic-reporting.md#Configuration) de ER que contiene diferentes componentes. Las etiquetas se pueden mantener independientemente de la lógica configurada de los modelos de datos ER, las asignaciones de modelos ER y los componentes de formato ER.

Cada etiqueta ER se identifica mediante un identificador que es único en el alcance de la configuración ER que contiene esa etiqueta. Cada etiqueta puede contener texto de etiqueta para cada idioma admitido en la instancia actual de Microsoft Dynamics 365 Finance. Estos idiomas admitidos incluyen los idiomas de las personalizaciones implementadas.

## <a name="entry"></a>Entrada

Cuando diseña un modelo de datos ER, una asignación de modelo ER o un formato ER, la opción **Traducir** se muestra cada vez que selecciona un campo que puede contener el contexto traducible. Cuando selecciona esta opción, puede vincular el campo seleccionado a una etiqueta ER en el <a name="TextTranslationPane">panel</a> **Traducción de textos**. Puede seleccionar una etiqueta ER existente o puede agregar una nueva etiqueta ER si aún no está disponible. Cuando selecciona o agrega una etiqueta ER, puede agregar texto relacionado para cada idioma que sea compatible con la instancia actual de Finanzas.

La siguiente ilustración muestra cómo se realiza esta traducción en un modelo de datos ER editable. En este ejemplo, el atributo **Descripción** del campo **Pedido de compra** para el **Modelo de factura** editable se traduce al alemán de Austria (DE-AT) y al japonés (JA).

![Traducir una etiqueta ER en el diseñador del modelo de datos ER](./media/er-multilingual-labels-refer.png)

Solo se puede traducir el texto de las etiquetas que residen en un componente ER editable. Por ejemplo, si selecciona **Traducir** para el atributo de etiqueta de un origen de datos de asignación de modelo ER, y luego selecciona una etiqueta ER que reside en el modelo de datos ER primario, verá el contenido de la etiqueta, pero no podrá cambiarlo. En estos casos, el campo **Texto traducido** no está disponible, como se muestra en la siguiente ilustración.

![Revisar la traducción proporcionada de una etiqueta ER en el diseñador de asignación de modelos ER](./media/er-multilingual-labels-refer-mapping.png)

> [!NOTE]
> No puede usar los diseñadores para eliminar la etiqueta que se ha especificado en un componente ER editable.

## <a name="scope"></a>Ámbito

Se puede hacer referencia a las etiquetas ER en varios atributos traducibles de componentes ER.

### <a name="data-model-component"></a>Componente de modelo de datos

Cuando configura un modelo de datos ER, puede agregarle etiquetas ER. Los valores de los atributos **Etiqueta** y **Descripción** del elemento del modelo, el campo de cada modelo y cada <a id="LinkModelEnum"></a>enumeración del modelo se pueden vincular a una etiqueta ER que se agrega al modelo de datos ER.

![Proporcionar una traducción para el atributo Descripción en el diseñador del modelo de datos ER](./media/er-multilingual-labels-refer.png)

Cuando un modelo de datos ER se configura de esta manera, su contenido se presentará a los usuarios del diseñador del modelo de datos ER en el idioma preferido de cada usuario. Por lo tanto, el mantenimiento del modelo se simplifica. Las siguientes ilustraciones muestran cómo funciona esta funcionalidad para los usuarios que tienen DE-AT y JA establecidos como su idioma preferido.

![Diseño del diseñador del modelo de datos ER para un usuario que tiene DE-AT establecido como el idioma preferido](./media/er-multilingual-labels-refer-de.png)

![Diseño del diseñador del modelo de datos ER para un usuario que tiene JA establecido como el idioma preferido](./media/er-multilingual-labels-refer-ja.png)

### <a name="model-mapping-component"></a>Componente de asignación de modelos

Dado que la asignación del modelo ER se basa en un modelo de datos ER, las etiquetas de los elementos del modelo de datos a los que se hace referencia aparecen en el idioma preferido del usuario en el diseñador de asignación del modelo. La siguiente ilustración muestra cómo el significado del campo **Pedido de compra** se explica en la asignación del modelo editable utilizando la etiqueta del atributo **Descripción** que se ha agregado al modelo de datos configurado. Observe que esta etiqueta se presenta en el idioma preferido del usuario (DE-AT en este ejemplo).

![Diseño del diseñador de asignación de modelos ER para un usuario que tiene DE-AT establecido como el idioma preferido](./media/er-multilingual-labels-show-mapping.png)

Cuando el atributo **Etiqueta** del origen de datos **Parámetro de entrada del usuario** se configura como vinculado a una etiqueta ER, el campo de parámetro que corresponde a este origen de datos se presenta en el cuadro de diálogo del usuario en tiempo de ejecución a los usuarios en su idioma preferido.

### <a name="format-component"></a>Componente de formato

Cuando configura un formato ER, puede agregarle etiquetas ER. Los atributos **Etiqueta** y **Texto de ayuda** de cada origen de datos configurado se pueden vincular a una etiqueta ER que se agrega al formato ER. Los atributos **Etiqueta** y **Descripción** de cada valor enumeración <a id="LinkFormatEnum"></a>de formato también se puede vincular a una etiqueta ER que sea accesible desde el formato ER editable.

> [!NOTE]
> También puede vincular estos atributos a una etiqueta ER del modelo de datos ER primario que reutiliza las etiquetas del modelo en cada formato ER configurado para este modelo de datos ER.

Cuando un formato ER se configura de esta manera, el contenido del formato se presentará a los usuarios del diseñador de la operación ER en el idioma preferido de cada usuario. Por lo tanto, el mantenimiento del formato y el análisis de la lógica configurada se simplifican.

Dado que un formato ER se basa en un modelo de datos ER, las etiquetas de los elementos del modelo de datos a los que se hace referencia aparecen en el diseñador de formato ER en el idioma preferido del usuario.

Cuando el atributo **Etiqueta** del origen de datos **Parámetro de entrada del usuario** está vinculado a una etiqueta ER, el campo que corresponde al parámetro en el cuadro de diálogo del usuario en tiempo de ejecución se presenta al usuario como una solicitud. Las siguientes ilustraciones muestran cómo puede vincular el atributo **Etiqueta** del origen de datos **Parámetro de entrada del usuario** en tiempo de diseño a una etiqueta ER, de modo que se solicite a los usuarios el parámetro en diferentes idiomas preferidos del usuario (se muestran para inglés de Estados Unidos (EN-US) e idiomas DE-AT) en tiempo de ejecución.

![Proporcionar una traducción de los atributos de un parámetro de entrada del usuario en el diseñador de operaciones de ER](./media/er-multilingual-labels-refer-format.png)

![Procesamiento de pagos de proveedores de ER en tiempo de ejecución para el idioma preferido por el usuario EN-US](./media/er-multilingual-labels-show-runtime-en.png)

![Procesamiento de pagos de proveedores de ER en tiempo de ejecución para el idioma preferido por el usuario DE-AT](./media/er-multilingual-labels-show-runtime-de.png)

### <a name="expressions"></a>Expresiones

Para usar una etiqueta en una [expresión](er-formula-language.md) ER, debe usar la sintaxis **@"GER\_LABEL:X"**, donde el prefijo **@** indica que el operando se refiere a una etiqueta, **GER\_LABEL** indica que una etiqueta ER está presente, y **X** es el identificador de la etiqueta ER.

![Configurar una expresión ER que contiene una referencia a una etiqueta ER en el diseñador de fórmulas ER](./media/er-multilingual-labels-expression1.png)

Para referirse a la etiqueta de un sistema (aplicación), use la sintaxis **@"X"**, donde el prefijo **@** indica que el operando se refiere a una etiqueta, y **X** es el identificador de la etiqueta del sistema.

![Configurar una expresión ER que contiene una referencia a una etiqueta de aplicación en el diseñador de fórmulas ER](./media/er-multilingual-labels-expression2.png)

#### <a name="model-mapping"></a>Distribución del modelo

Se puede configurar una expresión de una asignación de modelos ER mediante el uso de una etiqueta. Cuando se llama a esta asignación mediante un formato ER que se ejecuta para generar un documento saliente, el contexto de la ejecución incluye un código de idioma. Una etiqueta de expresión configurada se completará con el texto de la etiqueta que se ha configurado para el idioma de ese contexto.

Si una etiqueta referenciada no tiene traducción para el idioma del contexto de ejecución del formato que llama a la asignación del modelo, se utiliza el texto de la etiqueta en el idioma EN-US.

#### <a name="format"></a>Formato

Se puede configurar una expresión ER de un formato ER mediante el uso de etiquetas. Cuando ejecuta este formato para generar un documento saliente, el contexto de la ejecución incluye un código de idioma. Una etiqueta de expresión configurada se completará con el texto de la etiqueta que se ha configurado para el idioma de ese contexto.

![Proporcionar traducción de una etiqueta ER de la expresión ER editable en el diseñador de fórmulas ER](./media/er-multilingual-labels-refer-in-expression.png)

![Muestra de enlace de datos que se refiere a una etiqueta ER en el diseñador de operaciones ER](./media/er-multilingual-labels-refer-in-binding.png)

Puede configurar el componente **ARCHIVO** de un formato ER para generar el informe en el idioma preferido del usuario.

![Configure el componente ARCHIVO en el diseñador de operaciones ER para generar el informe en el idioma preferido del usuario](./media/er-multilingual-labels-language-context-user.png)

Si configura un formato ER de esta manera, el informe se genera utilizando el texto correspondiente de las etiquetas ER. Las siguientes ilustraciones muestran ejemplos de informes para los idiomas de usuario EN-US y DE-AT.

![Vista previa del informe que se ha generado en el idioma preferido del usuario EN-US](./media/er-multilingual-labels-report-preview-en.png)

![Vista previa del informe que se ha generado en el idioma preferido del usuario DE-AT](./media/er-multilingual-labels-report-preview-de.png)

Si una etiqueta referenciada no tiene traducción para el idioma del contexto de ejecución del formato, se utiliza el texto de la etiqueta en el idioma EN-US en su lugar.

## <a name="language"></a>Idioma

ER admite diferentes formas de especificar un idioma para un informe generado. En el campo **Preferencias de idioma** en la pestaña **Formato**, puede seleccionar los siguientes valores:

- **Preferencia de la empresa**: genere un informe en un idioma especificado por la empresa.

    ![Especifique en el diseñador de operaciones ER el idioma preferido de la empresa como el idioma de un informe generado](./media/er-multilingual-labels-language-context-company.png)

- **Preferencia de usuario**: genere un informe en el idioma preferido del usuario.
- **Definido explícitamente**: genere un informe en un idioma que se especifica en tiempo de diseño.

    ![Especificar en el diseñador de operaciones ER un idioma definido en tiempo de diseño de la empresa como el idioma de un informe generado](./media/er-multilingual-labels-language-context-fixed.png)

- **Definido en tiempo de ejecución**: genere un informe en un idioma que se especifica en tiempo de ejecución. Si selecciona este valor, en el campo **Idioma**, configure una expresión ER que devuelva el código de idioma para el idioma, como el idioma del cliente correspondiente.

    ![Especificar en el diseñador de operaciones ER un idioma definido en tiempo de ejecución de la empresa como el idioma de un informe generado](./media/er-multilingual-labels-language-context-runtime.png)

## <a name="translation"></a>Traducción

Puede agregar las etiquetas ER necesarias para un componente ER editable. Cuando se agrega una etiqueta ER, se puede traducir de dos maneras: manual y automáticamente.

### <a name="manual-translation"></a>Traducción manual

Cuando agrega una etiqueta ER en el [panel](#TextTranslationPane) **Traducción de textos**, puede traducirla manualmente a todos los idiomas admitidos en la instancia actual de Finance. Puede seleccionar el idioma preferido en el campo **Idioma** en la sección **Idioma del sistema** o **Idioma del usuario**, escriba el texto apropiado en el campo **Texto traducido** correspondiente y luego seleccione **Traducir**. Este proceso debe repetirse para cada idioma requerido y cada etiqueta que agregue.

### <a name="automatic-translation"></a>Traducción automática

La configuración de un componente ER se realiza en la versión borrador de la configuración ER en la que reside el componente ER editable.

![Página de configuraciones ER que ofrece acceso a la versión de la configuración en el estado Borrador](./media/er-multilingual-labels-configurations.png)

Como se describió anteriormente en este tema, puede agregar las etiquetas ER necesarias a un componente ER editable. De esta forma, puede especificar el texto de las etiquetas ER en el idioma EN-US. Luego puede exportar las etiquetas del componente ER utilizando la función ER incorporada. Seleccione la versión borrador de una configuración de ER que contenga el componente de ER editable y luego seleccione **Intercambiar \> Exportar etiquetas**.

![Página de configuraciones de ER que permite exportar etiquetas de ER desde la versión de configuración seleccionada](./media/er-multilingual-labels-export.png)

Puede exportar todas las etiquetas o las etiquetas para un solo idioma que especifique al comienzo de la exportación. Las etiquetas se exportan como un archivo zip que contiene archivos XML. Cada archivo XML contiene etiquetas para un solo idioma.

![Ejemplo del archivo exportado que contiene etiquetas ER para el lenguaje DE-AT](./media/er-multilingual-labels-in-xml.png)

Este formato se utiliza para la traducción automática de etiquetas por servicios de traducción externos como [Dynamics 365 Translation Service](../lifecycle-services/translation-service-overview.md). Cuando reciba las etiquetas traducidas, puede volver a importarlas en la versión borrador de una configuración ER que contenga los componentes de ER que poseen esas etiquetas. Seleccione la versión borrador de una configuración de ER que contenga el componente de ER editable y luego seleccione **Intercambiar \> Cargar etiquetas**.

![Página de configuraciones de ER para importar etiquetas de ER a la versión de configuración seleccionada](./media/er-multilingual-labels-load.png)

Las etiquetas traducidas se importarán a la configuración de ER seleccionada. Las etiquetas traducidas que existen en esta configuración de ER se reemplazan. Si falta alguna etiqueta traducida en la configuración de ER, se adjunta.

## <a name="lifecycle"></a>Ciclo de vida

Las etiquetas de un componente ER que se pueden editar se guardan, junto con otro contenido para el componente, en la versión adecuada de una configuración ER.

Se puede hacer referencia a las etiquetas de un componente ER base en una versión derivada del componente ER que cree para introducir sus modificaciones.

El control de versiones de ER controla la asignación de etiquetas a cualquier atributo en un componente de ER. Los cambios en la asignación de etiquetas se registran en la lista de cambios (delta) de un componente ER editable que se ha creado como una versión derivada del componente ER proporcionado. Estos cambios se validarán cuando una versión derivada se cambie a una nueva versión base.

## <a name="functions"></a>Funciones

La función [LISTOFFIELDS](er-functions-list-listoffields.md) de ER incorporada puede acceder a las etiquetas ER que se han configurado para algunos elementos de los componentes ER.

Como se describió anteriormente en este tema, los atributos **Etiqueta** y **Descripción** de cada valor de enumeración de ER de [modelo](#LinkModelEnum) o [formato](#LinkFormatEnum) se pueden vincular a una etiqueta ER que sea accesible en el componente ER apropiado. Puede configurar una expresión ER donde llame a la función **LISTOFFIELDS** utilizando la enumeración ER como argumento. Esta expresión devuelve una lista que contiene un registro para cada valor de una enumeración ER que se ha definido como un argumento de esta función. Cada registro contiene el valor de una etiqueta ER que está vinculada a un valor de enumeración ER:

- El valor de una etiqueta ER que está vinculada a los atributos **Etiqueta** se almacena en el campo **Etiqueta** del registro devuelto.
- El valor de una etiqueta ER que está vinculada a los atributos **Descripción** se almacena en el campo **Descripción** del registro devuelto.

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general de los informes electrónicos](general-electronic-reporting.md)
- [Funciones de informes electrónicos](er-formula-language.md#functions)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]