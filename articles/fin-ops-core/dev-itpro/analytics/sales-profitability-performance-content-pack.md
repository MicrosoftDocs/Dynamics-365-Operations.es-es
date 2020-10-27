---
title: Contenido de Power BI de rendimiento de ventas y rentabilidad
description: Este tema describe lo que se incluye en el contenido de Power BI sobre Rendimiento de ventas y rentabilidad. Explica cómo obtener acceso a los informes de Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.
author: ShylaThompson
manager: AnnBe
ms.date: 12/18/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SalesProfitabilityPerformancePowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 260674
ms.assetid: ab457f02-929e-4d34-b813-335be3092287
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 490a4f6d1bd9f3bdb0af09bd4e6f7f8fb2c92a1b
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/10/2020
ms.locfileid: "3984283"
---
# <a name="sales-and-profitability-performance-power-bi-content"></a>Contenido de Power BI de rendimiento de ventas y rentabilidad

[!include [banner](../includes/banner.md)]

Este tema describe lo que incluye el contenido de Microsoft Power BI sobre **Rendimiento de ventas y rentabilidad**. Explica cómo obtener acceso a los informes de Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.

## <a name="overview"></a>Información general

El contenido de Power BI sobre **Rendimiento de ventas y rentabilidad** se creó de modo que los directores de ventas puedan controlar medidas clave de ingresos, beneficio bruto y margen de beneficio. Usa datos transaccionales de ventas y proporciona una visión global de las cifras de ventas empresariales y un desglose de rendimiento de ventas para los clientes y los productos.

Los informes resaltan los cambios en ingresos y el crecimiento de las ganancias con el tiempo. Por lo tanto, los informes se pueden usar para notificar a los administradores las tendencias positivas y negativas de clientes y productos individuales. Además, los gráficos comparan los ingresos y la rentabilidad de distintas categorías de productos y grupos de clientes entre sí. Por lo tanto, los directores de categoría y regionales pueden identificar a los rezagados y a los que van en primer lugar. Finalmente, un informe exhaustivo traza ingresos de un cliente individual frente al margen de beneficio. Por lo tanto, los administradores de cuentas tienen una base respaldada por datos que pueden usar para ajustar los esfuerzos de ventas y marketing al perfil de cada cliente.

El contenido **Rendimiento de ventas y rentabilidad** permite a los directores de ventas analizar el rendimiento de ventas de las maneras siguientes:

- Ingresos, año hasta la fecha (por grupos de clientes y clientes individuales, categorías de ventas, y productos individuales y geografías)
- Cambio de ingresos, año a año (por regiones y categorías de ventas del cliente)

La rentabilidad se pueda analizar mediante los siguientes procedimientos:

- Ganancia bruta y margen de beneficio (por grupos de clientes y categorías de ventas de producto)
- Cambio de ganancias brutas, año a año
- Rentabilidad del cliente (por ingreso comparado con margen bruto)

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI
El contenido de Power BI **Rendimiento de ventas y rentabilidad** se muestra en la página **Rendimiento de ventas y rentabilidad** (**Ventas y marketing** \> **Consultas e informes** \> **Análisis de rendimiento de ventas** \> **Rendimiento de ventas y rentabilidad**).

## <a name="metricsthat-are-included-in-the-power-bi-content"></a>Métricas que se incluyen en el contenido de Power BI
El contenido de Power BI sobre **Rendimiento de ventas y rentabilidad** incluye un informe compuesto por un conjunto de métricas. Estas métricas se visualizan como gráficos, mosaicos y tablas. La tabla siguiente proporciona información general de las visualizaciones del contenido.

| Página de informes            | Gráficos                                     | Mosaicos                                                   |
|------------------------|--------------------------------------------|---------------------------------------------------------|
| Ingresos por cliente    | 10 clientes principales por ingresos                | Ingresos totales                                           |
|                        | Ingresos totales por grupo de clientes            | Crecimiento de ingresos interanual                                      |
|                        | Ingresos de cliente medio por grupo de clientes | Margen bruto                                            |
|                        | Ingresos y ganancias brutas por grupo de clientes   |                                                         |
| Ingresos por producto     | Ingresos y ganancias brutas por categoría de ventas   | \# total de productos                                    |
|                        | 10 productos principales por ingresos                 | Número total de productos activos y porcentaje del total |
|                        | Ingresos totales por categoría de ventas            | Número de productos que representan el 80 % de los ingresos           |
| Ingresos por período\*    | Ingresos por mes                           | Crecimiento de ingresos interanual                                      |
|                        | Desviación de los ingresos finales, interanual             | % crecimiento de ingresos interanuales                                    |
|                        | Desviación de ventas total por región del cliente    |                                                         |
| Ingresos por ubicación    | Ingresos de ventas por ciudad                      |                                                         |
|                        | % crecimiento de ingresos interanuales                       |                                                         |
|                        | Ingresos de ventas por región                    |                                                         |
| Rentabilidad del cliente | Margen bruto comparado con los ingresos, por cliente   | Ganancias brutas, margen bruto, crecimiento de ingresos interanual          |
| Análisis de rentabilidad | Ingresos y ganancias brutas por mes          |                                                         |
|                        | 15 clientes principales por margen bruto           |                                                         |
|                        | Ganancias brutas por mes, interanual                 |                                                         |

\* Ingresos este año y el año anterior, y crecimiento por categoría de ventas

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades
Los datos siguientes se usan para rellenar el informe del contenido de Power BI sobre **Rendimiento de ventas y rentabilidad**. Estos datos se representan como medidas agregadas que se realizan en el almacén de la entidad. El almacén de la entidad es una base de datos de Microsoft SQL Server que se optimiza para el análisis. Para obtener más información, consulte [Integración de Power BI con el almacén de entidades](power-bi-integration-entity-store.md).

Las medidas globales de este paquete de contenido son el subconjunto de las medidas globales que estaban disponibles en el cubo de ventas en Microsoft Dynamics AX 2012 y Microsoft Dynamics AX 2012 R3. Para realizar las medidas globales del cubo en el almacén de entidades debe hacer que sean desplegables. Para obtener más información, consulte el procedimiento relativo a cómo realizar mediciones globales en el almacén de entidades en el blog sobre [integración de Power BI con el almacén de entidades en Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/).

Las siguientes medidas agregadas clave de la entidad de líneas de factura se usan como base del contenido.

| Entidad        | Medidas agregadas clave                   | Origen de datos para Dynamics 365 | Campo                                        | Descripción                                       |
|---------------|----------------------------------------------|------------------------------|----------------------------------------------|---------------------------------------------------|
| Líneas de factura | Ingresos                                      | CustInvoiceTrans             | SUM(LineAmountMST)                           | El importe en la divisa de contabilidad.            |
|               | Coste de bienes vendidos                           | InventTrans                  | SUM(CostAmountPosted + CostAmountAdjustment) | La suma del importe de coste y el ajuste.    |
|               | Importe de la línea de comisión - divisa de contabilidad | CustInvoiceTrans             | SUM(CommissAmountMST)                        | El importe de la comisión en la divisa de la contabilidad. |

La tabla siguiente muestra las medidas agregadas clave de la entidad de líneas de factura que se usan para crear varias medidas calculadas en el conjunto de datos del contenido.

| Medida           | Cálculo                                                                                      |
|-------------------|--------------------------------------------------------------------------------------------------|
| Ganancias brutas      | SUM(Ingresos – COGS – Comisión – Impuestos (incluidos en el importe de la línea de factura de cliente))          |
| Margen bruto      | SUM(Ganancias brutas / (Ingresos - Impuestos (incluidos en el importe de la línea de factura de cliente)))             |
| Ingresos el último año | Ingresos el último año = CALCULATE(SUM('Líneas factura'\[Ingresos\]), SAMEPERIODLASTYEAR(Fechas\[Fecha\]) |

Las dimensiones clave siguientes del cubo de ventas se utilizan como filtros para cortar las medidas globales de forma que logre mayor granularidad y profundizar en la visión analítica.

| Entidad           | Ejemplos de atributos                               |
|------------------|------------------------------------------------------|
| Empresas cliente        | Grupos de clientes, regiones de clientes, dirección, sector |
| Productos         | Número de producto, nombre de producto, nombre de grupos de artículos       |
| Categorías de ventas | Nombres de categoría de ventas                                 |
| Entidades jurídicas   | Nombres de entidad jurídica                                   |
| Fechas            | Fechas                                                |

De forma predeterminada, el contenido muestra los datos del año natural actual. Sin embargo, puede cambiar el filtro de la fecha en la sección de filtros de informe. También puede cambiar el filtro de empresa.
