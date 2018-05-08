---
title: Fecha de media ponderada
description: "La fecha de media ponderada es un modelo de inventario basado en el principio de media ponderada, según el cual las emisiones de inventario se valoran según el valor medio de los artículos que se reciben en inventario para cada día diferente en el período de cierre de inventario."
author: AndersGirke
manager: AnnBe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, Retail
ms.custom: 28991
ms.assetid: 945d5088-a99d-4e54-bc42-d2bd61c61e22
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: a258c7d6314546262a3f9d07d06da5cad797d99b
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="weighted-average-date"></a>Fecha de media ponderada

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

La fecha de media ponderada es un modelo de inventario basado en el principio de medias ponderadas. En el principio de medias ponderadas, las emisiones de inventario se valoran según el valor medio de los artículos que se reciben en el inventario para cada día del período de cierre de inventario. 

Cuando se ejecuta un cierre de inventario con la fecha de media ponderada, todas las recepciones de un día se liquidan contra una emisión virtual. Esta emisión virtual mantiene la cantidad recibida total y el valor para dicho día. La emisión virtual tiene una recepción virtual correspondiente a partir de la cual se liquidarán las emisiones. Así pues, todas las emisiones reciben el mismo coste medio. La emisión y la recepción virtual pueden verse como una transferencia virtual llamada *transferencia de cierre de inventario de media ponderada*. 

Si solo ha tenido lugar una recepción hasta la fecha, no es necesario valorar la media. Dado que todas las emisiones se liquidan a partir de esa recepción, no se creará la transferencia virtual. Del mismo modo, si solo tienen lugar emisiones en la fecha, no hay recepciones a partir de las cuales valorar la media, por lo que tampoco se creará la transferencia virtual. Al usar la fecha de media ponderada, puede marcar las transacciones de inventario de modo que se liquide una recepción de artículo específica con una emisión específica. En este caso, no utilizará la regla de fecha de media ponderada. Recomendamos un cierre de inventario mensual si se utiliza el modelo de inventario de fecha de media ponderada. 

La fórmula siguiente se usa para calcular el método de gestión de costes de fecha media ponderada: 

Media ponderada = (\[Q1 × P1\] + \[Q2 × P2\] + \[Q*n* × P*n*\]) ÷ (Q1 + Q2 + Q*n*) 

Durante el cierre de inventario, el cálculo se realiza a diario hasta el período de cierre, tal y como se muestra en la ilustración siguiente. 

![Modelo de cálculo diario de fecha de media ponderada](./media/weightedaveragedatedailycalculationmodel.gif) 

Las transacciones de inventario que salen del inventario, como los pedidos de ventas, los diarios de inventario y los pedidos de producción, se producen con un precio de coste estimado en la fecha del registro. Este precio de coste estimado recibe también el nombre de precio de coste promedio móvil. En la fecha de cierre del inventario, el sistema analizará las transacciones de inventario de los períodos anteriores, los días anteriores y del día actual. Este análisis se utiliza para determinar cuáles de los siguientes principios de cierre deberán utilizarse:

-   Liquidación directa
-   Liquidación resumida

Las liquidaciones son registros del cierre del inventario que ajustan las emisiones con el fin de obtener el valor correcto de la media ponderada en la fecha de cierre. 

**Nota:** para obtener más información acerca de las liquidaciones, vea el artículo acerca del cierre de inventario. En los ejemplos siguientes se muestra el efecto del uso del método de media ponderada con cinco configuraciones:

-   Liquidación directa de la fecha de media ponderada cuando no se usa la opción **Incluir valor físico en coste**
-   Liquidación resumida de la fecha de media ponderada cuando no se usa la opción **Incluir valor físico en coste**
-   Liquidación directa de la fecha de media ponderada cuando se usa la opción **Incluir valor físico en coste**
-   Liquidación resumida de la fecha de media ponderada cuando se usa la opción **Incluir valor físico en coste**
-   Fecha de media ponderada cuando se usa el marcado

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-isnt-used"></a>Liquidación directa de la fecha de media ponderada cuando no se usa la opción Incluir valor físico en coste
La versión actual utiliza el mismo principio de liquidación directa que se usa para la media ponderada de las versiones anteriores. El sistema efectúa la liquidación directa de las recepciones y las emisiones. El sistema utiliza este principio de liquidación directa en situaciones específicas:

-   Se ha registrado una o varias recepciones en el período.
-   Solo se han registrado emisiones en el período y el inventario incluye artículos disponibles de un cierre anterior.

En el siguiente caso, se ha registrado una recepción y una emisión actualizadas financieramente. Durante el cierre de inventario, el sistema liquidará directamente la recepción contra la emisión, y no será necesario realizar ningún ajuste en el precio de coste de la emisión. 

La ilustración que sigue muestra estas transacciones:

-   1a. Recepción del inventario físico actualizado para una cantidad de 5 unidades a un coste de 10,00 dólares USD por unidad.
-   1b. Recepción del inventario financiero actualizado para una cantidad de 5 unidades a un coste de 10,00 dólares USD por unidad.
-   2a. Emisión del inventario físico actualizado para una cantidad de 2 unidades a un coste de 10,00 dólares USD por unidad.
-   2b. Emisión del inventario financiero actualizado para una cantidad de 2 unidades a un coste de 10,00 dólares USD por unidad.
-   3. El cierre de inventario se realiza mediante el método de liquidación directa para liquidar la recepción financiera de inventario a la emisión financiera de inventario.

![Liquidación directa de la fecha de media ponderada sin la opción Incluir valor físico en coste](./media/weightedaveragedatedirectsettlementwithoutincludephysicalvalue.gif) 

**Clave de la ilustración:**

-   Las transacciones de inventario se representan por medio de flechas verticales.
-   Las recepciones de inventario se representan por medio de flechas verticales por encima de la línea de tiempo.
-   Las emisiones de inventario se representan por medio de flechas verticales por debajo de la línea de tiempo.
-   Por encima (o por debajo) de cada flecha vertical, se especifica el valor de la transacción de inventario con el formato *Cantidad*@*Precio unitario*.
-   Los valores de transacciones de inventarios entre paréntesis indican que la transacción de inventario se ha registrado físicamente en el inventario.
-   Si los valores de transacciones de inventarios no van incluidos entre paréntesis es que la transacción de inventario se ha registrado financieramente en el inventario.
-   Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
-   Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican la secuencia de los registros de transacciones de inventario en la línea de tiempo.
-   Los cierres de inventario se representan por medio de una línea roja vertical discontinua y la etiqueta *Cierre de inventario*.
-   Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas con rayas que van en sentido diagonal desde las recepciones a las emisiones.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-isnt-used"></a>Liquidación resumida de la fecha de media ponderada cuando no se usa la opción Incluir valor físico en coste
La media ponderada se basa en el principio de que todas las recepciones dentro de un período de cierre se resumen en una nueva transacción de transferencia de inventario. Esta transacción se denomina *cierre de inventario de media ponderada*. Todas las recepciones efectuadas en un día se liquidan contra las emisiones de las nuevas transacciones de transferencias del inventario. Todas las emisiones efectuadas en un día se liquidan contra las recepciones de las nuevas transacciones de transferencias del inventario. Si el inventario disponible es positivo tras el cierre de inventario, se muestra un resumen de dicho inventario disponible y el valor del inventario en la nueva transacción de transferencia de inventario (recepción). Si el inventario disponible es negativo tras el cierre de inventario, el inventario disponible y el valor del inventario son la suma de las emisiones individuales que no se han liquidado totalmente. 

En el caso siguiente, se han registrado varias recepciones y emisiones actualizadas financieramente durante el período. Durante el cierre de inventario, el sistema evaluará cada día para determinar cómo debe tratarse cada día durante el cierre. 

La ilustración que sigue muestra estas transacciones: 

**Día 1:**

-   1a. Recepción del inventario físico actualizado para una cantidad de 3 unidades a un coste de 15,00 dólares USD por unidad.
-   1b. Recepción del inventario financiero actualizado para una cantidad de 3 unidades a un coste de 15,00 dólares USD por unidad.
-   2a. Emisión del inventario físico actualizado de una cantidad de 1 unidad a un coste promedio móvil de 15,00 dólares USD por unidad.
-   2b. Emisión del inventario financiero de una cantidad de 1 unidad a un coste promedio móvil de 15,00 dólares USD por unidad.

El sistema utilizará el método de liquidación directa para el día 1. 

**Día 2:**

-   3a. Emisión del inventario físico para una cantidad de 1 unidad a un coste promedio móvil de 15,00 dólares USD por unidad.
-   3b. Emisión financiera de inventario para una cantidad de 1 a un coste de promedio móvil de 15.00 dólares

El sistema utilizará el método de liquidación directa para el día 2. 

**Día 3:**

-   4a. Emisión del inventario físico para una cantidad de 1 unidad a un coste promedio móvil de 15,00 dólares USD por unidad.
-   4b. Emisión financiera de inventario para una cantidad de 1 a un coste de promedio móvil de 15.00 dólares
-   5a. Recepción del inventario físico para una cantidad de 1 unidad a un coste de 17,00 dólares USD por unidad.
-   5b. Recepción del inventario financiero para una cantidad de 1 unidad a un coste de 17,00 dólares USD por unidad.

Se efectúa el cierre de inventario. Será necesario utilizar la liquidación directa, ya que se registran varias recepciones que atraviesan días diferentes.

-   7a. Se crea una emisión financiera para la transacción de cierre de inventario de media ponderada para una cantidad de 2 unidades por un coste de 32,00 dólares USD para resumir las liquidaciones de todas las recepciones financieras de inventario hasta la fecha que no se han cerrado.
-   7b. Se crea una recepción del inventario financiero para la transacción de cierre de inventario de media ponderada como contrapartida de 7a.

El sistema genera y registra la transacción de transferencia de inventario resumida. Además, el sistema liquida todas las recepciones del día y el inventario disponible de los días anteriores contra la transacción resumida de emisión de transferencia de inventario. Todas las emisiones efectuadas en el día se liquidan con la transacción de recepción de transferencia de inventario resumida. Se calcula el precio de coste de media ponderada con un valor de 16,00 dólares USD por unidad. Se realiza un ajuste en la emisión de 1,00 dólar USD con el fin de ajustar el coste de media ponderada. El nuevo precio de coste promedio móvil es de 16,00 dólares USD. 

En la ilustración siguiente se muestra esta serie de transacciones con los efectos que resultan de elegir el modelo de inventario de media ponderada y el principio de liquidación resumida pero sin usar la opción **Incluir valor físico en coste**. 

![Liquidación resumida de la fecha de media ponderada sin la opción Incluir valor físico en coste](./media/weightedaveragedatesummarizedsettlementwithoutincludephysicalvalue.gif) 

**Clave de la ilustración**

-   Las transacciones de inventario se representan por medio de flechas verticales.
-   Las recepciones de inventario se representan por medio de flechas verticales por encima de la línea de tiempo.
-   Las emisiones de inventario se representan por medio de flechas verticales por debajo de la línea de tiempo.
-   Por encima (o por debajo) de cada flecha vertical, se especifica el valor de la transacción de inventario con el formato *Cantidad*@*Precio unitario*.
-   Los valores de transacciones de inventarios entre paréntesis indican que la transacción de inventario se ha registrado físicamente en el inventario.
-   Si los valores de transacciones de inventarios no van incluidos entre paréntesis es que la transacción de inventario se ha registrado financieramente en el inventario.
-   Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
-   Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican la secuencia de los registros de transacciones de inventario en la línea de tiempo.
-   Los cierres de inventario se representan por medio de una línea roja vertical discontinua y la etiqueta *Cierre de inventario*.
-   Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas con rayas que van en sentido diagonal desde las recepciones a las emisiones.
-   Las flechas rojas diagonales muestran las transacciones de recepción que se liquidan con las transacciones de emisión creadas por el sistema.
-   La flecha verde diagonal representa la transacción de recepción de compensación generada por el sistema con la que se liquida la transacción de emisión registrada inicialmente.

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-is-used"></a>Liquidación directa de la fecha de media ponderada cuando se usa la opción Incluir valor físico en coste
La versión actual usa el mismo principio de liquidación directa para fecha de media ponderada que se utilizaba en versiones anteriores. El sistema efectúa la liquidación directa de las recepciones y las emisiones. El sistema utiliza este principio de liquidación directa en situaciones específicas:

-   Se ha registrado una o varias recepciones en el período.
-   Solo se han registrado emisiones en el período y el inventario contiene artículos disponibles de un cierre anterior.

Si selecciona la casilla **Incluir valor físico en coste** para un artículo en la página **Grupo de modelos de artículo**, el sistema utiliza las recepciones actualizadas físicamente al calcular el precio de coste estimado o el promedio móvil. Las emisiones se registran según el precio de coste estimado durante el período. Durante el cierre de inventario, solo se tendrán en cuenta para el cálculo de la media ponderada las transacciones de recepción actualizadas financieramente.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-is-used"></a>Liquidación resumida de la fecha de media ponderada cuando se usa la opción Incluir valor físico en coste
Si selecciona la casilla **Incluir valor físico en coste** para un artículo en la página **Grupo de modelos de artículo**, el sistema utiliza las recepciones actualizadas físicamente al calcular el precio de coste estimado o el promedio móvil. Las emisiones se registran según el precio de coste estimado durante el período. Durante el cierre de inventario, solo se tendrán en cuenta para el cálculo de la media ponderada las transacciones de recepción actualizadas financieramente. La liquidación de media ponderada se basa en el principio de que las recepciones dentro de un período de cierre se resumen en una nueva transacción de transferencia de inventario denominada *cierre de inventario de media ponderada*. Todas las recepciones efectuadas en un día se liquidan contra las emisiones de las nuevas transacciones de transferencias del inventario. Todas las emisiones efectuadas en un día se liquidan contra las recepciones de las nuevas transacciones de transferencias del inventario. Si el inventario disponible es positivo tras el cierre de inventario, se muestra un resumen de dicho inventario disponible y el valor del inventario en la nueva transacción de transferencia de inventario (recepción). Si el inventario disponible es negativo tras el cierre de inventario, el inventario disponible y el valor del inventario son la suma de las emisiones individuales que no se han liquidado totalmente.

## <a name="weighted-average-date-when-marking-is-used"></a>Fecha de media ponderada cuando se usa el marcado
La marcación es un proceso que permite vincular una transacción de emisión con una transacción de recepción. La marcación se puede efectuar con anterioridad o con posterioridad al registro de una transacción. Puede utilizar la marcación cuando desee asegurarse del coste exacto del inventario cuando se registra una transacción o cuando se efectúa el cierre de inventario. 

Por ejemplo, supongamos que el Departamento de Atención al Cliente ha aceptado un pedido urgente de un cliente importante. Al tratarse de un pedido urgente, tendrá que pagar más por el artículo para poder atender a la solicitud del cliente. Debe asegurarse de que el coste del artículo de inventario correspondiente queda reflejado en el margen, o coste de mercancías vendidas (COGS), de la factura de este pedido de ventas. Cuando se registra el pedido de compra, se anota la recepción en el inventario con un coste de 120,00 dólares USD. El documento de pedido de ventas se marca con el pedido de compra antes de registrar el albarán o la factura. El coste de mercancías vendidas (COGS) será de 120,00 USD en lugar del coste promedio móvil actual para el artículo. Si el albarán o la factura del pedido de ventas se registra antes de que se realice la marcación, el coste de mercancías vendidas (COGS) se registrará con el precio de coste promedio móvil. Antes de que se efectúe el cierre de inventario, puede mantenerse el marcado de las transacciones. Cuando una transacción de recepción se marca con una transacción de emisión, se descarta el método de valoración definido en el grupo de modelos de artículo. En su lugar, el sistema liquida estas transacciones entre sí. 

Puede marcar una transacción de emisión con una transacción de recepción antes de registrar una transacción. Puede hacerlo desde una línea de pedido de ventas en la página **Detalles del pedido de ventas**. Puede ver las transacciones de recepción abiertas en la página **Marcado**. Puede marcar una transacción de emisión con una transacción de recepción después de registrar una transacción. Puede confrontar o marcar una transacción de emisión para una transacción de recepción abierta para un artículo en inventario desde un diario de ajuste de inventario registrado. La ilustración que sigue muestra estas transacciones:

-   1a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
-   1b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
-   2a. Recepción del inventario físico de una cantidad de 1 unidad con un precio de coste de 20,00 dólares USD por unidad.
-   2b. Recepción del inventario financiero de una cantidad de 1 unidad con un precio de coste de 20,00 dólares USD por unidad.
-   3a. Recepción del inventario físico de una cantidad de 1 unidad con un precio de coste de 25,00 dólares USD por unidad.
-   4a. Recepción del inventario físico de una cantidad de 1 unidad con un precio de coste de 30,00 dólares USD por unidad.
-   4b. Recepción del inventario financiero de una cantidad de 1 unidad con un precio de coste de 30,00 dólares USD por unidad.
-   5a. Emisión del inventario físico de una cantidad de 1 unidad con un precio de coste de 21,25 dólares USD por unidad (promedio móvil de transacciones actualizadas físicamente y financieramente).
-   5b. La emisión del inventario financiero de una cantidad de 1 unidad se marca con la recepción de inventario 2b antes de registrar la transacción. Esta transacción se registra con un precio de coste de 20,00 dólares USD.
-   6a. Emisión del inventario físico de una cantidad de 1 unidad con un precio de coste de 21,25 dólares USD por unidad.
-   7. Se efectúa el cierre de inventario. Dado que la transacción actualizada financieramente se ha marcado con una recepción existente, estas transacciones se liquidan entre sí y no se realiza ningún ajuste.

El nuevo precio de coste promedio móvil refleja la media de las transacciones actualizadas financieramente y físicamente a 27,50 dólares USD. La ilustración siguiente muestra esta serie de transacciones y los efectos que resultan de usar el inventario de fecha de media ponderada y el marcado.

![Fecha de media ponderada con marcado](./media/weightedaveragedatewithmarking.gif) 

**Clave de la ilustración:**

-   Las transacciones de inventario se representan por medio de flechas verticales.
-   Las recepciones de inventario se representan por medio de flechas verticales por encima de la línea de tiempo.
-   Las emisiones de inventario se representan por medio de flechas verticales por debajo de la línea de tiempo.
-   Por encima (o por debajo) de cada flecha vertical, se especifica el valor de la transacción de inventario con el formato *Cantidad*@*Precio unitario*.
-   Los valores de transacciones de inventarios entre paréntesis indican que la transacción de inventario se ha registrado físicamente en el inventario.
-   Si los valores de transacciones de inventarios no van incluidos entre paréntesis es que la transacción de inventario se ha registrado financieramente en el inventario.
-   Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
-   Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican la secuencia de los registros de transacciones de inventario en la línea de tiempo.
-   Los cierres de inventario se representan por medio de una línea roja vertical discontinua y la etiqueta *Cierre de inventario*.
-   Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas con rayas que van en sentido diagonal desde las recepciones a las emisiones.





