---
title: Función FORMAT de ER
description: En este tema se proporciona información sobre cómo usar la función FORMAT de informes electrónicos (ER).
author: NickSelin
manager: kfend
ms.date: 12/12/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
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
ms.openlocfilehash: 8b347a7209ee543f6bd687c2864203eb632d6a4a
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "4688422"
---
# <a name="format-er-function"></a>Función FORMAT de ER

[!include [banner](../includes/banner.md)]

La función `FORMAT` devuelve la cadena especificada como un valor de tipo *Cadena* tras aplicar formato sustituyendo cualquier instancia de **%N** por el argumento *N*-ésimo.

## <a name="syntax"></a>Sintaxis

```vb
FORMAT (string, argument 1[, argument 2, …, argument N])
```

## <a name="arguments"></a>Argumentos

`string`: *Cadena*

Hay que aplicar formato a una referencia a un origen de datos de tipo *Cadena*. Este argumento es obligatorio.

`argument 1`: *Cadena*

El primer argumento, que se utiliza para reemplazar instancias de **%1**. Este argumento es obligatorio.

`argument N`: *Cadena*

El *N*-ésimo argumento, que se utiliza para reemplazar instancias de **%2**, **%3**, etc. Estos argumentos adicionales son opcionales.

## <a name="return-values"></a>Valores de retorno

*Cadena*

El valor de texto resultante.

## <a name="usage-notes"></a>Notas de uso

Si no se proporciona un argumento para un parámetro, el parámetro se devuelve como **“%N”** en la cadena. Para valores del tipo *Real*, la conversión de cadena predetermina está limitada a dos posiciones decimales.

## <a name="example"></a>Ejemplo

En la siguiente ilustración, el origen de datos **PaymentModel** devuelve una lista de registros de cliente mediante el componente **Cliente**. Devuelve el valor de la fecha de procesamiento a través del campo **ProcessingDate**.

<a href="./media/picture-format-datasource.jpg"><img src="./media/picture-format-datasource.jpg" alt="PaymentModel data source" class="alignnone wp-image-290751 size-full" width="293" height="143" /></a>

En el formato de informes electrónicos (ER) diseñado para generar un archivo electrónico para los clientes seleccionados, **PaymentModel** se selecciona como origen de datos y controla el flujo de proceso. Si un cliente está detenido para la fecha de procesamiento del informe, se genera una excepción para notificárselo al usuario. La fórmula que está diseñada para este tipo de control de proceso puede usar los recursos siguientes:

- Etiqueta SYS70894, que tiene el siguiente texto:

    - **Para el idioma EN-US:** “No hay nada que imprimir”
    - **Para el idioma DE:** "Nichts zu drucken"

- Etiqueta SYS18389, que tiene el siguiente texto:

    - **Para el idioma EN-US:** "Customer %1 is stopped for %2."
    - **Para el idioma DE:** "Debitor '%1' wird für %2 gesperrt."

Esta es la expresión que se puede diseñar.

```vb
FORMAT (CONCATENATE (@"SYS70894", ". ", @"SYS18389"), model.Customer.Name, DATETIMEFORMAT (model.ProcessingDate, "d"))
```

Si se procesa un informe para el cliente **Litware Retail** el 17 de diciembre de 2015, en la cultura **EN-US** y el idioma **EN-US**, esta fórmula devuelve el siguiente texto, que puede presentarse al usuario como mensaje de excepción:

*Nothing to print. Customer Litware Retail is stopped for 12/17/2015.*

Si el mismo informe se procesa para el cliente **Litware Retail** el 17 de diciembre de 2015, en la cultura **DE** y el idioma **DE**, la fórmula devuelve el siguiente texto, que usa un formato de fecha diferente:

*Nichts zu drucken. Debitor 'Litware Retail' wird für 17.12.2015 gesperrt.*

>[!NOTE]
> La sintaxis siguiente se aplica en las fórmulas de ER para las etiquetas:
>
> - **Para las etiquetas de recursos de la aplicación de Microsoft Dynamics 365 Finance:** **\@X**, donde **X** es el id. de etiqueta en el árbol de objetos de aplicación (AOT)
> - **Para las etiquetas que se encuentran en las configuraciones de ER:** **@"GER_LABEL:X**, donde **X** es el id. de etiqueta de la configuración de ER

## <a name="additional-resources"></a>Recursos adicionales

[Funciones de texto](er-functions-category-text.md)
