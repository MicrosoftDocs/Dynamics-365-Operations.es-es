--- 
title: "Programar un pedido de producción"
description: "Este procedimiento muestra cómo programar un pedido de producción."
author: johanhoffmann
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob, WrkCtrCapResSum
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: dadf0e87eac8522f61bb094c146e37f46a21fc09
ms.openlocfilehash: 6cbbf509c9e60040e08ab7932fcb0e8eed5ddd22
ms.contentlocale: es-es
ms.lasthandoff: 02/06/2018

---
# <a name="schedule-a-production-order"></a>Programar un pedido de producción

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo programar un pedido de producción. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este es el tercer procedimiento de siete que explica el ciclo de vida del pedido de producción.


## <a name="schedule-a-production-order"></a>Programar un pedido de producción
1. Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.
    * Seleccione un pedido de producción con el Estimado.  
2. En el panel de acciones, haga clic en Programar.
3. Haga clic en Programar trabajos.
    * Los parámetros para programar se configuran en esta página. Puede configurar los parámetros para usuarios específicos o todos los usuarios.  
4. En el campo Dirección de programación, seleccione “Remitir a partir de hoy”.
5. En el campo Fecha de programación, especifique una fecha.
6. Active o desactive la casilla Capacidad limitada.
7. Active o desactive la casilla Material limitado.
8. Haga clic en Aceptar

## <a name="view-the-scheduling-results"></a>Ver los resultados de la programación
1. En el panel de acciones, haga clic en Pedido de producción.
2. Haga clic en Todos los trabajos.
    * Esta página muestra los trabajos programados que acaba de generar.  
3. Expanda o contraiga la sección Programación.
    * En la ficha desplegable Programación, puede ver la fecha y la hora programadas.  
4. Haga clic en Consultas.
5. Haga clic en Carga de capacidad.
    * La página Carga de capacidad muestra la capacidad reservada mediante la programación de trabajos, el número total de horas actualmente reservadas en el recurso y el número de horas que siguen disponibles para la programación de trabajos en el recurso.  
6. Cierre la página.
7. Cierre la página.


