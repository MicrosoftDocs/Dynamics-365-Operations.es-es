---
title: Función GETENUMVALUEBYNAME de ER
description: En este artículo se proporciona información sobre cómo usar la función GETENUMVALUEBYNAME de informes electrónicos (ER).
author: NickSelin
ms.date: 09/23/2020
ms.prod: ''
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c1ebadd72dda296de67ac041957cffb9ab407b7c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8858723"
---
# <a name="getenumvaluebyname-er-function"></a>Función GETENUMVALUEBYNAME de ER

[!include [banner](../includes/banner.md)]

La función `GETENUMVALUEBYNAME` busca un valor específico de tipo *Enum* en el origen de datos de enumeración especificado utilizando el nombre de enumeración especificado como un valor de tipo *Cadena*. Si el valor *Enum* se encuentra, la función lo devuelve. De lo contrario, la función devuelve el valor de enumeración **nulo**.

## <a name="syntax"></a>Sintaxis

```vb
GETENUMVALUEBYNAME (enumeration data source path, enumeration value text)
```

## <a name="arguments"></a>Argumentos

`enumeration data source path`: *Enumeración*

La ruta válida de un origen de datos de uno de los siguientes tipos de enumeración:

- Enumeración de modelo de informes electrónicos (ER)
- Enumeración de formato de ER
- Enumeración de Microsoft Dynamics 365 Finance

`enumeration value text`: *Cadena*

Un valor de cadena que representa el nombre de un valor de enumeración único.

## <a name="return-values"></a>Valores de retorno

*Enum* anulable

El valor de enumeración resultante.

## <a name="usage-notes"></a>Notas de uso

No se produce ninguna excepción si no se encuentra un valor de tipo *Enum* con el nombre del valor de enumeración especificado como un valor de tipo *Cadena*.

## <a name="example-1"></a>Ejemplo 1

En la siguiente ilustración, la enumeración **ReportDirection** se introduce en un modelo de datos. Tenga en cuenta que se definen etiquetas para los valores de enumeración.

![Valores disponibles para una enumeración de modelo de datos.](./media/ER-data-model-enumeration-values.PNG)

La siguiente ilustración muestra estos detalles:

- El origen de datos **$Direction** se configura en un informe de ER. Este origen de datos se configura en función de la enumeración del modelo **ReportDirection**.
- La expresión `$IsArrivals` está diseñada para usar el origen de datos **$Direction** basado en la enumeración del modelo como un parámetro de esta función.
- El valor de esta expresión de comparación es **TRUE**.

![Ejemplo de enumeración de modelo de datos.](./media/ER-data-model-enumeration-usage.PNG)

## <a name="example-2"></a>Ejemplo 2

Las funciones `GETENUMVALUEBYNAME` y [`LISTOFFIELDS`](er-functions-list-listoffields.md) permiten obtener valores y etiquetas de enumeraciones compatibles como valores de texto. (Las enumeraciones admitidas son enumeraciones de aplicaciones, enumeraciones de modelos de datos y enumeraciones de formato).

En la siguiente ilustración, el origen de datos **TransType** se introduce en una asignación de modelos. Este origen de datos hace referencia a la enumeración de aplicación **LedgerTransType**.

![Fuente de datos de un mapeo de modelo que se refiere a una enumeración de aplicaciones.](./media/er-functions-text-getenumvaluebyname-example2-1.png)

En la siguiente ilustración se muestra el origen de datos **TransTypeList** que se configura en una asignación de modelos. Este origen de datos se configura en función de la enumeración de aplicación **TransType**. La función `LISTOFFIELDS` se utiliza para devolver todos los valores de enumeración como una lista de registros que contienen campos. De esta manera, se exponen los detalles de cada valor de enumeración.

> [!NOTE]
> El campo **EnumValue** está configurado para el origen de datos **TransTypeList** mediante la expresión `GETENUMVALUEBYNAME(TransType, TransTypeList.Name)`. Este campo devuelve un valor de enumeración para cada registro de esta lista.

![Fuente de datos de un mapeo de modelo que devuelve todos los valores de enumeración de una enumeración seleccionada como una lista de registros.](./media/er-functions-text-getenumvaluebyname-example2-2.png)

En la siguiente ilustración se muestra el origen de datos **VendTrans** que se configura en una asignación de modelos. Esta fuente de datos devuelve registros de transacciones de proveedores de la tabla de aplicación **VendTrans**. El tipo de libro mayor de cada transacción se define por el valor del campo **TransType**.

> [!NOTE]
> El campo **TransTypeTitle** está configurado para el origen de datos **VendTrans** mediante la expresión `FIRSTORNULL(WHERE(TransTypeList, TransTypeList.EnumValue = @.TransType)).Label`. Este campo devuelve la etiqueta de un valor de enumeración de la transacción actual como texto, si este valor de enumeración está disponible. En caso contrario, devuelve un valor de cadena en blanco.
>
> El campo **TransTypeTitle** está vinculado al campo **LedgerType** de un modelo de datos que permite que esta información se utilice en todos los formatos ER que utilizan el modelo de datos como fuente de datos.

![Fuente de datos de un mapeo de modelo que devuelve transacciones de proveedores.](./media/er-functions-text-getenumvaluebyname-example2-3.png)

La siguiente ilustración muestra cómo puede utilizar el [depurador de fuente de datos](er-debug-data-sources.md) para probar el mapeo del modelo configurado.

![Usar el depurador de la fuente de datos para probar el mapeo del modelo configurado.](./media/er-functions-text-getenumvaluebyname-example2-4.gif)

El campo **LedgerType** de un modelo de datos expone las etiquetas de tipos de transacciones como se esperaba.

Si planea utilizar este enfoque para una gran cantidad de datos transaccionales, debe considerar el rendimiento de la ejecución. Para obtener más información, vea [Realizar un seguimiento de la ejecución de los formatos de ER para solucionar problemas de rendimiento](trace-execution-er-troubleshoot-perf.md).

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)

[Realizar un seguimiento de la ejecución de los formatos de ER para solucionar problemas de rendimiento](trace-execution-er-troubleshoot-perf.md)

[Función LISTOFFIELDS de ER](er-functions-list-listoffields.md)

[Función FIRSTORNULL de ER](er-functions-list-firstornull.md)

[Función WHERE de ER](er-functions-list-where.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]