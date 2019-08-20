---
title: Contenido de director de prácticas de Power BI
description: En este tema se describe lo que se incluye en el contenido de Power BI para Director de práctica. Explica cómo tener acceso a los informes que se incluyen en el contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.
author: KimANelson
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ProjManagementWorkspace
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: c526bc42595c20024016d0d7da78b8638b0daa4b
ms.sourcegitcommit: 16bfa0fd08feec1647829630401ce62ce2ffa1a4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/02/2019
ms.locfileid: "1850106"
---
# <a name="practice-manager-power-bi-content"></a>Contenido de director de prácticas de Power BI

[!include [banner](../includes/banner.md)]

En este tema se describe lo que se incluye en el contenido de Microsoft Power BI para **Director de práctica**. Explica cómo obtener acceso a los informes de Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.

## <a name="overview"></a>Información general

El contenido de Power BI para **Director de práctica** se creó para los directores de práctica y los directores de proyecto. Proporciona métricas clave relacionadas con los proyectos en los que la organización está trabajando. El panel ofrece una visión general de los proyectos y los clientes relacionados. Se puede usar un filtro de informes para entidades jurídicas específicas. Este contenido de Power BI extrae datos de las medidas agregadas de contabilidad del proyecto.

El contenido en Power BI de **Director de práctica** contiene cinco páginas de informes: una página de visión general y cuatro páginas con detalles sobre costes de proyecto, ingresos, administración del valor acumulado y métricas de horas que se desglosan según varias dimensiones.

Todos los importes del contenido se muestran en la divisa del sistema. Puede establecer la divisa del sistema en la página **Parámetros del sistema** .

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI

El contenido de Power BI **Director de prácticas** se muestra en el área de trabajo **Administración de proyectos**.

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Informes que se incluyen en el contenido de Power BI

La siguiente tabla ofrece información sobre las métricas que se encuentran en cada página de informe en el contenido de Power BI de **Director de práctica**.

| Página de informes       | Métricas |
|-------------------|---------|
| Visión general de proyectos | <ul><li>Proyectos creados</li><li>Proyectos estimados</li><li>Proyectos en curso</li><li>Ingresos reales por cliente</li><li>Margen bruto presupuestario por proyecto</li><li>Visión general de la administración del valor obtenido</li></ul> |
| Coste              | <ul><li>Comparación de coste real y coste presupuestado por mes</li><li>Comparación de coste real y coste presupuestado por año</li><li>Comparación de coste real y coste presupuestado por categoría</li><li>Coste real por tipo de transacción</li></ul> |
| Ingresos           | <ul><li>Ingresos reales por mes</li><li>Ingresos reales por código postal</li><li>Comparación de ingresos reales e ingresos presupuestados por categoría</li><li>Ingresos reales por sector del cliente</li></ul> |
| EVM               | Coste e índice de rendimiento de la programación por proyecto |
| Horas             | <ul><li>Comparación de horas facturables usadas reales, horas no facturables reales y horas presupuestadas</li><li>Comparación de horas facturables usadas reales y horas no facturables reales por proyecto</li><li>Comparación de horas facturables usadas reales y horas no facturables reales por recurso</li><li>Proporción de horas facturables reales por proyecto</li><li>Proporción de horas facturables reales por recurso</li></ul> |

Los gráficos y los iconos en todos estos informes se pueden filtrar y anclar al panel de información. Para obtener más información acerca de cómo filtrar y anclar en Power BI, consulte [Crear y configurar un panel de información](https://powerbi.microsoft.com/guided-learning/powerbi-learning-4-2-create-configure-dashboards/). También puede usar la funcionalidad subyacente de exportación de datos para exportar los datos subyacente que se resume en una visualización.

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades

Los datos siguientes se usan para rellenar las páginas de informes en el contenido de Power BI **Director de prácticas**. Estos datos se representan como medidas agregadas que se realizan en el almacén de la entidad. El almacén de la entidad es una base de datos de Microsoft SQL Server que se optimiza para el análisis. Para obtener más información, consulte [Visión general de la integración de Power BI con el almacén de entidades](power-bi-integration-entity-store.md).

En las secciones siguientes se describen las medidas de agregado que se utilizan en cada entidad.

### <a name="entity-projectaccountingcube_actualhourutilization"></a>Entidad: ProjectAccountingCube\_ActualHourUtilization
**Origen de datos:** ProjEmplTrans

| Medida agregada clave      | Campo                              | Descripción |
|--------------------------------|------------------------------------|-------------|
| Horas facturables usadas reales | Sum(ActualUtilizationBillableRate) | Total de horas facturables usadas reales. |
| Horas facturables/no facturables reales   | Sum(ActualBurdenBillableRate)      | Total de horas no facturables reales. |

### <a name="entity-projectaccountingcube_actuals"></a>Entidad: ProjectAccountingCube\_Actuals
**Origen de datos:** ProjTransPosting

| Medida agregada clave | Campo              | Descripción |
|---------------------------|--------------------|-------------|
| Ingresos reales            | Sum(ActualRevenue) | Total de ingresos registrados para todas las transacciones. |
| Coste real               | Sum(ActualCost)    | Total de costes registrados para todos los tipos de transacciones. |

### <a name="entity-projectaccountingcube_customer"></a>Entidad: ProjectAccountingCube\_Customer
**Origen de datos:** CustTable

| Medida agregada clave | Campo                                             | Descripción |
|---------------------------|---------------------------------------------------|-------------|
| Número de proyectos        | COUNTA(ProjectAccountingCube\_Projects\[PROJECTS\]) | Número de proyectos disponibles. |

### <a name="entity-projectaccountingcube_forecasts"></a>Entidad: ProjectAccountingCube\_Forecasts
**Origen de datos:** ProjTransBudget

| Medida agregada clave | Campo                  | Descripción |
|---------------------------|------------------------|-------------|
| Coste presupuestario               | Sum(BudgetCost)        | Total de costes previstos para todos los tipos de transacciones. |
| Ingresos presupuestarios            | Sum(BudgetRevenue)     | Total de ingresos acumulados/facturados previstos. |
| Margen bruto presupuestario       | Sum(BudgetGrossMargin) | Diferencia entre la suma de ingresos totales previstos y la suma de costes totales previstos. |

### <a name="entity-projectaccountingcube_projectplancostsview"></a>Entidad: ProjectAccountingCube\_ProjectPlanCostsView
**Origen de datos:** Project

| Medida agregada clave | Campo                    | Descripción |
|---------------------------|--------------------------|-------------|
| Costes planificados              | Sum(SumOfTotalCostPrice) | Precio de coste total en las estimaciones de todos los tipos de transacciones de proyecto que cuentan con tareas planificadas. |

### <a name="entity-projectaccountingcube_projects"></a>Entidad: ProjectAccountingCube\_Projects
**Origen de datos:** Project

| Medida agregada clave    | Campo | Descripción |
|------------------------------|-------|-------------|
| Índice de rendimiento de costes       | ProjectAccountingCube\_Projects\[Valor obtenido\] ÷ ProjectAccountingCube\_Projects\[Coste real total de las tareas completadas\] | Cálculo del valor obtenido total dividido por el coste real total. |
| Índice de rendimiento de la programación   | ProjectAccountingCube\_Projects\[Valor obtenido\] ÷ ProjectAccountingCube\_Projects\[Coste planificado total de las tareas completadas\] | Cálculo del valor obtenido total dividido por el coste planificado total. |
| Porcentaje de trabajo completado | Porcentaje de trabajo completado = ProjectAccountingCube\_Projects\[Coste real total de las tareas completadas\] ÷ (ProjectAccountingCube\_Projects\[Coste real total de tareas completadas\] + ProjectAccountingCube\_Projects\[Coste planificado total del proyecto\] - – ProjectAccountingCube\_Projects\[Coste planificado total de tareas completadas\]) | Porcentaje total de trabajo completado basado en el coste real total de tareas completadas y el coste planificado del proyecto. |
| Proporción de horas facturables reales  | ProjectAccountingCube\_Projects\[Horas utilizadas facturables reales totales del proyecto\] ÷ (ProjectAccountingCube\_Projects\[Horas utilizadas facturables reales totales del proyecto\] + ProjectAccountingCube\_Projects\[Horas no facturables reales totales del proyecto\]) | Horas facturables totales reales, en función de las horas usadas y las horas no facturables. |
| Valor obtenido                 | ProjectAccountingCube\_Projects\[Coste planificado total del proyecto\] × ProjectAccountingCube\_Projects\[Porcentaje de trabajo completado\] | Coste planificado total multiplicado por el porcentaje de trabajo completado. |

### <a name="entity-projectaccountingcube_totalestimatedcosts"></a>Entidad: ProjectAccountingCube\_TotalEstimatedCosts 
**Origen de datos:** ProjTable

| Medida agregada clave       | Campo               | Descripción |
|---------------------------------|---------------------|-------------|
| Coste de la actividad planificada completada | Sum(TotalCostPrice) | Precio de coste total en las estimaciones de todos los tipos de transacciones de proyecto que cuentan con tareas completadas. |
