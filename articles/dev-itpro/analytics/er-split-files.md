---
title: Dividir los archivos XML generados según su tamaño y la cantidad de contenido
description: En este tema se proporciona información acerca de cómo dividir archivos generados según su tamaño y la cantidad de elementos del contenido.
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 8c3899d5c6602b3afe13b447b40f0b4dcc701448
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "347109"
---
# <a name="split-generated-xml-files-based-on-file-size-and-content-quantity"></a>Dividir los archivos XML generados según su tamaño y la cantidad de contenido

[!include[banner](../includes/banner.md)]

Puede diseñar formatos de informes electrónicos (ER) para generar documentos salientes en formato XML. A veces, se pueden aceptar esos documentos solo si cumplen criterios específicos, como un tamaño máximo de archivo o un número máximo de algunos nodos XML. Puede diseñar formatos de ER para generar documentos electrónicos que satisfacen los requisitos que especifican los destinatarios de esos documentos.

- Para el elemento de formato ARCHIVO, puede definir un límite en el tamaño de archivo como una expresión de ER. Si se supera el límite definido cuando se genera un informe de ER, el ER termina creando el archivo actual y luego se mueve para crear el siguiente archivo.
- Para cualquier formato ELEMENTO XML, puede definir un límite en el número de elementos como una expresión de ER. Si el número de nodos XML en el archivo que se genera supera el límite definido cuando se ejecuta un informe de ER, el ER termina creando el archivo actual y luego se mueve para crear el siguiente archivo.
- Para cualquier elemento de formato SECUENCIA XML, puede definir un límite en el número de elementos secundarios como una expresión de ER. Si el número de nodos XML anidados del elemento de formato en el archivo generado supera el límite definido cuando se ejecuta un informe de ER, el ER termina creando el archivo actual y luego se mueve para crear el siguiente archivo.
- Puede marcar cualquier elemento de formato ELEMENTO XML como irrompible. De esta manera, puede mantener los elementos anidados de los nodos XML que se generan bajo el elemento de formato en un único archivo generado.

Además de utilizar los elementos de formato ELEMENTO XML y SECUENCIA XML para agregar nodos XML al archivo generado, puede usar el elemento de formato XML SIN FORMATO. Sin embargo, los nodos que agregue mediante el elemento de formato XML SIN FORMATO no se tienen en cuenta cuando el número de nodos se calcula para evaluar los límites en el número de elementos.

Si configuró los destinos de archivo para un elemento de formato ARCHIVO que se ha configurado para dividir la salida generada siempre que se superen los límites específicos, cada pieza de salida generada se envía al destino de archivo configurado como un archivo individual. Para nombra de forma exclusiva los archivos que se han creado dividiendo la salida, debe configurar una expresión de ER para el elemento de formato ARCHIVO. Si incluye un origen de datos de ER del tipo SECUENCIA NUMÉRICA, la secuencia numérica se verá incrementada para cada pieza de la salida dividida.

Para obtener más información acerca de esta función, reproduzca la guía de tareas **ER Dividir archivos XML según su tamaño y la cantidad de elementos del contenido**, que forma parte del proceso empresarial **7.5.4.3 Adquirir o desarrollar componentes de soluciones y servicios de TI (10677)** y puede descargarse del [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/?linkid=874684). Esta guía de tareas le guía por el proceso de configuración de un formato de ER para dividir archivos generados según los límites en el tamaño de los archivos y la cantidad de elementos del contenido. Para completar la guía de tareas, debe descargar los siguientes archivos:

- [Configuración del modelo de ER - XmlFilesSplittingModel.xml](https://go.microsoft.com/fwlink/?linkid=874111)
- [Configuración del formato de ER - XmlFilesSplittingFormat.xml](https://go.microsoft.com/fwlink/?linkid=874111)

## <a name="additional-resources"></a>Recursos adicionales
[Destinos de informes electrónicos](electronic-reporting-destinations.md)

[Diseñador de fórmulas en los informes electrónicos](general-electronic-reporting-formula-designer.md)
