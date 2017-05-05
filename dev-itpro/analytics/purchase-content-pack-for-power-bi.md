---
title: "Contenido de Power BI sobre análisis de gastos de compra"
description: "Este tema describe lo que se incluye en el paquete de contenido de análisis de gastos de compra en Microsoft Power BI. Explica cómo tener acceso a los informes que se incluyen en el paquete de contenido, y proporciona información acerca del modelo de datos y las entidades que se usan para generar el paquete del contenido."
author: YuyuScheller
manager: AnnBe
ms.date: 2016-12-30 09 - 40 - 51
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 8cb928cbf1316e63a8c7de833587168cd36a455c
ms.lasthandoff: 03/29/2017


---

# <a name="purchase-spend-analysis-power-bi-content"></a>Contenido de Power BI sobre análisis de gastos de compra

Este tema describe lo que se incluye en el paquete de contenido de análisis de gastos de compra en Microsoft Power BI. Explica cómo tener acceso a los informes que se incluyen en el paquete de contenido, y proporciona información acerca del modelo de datos y las entidades que se usan para generar el paquete del contenido.

<a name="overview"></a>Visión general
--------

El paquete de contenido de análisis de gastos de compra para Microsoft Power BI se creó para los directores de compra y los administradores responsables de presupuestos. Se ha diseñado para ayudar a vigilar los gastos de compra. Usa datos transaccionales de compras de Microsoft Dynamics 365 for Operations y proporciona una visión global de las cifras de compras en la empresa y un desglose de los gastos de compras por proveedor y producto. Los informes resaltan cambios en los gastos de compra a lo largo del tiempo. Por lo tanto, se pueden usar para notificar a los administradores las tendencias positivas y negativas de los gastos relativas a proveedores y productos individuales. Los gráficos muestran los gastos de compra para las diversas categorías de compras y grupos de proveedores. A los administradores de categorías y regionales puede serles útil usar estos gráficos como ayuda para identificar los cambios en comportamiento del gasto. El paquete de contenido permite a los administradores de compras y los administradores responsables de presupuestos analizar los gastos de compra de las siguientes formas:

-   Compras hasta la fecha (por grupo de proveedores y proveedores individuales, productos de la categoría de compras e individuales y ubicación del proveedor)
-   Cambio de las compras año por año (por grupo de proveedores y categoría de compras)

## <a name="accessing-the-content-pack"></a>Acceso al paquete de contenido
El paquete de contenido del análisis de gastos de compra está publicado como un activo de la implementación en Microsoft Dynamics Lifecycle Services (LCS) y se puede acceder a él desde Microsoft Dynamics 365 for Operations. Para obtener más información acerca de cómo obtener acceso a los informes de Power BI y abrirlos, consulte [Contenido de Power BI en LCS de Microsoft y sus socios](power-bi-content-microsoft-partners.md)

## <a name="metrics-that-are-included-in-the-content-pack"></a>Métricas que se incluyen en el paquete contenido
El paquete de contenido de análisis de los gastos de compra incluye un informe compuesto por un conjunto de medidas. Estas métricas se visualizan como gráficos, mosaicos y tablas. La tabla siguiente proporciona información general de las visualizaciones del paquete de contenido.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Página de informes</th>
<th>Gráficos</th>
<th>Mosaicos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Compras por proveedor</td>
<td><ul>
<li>Los 10 principales proveedores por compra (gráfico de barras apiladas)</li>
<li>Compras totales por grupo de proveedores/país/nombre (gráfico circular)</li>
<li>Compras por grupo de proveedores/país/nombre (gráfico de columnas)</li>
<li>Promedio de compras por grupo de proveedores/país/nombre (gráfico de columnas)</li>
</ul></td>
<td><ul>
<li>Total de la compra</li>
<li>Crecimiento de compras interanual</li>
<li>N.º total de proveedores</li>
<li>N.º total de proveedores activos</li>
</ul></td>
</tr>
<tr class="even">
<td>Compras por producto</td>
<td><ul>
<li>Compras por categoría de compras o nombre del producto (gráfico de columnas)</li>
<li>Compra total por categoría de compras o nombre del producto (gráfico circular)</li>
<li>Los 10 principales productos por compra (gráfico de barras apiladas)</li>
</ul></td>
<td><ul>
<li>N.º total de productos</li>
<li>Porcentaje total de productos activos de n.º total de productos</li>
<li>Número de productos que representan el 80 % de la compra</li>
</ul></td>
</tr>
<tr class="odd">
<td>Compras por período*</td>
<td><ul>
<li>Compras por mes/día (gráfico de columnas)</li>
<li>Desviación interanual de compras acumuladas (gráfico de cascada)</li>
<li>Crecimiento total de la compra interanual (gráfico de columnas)</li>
<li>Extracto de compras (matriz)</li>
</ul></td>
<td><ul>
<li>Crecimiento de compras interanual</li>
<li>% de crecimiento de compras interanual</li>
</ul></td>
</tr>
<tr class="even">
<td>Compras por ubicación de proveedor</td>
<td><ul>
<li>Compras por ciudad</li>
<li>% de crecimiento de compras interanual</li>
<li>Compras por país</li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td>Análisis de gasto de compras por hora</td>
<td><ul>
<li>Compras de año actual por mes/día (gráfico de líneas)</li>
<li>Compras este año y el año anterior (gráficos de líneas y columnas)</li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td>Análisis de gasto de compras por proveedor</td>
<td><ul>
<li>% de compras de los 10 principales proveedores sobre el total de compras (embudo)</li>
<li>10 principales proveedores con aumento de gastos interanual</li>
<li>10 principales proveedores con disminución de gastos interanual</li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

\* Compras este año y el año anterior, y crecimiento por categoría de compras

## <a name="data-model-and-entities"></a>Modelo de datos y entidades
Los datos de Dynamics 365 for Operations se usan para el informe del paquete de contenido de análisis de gastos de compra. Estos datos se representan como medidas globales que se realizan en el almacén de la entidad, que es una base de datos de Microsoft SQL que se optimiza para análisis. Para obtener más información sobre el almacén de entidades, consulte la publicación de blog sobre [integración de Power BI con el almacén de entidades en Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Las medidas globales de este paquete de contenido son el subconjunto de las medidas globales que estaban disponibles en el cubo de compra en Microsoft Dynamics AX 2012 y Microsoft Dynamics 365 for Operations 2012 R3. Para realizar las medidas globales del cubo en el almacén de entidades debe hacer que sean desplegables. Para obtener más información, consulte el procedimiento relativo a cómo realizar mediciones globales en el almacén de entidades en el blog sobre [integración de Power BI con el almacén de entidades en Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Las siguientes medidas agregadas clave están directamente disponibles en la entidad de líneas de factura y se usan como base del paquete de contenido.

| Entidad        | Medidas agregadas clave | Origen de datos para Dynamics 365 for Operations | Campo              | Descripción                           |
|---------------|----------------------------|---------------------------------------------|--------------------|---------------------------------------|
| Líneas de factura | Compra                   | VendInvoiceTrans                            | SUM(LineAmountMST) | Importe en divisa de contabilidad |

En la tabla siguiente se muestran las medidas clave que se calculan en el paquete de contenido de la entidad de las líneas de factura.

| Medida               | Cálculo                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Año actual de compra | Año actual de compra = SUM('Líneas de factura'\[Compra\])                                            |
| Compra el año pasado    | Compra el año pasado = CALCULATE(SUM('Líneas factura'\[Compra\]), SAMEPERIODLASTYEAR(Fechas\[Fecha\]) |
| Crecimiento de compras interanual   | Crecimiento de compras interanual = \[Compra año actual\] – \[Compra el año pasado\]                            |

Las dimensiones clave siguientes del paquete de contenido se utilizan como filtros para cortar las medidas globales para lograr mayor granularidad y para profundizar en la visión analítica.

| Entidad                 | Ejemplos de atributos                                |
|------------------------|-------------------------------------------------------|
| Empresas proveedoras                | Grupos de proveedores, países o regiones de proveedores, nombre del proveedor |
| Productos               | Número de producto, nombre de producto, nombre de grupos de artículos        |
| Categorías de adquisición | Categoría de compras, nombres de la categoría de compras      |
| Entidades jurídicas         | Nombre de la entidad jurídica                                     |
| Fechas                  | Fechas, contrapartida anual                                    |

De forma predeterminada, el paquete de contenido muestra los datos del año natural actual. Sin embargo, puede cambiar el filtro de la fecha en la sección de filtros de informe. También puede cambiar el filtro de empresa.

## <a name="additional-resources"></a>Recursos adicionales
Estos son algunos vínculos útiles relacionados con las entidades y la creación de contenido de Power BI:

-   [Entidades de datos](..\data-entities\data-entities.md)
-   [Creación de paquetes de contenido organizativo](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelado de datos con Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adición de iconos de Power BI a espacios de trabajo](configure-power-bi-integration.md)



