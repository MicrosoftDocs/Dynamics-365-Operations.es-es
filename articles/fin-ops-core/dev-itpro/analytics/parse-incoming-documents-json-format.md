---
title: Analizar documentos de entrada en formato JSON
description: En este tema se explica cómo configurar formatos de informes electrónicos (ER) para analizar documentos de entrada en formato JavaScript Object Notation (JSON).
author: kfend
ms.date: 05/20/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.1
ms.openlocfilehash: ba30b06cc0c4af230113d532a932594278e13b29a87e6252849483c9dfcbc198
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6713927"
---
# <a name="parse-incoming-documents-in-json-format"></a>Analizar documentos de entrada en formato JSON

[!include[banner](../includes/banner.md)]

Puede diseñar formatos de informes electrónicos (ER) para analizar documentos electrónicos de entrada que representan datos en un formato de texto que se basa en JavaScript (es decir, archivos en formato JavaScript Object Notation \[JSON\]).

Para obtener más información acerca de esta característica, descargue los archivos en la siguiente tabla y, a continuación, reproduzca el ER Crear una configuración de formato para importar datos de una guía de tareas del archivo JSON externo. Esta guía de tareas muestra cómo se puede utilizar el formato de ER para analizar un archivo JSON de entrada para actualizar datos de la aplicación.

| Cargo                                  | Nombre de archivo |
|----------------------------------------|-----------|
| Configuración del formato de ER                | [Formato para importar trans_JSON.xml de proveedores](https://go.microsoft.com/fwlink/?linkid=874111) |
| Ejemplo de archivo de entrada en formato .csv | [1099entries_JSON.txt](https://go.microsoft.com/fwlink/?linkid=874111) |

## <a name="requirements"></a>Requisitos

Antes de completar el ER Crear una configuración de formato para importar datos de una guía de tareas del archivo JSON externo, debe cumplirse el siguiente requisito:

- Los elementos principales del archivo JSON solo pueden ser elementos de objeto.
- Los elementos anidados para un objeto deben ser elementos de propiedad para que se cree una estructura JSON válida.
- Las matrices JSON solo pueden ser elementos anidados de los elementos de propiedad de un objeto.
- Las matrices JSON solo pueden contener objetos JSON. No pueden contener valores de cadena/numéricos directos y matrices anidadas. Los elementos de estas matrices se analizarán en orden, tal como se especifican en el formato. Se considerará la configuración de multiplicidad en cada objeto JSON.

Además, debe completar la guía de tareas de [ER Crear las configuraciones requeridas para importar datos de un archivo externo](tasks/er-required-configurations-import-data.md) si no la ha completado todavía. Descargue el siguiente archivo para completar la guía de tareas.

| Cargo                  | Nombre de archivo |
|------------------------|-----------|
| Configuración del modelo de ER | [1099model.xml](https://go.microsoft.com/fwlink/?linkid=874111) |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]