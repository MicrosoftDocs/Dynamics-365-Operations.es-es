---
title: "Determine la versión de L"
description: "Durante una expansión de demanda, si un artículo tiene un tipo de pedido predeterminado de producción, el motor de planificación busca una versión de L según el sitio."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMConsistOf, BOMDesigner, BOMTable, InventItemOrderSetup
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2534
ms.assetid: a5b64301-a011-4469-afaf-e4c9164ef9c6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 4e4f5f02dfa986669decbc8854148b5eff928c2a
ms.lasthandoff: 03/31/2017


---

# <a name="determine-the-bom-version"></a>Determine la versión de L

Durante una expansión de demanda, si un artículo tiene un tipo de pedido predeterminado de producción, el motor de planificación busca una versión de L según el sitio. 

La dimensión del sitio se conoce siempre y se indica en la transacción de demanda. El siguiente proceso se usa para determinar la versión de L. MAT que utilizar:

-   Si hay una versión de L. MAT definida para el artículo en el sitio de demanda, se usa la L. MAT específica del sitio.
-   Si no hay una versión de L. MAT definida para el artículo en el sitio de demanda, se usa una L. MAT general. Una L. MAT general no indica un sitio, y es válida para varios sitios. Si hay una L. MAT general, se utiliza.
-   Si no hay ninguna L. MAT. general que se pueda usar, la expansión de la demanda se detiene en este punto.

Una versión de L. MAT válida, tanto si es específica del sitio como si es general, debe cumplir los criterios necesarios para la fecha y la cantidad.




