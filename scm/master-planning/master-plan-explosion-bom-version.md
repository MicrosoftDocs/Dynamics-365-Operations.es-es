---
title: "Expansión de una versión de L"
description: "Este artículo para una situación de planificación maestra que implica la expansión de una versión (BOM) de la lista de materiales."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: ReqTransExplosion
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19211
ms.assetid: fe08c2e6-9cc5-4e34-bbb2-cd07843403b5
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 6461a07f8c8f02f584e5ef70b21ebaf04f29b57b
ms.lasthandoff: 03/31/2017


---

# <a name="explosion-of-a-bom-version"></a>Expansión de una versión de L

Este artículo para una situación de planificación maestra que implica la expansión de una versión (BOM) de la lista de materiales.

Una expansión de demanda de una versión de lista de materiales (L. MAT.) crea una demanda de cada elemento de línea de lista de materiales en un sitio específico y, posiblemente, en un almacén específico. Una lista de materiales específica de un sitio puede definir un almacén para cada línea de lista de materiales. Además, para cada línea de lista de materiales, la configuración de las dimensiones de artículos determina si es preciso especificar el almacén. La demanda resultante para cada elemento de línea de lista de materiales se convierte, a su vez, en el punto de partida para expansiones de demandas adicionales. El escenario de planificación maestra implica las condiciones siguientes:

-   La dimensión Sitio es obligatoria y debe especificarse en la transacción de demanda.
-   La dimensión Sitio es coherente. Por lo tanto, el sitio de menor nivel de demanda es equivalente al sitio de la transacción de demanda inicial.

La ilustración siguiente muestra el proceso de expansión de la demanda de planificación maestra. ![Expansión de la demanda con una versión de L. MAT](./media/multisitedemandexplosionscenariousingbomversion.gif)

<a name="see-also"></a>Consulte también
--------

[- Planificación maestra cómo se determina la versión de L master-plan-bom-version-determined.md] ()

[Master planning and multisite functionality](master-plan-multisite-functionality.md)


