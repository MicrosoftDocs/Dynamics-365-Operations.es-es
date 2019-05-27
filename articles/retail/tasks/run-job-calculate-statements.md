---
title: Configurar y ejecutar trabajo para calcular extractos
description: Este procedimiento le muestra la configuración y ejecución de trabajos por lotes periódicos para crear y calcular extractos para una tienda seleccionada o un grupo de tiendas.
author: josaw1
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailChannelOperationsWorkspace, RetailOperatingUnitPicker, SysRecurrence
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f52603672e95d0ae4973844851c4ed260484e5f0
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1550171"
---
# <a name="configure-and-run-job-to-calculate-statements"></a>Configurar y ejecutar trabajo para calcular extractos

[!include[task guide banner](../includes/task-guide-banner.md)]

Este procedimiento le muestra la configuración y ejecución de trabajos por lotes periódicos para crear y calcular extractos para una tienda seleccionada o un grupo de tiendas. Este procedimiento usa la empresa USRT en los datos de demostración.

1. Vaya a Todos los espacios de trabajo > Operaciones financieras de tienda.
2. Haga clic en Calcular extractos.
    * Seleccione una tienda concreta o un nodo si desea crear el trabajo por lotes para un grupo de tiendas.  
    * Haga clic en la flecha para agregar su selección.  
3. Haga clic en la ficha Ejecutar en segundo plano.
4. Seleccione "Sí" en Procesamiento por lotes.
5. Haga clic en Periodicidad.
6. En el campo Fecha inicial, especifique una fecha.
7. Especifique una hora en el campo Hora inicial.
8. Seleccione la opción No hay fecha final.
9. En el campo PatternUnit, especifique "Days".
10. En el campo Por, especifique un número.
11. Haga clic en Aceptar
12. Haga clic en Aceptar

