---
title: Configurar y ejecutar trabajo para registrar extractos
description: Este procedimiento le muestra la configuración y ejecución de un trabajo por lotes periódico para registrar extractos para una tienda seleccionada o un grupo de tiendas.
author: josaw1
manager: AnnBe
ms.date: 07/29/2019
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
ms.openlocfilehash: f89203850b302b769b22920fa5c42d2b0b877684
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/18/2020
ms.locfileid: "3141186"
---
# <a name="configure-and-run-job-to-post-statements"></a>Configurar y ejecutar trabajo para registrar extractos

[!include [banner](../includes/banner.md)]

Este procedimiento le muestra la configuración y ejecución de un trabajo por lotes periódico para registrar extractos para una tienda seleccionada o un grupo de tiendas. Este procedimiento usa la empresa USRT en los datos de demostración.

1. Vaya a Todos los espacios de trabajo > .. > Operaciones financieras de tiendas.
2. Haga clic en Registrar extractos por lotes.
    * Seleccione una jerarquía organizativa y en el árbol de nodos de la organización, seleccione un nodo o una tienda individual. Seleccione un nodo si desea crear el trabajo por lotes para un grupo de tiendas.  
    * Haga clic en la flecha para agregar su selección.  
3. Haga clic en la pestaña Ejecutar en segundo plano. ![Ejecutar en segundo planoEjecutar en segundo plano](../dev-itpro/media/runbackground.png "Ejecutar en segundo plano") 
4. Active o desactive la casilla Procesamiento por lotes.
![Procesamiento por lotes](../dev-itpro/media/batchprocessing.png "Procesamiento por lotes y periodicidad") 
5. Haga clic en Periodicidad.
6. En el campo Fecha inicial, especifique una fecha.
7. Especifique una hora en el campo Hora inicial.
    * Seleccione si desea finalizar la periodicidad después de un número específico de ejecuciones, en una fecha concreta, o nunca. A continuación, elija las diversas opciones para definir la frecuencia con la que desea ejecutar el trabajo.  
8. Haga clic en Aceptar.
9. Haga clic en Aceptar.

