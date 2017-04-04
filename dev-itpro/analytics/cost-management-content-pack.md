---
title: "Contenido de Power BI de administración de costes"
description: "Este tema describe lo que se incluye en el contenido de Power BI de administración de costes. Explica de cómo obtener acceso a los informes de Power BI, y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations
ms.custom: 270314
ms.assetid: 9680d977-43c8-47a7-966d-2280ba21402a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: e4de011e6eeac58643b828b65e24b874d981d5e7
ms.lasthandoff: 03/31/2017


---

# <a name="cost-management-power-bi-content"></a>Contenido de Power BI de administración de costes

Este tema describe lo que se incluye en el contenido de Power BI de administración de costes. Explica de cómo obtener acceso a los informes de Power BI, y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.

# <a name="overview"></a>Visión general

** Gestión de costes ** el contenido de Power BI de Microsoft está destinado a los contables o individuos de inventario en la organización que es responsable de inventario. ** Gestión de costes ** el contenido de Power BI proporciona la penetración directiva de inventario y el inventario (WIP) del trabajo en curso, y cómo el coste los fluye por categoría en el tiempo. La información se puede usar como suplemento detallado el informe financiero.

## <a name="key-measures"></a>Acciones de la clave

+ Saldo inicial
+ Saldo final
+ Cambio neto
+ Cambio neto en %
+ Vencimiento

## <a name="key-performance-indicators"></a>Indicadores clave de rendimiento
+ Rotación de inventario
+ Precisión del inventario

El origen de datos principal para CostAggregatedCostStatementEntryEntity es la tabla de CostStatementCache. Esta tabla se gestiona a través del marco de memoria caché del conjunto de datos. De forma predeterminada, la tabla se actualiza cada 24 horas, pero puede habilitar actualizaciones manuales en la configuración de la caché de datos. A continuación puede realizar una actualización manual en ** administración de costes o ** ** análisis de coste ** área de trabajo. Una vez finalizada la actualización de CostStatementCache se ejecute, debe actualizar la conexión de OData en el potencia BI.com para ver datos actualizados en el sitio. Las medidas de desviación (compra, producción) en este contenido de Power BI pertenecen a sólo los artículos que valuated por el método de inventario de coste estándar. La desviación de producción se calcula como la diferencia entre el coste activo y el coste realizado. Se calcula la desviación de producción cuando el pedido de producción tiene un estado de ** ** terminado. Para obtener más información sobre los tipos de desviación de producción y cómo cada tipo se calcula, consulte [sobre las desviaciones de desviaciones de un pedido de producción] completado (https://technet.microsoft.com/en-us/library/gg242850.aspx).

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI
** Gestión de costes ** el contenido de Power BI está disponible en PowerBI.com. Para obtener más información sobre cómo conectar y cargar su Microsoft Dynamics 365 para los datos de las operaciones, consulte [contenido de Power BI de acceso de PowerBI.com] () power-bi-home-page.md.

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Métricas que se incluyen en el contenido de Power BI
El contenido incluye un conjunto de páginas del informe. Cada página consta de un conjunto de métricas que se visualicen como gráficos, los mosaicos, y tablas. La tabla siguiente proporciona una visión general de las vistas en ** administración de costes ** acciona el contenido de BI.

| Página de informe | Gráficos | Cargos |
|---|---|---|
|Inventario total (predeterminado por período actual) |Precisión |Acciones de inventario:<br>Saldo de cierre de inventario<br>Cambio del inventario<br>Cambio % del inventario<br>|
| |Rotación de inventario | |
| |Saldo de cierre de inventario del grupo de recursos | |
| |Cambio del inventario por el nivel 1 del nombre de categoría y el nivel 2 del nombre de categoría| |
| |Adquiera las desviaciones por el nivel 3 del grupo de recursos y el nombre de categoría | |
|Inventario según el sitio (predeterminado por período actual) |Saldo de cierre de inventario del nombre y grupo de recursos de sitio | |
| |Vuelta de inventario del nombre y grupo de recursos de sitio | |
| |Saldo de cierre del inventario de la ciudad y del grupo de recursos | |
|Inventario del grupo de recursos (predeterminado por período actual) |Acciones de inventario | |
| |Exactitud de inventario por importe del grupo de recursos | |
| |Vuelta de inventario por importe del grupo de recursos | |
|Inventario YOY (año actual predeterminado con año anterior) |Acciones de inventario | |
| |Inventario KPI:<br>Rotación de inventario<br>Precisión del inventario | |
| |Saldo de cierre del inventario del año y grupo de recursos | |
| |Adquiera las desviaciones por el nivel 3 en el año y el nombre de categoría | |
|Recepción del inventario el antigüedad (el valor predeterminado del año actual) |Recepción del inventario de antigüedad el trimestre y del grupo de recursos | |
| |Recepción del inventario el antigüedad por trimestre y buscar el nombre | |
|Trabajo en curso total (predeterminado por período actual) |Cambio de la red del trabajo en curso por el nivel 1 del nombre de categoría y el nivel 2 del nombre de categoría |Acciones del trabajo en curso en curso:<br>Saldo de cierre del trabajo en curso<br>Cambio de la red del trabajo en curso<br>Cambio % de la red del trabajo en curso<br> |
| |Desviaciones de producción por el nivel 3 del grupo de recursos y el nombre de categoría | |
| |Cambio de la red del trabajo en curso del grupo de recursos | |
|Trabajo en curso por sitio (predeterminado por período actual) |Acciones del trabajo en curso en curso | |
| |Cambio de la red del trabajo en curso por el nombre y el nivel 2 del sitio del nombre de categoría | |
| |Desviaciones de producción por el nombre y el nivel 3 del sitio del nombre de categoría | |

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades
Las Dynamics 365 para las operaciones que los datos se usa para rellenar las páginas de informes de ** administración de costes ** acciona el contenido de BI. Estos datos se representa como medidas globales que se realizan en el almacén de la entidad, que es una base de datos de Microsoft SQL que se optimiza para analítica. Para obtener más información, consulte [visión general de la integración de Power BI con la entidad almacenada power-bi-integration-entity-store.md] (). Las medidas siguientes de agregado de la clave se usan como base del contenido.

| Entidad            | Medida clave global | Origen de datos para Dynamics 365 para las operaciones | Campo             | Descripción                       |
|-------------------|---------------------------|---------------------------------------------|-------------------|-----------------------------------|
| Entradas del extracto | Cambio neto                | CostAggregatedCostStatementEntryEntity      | suma (importe de\[\])   | Importe en la divisa de contabilidad |
| Entradas del extracto | Cantidad de cambio neto       | CostAggregatedCostStatementEntryEntity      | suma (cantidad\[\]\[) |                                   |

Se usará las tablas siguiente muestra cómo cerrar las medidas globales para crear varias medidas calculadas en el conjunto de datos del contenido.

| Medida                                 | Cómo se calcula la medida                                                                                                                                                                                                                                                                                                                                                                                                                                              |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Saldo inicial                       | \]cambio de la red\]-\[del saldo\[cierre\[                                                                                                                                                                                                                                                                                                                                                                                                                                          |
| Cantidad de saldo inicial              | \]cantidad de cambio neto\]-\[de la cantidad del saldo\[cierre\[                                                                                                                                                                                                                                                                                                                                                                                                                        |
| Saldo final                          | CALCULE (importe SUM (\]), FILTRO (ALLEXCEPT (“calendarios fiscales, “calendars'entity_PLACEHOLDER \ [fiscal LedgerRecId\],\]“identificador de entities'entity_PLACEHOLDER \ [, “nombre de entities'entity_PLACEHOLDER\]\ [, “divisa de Ledgers'entity_PLACEHOLDER\]\ [, “descripción de Ledgers'entity_PLACEHOLDER\]\ [, “nombre\[\]\[\ de Ledgers'entity_PLACEHOLDER [), “>Fecha fiscal\] = &lt;MAX. (fiscal “>Fecha de\]\ calendars'entity_PLACEHOLDER [de calendars'entity_PLACEHOLDER \ [)))                                                                                                                                                                                           |
| Cantidad del saldo de cierre                 | CALCULE (SUM cantidad (\]), FILTRO (ALLEXCEPT (“calendarios fiscales, “calendars'entity_PLACEHOLDER \ [fiscal LedgerRecId\],\]“identificador de entities'entity_PLACEHOLDER \ [, “nombre de entities'entity_PLACEHOLDER\]\ [, “divisa de Ledgers'entity_PLACEHOLDER\]\ [, “descripción de Ledgers'entity_PLACEHOLDER\]\ [, “nombre\[\]\[\ de Ledgers'entity_PLACEHOLDER [), “>Fecha fiscal\] = &lt;MAX. (fiscal “>Fecha de\]\ calendars'entity_PLACEHOLDER [de calendars'entity_PLACEHOLDER \ [)))                                                                                                                                                                                         |
| Recepción del inventario los saldos iniciales             | CALCULE (saldos iniciales\[\]\[,\] 'tipo de instrucción del entries'entity_PLACEHOLDER \ [del extracto = “inventario”)                                                                                                                                                                                                                                                                                                                                                                                      |
| Saldo de cierre de inventario                | CALCULE (saldo de cierre\[\]\[,\] 'tipo de instrucción del entries'entity_PLACEHOLDER \ [del extracto = “inventario”)                                                                                                                                                                                                                                                                                                                                                                                         |
| Cambio del inventario                    | CALCULE cambio (\]de la red\[,\] 'tipo de instrucción del entries'entity_PLACEHOLDER \ [del extracto = “inventario”)                                                                                                                                                                                                                                                                                                                                                                                             |
| Cambiar cantidad del inventario           | CALCULE\](cantidad de cambio neto\[,\] 'tipo de instrucción del entries'entity_PLACEHOLDER \ [del extracto = “inventario”)                                                                                                                                                                                                                                                                                                                                                                                    |
| Cambio % del inventario                  | (SI saldo de cierre\]\[inventario\[= 0, 0, saldo de cierre\]\]inventario\] / \[del cambio neto \[inventario \[)                                                                                                                                                                                                                                                                                                                                                                           |
| Vuelta de inventario por importe                | (O bien si (saldo\] medio del inventario\[&lt;= 0, las emisiones vendidos o consumidos\] \[inventario \[&gt;= 0), 0, ABS vendidos (emisiones o consumidos\]\[inventario\[)/saldo\]medio\[inventario\[)                                                                                                                                                                                                                                                                                                  |
| Saldo medio del inventario               | ()/2\]de saldo inicial\]inventario\] + \[del saldo de cierre\[inventario\[                                                                                                                                                                                                                                                                                                                                                                                                       |
| Problemas vendidos o consumidos de inventario       | el inventario\[vendió el coste materiales consumidos inventario\]\]\] + \[                                                                                                                                                                                                                                                                                                                                                                                                                  |
| Coste materiales consumidos inventario        | CALCULE cambio (\]del inventario\[, 'nombre de la categoría de entries'entity_PLACEHOLDER \ [del extracto nivel 2 -\_\] = “ConsumedMaterialsCost”)                                                                                                                                                                                                                                                                                                                                                            |
| Inventario vendido                          | CALCULE cambio (\]del inventario\[, 'nombre de la categoría de entries'entity_PLACEHOLDER \ [del extracto nivel 2 -\_\] = “vendido”)                                                                                                                                                                                                                                                                                                                                                                             |
| Exactitud de inventario por importe            | (SI saldo de cierre\]\[inventario\[&lt;= 0, IF (O bien (\[\] 0, &lt;&gt; saldo de cierre\] 0 de inventario importe contado \[inventario &lt; \[), 0, 1), MAX. (0, (saldo de cierre\] - ABS\[(\]inventario importe contado) del inventario\[)/saldo de cierre\]\[inventario\[))                                                                                                                                                                                                                              |
| Importe contado de inventario                | CALCULE cambio (\]del inventario\[, 'nombre de la categoría de entries'entity_PLACEHOLDER \ [del extracto nivel 3 -\_\] = “contando”)                                                                                                                                                                                                                                                                                                                                                                         |
| Vencimiento de inventario                         | (si ISBLANK (máximo ('fiscal fecha de calendars'entity_PLACEHOLDER\]\) [), espacio en blanco (), MAX. (0, MIN (cantidad de antigüedad\]de recepciones\[inventario\[, cantidad de vencimiento en el futuro\]de recepciones del saldo de cierre \[inventario \[de la cantidad de inventario vencimiento\] - \[))) coste unitario de\]media) \* inventario \* \[                                                                                                                                                                                                                                |
| Cantidad de vencimiento de las recepciones de inventario       | (SI el minDate\] = \[\[minDateAllSelected\[\], CALCULA\](cantidad de cambio neto\[inventario\[, “cantidad\] 0, &gt; FILTRO (ALLEXCEPT (“calendarios fiscales, “calendars'entity_PLACEHOLDER \ [fiscal LedgerRecId\],\]“identificador de entities'entity_PLACEHOLDER \ [, “nombre de entities'entity_PLACEHOLDER\]\ [, “divisa de Ledgers'entity_PLACEHOLDER\]\ [, “descripción de Ledgers'entity_PLACEHOLDER\]\ [, “nombre de entries'entity_PLACEHOLDER\]\ [del extracto de Ledgers'entity_PLACEHOLDER \ [), “>Fecha fiscal\] = &lt;MAX. ('fiscal fecha de calendars'entity_PLACEHOLDER\]\ [de calendars'entity_PLACEHOLDER \ [)))CALCULE,\](cantidad de cambio neto\[inventario\[,\] 'cantidad de 0 \ &gt; entries'entity_PLACEHOLDER [del informe)) |
| Cantidad de vencimiento del saldo de cierre de inventario | \] la cantidad del saldo de cierre\[inventario\[+ (cantidad CALCULA\], FILTRO (ALLEXCEPT (“calendarios fiscales, “calendars'entity_PLACEHOLDER \ [fiscal LedgerRecId\],\]“identificador de entities'entity_PLACEHOLDER \ [, “nombre de entities'entity_PLACEHOLDER\]\ [, “divisa de Ledgers'entity_PLACEHOLDER\]\ [, “descripción de Ledgers'entity_PLACEHOLDER\]\ [,\]nombre “de cambio neto\[inventario\[de Ledgers'entity_PLACEHOLDER \ [), “>Fecha fiscal de\] \ &gt; calendars'entity_PLACEHOLDER [máximo (fiscal “>Fecha de\]\ calendars'entity_PLACEHOLDER [)))                                                                                                                                 |
| Recibos vencimientos de inventario en el futuro  | CALCULE cambio (\]del inventario\[, “del informe\] , &gt; FILTRO 0 (ALLEXCEPT (“calendarios fiscales, “calendars'entity_PLACEHOLDER \ [fiscal LedgerRecId\],\]“identificador de entities'entity_PLACEHOLDER \ [, “nombre de entities'entity_PLACEHOLDER\]\ [, “divisa de Ledgers'entity_PLACEHOLDER\]\ [, “descripción de Ledgers'entity_PLACEHOLDER\]\ [, “nombre de entries'entity_PLACEHOLDER\]\ [importe de Ledgers'entity_PLACEHOLDER \ [), “MAX. fiscal\] de la fecha &gt; de calendars'entity_PLACEHOLDER \ [('fiscal fecha de calendars'entity_PLACEHOLDER\]\ [)))                                                                                                                                             |
| Coste unitario de inventario de media)                 | CALCULE (cantidad,\](“ALLEXCEPT calendarios fiscales, “calendars'entity_PLACEHOLDER \ [fiscal LedgerRecId\],\]“identificador de entities'entity_PLACEHOLDER \ [, “nombre de entities'entity_PLACEHOLDER\]\ [, “divisa de Ledgers'entity_PLACEHOLDER\]\ [, “descripción de Ledgers'entity_PLACEHOLDER\]\ [,\]“nombre del saldo de cierre\]inventario\] / \[del saldo de cierre\[inventario\[de Ledgers'entity_PLACEHOLDER \) [)                                                                                                                                                                                                                 |
| Adquiera las desviaciones                      | CALCULE (SUM (importe\[\]), “nombre de la categoría de entries'entity_PLACEHOLDER \ [del extracto nivel 2 -\_\] = “procurado “, “la instrucción de entries'entity_PLACEHOLDER \ [del extracto escribe\] = “la desviación”)                                                                                                                                                                                                                                                                                                                              |
| Saldo inicial del trabajo en curso                   | CALCULE (saldos iniciales\[\]\[,\] 'tipo de instrucción del entries'entity_PLACEHOLDER \ [del extracto = “” trabajo en curso)                                                                                                                                                                                                                                                                                                                                                                                            |
| Saldo de cierre del trabajo en curso                      | CALCULE (saldo de cierre\[\]\[,\] 'tipo de instrucción del entries'entity_PLACEHOLDER \ [del extracto = “” trabajo en curso)                                                                                                                                                                                                                                                                                                                                                                                               |
| Cambio de la red del trabajo en curso                          | CALCULE cambio (\]de la red\[,\] 'tipo de instrucción del entries'entity_PLACEHOLDER \ [del extracto = “” trabajo en curso)                                                                                                                                                                                                                                                                                                                                                                                                   |
| Cambio % de la red del trabajo en curso                        | (SI saldo de cierre\[\]\[trabajo en curso = 0, 0, saldo de cierre\]\]\] / \[trabajo en proceso de cambio neto \[trabajo en curso)                                                                                                                                                                                                                                                                                                                                                                                             |
| Desviaciones de producción                    | CALCULE (SUM (importe\[\]), “nombre de la categoría de entries'entity_PLACEHOLDER \ [del extracto nivel 2 -\_\] = “ManufacturedCost “, “la instrucción de entries'entity_PLACEHOLDER \ [del extracto escribe\] = “la desviación”)                                                                                                                                                                                                                                                                                                                      |
| Nombre de categoría - nivel 1                 | cambio (nombre de categoría\[- nivel 1\_\]Ninguno, ““, “Ninguno “, “NetSourcing “, “compra de componentes neto “, “NetUsage “, “uso neto “, “NetConversionCost “, “coste de conversión neto “, “NetCostOfGoodsManufactured “, “precio neto de las mercancías manufacturadas “, “BeginningBalance “, “” saldos iniciales)                                                                                                                                                                                                         |
| Nombre de categoría - nivel 2                 | cambio (nombre de categoría\[- el nivel 2\_\], “none”, “none”, “procurado “, “procurado “, “cancelado “, “cancelado “, “transferido “, “transferido “, “vendido “, “vendido “, “ConsumedMaterialsCost “, “coste materiales consumidos “, “ConsumedManufacturingCost “, “coste consumido de fabricación “, “ConsumedOutsourcingCost “, “coste consumido de externalización “, “ConsumedIndirectCost “, “coste indirecto consumido “, “ManufacturedCost “, “fabricó coste”, “las desviaciones”, “las desviaciones”)                            |
| Nombre de categoría - nivel 3                 | cambio (nombre de categoría\[- nivel 3\_\], precio “Ninguno “, “” Ninguno, el “contar “, “Ninguno”, “ProductionPriceVariance “, “de la producción,” Tamaño”, “RevaluationVariance “, “revalorización “, “PurchasePriceVariance “, “precio de adquisición “, “CostChangeVariance “, “cambio de coste “, “” RoundingVariance de “QuantityVariance”, “cantidad”, “SubstitutionVariance”, “sustitución de”, “ScrapVariance”, “residuo”, “LotSizeVariance “, “de lote, redondeando “la desviación”)                                                   |

Las dimensiones clave siguientes se utilizan como filtros para cortar las medidas globales para lograr mayor granularidad y para proporcionar penetraciones analíticas más profundas.

| Entidad           | Ejemplos de atributos                       |
|------------------|----------------------------------------------|
| Entidades         | Identificador, nombre                                     |
| Calendarios fiscales | Calendario, mes, período, trimestre, año       |
| Objetivos de KPI        | Objetivo de la precisión del inventario, objetivo de la devolución del inventario |
| Libros mayores          | Divisa, nombre, descripción                  |
| Sitios            | Identificador, nombre, País, ciudad                      |

## <a name="additional-resources"></a>Recursos adicionales
Estos son algunos vínculos útiles relacionados con las entidades y la creación de contenido de Power BI:

-   [Entidades de datos](..\data-entities\data-entities.md)
-   [Creación de paquetes de contenido organizativo](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelado de datos con Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adición de iconos de Power BI a espacios de trabajo](configure-power-bi-integration.md)



