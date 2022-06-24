---
title: Utilice fuentes de datos de PARÁMETROS DE ENTRADA DE USUARIO para especificar parámetros para un informe
description: Este artículo explica cómo usar fuentes de datos de PARÁMETROS DE ENTRADA DE USUARIO para especificar parámetros para los informes que genera.
author: NickSelin
ms.date: 04/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERModelMappingDesigner, EROperationDesigner
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: ''
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: Version 10.0.27
ms.openlocfilehash: 62b7a8173416a1d36a2985823d186a7a0e6a7e60
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8872983"
---
# <a name="use-user-input-parameter-data-sources-to-specify-parameters-for-a-report"></a>Utilice fuentes de datos de PARÁMETROS DE ENTRADA DE USUARIO para especificar parámetros para un informe

[!include[banner](../includes/banner.md)]

Cuando diseña [Asignación de modelos](er-overview-components.md#model-mapping-component) de [Informes electrónicos](general-electronic-reporting.md) (ER) y componentes de [formato](er-overview-components.md#format-component) de ER, puede utilizar fuentes de datos de un *PARÁMETRO DE ENTRADA DE USUARIO* para obtener los valores necesarios que se pueden especificar en los campos de entrada de datos en el cuadro de diálogo en runtime, antes de que comience la ejecución de un formato ER. Este artículo describe las fuentes de datos de *PARÁMETRO DE ENTRADA DE USUARIO* que son compatibles actualmente.

## <a name="mandatory-properties"></a><a name="mandatory-properties"></a>Propiedades obligatorias

Debe especificar las siguientes propiedades para las fuentes de datos de cada tipo de *PARÁMETRO DE ENTRADA DE USUARIO*:

- En el campo **Nombre**, especifique el nombre interno del origen de datos. Puede utilizar este nombre en otras [expresiones](er-formula-language.md) y enlaces del componente de formato o asignación de modelo configurado.

## <a name="optional-properties"></a><a name="optional-properties"></a>Propiedades opcionales

Puede especificar opcionalmente las siguientes propiedades para las fuentes de datos de un tipo de *PARÁMETRO DE ENTRADA DE USUARIO*:

- En el campo **Etiqueta**, especifique la etiqueta que se utiliza para el campo de entrada de datos relacionado en el cuadro de diálogo en runtime. Puede agregar texto de etiqueta diferente para diferentes códigos de idioma activando el campo **Etiqueta** y luego seleccionando **Traducir**.
- En el campo **Ayuda**, especifique el texto de ayuda que se muestra en tiempo de diseño en la parte inferior de la página **Diseñador de formato** o la página **Diseñador de asignación de modelos** cuando un origen de datos editable de tipo *PARÁMETRO DE ENTRADA DE USUARIO* se selecciona. Este texto puede proporcionar detalles adicionales sobre el origen de datos para ayudar a los usuarios cuando configuren el formato editable o el componente de asignación de modelos. Puede agregar diferentes textos de ayuda para diferentes códigos de idioma seleccionando **Traducir**.

    > [!NOTE]
    > El botón **Traducir**, que puede usar para agregar [etiquetas y texto específicos del idioma](er-design-multilingual-reports.md#format-component) estará disponible solo después de agregar el origen de datos, guardar los cambios y luego volver a abrir el origen de datos para editarla.

- En el campo **Solo lectura**, configure una expresión que devuelva un valor *[Booleano](er-formula-supported-data-types-primitive.md#boolean)*.

    - Si la expresión configurada devuelve un valor **True** en runtime, el campo de entrada de datos relacionado aparece atenuado en el cuadro de diálogo y no se puede cambiar su valor.
    - Si la expresión configurada devuelve un valor **False** en runtime, o si no se configura ninguna expresión, el campo de entrada de datos relacionado está disponible en el cuadro de diálogo y se puede cambiar su valor.

- En el campo **Valor predeterminado** configure una expresión que devuelva el valor del tipo de parámetro al que se hace referencia. Este valor se puede usar para rellenar un valor predeterminado para el campo de entrada de datos relacionado en el cuadro de diálogo en runtime.

    Cuando ejecuta un formato ER, el valor que introduce en el campo de entrada de datos relacionado en el cuadro de diálogo en tiempo de ejecución se guarda en la memoria como el valor utilizado anteriormente. Los valores utilizados anteriormente se guardan individualmente para cada campo, la ejecución del formato ER, el usuario actual y la organización actual (empresa).

    - Seleccione la opción **Restablecer siempre al valor predeterminado** en **Sí** si el valor devuelto por la expresión **Valor predeterminado** siempre se debe utilizar como valor predeterminado, independientemente del valor utilizado anteriormente.
    - Seleccione la opción **Restablecer siempre al valor predeterminado** en **No** si el valor devuelto por la expresión **Valor predeterminado** se debe utilizar como valor predeterminado solo cuando falte el valor utilizado anteriormente.

    > [!NOTE]
    > Si configura la opción **Restablecer siempre al valor predeterminado** en **Sí**, se debe configurar una expresión en el campo **Valor predeterminado**.

- Si configura la opción **Permitir selección múltiple** en **Sí**, puede seleccionar varios valores para el parámetro configurado en runtime. Si lo configura en **No**, solo puede seleccionar un único valor.

    > [!NOTE]
    > Esta opción no es aplicable a todos los tipos de *PARÁMETRO DE ENTRADA DE USUARIO*. En tiempo de diseño, se lanza una excepción para informar al usuario que el parámetro de entrada de usuario configurado no admite la selección múltiple y que solo se puede seleccionar o introducir un único valor.
    >
    > Si configura la opción **Permitir selección múltiple** en **Sí** y especificó una expresión en el campo **Valor predeterminado**, esa expresión se puede utilizar para establecer un único valor predeterminado.

- Seleccione la opción **Editar visibilidad** para especificar si el parámetro configurado debe mostrarse en el cuadro de diálogo en runtime.

    > [!NOTE]
    > La visibilidad predeterminada de las fuentes de datos de un tipo de *PARÁMETRO DE ENTRADA DE USUARIO* depende del componente ER que los contiene.
    >
    > - Si un origen de datos está configurado en el componente de formato, es visible de forma predeterminada.
    > - Si se configura un origen de datos en el componente de asignación de modelos, solo es visible si el valor del origen de datos afecta al resultado cuando se ejecuta un componente de ER. Por ejemplo, agregó un origen de datos pero no lo usó en expresiones y enlaces del componente de asignación del modelo actual. En este caso, de forma predeterminada, el campo de entrada de datos relevante no se mostrará en el cuadro de diálogo en runtime. 

    En la página **Diseñador de fórmulas**, en el campo **Fórmula**, configure una expresión que devuelva un valor *booleano*.

    - Si la expresión configurada devuelve un valor **True** en runtime, o si no se configura ninguna expresión, el campo de entrada de datos relacionado es visible en el cuadro de diálogo en runtime.
    - Si la expresión configurada devuelve un valor **False**, el campo de entrada de datos relacionado está oculto en el cuadro de diálogo en runtime. Cuando lo llaman otras expresiones en runtime, devuelve el valor predeterminado, el valor utilizado anteriormente o el valor predeterminado para el valor del tipo de datos actual, dependiendo de otras configuraciones.

## <a name="type-specific-properties"></a>Propiedades específicas del tipo

### <a name="application-dependent-user-input-parameter"></a>Parámetro de entrada de usuario dependiente de la aplicación

Utilice un origen de datos del tipo **General** \> **Parámetro de entrada del usuario** para obtener el valor o valores requeridos de un tipo de datos que se especifica para la instancia actual de la aplicación de Microsoft Dynamics 365 Finance. Cuando agregue un origen de datos de este tipo a un componente de ER, especifique las siguientes propiedades:

- En el campo **Nombre del tipo de datos de operaciones (EDT, enumeración)**, seleccione una aplicación de [Tipo de datos extendido (EDT)](../extensibility/extensible-edts.md) o una enumeración de aplicaciones.

> [!NOTE]
> Le recomendamos revisar las expresiones que están configuradas en los campos **Solo lectura** y **Valor predeterminado** cuando cambia la referencia **Nombre del tipo de datos de operaciones (EDT, enumeración)** en un origen de datos editable de este tipo *PARÁMETRO DE ENTRADA DE USUARIO*.

La siguiente ilustración muestra las propiedades del origen de datos `$TaxRegNum` que se configuró en la configuración del formato **XML instantáneo (DE)** de ER. Este origen de datos está configurada para usar el EDT *Descripción* para ofrecer el campo de entrada de datos **Número de registro de impuestos** en el cuadro de diálogo en runtime.

![Propiedades de un origen de datos del tipo PARÁMETRO DE ENTRADA DE USUARIO en el cuadro de diálogo de la página del diseñador de formato.](./media/er-user-input-parameter-data-sources-01.png)

La siguiente ilustración muestra el cuadro de diálogo que se muestra en runtime cuando se ejecuta la configuración de formato **XML instantáneo (DE)** de ER para [generar](../../../finance/localizations/tasks/eur-00002-eu-intrastat-declaration.md) la declaración Intrastat. Observe que el campo **Número de registro de impuestos** configurado está disponible para la entrada de datos.

![Cuadro de diálogo Informe Intrastat del formato ER en ejecución en la página Intrastat.](./media/er-user-input-parameter-data-sources-02.png)

### <a name="data-model-enumeration-user-input-parameter"></a>Parámetro de entrada de usuario de enumeración de modelo de datos

Utilice un origen de datos del tipo **Modelo de datos** \> **Parámetro de entrada de usuario de enumeración** para obtener el valor o valores requeridos de un solo modelo de datos de [enumeración](er-formula-supported-data-types-primitive.md#enumeration). Cuando agregue un origen de datos de este tipo a un componente de ER, especifique las siguientes propiedades:

- En el campo **Modelo**, especifique una referencia al modelo de datos base.
- En el campo **Enumeración modelo**, especifique una referencia a una enumeración del modelo de datos de referencia.
- En el campo **Versión**, seleccione el número de revisión del componente del modelo de datos de ER que contiene la enumeración del modelo al que se hace referencia.

    > [!TIP]
    > En el momento del diseño, puede dejar el campo **Versión** en blanco, para acceder a la lista de enumeraciones para el componente del modelo de datos al que se hace referencia que reside en la versión de borrador de la configuración del modelo de datos de ER correspondiente. De esta forma, puede editar simultáneamente la versión de borrador de su componente de formato o asignación de modelo y la versión de borrador del componente de modelo de datos base.
    >
    > Sin embargo, tenga en cuenta que el campo **Versión** se puede dejar en blanco solo en la versión de borrador de un componente de formato o asignación de modelo. Cuando cambia el estado de una asignación de modelo de ER o una configuración de formato de **Borrador** a **Completado**, este campo se rellena automáticamente con el número de revisión de modelo más alto que está disponible en la instancia de Finance actual. Si introduce una nueva enumeración o un nuevo valor de enumeración en la versión preliminar de su modelo de datos base y hace referencia a él en el componente de formato o asignación de modelo editable, complete esa versión preliminar de la configuración del modelo de datos base antes de que la versión de borrador de su configuración de asignación de modelo o formato se complete. De lo contrario, se lanzará una excepción de "Ruta no encontrada" cuando cambie el estado de la configuración de asignación del modelo o de formato de **Borrador** a **Completado**. El mensaje le informará que la enumeración a la que se hace referencia o el valor de enumeración faltan en el modelo de datos base.

La siguiente ilustración muestra las propiedades del origen de datos `$ReportDirection` que se configuró en la configuración del formato **Instat XML (DE) Contoso** de ER. La configuración **Instant XML (DE) Contoso** se ha [derivado](general-electronic-reporting.md#Configuration) desde la configuración **Instat XML (DE)**. Este origen de datos está configurado para usar la enumeración de modelos *ReportDirection* para ofrecer el campo de búsqueda apropiado en el cuadro de diálogo en runtime.

![Propiedades del origen de datos del tipo PARÁMETRO DE ENTRADA DE USUARIO en el cuadro de diálogo de la página del diseñador de formatos.](./media/er-user-input-parameter-data-sources-03.png)

### <a name="format-enumeration-user-input-parameter"></a>Parámetro de entrada de usuario de enumeración de formato

Utilice un origen de datos del tipo **Enumeración de formatos** \> **Parámetro de entrada de usuario de enumeración** para obtener el valor o valores requeridos de una sola enumeración de formatos. Cuando agregue un origen de datos de este tipo a un componente de ER, especifique las siguientes propiedades:

- En el campo **Enumeración de formatos**, especifique una enumeración del formato editable.

> [!NOTE]
> Las fuentes de datos de este tipo solo se pueden configurar en el ámbito del componente de formato editable.

## <a name="additional-resources"></a>Recursos adicionales

[Diseñador de fórmulas en los informes electrónicos](general-electronic-reporting-formula-designer.md)

[Iniciar valores de origen de datos del tipo USER INPUT PARAMETER desde el código fuente](er-initiate-uip-data-source-value-from-source-code.md)
