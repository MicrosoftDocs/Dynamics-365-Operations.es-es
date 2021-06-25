---
title: Supervisión de la precisión de previsión
description: Este tema describe los tipos de precisión de previsión que Dynamics 365 Supply Chain Management calcula, y se explica cómo puede ver los valores de precisos.
author: roxanadiaconu
ms.date: 01/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanForecastDetails
audience: Application User
ms.reviewer: kamaybac
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6ad41e002f6246311c3755df5baf4a010f9204ee
ms.sourcegitcommit: ff09736563d3cd2bc74c7664edd1767b218401cb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2021
ms.locfileid: "6188919"
---
# <a name="monitor-forecast-accuracy"></a>Supervisión de la precisión de previsión

[!include [banner](../includes/banner.md)]

Este tema describe los tipos de precisión de previsión que Microsoft Dynamics 365 Supply Chain Management calcula, y se explica cómo puede ver los valores de precisos.

Supply Chain Management calcula los siguientes tipos de precisión de previsión:

-   Precisión histórica de previsión, comparando la previsión histórica que la planificación maestra usa con la demanda histórica. Para ver los valores (los valores absolutos y los valores de porcentaje) para la precisión histórica de previsión, haga clic en **Mostrar precisión** en la página **Detalles de previsión de la demanda**.
-   La precisión estimada del modelo de previsión que se usa para generar las predicciones. Puede ver el porcentaje de precisión en **Detalles del modelo: MAPE** en la página **Detalles de previsión de la demanda**. 

> [!NOTE]
> Si usa el servicio de aprendizaje automático de Microsoft Azure para la previsión de la demanda, el cálculo de la precisión del modelo interno se basa en el conjunto de datos de prueba. Para especificar el tamaño del conjunto de datos de la prueba, establezca el parámetro **TEST\_SET\_SIZE\_PERCENT** en la página **Parámetros de previsión de demanda**. Por ejemplo, si establece el valor a **20**, el último 20 por ciento de los datos históricos se usarán para calcular la precisión de modelo interna.


## <a name="additional-resources"></a>Recursos adicionales

[Autorizar previsión de la demanda ajustada](authorize-adjusted-forecast.md)

[Eliminación de valores atípicos de los datos de transacción históricos al calcular una previsión de la demanda](remove-historical-outliers-calculating-demand-forecast.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]