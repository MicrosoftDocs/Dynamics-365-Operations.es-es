---
title: "Contenido en Power BI sobre el análisis de la contabilidad de costes"
description: "Este tema describe lo que se incluye en el contenido de análisis de contabilidad de costes en Power BI. Explica cómo obtener acceso a los informes de Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido."
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

# <a name="cost-accounting-analysis-power-bi-content"></a>Contenido en Power BI sobre el análisis de la contabilidad de costes

Este tema describe lo que se incluye en el contenido de análisis de contabilidad de costes en Power BI. Explica cómo obtener acceso a los informes de Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.

<a name="overview"></a>Visión general
--------

El contenido de **Análisis de la contabilidad de costes** en Microsoft Power BI está destinado a los controladores de costes responsables de realizar el control de costes de una organización. Incluye medidas clave, como el coste, magnitud, el índice de coste por coste real, coste presupuestario, y coste presupuestario flexible. Usa datos de transacción de la contabilidad de costes de Microsoft Dynamics 365 for Operations y proporciona una visión global de costes para la organización completa en una divisa de notificación. Los directores pueden filtrar los datos por objetos de coste para realizar el control de costes de sus unidades organizativas, incluso aunque la organización tenga varias entidades jurídicas. Dado que el contenido de **Análisis de la contabilidad de costes** en Power BI resalta las desviaciones entre los costes reales y los costes presupuestados, se puede notificar a los directores las tendencias positivas y negativas de sus unidades operativas. Los directores pueden explorar en profundidad las jerarquías de artículos de coste o elementos de coste individuales para conseguir una visión detallada sobre cómo las variaciones de coste se han producido y luego tomar medidas efectivas. El contenido de **Análisis de la contabilidad de costes** de Power BI permite a los contables de coste analizar cómo el coste fluye por los objetos de coste de toda la organización. Para obtener más información acerca de la contabilidad de costes, consulte [la página principal de la contabilidad de costes](/dynamics365/operations/financials/cost-accounting/cost-accounting-home-page.md). Si define la seguridad de nivel de acceso en contabilidad de costes y la combina con seguridad de nivel fila en Power BI, puede conceder a todos los propietarios de objetos de coste acceso al contenido de **Análisis de la contabilidad de costes** en Power BI. Después todos los datos de las vistas se filtrarán en función del nivel de acceso que se controla en contabilidad de costes. Para obtener más información acerca de la seguridad de nivel de acceso y seguridad de nivel fila, consulte la [configuración de seguridad del contenido de la contabilidad de costes de Power BI](setup-security-cost-accounting-content-pack.md).

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI
El contenido de **Análisis de la contabilidad de costes** de Power BI se encuentra en la biblioteca de activos compartidos en Microsoft Dynamics Lifecycle Services (LCS). Para obtener más información sobre cómo descargar el contenido y conectarlo a los datos de Dynamics 365 for Operations, consulte [Contenido de Power BI en LCS en Microsoft y sus socios](power-bi-content-microsoft-partners.md). **Nota:** KB4011327** ** es un requisito previo para el contenido de **Análisis de la contabilidad de costes** en Power BI.  Tras iniciar sesión en Lifecycle Services, puede tener acceso a KB aquí: <https://fix.lcs.dynamics.com/issue/results/?q=kb4011327>.

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Métricas que se incluyen en el contenido de Power BI
El contenido incluye un conjunto de páginas de informe. Cada página consta de un conjunto de métricas que se visualizan como gráficos, mosaicos y tablas. La tabla siguiente proporciona una visión general de las visualizaciones en el contenido de **Análisis de la contabilidad de costes** en Power BI.

| Página de informes                      | Gráfico                                                                                                                         | Icono                                          |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------|
| Control de costes por período fiscal    | Coste real y coste presupuestario por nivel de la jerarquía de artículo de coste                                                                   | Coste real frente a coste presupuestario                    |
|                                  | Desviación de presupuesto por el nivel de la jerarquía de artículo de coste                                                                               | Índice de coste real frente a coste presupuestario          |
|                                  | Los 10 con mayor desviación de presupuesto en porcentaje por artículo de coste                                                                          | Magnitud real frente a magnitud del presupuesto          |
| Control de costes del año hasta la fecha     | Coste real y coste presupuestario por período del año natural                                                                           | Coste real frente a coste presupuestario                    |
|                                  | Desviación de presupuesto por período del año natural                                                                                       | Índice de coste real frente a coste presupuestario          |
|                                  | Los 10 con mayor desviación de presupuesto en porcentaje por artículo de coste                                                                          | Magnitud real frente a magnitud del presupuesto          |
| Índice de coste por año fiscal         | Tasa de coste real por comportamiento del coste                                                                                             | Índice de coste real frente a coste presupuestario          |
|                                  | Tasa del coste real, desviación de índice de coste presupuestario, porcentaje de la tasa de coste presupuestario y índice de coste presupuestario por el nivel de la jerarquía de artículo de coste | Magnitud real frente a magnitud del presupuesto          |
|                                  | Desviación de presupuesto por el nivel de la jerarquía de artículo de coste                                                                               |                                               |
|                                  | Los 10 con mayor desviación de presupuesto en porcentaje por artículo de coste                                                                          |                                               |
| Presupuesto flexible por período fiscal | Coste real, coste presupuestario y coste presupuestario flexible por nivel de la jerarquía de artículo de coste                                             | Magnitud real frente a magnitud del presupuesto          |
|                                  | Desviación de presupuesto y desviación de presupuesto flexible por nivel de la jerarquía de artículo de coste                                                  | Coste real frente a coste presupuestario flexible           |
|                                  | Coste real, coste presupuestario y coste flexible por comportamiento de coste y nivel de la jerarquía de artículo de coste                                  | Índice de coste real frente a índice de coste presupuestario flexible |
| Extracto del coste por período fiscal  | Coste real por nivel de la jerarquía de artículo de coste y nombre de miembro de dimensión de objeto de coste                                             |                                               |
|                                  | Coste real por nombre de miembro de dimensión de objeto de coste y nombre de miembro de dimensión de artículo de coste                                       |                                               |

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades
Los datos de Dynamics 365 for Operations se usan para rellenar las páginas de informes en el contenido de **Análisis de la contabilidad de costes** en Power BI. Estos datos se representan como medidas globales que se realizan en el almacén de la entidad, que es una base de datos de Microsoft SQL que se optimiza para análisis. Para obtener más información, consulte [Visión general de la integración de Power BI con el almacén de entidades](power-bi-integration-entity-store.md). Las siguientes medidas agregadas clave se usan como la base del contenido.

| Entidad                  | Medida agregada clave | Origen de datos para Dynamics 365 for Operations | Campo     | Descripción                                   |
|-------------------------|---------------------------|---------------------------------------------|-----------|-----------------------------------------------|
| Entradas de contabilidad de costes | SUM(Amount)               | CAMDATAAggregatedCostEntry                  | Importe    | Importe en divisa del libro mayor de contabilidad de costes. |
| Entradas estadísticas     | SUM(Magnitude)            | CAMDATAAggregatedStatisctialEntry           | Magnitud |                                               |

Se usará la tabla siguiente para mostrar cómo se usan las medidas agregadas clave para crear varias medidas calculadas en el conjunto de datos del contenido.

| Medida                                       | Cómo se calcula la medida                                                                                          |
|-----------------------------------------------|------------------------------------------------------------------------------------------------------------------------|
| Coste real                                   | CALCULATE('Entradas de contabilidad de costes'\[Medida\], 'Versiones de transacción'\[ISSOURCEVERSIONBUDGET\_VALUE\] = 0)            |
| Coste presupuestario                                   | CALCULATE('Entradas de contabilidad de costes'\[Medida\], 'Versiones de transacción'\[ISSOURCEVERSIONBUDGET\_VALUE\] = 1)            |
| Desviación del coste presupuestario                          | \[Coste presupuestario\] - \[Coste real\]                                                                                      |
| Porcentaje de desviación de presupuesto                    | IF(\[Coste presupuestario\] = 0, blank(), \[Desviación del presupuesto\] / \[Coste presupuestario\])                                                |
| Magnitud real                              | CALCULATE('Entradas estadísticas'\[Magnitud completa\], 'Versiones de transacción'\[ISSOURCEVERSIONBUDGET\_VALUE\] = 0)          |
| Magnitud de presupuesto                              | CALCULATE(\[Magnitud completa\], 'Versiones de transacción'\[ISSOURCEVERSIONBUDGET\_VALUE\] = 1)                               |
| Desviación de presupuesto estadística                   | \[Magnitud de presupuesto\] - \[Magnitud real\]                                                                            |
| Porcentaje de desviación de presupuesto estadístico        | IF(\[Magnitud de presupuesto\] = 0, blank(), \[Desvío de presupuesto estadístico\] / \[Magnitud de presupuesto\])                          |
| Índice de costes reales                              | IF(\[Magnitud real\] = 0, BLANK(), \[Coste real\] / \[Magnitud real\])                                          |
| Índice de coste de presupuesto                              | IF(\[Magnitud de presupuesto\] = 0, BLANK(), \[Coste presupuestario\] / \[Magnitud de presupuesto\])                                          |
| Desvío de índice del coste presupuestario                     | \[Índice de coste presupuestario\] - \[Índice de coste real\]                                                                            |
| Porcentaje de desvío de índice del coste presupuestario          | IF(\[Coste presupuestario\] = 0, blank(), \[Desviación de índice de coste del presupuesto\] / \[Índice de coste presupuestario\])                                 |
| Coste presupuestario fijo                             | CALCULATE(\[Coste presupuestario\], 'Entradas de contabilidad de costes'\[COSTBEHAVIOR\] = 1)                                              |
| Coste presupuestario variable                          | CALCULATE(\[Coste presupuestario\], 'Entradas de contabilidad de costes'\[COSTBEHAVIOR\] = 2)                                              |
| Coste presupuestario flexible fijo                    | \[Coste presupuestario fijo\]                                                                                                  |
| Coste presupuestario flexible variable                 | IF(\[Magnitud presupuestaria\] = 0, BLANK(), (\[Coste presupuestario variable\] / \[Magnitud de presupuesto\]) \* \[Magnitud real\])       |
| Coste presupuestario flexible                          | \[Coste presupuestario flexible fijo\] + \[Coste presupuestario flexible variable\]                                                     |
| Desviación de presupuesto flexible                      | \[Coste presupuestario flexible\] - \[Coste real\]                                                                             |
| Porcentaje de desviación de presupuesto flexible           | IF(\[Coste presupuestario flexible\] = 0, BLANK(), \[Desviación de presupuesto flexible\] / \[Coste presupuestario flexible\])                     |
| Índice de coste presupuestario flexible                     | IF(\[Magnitud real\] = 0, BLANK(), \[Coste presupuestario flexible\] / \[Magnitud real\])                                 |
| Desviación de índice del coste presupuestario flexible            | \[Índice de coste presupuestario flexible\] - \[Índice de coste real\]                                                                   |
| Porcentaje de desviación de índice del coste presupuestario flexible | IF(\[Índice de coste presupuestario flexible\] = 0, BLANK(), \[Desviación de índice de coste presupuestario flexible\] / \[Índice de coste presupuestario flexible\]) |

Las dimensiones clave siguientes se utilizan como filtros para cortar las medidas globales para lograr mayor granularidad y para proporcionar una visión analítica más profunda.

| Entidad                             | Ejemplos de atributos                                                                                               |
|------------------------------------|----------------------------------------------------------------------------------------------------------------------|
| Libros mayores de contabilidad de costes            | Libro mayor de contabilidad de costes                                                                                               |
| Unidades de control de costes                 | Nombre de unidad de control de costes                                                                                               |
| Dimensiones de elemento de coste            | Nombre de la dimensión de artículo de coste, Nombre de miembro de dimensión de artículo de coste, Descripción de miembro de dimensión de artículo de coste          |
| Dimensiones de objeto de coste             | Nombre de la dimensión de objeto de coste, Nombre de miembro de dimensión de objeto de coste, Descripción de miembro de dimensión de objeto de coste              |
| Dimensiones estadísticas             | Nombre de la dimensión estadística, Nombre de miembro de dimensión estadística, Descripción de miembro de dimensión estadística              |
| Jerarquías de dimensiones de objeto de coste  | Nombre de la jerarquía de dimensiones de objeto de coste, nivel de la jerarquía de dimensiones de objeto de coste, árbol de la jerarquía de dimensiones de objeto de coste    |
| Jerarquías de dimensión de elemento de coste | Nombre de la jerarquía de dimensiones de artículo de coste, nivel de la jerarquía de dimensiones de artículo de coste, árbol de la jerarquía de dimensiones de artículo de coste |
| Jerarquías de dimensión estadística  | Nombre de la jerarquía de dimensiones estadísticas, nivel de la jerarquía de dimensiones estadísticas, árbol de la jerarquía de dimensiones estadísticas    |
| Versiones de transacción               | Nombre de versión                                                                                                         |
| Calendarios fiscales                   | Calendario, descripción del calendario                                                                                       |
| Ejercicios                       | Año natural                                                                                                        |
| Períodos fiscales                     | Período del año natural                                                                                                 |

## <a name="additional-resources"></a>Recursos adicionales
Estos son algunos vínculos útiles relacionados con las entidades y la creación de contenido de Power BI:

-   [Entidades de datos](..\data-entities\data-entities.md)
-   [Creación de paquetes de contenido organizativo](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelado de datos con Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adición de iconos de Power BI a espacios de trabajo](configure-power-bi-integration.md)
-   [Configuración de seguridad del contenido de la contabilidad de costes de Power B](setup-security-cost-accounting-content-pack.md)


