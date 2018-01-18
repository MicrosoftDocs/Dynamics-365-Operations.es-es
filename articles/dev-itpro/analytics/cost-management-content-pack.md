---
title: "Contenido de gestión de costes en Power BI"
description: "Este tema describe lo que se incluye en el contenido de gestión de costes en Power BI."
author: YuyuScheller
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Operations
ms.custom: 270314
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: cb43245afe578341251b140383a3b03ba2abd962
ms.openlocfilehash: e0f9042b2647a484a70670d1d29e8036401b39f1
ms.contentlocale: es-es
ms.lasthandoff: 12/19/2017

---

# <a name="cost-management-power-bi-content"></a>Contenido de gestión de costes en Power BI

[!include[banner](../includes/banner.md)]


Este tema describe lo que se incluye en el contenido de gestión de costes en Power BI. 

# <a name="overview"></a>Información general

El contenido de **gestión de costes** en Microsoft Power BI está destinado a los contables de inventario o a los individuos de la organización responsables del inventario. El contenido de **gestión de costes** en Power BI proporciona información administrativa de inventario y de inventario del trabajo en curso y explica cómo el coste fluye por categoría en el tiempo. La información se puede usar como suplemento detallado del informe financiero.

## <a name="key-measures"></a>Medidas clave

+ Saldo inicial
+ Saldo final
+ Cambio neto
+ Cambio neto en %
+ Vencimiento

## <a name="key-performance-indicators"></a>Indicadores clave de rendimiento
+ Rotación de inventario
+ Precisión del inventario

El origen de datos principal para CostAggregatedCostStatementEntryEntity es la tabla CostStatementCache. Esta tabla se gestiona a través del marco de caché del conjunto de datos. De forma predeterminada, la tabla se actualiza cada 24 horas, pero puede habilitar actualizaciones manuales en la configuración de la caché de datos. Puede realizar entonces una actualización manual en el área de trabajo **Gestión de costes** o **Análisis de coste**. Una vez ejecutada la actualización de CostStatementCache, debe actualizar la conexión de OData en Power BI.com para ver los datos actualizados en el sitio. Las medidas de desviación (compra, producción) en este contenido de Power BI pertenecen a solo los artículos que se han evaluado por el método de inventario de coste estándar. La desviación de producción se calcula como la diferencia entre el coste activo y el coste realizado. Se calcula la desviación de producción cuando el pedido de producción tiene el estado **Finalizado**. Para obtener más información sobre los tipos de desviación de producción y cómo cada tipo se calcula, consulte [Acerca del análisis de desviaciones de un pedido de producción completado](https://technet.microsoft.com/en-us/library/gg242850.aspx).


## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Métricas que se incluyen en el contenido de Power BI
El contenido incluye un conjunto de páginas de informe. Cada página consta de un conjunto de métricas que se visualizan como gráficos, mosaicos y tablas. La tabla siguiente proporciona una visión general de las visualizaciones en el contenido de **gestión de costes** en Power BI.

| Página de informes | Gráficos | Cargos |
|---|---|---|
|Inventario total (predeterminado por período actual) |Precisión |Medidas de inventario:<br>Saldo final de inventario<br>Cambio neto de inventario<br>Cambio neto de inventario %<br>|
| |Rotación de inventario | |
| |Saldo final de inventario por grupo de recursos | |
| |Cambio neto de inventario por nombre de categoría nivel 1 y nombre de categoría nivel 2| |
| |Desviaciones de compras por grupo de recursos y nombre de categoría nivel 3 | |
|Inventario por sitio (predeterminado por período actual) |Saldo final de inventario por nombre de sitio y grupo de recursos | |
| |Rotación de inventario por nombre de sitio y grupo de recursos | |
| |Saldo final de inventario por ciudad y grupo de recursos | |
|Inventario por grupo de recursos (predeterminado por período actual) |Medidas de inventario | |
| |Precisión del inventario por importe por grupo de recursos | |
| |Rotación de inventario por importe por grupo de recursos | |
|YOY de inventario (año actual predeterminado frente a año anterior) |Medidas de inventario | |
| |KPI de inventario:<br>Rotación de inventario<br>Precisión del inventario | |
| |Saldo final de inventario por año y grupo de recursos | |
| |Desviaciones de compras por año y nombre de categoría nivel 3 | |
|Vencimiento de inventario (el valor predeterminado del año actual) |Vencimiento de inventario por trimestre y por grupo de recursos | |
| |Vencimiento de inventario por trimestre y por nombre de sitio | |
|Trabajo en curso total (predeterminado por período actual) |Cambio neto de trabajo en curso por nombre de categoría nivel 1 y nombre de categoría nivel 2 |Medidas de trabajo en curso:<br>Saldo final de trabajo en curso<br>Cambio neto de trabajo en curso<br>Cambio neto de trabajo en curso %<br> |
| |Desviaciones de producción por grupo de recursos y nombre de categoría nivel 3 | |
| |Cambio neto de trabajo en curso por grupo de recursos | |
|Trabajo en curso por sitio (predeterminado por período actual) |Medidas de trabajo en curso | |
| |Cambio neto de trabajo en curso por nombre de sitio y nombre de categoría nivel 2 | |
| |Desviaciones de producción por nombre de sitio y nombre de categoría nivel 3 | |

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades
Finance and Operations se usan para rellenar las páginas de informes en el contenido de **gestión de costes** en Power BI. Estos datos se representan como medidas globales que se realizan en el almacén de la entidad, que es una base de datos de Microsoft SQL que se optimiza para análisis. Para obtener más información, consulte [Visión general de la integración de Power BI con el almacén de entidades](power-bi-integration-entity-store.md). Las siguientes medidas agregadas clave se usan como la base del contenido.

| Entidad            | Medida agregada clave | Origen de datos para Finance and Operations | Campo             | Descripción                       |
|-------------------|---------------------------|---------------------------------------------|-------------------|-----------------------------------|
| Entradas del extracto | Cambio neto                | CostAggregatedCostStatementEntryEntity      | suma(\[Importe\])   | Importe en la divisa de contabilidad |
| Entradas del extracto | Cantidad de cambio neto       | CostAggregatedCostStatementEntryEntity      | suma(\[Cantidad\]) |                                   |

Se usará la tabla siguiente para mostrar cómo se usan las medidas agregadas clave para crear varias medidas calculadas en el conjunto de datos del contenido.

| Medida                                 | Cómo se calcula la medida                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Saldo inicial                       | \[Saldo final\]-\[Cambio neto\]                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Cantidad de saldo inicial              | \[Cantidad de saldo final\]-\[Cantidad de cambio neto\]                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Saldo final                          | CALCULATE(SUM(\[Importe\]), FILTER(ALLEXCEPT('Calendarios fiscales', 'Calendarios fiscales'\[LedgerRecId\], 'entidades'\[ID\], 'entidades'\[Nombre\], 'Libros mayores'\[Divisa\], 'Libros mayores'\[Descripción\], 'Libros mayores'\[Nombre\]), 'Calendarios fiscales'\[Fecha\] &lt;= MAX('Calendarios fiscales'\[Fecha\])))                                                                                                                                                                                           |
| Cantidad de saldo final                 | CALCULATE(SUM(\[Cantidad\]), FILTER(ALLEXCEPT('Calendarios fiscales', 'Calendarios fiscales'\[LedgerRecId\], 'entidades'\[ID\], 'entidades'\[Nombre\], 'Libros mayores'\[Divisa\], 'Libros mayores'\[Descripción\], 'Libros mayores'\[Nombre\]), 'Calendarios fiscales'\[Fecha\] &lt;= MAX('Calendarios fiscales'\[Fecha\])))                                                                                                                                                                                         |
| Saldo inicial de inventario             | CALCULATE(\[Saldo inicial\], 'Entradas del extracto'\[Tipo de instrucción\] = "Inventario")                                                                                                                                                                                                                                                                                                                                                                                      |
| Saldo final de inventario                | CALCULATE(\[Saldo final\], 'Entradas del extracto'\[Tipo de extracto\] = "Inventario")                                                                                                                                                                                                                                                                                                                                                                                         |
| Cambio neto de inventario                    | CALCULATE(\[Cambio neto\], 'Entradas del extracto'\[Tipo de extracto\] = "Inventario")                                                                                                                                                                                                                                                                                                                                                                                             |
| Cantidad de cambio neto de inventario           | CALCULATE(\[Cantidad de cambio neto\], 'Entradas del extracto'\[Tipo de extracto\] = "Inventario")                                                                                                                                                                                                                                                                                                                                                                                    |
| Cambio neto de inventario %                  | IF(\[Saldo final de inventario\] = 0, 0, \[Cambio neto de inventario\] / \[Saldo final de inventario\])                                                                                                                                                                                                                                                                                                                                                                           |
| Rotación de inventario por importe                | if(OR(\[Saldo medio de inventario\] &lt;= 0, \[Inventario vendido o emisiones consumidas\] &gt;= 0), 0, ABS(\[Inventario vendido o emisiones consumidas\])/\[Saldo medio de inventario\])                                                                                                                                                                                                                                                                                                  |
| Saldo medio de inventario               | (\[Saldo final de inventario\] + \[Saldo inicial de inventario\]) / 2                                                                                                                                                                                                                                                                                                                                                                                                       |
| Inventario vendido o emisiones consumidas       | \[Inventario vendido\] + \[Coste de material consumido de inventario\]                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Coste de material consumido de inventario        | CALCULATE(\[Saldo neto de inventario\], 'Entradas del extracto'\[Nombre de categoría - nivel 2\_\] = "ConsumedMaterialsCost")                                                                                                                                                                                                                                                                                                                                                            |
| Inventario vendido                          | CALCULATE(\[Saldo neto de inventario\], 'Entradas del extracto'\[Nombre de categoría - nivel 2\_\] = "Vendido")                                                                                                                                                                                                                                                                                                                                                                             |
| Precisión de inventario por importe            | IF(\[Saldo final de inventario\] &lt;= 0, IF(OR(\[Importe contabilizado de inventario\] &lt;&gt; 0, \[Saldo final de inventario\] &lt; 0), 0, 1), MAX(0, (\[Saldo final de inventario\] - ABS(\[Importe contabilizado de inventario\]))/\[Saldo final de inventario\]))                                                                                                                                                                                                                              |
| Importe contabilizado de inventario                | CALCULATE(\[Saldo neto de inventario\], 'Entradas del extracto'\[Nombre de categoría - nivel 3\_\] = "Recuento")                                                                                                                                                                                                                                                                                                                                                                         |
| Vencimiento de inventario                         | if(ISBLANK(max('Calendarios fiscales'\[Fecha\])), blank(), MAX(0, MIN(\[Cantidad de recibos de vencimiento de inventario\], \[Cantidad de saldo final de vencimiento de inventario\] - \[Cantidad de recibos de vencimiento de inventario en el futuro\]))) \* \[Coste unitario medio de inventario\]                                                                                                                                                                                                                                |
| Cantidad de recibos de vencimiento de inventario       | IF(\[minDate\] = \[minDateAllSelected\], CALCULATE(\[Cantidad de cambio neto de inventario\], 'Entradas del extracto'\[Cantidad\] &gt; 0, FILTER(ALLEXCEPT('Calendarios fiscales', 'Calendarios fiscales'\[LedgerRecId\], 'entidades'\[ID\], 'entidades'\[Nombre\], 'Libros mayores'\[Divisa\], 'Libros mayores'\[Descripción\], 'Libros mayores'\[Nombre\]), 'Calendarios fiscales'\[Fecha\] &lt;= MAX('Calendarios fiscales'\[Date\]))), CALCULATE(\[Cantidad de cambio neto de inventario\], 'Entradas del extracto'\[Cantidad\] &gt; 0)) |
| Cantidad de saldo final de vencimiento de inventario | \[Cantidad de saldo final de inventario\] + CALCULATE(\[Cantidad de cambio neto de inventario\], FILTER(ALLEXCEPT('Calendarios fiscales', 'Calendarios fiscales'\[LedgerRecId\], 'entidades'\[ID\], 'entdades'\[Nombre\], 'Libros mayores'\[Divisa\], 'Libros mayores'\[Descripción\], 'Libros mayores'\[Nombre\]), 'Calendarios fiscales'\[Fecha\] &gt; max('Calendarios fiscales'\[Fecha\]) ))                                                                                                                                 |
| Recibos de vencimientos de inventario en el futuro  | CALCULATE(\[Cambio neto de inventario\], 'Entradas del extracto'\[Importe\] &gt; 0, FILTER(ALLEXCEPT('Calendarios fiscales', 'Calendarios fiscales'\[LedgerRecId\], 'entidades'\[ID\], 'entidades'\[Nombre\], 'Libros mayores'\[Divisa\], 'Libros mayores'\[Descripción\], 'Libros mayores'\[Nombre\]), 'Calendarios fiscales'\[Date\] &gt; MAX('Calendarios fiscales'\[Fecha\])))                                                                                                                                             |
| Coste unitario medio de inventario                 | CALCULATE(\[Saldo final de inventario\] / \[Cantidad de saldo final de inventario\],ALLEXCEPT('Calendarios fiscales', 'Calendarios fiscales'\[LedgerRecId\], 'entidades'\[ID\], 'entidades'\[Nombre\], 'Libros mayores'\[Divisa\], 'Libros mayores'\[Descripción\], 'Libros mayores'\[Nombre\]))                                                                                                                                                                                                                 |
| Desviaciones de compras                      | CALCULATE(SUM(\[Importe\]), 'Entradas del extracto'\[Nombre de categoría - nivel 2\_\] = "Comprado", 'Entradas del extracto'\[Tipo de extracto\] = "Desviación")                                                                                                                                                                                                                                                                                                                              |
| Saldo inicial de trabajo en curso                   | CALCULATE(\[Saldo inicial\], 'Entradas de extracto'\[Tipo de extracto\] = "Trabajo en curso")                                                                                                                                                                                                                                                                                                                                                                                            |
| Saldo final de trabajo en curso                      | CALCULATE(\[Saldo final\], 'Entradas de extracto'\[Tipo de extracto\] = "Trabajo en curso")                                                                                                                                                                                                                                                                                                                                                                                               |
| Cambio neto de trabajo en curso                          | CALCULATE(\[Cambio neto\], 'Entradas del extracto'\[Tipo de extracto\] = "Trabajo en curso")                                                                                                                                                                                                                                                                                                                                                                                                   |
| Cambio neto de trabajo en curso %                        | IF(\[Saldo final de trabajo en curso\] = 0, 0, \[Cambio neto de trabajo en curso\] / \[Saldo final de trabajo en curso\])                                                                                                                                                                                                                                                                                                                                                                                             |
| Desviaciones de producción                    | CALCULATE(SUM(\[Importe\]), 'Entradas del extracto'\[Nombre de categoría - nivel 2\_\] = "ManufacturedCost", 'Entradas del extracto'\[Tipo de extracto\] = "Desviación")                                                                                                                                                                                                                                                                                                                      |
| Nombre de categoría - nivel 1                 | switch(\[Nombre de categoría - nivel 1\_\], "Ninguno", "Ninguno", "NetSourcing", "Abastecimiento neto", "NetUsage", "Uso neto", "NetConversionCost", "Coste neto de conversión", "NetCostOfGoodsManufactured", "Coste neto de bienes fabricados", "BeginningBalance", "Saldo inicial")                                                                                                                                                                                                         |
| Nombre de categoría - nivel 2                 | switch(\[Nombre de categoría - nivel 2\_\], "Ninguno", "Ninguno", "Comprado", "Comprado", "Desechado", "Desechado", "Transferido", "Transferido", "Vendido", "Vendido", "ConsumedMaterialsCost", "Coste de material consumido", "ConsumedManufacturingCost", "Coste de fabricación consumido", "ConsumedOutsourcingCost", "Coste de subcontratación consumido", "ConsumedIndirectCost", "Coste indirecto consumido", "ManufacturedCost", "Coste de artículos fabricados", "Desviaciones", "Desviaciones")                            |
| Nombre de categoría - nivel 3                 | switch(\[Nombre de categoría - nivel 3\_\], "Ninguno", "Ninguno", "Recuento", "v", "ProductionPriceVariance", "Precio de producción", "QuantityVariance", "Cantidad", "SubstitutionVariance", "Sustitución", "ScrapVariance", "Residuo", "LotSizeVariance", "Tamaño del lote", "RevaluationVariance", "Revalorización", "PurchasePriceVariance", "Precio de compra", "CostChangeVariance", "Cambio de coste", "RoundingVariance", "Desviación por redondeo")                                                   |

Las dimensiones clave siguientes se utilizan como filtros para cortar las medidas globales para lograr mayor granularidad y para proporcionar una visión analítica más profunda.

| Entidad           | Ejemplos de atributos                       |
|------------------|----------------------------------------------|
| Entidades         | Identificador, nombre                                     |
| Calendarios fiscales | Calendario, mes, período, trimestre, año       |
| Objetivos de KPI        | Objetivo de la precisión del inventario, objetivo de rotación de inventario |
| Libros mayores          | Divisa, nombre, descripción                  |
| Sitios            | Identificador, nombre, país, ciudad                      |






