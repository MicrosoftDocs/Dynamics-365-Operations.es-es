---
title: Contenido de Power BI para rendimiento de la rentabilidad y las ventas
description: "Este tema describe lo que se incluye en el paquete de contenido de rendimiento de la rentabilidad y las ventas de Dynamics 365 for Operations para Microsoft Power BI. Explica cómo tener acceso a los informes que se incluyen en el paquete de contenido, y proporciona información acerca del modelo de datos y las entidades que se usan para generar el paquete del contenido."
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

# <a name="sales-and-profitability-performance-power-bi-content"></a>Contenido de Power BI para rendimiento de la rentabilidad y las ventas

Este tema describe lo que se incluye en el paquete de contenido de rendimiento de la rentabilidad y las ventas de Dynamics 365 for Operations para Microsoft Power BI. Explica cómo tener acceso a los informes que se incluyen en el paquete de contenido, y proporciona información acerca del modelo de datos y las entidades que se usan para generar el paquete del contenido.

<a name="overview"></a>Visión general
--------

Este paquete de contenido se creó para que los directores de ventas controlen medidas clave de las ventas de los ingresos, las ganancias brutas y los márgenes de prestación. Usa datos transaccionales de ventas de Dynamics 365 for Operations y proporciona una visión global de las cifras de ventas empresariales y un desglose de rendimiento de ventas para los clientes y los productos. Al destacar los cambios en el crecimiento de los ingresos y las ganancias en el tiempo, los informes se pueden utilizar para notificar a los administradores de las tendencias positivas y negativas para clientes y productos individuales. Los administradores de categorías y regionales lo encontrarán útil para tener gráficos que comparen los ingresos y la rentabilidad de distintas categorías de productos y grupos de clientes entre sí para resaltar a los rezagados y los que van en primer lugar. Un informe exhaustivo que compara los ingresos del cliente individual con el margen de beneficio proporciona a los administradores de cuentas una base fundada en datos para ajustar las ventas y los esfuerzos de marketing al perfil respectivo de cada cliente. El paquete de rendimiento de rentabilidad y ventas permite a los directores de ventas analizar el rendimiento de ventas por:

-   Ingresos, año hasta la fecha (por grupos de clientes y clientes individuales, categorías de ventas, y productos individuales y geografías)
-   Cambio de ingresos, año a año (por regiones y categorías de ventas del cliente)

La rentabilidad se pueda analizar por:

-   Ganancia bruta y margen de beneficio (por grupos de clientes y categorías de ventas de producto)
-   Cambio de ganancias brutas, año a año
-   Rentabilidad del cliente (por ingreso comparado con margen bruto)

## <a name="accessing-the-content-pack"></a>Acceso al paquete de contenido
El paquete de contenido del rendimiento de la rentabilidad y las ventas para Power BI está publicado como un activo de la implementación en Lifecycle Services (LCS) y se puede acceder a él desde Dynamics 365 for Operations. Para obtener más información acerca de cómo obtener acceso a los informes de Power BI e iniciarlos, consulte [Contenido de Power BI en LCS de Microsoft y sus socios](power-bi-content-microsoft-partners.md)

## <a name="metrics-included-in-the-content-pack"></a>Métricas incluidas en el paquete de contenido
El paquete de contenido incluye un informe compuesto por un conjunto de medidas visualizadas como gráficos, mosaicos, y tablas. La tabla siguiente proporciona información general de las visualizaciones del paquete de contenido.

|                        |                                            |                                                         |
|------------------------|--------------------------------------------|---------------------------------------------------------|
| **Página de informes**        | **Gráficos**                                 | **Mosaicos**                                               |
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
Los datos de Dynamics 365 for Operations se utilizan para rellenar los informes del paquete de contenido de rendimiento de la rentabilidad y las ventas. Esto se representa como medidas globales que se realizan en el almacén de la entidad, que es una base de datos de Microsoft SQL que se optimiza para análisis. Lea más información sobre este tema en el blog [Integración de Power BI con el almacén de entidades en Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Las medidas globales de este paquete de contenido son el subconjunto de las medidas globales que estaban disponibles en el cubo de venta en Dynamics AX 2012 y AX 2012 R3. Para realizar las medidas globales del cubo en el almacén de entidades debe hacer que sean desplegables. Para obtener más información, consulte el procedimiento relativo a cómo realizar mediciones globales en el almacén de entidades en el blog [Integración de Power BI con el almacén de entidades en Dynamics](https://blogs.msdn.microsoft.com/dynamicsaxbi/2016/06/09/power-bi-integration-with-entity-store-in-dynamics-ax-7-may-update/). Las siguientes medidas agregadas clave de la entidad de líneas de factura se usan como base del paquete de contenido.

|               |                                              |                                                 |                                              |                                          |
|---------------|----------------------------------------------|-------------------------------------------------|----------------------------------------------|------------------------------------------|
| **Entidad**    | **Medidas agregadas clave**               | **Origen de datos para Dynamics 365 for Operations** | **Campo**                                    | **Descripción**                          |
| Líneas de factura | Ingresos                                      | CustInvoiceTrans                                | SUM(LineAmountMST)                           | Importe en la divisa de contabilidad            |
|               | Coste de bienes vendidos                           | InventTrans                                     | SUM(CostAmountPosted + CostAmountAdjustment) | Importe del coste + ajuste                 |
|               | Importe de la línea de comisión - divisa de contabilidad | CustInvoiceTrans                                | SUM(CommissAmountMST)                        | Importe de la comisión en divisa de contabilidad |

Se usará la tabla siguiente para mostrar cómo se usan las medidas agregadas clave de la entidad de líneas de factura para crear varias medidas calculadas en el conjunto de datos del paquete de contenido.

|                   |                                                                                                  |
|-------------------|--------------------------------------------------------------------------------------------------|
| **Medida**       | **Calculado como**                                                                                |
| Ganancias brutas      | SUM(Ingresos – COGS – Comisión – Impuestos (incluidos en el importe de la línea de factura de cliente))          |
| Margen bruto      | SUM(Ganancias brutas / (Ingresos - Impuestos (incluidos en el importe de la línea de factura de cliente)))             |
| Ingresos el último año | Ingresos el último año = CALCULATE(SUM('Líneas factura'\[Ingresos\]), SAMEPERIODLASTYEAR(Fechas\[Fecha\]) |

Las dimensiones clave siguientes del **cubo de venta** se utilizan como filtros para cortar las medidas globales para lograr mayor granularidad y para profundizar en la visión analítica.

|                  |                                                      |
|------------------|------------------------------------------------------|
| **Entidad**       | **Ejemplos de atributos**                           |
| Empresas cliente        | Grupos de clientes, regiones de clientes, dirección, sector |
| Productos         | Número de producto, nombre de producto, nombre de grupos de artículos       |
| Categorías de ventas | Nombres de categoría de ventas                                 |
| Entidades jurídicas   | Nombres de entidad jurídica                                   |
| Fechas            | Fechas                                                |

De forma predeterminada, el paquete de contenido muestra los datos por año natural actual, pero puede abrir la sección de filtros de informe y cambiar el filtro de fecha. También puede cambiar el filtro de empresa.

## <a name="additional-resources"></a>Recursos adicionales
Estos son algunos vínculos útiles relacionados con las entidades y la creación de contenido de Power BI:

-   [Entidades de datos](..\data-entities\data-entities.md)
-   [Creación de paquetes de contenido organizativo](https://powerbi.microsoft.com/en-us/documentation/powerbi-service-organizational-content-packs-introduction/)
-   [Modelado de datos con Power BI](https://powerbi.microsoft.com/en-us/guided-learning/powerbi-learning-2-1-intro-modeling-data)
-   [Adición de iconos de Power BI a espacios de trabajo](configure-power-bi-integration.md)



