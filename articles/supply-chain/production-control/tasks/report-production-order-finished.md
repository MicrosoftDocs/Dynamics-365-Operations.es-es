---
title: Notificar un pedido de producción como terminado
description: Este procedimiento muestra cómo notificar un pedido de producción como terminado.
author: johanhoffmann
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmReportFinished, ProdJournalTransProd
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 97e67ff51e4bc4533aeb2485c34cd5ec8a882bb6
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1558443"
---
# <a name="report-a-production-order-as-finished"></a>Notificar un pedido de producción como terminado

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo notificar un pedido de producción como terminado. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este es el sexto procedimiento de siete que explica el ciclo de vida del pedido de producción.


## <a name="report-a-production-order-as-finished"></a>Notificar un pedido de producción como terminado
1. Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.
    * Seleccione un pedido de producción con estado Iniciado.  
2. En el panel de acciones, haga clic en Pedido de producción.
3. Haga clic en Notificar como terminado.
    * En esta página, puede confirmar la cantidad de producto terminado que se va a notificar como terminado.  
4. Haga clic en la pestaña General.
5. Defina la Cantidad sin errores en "18".
6. Defina la Cantidad con errores en "2".
7. En el campo Causa del error, seleccione "Material".
8. Active o desactive la casilla Cierre final.
9. Active o desactive la casilla Aceptar error.
10. Haga clic en Aceptar

## <a name="verify-the-report-as-finished-journal"></a>Comprobar Notificar como diario terminado
1. En el panel de acciones, haga clic en Ver.
2. Haga clic en Notificado como terminado.
3. En la lista, marque la fila seleccionada.
4. En la lista, haga clic en el vínculo de la fila seleccionada.
    * Se registra Notificar como diario terminado. Si desea realizar ajustes en el diario, puede crear manualmente un nuevo diario en el que puede realizar cambios.  

