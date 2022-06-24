---
title: Dividir los archivos XML generados según su tamaño y la cantidad de contenido
description: En este artículo se proporciona información acerca de cómo dividir archivos generados según su tamaño y la cantidad de elementos del contenido.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.openlocfilehash: 041bec441d2517a7b646c4a18a45863c541b2b7a
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8873012"
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

- [Configuración del modelo de ER - XmlFilesSplittingModel.xml](https://download.microsoft.com/download/e/a/f/eaffe96a-22ec-4a32-898a-f4328c91c387/XmlFilesSplittingModel.xml)
- [Configuración del formato de ER - XmlFilesSplittingFormat.xml](https://download.microsoft.com/download/e/9/c/e9c5849b-8254-4cdf-bb00-4c2ebc72ddec/XmlFilesSplittingFormat.xml)

## <a name="additional-resources"></a>Recursos adicionales
[Destinos de informes electrónicos (ER)](electronic-reporting-destinations.md)

[Diseñador de fórmulas en los informes electrónicos (ER)](general-electronic-reporting-formula-designer.md)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
