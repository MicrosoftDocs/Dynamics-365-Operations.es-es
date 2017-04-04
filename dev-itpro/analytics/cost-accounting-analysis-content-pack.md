---
title: "Contenido de Power BI de análisis de la contabilidad de costes"
description: "Este tema describe lo que se incluye en el contenido de Power BI de análisis de la contabilidad de costes. Explica de cómo obtener acceso a los informes de Power BI, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para compilar el contenido."
author: YuyuScheller
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations
ms.custom: 270274
ms.assetid: b74549df-35d5-4f2f-b3c7-405b0d38ea78
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 50e7bd92ee693f59fd013226aee22bd1a54c81e2
ms.lasthandoff: 03/31/2017


---

# <a name="cost-accounting-analysis-power-bi-content"></a>Contenido de Power BI de análisis de la contabilidad de costes

Este tema describe lo que se incluye en el contenido de Power BI de análisis de la contabilidad de costes. Explica de cómo obtener acceso a los informes de Power BI, y proporciona información acerca del modelo de datos y las entidades que se utilizaron para compilar el contenido.

<a name="overview"></a>Visión general
--------

** Análisis de la contabilidad de costes ** el contenido de Power BI de Microsoft está destinado a los conductores o cualquier entidad de costes que es responsable de realizar el control de costes de una organización. Incluye medidas clave, como el coste, magnitud, y del índice de coste por coste real, coste de presupuesto, y coste de presupuesto flexible. Usa datos de transacción de la contabilidad de costes en Microsoft Dynamics 365 para las operaciones y proporciona una visión global de costes para la organización completa en una divisa de notificación. Los directores pueden filtrar los datos por objetos de coste para realizar el control de costes de sus unidades organizativas, incluso si la organización puede tener varias entidades jurídicas. Dado que ** análisis de la contabilidad de costes ** accione las desviaciones de contenido de los resaltes de BI entre los costes reales y los costes presupuestados, los administradores pueden para enviar sobre las tendencias y positivas negativas para sus unidades operativas. Los directores pueden explorar en profundidad las jerarquías de artículo de coste o elementos de coste individuales para conseguir la penetración detallada sobre cómo variaciones de coste han aparecido y, a continuación para tomar medidas vigencia. ** Análisis de la contabilidad de costes ** el contenido de Power BI permite a contables de coste analizar cómo el coste fluye los objetos de coste de toda la organización. Para obtener más información acerca de la contabilidad de costes, consulte [] página principal de la contabilidad de costes (estadísticas de /dynamics365/operations/financials/cost/contabilidad de costes - home-page.md). Definición de la seguridad de nivel de acceso en contabilidad de costes y combinándola con seguridad de nivel fila- en BI de la potencia, puede conceder a todos los propietarios de objeto de coste que el acceso a ** análisis de la contabilidad de costes acciona ** el contenido de BI. Todos los datos en las vistas continuación filtrarán en función del nivel de acceso que se controla en contabilidad de costes. Para obtener más información acerca de la seguridad de nivel de acceso y seguridad de nivel fila-, consulte [seguridad Configuración para el contenido de la contabilidad de costes para el BI] de la potencia (setup-security-cost-accounting-content-pack.md).

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI
Puede encontrar ** análisis de la contabilidad de costes acciona ** el contenido de BI en la biblioteca compartida de los activos en los servicios (LCS) del ciclo de vida de Microsoft Dynamics. Para obtener más información sobre cómo descargar el contenido y conectarlo a su Dynamics 365 para los datos de las operaciones, consulte [contenido de Power BI en el CD de Microsoft y sus socios power-bi-content-microsoft-partners.md] (). ** Nota: ** KB4011327 ** ** es un requisito previo por ** análisis de la contabilidad de costes ** el contenido de Power BI.  Tras en firme a los Servicios de ciclo de vida, puede tener acceso a KB aquí: <https://fix.lcs.dynamics.com/issue/results/?q=kb4011327>.

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Métricas que se incluyen en el contenido de Power BI
El contenido incluye un conjunto de páginas del informe. Cada página consta de un conjunto de métricas que se visualicen como gráficos, los mosaicos, y tablas. La tabla siguiente proporciona una visión general de las vistas en ** análisis de la contabilidad de costes acciona ** el contenido de BI.

| Página de informe                      | Gráfico                                                                                                                         | Icono                                          |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| Control de costes por período fiscal    | Coste real y coste de presupuesto por el nivel de la jerarquía de artículo de coste                                                                   | Coste real frente coste de presupuesto                    |
|                                  | Desviación de presupuesto por el nivel de la jerarquía de artículo de coste                                                                               | Tasa de coste real frente índice de coste de presupuesto          |
|                                  | Desviación de presupuesto de la parte superior 10 en porcentaje por el artículo de coste                                                                          | Magnitud real frente magnitud del presupuesto          |
| Control de costes del año Hasta fecha     | Coste real y coste de presupuesto por período del año natural                                                                           | Coste real frente coste de presupuesto                    |
|                                  | Desviación de presupuesto por período del año natural                                                                                       | Tasa de coste real frente índice de coste de presupuesto          |
|                                  | Desviación de presupuesto de la parte superior 10 en porcentaje por el artículo de coste                                                                          | Magnitud real frente magnitud del presupuesto          |
| Índice de coste del año fiscal         | Tasa de coste real por comportamiento del coste                                                                                             | Tasa de coste real frente índice de coste de presupuesto          |
|                                  | Tasa del coste real, desviación de índice de coste de presupuesto, porcentaje de la tasa de coste de presupuesto y índice de coste de presupuesto por el nivel de la jerarquía de artículo de coste | Magnitud real frente magnitud del presupuesto          |
|                                  | Desviación de presupuesto por el nivel de la jerarquía de artículo de coste                                                                               |                                               |
|                                  | Desviación de presupuesto de la parte superior 10 en porcentaje por el artículo de coste                                                                          |                                               |
| Presupuesto flexible por período fiscal | Coste real, coste de presupuesto y coste de presupuesto flexible por el nivel de la jerarquía de artículo de coste                                             | Magnitud real frente magnitud del presupuesto          |
|                                  | Desviación de presupuesto y desviación de presupuesto flexible por el nivel de la jerarquía de artículo de coste                                                  | Coste real frente coste de presupuesto flexible           |
|                                  | Coste real, coste de presupuesto y coste flexible por el nivel de la jerarquía de comportamiento de costes y el coste de artículo                                  | Tasa de coste real frente flexible índice de coste de presupuesto |
| Extracto del coste por período fiscal  | Coste real por nombre de miembro de dimensión del nivel de la jerarquía del artículo de coste y de objeto de coste                                             |                                               |
|                                  | Coste real por nombre de miembro de dimensión del nombre de miembro de dimensión del objeto de costes y el coste de artículo                                       |                                               |

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades
Las Dynamics 365 para las operaciones que los datos se usa para rellenar las páginas de informes de ** análisis de la contabilidad de costes acciona ** el contenido de BI. Estos datos se representa como medidas globales que se realizan en el almacén de la entidad, que es una base de datos de Microsoft SQL que se optimiza para analítica. Para obtener más información, consulte [visión general de la integración de Power BI con la entidad almacenada power-bi-integration-entity-store.md] (). Las medidas siguientes de agregado de la clave se usan como base del contenido.

| Entidad                  | Medida clave global | Origen de datos para Dynamics 365 para las operaciones | Campo     | Descripción                                   |
|-------------------------|---------------------------|---------------------------------------------|-----------|-----------------------------------------------|
| Entradas de la contabilidad de costes | SUM (importe)               | CAMDATAAggregatedCostEntry                  | Importe    | Importe en la divisa de contabilidad de la contabilidad de costes |
| Entradas estadísticas     | SUM (magnitud)            | CAMDATAAggregatedStatisctialEntry           | Magnitud |                                               |

Se usará las tablas siguiente muestra cómo cerrar las medidas globales para crear varias medidas calculadas en el conjunto de datos del contenido.

| Medida                                       | Cómo se calcula la medida                                                                                          |
|-----------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Coste real                                   | CALCULE (“VALOR de versions'entity_PLACEHOLDER\] \\_[ISSOURCEVERSIONBUDGET de la medida\], “de la transacción de entries'entity_PLACEHOLDER \ [de la contabilidad de costes = 0)            |
| Coste presupuestario                                   | CALCULE (“medida de entries'entity_PLACEHOLDER\]\ [de contabilidad de costes, “VALOR de versions'entity_PLACEHOLDER\] \\_[ISSOURCEVERSIONBUDGET de la transacción = 1)            |
| Desviación de coste de presupuesto                          | coste real\]\]\] - \[de coste de presupuesto\[                                                                                      |
| Porcentaje de desviación del presupuesto                    | (SI coste de presupuesto\[\]\[= 0, espacio en blanco (), coste de presupuesto\]\]\] / \[de desviación de presupuesto \[)                                                |
| Magnitud real                              | CALCULE (“entries'entity_PLACEHOLDER \ [estadístico FullMagnitude\], “VALOR de versions'entity_PLACEHOLDER\] \\_[ISSOURCEVERSIONBUDGET de la transacción = 0)          |
| Presupueste la magnitud                              | CALCULE (\[FullMagnitude\], VALOR 'de versions'entity_PLACEHOLDER\] \\_[ISSOURCEVERSIONBUDGET de la transacción = 1)                               |
| Desviación estadística de presupuesto                   | magnitud real\]\]\] - \[de la magnitud del presupuesto\[                                                                            |
| Porcentaje de desviación estadístico de presupuesto        | (SI magnitud\] del presupuesto\[= 0, espacio en blanco (), magnitud estadística\]del presupuesto\] / \[de desviación de presupuesto \[)                          |
| Índice de costes reales                              | (SI magnitud real\[\]\[= 0, carácter EN BLANCO (), magnitud real\]\]\] / \[\[real \[)                                          |
| Índice de coste de presupuesto                              | (SI magnitud\] del presupuesto\[= 0, carácter EN BLANCO (),\]magnitud del presupuesto\] / \[de coste de presupuesto \[)                                          |
| Desviación de índice de coste de presupuesto                     | \]índice\]real\] - \[de índice de coste de presupuesto\[                                                                            |
| Porcentaje de desviación de índice de coste de presupuesto          | (SI coste de presupuesto\[\]\[= 0, espacio en blanco (),\]índice de coste de presupuesto\] / \[de desviación de índice de coste de presupuesto \[)                                 |
| Coste de presupuesto fijo                             | CALCULE (coste de presupuesto\[\]\[, 'entries'entity_PLACEHOLDER \\] [COSTBEHAVIOR de la contabilidad de costes = 1)                                              |
| Coste de presupuesto variable                          | CALCULE (coste de presupuesto\[\]\[, 'entries'entity_PLACEHOLDER \\] [COSTBEHAVIOR de la contabilidad de costes = 2)                                              |
| Coste de presupuesto flexible fijo                    | \[Coste de presupuesto fijo\]                                                                                                  |
| Coste de presupuesto flexible variable                 | (SI magnitud\] del presupuesto\[= 0, carácter EN BLANCO (), (magnitud\]variable del presupuesto\] / \[de coste de presupuesto\[) magnitud real \*\]\* \[)       |
| Coste de presupuesto flexible                          | \[del coste de presupuesto flexible variable flexible\]\]\] + \[de coste de presupuesto                                                     |
| Desviación de presupuesto flexible                      | coste real flexible\]\]\] - \[de coste de presupuesto\[                                                                             |
| Porcentaje de desviación Presupuesto flexible           | (SI coste de presupuesto flexible\[\]\[= 0, carácter EN BLANCO (), de costes de presupuesto flexible flexible\]\]\] / \[de desviación de presupuesto \[)                     |
| Tasa flexible del coste de presupuesto                     | (SI magnitud real\[\]\[= 0, carácter EN BLANCO (), magnitud flexible real\]\]\] / \[de coste de presupuesto \[)                                 |
| Desviación flexible de índice de coste de presupuesto            | tasa flexible\]\]real\] - \[de índice de coste de presupuesto\[                                                                   |
| Porcentaje de desviación flexible de índice de coste de presupuesto | SI flexible (índice de coste\] de presupuesto\[= 0, carácter EN BLANCO (), tasa flexible flexible\]de coste de presupuesto\] / \[de desviación de índice de coste de presupuesto \[) |

Las dimensiones clave siguientes se utilizan como filtros para cortar las medidas globales para lograr mayor granularidad y para proporcionar penetraciones analíticas más profundas.

| Entidad                             | Ejemplos de atributos                                                                                               |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Libros mayores de contabilidad de costes            | Libro mayor de contabilidad de costes                                                                                               |
| Unidades de control de costes                 | Nombre de unidad de control de costes                                                                                               |
| Dimensiones de elemento de coste            | Nombre de dimensión de artículos de costes, nombre de miembro de dimensión de artículo de coste, descripción de miembro de dimensión de artículo de coste          |
| Dimensiones de objeto de coste             | Coste el nombre de dimensión de objeto, nombre de miembro de dimensión de objeto de coste, descripción de miembro de dimensión de objeto de coste              |
| Dimensiones estadísticas             | Nombre de dimensión, estadístico nombre estadístico de miembro de dimensión, descripción estadística de miembro de dimensión              |
| Jerarquías de dimensión de objeto de coste  | Nombre de la jerarquía de dimensiones de objeto de coste, nivel de la jerarquía de dimensiones de objeto de coste, árbol de la jerarquía de dimensiones de objeto de coste    |
| Jerarquías de dimensión de artículo de coste | Nombre de la jerarquía de dimensión de artículo de coste, nivel de la jerarquía de dimensión de artículo de coste, árbol de la jerarquía de dimensión de artículo de coste |
| Jerarquías de dimensión estadísticas  | Nombre estadístico de la jerarquía de dimensión, estadístico nivel de la jerarquía de dimensión, estadístico árbol de la jerarquía de dimensión    |
| Versiones de transacción               | Nombre de versión                                                                                                         |
| Calendarios fiscales                   | Calendario, descripción del calendario                                                                                       |
| Años fiscales                       | Año natural                                                                                                        |
| Períodos fiscales                     | Período del año natural                                                                                                 |

## <a name="additional-resources"></a>Recursos adicionales
Estos son algunos vínculos útiles relacionados con las entidades y la creación de contenido de Power BI:

-   [Entidades de datos](..\data-entities\data-entities.md)
-   [Creación de paquetes de contenido organizativo](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelado de datos con Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adición de iconos de Power BI a espacios de trabajo](configure-power-bi-integration.md)
-   [Seguridad de la configuración para el contenido de la contabilidad de costes para el BI] de la potencia (setup-security-cost-accounting-content-pack.md)


