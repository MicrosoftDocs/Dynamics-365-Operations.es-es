---
title: "Contenido de Power BI para Director de práctica"
description: "En este tema se describe lo que se incluye en el contenido de Power BI para Director de práctica. Explica cómo tener acceso a los informes que se incluyen en el contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido."
author: KimANelson
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations, UnifiedOperations
ms.assetid: 
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 99e5b5087cc72c01ff3e92d0b2b3a6279385eb19
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="practice-manager-power-bi-content"></a>Contenido de Power BI para Director de práctica

[!include[banner](../includes/banner.md)]

En este tema se describe lo que se incluye en el contenido de Microsoft Power BI para **Director de práctica**. Explica cómo obtener acceso a los informes de Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.

## <a name="overview"></a>Información general

El contenido de Power BI para **Director de práctica** se creó para los directores de práctica y los directores de proyecto. Proporciona métricas clave relacionadas con los proyectos en los que la organización está trabajando. El panel ofrece una visión general de los proyectos y los clientes relacionados. Se puede usar un filtro de informes para entidades jurídicas específicas. Este contenido de Power BI extrae datos de las medidas agregadas de contabilidad del proyecto.

El contenido en Power BI de **Director de práctica** contiene cinco páginas de informes: una página de visión general y cuatro páginas con detalles sobre costes de proyecto, ingresos, administración del valor acumulado y métricas de horas que se desglosan según varias dimensiones.

Todos los importes del contenido se muestran en la divisa del sistema. Puede establecer la divisa del sistema en la página **Parámetros del sistema** .

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI
Si utiliza Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (julio de 2017), el contenido en Power BI de **Director de prácticas** aparece en el espacio de trabajo **Administración de proyectos**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Informes que se incluyen en el contenido de Power BI

La siguiente tabla ofrece información sobre las métricas que se encuentran en cada página de informe en el contenido de Power BI de **Director de práctica** .

| Página de informes       | Métricas |
|-------------------|---------|
| Visión general de proyectos | <ul><li>Proyectos creados</li><li>Proyectos estimados</li><li>Proyectos en curso</li><li>Número de proyectos por etapa</li><li>Número de proyectos por ciudad</li><li>Ingresos reales por cliente</li><li>Margen bruto presupuestario por proyecto</li><li>Visión general de la administración del valor obtenido</li></ul> |
| Coste              | <ul><li>Comparación de coste real y coste presupuestado por mes</li><li>Comparación de coste real y coste presupuestado por año</li><li>Comparación de coste real y coste presupuestado por categoría</li><li>Coste real por tipo de transacción</li></ul> |
| Ingresos           | <ul><li>Ingresos reales por mes</li><li>Ingresos reales por código postal</li><li>Comparación de ingresos reales e ingresos presupuestados por categoría</li><li>Ingresos reales por sector del cliente</li></ul> |
| EVM               | Coste e índice de rendimiento de la programación por proyecto |
| Horas             | <ul><li>Comparación de horas facturables usadas reales, horas no facturables reales y horas presupuestadas</li><li>Comparación de horas facturables usadas reales y horas no facturables reales por proyecto</li><li>Comparación de horas facturables usadas reales y horas no facturables reales por recurso</li><li>Proporción de horas facturables reales por proyecto</li><li>Proporción de horas facturables reales por recurso</li></ul> |

Los gráficos y los iconos en todos estos informes se pueden filtrar y anclar al panel de información. Para obtener más información acerca de cómo filtrar y anclar en Power BI, consulte [Crear y configurar un panel de información](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). También puede usar la funcionalidad subyacente de exportación de datos para exportar los datos subyacente que se resume en una visualización.

## <a name="extending-the-power-bi-content"></a>Ampliar el contenido de Power BI
Mediante los paquetes de contenido disponibles en Microsoft Dynamics Lifecycle Services (LCS), puede ofrecer análisis muy buenos a las personas que no inician sesión en Microsoft Dynamics 365. Puede modificar estos paquetes de contenido para que incluyan otros informes o representaciones visuales y, a continuación, publicarlos en el inquilino de Power BI.com para su análisis. 

Puede encontrar el contenido en Power BI de **Director de prácticas** en la biblioteca de activos compartidos de LCS. Para obtener información sobre cómo descargar contenido e implementarlo en su organización, consulte [Contenido de Power BI en LCS en Microsoft y sus socios](power-bi-content-microsoft-partners.md). Para ver una demostración que muestra cómo implementar el contenido de Power BI, consulte [Contenido de Power BI de Microsoft y sus socios en Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) (Office Mix).

Asegúrese de descargar el contenido **Director de prácticas** que se aplica a la versión de Dynamics 365 que esté usando.

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades

Los datos siguientes se usan para rellenar las páginas de informes en el contenido de Power BI **Director de prácticas**. Estos datos se representan como medidas agregadas que se realizan en el almacén de la entidad. El almacén de la entidad es una base de datos de Microsoft SQL Server que se optimiza para el análisis. Para obtener más información, consulte [Visión general de la integración de Power BI con el almacén de entidades](power-bi-integration-entity-store.md).

En las secciones siguientes se describen las medidas de agregado que se utilizan en cada entidad.

### <a name="entity-projectaccountingcubeactualhourutilization"></a>Entidad: ProjectAccountingCube_ActualHourUtilization
**Origen de datos:** ProjEmplTrans

| Medida agregada clave      | Campo                              | Descripción | 
|--------------------------------|------------------------------------|-------------|
| Horas facturables usadas reales | Sum(ActualUtilizationBillableRate) | Total de horas facturables usadas reales. |
| Horas facturables/no facturables reales   | Sum(ActualBurdenBillableRate)      | Total de horas no facturables reales. |

### <a name="entity-projectaccountingcubeactuals"></a>Entidad: ProjectAccountingCube_Actuals
**Origen de datos:** ProjTransPosting

| Medida agregada clave | Campo              | Descripción | 
|---------------------------|--------------------|-------------|
| Ingresos reales            | Sum(ActualRevenue) | Total de ingresos registrados para todas las transacciones. |   
| Coste real               | Sum(ActualCost)    | Total de costes registrados para todos los tipos de transacciones. |

### <a name="entity-projectaccountingcubecustomer"></a>Entidad: ProjectAccountingCube_Customer
**Origen de datos:** CustTable

| Medida agregada clave | Campo                                            | Descripción | 
|---------------------------|--------------------------------------------------|-------------|
| Número de proyectos        | COUNTA(ProjectAccountingCube_Projects[PROJECTS]) | Número de proyectos disponibles. |


### <a name="entity-projectaccountingcubeforecasts"></a>Entidad: ProjectAccountingCube_Forecasts
**Origen de datos:** ProjTransBudget

| Medida agregada clave | Campo                  | Descripción | 
|---------------------------|------------------------|-------------|
| Coste presupuestario               | Sum(BudgetCost)        | Total de costes previstos para todos los tipos de transacciones. |
| Ingresos presupuestarios            | Sum(BudgetRevenue)     | Total de ingresos acumulados/facturados previstos.  |
| Margen bruto presupuestario       | Sum(BudgetGrossMargin) | Diferencia entre la suma de ingresos totales previstos y la suma de costes totales previstos. |

### <a name="entity-projectaccountingcubeprojectplancostsview"></a>Entidad: ProjectAccountingCube_ProjectPlanCostsView
**Origen de datos:** Project

| Medida agregada clave | Campo                    | Descripción | 
|---------------------------|--------------------------|-------------|
| Costes planificados              | Sum(SumOfTotalCostPrice) | Precio de coste total en las estimaciones de todos los tipos de transacciones de proyecto que cuentan con tareas planificadas. |

### <a name="entity-projectaccountingcubeprojects"></a>Entidad: ProjectAccountingCube_Projects
**Origen de datos:** Project

| Medida agregada clave    | Campo | Descripción | 
|------------------------------|-------|-------------|
| Índice de rendimiento de costes       | ProjectAccountingCube_Projects[Valor obtenido] / ProjectAccountingCube_Projects[Coste real total de las tareas completadas] | Cálculo del valor obtenido total dividido por el coste real total. |
| Índice de rendimiento de la programación   | ProjectAccountingCube_Projects[Valor obtenido] / ProjectAccountingCube_Projects[Coste planificado total de las tareas completadas] | Cálculo del valor obtenido total dividido por el coste planificado total. |
| Porcentaje de trabajo completado | Porcentaje de trabajo completado = [ProjectAccountingCube_Projects[Coste real total de las tareas completadas] / (ProjectAccountingCube_Projects[Coste real total de tareas completadas] + ProjectAccountingCube_Projects[Coste planificado total del proyecto] - ProjectAccountingCube_Projects[Coste planificado total de tareas completadas]) | Porcentaje total de trabajo completado basado en el coste real total de tareas completadas y el coste planificado del proyecto. |
| Proporción de horas facturables reales  | ProjectAccountingCube_Projects[Horas utilizadas facturables reales totales del proyecto] / (ProjectAccountingCube_Projects[Horas utilizadas facturables reales totales del proyecto] + ProjectAccountingCube_Projects[Horas no facturables reales totales del proyecto]) | Horas facturables totales reales, en función de las horas usadas y las horas no facturables. |
| Valor obtenido                 | ProjectAccountingCube_Projects[Coste planificado total del proyecto] * ProjectAccountingCube_Projects[Porcentaje de trabajo completado] | Coste planificado total multiplicado por el porcentaje de trabajo completado. |

### <a name="entity-projectaccountingcubetotalestimatedcosts"></a>Entidad: ProjectAccountingCube_TotalEstimatedCosts 
**Origen de datos:** ProjTable

| Medida agregada clave       | Campo               | Descripción | 
|---------------------------------|---------------------|-------------|
| Coste de la actividad planificada completada | Sum(TotalCostPrice) | Precio de coste total en las estimaciones de todos los tipos de transacciones de proyecto que cuentan con tareas completadas. |

