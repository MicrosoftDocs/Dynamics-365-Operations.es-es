---
title: Contenido de Power BI de rendimiento de producción
description: Este tema describe lo que se incluye en el contenido de Power BI sobre Rendimiento de la producción.
author: AndersGirke
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: ProductionPerformancePowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: c815a2e37f9882d695bf170a806301a3145d0f06
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5094221"
---
# <a name="production-performance-power-bi-content"></a>Contenido de Power BI de rendimiento de producción

[!include [banner](../includes/banner.md)]

Este tema describe lo que se incluye en el contenido de Microsoft Power BI sobre **Rendimiento de la producción**. Explica cómo obtener acceso a los informes Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.

## <a name="overview"></a>Información general

El contenido de Power BI sobre **Rendimiento de la producción** es para directores de producción o personas de la organización responsables del control de producción.

Los informes que se incluyen le permiten usar Power BI para controlar el rendimiento de las operaciones de fabricación en relación con la ejecución, la calidad y el coste oportunos. Los informes utilizan datos transaccionales de pedidos de producción y de lotes, y proporcionan tanto una vista global de medidas empresariales de la producción y un desglose de medidas por producto y recurso.

El contenido de Power BI destaca la capacidad de la organización para completar la producción a tiempo y completamente. El rendimiento futuro se proyecta en función de los planes de producción. Los informes completos proporcionan conocimientos detallados de los defectos de los productos causados por la producción, así como del índice de defectos para recursos y operaciones.

Este contenido de Power BI también le permite analizar las desviaciones de producción. Las desviaciones de producción se calculan como la diferencia entre el coste estimado y el coste realizado. Las desviaciones de producción se calculan cuando los pedidos de producción o los pedidos de lote alcanzan el estado **Terminado** .

El contenido de Power BI sobre **Rendimiento de la producción** incluye datos procedentes de pedidos de producción y de pedidos de lote. Los informes no incluyen datos relacionados con las producciones de kanban.

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI
El contenido de Power BI **Rendimiento de producción** se muestra en la página **Rendimiento de producción** (**Control de producción** \> **Consultas e informes** \> **Análisis de rendimiento de producción** \> **Rendimiento de producción**). 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Métricas que se incluyen en el contenido de Power BI

El contenido de Power BI sobre **Rendimiento de la producción** incluye un conjunto de páginas de informes. Cada página consta de un conjunto de métricas que se visualizan como gráficos, mosaicos y tablas.

La tabla siguiente proporciona información general de las visualizaciones que se incluyen.

| Página de informes                                | Gráficos | Mosaicos |
|--------------------------------------------|--------|-------|
| Rendimiento de producción                     | <ul><li>Número de producción por fecha</li><li>Número de producciones por producto y grupo de artículos</li><li>Número de producciones planificadas por fecha</li><li>10 últimos productos por puntualidad &amp; completitud</li></ul> | <ul><li>Total de pedidos</li><li>% Puntuales &amp; completados</li><li>Porcentaje de incompletos</li><li>Porcentaje de finalizados con antelación</li><li>Porcentaje de finalizados con retraso</li></ul> |
| Defectos por producto                         | <ul><li>Tasa de defectos (ppm) por fecha</li><li>Tasa de defectos (ppm) por producto y grupo de artículos</li><li>Cantidad producida por fecha</li><li>10 primeros productos por tasa de defectos</li></ul> | <ul><li>Tasa de defectos (ppm)</li><li>Cantidad defectuosa</li><li>Cantidad total</li></ul> |
| Tendencia de defectos por producto                   | Tasa de defectos (ppm) por cantidad producida | Tasa de defectos (ppm) |
| Defectos por recurso                        | <ul><li>Tasa de defectos (ppm) por fecha</li><li>Tasa de defectos (ppm) por recurso y ubicación</li><li>Tasa de defectos (ppm) por operación</li><li>10 primeros recursos por tasa de defectos</li></ul> | Cantidad defectuosa |
| Tendencia de defectos por recurso                  | Tasa de defectos (ppm) por cantidad procesada | |
| Desviaciones de producción para gestión de costes de órdenes de producción | <ul><li>Desviación de producción por fecha y tipo de grupo de costes</li><li>Desviación de producción por ubicación y tipo de grupo de costes</li><li>10 primeros productos con desviación de producción desfavorable</li><li>10 primeros con desviación de producción desfavorable por recurso</li></ul> | <ul><li>Coste realizado</li><li>Desviación de producción</li><li>Porcentaje de desviación de producción</li></ul> |


## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades

Los datos siguientes se usan para las páginas de informes en el contenido de Power BI sobre **Rendimiento de la producción**. Estos datos se representan como medidas agregadas que se realizan en el almacén de la entidad. El almacén de la entidad es una base de datos de Microsoft SQL Server que se optimiza para el análisis. Para obtener más información acerca del almacén de entidades, consulte Integración de [Power BI con el almacén de entidades](power-bi-integration-entity-store.md).

La tabla siguiente muestra las medidas agregadas clave que se usan como base del contenido de Power BI.

| Entidad                   | Medidas agregadas clave  | Origen de datos para aplicaciones Finance and Operations | Campo              |
|--------------------------|-----------------------------|----------------------------------------|--------------------|
| CostCalculation          | CostAmount                  | ProdCalcTransExpanded                  | CostAmount         |
| CostCalculation          | CostMarkup                  | ProdCalcTransExpanded                  | CostMarkup         |
| CostCalculation          | ActualCostAmount            | ProdCalcTransExpanded                  | RealCostAmount     |
| CostCalculation          | RealCostAdjustment          | ProdCalcTransExpanded                  | RealCostAdjustment |
| RouteTransactions        | ErrorQuantity               | ProdRouteTransExpanded                 | QtyError           |
| RouteTransactions        | GoodQuantity                | ProdRouteTransExpanded                 | QtyGood            |
| ProductionOrder          | DaysDelayed                 | ProdTableExpanded                      | DaysDelayed        |
| ProductionOrder          | LeadTime                    | ProdTableExpanded                      | LeadTime           |
| ProductionOrder          | PlannedLeadTime             | ProdTableExpanded                      | PlannedLeadTime    |
| ProductionOrder          | ProductionOrderCount        | ProdTableExpanded                      |                    |
| CoproductCostCalculation | CoproductCostAmount         | PmfCoByProdCalcTransExpanded           | CostAmount         |
| CoproductCostCalculation | CoproductCostMarkup         | PmfCoByProdCalcTransExpanded           | CostMarkup         |
| CoproductCostCalculation | CoproductRealCostAdjustment | PmfCoByProdCalcTransExpanded           | RealCostAdjustment |
| CoproductCostCalculation | CoproductActualCostAmount   | PmfCoByProdCalcTransExpanded           | RealCostAmount     |

Se usará la tabla siguiente para mostrar cómo se usan las medidas agregadas clave para crear varias medidas calculadas en el conjunto de datos del contenido.

| Medida                  | Cómo se calcula la medida |
|--------------------------|-------------------------------|
| Desviación de la producción, en %   | SUM('Desviación de la producción'\[Desviación de la producción\]) / SUM('Desviación de la producción'\[Coste estimado\]) |
| Todos los pedidos planificados       | COUNTROWS('Pedido de producción planificado') |
| Con antelación                    | COUNTROWS(FILTER('Pedido de producción planificado', 'Pedido de producción planificado'\[Fecha final programada\] \< 'Pedido de producción planificado'\[Fecha de requisito\])) |
| Con retraso                     | COUNTROWS(FILTER('Pedido de producción planificado', 'Pedido de producción planificado'\[Fecha final programada\] \> 'Pedido de producción planificado'\[Fecha de requisito\])) |
| Puntual                  | COUNTROWS(FILTER('Pedido de producción planificado', 'Pedido de producción planificado'\[Fecha final programada\] = 'Pedido de producción planificado'\[Fecha de requisito\])) |
| Porcentaje de puntuales                | IF ( 'Pedido de producción planificado'\[Puntual\] \<\> 0, 'Pedido de producción planificado'\[Puntual\], IF ('Pedido de producción planificado'\[Todos los pedidos planificados\] \<\> 0, 0, BLANK()) ) / 'Pedido de producción planificado'\[Todos los pedidos planificados\] |
| Completados                | COUNTROWS(FILTER('Pedido de producción', 'Pedido de producción'\[Notificado como terminado\] = TRUE)) |
| Tasa de defectos (ppm)     | SI( 'Pedido de producción'\[Cantidad total\] = 0, BLANK(), (SUM('Pedido de producción'\[Cantidad defectuosa\]) / 'Pedido de producción'\[Cantidad total\]) \* 1000000) |
| Tasa de producción retrasada  | 'Pedido de producción'\[Retrasado \#\] / 'Pedido de producción'\[Completado\] |
| Con antelación y completados          | COUNTROWS(FILTER('Pedido de producción', 'Pedido de producción'\[Completado\] = TRUE && 'Pedido de producción'\[Con antelación\] = TRUE)) |
| Con antelación \#                 | COUNTROWS(FILTER('Pedido de producción', 'Pedido de producción'\[Con antelación\] = TRUE)) |
| Porcentaje de finalizados con antelación                  | IFERROR( IF('Pedido de producción'\[Con antelación \#\] \<\> 0, 'Pedido de producción'\[Con antelación \#\], IF('Pedido de producción'\[Total de pedidos\] = 0, BLANK(), 0)) / 'Pedido de producción'\[Total de pedidos\], BLANK()) |
| Incompleto               | COUNTROWS(FILTER('Pedido de producción', 'Pedido de producción'\[Completado\] = FALSE && 'Pedido de producción'\[Notificado como terminado\] = TRUE)) |
| Porcentaje de incompletos             | IFERROR( IF('Pedido de producción'\[Incompleto\] \<\> 0, 'Pedido de producción'\[Incompleto\], IF('Pedido de producción'\[Total de pedidos\] = 0, BLANK(), 0)) / 'Pedido de producción'\[Total de pedidos\], BLANK()) |
| Se retrasa               | 'Pedido de producción'\[Notificado como terminado\] = TRUE && 'Pedido de producción'\[Valor de retrasado\] = 1 |
| Con antelación                 | 'Pedido de producción'\[Notificado como terminado\] = TRUE && 'Pedido de producción'\[Días de retraso\] \< 0 |
| Completado               | 'Pedido de producción'\[Buena cantidad\] \>= 'Pedido de producción'\[Cantidad programada\] |
| Notificado como terminado                | 'Pedido de producción'\[Valor de estado de producción\] = 5 \|\| 'Pedido de producción'\[Valor de estado de producción\] = 7 |
| Tarde y completo           | COUNTROWS(FILTER('Pedido de producción', 'Pedido de producción'\[Completado\] = TRUE && 'Pedido de producción'\[Con retraso\] = TRUE)) |
| Cetraso \#                  | COUNTROWS(FILTER('Pedido de producción', 'Pedido de producción'\[Con retraso\] = TRUE)) |
| Porcentaje de finalizados con retraso                   | IFERROR( IF('Pedido de producción'\[Con retraso \#\] \<\> 0, 'Pedido de producción'\[Con retraso \#\], IF('Pedido de producción'\[Total de pedidos\] = 0, BLANK(), 0)) / 'Pedido de producción'\[Total de pedidos\], BLANK()) |
| Puntuales y completados        | COUNTROWS(FILTER('Pedido de producción', 'Pedido de producción'\[Completado\] = TRUE && 'Pedido de producción'\[Con retraso\] = FALSE && 'Pedido de producción'\[Con antelación\] = FALSE)) |
| Porcentaje de puntuales y completados      | IFERROR( IF('Pedido de producción'\[Puntual y completo\] \<\> 0, 'Pedido de producción'\[Puntual y completo\], IF('Pedido de producción'\[Completo\] = 0, BLANK(), 0)) / 'Pedido de producción'\[Completo\], BLANK()) |
| Total de pedidos             | COUNTROWS('Pedido de producción') |
| Cantidad total           | SUM('Pedido de producción'\[Cantidad sin errores\]) + SUM('Pedido de producción'\[Cantidad defectuosa\]) |
| Tasa de defectos (ppm)        | IF( 'Transacciones de ruta'\[Cantidad procesada\] = 0, BLANK(), (SUM('Transacciones de ruta'\[Cantidad defectuosa\]) / 'Transacciones de ruta'\[Cantidad procesada\]) \* 1000000) |
| Proporción defectuosa mezclada (ppm) | IF( 'Transacciones de ruta'\[Total de cantidad mezclada\] = 0, BLANK(), (SUM('Transacciones de ruta'\[Cantidad defectuosa\]) / 'Transacciones de ruta'\[Total de cantidad mezclada\]) \* 1000000) |
| Cantidad procesada       | SUM('Transacciones de ruta'\[Cantidad sin errores\]) + SUM('Transacciones de ruta'\[Cantidad defectuosa\]) |
| Total de cantidad mezclada     | SUM('Pedido de producción'\[Cantidad sin errores\]) + SUM('Transacciones de ruta'\[Cantidad defectuosa\]) |

Las tabla siguiente muestra las dimensiones clave que se utilizan como filtros para cortar las medidas globales de forma que logre mayor granularidad y profundizar en la visión analítica.

| Entidad                    | Ejemplos de atributos                                        |
|---------------------------|---------------------------------------------------------------|
| Notificado como fecha finalizada | Fecha de finalización (notificada como terminada), contrapartida mensual y anual                 |
| Fecha de finalización                | Contrapartida mensual terminada y mes                                  |
| Fecha de requisito          | Contrapartida mensual de fecha de requisito y fecha de requisito            |
| Fecha de transacción de ruta    | Contrapartida mensual de transacción de ruta y fecha                       |
| Sitios                     | Identificador de sitios, nombre del sitio, estado y localidad                          |
| Entidades                  | Identificador y nombre                                                   |
| Recursos                 | Identificador de recurso, nombre de recurso, tipo de recurso y grupo de recursos |
| Productos                  | Número de producto, nombre de producto, identificador de artículo y grupo de artículos         |


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]