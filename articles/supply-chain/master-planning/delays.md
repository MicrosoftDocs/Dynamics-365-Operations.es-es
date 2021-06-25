---
title: Retrasos
description: Este tema proporciona información acerca de fechas retrasadas en la planificación maestra. Una fecha retrasada es una fecha de vencimiento realista que una transacción recibe si la fecha de cumplimiento más temprana que la planificación maestra calcula es posterior a la fecha solicitada.
author: roxanadiaconu
ms.date: 03/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a8e863ae63466f68e763b133da9f0e9488c6cfa6
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "6189355"
---
# <a name="delays"></a>Retrasos

[!include [banner](../includes/banner.md)]

Este tema proporciona información acerca de fechas retrasadas en la planificación maestra. Una fecha retrasada es una fecha de vencimiento realista que una transacción recibe si la fecha de cumplimiento más temprana que la planificación maestra calcula es posterior a la fecha solicitada.

La planificación maestra puede calcular la fecha más temprana de cumplimiento para una transacción según los plazos, la disponibilidad de material, la disponibilidad de capacidad y los diferentes parámetros de planificación. 

Si la planificación maestra calcula una fecha de pedido anterior a la fecha en curso, el pedido no se puede satisfacer a tiempo. Por tanto, se retrasa el pedido. En este caso, la planificación maestra adelanta la planificación del pedido a partir de la fecha en uso e incluye plazos. Estos plazos empiezan con cualquier artículo componente de nivel inferior. El pedido recibe a continuación una fecha retrasada. La fecha retrasada es una fecha de vencimiento real en función de los datos actuales. La planificación maestra también calcula el número de días de retraso. 

En algunos casos, es posible optar por no calcular retrasos, como cuando los usuarios saben que pueden acelerar los plazos seleccionando modos de entrega alternativos. 

Puede configurar cómo calcular los retrasos para un grupo de cobertura. Más adelante puede adjuntar el grupo de cobertura a un artículo. 

En la página **Parámetros de planificación maestra** puede establecer el momento de inicio para el cálculo de retrasos. Si se satisface un pedido después de este momento, entonces se añade un retraso de un día a la fecha de retraso del pedido. 

> [!NOTE]
> En versiones anteriores, los retrasos calculados se conocían como *mensajes de futuros*, la fecha retrasada como *fecha de futuros* y las transacciones retrasadas como *transacciones establecidas en una fecha futura*.

## <a name="limited-delays-in-production-setup-with-multiple-bom-levels"></a>Demoras limitadas en la configuración de producción con múltiples niveles de lista de materiales
Cuando trabaja con retrasos en una configuración de producción que tiene varios niveles de lista de materiales, es importante tener en cuenta que solo los artículos directamente encima del artículo (en la estructura de la lista de materiales) que causan el retraso, se actualizarán con un retraso como parte de la ejecución de la planificación maestra. Otros elementos en la estructura de la lista de materiales no aplicarán el retraso hasta la primera ejecución de planificación maestra, cuando se apruebe o firme el pedido planificado para el nivel superior. 

Para evitar esta limitación conocida, las órdenes de producción en la parte superior de la estructura de la lista de materiales con demoras pueden aprobarse (o reafirmarse) antes de la próxima ejecución de planificación maestra. De esta forma, se mantendrá el retraso del pedido de producción planificado aprobado retrasado y todos los componentes subyacentes se actualizarán en consecuencia.
Los mensajes de acción también se pueden usar para identificar órdenes planificadas que se pueden mover a una fecha posterior, debido a otros retrasos en la estructura de la lista de materiales.

## <a name="desired-date"></a>Fecha deseada

En la página **Pedido planificado** , en la pestaña **Retrasos** está la **Fecha deseada** para el pedido planificado. La fecha deseada de un pedido planificado es la fecha base para los retrasos, que es una fecha calculada igual a la **Fecha solicitada** calculada a partir del **Requisito neto**. Si el pedido planificado es una línea de L. MAT, una línea de producción o una línea kanban, la fecha deseada se basa en **Fecha de requisito** y la fecha deseada no se mostrará en la página **Pedido planificado**.

## <a name="additional-resources"></a>Recursos adicionales

[Configuración de cobertura](coverage-settings.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]