---
title: "Supervisión de la precisión de previsión"
description: "Este artículo describe los tipos de precisión de previsión que Microsoft Dynamics 365 for Finance and Operations calcula, y se explica cómo puede ver los valores de precisos."
author: roxanadiaconu
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqDemPlanForecastDetails
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 72863
ms.assetid: 810a0d63-f4c6-4167-b2b3-a178b74ead89
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: efcb77ff883b29a4bbaba27551e02311742afbbd
ms.openlocfilehash: 1f54251b6f6937c59293bd44a0fc27272ffd3d55
ms.contentlocale: es-es
ms.lasthandoff: 05/08/2018

---

# <a name="monitor-forecast-accuracy"></a><span data-ttu-id="b2ba4-103">Supervisión de la precisión de previsión</span><span class="sxs-lookup"><span data-stu-id="b2ba4-103">Monitor forecast accuracy</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b2ba4-104">Este artículo describe los tipos de precisión de previsión que Microsoft Dynamics 365 for Finance and Operations calcula, y se explica cómo puede ver los valores de precisos.</span><span class="sxs-lookup"><span data-stu-id="b2ba4-104">This article describes the types of forecast accuracy that Microsoft Dynamics 365 for Finance and Operations calculates, and explains how you can view the accuracy values.</span></span>

<span data-ttu-id="b2ba4-105">Finance and Operations calcula los siguientes tipos de precisión de previsión:</span><span class="sxs-lookup"><span data-stu-id="b2ba4-105">Finance and Operations calculates the following types of forecast accuracy:</span></span>

-   <span data-ttu-id="b2ba4-106">Precisión histórica de previsión, comparando la previsión histórica que la planificación maestra usa con la demanda histórica.</span><span class="sxs-lookup"><span data-stu-id="b2ba4-106">Historical forecast accuracy, by comparing the historical forecast that Master Planning uses with the historical demand.</span></span> <span data-ttu-id="b2ba4-107">Para ver los valores (los valores absolutos y los valores de porcentaje) para la precisión histórica de previsión, haga clic en **Mostrar precisión** en la página **Detalles de previsión de la demanda**.</span><span class="sxs-lookup"><span data-stu-id="b2ba4-107">To view the values (both absolute values and percentage values) for historical forecast accuracy, click **Show accuracy** on the **Demand forecast details** page.</span></span>
-   <span data-ttu-id="b2ba4-108">La precisión estimada del modelo de previsión que se usa para generar las predicciones.</span><span class="sxs-lookup"><span data-stu-id="b2ba4-108">The estimated accuracy of the forecasting model that is used to generate the predictions.</span></span> <span data-ttu-id="b2ba4-109">Puede ver el porcentaje de precisión en **Detalles del modelo: MAPE** en la página **Detalles de previsión de la demanda**.</span><span class="sxs-lookup"><span data-stu-id="b2ba4-109">You can view the accuracy percentage under **Model details - MAPE** on the **Demand forecast details** page.</span></span> 

<span data-ttu-id="b2ba4-110">**Nota:** Si usa el servicio de aprendizaje automático de Microsoft Azure para la previsión de la demanda de Finance and Operations, el cálculo de la precisión de modelo interno se basa en el conjunto de datos de la prueba.</span><span class="sxs-lookup"><span data-stu-id="b2ba4-110">**Note:** If you use the Finance and Operations Demand forecasting Microsoft Azure Machine Learning service, the calculation of internal model accuracy is based on the test data set.</span></span> <span data-ttu-id="b2ba4-111">Para especificar el tamaño del conjunto de datos de la prueba, establezca el parámetro **TEST\_SET\_SIZE\_PERCENT** en la página **Parámetros de previsión de demanda**.</span><span class="sxs-lookup"><span data-stu-id="b2ba4-111">To specify the size of the test data set, set the **TEST\_SET\_SIZE\_PERCENT** parameter on the **Demand forecasting parameters** page.</span></span> <span data-ttu-id="b2ba4-112">Por ejemplo, si establece el valor a **20**, el último 20 por ciento de los datos históricos se usarán para calcular la precisión de modelo interna.</span><span class="sxs-lookup"><span data-stu-id="b2ba4-112">For example, if you set the value to **20**, the last 20 percent of the historical data will be used to calculate the internal model accuracy.</span></span>


<a name="additional-resources"></a><span data-ttu-id="b2ba4-113">Recursos adicionales</span><span class="sxs-lookup"><span data-stu-id="b2ba4-113">Additional resources</span></span>
--------

[<span data-ttu-id="b2ba4-114">Autorización de la previsión ajustada</span><span class="sxs-lookup"><span data-stu-id="b2ba4-114">Authorizing the adjusted forecast</span></span>](authorize-adjusted-forecast.md)

[<span data-ttu-id="b2ba4-115">Eliminación de valores atípicos de los datos de transacción históricos al calcular una previsión de la demanda</span><span class="sxs-lookup"><span data-stu-id="b2ba4-115">Remove outliers from historical transaction data when calculating a demand forecast</span></span>](remove-historical-outliers-calculating-demand-forecast.md)




