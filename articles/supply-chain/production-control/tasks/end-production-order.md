---
title: "Finalizar un pedido de producción"
description: "Este procedimiento muestra cómo terminar un pedido de producción."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: dadf0e87eac8522f61bb094c146e37f46a21fc09
ms.openlocfilehash: 1cc586f804a072ca5499c73ecdf7d37778cbf067
ms.contentlocale: es-es
ms.lasthandoff: 02/06/2018

---
# <a name="end-a-production-order"></a>Finalizar un pedido de producción

[!include [task guide banner](../../includes/task-guide-banner.md)]

Este procedimiento muestra cómo terminar un pedido de producción. La empresa de datos de prueba utilizada para crear este procedimiento es USMF. Este es el último procedimiento de siete que explica el ciclo de vida del pedido de producción.


## <a name="end-a-production-order"></a>Finalizar un pedido de producción
1. Vaya a Control de producción > Pedidos de producción > Todos los pedidos de producción.
    * Seleccione un pedido de producción con estado Notificado como terminado.  
2. En el panel de acciones, haga clic en Pedido de producción.
3. Haga clic en Fin.
    * En esta página, puede confirmar que desea finalizar el pedido de producción.  
4. Haga clic en la pestaña General.
5. En el campo Fecha, escriba una fecha.
6. En el campo Método de valoración del residuo, seleccione Asignación.
    * Cuando selecciona el método Asignación, los costes de los materiales desechados se agregan a los productos terminados.  
7. Haga clic en Aceptar

## <a name="validate-calculation-results"></a>Validación de resultados de cálculo
1. En el panel de acciones, haga clic en Gestionar costes.
2. Haga clic en Ver comparación del coste.
    * Una vez finalizado el pedido de producción, puede comparar el precio de coste estimado con el precio de coste real para obtener una visión general de las desviaciones de producción.  

