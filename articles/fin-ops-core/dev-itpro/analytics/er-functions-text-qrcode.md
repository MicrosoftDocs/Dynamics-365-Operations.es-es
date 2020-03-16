---
title: Función QRCODE de ER
description: Este tema proporciona información general sobre cómo usar la función QRCODE de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ERDataModelDesigner, ERExpressionDesignerFormula, ERMappedFormatDesigner, ERModelMappingDesigner
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 58771
ms.assetid: 24223e13-727a-4be6-a22d-4d427f504ac9
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8a52dbce29140591baf4be97baef237dce1f2511
ms.sourcegitcommit: 3c1eb3d89c6ab9bd70b806ca42ef9df74cf850bc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/12/2020
ms.locfileid: "3040857"
---
# <a name="QRCODE">Función QRCODE de ER</a>

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
