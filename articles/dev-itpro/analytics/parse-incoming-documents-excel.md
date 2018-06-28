---
title: Analizar documentos de entrada en Microsoft Excel
description: "Este tema proporciona información sobre el diseño de los formatos de informes electrónicos (ER) que analizan el contenido de los archivos de Microsoft Excel de entrada."
author: NickSelin
manager: AnnBe
ms.date: 05/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 220314
ms.assetid: 2685df16-5ec8-4fd7-9495-c0f653e82567
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2018-04-01
ms.dyn365.ops.version: Release 8.0
ms.translationtype: HT
ms.sourcegitcommit: 2fc887668171175d436b9eb281a35c1c9d089591
ms.openlocfilehash: 001e287590b9f43ed38de803bcace3a25a6f6637
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2018

---

# <a name="parse-incoming-microsoft-excel-files"></a>Analizar archivos de entrada de Microsoft Excel

[!include[banner](../includes/banner.md)]

Puede diseñar los formatos de informes electrónicos de (ER) para analizar archivos de Microsoft Excel de entrada que representan datos en los libros de Microsoft Excel (archivos en formato de XLSX). Puede usar el contenido de estos archivos para actualizar datos de la aplicación. Esto resulta útil si:

-   Diseña un modelo y un formato nuevos y los desea probar en el tiempo de ejecución. En este caso, Excel simulará los datos de la aplicación reales.
-   Gestiona los datos más allá de la aplicación en Excel y desea importar estos datos para mostrar un informe específico.

Para obtener más información acerca de esta función, reproduzca las guías de tareas **Datos de importación de ER de un archivo de Microsoft Excel (Parte 1: Formato de diseño)** y **Datos de importación de ER de un archivo de Microsoft Excel (Parte 2: Datos de la importación)** (partes del proceso empresarial 7.5.4.3 Acquire/servicio Develop IT/componentes de la solución (10677)). Estas guías de la tarea le enseñan cómo el archivo de Excel de entrada se puede analizar mediante el formato de ER para importar la información de documentos de entrada y actualizar datos de la aplicación. Puede descargar los archivos de la guía de tareas del [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/?linkid=874684).

Descargue los siguientes archivos para completar la guía de tareas mencionadas arriba.

| Descripción del contenido                        | Archivo                                                                       |
---------------------------------------------|----------------------------------------------------------------------------|
| Archivo de entrada en el formato .XLSX - plantilla   | [1099import-template.xlsx](https://go.microsoft.com/fwlink/?linkid=862266)  |
| Archivo de entrada en el formato .XLSX - datos de muestra| [1099import-data.xlsx](https://go.microsoft.com/fwlink/?linkid=862266)     |

Si aún no ha reproducido la guía de tareas siguiente, [ER Crear las configuraciones necesarias para importar datos desde un archivo externo](./tasks/er-required-configurations-import-data.md) en la aplicación actual Dynamics 365 for Finance and Operation, descargue el siguiente archivo.

| Descripción del contenido                        | Archivo                                                                       |
---------------------------------------------|----------------------------------------------------------------------------|
| Configuración del modelo de ER                     | [1099model.xml](https://go.microsoft.com/fwlink/?linkid=862266)            |


