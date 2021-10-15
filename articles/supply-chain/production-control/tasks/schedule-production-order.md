---
title: Programar un pedido de producción
description: Este procedimiento muestra cómo programar un pedido de producción.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdSchedule, ProdRouteJob, WrkCtrCapResSum, ProdRouteJobSched, ProductionOrderScheduleDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 43d183764def1b1bea7bbe140c25e0eec0b692b1
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580585"
---
# <a name="schedule-a-production-order"></a>Programar un pedido de producción

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]