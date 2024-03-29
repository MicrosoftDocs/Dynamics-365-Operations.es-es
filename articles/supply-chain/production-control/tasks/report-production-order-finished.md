---
title: Notificar un pedido de producción como terminado
description: Este procedimiento muestra cómo notificar un pedido de producción como terminado.
author: johanhoffmann
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmReportFinished, ProdJournalTransProd, ProdSetupReportFinished
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: aa27691942b27886e85c52b7b3a736a62db7b7bd
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/29/2021
ms.locfileid: "7580609"
---
# <a name="report-a-production-order-as-finished"></a>Notificar un pedido de producción como terminado

[!include [banner](../../includes/banner.md)]

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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]