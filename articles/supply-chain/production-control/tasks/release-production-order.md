---
title: "Publicar un pedido de producción"
description: "Este procedimiento muestra cómo liberar un pedido de producción."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: dadf0e87eac8522f61bb094c146e37f46a21fc09
ms.openlocfilehash: 6e628d8564c093c5d75fffe268b2107262d508c3
ms.contentlocale: es-es
ms.lasthandoff: 02/06/2018

---
# <a name="release-a-production-order"></a>Publicar un pedido de producción

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo liberar un pedido de producción. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este es el cuarto procedimiento de siete que explican el ciclo de vida del pedido de producción.

1. Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.
    * En la cuadrícula, seleccione un pedido de producción con el estado Programado.  
2. En el panel de acciones, haga clic en Pedido de producción.
3. Haga clic en Liberar.
    * En esta página, puede confirmar la liberación del intervalo seleccionado de pedidos de producción. Haga clic en Seleccionar si desea agregar pedidos.  
    * El paso de liberación indica si el pedido de producción se libera en la planta de producción de modo que los operadores de planta pueden notificar el progreso en cuanto a los trabajos de producción. Se pueden emitir documentos de producción que contienen información pertinente sobre el proceso de los trabajos. El trabajo del almacén para seleccionar la materia prima se genera para los artículos que se configuran para el proceso de almacén.  
4. Haga clic en la pestaña General.
    * Seleccione qué informes de producción deben imprimirse. El informe de la tarjeta de trabajo imprime una página para cada trabajo programado y requiere que el pedido de producción se programe en el nivel de trabajo. El informe contiene información acerca del inicio y la hora final programadas, la cantidad de producción y qué recurso procesa el trabajo. El informe de trabajo de ruta recoge la misma información en la misma página, pero no imprime una página para cada trabajo. El informe de tarjeta de ruta solo muestra las operaciones pero no los trabajos. Por lo tanto, este informe no requiere programación de trabajos, pero se puede usar cuando los pedidos de producción se programan en el nivel de operación.  
5. Haga clic en la casilla Imprimir tarjeta de ruta.
6. Haga clic en Aceptar
7. Cierre la página.

