---
title: "Media ponderada con valor físico y marcado"
description: "La media ponderada es un modelo de inventario que se basa en el principio de media ponderada, donde las emisiones de inventario se tasan en el valor medio de los artículos recibidos en inventario durante el período de cierre de inventario, más cualquier inventario disponible del período anterior."
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
ms.custom: 65501
ms.assetid: 25041ff0-bafe-484d-a94a-e1772ad43204
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: ec7f1ef643d864a2729642d78d19fc43d5f6a7fb
ms.contentlocale: es-es
ms.lasthandoff: 04/13/2018

---

# <a name="weighted-average-with-physical-value-and-marking"></a>Media ponderada con valor físico y marcado

[!INCLUDE [banner](../includes/banner.md)]

[!INCLUDE [retail name](../includes/retail-name.md)]

La media ponderada es un modelo de inventario que se basa en el principio de media ponderada, donde las emisiones de inventario se tasan en el valor medio de los artículos recibidos en inventario durante el período de cierre de inventario, más cualquier inventario disponible del período anterior.

Cuando se ejecuta un cierre de inventario, todas las recepciones se liquidan contra una emisión virtual, que mantiene la cantidad recibida total y el valor. Esta emisión virtual tiene una recepción virtual correspondiente a partir de la cual se liquidan las emisiones. De este modo, todas las emisiones obtienen el mismo coste medio. La emisión y recepción virtual puede verse como una transferencia virtual, llamada “transferencia de cierre de inventario de media ponderada”.

Si solo existe una recepción, todas las emisiones se pueden liquidar a partir de ella y no se creará la transferencia virtual. 

Al usar la media ponderada, puede marcar las transacciones de inventario de modo que se liquide una recepción de artículo específica con una emisión específica, en lugar de usar la regla de media ponderada. 

Recomendamos un cierre de inventario mensual si se utiliza el modelo de inventario de media ponderada. 

El método de gestión de costes de inventario de media ponderada se calcula mediante la fórmula siguiente:
-   Media ponderada = (Q1\*P1 + Q2\*P2 + Qn\*Pn) / (Q1 + Q2 + Qn)

Transacciones de inventario que salen de emisiones de inventario. Esto incluye los pedidos de ventas, diarios de inventario y pedidos de producción, y se producen con un precio de coste estimado en la fecha de registro. Este precio de coste estimado también se conoce como promedio móvil. En el momento del cierre de inventario, el sistema analizará las transacciones de inventario de los períodos anteriores y actual, y determinará cuáles de los siguientes principios de cierre deberán usarse.
-   Liquidación directa
-   Liquidación resumida

Las liquidaciones son registros del cierre del inventario que ajustan las emisiones con el fin de obtener el valor correcto de la media ponderada en la fecha de cierre. En los ejemplos siguientes se muestra el efecto del uso del método de la media ponderada en cinco configuraciones diferentes:
-   Liquidación directa de media ponderada sin la opción Incluir valor físico en coste
-   Liquidación resumida de media ponderada sin la opción Incluir valor físico en coste
-   Liquidación directa de media ponderada con la opción Incluir valor físico en coste
-   Liquidación resumida de media ponderada con la opción Incluir valor físico en coste
-   Media ponderada con marcado

## <a name="weighted-average-direct-settlement-without-include-physical-value"></a>Liquidación directa de media ponderada sin la opción Incluir valor físico en coste
El principio de liquidación directa es el mismo que el que se usa para la media ponderada de las versiones anteriores. El sistema efectuará la liquidación directa de las recepciones y las emisiones. El sistema utiliza este principio de liquidación directa en situaciones específicas:
-   Se ha registrado una recepción y varias emisiones en el período
-   Solo se han registrado emisiones en el período y el inventario incluye artículos disponibles de un cierre anterior

En las siguientes secciones del escenario, se ha registrado una recepción y una emisión actualizadas financieramente. Durante el cierre de inventario, el sistema liquidará directamente la recepción contra la emisión, y no será necesario realizar ningún ajuste en el precio de coste de la emisión. En el gráfico se muestran las siguientes transacciones:
-   1a. Recepción física de inventario actualizada para una cantidad de 5 a 10,00 USD por unidad
-   1b. Recepción financiera de inventario actualizada para una cantidad de 5 a 10,00 USD por unidad
-   2a. Emisión física de inventario actualizada para una cantidad de 2 a 10,00 USD por unidad
-   2b. Emisión financiera de inventario actualizada para una cantidad de 2 a 10,00 USD por unidad
-   3. El cierre de inventario se realiza mediante el método de liquidación directa para liquidar la recepción financiera de inventario a la emisión financiera de inventario.

En el diagrama siguiente se muestra esta serie de transacciones con los efectos que resultan de elegir el modelo de inventario de media ponderada y el principio de liquidación directa sin la opción Incluir valor físico en coste. 

![LD de media ponderada sin Incluir valor físico en coste](./media/weightedaveragedirectsettlementwithoutincludephysicalvalue.gif) 

**Clave del diagrama**
- Las transacciones de inventario se representan por medio de flechas verticales.
- Las recepciones de inventario se representan por medio de flechas verticales por encima de la línea de tiempo.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo de la línea de tiempo.
- Por encima (o por debajo) de cada flecha vertical, se especifica el valor de la transacción de inventario con el formato Quantity@Unitprice.
- Los valores de transacciones de inventarios entre corchetes indican que la transacción de inventario se ha registrado físicamente en el inventario.
- Los valores de transacciones de inventario que no van encerrados entre corchetes indican que la transacción de inventario se ha registrado financieramente en el inventario.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican la secuencia de los registros de transacciones de inventario en la línea de tiempo.
- Los cierres de inventario se representan por medio de una línea roja vertical discontinua y la etiqueta Cierre de inventario.
- Las liquidaciones realizadas por el cierre de inventario se representan mediante flechas rojas de puntos en dirección diagonal desde una recepción hasta una emisión.

## <a name="weighted-average-summarized-settlement-without-the-include-physical-value-option"></a>Liquidación resumida de media ponderada sin la opción Incluir valor físico en coste
La media ponderada utiliza el principio de liquidación de que todas las recepciones dentro de un período de cierre se resumen en una transacción denominada cierre de inventario de media ponderada. Todas las recepciones del período se liquidarán con la emisión de la transacción de transferencia de inventario recién creada. Todas las emisiones del período se liquidarán contra la recepción de la nueva transacción de transferencia de inventario. Si el inventario disponible es positivo tras el cierre de inventario, se muestra un resumen de dicho inventario disponible y del valor del inventario en la nueva transacción de transferencia de inventario (recepción). Si el inventario disponible es negativo tras el cierre de inventario, el inventario disponible y el valor del inventario es la suma de las emisiones individuales que no se han liquidado totalmente. En la situación siguiente, se han registrado varias recepciones y una emisión actualizadas financieramente. 

Durante el cierre de inventario, el sistema generará y registrará la transacción de transferencia de inventario resumida, y liquidará las recepciones del período con la transacción de emisión de transferencia de inventario resumida. Todas las emisiones registradas del período se liquidarán con la transacción de recepción de transferencia de inventario resumida. Se calcula que la media ponderada sea de 15,00 USD. La emisión se registró originalmente con un precio de coste estimado de 14,67 USD. Por tanto, se creará y registrará un ajuste de menos 0,33 USD en la emisión. A partir de la fecha de cierre de inventario, el inventario disponible es de 3 unidades con un valor de 45,00 USD. 

En el gráfico que aparece a continuación se muestran las transacciones siguientes:
-   1a. Recepción física de inventario actualizada para una cantidad de 2 a un coste de 11,00 USD por unidad.
-   1b. Recepción financiera de inventario actualizada para una cantidad de 2 a un coste de 14,00 USD por unidad.
-   2a. Recepción física de inventario actualizada para una cantidad de 1 a un coste de 12,00 USD por unidad.
-   2b. Recepción financiera de inventario actualizada para una cantidad de 1 a un coste de 16,00 USD por unidad.
-   3a. Emisión física de inventario actualizada para una cantidad de 1 a un coste de 14,67 USD por unidad (promedio móvil).
-   3b. Emisión financiera de inventario actualizada para una cantidad de 1 a un coste de 14,67 USD por unidad (promedio móvil).
-   4a. Recepción física de inventario actualizada para una cantidad de 1 a un coste de 14,00 USD por unidad.
-   4b. Recepción financiera de inventario actualizada para una cantidad de 1 a un coste de 16,00 USD por unidad.
-   5. Se efectúa el cierre de inventario.
-   6a. Se crea una emisión financiera “Transacción de cierre de inventario de media ponderada” para realizar la suma de las liquidaciones de todas las recepciones financieras de inventario.
-   6b. Se crea una recepción financiera “Transacción de cierre de inventario de media ponderada” como contrapartida de 5a.

En el diagrama siguiente se muestra esta serie de transacciones con los efectos que resultan de elegir el modelo de inventario de media ponderada y el principio de liquidación resumida sin la opción Incluir valor físico en coste. 

![LR de media ponderada sin Incluir valor físico en coste](./media/weightedaveragesummarizedsettlementwithoutincludephysicalvalue.gif) 

**Clave del diagrama**
- Las transacciones de inventario se representan por medio de flechas verticales.
- Las recepciones de inventario se representan por medio de flechas verticales por encima de la línea de tiempo.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo de la línea de tiempo.
- Por encima (o por debajo) de cada flecha vertical, se especifica el valor de la transacción de inventario con el formato Quantity@Unitprice.
- Los valores de transacciones de inventarios entre corchetes indican que la transacción de inventario se ha registrado físicamente en el inventario.
- Los valores de transacciones de inventario que no van encerrados entre corchetes indican que la transacción de inventario se ha registrado financieramente en el inventario.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican la secuencia de los registros de transacciones de inventario en la línea de tiempo.
- Los cierres de inventario se representan por medio de una línea roja vertical discontinua y la etiqueta Cierre de inventario.
- Las liquidaciones realizadas por el cierre de inventario se representan mediante flechas rojas de puntos en dirección diagonal desde una recepción hasta una emisión.
- Las flechas rojas indican las transacciones de recepción que se están liquidando en la transacción de emisión creada por el sistema.
- La flecha verde representa la transacción de recepción de contrapartida generada por el sistema a la que se liquida la transacción de emisión original registrada

## <a name="weighted-average-direct-settlement-with-the-include-physical-value-option"></a>Liquidación directa de media ponderada con la opción Incluir valor físico en coste
El parámetro Incluir valor físico en coste funciona de manera diferente con el modelo de inventario de media ponderada que en las versiones anteriores del producto. Seleccione el cuadro Incluir valor físico en coste para un artículo en el formulario del grupo de modelos de artículo. A continuación, el sistema utilizará recepciones actualizadas físicamente para calcular el precio de coste estimado o el promedio móvil. Las emisiones se registrarán con el precio de coste estimado durante el período. Durante el cierre de inventario, en el cálculo de media ponderara sólo se tomarán en cuenta las recepciones actualizadas financieramente. Es recomendable realizar un cierre de inventario mensual cuando se usa el modelo de inventario de media ponderada. En este ejemplo de liquidación directa de media ponderada, el grupo de modelos de artículo está marcado para incluir el valor físico. 

En el gráfico que se incluye a continuación se muestran las siguientes transacciones:
-   1a. Recepción física de inventario actualizada para una cantidad de 1 a un coste de 11,00 USD por unidad.
-   1b. Recepción financiera de inventario actualizada para una cantidad de 1 a un coste de 10,00 USD por unidad.
-   2a. Recepción física de inventario actualizada para una cantidad de 1 a un coste de 15,00 USD por unidad.
-   3a. Emisión física de inventario actualizada para una cantidad de 1 a un coste de 12,50 USD por unidad (coste promedio móvil, ya que se toma en cuenta el valor de recepción física).
-   3b. Emisión financiera de inventario actualizada para una cantidad de 1 a un coste de 12,50 USD por unidad (coste promedio móvil, ya que se toma en cuenta el valor de recepción física).
-   4. Se efectúa el cierre de inventario. Durante el cierre de inventario, el sistema no tomará en cuenta ninguna transacción de inventario que se haya actualizado sólo físicamente. En cambio, se usará el principio de liquidación directa porque sólo existe una única recepción financiera. Se registrará un ajuste de 2,50 USD en la transacción de inventario emitida financieramente a partir de la fecha de cierre de inventario. Después del cierre, el inventario disponible será una cantidad de 1 con un precio de coste promedio móvil de 15,00 USD.

En el diagrama siguiente se muestra esta serie de transacciones con los efectos que resultan de elegir el modelo de inventario de media ponderada y el principio de liquidación directa con la opción Incluir valor físico en coste. 

![LD de media ponderada con Incluir valor físico en coste](./media/weightedaveragedirectsettlementwithincludephysicalvalue.gif) 

**Clave del diagrama**
- Las transacciones de inventario se representan por medio de flechas verticales.
- Las recepciones de inventario se representan por medio de flechas verticales por encima de la línea de tiempo.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo de la línea de tiempo.
- Por encima (o por debajo) de cada flecha vertical, se especifica el valor de la transacción de inventario con el formato Quantity@Unitprice.
- Los valores de transacciones de inventarios entre corchetes indican que la transacción de inventario se ha registrado físicamente en el inventario.
- Los valores de transacciones de inventario que no van encerrados entre corchetes indican que la transacción de inventario se ha registrado financieramente en el inventario.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican la secuencia de los registros de transacciones de inventario en la línea de tiempo.
- Los cierres de inventario se representan por medio de una línea roja vertical discontinua y la etiqueta Cierre de inventario.
- Las liquidaciones realizadas por el cierre de inventario se representan mediante flechas rojas de puntos en dirección diagonal desde una recepción hasta una emisión.

## <a name="weighted-average-summarized-settlement-with-the-include-physical-value-option"></a>Liquidación resumida de media ponderada con la opción Incluir valor físico en coste
El parámetro Incluir valor físico en coste funciona de manera diferente con la media ponderada que en las versiones anteriores del programa. Seleccione el cuadro Incluir valor físico en coste para un artículo en la página del grupo de modelos de artículo. A continuación el sistema utilizará recepciones actualizadas físicamente para calcular el precio de coste estimado o el promedio móvil. Las emisiones se registrarán según este precio de coste estimado durante el período. Durante el cierre de inventario, en el cálculo de media ponderara sólo se tomarán en cuenta las recepciones actualizadas financieramente. Es recomendable realizar un cierre de inventario mensual cuando se usa el modelo de inventario de media ponderada. En este ejemplo de liquidación resumida de media ponderada, el modelo de inventario está marcado para incluir el valor físico en coste. 

En el gráfico que aparece a continuación se muestran las transacciones siguientes:
-   1a. Recepción física de inventario actualizada para una cantidad de 2 a un coste de 11,00 USD por unidad.
-   1b. Recepción financiera de inventario actualizada para una cantidad de 2 a un coste de 14,00 USD por unidad.
-   2. Recepción física de inventario actualizada para una cantidad de 1 a un coste de 10,00 USD por unidad.
-   3a. Recepción física de inventario actualizada para una cantidad de 1 a un coste de 12,00 USD por unidad.
-   3b. Recepción financiera de inventario actualizada para una cantidad de 1 a un coste de 16,00 USD por unidad.
-   4a. Emisión física de inventario actualizada para una cantidad de 1 a un coste de 13,50 USD por unidad (coste promedio móvil, ya que se toma en cuenta el valor de recepción física).
-   4b. Emisión financiera de inventario actualizada para una cantidad de 1 a un coste de 13,50 USD por unidad (coste promedio móvil, ya que se toma en cuenta el valor de recepción física).
-   5a. Recepción física de inventario actualizada para una cantidad de 1 a un coste de 14,00 USD por unidad.
-   5b. Recepción financiera de inventario actualizada para una cantidad de 1 a un coste de 16,00 USD por unidad.
-   6. Se efectúa el cierre de inventario. Durante el cierre de inventario, el sistema no tomará en cuenta ninguna transacción de inventario que se haya actualizado sólo físicamente. Se usará el principio de liquidación resumida porque sólo existe una única recepción financiera. Se registrará un ajuste de 1,50 USD en la transacción de inventario emitida financieramente a partir de la fecha de cierre de inventario. Después del cierre, el inventario disponible será una cantidad de 3 con un precio de coste promedio móvil de 15,00 USD.
-   7a. Se crea una emisión financiera “Transacción de cierre de inventario de media ponderada” para realizar la suma de las liquidaciones de todas las recepciones financieras de inventario.
-   7b. Se crea una recepción financiera “Transacción de cierre de inventario de media ponderada” como contrapartida de 5a.

En el diagrama siguiente se muestra esta serie de transacciones con los efectos que resultan de elegir el modelo de inventario de media ponderada y el principio de liquidación resumida sin la opción Incluir valor físico en coste. 

![LR de media ponderada con Incluir valor físico en coste](./media/weightedaveragesummarizedsettlementwithincludephysicalvalue.gif) 

**Clave del diagrama**
- Las transacciones de inventario se representan por medio de flechas verticales.
- Las recepciones de inventario se representan por medio de flechas verticales por encima de la línea de tiempo.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo de la línea de tiempo.
- Por encima (o por debajo) de cada flecha vertical, se especifica el valor de la transacción de inventario con el formato Quantity@Unitprice.
- Los valores de transacciones de inventarios entre corchetes indican que la transacción de inventario se ha registrado físicamente en el inventario.
- Los valores de transacciones de inventario que no van encerrados entre corchetes indican que la transacción de inventario se ha registrado financieramente en el inventario.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, 1a. Los identificadores indican la secuencia de los registros de transacciones de inventario en la línea de tiempo.
- Los cierres de inventario se representan por medio de una línea roja vertical discontinua y la etiqueta Cierre de inventario.
- Las liquidaciones realizadas por el cierre de inventario se representan mediante flechas rojas de puntos en dirección diagonal desde una recepción hasta una emisión.
- Las flechas rojas indican las transacciones de recepción que se están liquidando en la transacción de emisión creada por el sistema.
- La flecha verde representa la transacción de recepción de contrapartida generada por el sistema a la que se liquida la transacción de emisión original registrada.

## <a name="weighted-average-with-marking"></a>Media ponderada con marcado
La marcación es un proceso que permite vincular, o marcar, una transacción de emisión con una transacción de recepción. La marcación se puede efectuar con anterioridad o con posterioridad al registro de una transacción. Puede utilizar la marcación cuando desee asegurarse del coste exacto del inventario cuando se registra una transacción o cuando se efectúa el cierre de inventario. 

Por ejemplo, supongamos que el Departamento de Atención al Cliente ha aceptado un pedido urgente de un cliente importante. Al tratarse de un pedido urgente, tendrá que pagar más por el artículo para poder responder a la solicitud del cliente. Debe estar seguro de que el coste del artículo de inventario correspondiente queda reflejado en el margen, o el coste de mercancías vendidas (COGS), de la factura de este pedido de ventas. 

Cuando se registra el pedido de compra, se anota la recepción en el inventario con un coste de 120,00 USD. Por ejemplo, este documento de pedido de ventas se marca con el pedido de compra antes de registrar el albarán o la factura. Entonces, el coste de mercancías vendidas (COGS) será de 120,00 USD en lugar del coste promedio móvil actual para el artículo. Si el albarán o la factura del pedido de ventas se registra antes de que se realice la marcación, el coste de mercancías vendidas (COGS) se registrará con el precio de coste promedio móvil. 

Antes de que se efectúe el cierre de inventario, puede mantenerse el marcado de las transacciones. 

Una transacción de recepción se marca con una transacción de emisión. Entonces, no se tendrá en cuenta el método de valoración seleccionado para el grupo de modelos de artículo del artículo y el sistema liquidará estas transacciones entre sí. 

Puede marcar una transacción de emisión con una transacción de recepción antes de registrar una transacción. Puede hacerlo desde una línea de pedido de ventas en la página Detalles del pedido de ventas. Las transacciones de recepción abiertas se ven en la página Marcado. 

Puede marcar una transacción de emisión con una transacción de recepción después de registrar la transacción. Puede confrontar o marcar una transacción de emisión para una transacción de recepción abierta para un artículo en inventario desde un diario de ajuste de inventario registrado. 

En el gráfico que se incluye a continuación se muestran las siguientes transacciones:
-   1a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
-   1b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
-   2a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 20,00 dólares USD por unidad.
-   2b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 20,00 dólares USD por unidad.
-   3a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 25,00 dólares USD por unidad.
-   4a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
-   4b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
-   5a. Emisión física de inventario para una cantidad de 1 a un precio de coste de 21,25 USD (promedio móvil de las transacciones actualizadas financieramente y físicamente).
-   5b. Emisión financiera de inventario para una cantidad de 1 se marca a la recepción de inventario 2b antes del registro de la transacción. Esta transacción se registra con un precio de coste de 20,00 USD.
-   6a. Emisión física de inventario para una cantidad de 1 a un precio de coste de 21,25 USD por unidad.
-   7. Se realiza el cierre de inventario. Dado que la transacción actualizada financieramente está marcada a una recepción existente, estas transacciones se liquidan entre sí y no se realiza ningún ajuste.

El nuevo precio de coste promedio móvil refleja la media de las transacciones actualizadas financieramente y físicamente a 27,50 dólares USD. 

En el diagrama siguiente se muestra esta serie de transacciones con los efectos que resultan de la selección del modelo de inventario de media ponderada con marcado. 

![Media ponderada con marcado](./media/weightedaveragewithmarking.gif) 

**Clave del diagrama**
- Las transacciones de inventario se representan por medio de flechas verticales.
- Las recepciones de inventario se representan por medio de flechas verticales por encima de la línea de tiempo.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo de la línea de tiempo.
- Por encima (o por debajo) de cada flecha vertical, se especifica el valor de la transacción de inventario con el formato Cantidad@"Unitprice".
- Los valores de transacciones de inventarios entre corchetes indican que la transacción de inventario se ha registrado físicamente en el inventario.
- Los valores de transacciones de inventario que no van encerrados entre corchetes indican que la transacción de inventario se ha registrado financieramente en el inventario.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican la secuencia de los registros de transacciones de inventario en la línea de tiempo.
- Los cierres de inventario se representan por medio de una línea roja vertical discontinua y la etiqueta Cierre de inventario.
- Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas de puntos que van en sentido diagonal desde las recepciones a las emisiones.






