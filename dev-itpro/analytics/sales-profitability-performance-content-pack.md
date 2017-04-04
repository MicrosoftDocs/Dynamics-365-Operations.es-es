---
title: Ventas y contenido de Power BI del rendimiento de la rentabilidad
description: "Este tema describe lo que se incluye en Dynamics 365 para las operaciones (las ventas y paquete de contenido del rendimiento de la rentabilidad para el BI de la potencia de Microsoft. Explica de cómo obtener acceso a los informes incluidos en el paquete de contenido y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el paquete del contenido."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 260674
ms.assetid: ab457f02-929e-4d34-b813-335be3092287
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 388b6398488e6f316c1ec07a00182e81c1dc8d08
ms.openlocfilehash: 3e6b48768bb8e69d46f1555d9300f3b878b01ff1
ms.lasthandoff: 03/31/2017


---

# <a name="sales-and-profitability-performance-power-bi-content"></a>Ventas y contenido de Power BI del rendimiento de la rentabilidad

Este tema describe lo que se incluye en Dynamics 365 para las operaciones (las ventas y paquete de contenido del rendimiento de la rentabilidad para el BI de la potencia de Microsoft. Explica de cómo obtener acceso a los informes incluidos en el paquete de contenido y proporciona información acerca del modelo de datos y las entidades que se utilizan para generar el paquete del contenido.

<a name="overview"></a>Visión general
--------

Este paquete de contenido se creó para que los directores de ventas controlen medidas clave de las ventas de ingresos, bruto de la prestación, y los márgenes de prestación. Usa datos transaccionales de ventas de las Dynamics 365 para operaciones, y proporciona una visión global de las cifras de ventas empresariales y un desglose de rendimiento de ventas para los clientes y los productos. Destacando cambios en los ingresos y el aumento de prestaciones en el tiempo, informes se pueden utilizar para notificar a los administradores de las tendencias y positivas negativas para los clientes individuales y los productos. La categoría y los administradores regionales lo encontrarán útil para tener gráficos que comparen los ingresos y la rentabilidad de distintos categorías de producto y grupos de clientes entre sí para resaltar rezagados y a jefes. Un informe exhaustivo que los ingresos traza de cliente individual con marcado proporciona a administradores de cuentas una base dato- apoyada para ajustar las ventas y esfuerzos de marketing al perfil respectivo de cada cliente. Ventas y los directores de ventas de permisos de paquete de contenido del rendimiento de la rentabilidad para analizar el rendimiento de ventas por:

-   Ingresos, año-a- fecha (por clientes del grupo de clientes y de la persona, las categorías de ventas, y los productos individuales y las geografías)
-   Cambio de ingresos, año a año (por regiones y las categorías de ventas del cliente)

La rentabilidad se pueda analizar por:

-   Ganancia bruto y marcado (por grupos de clientes y las categorías de ventas del producto)
-   Cambio de prestaciones bruto, año a año
-   Rentabilidad del cliente (por ingreso con margen bruto)

## <a name="accessing-the-content-pack"></a>Acceso al paquete de contenido
Se publica las ventas y el paquete de contenido de Power BI del rendimiento de la rentabilidad como un activo de la implementación del ciclo de vida mantiene (LCS) y se obtiene acceso desde Dynamics 365 para las operaciones. Para obtener más información acerca de cómo obtener acceso y poner en marcha a informes de Power BI, consulte [contenido de Power BI en el CD de Microsoft y sus socios power-bi-content-microsoft-partners.md] ().

## <a name="metrics-included-in-the-content-pack"></a>Métrica incluirá en el paquete de contenido
El paquete de contenido incluye un informe compuesta por un conjunto de medidas visualizada como gráficos, los mosaicos, y tablas. La tabla siguiente proporciona una visión general de las vistas en el paquete del contenido.

|                        |                                            |                                                         |
|------------------------|--------------------------------------------|---------------------------------------------------------|
| ** Página de informe **        | **Charts**                                 | ** Mosaicos **                                               |
| Ingresos de cliente    | Clientes de la parte superior 10 por ingresos                | Ingresos totales                                           |
|                        | Ingresos total del grupo de clientes            | Crecimiento de ingresos de YOY                                      |
|                        | Ingresos de cliente medio del grupo de clientes | Margen bruto                                            |
|                        | Ingresos prestación y bruto por grupo de clientes   |                                                         |
| Por producto de ingresos     | Ingresos prestación y bruto por categoría de ventas   | \# total de productos                                    |
|                        | Productos de la parte superior 10 por ingresos                 | Número total de productos activo y porcentaje del total |
|                        | Ingresos total por categoría de ventas            | Número de productos que explican los ingresos del 80%           |
| Ingresos por el período\*    | Ingresos por mes                           | Crecimiento de ingresos de YOY                                      |
|                        | Desviación final de ingresos, YOY             | Crecimiento % de ingresos de YOY                                    |
|                        | Desviación de ventas total por región del cliente    |                                                         |
| Ingresos por ubicación    | Ingresos de ventas de la ciudad                      |                                                         |
|                        | Crecimiento % de ingresos de YOY                       |                                                         |
|                        | Ingresos de ventas por región                    |                                                         |
| Rentabilidad del cliente | Margen bruto con ingresos, por el cliente   | Ganancia bruto, margen bruto, crecimiento de ingresos de YOY          |
| Análisis de rentabilidad | Ingresos prestación y bruto por mes          |                                                         |
|                        | Clientes de la parte superior 15 por margen bruto           |                                                         |
|                        | Ganancia bruto por el mes, YOY                 |                                                         |

ingresos\* este\* y el último año, y crecimiento por categoría de ventas.

## <a name="understanding-the-data-model-and-entities"></a>Comprensión del modelo de datos y de las entidades
La Dynamics 365 para los datos de las operaciones se usa para rellenar el informe en el paquete de contenido del rendimiento de la rentabilidad. Esto se representa como medidas globales que se realizan en el almacén de la entidad, que es una base de datos de Microsoft SQL optimizada para analítica. Lea más información acerca de ella en la blog [integración de Power BI con la entidad almacenada en Dynamics] (https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Las medidas globales en este paquete de contenido son el subconjunto de las medidas global que estaban disponibles en el cubo de ventas en Dynamics AX 2012 y AX 2012 R3. Para realizar las medidas globales del cubo en la entidad almacenele debe crearlas desplegables. Para obtener más información, consulte el procedimiento relativa a cómo realizar mediciones globales en el almacén de la entidad en el blog [integración de Power BI con la entidad almacenada en Dynamics] (https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Las medidas siguientes de agregado de la clave de la entidad de las líneas de factura se usan como base del paquete del contenido.

|               |                                              |                                                 |                                              |                                          |
|---------------|----------------------------------------------|-------------------------------------------------|----------------------------------------------|------------------------------------------|
| **Entity**    | ** Medidas globales clave **               | ** Origen de datos para Dynamics 365 para las operaciones ** | **Field**                                    | **Description**                          |
| Líneas de factura | Ingresos                                      | CustInvoiceTrans                                | SUM (LineAmountMST)                           | Importe en la divisa de contabilidad            |
|               | Coste de bienes vendidos                           | InventTrans                                     | SUM CostAmountPosted (+) CostAmountAdjustment | Importe de coste + ajuste                 |
|               | Importe de línea de la comisión – divisa de contabilidad | CustInvoiceTrans                                | SUM (CommissAmountMST)                        | Importe de la comisión en la divisa de contabilidad |

En la tabla siguiente se muestran las medidas cierre globales de la entidad de las líneas de factura que se usan para crear varias medidas calculadas en el conjunto de datos de embalaje del contenido.

|                   |                                                                                                  |
|-------------------|--------------------------------------------------------------------------------------------------|
| **Measure**       | ** Se calculan como **                                                                                |
| Ganancias brutas      | SUM ingresos – (COGS – Grupo de impuestos – (incluidos en el importe de la línea de factura de cliente))          |
| Margen bruto      | SUM (prestación bruto/(ingresos - impuestos (incluidos en el importe de la línea de factura de cliente)))             |
| Ingresos el último año | Los ingresos el último año CALCULA = (SUM ('ingresos\]), SAMEPERIODLASTYEAR (fecha de lines'entity_PLACEHOLDER\]\ [de la factura\[de las fechas) |

Las dimensiones clave siguientes en ** cubo de ventas ** se utilizan como filtros para cortar las medidas globales para lograr granularidad contabilidad y penetraciones analíticas más profundas.

|                  |                                                      |
|------------------|------------------------------------------------------|
| **Entity**       | ** Ejemplos de atributos **                           |
| Empresas cliente        | Grupos de clientes, regiones del cliente, dirección, sector |
| Productos         | Número de producto, nombre de producto, nombre de grupos de artículos       |
| Categorías de ventas | Nombres de la categoría de ventas                                 |
| Entidades jurídicas   | Nombres de entidad jurídica                                   |
| Fechas            | Fechas                                                |

De forma predeterminada, el embalaje y muestra los datos por año natural actual, pero puede abrir la sección de filtros de informe y cambiar el filtro de fecha. También puede modificar el filtro de la empresa.

## <a name="additional-resources"></a>Recursos adicionales
Estos son algunos vínculos útiles relacionados con las entidades y la creación de contenido de Power BI:

-   [Entidades de datos](..\data-entities\data-entities.md)
-   [Creación de paquetes de contenido organizativo](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelado de datos con Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adición de iconos de Power BI a espacios de trabajo](configure-power-bi-integration.md)



