---
title: "Exactitud de previsión de Monitor"
description: "Este artículo describe los tipos de precisión de previsión que Microsoft Dynamics 365 para las operaciones calcula, y explica cómo puede ver los valores de precisión."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: d3f88a4fa54217cea909c54955de05e2175db0cd
ms.lasthandoff: 03/29/2017


---

# <a name="monitor-forecast-accuracy"></a>Exactitud de previsión de Monitor

Este artículo describe los tipos de precisión de previsión que Microsoft Dynamics 365 para las operaciones calcula, y explica cómo puede ver los valores de precisión.

La Dynamics 365 para las operaciones calcula los siguientes tipos de precisión de previsión:

-   Precisión histórica de previsión, comparando la previsión histórica que la planificación maestra usa con la demanda histórica. Para ver los valores (los valores absolutos y los valores de porcentaje) para la precisión histórica de previsión, haga clic en **Mostrar precisión** en la página **Detalles de previsión de la demanda**.
-   La precisión estimada del modelo de previsión que se usa para generar las predicciones. Puede ver el porcentaje de precisión en **Detalles del modelo: MAPE** en la página **Detalles de previsión de la demanda**. 

** Nota: ** Si usa Dynamics 365 para el servicio de Microsoft Azure Machine Learning de previsión de demanda de operaciones, el cálculo de precisión interna de modelo se basa en el conjunto de datos de pruebas. Para especificar el tamaño del conjunto de datos de pruebas, establezca ** CALIBRE DETERMINADO\_PERCENT\_\_de la PRUEBA ** el parámetro en ** los parámetros de la previsión de demanda ** la página. Por ejemplo, si establece el valor a **20**, el último 20 por ciento de los datos históricos se usarán para calcular la precisión de modelo interna.


<a name="see-also"></a>Consulte también
--------

[Authorizing the adjusted forecast](authorize-adjusted-forecast.md)

[Remove outliers from historical transaction data when calculating a demand forecast](remove-historical-outliers-calculating-demand-forecast.md)


