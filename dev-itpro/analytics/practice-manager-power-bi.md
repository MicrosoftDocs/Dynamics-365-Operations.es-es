---
title: "Contenido de Power BI para Director de práctica"
description: "En este tema se describe lo que se incluye en el contenido de Power BI para Director de práctica. Explica cómo tener acceso a los informes que se incluyen en el paquete de contenido, y proporciona información acerca del modelo de datos y las entidades que se usan para generar el paquete del contenido."
author: knelson
manager: AnnBe
ms.date: 04/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Developer/IT Pro
ms.assetid: 
ms.search.region: Global
ms.author: knelson
ms.dyn365.intro: 2017/04/27
ms.dyn365.version: 
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 0f2a1a9df8e5036c60b74b8a710e606b0b1e312a
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017


---

# <a name="practice-manager-power-bi-content"></a>Contenido de Power BI para Director de práctica

[!include[banner](../includes/banner.md)]


En este tema se describe lo que se incluye en el contenido de Microsoft Power BI para **Director de práctica**. Explica cómo obtener acceso a los informes de Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.

## <a name="overview"></a>Información general

El contenido de Power BI para **Director de práctica** se creó para los directores de práctica y los directores de proyecto. Proporciona métricas clave relacionadas con los proyectos en los que la organización está trabajando. El panel ofrece una visión general de los proyectos y los clientes relacionados. Se puede usar un filtro de informes para entidades jurídicas específicas. Este contenido de Power BI extrae datos de las medidas de agregado de contabilidad de proyecto para Microsoft Dynamics 365 for Operations.

El contenido de Power BI para **Director de práctica** contiene cinco páginas de informes: una página de visión general y cuatro páginas con detalles de costes de proyecto, ingresos, administración del valor acumulado y métricas de horas que se analizan según varias dimensiones.

Todos los importes del contenido se muestran en la divisa del sistema. Puede establecer la divisa del sistema en la página **Parámetros del sistema** .

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI

El contenido de Power BI para **Director de práctica** se encuentra en la biblioteca de activos compartidos de Microsoft Dynamics Lifecycle Services (LCS). Para obtener más información sobre cómo descargar el paquete de contenido y conectarlo a los datos de Dynamics 365 for Operations, consulte [Contenido de Power BI en LCS de Microsoft y sus socios](power-bi-content-microsoft-partners.md).

Para ver una demostración que muestra cómo implementar el contenido de Power BI, consulte [Contenido de Power BI de Microsoft y sus socios en Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) (Office mix).

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Informes que se incluyen en el contenido de Power BI

La siguiente tabla ofrece información sobre las métricas que se encuentran en cada página de informe en el contenido de Power BI de **Director de práctica** .

| Página de informes                                          | Métricas               |
|------------------------------------------------------|-----------------------------------------------|
| Panel de información  | Proyectos creados<br>Proyectos estimados<br>Proyectos en curso<br>Número de proyectos por etapa<br>Número de proyectos por ciudad<br>Ingresos reales por cliente<br>Margen bruto presupuestario por proyecto<br>Visión general de la administración del valor obtenido |
| Coste                                                 | Comparación de coste real y coste presupuestado por mes<br>Comparación de coste real y coste presupuestado por año<br>Comparación de coste real y coste presupuestado por categoría<br>Coste real por tipo de transacción       |
| Ingresos                                              | Ingresos reales por mes<br>Ingresos reales por código postal<br>Comparación de ingresos reales e ingresos presupuestados por categoría<br>Ingresos reales por sector del cliente        |
| EVM                                                  | Coste e índice de rendimiento de la programación por proyecto                 |
| Horas                                                | Comparación de horas facturables usadas reales, horas no facturables reales y horas presupuestadas<br>Comparación de horas facturables usadas reales y horas no facturables reales por proyecto<br>Comparación de horas facturables usadas reales y horas no facturables reales por recurso<br>Proporción de horas facturables reales por proyecto<br>Proporción de horas facturables reales por recurso |

Los gráficos y los iconos en todos estos informes se pueden filtrar y anclar al panel de información. Para obtener más información acerca de cómo filtrar y anclar en Power BI, consulte [Crear y configurar un panel de información](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). También puede usar la funcionalidad subyacente de exportación de datos para exportar los datos subyacente que se resume en una visualización.

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades

Los datos de Dynamics 365 for Operations se usan para rellenar las páginas de informes en el contenido de **Director de práctica**. Estos datos se representan como medidas globales que se realizan en el almacén de la entidad, que es una base de datos de Microsoft SQL que se optimiza para análisis. Para obtener más información, consulte [Visión general de la integración de Power BI con el almacén de entidades](power-bi-integration-entity-store.md).

En las secciones siguientes se describen las medidas de agregado que se utilizan en cada entidad.

### <a name="entity-projectaccountingcubeactualhourutilization"></a>Entidad: ProjectAccountingCube_ActualHourUtilization
**Origen de datos**: ProjEmplTrans

| Medida agregada clave                | Campo                                | Descripción                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
| ActualBillableUtilizedHours              | Sum(ActualUtilizationBillableRate)   | Total de horas facturables usadas reales |
| ActualBillableBurdenHours                | Sum(ActualBurdenBillableRate)        | Total de horas no facturables reales             |

### <a name="entity-projectaccountingcubeactuals"></a>Entidad: ProjectAccountingCube_Actuals
**Origen de datos**: ProjTransPosting

| Medida agregada clave                | Campo                                | Descripción                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
| ActualRevenue                            |     Sum(ActualRevenue)               |  Total de ingresos registrados para toda la transacción |   
| ActualCost   |                             Sum(ActualCost)           |    Total de costes registrados para todos los tipos de transacciones    |

### <a name="entity-projectaccountingcubecustomer"></a>Entidad: ProjectAccountingCube_Customer
**Origen de datos**: CustTable

| Medida agregada clave                | Campo                                | Descripción                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|    Número de proyectos        |   COUNTA(ProjectAccountingCube_Projects[PROJECTS])       |         Número de proyectos disponibles    |


### <a name="entity-projectaccountingcubeforecasts"></a>Entidad: ProjectAccountingCube_Forecasts
**Origen de datos**: ProjTransBudget

| Medida agregada clave                | Campo                                | Descripción                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|    BudgetCost    |       Sum(BudgetCost)  |       Total de costes previstos para todos los tipos de transacciones     |
|     BudgetRevenue    |         Sum(BudgetRevenue)    |    Total de ingresos acumulados/facturados previstos         |
|BudgetGrossMargin | Sum(BudgetGrossMargin) |Diferencia entre la suma de ingresos totales previstos y la suma de costes totales previstos

### <a name="entity-projectaccountingcubeprojectplancostsview"></a>Entidad: ProjectAccountingCube_ProjectPlanCostsView
**Origen de datos**: Project

| Medida agregada clave                | Campo                                | Descripción                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|      PlannedCost      |        Sum(SumOfTotalCostPrice)   | Precio de coste total en las estimaciones de todos los tipos de transacciones de proyecto con tareas planificadas |

### <a name="entity-projectaccountingcubeprojects"></a>Entidad: ProjectAccountingCube_Projects
**Origen de datos**: Project

| Medida agregada clave                | Campo                                | Descripción                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
|   Índice de rendimiento de costes  |ProjectAccountingCube_Projects[Valor obtenido] / ProjectAccountingCube_Projects[Coste real total de las tareas completadas] |     Cálculo del valor obtenido total dividido por el coste real total|
|  Índice de rendimiento de la programación |ProjectAccountingCube_Projects[Valor obtenido] / ProjectAccountingCube_Projects[Coste planificado total de las tareas completadas]|Cálculo del valor obtenido total dividido por el coste planificado total |
|Porcentaje de trabajo completado |Porcentaje de trabajo completado = [ProjectAccountingCube_Projects[Coste real total de las tareas completadas] / (ProjectAccountingCube_Projects[Coste real total de tareas completadas] + ProjectAccountingCube_Projects[Coste planificado total del proyecto] - ProjectAccountingCube_Projects[Coste planificado total de tareas completadas])|Porcentaje total de trabajo completado basado en el coste real total de tareas completadas y el coste planificado del proyecto|
|Proporción de horas facturables reales del proyecto|ProjectAccountingCube_Projects[Horas utilizadas facturables reales totales del proyecto] / (ProjectAccountingCube_Projects[Horas utilizadas facturables reales totales del proyecto] + ProjectAccountingCube_Projects[Horas no facturables reales totales del proyecto])|Horas facturables reales totales basadas en horas utilizadas + horas no facturables|
|Valor obtenido|ProjectAccountingCube_Projects[Coste planificado total del proyecto] * ProjectAccountingCube_Projects[Porcentaje de trabajo completado]|Coste planificado total multiplicado por el porcentaje de trabajo completado|

### <a name="entity-projectaccountingcubetotalestimatedcosts"></a>Entidad: ProjectAccountingCube_TotalEstimatedCosts 
**Origen de datos**: ProjTable

| Medida agregada clave                | Campo                                | Descripción                            | 
|------------------------------------------|--------------------------------------|----------------------------------------|
| CompletedActivityPlannedCost  |  Sum(TotalCostPrice)  |   Precio de coste total en las estimaciones de todos los tipos de transacciones de proyecto con tareas completadas|

## <a name="additional-resources"></a>Recursos adicionales

Estos son algunos vínculos útiles relacionados con las entidades y la creación de contenido de Power BI:

- [Entidades de datos](/dynamics365/operations/dev-itpro/data-entities/data-entities)
- [Creación de paquetes de contenido organizativo](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
- [Modelado de datos con Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
- [Configuración de la integración de Power BI para espacios de trabajo](configure-power-bi-integration.md)

