---
title: Diseños de etiquetas de ruta de documentos
description: Este artículo describe cómo usar métodos de formato para imprimir valores en etiquetas.
author: perlynne
ms.date: 04/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLicensePlateLabel, WHSLicensePlateLabelBuildConfig, WHSLicensePlateLabel, WHSDocumentRoutingLayout
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2012-04-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: a4e0c16b71c257cae832870ca58679884047ea16
ms.sourcegitcommit: 9e6a9d644a34158390c6e209e80053ccbdb7d974
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/20/2022
ms.locfileid: "9708655"
---
# <a name="document-routing-label-layout"></a>Diseño de etiquetas de ruta de documentos

[!include [banner](../includes/banner.md)]

En este artículo se describe cómo crear diseños para etiquetas de matrículas, contenedores y olas. También proporciona pautas para usar el lenguaje de programación Zebra (ZPL) que se usa para crear los diseños.

Los diseños de etiqueta de enrutamiento del documento definen la forma en que se disponen las etiquetas y los datos que se imprimen en ellas. Configure los puntos de activación de impresión cuando configure elementos de menú del dispositivo móvil y plantillas de trabajo.

La información de este artículo se aplica a todos los diseños de etiquetas de enrutamiento de documentos, incluidos los diseños para [etiquetas de matrícula](tasks/license-plate-label-printing.md), [etiquetas de contenedores](print-container-labels.md) y [etiquetas de ola](configure-wave-label-printing.md).

Puede imprimir etiquetas muy complejas, siempre que el dispositivo de impresión pueda interpretar el texto que se le envía. Por ejemplo, un diseño ZPL que incluye un código de barras podría parecerse al siguiente ejemplo.

```dos
^XA~TA000~JSN^LT0^MNW^MTD^PON^PMN^LH0,0^JMA^PR2,2~SD15^JUS^LRN^CI0^XZ
^XA
^MMT
^PW320
^LL0160
^LS0
^FT20,58^A0N,28,28^FH\^FDLabel:^FS
^FT20,81^AAN,18,10^FH\^FD$LicensePlateId$^FS
^BY1,3,17^FT20,106^BCN,,Y,N,N,A
^FD$LicensePlateId$^FS
^PQ1,,,Y^XZ
```

Como parte del proceso de impresión de etiquetas, el texto `$LicensePlateId$` en este ejemplo será reemplazado con un valor de datos. Varias herramientas de generación de etiquetas ampliamente disponibles pueden ayudarlo a formatear el texto para el diseño de la etiqueta. Muchas de estas herramientas son compatibles con el formato `$FieldName$`. Además, Microsoft Dynamics 365 Supply Chain Management utiliza una lógica de formato especial como parte de la asignación de campo para el diseño de enrutamiento de documentos.

Para ver los valores que se imprimirán, vaya a **Gestión de almacenes \> Consultas e informes \> Etiquetas de matrícula de entidad**.

## <a name="turn-on-this-feature-for-your-system"></a>Activar esta función para su sistema

Si su sistema aún no incluye las funciones descritas en este artículo, vaya a [Gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) y active la característica *Diseños mejorados de etiquetas de matrículas*. A partir de la versión 10.0.21 de Supply Chain Management, esta característica está activada de forma predeterminada. A partir de la versión 10.0.25 de Supply Chain Management, esta característica es obligatoria y no se puede desactivar.

## <a name="custom-number-formats"></a>Formatos de números personalizados

Puede personalizar el formato de los valores de campo numéricos que se imprimen utilizando códigos que tengan el siguiente formato.

```dos
$FieldName:FormatString$
```

A continuación aparece una explicación de este formato:

- `FieldName` es el nombre del campo de datos (como **Cantidad**).
- `FormatString` define cómo se deben imprimir los datos.

Los siguientes ejemplos muestran cómo puede personalizar el campo cantidad de trabajo (**Cantidad**):

- Para mostrar siempre cuatro dígitos (usando ceros como marcadores de posición), use `$Qty:0000$`. Por ejemplo, si la cantidad es 10, la etiqueta mostrará "0010".
- Para mostrar siempre dos lugares decimales, use `$Qty:0.00$`. Por ejemplo, si la cantidad es 10, la etiqueta mostrará "10,00".

Para obtener una lista completa de las cadenas de formato de número disponibles, vea [Cadenas de formato numérico personalizado](/dotnet/standard/base-types/custom-numeric-format-strings).

## <a name="custom-string-formats"></a>Formatos de cadena personalizados

Puede eliminar los primeros caracteres de una cadena utilizando el siguiente campo y código de formato.

```dos
$FieldName:#..$
```

Aquí, `#` especifica el número de caracteres que se omitirán. Por ejemplo, para imprimir un número de matrícula de entidad de almacén de código de contenedor de envío en serie (SSCC) que no incluye los dos primeros caracteres, use `$LicensePlateId:2..$`. En este caso, la matrícula de entidad de almacén 0011111111111222221 se imprimirá como "11111111111222221".

## <a name="custom-datetime-formats"></a>Formatos de fecha / hora personalizados

El siguiente ejemplo muestra cómo puede controlar el formato que se utiliza para imprimir fechas.

```dos
$PrintedDate:dd-MM-yyyy$
```

En este ejemplo, la fecha 30 de abril de 2020 se imprimirá como "30-04-2020".

Para obtener una lista completa de las formatos de fecha / hora disponibles, vea [Cadenas de formato de fecha y personalizadas](/dotnet/standard/base-types/custom-date-and-time-format-strings).

## <a name="print-individual-lines-from-multiline-data"></a>Imprima líneas individuales a partir de datos multilínea

Si un campo de datos contiene varias líneas (es decir, líneas que están separadas por saltos de línea), puede imprimir una línea individual utilizando el siguiente formato.

```dos
$FieldName[#]$
```

Aquí, `#` es el número de línea que desea imprimir. (Use 1 para la primera línea).

Por ejemplo, su sistema tiene un campo `AdditionalAddress` que almacena la siguiente dirección multilínea:

Contoso Inc.  
123 Nombre de la calle  
Alguna ciudad, algún estado

Puede imprimir esta dirección, una línea a la vez, utilizando los siguientes códigos.

| Código | Texto impreso |
|---|---|
| `$AdditionalAddress[1]$` | Contoso Inc. |
| `$AdditionalAddress[2]$` | 123 Nombre de la calle |
| `$AdditionalAddress[3]$` | Alguna ciudad, algún estado |

## <a name="print-and-format-from-a-display-method"></a>Imprima y formatee desde un método de visualización

Puede imprimir desde un método de visualización utilizando el siguiente formato.

```dos
$DisplayMethod()$
```

Puede combinar este formato con otros tipos que se describieron anteriormente en este artículo. Por ejemplo, tiene un método de visualización que se denomina `DisplayListOfItemsNumbers()`, y desea imprimir el primer número de elemento de este método. En este caso, puede usar el código siguiente.

```dos
$DisplayListOfItemsNumbers()[1]$
```

## <a name="more-information-about-how-to-print-labels"></a>Más información sobre cómo imprimir etiquetas

Para obtener más información sobre cómo configurar e imprimir etiquetas, vea los siguientes artículos:

- [Impresión de la etiqueta de matrícula](tasks/license-plate-label-printing.md)
- [Imprimir etiquetas de contenedores](print-container-labels.md)
- [Impresión de etiquetas de oleadas](configure-wave-label-printing.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
