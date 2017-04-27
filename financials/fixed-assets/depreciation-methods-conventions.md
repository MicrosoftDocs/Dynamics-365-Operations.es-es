---
title: "Convenciones y métodos de depreciación"
description: "Este artículo proporciona una visión general de las convenciones de depreciación y los métodos de depreciación que son compatibles con Microsoft Dynamics AX."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetDepreciationProfile, AssetGroupBookSetup, AssetGroupDepBookSetup
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3441
ms.assetid: 1d8267b1-86a8-44bf-8814-f56b5d45a0ae
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 8e89a57dda8f2d392483ed13c686ea97b74926b0
ms.openlocfilehash: 51c053e6c130d20258e02284d097431a18bb38cb
ms.lasthandoff: 03/31/2017


---

# <a name="depreciation-methods-and-conventions"></a>Convenciones y métodos de depreciación

[!include[banner](../includes/banner.md)]


Este artículo proporciona una visión general de las convenciones de depreciación y los métodos de depreciación que son compatibles con Microsoft Dynamics AX.

Puede seleccionar varios métodos de depreciación y convenciones de amortizaciones. El objetivo de los métodos es ubicar el valor depreciable del activo fijo en períodos fiscales. El valor depreciable del activo fijo es el precio de la adquisición reducido por el valor residual, si lo hubiere. 

Si utiliza convenciones de amortización y modifica la última fecha de ejecución de la depreciación de un activo que se salta algunas depreciaciones, la depreciación del último año puede ser mayor o menor de lo esperado. La depreciación se ajusta con el número de períodos de depreciación afectados por la modificación de la última fecha de ejecución de la depreciación.

Por ejemplo, si utiliza la convención de amortización de medio año durante tres años, la amortización ocurrirá normalmente a lo largo de 3 1/2 años. Si cambia la última fecha de ejecución de la depreciación durante los 3 1/2 años, el último año de depreciación cambiará el número de períodos afectados. Si cambia la fecha en tres meses, el último año tendrá un valor de depreciación de nueve meses, cuando normalmente serían seis meses.

Puede seleccionar entre las siguientes convenciones de amortización.


-   Medio año
-   Mes completo
-   Medio trimestre
-   Medio mes (primero de mes)
-   Medio mes (el día 15 del mes)
-   Medio año (inicio de año)
-   Medio año (próximo año)

Puede seleccionar entre los siguientes métodos de amortización.
-   Tiempo de vida de depreciación lineal
-   Depreciación degresiva
-   Manual
-   Factor
-   Consumo
-   Tiempo de vida restante de depreciación lineal
-   Depreciación degresiva del 200%
-   Depreciación degresiva del 175%
-   Depreciación degresiva del 150%
-   Depreciación degresiva del 125%

 



<a name="see-also"></a>Consulte también
--------

[Depreciación de activo fijo](fixed-asset-depreciation.md)

[Tiempo de vida de depreciación lineal](Straight-line-service-life-depreciation.md)

[Reducción de la depreciación del saldo](reduce-balance-depreciation.md)

[Depreciación manual](manual-depreciation.md)

[Depreciación de factor](factor-depreciation.md)

[Depreciación de consumo](consumption-depreciation.md)

[Tiempo de vida restante de depreciación lineal](straight-line-life-remaining-depreciation.md)

[Depreciación con amortización degresiva del 125%](125-percent-reducing-balance-depreciation.md)

[Depreciación con amortización degresiva del 150%](150-percent-reducing-balance-depreciation.md)

[Depreciación con amortización degresiva del 175%](175-percent-reducing-balance-depreciation.md)

[Depreciación con amortización degresiva del 200%](200-percent-reducing-balance-depreciation.md)



