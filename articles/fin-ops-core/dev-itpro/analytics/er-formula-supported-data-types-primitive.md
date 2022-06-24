---
title: Tipos de datos primitivos admitidos para fórmulas de informes electrónicos
description: Este artículo proporciona información sobre las entidades de datos primitivas que son compatibles con las fórmulas de informes electrónicos (ER).
author: NickSelin
ms.date: 06/02/2021
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 41cda188e774630e96c46fba1200fd2e640f9915
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891886"
---
# <a name="supported-primitive-data-types-for-electronic-reporting-formulas"></a>Tipos de datos primitivos admitidos para fórmulas de informes electrónicos

[!include [banner](../includes/banner.md)]

Este artículo proporciona información sobre las entidades de datos primitivas que son compatibles con las expresiones de [informes electrónicos (ER)](general-electronic-reporting.md). A continuación se indica una lista de las entidades de datos primitivos:

- [booleano](#boolean)
- [fecha](#date)
- [fecha y hora](#datetime)
- [enumeración](#enumeration)
- [guid](#guid)
- [entero](#integer)
- [int64](#int64)
- [real](#real)
- [cadena](#string)

## <a name="boolean"></a><a name="boolean"></a>Booleano

La entidad datos primitivos *booleanos* contiene un valor que se evalúa como *cierto* o como *falso*. Puede utilizar las palabras clave literales reservadas **Verdadero** y **Falso** cuando se espere una expresión *booleana*. El valor predeterminado es *falso*.

La representación interna de un *booleano* es un *entero*. El valor *entero* 0 (cero) se evalúa como *falso* y todos los demás valores *enteros* se evalúan como *verdaderos*. Cuando usted [valide](general-electronic-reporting-formula-designer.md#TestFormula) una expresión configurada que devuelve un *booleano* en el [Diseñador de fórmulas ER](er-advanced-formula-editor.md), el panel de resultados de la prueba devuelve *0* (cero) cuando una expresión es *falsa*. De lo contrario, el panel de resultados de la prueba presenta *1*.

Un *booleano* no tiene conversiones implícitas. Sin embargo, puede utilizar la función [TEXT](er-functions-text-text.md) para convertir explícitamente un *booleano* a una *cadena*:

- El valor *falso* se convierte en la cadena de texto **Falso**.
- El valor *verdadero* se convierte en la cadena de texto **Verdadero**.

> [!NOTE]
> Esta conversión no depende del [contexto](er-design-multilingual-reports.md) del idioma y la cultura proporcionados.

Los [operadores](er-formula-language.md#Operators) de comparación son el único tipo de operador que se puede utilizar con el tipo de datos *booleanos*. Los siguientes operadores se pueden utilizar para comparar dos valores *booleanos*: \<\> y =.

## <a name="date"></a><a name="date"></a>Fecha

El tipo de datos primitivos *fecha* contiene el día, el mes y el año. Las fechas se puede iniciar utilizando las siguientes funciones:

- [DATEVALUE](er-functions-datetime-datevalue.md)
- [NULLDATE](er-functions-datetime-nulldate.md)
- [SESSIONTODAY](er-functions-datetime-sessiontoday.md)
- [TODAY](er-functions-datetime-today.md)

El tipo de datos *fecha* puede contener fechas entre el 1 de enero de 1900 y el 31 de diciembre de 2154. El valor predeterminado es **nulo**, y la representación interna es la fecha 1 de enero de 1900.

Una *fecha* no tiene conversiones implícitas. Sin embargo, puede utilizar las siguientes funciones de conversión explícitas:

- [DATEFORMAT](er-functions-datetime-dateformat.md)
- [DATETODATETIME](er-functions-datetime-datetodatetime.md)
- [TEXT](er-functions-text-text.md)

La función [ADDDAYS](er-functions-datetime-adddays.md) le permite sumar y restar días a las fechas. De esta manera, puede mover la fecha un número específico de días hacia el futuro y hacia el pasado. La función [DAYS](er-functions-datetime-days.md) le permite restar fechas entre sí y calcular la diferencia en días. Para obtener más información sobre la transformación de valores de *fecha*, consulte [Lista de funciones de ER en la categoría de Fecha y hora](er-functions-category-datetime.md).

Los [operadores](er-formula-language.md#Operators) de comparación son el único tipo de operador que se puede utilizar con el tipo de datos *fecha*. Los siguientes operadores se pueden utilizar para comparar dos valores *fecha*: \<\>, \<, \<=, =, \> y \>=.

## <a name="datetime"></a><a name="datetime"></a>Datetime

El tipo de datos primitivos *datetime* combina el tipo *fecha* y un valor que representa el tiempo transcurrido desde la medianoche. El tiempo se expresa en horas, minutos, segundos y fracciones de segundo. Un valor *datetime* también contiene información sobre la zona horaria.

El tipo de datos *datetime* puede contener fechas entre el 1 de enero de 1900 (1900-01-01T00:00:00.0000000+00:00 en el [formato](/dotnet/standard/base-types/standard-date-and-time-format-strings)) ida y vuelta, y 31 de diciembre de 2154 (2154/12/31T11:59:59.9999999+00:00 en el formato de ida y vuelta). La unidad de tiempo más pequeña en *datetime* es una diez millonésima de segundo.

> [!NOTE]
> Cuando el [especificador](/dotnet/standard/base-types/standard-date-and-time-format-strings) **hh** se utiliza para horas, los valores de tiempo superiores a 12:59:59:9999999 no se pueden interpretar como tiempos válidos.
>
> Cuando el especificador **HH** se utiliza para horas, los valores de tiempo superiores a 23:59:59:9999999 no se pueden interpretar como tiempos válidos.

El valor predeterminado es **null**, y la representación interna es la fecha 1 de enero de 1900 (1900-01-01T00:00:00.0000000+00:00 en formato de ida y vuelta).

La fecha y la hora se pueden iniciar utilizando las siguientes funciones:

- [DATETIMEVALUE](er-functions-datetime-datetimevalue.md)
- [NULNULLDATETIMELDATE](er-functions-datetime-nulldatetime.md)
- [SESSIONNOW](er-functions-datetime-sessionnow.md)
- [NOW](er-functions-datetime-now.md)

*datetime* no tiene conversiones implícitas. Sin embargo, puede utilizar las siguientes funciones de conversión explícitas:

- [DATETIMEFORMAT](er-functions-datetime-datetimeformat.md)
- [TEXT](er-functions-text-text.md)

Para obtener más información sobre la transformación de valores de *datetime*, consulte [Lista de funciones de ER en la categoría de Fecha y hora](er-functions-category-datetime.md).

Los [operadores](er-formula-language.md#Operators) de comparación son el único tipo de operador que se puede utilizar con el tipo de datos *datetime*. Los siguientes operadores se pueden utilizar para comparar dos valores *datetime*: \<\>, \<, \<=, =, \> y \>=.

## <a name="enumeration"></a><a name="enumeration"></a>Enumeración

El tipo de datos primitivos *enumeración* es una lista de literales. Puede utilizar enumeraciones que se definen en la aplicación [código fuente](../dev-ref/xpp-data-primitive.md#enum). También puede introducir sus propias enumeraciones en el modelo de datos ER y en los componentes formato ER.

Una aplicación *enumeración* se puede utilizar en expresiones de cualquier asignación de modelo ER y formato ER.

La siguiente ilustración muestra cómo puede agregar la enumeración de modelo **CustVendCorrectiveReasonCode** al modelo de datos ER editable.

[![Configurar una enumeración de modelo en el diseñador de modelo de datos de ER.](./media/er-formula-supported-data-types-primitive-enum1.gif)](./media/er-formula-supported-data-types-primitive-enum1.gif)

Una *enumeración* de modelo se puede utilizar en expresiones de cualquier asignación de modelo ER y formato ER que se crearon bajo un modelo de datos donde la *enumeración* se presentó.

La siguiente ilustración muestra cómo puede agregar la enumeración de formato **Lista de subcategorías de cargo revertido Natura** al formato ER editable.

[![Configurar una enumeración de formato en el diseñador de formato de ER.](./media/er-formula-supported-data-types-primitive-enum2.gif)](./media/er-formula-supported-data-types-primitive-enum2.gif)

Una enumeración de *formato* solo se puede utilizar en expresiones del formato ER donde la *enumeración* se presentó.

Debe usar el tipo apropiado de fuentes de datos de ER para traer una enumeración específica a un componente de ER configurado como una constante o como un valor que el usuario que está ejecutando una solución de ER definió en el cuadro de diálogo en tiempo de ejecución.

- Se puede acceder a las enumeraciones de aplicaciones utilizando los orígenes de datos **Dynamics 365 for Operations \ Enumeración** y **General \ Parámetros de entrada de usuario**. La siguiente ilustración muestra cómo puede agregar los orígenes de datos **appenumNoYes** y **uipNoYes** que se refieren a la enumeración de aplicación **NoYes**.

    [![Agregar orígenes de datos de enumeración de aplicaciones en el diseñador de formato ER.](./media/er-formula-supported-data-types-primitive-enum3a.gif)](./media/er-formula-supported-data-types-primitive-enum3a.gif)

- Se puede acceder a las enumeraciones de modelo de datos utilizando los orígenes de datos **Modelo de datos \ Enumeración** y **Parámetros de entrada de usuario Modelo de datos \ Enumeración**. La siguiente ilustración muestra cómo puede agregar los orígenes de datos **CustVendCorrectiveReasonCode** que se refieren a la enumeración de modelo de datos **CustVendCorrectiveReasonCode** al formato ER editable.

    [![Agregar orígenes de datos de enumeración de modelos en el diseñador de formato ER.](./media/er-formula-supported-data-types-primitive-enum3b.gif)](./media/er-formula-supported-data-types-primitive-enum3b.gif)

- Se puede acceder a las enumeraciones de formato utilizando los orígenes de datos **Formato \ Enumeración** y **Parámetros de entrada de usuario Formato \ Enumeración**. La siguiente ilustración muestra cómo puede agregar los orígenes de datos **NaturaReverseCharge** que se refieren a la enumeración de formato **Natura reverse charge subcategories** al formato ER editable.

    [![Agregar orígenes de datos de enumeración de formato en el diseñador de formato ER.](./media/er-formula-supported-data-types-primitive-enum3c.gif)](./media/er-formula-supported-data-types-primitive-enum3c.gif)

Una *enumeración* no tiene conversiones implícitas. Sin embargo, puede utilizar la función de conversión [TEXT](er-functions-text-text.md) para convertir una *enumeración* a una cadena de texto. Esta conversión no depende del idioma. Para saber cómo puede asociar un valor de *enumeración* con las etiquetas específicas del idioma correspondientes, consulte los ejemplos de uso para las funciones [LISTOFFIELDS](er-functions-list-listoffields.md) y [GETENUMVALUEBYNAME](er-functions-text-getenumvaluebyname.md).

Los [operadores](er-formula-language.md#Operators) de comparación son el único tipo de operador que se puede utilizar con el tipo de datos *enumeración*. Los siguientes operadores se pueden utilizar para comparar dos valores de *enumeración*: \<\> y =.

## <a name="guid"></a><a name="guid"></a>Guid

El tipo de datos primitivos *guid* contiene un valor de identificador único global (GUID). Un GUID es un valor que se puede utilizar en todas las computadoras y redes, siempre que se requiera un identificador único. Es poco probable que se duplique el número. Un GUID válido cumple todas las siguientes especificaciones:

- Debe haber 32 dígitos hexadecimales.
- Además, debe haber cuatro guiones incrustados en las siguientes ubicaciones: 8-4-4-4-12.
- Además, llaves opcionales \{\} se pueden agregar al principio y al final de la cadena. Por ejemplo, las cadenas **\{2CDB0FE7-D7B3-4938-A0F0-FE28FB8FE212\}** y **2CDB0FE7-D7B3-4938-A0F0-FE28FB8FE212** son cadenas GUID válidas.
- Por lo tanto, debe haber un total de 36 o 38 caracteres, dependiendo de si se agregan llaves.
- Las letras que se utilizan como dígitos hexadecimales pueden ser mayúsculas (A–F), minúsculas (a–f) o mixtas.

Se pueden utilizar las siguientes funciones de conversión explícitas:

- [GUIDVALUE](er-functions-text-guidvalue.md)
- [TEXT](er-functions-text-text.md)

Los [operadores](er-formula-language.md#Operators) de comparación son el único tipo de operador que se puede utilizar con el tipo de datos *guid*. Los siguientes operadores se pueden utilizar para comparar dos valores de *guid*: \<\> y =.

## <a name="integer"></a><a name="integer"></a>Entero

El tipo de datos primitivos *entero* representa un número que no tiene decimales. Los enteros se utilizan como variables de control en declaraciones repetitivas o como índices en listas de registros.

Un literal *entero* es el número entero que se ingresa directamente en una [expresión](general-electronic-reporting-formula-designer.md#formula-designer-overview) ER (fórmula), como **12345**. Un *entero* tiene 32 bits de ancho. El valor predeterminado es **0**, y la representación interna es un número largo. Un *entero* se convierte automáticamente en un *verdadero*.

Además, se pueden utilizar las siguientes funciones de conversión explícitas:

- [INTVALUE](er-functions-conversion-intvalue.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)

El rango de un *entero* es \[-2,147,483,647 : 2,147,483,647\]. Todos los enteros de este rango se pueden usar como literales.

Todos los [operadores](er-formula-language.md#Operators) de comparación y matemáticos se pueden utilizar con el tipo de datos *entero*.

## <a name="int64"></a><a name="int64"></a>Int64

El tipo de datos primitivos *int64* representa un número que no tiene decimales. Los valores *Int64* se utilizan como variables de control en declaraciones repetitivas o como identificadores de registro.

Un *int64* tiene 64 bits de ancho. El valor predeterminado es **0**, y la representación interna es un número largo. Un *int64* se convierte automáticamente en un *verdadero*.

Además, se pueden utilizar las siguientes funciones de conversión explícitas:

- [INT64VALUE](er-functions-conversion-int64value.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)

El rango de un *int64* es \[-9,223,372,036,854,775,807 : 9,223,372,036,854,775,807\].

Todos los [operadores](er-formula-language.md#Operators) de comparación y matemáticos se pueden utilizar con el tipo de datos *int64*.

## <a name="real"></a><a name="real"></a>Real

El tipo de datos primitivos *verdadero* puede contener valores decimales además de enteros. Puede usar literales decimales en cualquier lugar donde *verdadero* se espera. Un literal decimal es el decimal que se ingresa directamente en el código, como **2.19**.

> [!NOTE]
> En las expresiones ER, siempre se usa un punto (.) como separador decimal.

Los verdaderos se pueden usar en todas las expresiones y se pueden usar tanto con operadores de comparación como con operadores aritméticos. Un *verdadero* tiene una precisión de 16 dígitos significativos. El valor predeterminado para un *verdadero* es **0.0** y la representación interna es un número digital codificado en binario (BCD). La codificación BCD permite representaciones exactas de valores que son múltiplos de 0,1. El rango de una variable de *verdadero* es -(10)<sup>127</sup> hasta (10)<sup>127</sup>. Todos los verdaderos en este rango se pueden usar como literales en expresiones ER.

Un *verdadero* no tiene conversiones implícitas. Sin embargo, puede utilizar las siguientes funciones para convertir explícitamente un *verdadero* a otros tipos de datos y otros tipos de datos a un *verdadero*:

- [INTVALUE](er-functions-conversion-intvalue.md)
- [INT64VALUE](er-functions-conversion-int64value.md)
- [NUMBERFORMAT](er-functions-text-numberformat.md)
- [TEXT](er-functions-text-text.md)
- [VALUE](er-functions-conversion-value.md)

Todos los [operadores](er-formula-language.md#Operators) de comparación y matemáticos se pueden utilizar con el tipo de datos *verdadero*.

## <a name="string"></a><a name="string"></a>Cadena

El tipo de datos primitivos *cadena* representa una secuencia de caracteres que se utilizan como textos, números de cuenta, direcciones y números de teléfono.

Los literales de *cadena* son caracteres entre comillas (""). Los literales de *cadena* se pueden usar donde se esperen valores de *cadena* en las expresiones ER. Puede utilizar cadenas en expresiones lógicas, como comparaciones. También puede concatenar valores de *cadena* usando el operador **\&** o la función [CONCATENATE](er-functions-text-concatenate.md).

> [!NOTE]
> Si concatena dos valores de *cadena* y desea que la *cadena* resultante abarque más de una línea, utilice el separador de salto de línea entre los valores. Para la salida de TEXTO, este separador puede ser un carácter que se genera usando la expresión [CHAR](er-functions-text-char.md)(10) o CHAR(13). Para HTML, puede ser la etiqueta **\<br\>**.

El valor predeterminado para una *cadena* es una cadena de texto en blanco que no tiene caracteres y la representación interna es una lista de caracteres.

No hay conversiones automáticas para cadenas. Sin embargo, se pueden utilizar las siguientes funciones de conversión explícitas:

- [CHAR](er-functions-text-char.md)
- [FORMAT](er-functions-text-format.md)
- [LEFT](er-functions-text-left.md)
- [LEN](er-functions-text-len.md)
- [MID](er-functions-text-mid.md)
- [PADLEFT](er-functions-text-padleft.md)
- [REPLACE](er-functions-text-replace.md)
- [RIGHT](er-functions-text-right.md)
- [TEXT](er-functions-text-text.md)
- [TRANSLATE](er-functions-text-translate.md)
- [TRIM](er-functions-text-trim.md)
- [UPPER](er-functions-text-upper.md)

Para obtener más información sobre la transformación de valores de *cadena*, consule [Lista de funciones de ER de la categoría de texto](er-functions-category-text.md).

Una *cadena* puede contener un número indefinido de caracteres.

Todos los [operadores](er-formula-language.md#Operators) de comparación se pueden utilizar con el tipo de datos *cadena*.

## <a name="additional-resources"></a>Recursos adicionales

- [Visión general de los informes electrónicos](general-electronic-reporting.md)
- [Idioma de fórmulas en los informes electrónicos](er-formula-language.md)
- [Tipos de datos compuestos admitidos](er-formula-supported-data-types-composite.md)
