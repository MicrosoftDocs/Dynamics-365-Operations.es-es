---
title: "Contenido de Power BI de análisis de gastos de compra"
description: "Este tema describe lo que se incluye en el paquete de contenido de análisis de gastos de compra para el BI de la potencia de Microsoft. Explica de cómo obtener acceso a los informes que se incluyen en el paquete de contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el paquete del contenido."
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

# <a name="purchase-spend-analysis-power-bi-content"></a>Contenido de Power BI de análisis de gastos de compra

Este tema describe lo que se incluye en el paquete de contenido de análisis de gastos de compra para el BI de la potencia de Microsoft. Explica de cómo obtener acceso a los informes que se incluyen en el paquete de contenido, y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el paquete del contenido.

<a name="overview"></a>Visión general
--------

El paquete de contenido de análisis de gastos de compra para el BI de la potencia de Microsoft se creó para los directores de compra y los administradores responsables de presupuestos. Se ha diseñado ayudar a vigilar los gastos de compra. Usa datos transaccionales de compra de Microsoft Dynamics 365 para las operaciones, y proporciona una visión global de las cifras empresariales de la compra y un desglose de gastos de compra por proveedor y el producto. Los informes resaltarán cambios en la compra que entran en el tiempo. Por lo tanto, se pueden usar para notificar a los administradores de las tendencias y positivas negativas de gastos para proveedores individuales y los productos. Los gráficos muestran los gastos de compra para las diversas categorías de compras y grupos de proveedores. La categoría y los administradores pueden regionales serle útil para usar estos gráficos para ayudar a identificar cambios en comportamiento del gasto. El paquete de contenido permite a los administradores de la compra y los administradores responsables de presupuestos para analizar la compra que pasan de las siguientes formas:

-   compra de la Año-a- fecha (según el grupo de proveedores y proveedores individuales, productos de la categoría de compras y de la persona, y ubicación del proveedor)
-   Cambio año a año de la compra (por grupo de proveedores y la categoría de compras)

## <a name="accessing-the-content-pack"></a>Acceso al paquete de contenido
Se publica el paquete de contenido de análisis de gastos de compra como un activo de la implementación del ciclo de vida de Microsoft Dynamics mantiene (LCS) y se puede acceder de Microsoft Dynamics 365 para las operaciones. Para obtener más información acerca de cómo obtener acceso y abrir los informes de Power BI, consulte [contenido de Power BI en el CD de Microsoft y sus socios power-bi-content-microsoft-partners.md] ().

## <a name="metrics-that-are-included-in-the-content-pack"></a>Métricas incluidos en el paquete de contenido
El paquete de contenido de análisis de gastos de compra incluye un informe compuesta por un conjunto de medidas. Estas métricas se visualizan gráficos, como los mosaicos, y tablas. La tabla siguiente proporciona una visión general de las vistas en el paquete del contenido.

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Página de informe</th>
<th>Gráficos</th>
<th>Tiles</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Compras del proveedor</td>
<td><ul>
<li>Proveedores de la parte superior 10 como la compra (gráfico de barras apiladas)</li>
<li>Compras total del grupo de proveedores/país/Nombre (gráfico circular)</li>
<li>Compras del grupo de proveedores/país/Nombre (gráfico de columnas)</li>
<li>Compras media del grupo de proveedores/país/Nombre (gráfico de columnas)</li>
</ul></td>
<td><ul>
<li>Total de la compra</li>
<li>Crecimiento de compra de YOY</li>
<li>Total # proveedores</li>
<li>Total n.º de proveedores activos</li>
</ul></td>
</tr>
<tr class="even">
<td>Por producto de la compra</td>
<td><ul>
<li>Compras por la categoría de compras o el nombre del producto (gráfico de columnas)</li>
<li>Compras total para la categoría de compras o el nombre del producto (gráfico circular)</li>
<li>Productos de la parte superior 10 como la compra (gráfico de barras apiladas)</li>
</ul></td>
<td><ul>
<li>Total n.º de productos</li>
<li>Porcentaje activo total de los productos de # total de productos</li>
<li>Número de productos que justifican la compra de 80%</li>
</ul></td>
</tr>
<tr class="odd">
<td>Compras por el period*</td>
<td><ul>
<li>Compras por el día/mes (gráfico de columnas)</li>
<li>Desviación acumulativa de la compra YOY (gráfico de la cascada)</li>
<li>Crecimiento total de la compra YOY (gráfico de columnas)</li>
<li>Extracto de compras (matriz)</li>
</ul></td>
<td><ul>
<li>Crecimiento de compra de YOY</li>
<li>Crecimiento % de compra de YOY</li>
</ul></td>
</tr>
<tr class="even">
<td>Compras por la ubicación del proveedor</td>
<td><ul>
<li>Formularios de la ciudad</li>
<li>Crecimiento % de la compra YOY</li>
<li>Compras del país</li>
</ul></td>
<td></td>
</tr>
<tr class="odd">
<td>Análisis de gastos de compra por tiempo</td>
<td><ul>
<li>Año actual de la compra por el día/mes (gráfico de líneas)</li>
<li>Actual de la compra y el último año (línea y gráfico de columnas)</li>
</ul></td>
<td></td>
</tr>
<tr class="even">
<td>Análisis de gastos de compra del proveedor</td>
<td><ul>
<li>Compras % del proveedor de la parte superior 10 de la compra (embudo)</li>
<li>Proveedores de la parte superior 10 con YOY de gastos mayor</li>
<li>Proveedores de la parte superior 10 con YOY de gasto reducido</li>
</ul></td>
<td></td>
</tr>
</tbody>
</table>

\* compra\* este año y el último año, y crecimiento por categoría de compras

## <a name="data-model-and-entities"></a>Modelo de datos y entidades
La Dynamics 365 para los datos de las operaciones se usa para el informe en el paquete de contenido de análisis de gastos de compra. Estos datos se representa como medidas globales que se realizan en el almacén de la entidad, que es una base de datos de Microsoft SQL que se optimiza para analítica. Para obtener más información sobre el almacén de la entidad, consulte [integración de Power BI al almacén de la entidad en Dynamics] (Registrar de blog de https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Las medidas globales en este paquete de contenido son el subconjunto de medidas global que estaban disponibles en el cubo de la compra en Microsoft Dynamics AX 2012 y Microsoft Dynamics 365 para las operaciones 2012 R3. Para realizar las medidas globales del cubo en el almacén de la entidad, primero deben crearse desplegables. Para obtener más información, consulte el procedimiento para realizar mediciones globales en el almacén de la entidad en [integración de Power BI al almacén de la entidad en Dynamics] (Registrar de blog de https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Las medidas siguientes de agregado de la clave están disponibles directamente de las líneas de factura y entidad se usan como base del paquete del contenido.

| Entidad        | Key aggregate measurements | Origen de datos para Dynamics 365 para las operaciones | Campo              | Descripción                           |
|---------------|----------------------------|---------------------------------------------|--------------------|---------------------------------------|
| Líneas de factura | Compra                   | VendInvoiceTrans                            | SUM (LineAmountMST) | Importe en divisa de contabilidad |

En la tabla siguiente se muestran las medidas clave que se calculan en el paquete de responsables de la entidad de las líneas de factura.

| Medida               | Cálculo                                                                                         |
|-----------------------|-----------------------------------------------------------------------------------------------------|
| Año actual de la compra | Año actual de la compra SUM = ('compra de\]\ lines'entity_PLACEHOLDER [de la factura)                                            |
| Compras el último año    | La compra el último año CALCULA = (SUM ('compra,\]) SAMEPERIODLASTYEAR (fecha de lines'entity_PLACEHOLDER\]\ [de la factura\[de las fechas)) |
| Crecimiento de compra de YOY   | Crecimiento de compra de YOY =\] año actual de la compra \[– compra el último año \[\]\[                            |

Las dimensiones siguientes clave en el paquete de contenido se utilizan como filtros para cortar las medidas globales, de modo que pueda alcanzar más granularidad y penetraciones analíticas más profundas.

| Entidad                 | Ejemplos de atributos                                |
|------------------------|-------------------------------------------------------|
| Empresas proveedoras                | País o regiones, nombre de los grupos de proveedores, del proveedor del proveedor |
| Productos               | Número de producto, nombre de producto, nombre de grupos de artículos        |
| Categorías de adquisición | Categoría de compras, nombres de la categoría de compras      |
| Entidades jurídicas         | Nombre de la entidad jurídica                                     |
| Fechas                  | Fechas, contrapartida del año                                    |

De forma predeterminada, el paquete de contenido muestra los datos por año natural actual. Sin embargo, puede cambiar el filtro de la fecha en la sección de filtros de informe. También puede modificar el filtro de la empresa.

## <a name="additional-resources"></a>Recursos adicionales
Estos son algunos vínculos útiles relacionados con las entidades y la creación de contenido de Power BI:

-   [Entidades de datos](..\data-entities\data-entities.md)
-   [Creación de paquetes de contenido organizativo](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelado de datos con Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adición de iconos de Power BI a espacios de trabajo](configure-power-bi-integration.md)



