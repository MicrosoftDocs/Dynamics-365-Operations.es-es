---
title: "Contenido de Power BI sobre análisis de gastos de compra"
description: "Este tema describe lo que se incluye en el contenido de Power BI acerca de análisis de compras y gastos. Explica cómo tener acceso a los informes que se incluyen en el contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido."
author: FrankDahl
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 3e42746329b1194c0ce0e2fb5c476742259a5b43
ms.contentlocale: es-es
ms.lasthandoff: 09/29/2017

---

# <a name="purchase-spend-analysis-power-bi-content"></a>Contenido de Power BI sobre análisis de gastos de compra

[!include[banner](../includes/banner.md)]

Este tema describe lo que se incluye en el contenido de Microsoft Power BI acerca de **Análisis de compras y gastos**. Explica cómo obtener acceso a los informes de Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.

## <a name="overview"></a>Información general

El contenido de Power BI sobre **Análisis de compras y gastos** se ha diseñado para ayudar a directores de compras y los administradores responsables de presupuestos a vigilar los gastos en adquisiciones. Los directores pueden analizar su gasto en adquisiciones de las siguientes formas:

-   Compras hasta la fecha (por grupo de proveedores y proveedores individuales, productos de la categoría de compras e individuales y ubicación del proveedor)
-   Cambio de las compras año por año (por grupo de proveedores y categoría de compras)

El contenido usa datos transaccionales de compras y proporciona tanto una visión global de las cifras de compras en la empresa como un desglose de los gastos en compras por proveedor y producto. Los informes resaltan cambios en los gastos de compra a lo largo del tiempo. Por lo tanto, los informes se pueden usar para notificar a los administradores las tendencias positivas y negativas de los gastos relativas a proveedores y productos individuales. Además, los gráficos muestran los gastos de compra para las diversas categorías de compras y grupos de proveedores. Por lo tanto, los administradores de categorías y regionales pueden utilizar los gráficos como ayuda para identificar los cambios en comportamiento del gasto.

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI
Si usa Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (julio de 2017), el contenido de Power BI sobre **Análisis de compras y gastos** se muestra en la página **Análisis de compras y gastos** (**Adquisición y abastecimiento** > **Consultas e informes** > **Análisis del rendimiento de compra** > **Análisis de compras y gastos**). 

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Métricas que se incluyen en el contenido de Power BI
El contenido de Power BI sobre **Análisis de compras y gastos** incluye un informe compuesto por un conjunto de métricas. Estas métricas se visualizan como gráficos, mosaicos y tablas. La tabla siguiente muestra una visión general de las visualizaciones.

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

## <a name="extending-the-power-bi-content"></a>Ampliar el contenido de Power BI
Mediante los paquetes de contenido disponibles en Microsoft Dynamics Lifecycle Services (LCS), puede ofrecer análisis muy buenos a las personas que no inician sesión en Microsoft Dynamics 365. Puede modificar estos paquetes de contenido para que incluyan otros informes o representaciones visuales y, a continuación, publicar los paquetes de contenidos en el inquilino de Power BI.com para su análisis. 

Puede encontrar el contenido de Power BI sobre **Análisis de compras y gastos** en la biblioteca de activos compartidos de LCS. Para obtener información sobre cómo descargar contenido e implementarlo en su organización, consulte [Contenido de Power BI en LCS en Microsoft y sus socios](power-bi-content-microsoft-partners.md). Para ver una demostración que muestra cómo implementar el contenido de Power BI, consulte [Contenido de Power BI de Microsoft y sus socios en Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) (Office Mix).

Asegúrese de descargar el contenido **Análisis de compras y gastos** que se aplica a la versión de Dynamics 365 que esté usando.

> [!NOTE]
> Si utiliza Microsoft Dynamics 365 for Operations, versión 1611, KB 4011327 es un requisito para este contenido de Power BI. Tras iniciar sesión en LCS, puede acceder a KB en https://fix.lcs.dynamics.com/issue/results/?q=kb4011327.

## <a name="data-model-and-entities"></a>Modelo de datos y entidades
Los datos siguientes se usan para rellenar las páginas de informes en el contenido de Power BI sobre **Análisis de compras y gastos**. Estos datos se representan como medidas agregadas que se realizan en el almacén de la entidad. El almacén de la entidad es una base de datos de Microsoft SQL Server que se optimiza para el análisis. Para obtener más información, consulte [Visión general de la integración de Power BI con el almacén de entidades](power-bi-integration-entity-store.md).

Las medidas agregadas en este contenido son el subconjunto de las medidas agregadas que estaban disponibles en el cubo de compra en Microsoft Dynamics AX 2012 y Microsoft Dynamics AX 2012 R3. Para realizar las medidas globales del cubo en el almacén de entidades debe hacer que sean desplegables. Para obtener más información, consulte el procedimiento relativo a cómo realizar mediciones globales en el almacén de entidades en [Visión general de la integración de Power BI con el almacén de entidades](power-bi-integration-entity-store.md). Las siguientes medidas agregadas clave están directamente disponibles en la entidad de líneas de factura y se usan como base del contenido.

| Entidad        | Medidas agregadas clave | Origen de datos                                 | Campo              | Descripción                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| Líneas de factura | Compra                   | VendInvoiceTrans                            | SUM(LineAmountMST) | El importe en la divisa de contabilidad. |

En la tabla siguiente se muestran las medidas clave del contenido que se calculan a partir de la entidad de las líneas de factura.

| Medida               | Cálculo                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Año actual de compra | Año actual de compra = SUM('Líneas de factura'\[Compra\])                                            |
| Compra el año pasado    | Compra el año pasado = CALCULATE(SUM('Líneas factura'\[Compra\]), SAMEPERIODLASTYEAR(Fechas\[Fecha\]) |
| Crecimiento de compras interanual   | Crecimiento de compras interanual = \[Compra año actual\] – \[Compra el año pasado\]                            |

Las dimensiones clave siguientes del contenido se utilizan como filtros para cortar las medidas globales para lograr mayor granularidad y profundizar en la visión analítica.

| Entidad                 | Ejemplos de atributos                                |
|------------------------|-------------------------------------------------------|
| Empresas proveedoras                | Grupos de proveedores, países o regiones de proveedores, nombre del proveedor |
| Productos               | Número de producto, nombre de producto, nombre de grupos de artículos        |
| Categorías de adquisición | Categoría de compras, nombres de la categoría de compras      |
| Entidades jurídicas         | Nombre de la entidad jurídica                                     |
| Fechas                  | Fechas, contrapartida anual                                    |

De forma predeterminada, el contenido muestra los datos del año natural actual. Sin embargo, puede cambiar el filtro de la fecha en la sección de filtros de informe. También puede cambiar el filtro de empresa.

