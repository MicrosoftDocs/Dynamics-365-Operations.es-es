---
title: Contenido de gestión de costes de Power BI
description: Este tema describe lo que se incluye en el contenido de gestión de costes en Power BI.
author: ShylaThompson
manager: AnnBe
ms.date: 03/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: CostAdminWorkspace, CostAnalysisWorkspace, CostObjectWithLowestAccuracy, CostVarianceChart, CostObjectWithLowestTurn
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Operations
ms.custom: 270314
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 54da05bb6b84390f9928d8400e3dafc3228ee2fc
ms.sourcegitcommit: cd339f48066b1d0fc740b513cb72ea19015acd16
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "3759265"
---
# <a name="cost-management-power-bi-content"></a>Contenido de gestión de costes de Power BI

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Información general

El contenido de **Gestión de costes** de Microsoft Power BI está destinado a los contables de inventario o individuos en la organización que son responsable o están interesados en el estado del inventario o del trabajo en curso (WIP), o que son responsables o están interesados en el análisis de desviaciones de coste estándar.

> [!NOTE]
> Los contenidos de **Gestión de costes** Power BI descrito en este tema se aplican a Dynamics 365 Finance and Operations 8.0.
> 
> El paquete de contenido de **Gestión de costes** Power BI, disponible en el sitio de AppSource se ha dejado de utilizar. Para obtener más información sobre dicha deprecación, consulte [Funcionalidades eliminadas u obsoletas de Finance and Operations](../migration-upgrade/deprecated-features.md#power-bi-content-packs-available-on-appsource).

Este contenido de Power BI proporciona un formato categorizado que ayuda a controlar el rendimiento de inventarios y visualizar cómo fluyen los coste a través de ellos. Puede obtener información de gestión como el ratio de facturación, el número de días que el inventario está disponible, precisión y "clasificación ABC" de su nivel agregado preferido (empresa, artículo, grupo de artículos o sitio). La información que se facilita se puede usar también como suplemento detallado del informe financiero.

El contenido de Power BI se basa en la medida agregada **CostObjectStatementCacheMonthly**, que tiene la tabla **CostObjectStatementCache** como su origen de datos principal. Esta tabla se gestiona a través del marco de caché del conjunto de datos. De forma predeterminada, la tabla se actualiza cada 24 horas, pero se puede cambiar la frecuencia de actualización o habilitar actualizaciones manuales en la configuración de la caché de datos. Las actualizaciones manuales pueden ejecutarse en el espacio de trabajo **Gestión de costes** o el espacio de trabajo **Análisis de costes**.

Después de cada actualización de la tabla **CostObjectStatementCache**, la medida agregada **CostObjectStatementCacheMonthly** debe actualizarse antes de que los datos en las vistas de Power BI se actualicen.

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI

El contenido de **Gestión de costes** Power BI se muestra en los espacios de trabajo **Gestión de costes** y **Análisis de costes**.

El espacio de trabajo **Gestión de costes** contiene las siguientes fichas:

- **Visión general** La ficha muestra datos de la aplicación.
- **Estado de contabilidad de inventario** - La ficha muestra el contenido de Power BI.
- **Estado de contabilidad de fabricación** - La ficha muestra el contenido de Power BI.

El espacio de trabajo **Análisis de costes** contiene las siguientes fichas:

- **Visión general** La ficha muestra datos de la aplicación.
- **Análisis de contabilidad de inventario** - La ficha muestra el contenido de Power BI.
- **Análisis de contabilidad de fabricación** - La ficha muestra el contenido de Power BI.
- **Análisis estándar de variación de costes** - La ficha muestra el contenido de Power BI.

## <a name="report-pages-that-are-included-in-the-power-bi-content"></a>Páginas de informes que se incluyen en el paquete de contenido Power BI

El contenido de **Gestión de costes** Power BI incluye un conjunto de páginas de informe compuesto por un conjunto de métricas. Estas métricas se visualizan como gráficos, mosaicos y tablas. 

Las tabla siguientes proporcionan una visión general de las visualizaciones en el contenido de **Gestión de costes** Power BI.

### <a name="inventory-accounting-status"></a>Estado de contabilidad de inventario

| Página de informes                               | Visualización                                   |
|-------------------------------------------|-------------------------------------------------|
| Visión general del inventario                        | Saldo inicial                               |
|                                           | Cambio neto                                      |
|                                           | Cambio neto %                                    |
|                                           | Saldo final                                  |
|                                           | Precisión del inventario                              |
|                                           | Tasa de facturación de inventario                        |
|                                           | Días de disponibilidad de inventario                          |
|                                           | Producto activo en el periodo                        |
|                                           | Objetos de coste activos en el período                   |
|                                           | Saldo por grupo de artículos                           |
|                                           | Saldo por sitio                                 |
|                                           | Extracto por categoría                           |
|                                           | Cambio neto por trimestre                           |
| Visión general de inventario por sitio y grupo de artículos | Precisión de inventario por sitio                      |
|                                           | Ratio de facturación de inventario por sitio                |
|                                           | Saldo final de inventario por sitio                |
|                                           | Precisión del inventario por grupo de artículos                |
|                                           | Ratio de facturación de inventario por grupo de artículos          |
|                                           | Saldo final de inventario por sitio y grupo de artículos |
| Extracto de inventario                       | Extracto de inventario                             |
| Extracto de inventario por sitio               | Extracto de inventario por sitio                     |
| Extracto de inventario por jerarquía de productos  | Extracto de inventario                             |
| Extracto de inventario por jerarquía de productos  | Extracto de inventario por sitio                     |

### <a name="manufacturing-accounting-status"></a>Estado de contabilidad de fabricación

| Página de informes                | Visualización                       |
|----------------------------|-------------------------------------|
| Visión general del trabajo en curso del año hasta la fecha           | Saldo inicial                   |
|                            | Cambio neto                          |
|                            | Cambio neto %                        |
|                            | Saldo final                      |
|                            | Ratio de facturación del trabajo en curso                  |
|                            | Días de trabajo en curso disponibles                    |
|                            | Objeto de coste activo en el período        |
|                            | Cambio neto por grupo de recursos        |
|                            | Saldo por sitio                     |
|                            | Extracto por categoría               |
|                            | Cambio neto por trimestre               |
| informe de trabajo en curso              | Saldo inicial                   |
|                            | Saldo final                      |
|                            | Extracto del trabajo en curso por categoría           |
| Extracto de trabajo en curso por sitio      | Saldo inicial                   |
|                            | Saldo final                      |
|                            | Extracto del trabajo en curso por categoría y sitio  |
| Extracto del trabajo en curso por jerarquía | Saldo inicial                   |
|                            | Saldo final                      |
|                            | Extracto del trabajo en curso por jerarquía de categoría |

### <a name="inventory-accounting-analysis"></a>Análisis de contabilidad de inventario

| Página de informes        | Visualización                                                                |
|--------------------|------------------------------------------------------------------------------|
| Detalles del inventario  | Los 10 recursos principales por saldo final                                           |
|                    | Los 10 recursos principales por aumento del cambio neto                                      |
|                    | Los 10 recursos principales por descenso del cambio neto                                      |
|                    | Los 10 recursos principales por ratio de facturación de inventario                                 |
|                    | Recursos por ratio de facturación de bajo inventario y por saldo final por encimario del umbral |
|                    | Los 10 recursos principales por baja precisión                                             |
| Clasificación ABC | Saldo final de inventario                                                     |
|                    | Material consumido                                                            |
|                    | Vendido (COGS)                                                                  |
| Tendencias de inventario   | Saldo final de inventario                                                     |
|                    | Cambio neto de inventario                                                         |
|                    | Tasa de facturación de inventario                                                     |
|                    | Precisión del inventario                                                           |

### <a name="manufacturing-accounting-analysis"></a>Análisis de contabilidad de fabricación

| Página de informes | Visualización      |
|-------------|--------------------|
| Tendencias del trabajo en curso  | Saldo final de trabajo en curso |
|             | Cambio neto de trabajo en curso     |
|             | Ratio de facturación del trabajo en curso |

### <a name="std-cost-variance-analysis"></a>Análisis de desviación del coste estándar

| Página de informes                             | Visualización                                        |
|-----------------------------------------|------------------------------------------------------|
| Desviación de precio de compra (coste estándar) del año hasta la fecha: | Saldo de las compras                                     |
|                                         | Desviación en el precio de compra                              |
|                                         | Ratio de desviación del precio de compra                        |
|                                         | Desviación por grupo de artículos                               |
|                                         | Desviación por sitio                                     |
|                                         | Precio de compra por trimestre                            |
|                                         | Precio de compra por trimestre y grupo de artículos             |
|                                         | Los 10 recursos principales por ratio desfavorable del precio de compra |
|                                         | Los 10 recursos principales por ratio favorable del precio de compra   |
| Desviación de producción (coste estándar) del año hasta la fecha     | Coste de artículos fabricados                                    |
|                                         | Desviación de producción                                  |
|                                         | Ratio de desviación de producción                            |
|                                         | Desviación por grupo de artículos                               |
|                                         | Desviación por sitio                                     |
|                                         | Desviación en la cantidad de producción por trimestre                       |
|                                         | Desviación de producción por trimestre y tipo de desviación     |
|                                         | Los 10 recursos principales por desviación de producción desfavorable  |
|                                         | Los 10 recursos principales por desviación de producción favorable    |

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades

Los datos de la aplicación se usan para rellenar las páginas de informes del contenido de Power BI de **Gestión de costes**. Estos datos se representan como medidas globales que se realizan en la tienda de la entidad, que es una base de datos de Microsoft SQL Server que se optimiza para análisis. Para obtener más información, consulte [Integración de Power BI con el almacén de entidades](power-bi-integration-entity-store.md).

Las medidas agregadas clave de los objetos siguientes se usan como base del contenido de Power BI.

| Objeto                          | Medidas agregadas clave | Origen de datos para Finance and Operations | Campo               |
|---------------------------------|----------------------------|----------------------------------------|---------------------|
| CostObjectStatementCacheMonthly | Importe                     | CostObjectStatementCache               | Importe              |
| CostObjectStatementCacheMonthly | Cantidad                   | CostObjectStatementCache               | Cant.                 |
| CostInventoryAccountingKPIGoal  | AnnualInventoryTurn        | CostInventoryAccountingKPIGoal         | AnnualInventoryTurn |
| CostInventoryAccountingKPIGoal  | InventoryAccuracy          | CostInventoryAccountingKPIGoal         | InventoryAccuracy   |

La tabla siguiente muestra las medidas calculadas clave en el contenido de Power BI.

| Medida                            | Cálculo |
|------------------------------------|-------------|
| Saldo inicial                  | Saldo inicial = \[Saldo final\]-\[Cambio neto\] |
| Cantidad de saldo inicial.             | Cantidad de saldo inicial = \[Cantidad de saldo final\]-\[Cantidad de cambio neto\] |
| Saldo final                     | Saldo final = (CALCULATE(SUM(\[Amount\]), FILTER(ALL(FiscalCalendar) ,FiscalCalendar\[MONTHSTARTDATE\] \<= MAX(FiscalCalendar\[MONTHSTARTDATE\])))) |
| Cantidad de saldo final                | Cantidad de saldo final = CALCULATE(SUM(\[QTY\]), FILTER(ALL(FiscalCalendar),FiscalCalendar\[MONTHSTARTDATE\] \<= MAX(FiscalCalendar\[MONTHSTARTDATE\]))) |
| Cambio neto                         | Cambio neto = SUM(\[AMOUNT\]) |
| Cantidad de cambio neto                    | Cantidad de cambio neto = SUM(\[QTY\]) |
| Ratio de facturación de inventario por importe | Ratio de facturación de inventario por importe = if(OR(\[Saldo medio de inventario\] \<= 0, \[Inventory sold or consumed issues\] \>= 0) 0, ABS (\[Emisiones de inventario vendidas o consumidas\])/\[Saldo medio de inventario\]) |
| Saldo medio de inventario          | Saldo medio de inventario = ((\[Saldo final\] + \[Saldo inicial\]) / 2) |
| Días de disponibilidad de inventario             | Días de disponibilidad de inventario = 365 / CostObjectStatementEntries\[Ratio de facturación de inventario por importe\] |
| Precisión del inventario                 | Precisión del inventario por cantidad = SI(\[Balance final\] \<= 0, IF(OR(\[Inventory counted amount\] \<\> 0, \[Balance final\] \< 0), 0, 1), MAX(0, (\[Balance final\] - ABS (\[Cantidad contada de inventario\]))/\[Balance final\])) |

Las dimensiones clave siguientes se utilizan como filtros para cortar las medidas agregadas, de forma que logre mayor granularidad y obtener una visión analítica más profunda.


| Entidad                                                  | Ejemplos de atributos                          |
|---------------------------------------------------------|-------------------------------------------------|
| Productos                                                | Número de producto, nombre de producto, unidad, grupos de artículos |
| Jerarquías de categorías (asignadas al rol de gestión de costes) | Jerarquía de categoría, nivel de categoría              |
| Entidades jurídicas                                          | Nombres de entidad jurídica                              |
| Calendarios fiscales                                        | Calendario fiscal, año, trimestre, período, mes   |
| Sitio                                                    | Identificador, nombre, dirección, Comunidad autónoma, País               |
