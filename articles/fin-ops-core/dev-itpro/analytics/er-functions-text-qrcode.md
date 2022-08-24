---
title: Función QRCODE de ER
description: Este artículo proporciona información general sobre cómo usar la función QRCODE de informes electrónicos (ER).
author: kfend
ms.date: 12/10/2019
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
ms.openlocfilehash: 9de62eefb82942ccc72e81bd9bf36eed07c99dba
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9287200"
---
# <a name="qrcode-er-function"></a>Función QRCODE de ER

[!include [banner](../includes/banner.md)]

La función `QRCODE` devuelve un valor de tipo *Contenedor* que presenta la imagen del código de respuesta rápida (código QR) para la cadena especificada en formato binario.

## <a name="syntax"></a>Sintaxis

```vb
QRCODE (text)
```

## <a name="arguments"></a>Argumentos

`text`: *Cadena*

Valor de tipo *Cadena* que representa el texto original.

## <a name="return-values"></a>Valores de retorno

*Contenedor*

La secuencia binaria resultante.

## <a name="example"></a>Ejemplo

Puede configurar un formato de informe electrónico (ER) para generar un documento de salida con formato de Microsoft Office (libros de Excel o documentos de Word) mediante una plantilla predefinida. Esta plantilla puede contener un objeto de tipo **Imagen** (libro de Excel) o un **Control de contenido de imagen** (Documento de Word) como marcador de posición para una imagen de código QR. Debe agregar al formato de ER configurado un elemento de **Celda** que se utilizará para rellenar este marcador de posición. Para especificar qué información se almacenará en un código QR, debe definir un enlace para este elemento **Celda**. Por ejemplo, puede configurar un enlace que contenga la siguiente expresión:

```vb
QRCODE (model.ListOfShelfLabels.LabelText)`
```

Al ejecutar el formato de ER configurado, el valor de texto del campo **LabelText** del origen de datos **model.ListOfShelfLabels** se usará para generar una imagen de código QR. Esta imagen reemplazará un marcador de posición de imagen de código QR en la plantilla de documento que se utiliza para generar un documento de salida. Cuando se escanea esta imagen del documento generado, devuelve el texto que se tomó del campo **LabelText** del origen de datos **model.ListOfShelfLabels**. Para obtener más información, consulte [Insertar imágenes y formas en los documentos generados con ER](electronic-reporting-embed-images-shapes.md).

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
