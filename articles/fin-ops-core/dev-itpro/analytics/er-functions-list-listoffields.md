---
title: Función LISTOFFIELDS de ER
description: En este artículo se proporciona información sobre cómo usar la función LISTOFFIELDS de informes electrónicos (ER).
author: kfend
ms.date: 12/12/2019
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
ms.openlocfilehash: e795251004136469f64e8ebbb190a3bceaa382ed
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9288180"
---
# <a name="listoffields-er-function"></a>Función LISTOFFIELDS de ER

[!include [banner](../includes/banner.md)]

La función `LISTOFFIELDS` devuelve un valor *Lista de registros* que se crea en función de la estructura del argumento especificado del tipo *Enumeración* o *Contenedor (registro)*.

## <a name="syntax-1"></a>Sintaxis 1

```vb
LISTOFFIELDS (path)
```

## <a name="syntax-2"></a>Sintaxis 2

```vb
LISTOFFIELDS (path, language)
```

## <a name="arguments"></a>Argumentos

`path`: referencia de origen de datos

La ruta de referencia válida de un origen de datos de uno de los siguientes tipos de datos:

- Enumeración de modelo
- Enumeración de formato
- Enumeración de aplicaciones
- Contenedor (registro)

`language`: *Cadena*

Texto que representa un código de idioma.

## <a name="return-values"></a>Valores de retorno

*Lista de registros*

La lista de registros resultante.

## <a name="usage-notes"></a>Notas de uso

La lista que se crea consta de registros con los siguientes campos:

- **Nombre** (tipo de datos *Cadena*)
- **Etiqueta** (tipo de datos *Cadena*)
- **Descripción** (tipo de datos *Cadena*)
- **IsTranslated** (tipo de datos *Booleano*)

Si el argumento `path` se refiere a una fuente de datos del tipo *Contenedor (registro)*, para cada campo del registro contenedor referenciado, se agrega un nuevo registro a la lista que se crea. Para cada registro que se crea, el campo **Nombre** devuelve el nombre del campo del registro de contenedor referenciado para el que se creó el registro actual.

Si el argumento `path` se refiere a un origen de datos de los tipos *Enumeración*, para cada valor de enumeración de la enumeración referenciada, se agrega un nuevo registro a la lista que se crea. Para cada registro que se crea, el campo **Nombre** devuelve el valor de la enumeración referenciada para el registro actual para el que se ha creado, el campo **Descripción** devuelve la descripción de esa enumeración, y el campo **Etiqueta** devuelve la etiqueta de esa enumeración.

En tiempo de ejecución, cuando se usa la sintaxis 1, los campos **Etiqueta** y **Descripción** deben devolver valores de devolución que se basan en la configuración de idioma del formato de informe electrónico (ER) que se está ejecutando:

- Si las etiquetas y descripciones para el idioma solicitado están disponibles, los campos **Etiqueta** y **Descripción** devuelven valores que se basan en ese idioma y el campo **IsTranslated** devuelve **True**.
- Si las etiquetas y las descripciones para el idioma solicitado no están disponibles, los campos **Etiqueta** y **Descripción** devuelven valores que se basan en el idioma predeterminado **EN-US** y el campo **IsTranslated** devuelve **False**.

En tiempo de ejecución, cuando se usa la sintaxis 2, los campos **Etiqueta** y **Descripción** deben devolver valores de devolución que se basan en el idioma que se define como el segundo argumento de la función llamada:

- Si las etiquetas y descripciones para el idioma solicitado están disponibles, los campos **Etiqueta** y **Descripción** devuelven valores que se basan en ese idioma y el campo **IsTranslated** devuelve **True**.
- Si las etiquetas y las descripciones para el idioma solicitado no están disponibles, los campos **Etiqueta** y **Descripción** devuelven valores que se basan en el idioma **EN-US** y el campo **IsTranslated** devuelve **False**.

## <a name="example-1"></a>Ejemplo 1

En la siguiente ilustración, se introduce una enumeración en un modelo de datos de ER.

<a href="./media/ger-listoffields-function-model-enumeration.png"><img src="./media/ger-listoffields-function-model-enumeration-e1474545790761.png" alt="Enumeration in a model" class="alignnone wp-image-1203943 size-full" width="514" height="155" /></a>

La siguiente ilustración muestra estos detalles:

- La enumeración del modelo se inserta en un informe como origen de datos.
- Una expresión del ER utiliza la enumeración de modelo como un parámetro de la función `LISTOFFIELDS`.
- Un origen de datos del tipo *Lista de registro* se inserta en un informe mediante la expresión de ER que se crea.

<a href="./media/ger-listoffields-function-in-format-expression.png"><img src="./media/ger-listoffields-function-in-format-expression-e1474546110395.png" alt="Format" class="alignnone wp-image-1204033 size-full" width="549" height="318" /></a>

El siguiente ejemplo muestra los elementos del formato de ER que están enlazados al origen de datos del tipo *Lista de registro* creado mediante la función de `LISTOFFIELDS`.

<a href="./media/ger-listoffields-function-format-design.png"><img src="./media/ger-listoffields-function-format-design.png" alt="Format design" class="alignnone size-full wp-image-1204043" width="466" height="221" /></a>

La siguiente ilustración muestra el resultado cuando se ejecuta el formato diseñado.

<a href="./media/ger-listoffields-function-format-output.png"><img src="./media/ger-listoffields-function-format-output.png" alt="Format output" class="alignnone size-full wp-image-1204053" width="585" height="158" /></a>

> [!NOTE] 
> Basado en la configuración de idioma de los elementos del formato del **ARCHIVO** principal y de la **CARPETA**, el texto traducido para las etiquetas y las descripciones se introduce en la salida del formato de ER.

## <a name="example-2"></a>Ejemplo 2

Por ejemplo, utiliza el tipo de origen de datos *Campo calculado* para configurar los orígenes de datos **enumType\_de** y **enumType\_deCH** para la enumeración del modelo de datos **enumType**.

- **enumType\_de** = `LISTOFFIELDS (enumType, "de")`
- **enumType\_deCH** = `LISTOFFIELDS (enumType, "de-CH")`

En este caso, puede usar la siguiente expresión para obtener la etiqueta del valor de enumeración en alemán suizo, si esta traducción está disponible. Si la traducción alemana suiza no está disponible, la etiqueta se encuentra en alemán.

```vb
IF (NOT (enumType_deCH.IsTranslated), enumType_de.Label, enumType_deCH.Label)
```

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de lista](er-functions-category-list.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
