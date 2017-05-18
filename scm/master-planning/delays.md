---
title: Retrasos
description: "Este artículo proporciona información acerca de fechas retrasadas en la planificación maestra. Una fecha retrasada es una fecha de vencimiento realista que una transacción recibe si la fecha de cumplimiento más temprana que la planificación maestra calcula es posterior a la fecha solicitada."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqTransFuturesListPage
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19311
ms.assetid: 5ffb1486-2e08-4cdc-bd34-b47ae795ef0f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: a48fbee727a2a553cd768287e60e0c9404b92549
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="delays"></a>Retrasos

[!include[banner](../includes/banner.md)]


Este artículo proporciona información acerca de fechas retrasadas en la planificación maestra. Una fecha retrasada es una fecha de vencimiento realista que una transacción recibe si la fecha de cumplimiento más temprana que la planificación maestra calcula es posterior a la fecha solicitada.

La planificación maestra puede calcular la fecha más temprana de cumplimiento para una transacción según los plazos, la disponibilidad de material, la disponibilidad de capacidad y los diferentes parámetros de planificación. 

Si la planificación maestra calcula una fecha de pedido anterior a la fecha en curso, el pedido no se puede satisfacer a tiempo. Por tanto, se retrasa el pedido. En este caso, la planificación maestra adelanta la planificación del pedido a partir de la fecha en uso e incluye plazos. Estos plazos empiezan con cualquier artículo componente de nivel inferior. El pedido recibe a continuación una fecha retrasada. La fecha retrasada es una fecha de vencimiento real en función de los datos actuales. La planificación maestra también calcula el número de días de retraso. 

En algunos casos, es posible optar por no calcular retrasos, como cuando los usuarios saben que pueden acelerar los plazos seleccionando modos de entrega alternativos. 

Puede configurar cómo calcular los retrasos para un grupo de cobertura. Más adelante puede adjuntar el grupo de cobertura a un artículo. 

En la página **Parámetros de planificación maestra** puede establecer el momento de inicio para el cálculo de retrasos. Si se satisface un pedido después de este momento, entonces se añade un retraso de un día a la fecha de retraso del pedido. 

**Nota:** en versiones anteriores, los retrasos calculados se conocían como *mensajes de futuros*, la fecha retrasada como *fecha de futuros* y las transacciones retrasadas como *transacciones establecidas en una fecha futura*.

<a name="see-also"></a>Consulte también
--------

[Configuración de cobertura](coverage-settings.md)




