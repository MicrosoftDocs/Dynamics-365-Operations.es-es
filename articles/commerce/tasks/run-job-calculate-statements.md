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
ms.search.region: Global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8366bfff16bac8ef8f7b15cb97417d474b52f59c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5232770"
---
# <a name="configure-and-run-job-to-calculate-statements"></a>Configurar y ejecutar trabajo para calcular extractos

[!include [banner](../includes/banner.md)]

Este procedimiento le muestra la configuración y ejecución de trabajos por lotes periódicos para crear y calcular extractos para una tienda seleccionada o un grupo de tiendas. Este procedimiento usa la empresa USRT en los datos de demostración.

1. Vaya a Todos los espacios de trabajo > Operaciones financieras de tiendas.
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



[!INCLUDE[footer-include](../../includes/footer-banner.md)]