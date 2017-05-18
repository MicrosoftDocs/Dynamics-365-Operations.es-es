---
title: "Supervisión de la precisión de previsión"
description: "Este artículo describe los tipos de precisión de previsión que Microsoft Dynamics 365 for Operations calcula, y se explica cómo puede ver los valores de precisos."
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
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 7e470e05d9acb1e7417d0d77655be99e94d15e1d
ms.contentlocale: es-es
ms.lasthandoff: 04/25/2017


---

# <a name="monitor-forecast-accuracy"></a>Supervisión de la precisión de previsión

[!include[banner](../includes/banner.md)]


Este artículo describe los tipos de precisión de previsión que Microsoft Dynamics 365 for Operations calcula, y se explica cómo puede ver los valores de precisos.

Dynamics 365 for Operations calcula los siguientes tipos de precisión de previsión:

-   Precisión histórica de previsión, comparando la previsión histórica que la planificación maestra usa con la demanda histórica. Para ver los valores (los valores absolutos y los valores de porcentaje) para la precisión histórica de previsión, haga clic en **Mostrar precisión** en la página **Detalles de previsión de la demanda**.
-   La precisión estimada del modelo de previsión que se usa para generar las predicciones. Puede ver el porcentaje de precisión en **Detalles del modelo: MAPE** en la página **Detalles de previsión de la demanda**. 

**Nota:** si usa el servicio de aprendizaje automático de precisión de la demanda de Microsoft Azure de Dynamics 365 for Operations, el cálculo de la precisión de modelo interno se basa en el conjunto de datos de la prueba. Para especificar el tamaño del conjunto de datos de la prueba, establezca el parámetro **TEST\_SET\_SIZE\_PERCENT** en la página **Parámetros de previsión de demanda**. Por ejemplo, si establece el valor a **20**, el último 20 por ciento de los datos históricos se usarán para calcular la precisión de modelo interna.


<a name="see-also"></a>Consulte también
--------

[Autorización de la previsión ajustada](authorize-adjusted-forecast.md)

[Eliminación de valores atípicos de los datos de transacción históricos al calcular una previsión de la demanda](remove-historical-outliers-calculating-demand-forecast.md)




