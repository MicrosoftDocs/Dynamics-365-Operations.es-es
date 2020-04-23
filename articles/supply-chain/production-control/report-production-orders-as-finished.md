---
title: Notificar pedidos de producción como terminados
description: Notificar como terminado es una etapa de producción. En esta etapa se notifica un producto terminado y se mueve del pedido de producción al inventario.
author: johanhoffmann
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProdJournalTransJob, ProdJournalTransProd, ProdJournalTransRoute, ProdParmReportFinished, ProdRouteOprOverview
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 27061
ms.assetid: 1c2dfc54-a293-49f2-9b96-5a912ac5762c
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 87e5d4f46a2ae34a2bc114a92ed4e037875dde43
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3211155"
---
# <a name="report-production-orders-as-finished"></a>Notificar pedidos de producción como terminados

[!include [banner](../includes/banner.md)]

Notificar como terminado es una etapa de producción. En esta etapa se notifica un producto terminado y se mueve del pedido de producción al inventario.

Cuando una cantidad de mercancías terminadas se notifica como terminada en un pedido de producción, esta se actualiza como disponible en el inventario. Las cantidades parciales de la cantidad de pedido planificado original se pueden notificar originalmente como terminadas. Al notificar cantidades como terminadas, también es posible notificar cantidades con error con su correspondiente motivo de error asociado. Cuando el pedido de producción llega a la etapa Notificado como terminado, indica que no se va a notificar más cantidad en el pedido de producción.
Las siguientes características se asocian también con el proceso **Notificar como terminado**:
-   Es posible configurar el consumo de materias primas y el tiempo proporcionales a la cantidad notificada (contabilización previa).
-   Se puede generar trabajo de guardado en ubicación para artículos habilitados para los procesos de almacén.
-   El valor de coste estándar o planificado de los productos terminados se puede configurar para notificarse en cuentas contables.
-   Se pueden crear pedidos de calidad para la cantidad notificada según la configuración de una asociación de calidad.

La cantidad se notifica a la ubicación de salida. El trabajo de almacén se genera a continuación para mover la cantidad desde la ubicación de salida a su destino final según defina la directiva de ubicación para el trabajo de guardado en ubicación.

-   Se puede crear un pedido de calidad cuando se notifica un pedido de producción como finalizado si se ha configurado una asociación de calidad.

## <a name="set-a-production-order-to-reporting-as-finished"></a>Definición de pedidos de producción para notificarse como terminados
Puede establecer un pedido de producción en **Notificar como terminado** mediante la función de actualización de pedido de producción estándar, mediante los diarios de tarjeta de trabajo y de ruta o mediante el diario **Notificar como terminado**. También puede actualizar la etapa a **Notificar como terminado** a través de la terminal de la tarjeta de trabajo y las páginas del dispositivo de tarjeta de trabajo al notificar sobre el último trabajo del pedido de producción. Finalmente, puede habilitar la opción **Notificar como terminado** como un proceso para la solución del dispositivo de almacén de mano.  



