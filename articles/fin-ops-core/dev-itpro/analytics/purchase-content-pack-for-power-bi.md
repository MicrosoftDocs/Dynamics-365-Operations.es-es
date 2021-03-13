---
title: Contenido de Power BI del análisis de compras y gastos
description: Este tema describe lo que se incluye en el contenido de Power BI acerca de análisis de compras y gastos.
author: FrankDahl
manager: AnnBe
ms.date: 04/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: PurchaseSpendAnalysisPowerBI
audience: Application User, IT Pro
ms.reviewer: kfend
ms.custom: 265434
ms.assetid: 3cd9dfce-2687-4303-bc78-349e7cb5ea75
ms.search.region: global
ms.author: fdahl
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 5914abaafab509e278d7a85441928feddb0b5164
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093451"
---
# <a name="purchase-spend-analysis-power-bi-content"></a>Contenido de Power BI del análisis de compras y gastos

[!include [banner](../includes/banner.md)]

Este tema describe lo que se incluye en el contenido de Microsoft Power BI acerca de **análisis de compras y gastos**. Explica cómo obtener acceso a los informes de Power BI y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el contenido.

## <a name="overview"></a>Información general

El contenido de Power BI sobre **Análisis de compras y gastos** se ha diseñado para ayudar a directores de compras y los administradores responsables de presupuestos y seguir los gastos en adquisiciones. Los directores pueden analizar su gasto en adquisiciones de las siguientes formas:

- Compras hasta la fecha (por grupo de proveedores y proveedores individuales, productos de la categoría de compras e individuales y ubicación del proveedor)
- Cambio de las compras año por año (por grupo de proveedores y categoría de compras)

El contenido usa datos transaccionales de compras y proporciona tanto una visión global de las cifras de compras en la empresa como un desglose de los gastos en compras por proveedor y producto. Los informes resaltan cambios en los gastos de compra a lo largo del tiempo. Por lo tanto, los informes se pueden usar para notificar a los administradores las tendencias positivas y negativas de los gastos relativas a proveedores y productos individuales. Además, los gráficos muestran los gastos de compra para las diversas categorías de compras y grupos de proveedores. Por lo tanto, los administradores de categorías y regionales pueden utilizar los gráficos como ayuda para identificar los cambios en comportamiento del gasto.

## <a name="accessing-the-power-bi-content"></a>Acceso al contenido de Power BI
El contenido de Power BI **Análisis de compras y gastos** se muestra en la página **Análisis de compras y gastos** (**Adquisición y abastecimiento** \> **Consultas e informes** \> **Análisis del rendimiento de compra** \> **Análisis de compras y gastos**).

## <a name="metrics-that-are-included-in-the-power-bi-content"></a>Métricas que se incluyen en el contenido de Power BI
El contenido de Power BI de **análisis de los gastos de compra** incluye un informe compuesto por un conjunto de medidas. Estas métricas se visualizan como gráficos, mosaicos y tablas. 

Las secciones siguientes muestran una visión general de las visualizaciones.

### <a name="purchase-by-vendor-report-page"></a>Compras por página del informe del proveedor
**Gráficos**
- Los 10 principales proveedores por compra (gráfico de barras apiladas)
- Compras totales por grupo de proveedores/país/nombre (gráfico circular)
- Compras por grupo de proveedores/país/nombre (gráfico de columnas)
- Promedio de compras por grupo de proveedores/país/nombre (gráfico de columnas)

**Mosaicos**
- Total de la compra
- Crecimiento de compras interanual
- N.º total de proveedores
- N.º total de proveedores activos

**Ejemplo**
<img src="media/spend1.png" alt="Purchase by vendor">

### <a name="purchase-by-product-report-page"></a>Compras por página del informe de producto

**Gráficos**
- Compras por categoría de compras o nombre del producto (gráfico de columnas)
- Compra total por categoría de compras o nombre del producto (gráfico circular)
- Los 10 principales productos por compra (gráfico de barras apiladas)

**Mosaicos**
- N.º total de productos</li>
- Porcentaje total de productos activos de n.º total de productos
- Número de productos que representan el 80 % de la compra

**Ejemplo**


<img src="media/purchaseByProduct.png" alt="Purchase by Product">

### <a name="purchase-by-period-report-page"></a>Compras por página del informe de período
Esta página muestra compras este año y el año anterior, y crecimiento por categoría de compras.

**Gráficos** 
- Compras por mes/día (gráfico de columnas)
- Desviación interanual de compras acumuladas (gráfico de cascada)
- Crecimiento total de la compra interanual (gráfico de columnas)
- Extracto de compras (matriz)

**Mosaicos**
- Crecimiento de compras interanual
- % de crecimiento de compras interanual

**Ejemplo**
<img src="media/purchaseByPeriod.png" alt="Purchase by Period">

### <a name="purchase-by-vendor-location-report-page"></a>Compras por página del informe de ubicación

**Gráficos**
- Compras por ciudad
- % de crecimiento de compras interanual
- Compras por país

**Ejemplo**
<img src="media/purchByVendorLocation.png" alt="Purchase by Vendor Location">

### <a name="purchase-spend-analysis-by-time-report-page"></a>Análisis de gasto de compras por página de hora del informe

**Gráficos** 
- Compras de año actual por mes/día (gráfico de líneas)
- Compras este año y el año anterior (gráficos de líneas y columnas)

**Ejemplo**
<img src="media/PurchByTIme.png" alt="Purchase by Time">

### <a name="purchase-spend-analysis-by-vendor-report-page"></a>Análisis de gasto de compras por página de proveedor del informe

**Gráficos** 
- % de compras de los 10 principales proveedores sobre el total de compras (embudo)
- 10 principales proveedores con aumento de gastos interanual
- 10 principales proveedores con disminución de gastos interanual

**Ejemplo** 
<img src="media/PurchSpendAnalysisByVendor.png" alt="Purchase spend by vendor">


## <a name="data-model-and-entities"></a>Modelo de datos y entidades
Los datos siguientes se usan para rellenar las páginas de informes en el contenido de Power BI sobre **Análisis de compras y gastos**. Estos datos se representan como medidas agregadas que se realizan en el almacén de la entidad. El almacén de la entidad es una base de datos de Microsoft SQL Server que se optimiza para el análisis. Para obtener más información, consulte [Integración de Power BI con el almacén de entidades](power-bi-integration-entity-store.md).

Las medidas globales de este paquete de contenido son el subconjunto de las medidas globales que estaban disponibles en el cubo de compra en Microsoft Dynamics AX 2012 y Microsoft Dynamics AX 2012 R3. Para realizar las medidas globales del cubo en el almacén de entidades debe hacer que sean desplegables. Para obtener más información, consulte el procedimiento relativo a cómo realizar mediciones globales en el almacén de entidades en [Visión general de la integración de Power BI con el almacén de entidades](power-bi-integration-entity-store.md). Las siguientes medidas agregadas clave están directamente disponibles en la entidad de líneas de factura y se usan como base del contenido.

| Entidad        | Medidas agregadas clave | Origen de datos                                 | Campo              | Descripción                            |
|---------------|----------------------------|---------------------------------------------|--------------------|----------------------------------------|
| Líneas de factura | Compra                   | VendInvoiceTrans                            | SUM(LineAmountMST) | El importe en la divisa de contabilidad. |

En la tabla siguiente se muestran las medidas clave del contenido que se calculan a partir de la entidad de las líneas de factura.

| Medida               | Cálculo                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Año actual de compra | Año actual de compra = SUM('Líneas de factura'\[Compra\])                                            |
| Compra el año pasado    | Compra el año pasado = CALCULATE(SUM('Líneas factura'\[Compra\]), SAMEPERIODLASTYEAR(Fechas\[Fecha\])) |
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
