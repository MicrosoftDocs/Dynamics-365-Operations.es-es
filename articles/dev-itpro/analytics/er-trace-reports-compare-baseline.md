---
title: "Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base"
description: "En este tema proporciona información sobre cómo puede comparar los resultados de los informes de ER generados con los valores del informe de línea base."
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
ms.openlocfilehash: 1a598d0bd053c60c3f8df6b05ecb7ff15addfaa3
ms.contentlocale: es-es
ms.lasthandoff: 08/09/2018

---

# <a name="trace-generated-report-results-and-compare-them-with-baseline-values"></a>Realizar un seguimiento de los resultados de informe generados y compararlos con valores de línea base

[!include[banner](../includes/banner.md)]

Puede realizar un seguimiento de los resultados de los formatos de ER que generan documentos electrónicos salientes. Cuando está activada la generación de seguimiento (parámetro del usuario de ER **Ejecutar en modo de depuración**), se genera un nuevo registro de ejecución del formato de ER cada vez que se ejecuta un informe de ER. Los siguientes detalles se almacenan en cada seguimiento que se genera:

- Todas las advertencias que se generaron mediante reglas de validación
- Todos los errores que se generaron mediante reglas de validación
- Todos los archivos generados que se almacenan como archivos adjuntos del registro de seguimiento

Puede almacenar los archivos de aplicación individuales de línea base para cualquier formato de ER. Los archivos se consideran archivos de línea base cuando describen los resultados esperados de los informes que se ejecutan. Si un archivo de línea base está disponible para un formato de ER que se ejecutó mientras estaba activada la generación de seguimiento, el seguimiento almacena, además de los detalles que se mencionaron anteriormente, el resultado de la comparación del documento electrónico generado al archivo de línea base. En un clic, también puede obtener el documento electrónico generado y su archivo de línea base en un único archivo zip. A continuación, puede hacer comparación detallada mediante una herramienta externa como Windiff.

Puede evaluar el seguimiento para analizar si los documentos electrónicos que se crean generan incluyen el contenido esperado. Puede hacer esta evaluación en un entorno de prueba de aceptación del usuario (UAT) cuando ha cambiado la base de código (por ejemplo, cuando migró a una nueva instancia de la aplicación, paquetes de revisión instalados o modificaciones de código implementadas). De este modo, puede asegurarse de que la evaluación no afecta a la ejecución de informes de ER que se usan. Para muchos informes de ER, la evaluación se puede realizar en modo desatendido.

Para obtener más información acerca de esta función, reproduzca las guías de tareas **ER Generar informes y comparar los resultados (Parte 1)** y **ER Generar informes y comparar los resultados (Parte 2)**, que forman parte del proceso empresarial **7.5.4.3 Probar soluciones y servicios de TI (10679)** y se puede descargar del [Centro de descarga de Microsoft](https://go.microsoft.com/fwlink/?linkid=874684). Estas guías de tareas le guían por el proceso de configuración del marco de ER para utilizar los archivos de línea base para evaluar documentos electrónicos generados.

