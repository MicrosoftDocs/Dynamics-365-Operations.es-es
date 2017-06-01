---
title: "Usar importación y exportación rápidas"
description: "El propósito de la importación y exportación rápidas es permitirle importar y exportar con menos pasos."
author: margoc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: dynamics-ax-2012
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 2012 R3 CU8
ms.custom: 89041
ms.assetid: 990d64e6-d436-4c79-9bb5-bf8c5c5a048f
ms.search.region: Global
ms.author: margoc
ms.search.validFrom: 
ms.dyn365.ops.version: AX 2012 R3 CU8
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 11cf53af2db453471175cec5de63d38f8b680c9b
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="run-the-test-data-transfer-tool-beta-for-dynamics-ax-ax-2012"></a>Ejecutar la herramienta de transferencia de datos de prueba (beta) para Dynamics AX (AX 2012)

[!include[banner](../../includes/banner.md)]


El propósito de la importación y exportación rápidas es permitirle importar y exportar con menos pasos.

Hemos agregado la característica Importación y exportación rápidas para permitir a los usuarios importar o exportar tareas sencillas que desean ejecutar con rapidez. Lo ideal es que esta característica se utilice en escenarios en los que un archivo se asigna automáticamente al sistema y el usuario no necesita pasar por la asignación avanzada ni crear trabajos repetidos de importación o exportación.

-   Esta característica es compatible con el trabajo tantos con entidades personalizadas como inmediatas.
-   Puede importar desde archivos y, si está utilizando un origen de datos ODBC, puede seleccionar una consulta para usarla para definir la importación.
-   Debe haber definido anteriormente formatos de datos de origen para AX o archivo, y saber dónde se encuentran.
-   No necesita crear un grupo de procesamiento para usar importación y exportación rápidas, el sistema creará uno automáticamente al ejecutar el trabajo de importación o exportación. También puede elegir conservar el historial de los datos importados por la importación o exportación rápidas.

  Tenga en cuenta que la importación y exportación rápidas supone que está familiarizado con los conceptos de DIXF.




