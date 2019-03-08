---
title: Página principal de la gestión de costes
description: La gestión de costes le permite gestionar la evaluación y la contabilidad de materias primas, productos semiterminados, productos terminados y de activos en curso.
author: AndersGirke
manager: AnnBe
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: fd94ae4c5ea855139fd1c41060de7db455ffab06
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2019
ms.locfileid: "333953"
---
# <a name="cost-management-home-page"></a>Página principal de la gestión de costes

[!include [banner](../includes/banner.md)]

La [gestión de costes](https://www.youtube.com/watch?v=vXzlC-mOBcg&feature=youtu.be) le permite trabajar con la evaluación y la contabilidad de materias primas, productos semiterminados, productos terminados y de activos en curso. Es el proceso de definir, gestionar e informar de la [contabilidad de inventario](cost-object.md) y la [contabilidad de fabricación](bom-calculations.md).

Puede definir directivas de costes en las siguientes áreas: 
-  [Coste predeterminado](costing-versions.md)
-  [Contabilidad de inventario](cost-object.md)
-  [Contabilidad de fabricación](bom-calculations.md)
-  [Contabilidad de costes indirectos](costing-sheets.md)
-  [Integración contable](production-order-cost-analysis.md)

Por ejemplo, puede definir los métodos de valoración de inventario, como [FIFO](fifo-physical-value-marking.md), [media ponderada](weighted-average-physical-value-marking.md), [coste estándar](prerequisites-standard-costs.md) o [media móvil](moving-average.md) que desea aplicar a los productos en [Grupo de modelos de artículos](../inventory/reserve-inventory-quantities.md) en Contabilidad de inventario.

Puede obtener acceso a la contabilidad de inventario y la contabilidad de fabricación desde los espacios de trabajo **Administración de costes** y **Análisis de costes** . Estos espacios de trabajo proporcionan una visión general completa del estado actual, los indicadores clave de rendimiento (KPI) y la detección de la desviación. 

La contabilidad de fabricación le permite administrar la [Gestión de costes de órdenes de producción](production-order-cost-analysis.md) en pedidos de producción y pedidos de lote, y [Contabilización previa de los costes](backflush-costing.md) en producción ajustada.

El Contenido de [Gestión de costes en Power BI](../../dev-itpro/analytics/cost-management-content-pack.md) proporciona información administrativa de inventario y de inventario del trabajo en curso, y explica cómo el coste fluye por categoría en el tiempo. La información se puede usar como suplemento detallado del informe financiero.

### <a name="additional-resources"></a>Recursos adicionales

#### <a name="whats-new-and-in-development"></a>Novedades y características en desarrollo

Consulte la [Guía básica de Microsoft Dynamics 365](https://roadmap.dynamics.com/) para ver qué características nuevas hemos lanzado y cuáles están en desarrollo. 

#### <a name="white-paper"></a>Documentación
El [cálculo de L. MAT. con una hoja de gestión de costes](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/white-papers/365operationsbomcalsheet) describe cómo configurar una hoja de gestión de costes que incluye material y fabricación, y cómo la configuración afecta a los resultados del cálculo de L. MAT. Para explicar mejor los temas, se proporcionan escenarios y datos concretos que demuestran el efecto de los distintos ajustes y configuraciones. No esperamos que siga todos estos escenarios porque este documento no proporciona suficientes detalles para configurarlos. Sin embargo, si posee el conocimiento básico, puede intentar reproducir las guías de tareas que se muestran a continuación en el orden en que aparecen. Use el conocimiento que ha obtenido de leer este documento para realizar el análisis del cálculo de L. MAT. 

-  [Cree un producto acabado.](tasks/create-finished-product-2016-02.md)
-  [Cree un producto semi-acabado.](tasks/create-semi-finished-product-2016-02.md)
-  [Crear materias primas](tasks/create-raw-materials-2016-02.md)
-  [Crear BOM](tasks/create-boms-2016-02.md)
-  [Crear rutas](tasks/create-routes-2016-02.md)
-  [Calcular una L.MAT mediante una estructura de un solo nivel](tasks/calculate-bom-single-level-structure-2016-02.md)
-  [Calcular un L.MAT mediante una estructura multinivel](tasks/calculate-bom-multilevel-structure-2016-02.md)


#### <a name="blogs"></a>Blogs
Puede encontrar opiniones, novedades y otra información acerca de la Gestión de costes en el [blog del equipo de I+D y fabricación de Dynamics AX](https://blogs.msdn.microsoft.com/axmfg) y el [blog del equipo de I+D de administración de Supply Chain Management en Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm). Aunque la mayoría de ellos se escribieron para la versión anterior de Gestión de costes, aún se aplican los mismos conceptos y, en la versión actual, los procedimientos son también similares.

#### <a name="task-guides"></a>Guías de tareas
Hay ayuda adicional disponible como guías de tareas en Finance and Operations. Para tener acceso a las guías de tareas, haga clic en el botón Ayuda en cualquier página.

