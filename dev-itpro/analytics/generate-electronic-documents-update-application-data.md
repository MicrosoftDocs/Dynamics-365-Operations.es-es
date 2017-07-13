---
title: "Generar documentos electrónicos y actualizar los datos de las aplicaciones mediante la herramienta de informes electrónicos"
description: "Puede diseñar los formatos de informes electrónicos (ER) que se pueden usar en la aplicación Finance and Operations para generar documentos electrónicos salientes. También puede diseñar formatos de ER que analizan los documentos electrónicos entrantes y usan el contenido en esos documentos para actualizar los datos de la aplicación."
author: kfend
manager: AnnBe
ms.date: 05/11/2017
ms.topic: article
ms.prod: 
ms.service: Lifecycle Services
ms.technology: 
ms.search.form: ERSolutionTable, ERVendorTable, ERWorkspace
audience: Developer, IT Pro
ms.reviewer: annbe
ms.search.scope: AX 7.2, Operations
ms.custom: 27621
ms.assetid: 018a11ae-854c-4f36-9358-8c39baca882d
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d37d20b26d8ae755a6c5a688afd1ad0541d1f693
ms.openlocfilehash: 7e4e0acb374fe091c0e099355204116345c62997
ms.contentlocale: es-es
ms.lasthandoff: 06/13/2017

---


Puede diseñar los formatos de informes electrónicos (ER) que se pueden usar en la aplicación Finance and Operations para generar documentos electrónicos salientes. También puede diseñar formatos de ER que analizan los documentos electrónicos entrantes y usan el contenido en esos documentos para actualizar los datos de la aplicación. 

Con esta funcionalidad, un único formato de ER se puede usar para generar documentos electrónicos salientes y actualizar los datos de la aplicación. Esta función también se puede en las situaciones siguientes:

- Para evitar el uso repetido de datos de la aplicación en procesos posteriores puede marcar un dato de aplicación inmediatamente después que se usa para generar documentos electrónicos. Por ejemplo, puede marcar transacciones de pago como ya procesadas inmediatamente después de que se hayan incluido en un mensaje de pago generado.
- Para archivar los detalles del procesamiento de los documentos electrónicos que se han generado mediante la lógica de ER. Por ejemplo, una identificación única del mensaje de pago que se genera mediante la expresión de ER. La expresión se basa en la información especificada al cuadro de diálogo de ER cuando el formato de ER se ejecuta para generar documentos.

Para obtener más información acerca de esta función, reproduzca el conjunto de documentos Generar ER con las guías de tareas de actualización de los datos de la aplicación (parte del proceso empresarial 7.5.4.3 Adquirir/Desarrollar componentes de solución/servicios de la TI (10677)), que describen los detalles de la generación de informes y el archivado de intrastat. Los archivos siguientes son necesarios para completar determinados pasos en estas guías de tareas. Descargue y guardar estos archivos en su equipo local.

- [Configuración del modelo de datos de ER: intrastat (modelo)](https://go.microsoft.com/fwlink/?linkid=849038)
- [Configuración de la asignación del modelo de ER: intrastat (asignación)](https://go.microsoft.com/fwlink/?linkid=849038)
- [Configuración del formato de ER: intrastat (formato)](https://go.microsoft.com/fwlink/?linkid=849038)

