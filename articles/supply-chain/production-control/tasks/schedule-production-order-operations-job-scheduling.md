--- 
title: "Programar un pedido de producción con programación de operaciones y trabajo"
description: "Este procedimiento se centra en la programación de un pedido de producción con programación de operaciones y programación de trabajos."
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdSchedule, ProdTable, ProdRouteJob
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: d4aac437876862e9f776264fc81f246c820bdf45
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---
# <a name="schedule-a-production-order-with-operations-and-job-scheduling"></a>Programar un pedido de producción con programación de operaciones y trabajo

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento se centra en la programación de un pedido de producción con programación de operaciones y programación de trabajos. No se crea ningún trabajo con la programación de tareas mientras que los trabajos se crean con programación de operaciones. La empresa de datos de prueba utilizada para crear esta tarea es USMF. Este procedimiento está pensado para el director de producción, el planificador de producción o el supervisor de planta que trabaja en un entorno de fabricación discreto.


## <a name="create-a-production-order"></a>Crear un pedido de producción
1. Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.
2. Haga clic en Nuevo pedido de producción.
3. En el campo Número de artículo, especifique o seleccione un valor.
    * Seleccione el número de artículo D0001.  
4. Haga clic en Crear.

## <a name="schedule-operations-for-the-production-order"></a>Programe operaciones para el pedido de producción
1. En la lista, marque la fila seleccionada.
    * Seleccione el pedido de producción que acaba de crear. Debe estar en la parte superior de la lista.      
2. En el panel de acciones, haga clic en Programar.
3. Haga clic en Programar operaciones.
4. En el campo Dirección de programación, seleccione “A partir de la fecha de programación”.
5. En el campo Fecha de programación, especifique una fecha.
    * Seleccione una fecha futura, por ejemplo, hoy más una semana. Con la dirección de programación seleccionada, el pedido de producción se programará hacia delante a partir de esta fecha.  
6. Haga clic en Aceptar
7. En la lista, marque la fila seleccionada.
    * Tenga en cuenta que el estado cambia a Programado.  
8. En la lista, haga clic en el vínculo de la fila seleccionada.
9. Haga clic en Todos los trabajos.
    * Tenga en cuenta que ningún trabajo se crea con la programación de operaciones.  
10. Cierre la página.

## <a name="schedule-jobs-for-the-production-order"></a>Programe tareas para el pedido de producción
1. En el panel de acciones, haga clic en Programar.
2. Haga clic en Programar trabajos.
3. En el campo Dirección de programación, seleccione “A partir de la fecha de programación”.
4. En el campo Fecha de programación, especifique una fecha.
    * Seleccione una fecha en el futuro, por ejemplo, hoy más una semana. Con la dirección de programación seleccionada, el pedido de producción se programará hacia delante a partir de esta fecha.  
5. Haga clic en Aceptar
6. En el panel de acciones, haga clic en Pedido de producción.
7. Haga clic en Todos los trabajos.
    * Tenga en cuenta que basándose en la ruta activa, se crean 5 trabajos con la programación de trabajos.  


