--- 
title: "Crear una programación para un sitio"
description: "Este procedimiento muestra cómo programar los pedidos de producción que no se han iniciado aún para un sitio."
author: ShylaThompson
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 775428bf84a752c03c492e764fa9ed576ab64fb8
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-schedule-for-a-site"></a>Crear una programación para un sitio

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo programar los pedidos de producción que no se han iniciado aún para un sitio.  Se usa la empresa de datos de demostración USMF para completar este procedimiento.


## <a name="identify-production-orders-that-are-not-started"></a>Identificar pedidos de producción que no se han iniciado
1. Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.
2. Use el filtro rápido para buscar registros. Por ejemplo, aplique un filtro en el campo Sitio con un valor de "1".
    * 1 representa un sitio en USMF. Si no utiliza USMF, seleccione un sitio de su propia empresa.  
3. Abra el filtro de columna Estado.
4. Aplique un filtro al campo "Estado", con el valor de "Programado", mediante el operador de filtro "es exactamente".

## <a name="create-a-schedule"></a>Crear una programación
1. En la lista, active o desactive todas las filas.
2. En el panel de acciones, haga clic en Programar.
3. Haga clic en Programar trabajos.
4. En el campo Dirección de programación, seleccione “Programar hacia atrás a partir de la fecha de entrega”.
5. Seleccione No en el campo Capacidad limitada.
6. Seleccione No en el campo Material limitado.
7. Haga clic en Aceptar
    * Esto puede tardar unos minutos.  

## <a name="view-the-result-of-scheduled-production-orders"></a>Ver el resultado de los pedidos de producción programados
1. En la lista, marque la fila seleccionada.
    * Puede marcar cualquier fila.  
2. En el panel de acciones, haga clic en Pedido de producción.
3. Haga clic en Todos los trabajos.
    * En esta página, puede ver la lista de trabajos. En la ficha Programación, puede ver la Fecha inicial y la Fecha final de un trabajo.  
4. Haga clic en Materiales.
    * En esta página, puede ver el consumo de materiales estimado para las operaciones en el pedido de producción y el inventario disponible actual.  


