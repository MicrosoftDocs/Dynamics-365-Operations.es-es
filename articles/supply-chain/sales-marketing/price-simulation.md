---
title: "Simulación de precios"
description: "Este artículo proporciona información acerca de la simulación de precios para los presupuestos. La simulación de precios le ayuda a evaluar el efecto de las deducciones en el precio de venta futuro durante el proceso de presupuesto, antes de confirmar un precio determinado."
author: omulvad
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesQuotationPriceSimulation
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 12254
ms.assetid: 92be7c85-73cf-4f77-833c-d37ce779a031
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 1db68ea5728cc417f0e70675d9074d5b054883da
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="price-simulation"></a>Simulación de precios

[!INCLUDE [banner](../includes/banner.md)]

Este artículo proporciona información acerca de la simulación de precios para los presupuestos. La simulación de precios le ayuda a evaluar el efecto de las deducciones en el precio de venta futuro durante el proceso de presupuesto, antes de confirmar un precio determinado.

Una simulación de precios para un presupuesto muestra un importe total nuevo, basado en un nuevo precio propuesto. Una simulación de precios también puede mostrar un importe nuevo para una línea específica que se crea en un presupuesto existente. Puede introducir una simulación de precios y aplicarla posteriormente. También puede usar el presupuesto original, sin simulación de precios, y realizar cambios adicionales a medida que avanza por el proceso de ventas con el cliente.  

Una simulación de precios no cambia el precio del presupuesto. Si la simulación de precios se aplica a todo el presupuesto, se trata como un descuento especial en el encabezado del presupuesto. Si la simulación de precios se aplica a artículos específicos, se trata como un descuento especial en las líneas de presupuesto. El precio unitario de venta de una línea de presupuesto que se crea no cambia cuando se aplique una simulación de precio. En cambio, se aplica un porcentaje de descuento que corresponda a la reducción de precios de la línea de presupuesto. Cuando se aplique una simulación de precios, el precio unitario y el porcentaje de descuento se transfieren a la línea de presupuesto o encabezado de presupuesto.  

**Nota:** cuando se realice una simulación de precios, únicamente se usa la divisa de ventas para crear la simulación. No obstante, al visualizar los totales de presupuesto, verá una combinación de la divisa de empresa y la de ventas.  

Los artículos adicionales que se agregan a líneas de presupuesto pueden desencadenar descuentos de línea o descuentos multilínea. También podrían desencadenar descuentos totales que modifiquen los márgenes y coeficientes de contribución de las líneas de presupuesto y el descuento completo.  

Puede ejecutar varias simulaciones de precios para realizar un seguimiento de los efectos de los ajustes de precios en los objetivos del presupuesto. Al ejecutar estas simulaciones, puede ajustar el precio global del presupuesto o el precio de una o más líneas específicas del presupuesto y, a continuación, aplicar la simulación de precios con mayor probabilidad de terminar en una venta.  

Al crear un presupuesto, puede configurar una alerta. Estas son algunas de las maneras en que se usan las alertas:

-   Pueden mantenerle informado acerca del estado de los presupuestos de la organización.
-   Pueden desencadenar una revisión de un presupuesto en particular o informarle cuando se han superado los límites de descuento.

## <a name="price-simulation-and-discounts"></a>Simulación de precios y descuentos
Para garantizar que los descuentos y precios se calculan correctamente, preste atención al ejecutar simulaciones de precios en presupuestos que tienen descuentos. Dado que todas las simulaciones de precios se tratan como descuentos especiales en la línea de presupuesto activa o en el presupuesto completo, debe realizar un seguimiento de las diferencias en los descuentos.

### <a name="types-of-discounts-in-trade-agreements"></a>Tipos de descuentos de acuerdos comerciales

Los acuerdos comerciales de Microsoft Dynamics 365 for Finance and Operations pueden tener cuatro tipos descuentos. Estos descuentos pueden configurarse para diferentes artículos, clientes o grupos de precios, y pueden estar limitados por fecha. Para evitar cálculos erróneos, debe tener en cuenta los acuerdos comerciales al ejecutar simulaciones de precios. Estos son los cuatro tipos de descuentos de los acuerdos comerciales:

-   **Precio de ventas**: se pueden especificar precios de ventas independientes de artículos. Cuando se crean las líneas de presupuesto, el programa busca el precio de venta correcto de un artículo y lo transfiere a las líneas de presupuesto. Por lo tanto, un acuerdo comercial con este tipo de descuento no afecta a la simulación de precios. El precio de venta que se usa en la línea de presupuesto refleja el acuerdo comercial.
-   **Descuento de línea**: se especifican descuentos de artículos especiales en función de la cantidad pedida. Los importes de línea suelen reducirse por el descuento de línea anterior a la ejecución de la simulación de precios. Por lo tanto, un acuerdo comercial con este tipo de descuento sí afecta a la simulación de precios.
-   **Descuento multilínea**: si las cantidades combinadas superan el límite que ha definido, las combinaciones predefinidas de artículos pedidos activan un descuento en todo el pedido. Los importes de línea suelen reducirse por el descuento de línea anterior a la ejecución de la simulación de precios. Por lo tanto, un acuerdo comercial con este tipo de descuento sí afecta a la simulación de precios.
-   **Descuento total**: si los importes combinados superan el límite que ha definido, los artículos pedidos predefinidos activan un descuento en todo el pedido. El descuento total se genera por las líneas de presupuesto. No obstante, debido a que el descuento total se aplica al total del presupuesto como un descuento, se reduce el importe total del presupuesto. Por lo tanto, un acuerdo comercial con este tipo de descuento sí afecta a la simulación de precios.

### <a name="quotation-lines-and-trade-agreements"></a>Líneas de presupuesto y acuerdos comerciales

Al crear o ajustar una línea de presupuesto, los descuentos de línea se calculan automáticamente. Se encuentra el precio de venta relevante para el artículo, según el acuerdo comercial.

## <a name="price-simulation-examples"></a>Ejemplos de simulación de precios
Los ejemplos siguientes utilizan la simulación de precios para encabezados de presupuesto y artículos de una línea.

### <a name="price-simulation-for-quotation-headers"></a>Simulación de precios para encabezados de presupuesto

Crea un presupuesto con las siguientes líneas:

-   10 unidades del artículo BR-12 (precio de coste por unidad 9,52 USD y precio de venta por unidad 15,32 USD)
-   12 unidades del artículo BR-14 (precio de coste por unidad 7,48 USD y precio de venta por unidad 13,75 USD)

La tabla siguiente muestra las líneas de presupuesto.

|                            | Cálculo                          | Resultado   |
|----------------------------|--------------------------------------|----------|
| Cantidad de ventas             | 10 unidades + 12 unidades                  | 22 unidades |
| Valor de ventas en USD         | (10 × 15,32) + (12 × 13,75)          | 318,20   |
| Valor de coste en USD          | (10 × 9,52) + (12 × 7,48)            | 184,96   |
| Margen de contribución en USD | 318,20 – 184,96                      | 133,24   |
| Coeficiente de contribución         | (\[318,20 – 184,96\] ÷ 318,20) × 100 | 41,87%   |

Ejecuta una simulación de precios y aplica un 15 por ciento de descuento total para todo el presupuesto o el encabezado del presupuesto. La siguiente tabla muestra los nuevos totales del presupuesto una vez ejecutada la simulación de precios.

|                                                      | Cálculo                               | Resultado   |
|------------------------------------------------------|-------------------------------------------|----------|
| Cantidad de ventas                                       | 10 unidades + 12 unidades                       | 22 unidades |
| Valor de ventas antiguo en USD                               | (10 × 15,32) + (12 × 13,75)               | 318,20   |
| Valor de coste antiguo en USD                                | (10 × 9,52) + (12 × 7,48)                 | 184,96   |
| Margen de contribución antiguo en USD                       | 318,20 – 184,96                           | 133,24   |
| Coeficiente de contribución antiguo                               | (\[318,20 – (10 × 9,52)\] ÷ 318,20) × 100 | 41,87%   |
| Simulación de precios de 15 % de descuento total en USD | (15 × 318,2) ÷ 100                        | 47,73    |
| Valor de ventas nuevo en USD                               | 318,20 – 47,73                            | 270,47   |
| Margen de contribución nuevo en USD                       | 270,47 – 184,96                           | 85,51    |
| Nuevo coeficiente de contribución                               | \[(270,47 – 184,96) ÷ 270,47\] × 100      | 31,61%   |

### <a name="price-simulation-for-single-line-items"></a>Simulación de precios de artículos de una sola línea

Crea un presupuesto con las siguientes líneas:

-   10 unidades del artículo BR-12 (precio de coste por unidad 9,52 USD y precio de venta por unidad 15,32 USD)
-   12 unidades del artículo BR-14 (precio de coste por unidad 7,48 USD y precio de venta por unidad 13,75 USD)

La tabla siguiente muestra las líneas de presupuesto.

|                                      | Cálculo                          | Resultado   |
|--------------------------------------|--------------------------------------|----------|
| Cantidad de ventas                       | 10 unidades + 12 unidades                  | 22 unidades |
| Valor de ventas en USD para BR-12         | 10 × 15,32                           | 153,20   |
| Valor de ventas en USD para BR-14         | 12 × 13,75                           | 165,00   |
| Valor de coste en USD para BR-12          | 10 × 9,52                            | 95,20    |
| Valor de coste en USD para BR-14          | 12 × 7,48                            | 89,76    |
| Margen de contribución en USD para BR-12 | 153,20 - 95,20                       | 58,00    |
| Margen de contribución en USD para BR-14 | 165,00 - 89,76                       | 75,24    |
| Coeficiente de contribución en USD para BR-12  | \[(153,20 – 95,20) ÷ 153,20\] × 100  | 37,86    |
| Coeficiente de contribución en USD para BR-14  | \[(165,00 – 89,76) ÷ 165,00\] × 100  | 45,60    |
| Valor de ventas total en USD             | (10 × 15,32) + (12 × 13,75)          | 318,20   |
| Valor de coste total en USD              | (10 × 9,52) + (12 × 7,48)            | 184,96   |
| Margen de contribución total en USD     | 318,20 – 184,96                      | 133,24   |
| Coeficiente de contribución total             | \[(318,20 – 184,96) ÷ 318,20\] × 100 | 41,87%   |

Ejecuta una simulación de precios y aplica un descuento total del 10 por ciento a las unidades BR-12. La siguiente tabla muestra los nuevos totales del presupuesto una vez ejecutada la simulación de precios para el artículo de línea única.

|                                                   | Cálculo                             | Resultado   |
|---------------------------------------------------|-----------------------------------------|----------|
| Cantidad de ventas                                    | 10 unidades + 12 unidades                     | 22 unidades |
| Valor de ventas antiguo en USD para BR-12                  | 10 × 15,32                              | 153,20   |
| Simulación de precios de 10 % de descuento para BR-12 | (10 × 153,2) ÷ 100                      | 15,32    |
| Valor de ventas nuevo en USD para BR-12                  | (10 × 15,32) – 15,32                    | 137,88   |
| Valor de ventas en USD para BR-14                      | 12 × 13,75                              | 165,00   |
| Valor de coste en USD para BR-12                       | 10 × 9,52                               | 95,20    |
| Valor de coste en USD para BR-14                       | 12 × 7,48                               | 89,76    |
| Margen de contribución nuevo en USD para BR-12          | 137,88 - 95,20                          | 42,68    |
| Margen de contribución en USD para BR-14              | 165,00 - 89,76                          | 75,24    |
| Coeficiente de contribución nuevo en USD para BR-12           | \[(137,88 – 95,20) ÷ 137,88\] × 100     | 30,95    |
| Coeficiente de contribución en USD para BR-14               | \[(165,00 – 89,76) ÷ 165,00\] × 100     | 45,60    |
| Valor de ventas total nuevo en USD                      | \[(10 × 15,32) – 15,32\] + (12 × 13,75) | 302,88   |
| Valor de coste total en USD                           | (10 × 9,52) + (12 × 7,48)               | 184,96   |
| Margen de contribución total nuevo en USD              | 302,88 – 184,96                         | 117,92   |
| Nuevo coeficiente total de contribución                      | \[(302,88 – 184,96) ÷ 302,88\] × 100    | 38,93 %   |

La simulación de precios solo afecta a la línea a la que se aplica y reduce el total para dicha línea.




