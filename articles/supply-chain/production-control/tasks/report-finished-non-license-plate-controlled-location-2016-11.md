---
title: Notificar como terminado a una ubicación no controlada mediante matrículas de entidad de almacén (solicitud, mayo de 2016)
description: Esta guía de tareas muestra un ejemplo de notificación como finalizado en una ubicación que no está controlada mediante matrículas de entidad de almacén.
author: ChristianRytt
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WrkCtrResourceGroup, ProdTableListPage, ProdTableCreate, InventItemIdLookupPurchase, ProdParmCostEstimation, ProdParmStartUp, ProdParmReportFinished, WHSWorkTable
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: crytt
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4da6868a2184a76c435efe824f4670504e1134e7
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1562938"
---
# <a name="report-as-finished-to-a-non-license-plate-controlled-location--application-may-2016"></a>Notificar como terminado a una ubicación no controlada mediante matrículas de entidad de almacén (solicitud, mayo de 2016)

[!include [task guide banner](../../includes/task-guide-banner.md)]

Esta guía de tareas muestra un ejemplo de notificación como finalizado en una ubicación que no está controlada mediante matrículas de entidad de almacén. Una directiva aplicable de trabajo es el requisito previo para esta tarea. Una guía de tareas anterior mostraba la configuración de la directiva de trabajo. Esta guía de tareas requiere la aplicación Dynamics AX 7.0.1 o versiones posteriores.




## <a name="set-up-an-output-location"></a>Configurar una ubicación de salida
1. Vaya a Administración de la organización > Recursos > Grupos de recursos..
2. En la lista, seleccione el grupo de recursos "5102".
3. Haga clic en Editar.
4. En el campo Almacén de salida, especifique "51".
5. En el campo Ubicación de salida, especifique "001".
    * La ubicación 001 no es una ubicación controlada mediante matrículas de entidad de almacén. Puede configurar una ubicación de salida que no sea de matrículas de entidad de almacén si existe una directiva aplicable de trabajo para la ubicación.  

## <a name="create-a-production-order-and-report-it-as-finished"></a>Crear un pedido de producción y notificarlo como terminado
1. Cierre la página.
2. Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.
3. Haga clic en Nuevo pedido de producción.
4. En el campo Número de artículo, especifique "L0101".
5. Haga clic en Crear.
6. En el panel de acciones, haga clic en Pedido de producción.
7. Haga clic en Estimación.
8. Haga clic en Aceptar
9. Haga clic en Inicio.
10. Haga clic en la ficha General.
11. En el campo Consumo automático de L. MAT, seleccione "Nunca".
12. Haga clic en Aceptar
13. Haga clic en Notificar como terminado.
14. Haga clic en la ficha General.
15. Seleccione Sí en el campo Aceptar error.
16. Haga clic en Aceptar
17. En el panel de acciones, haga clic en Almacén.
18. Haga clic en Detalles del trabajo.
    * Cuando el pedido de producción se ha notificado como finalizado, no se ha generado ningún trabajo para ubicación. Esto ocurre porque se define una directiva de trabajo que impide que el trabajo se genere cuando el producto L0101 se notifique como finalizado para la ubicación 001.  

