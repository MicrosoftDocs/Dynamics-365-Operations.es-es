---
title: Publicar un pedido de producción
description: Este procedimiento muestra cómo liberar un pedido de producción.
author: johanhoffmann
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdTableListPage, ProdParmRelease, SrsReportViewerForm, ProdSetupRelease
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: beef850e7e58fb58db545c0be5990b52619070d3
ms.sourcegitcommit: 175f9394021322c685c5b37317c2f649c81a731a
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/21/2020
ms.locfileid: "3826584"
---
# <a name="release-a-production-order"></a>Publicar un pedido de producción

[!include [banner](../../includes/banner.md)]

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

