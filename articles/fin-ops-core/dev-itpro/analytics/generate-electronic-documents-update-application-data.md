---
title: Generar documentos electrónicos y actualizar datos de aplicación utilizando ER
description: Puede diseñar los formatos de informes electrónicos (ER) que se pueden usar en la aplicación para generar documentos electrónicos salientes.
author: NickSelin
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro, Application user
ms.reviewer: kfend
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5f66a173c7d66f915a7802e42caf1a36f661eea1
ms.sourcegitcommit: ab3f5d0da6eb0177bbad720e73c58926d686f168
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/26/2021
ms.locfileid: "5944326"
---
# <a name="generate-electronic-documents-and-update-application-data-by-using-er"></a>Generar documentos electrónicos y actualizar datos de aplicaciones mediante ER

[!include [banner](../includes/banner.md)]

Puede diseñar los formatos de informes electrónicos (ER) que se pueden usar en la aplicación para generar documentos electrónicos salientes. También puede diseñar formatos de ER que analizan los documentos electrónicos entrantes y usan el contenido en esos documentos para actualizar los datos de la aplicación.

Con esta funcionalidad, un único formato de ER se puede usar para generar documentos electrónicos salientes y actualizar los datos de la aplicación. Esta función también se puede en las situaciones siguientes:

- Para evitar el uso repetido de datos de la aplicación en procesos posteriores puede marcar un dato de aplicación inmediatamente después que se usa para generar documentos electrónicos. Por ejemplo, puede marcar transacciones de pago como ya procesadas inmediatamente después de que se hayan incluido en un mensaje de pago generado.
- Para archivar los detalles del procesamiento de los documentos electrónicos que se han generado mediante la lógica de ER. Por ejemplo, una identificación única del mensaje de pago que se genera mediante la expresión de ER. La expresión se basa en la información especificada al cuadro de diálogo de ER cuando el formato de ER se ejecuta para generar documentos.

Para obtener más información acerca de esta función, reproduzca el conjunto de documentos Generar ER con las guías de tareas de actualización de los datos de la aplicación (parte del proceso empresarial 7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)), que describen los detalles de la generación de informes y el archivado de intrastat. Los archivos siguientes son necesarios para completar determinados pasos en estas guías de tareas. Descargue y guardar estos archivos en su equipo local.

- [Configuración del modelo de datos de ER: intrastat (modelo)](https://download.microsoft.com/download/9/c/e/9ceeacbe-c13e-422e-96f2-594c4a6b45b7/Intrastatmodel.xml)
- [Configuración de la asignación del modelo de ER: intrastat (asignación)](https://download.microsoft.com/download/2/1/d/21ddaaeb-64c5-4408-a35f-1ccb922d40a4/Intrastatmapping.xml)
- [Configuración del formato de ER: intrastat (formato)](https://download.microsoft.com/download/8/b/b/8bbb8891-e88d-4739-b92a-2d1d2fffcb79/Intrastatformat.xml)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
