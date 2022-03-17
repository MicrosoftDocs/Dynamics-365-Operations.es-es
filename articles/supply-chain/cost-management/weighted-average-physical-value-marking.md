---
title: Media ponderada con valor físico y marcado
description: La media ponderada es un modelo de inventario que se basa en el principio de media ponderada, donde las emisiones de inventario se tasan en el valor medio de los artículos recibidos en inventario durante el período de cierre de inventario, más cualquier inventario disponible del período anterior.
author: AndersGirke
ms.date: 02/21/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 65501
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 6c124716b70be837573506a738ef2034397f2bda
ms.sourcegitcommit: addae271ddfc5a8b0721c23337f69916153db4cd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/21/2022
ms.locfileid: "8330235"
---
# <a name="weighted-average-with-physical-value-and-marking"></a>Media ponderada con valor físico y marcado

[!include [banner](../includes/banner.md)]

El promedio ponderado es un modelo de inventario basado en un promedio que resulta de la multiplicación de cada componente (transacción de artículos) por un factor (precio de costo) que refleja su importancia (cantidad). Otra forma de decir esto es que el promedio ponderado es un modelo de inventario que asigna el costo de las transacciones de emisión en función del valor medio de todo el inventario recibido durante el período, más cualquier inventario disponible del período anterior.

Cuando ejecuta un cierre de inventario utilizando el modelo de inventario promedio ponderado, hay dos formas de crear una liquidación. Normalmente, todas las recepciones se liquidan contra una emisión virtual, que mantiene la cantidad recibida total y el valor. Esta emisión virtual tiene una recepción virtual correspondiente a partir de la cual se liquidan las emisiones. De este modo, todas las emisiones obtienen el mismo coste medio. La emisión y recepción virtual puede verse como una transferencia virtual, llamada *transferencia de cierre de inventario de media ponderada*. Este método de liquidación se denomina *liquidación resumida media ponderada*. Si solo existe una recepción, todas las emisiones se pueden liquidar a partir de ella y no se creará la transferencia virtual. Este método de liquidación se conoce como *liquidación directa*. Cualquier inventario que esté disponible después de realizar el cierre del inventario se valora al promedio ponderado del período anterior y se incluye en el cálculo del promedio ponderado en el período siguiente.

Puede reemplazar el principio de media ponderada marcando las transacciones de inventario de modo que se liquide una recepción de artículo específica con una emisión específica. Se requiere un cierre de inventario periódico cuando utiliza el modelo de inventario media ponderada para crear liquidaciones y ajustar el valor de las emisiones de acuerdo con el principio media ponderada. Hasta que ejecute el proceso de cierre de inventario, las transacciones de emisión se valoran en el promedio móvil cuando ocurrieron las actualizaciones físicas y financieras. A menos que esté utilizando el marcado, el promedio móvil se calcula cuando se realiza la actualización física o financiera.

El método de gestión de costes de inventario de media ponderada se calcula mediante la fórmula siguiente:

- Media ponderada = (\[Q1 × P1\] + \[Q2 × P2\] + \[Q *n* × P *n*\]) ÷ (Q1 + Q2 + Q *n*)

Q = cantidad de la transacción  
P = precio de la transacción

Las liquidaciones son registros del cierre del inventario que ajustan las emisiones con el fin de obtener el valor correcto de la media ponderada en la fecha de cierre. En los ejemplos siguientes se muestra el efecto del uso del método de la media ponderada en cinco configuraciones diferentes:

- Liquidación directa de media ponderada sin la opción **Incluir valor físico** en coste
- Liquidación resumida de media ponderada sin la opción **Incluir valor físico** en coste
- Liquidación directa de media ponderada con la opción **Incluir valor físico** en coste
- Liquidación resumida de media ponderada con la opción **Incluir valor físico** en coste
- Media ponderada con marcado

## <a name="weighted-average-direct-settlement-without-include-physical-value"></a>Liquidación directa de media ponderada sin la opción Incluir valor físico en coste

El principio de liquidación directa crea liquidaciones directamente entre recibos y salidas sin crear transacciones de inventario adicionales. El sistema utiliza este principio de liquidación directa en las siguientes situaciones:

- Se ha registrado una o más recepciones en el período.
- Solo se han registrado emisiones en el período y el inventario incluye artículos disponibles de un cierre anterior.

En este ejemplo, la casilla de verificación **Incluir valor físico** está desactivada en el **Grupo de modelo de artículo** para el producto emitido. En la ilustración siguiente se muestran estas transacciones:

- 1a. Recepción del inventario físico de una cantidad de 10 unidad a un coste de 10,00 dólares USD por unidad.
- 1b. Recepción del inventario financiero de una cantidad de 10 unidad a un coste de 10,00 dólares USD por unidad.
- 2a. Recepción del inventario físico de una cantidad de 10 unidad a un coste de 20,00 dólares USD por unidad.
- 3a. Recepción del inventario físico de una cantidad de 1 unidad con un precio de coste de 10,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).
- 3b. Emisión del inventario financiero de una cantidad de 1 unidad con un precio de coste de 10,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).
- 4a. Recepción del inventario físico de una cantidad de 1 unidad con un precio de coste de 10,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).
- 4b. Emisión del inventario financiero de una cantidad de 1 unidad con un precio de 10,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).
- 5a. Recepción del inventario físico de una cantidad de 1 unidad con un precio de coste de 10,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).
- 6\. Se efectúa el cierre de inventario. Basado en el método de promedio ponderado, el sistema utiliza el método de liquidación directa porque solo se actualiza financieramente un recibo en el período. En este ejemplo, se crea un asentamiento entre 1b y 3b y otro entre 1b y 4b. No se realiza ningún ajuste porque el promedio móvil es el mismo que el promedio ponderado.

En el diagrama siguiente se muestra esta serie de transacciones con los efectos que resultan de elegir el modelo de inventario de media ponderada y el principio de liquidación directa sin la opción **Incluir valor físico** en coste.

![DS WeightedAverage sin Incluir valor físico en coste.](media/weighted-average-direct-settlement-without-include-physical-value.png)

**Clave del diagrama**

- Las transacciones de inventario se representan por medio de flechas verticales.
- Las transacciones físicas están representadas por flechas grises claras más cortas.
- Las transacciones financieras están representadas por flechas negras más largas.
- Las recepciones de inventario se representan por medio de flechas verticales por encima del eje.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo del eje.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican el orden de los registros de transacciones de inventario en la línea de tiempo.
- Cada fecha en el diagrama está separada por una delgada línea vertical negra. La fecha se anota en la parte inferior del diagrama.
- Los cierres de inventario se representan por medio de una línea roja vertical discontinua.
- Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas de rayas que van en sentido diagonal desde las recepciones a las emisiones.

## <a name="weighted-average-summarized-settlement-without-the-include-physical-value-option"></a>Liquidación resumida de media ponderada sin la opción Incluir valor físico en coste

Cuando hay varios recibos en un período, la media ponderada utiliza el principio de liquidación de que todas las recepciones dentro de un período de cierre se resumen en una transacción denominada *cierre de inventario de media ponderada*. Todas las recepciones del período se liquidarán con la emisión de la transacción de inventario recién creada. Todas las emisiones del período se liquidarán contra la recepción de la nueva transacción de inventario. Si hay un valor restante de inventario disponible tras el cierre del inventario, el valor del inventario disponible se incluye en el recibo de la transacción de las transacciones de cierre de inventario de media ponderada.

En el gráfico que aparece a continuación se muestran las transacciones siguientes:

- 1a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
- 1b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
- 2a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 20,00 dólares USD por unidad.
- 2b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 22,00 dólares USD por unidad.
- 3a. Recepción del inventario físico de una cantidad de 1 unidad con un precio de coste de 16,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).
- 3b. Emisión del inventario financiero de una cantidad de 1 unidad con un precio de coste de 16,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).
- 4a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 25,00 dólares USD por unidad.
- 5a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
- 5b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
- 6a. Recepción del inventario físico de una cantidad de 1 unidad con un precio de coste de 23,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).
- 7\. Se efectúa el cierre de inventario.
- 7a. Se crea una emisión financiera Transacción de cierre de inventario de media ponderada para realizar la suma de las liquidaciones de todas las recepciones financieras de inventario.
  - La transacción 1b se liquida por una cantidad de 1 con una cantidad liquidada de USD 10,00.
  - La transacción 2b se liquida por una cantidad de 1 con una cantidad liquidada de USD 22,00.
  - La transacción 5b se liquida por una cantidad de 1 con una cantidad liquidada de USD 30,00.
  - Transacción 7a. se crea por una cantidad de 3 con una cantidad liquidada de USD 62,00. Esta transacción compensa la suma de las tres transacciones de recibo que se actualizan financieramente en el período.
- 7b. Se crea una recepción del inventario financiero para la transacción de cierre de inventario de media ponderada como contrapartida de las operaciones financieras cerradas.
  - La transacción 3b se liquida por una cantidad de 1 con una cantidad liquidada de USD 20,67. Esta transacción se ajusta en 4,67 USD para llevar el valor original de 16,00 USD a 20,67, que es el promedio ponderado de las transacciones registradas financieramente para el período.
  - Transacción 7b. se crea por una cantidad de 1 con una cantidad liquidada de USD 20,67 para completar 3b. Esta transacción compensa la suma de la transacción de recibo que se actualiza financieramente en el período.

En el diagrama siguiente se muestra esta serie de transacciones con los efectos que resultan de elegir el modelo de inventario de media ponderada y el principio de liquidación resumida sin la opción **Incluir valor físico en coste**.

![LR de media ponderada sin Incluir valor físico en coste.](media/weighted-average-summarized-settlement-without-include-physical-value.png)

**Clave del diagrama**

- Las transacciones de inventario se representan por medio de flechas verticales.
- Las transacciones físicas están representadas por flechas grises claras más cortas.
- Las transacciones financieras están representadas por flechas negras más largas.
- Las recepciones de inventario se representan por medio de flechas verticales por encima del eje.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo del eje.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican el orden de los registros de transacciones de inventario en la línea de tiempo.
- Cada fecha en el diagrama está separada por una delgada línea vertical negra. La fecha se anota en la parte inferior del diagrama.
- Los cierres de inventario se representan por medio de una línea roja vertical discontinua.
- Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas de rayas que van en sentido diagonal desde las recepciones a las emisiones.

## <a name="weighted-average-direct-settlement-with-the-include-physical-value-option"></a>Liquidación directa de media ponderada con la opción Incluir valor físico en coste

El parámetro **Incluir valor físico en coste** funciona de manera diferente con el modelo de inventario de media ponderada que en las versiones anteriores del producto. Cuando selecciona la opción **Incluir valor físico en coste** para un artículo en el formulario **Grupo de modelos de artículo**, el sistema utilizará las recepciones actualizadas físicamente al calcular el precio de coste estimado o el promedio móvil. Las emisiones se registrarán con el precio de coste estimado durante el período. Durante el cierre de inventario, en el cálculo de media ponderara sólo se tomarán en cuenta las recepciones actualizadas financieramente.

En el gráfico que aparece a continuación se muestran las transacciones siguientes:

- 1a. Recepción del inventario físico de una cantidad de 10 unidad a un coste de 10,00 dólares USD por unidad.
- 1b. Recepción del inventario financiero de una cantidad de 10 unidad a un coste de 10,00 dólares USD por unidad.
- 2a. Recepción del inventario físico de una cantidad de 10 unidad a un coste de 20,00 dólares USD por unidad.
- 3a. Emisión del inventario físico de una cantidad de 1 unidad con un precio de coste de 15,00 dólares USD por unidad (promedio móvil de transacciones registradas física y financieramente).
- 3b. Emisión del inventario financiero de una cantidad de 1 unidad con un precio de coste de 15,00 dólares USD por unidad (promedio móvil de transacciones registradas física y financieramente).
- 4a. Emisión del inventario físico de una cantidad de 1 unidad con un precio de 15,00 dólares USD por unidad (promedio móvil de transacciones registradas física y financieramente).
- 4b. Emisión del inventario financiero de una cantidad de 1 unidad con un precio de 15,00 dólares USD por unidad (promedio móvil de transacciones registradas física y financieramente).
- 5a. Emisión del inventario físico de una cantidad de 1 unidad con un precio de 15,00 dólares USD por unidad (promedio móvil de transacciones registradas física y financieramente).
- 6\. Se efectúa el cierre de inventario. Basado en el método de promedio ponderado, el sistema utiliza el método de liquidación directa porque solo se actualiza financieramente un recibo en el período. En este ejemplo, se crea un asentamiento entre 1b y 3b y otro entre 1b y 4b. Las transacciones 3b y 4b se ajustan cada una en USD -5,00 para llevar el valor a 10,00 USD.

En el diagrama siguiente se muestra esta serie de transacciones con los efectos que resultan de elegir el modelo de inventario de media ponderada y el principio de liquidación directa con la opción **Incluir valor físico en coste**.

![DS de media ponderada con Incluir valor físico en coste.](media/weighted-average-direct-settlement-with-include-physical-value.png)

**Clave del diagrama**

- Las transacciones de inventario se representan por medio de flechas verticales.
- Las transacciones físicas están representadas por flechas grises claras más cortas.
- Las transacciones financieras están representadas por flechas negras más largas.
- Las recepciones de inventario se representan por medio de flechas verticales por encima del eje.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo del eje.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican el orden de los registros de transacciones de inventario en la línea de tiempo.
- Cada fecha en el diagrama está separada por una delgada línea vertical negra. La fecha se anota en la parte inferior del diagrama.
- Los cierres de inventario se representan por medio de una línea roja vertical discontinua.
- Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas de rayas que van en sentido diagonal desde las recepciones a las emisiones.

## <a name="weighted-average-summarized-settlement-with-the-include-physical-value-option"></a>Liquidación resumida de media ponderada con la opción Incluir valor físico en coste

El parámetro **Incluir valor físico en coste** funciona de manera diferente con la media ponderada que en las versiones anteriores del programa. Seleccione la casilla **Incluir valor físico** en coste para un artículo en la página del **Grupo de modelos de artículo**. A continuación el sistema utilizará recepciones actualizadas físicamente para calcular el precio de coste estimado o el promedio móvil. Las emisiones se registrarán con el precio de coste estimado durante el período. Durante el cierre de inventario, en el cálculo de media ponderara sólo se tomarán en cuenta las recepciones actualizadas financieramente. Es recomendable realizar un cierre de inventario mensual cuando se usa el modelo de inventario de media ponderada. En este ejemplo de liquidación resumida de media ponderada, el modelo de inventario está marcado para incluir el valor físico en coste.

En el gráfico que aparece a continuación se muestran las transacciones siguientes:

- 1a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
- 1b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
- 2a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 20,00 dólares USD por unidad.
- 2b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 22,00 dólares USD por unidad.
- 3a. Emisión del inventario físico de una cantidad de 1 unidad con un precio de coste de 16,00 dólares USD por unidad (promedio móvil de transacciones registradas física y financieramente).
- 3b. Emisión del inventario financiero de una cantidad de 1 unidad con un precio de coste de 16,00 dólares USD por unidad (promedio móvil de transacciones registradas física y financieramente).
- 4a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 25,00 dólares USD por unidad.
- 5a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
- 5b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
- 6a. Emisión del inventario físico de una cantidad de 1 unidad con un precio de coste de 23,67 dólares USD por unidad (promedio móvil de transacciones registradas física y financieramente).
- 7\. Se efectúa el cierre de inventario.
- 7a. Se crea una emisión financiera Transacción de cierre de inventario de media ponderada para realizar la suma de las liquidaciones de todas las recepciones financieras de inventario.
  - La transacción 1b se liquida por una cantidad de 1 con una cantidad liquidada de USD 10,00.
  - La transacción 2b se liquida por una cantidad de 1 con una cantidad liquidada de USD 22,00.
  - La transacción 5b se liquida por una cantidad de 1 con una cantidad liquidada de USD 30,00.
  - Transacción 7a. se crea por una cantidad de 3 con una cantidad liquidada de USD 62,00.  
- 7b. Se crea una recepción del inventario financiero para la transacción de cierre de inventario de media ponderada como contrapartida de las operaciones financieras cerradas.
  - La transacción 3b se liquida por una cantidad de 1 con una cantidad liquidada de USD 20,67. Esta transacción se ajusta en 4,67 USD para llevar el valor original de 16,00 USD a 20,67, que es el promedio ponderado de las transacciones registradas financieramente para el período.
  - Transacción 7b. se crea por una cantidad de 1 con una cantidad liquidada de USD 20,67 para completar 3b.

En el diagrama siguiente se muestra esta serie de transacciones con los efectos que resultan de elegir el modelo de inventario de media ponderada y el principio de liquidación resumida sin la opción **Incluir valor físico en coste**.

![WeightedAverage LR con Incluir valor físico en coste.](media/weighted-average-summarized-settlement-with-include-physical-value.png)

**Clave del diagrama**

- Las transacciones de inventario se representan por medio de flechas verticales.
- Las transacciones físicas están representadas por flechas grises claras más cortas.
- Las transacciones financieras están representadas por flechas negras más largas.
- Las recepciones de inventario se representan por medio de flechas verticales por encima del eje.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo del eje.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican el orden de los registros de transacciones de inventario en la línea de tiempo.
- Cada fecha en el diagrama está separada por una delgada línea vertical negra. La fecha se anota en la parte inferior del diagrama.
- Los cierres de inventario se representan por medio de una línea roja vertical discontinua.
- Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas de rayas que van en sentido diagonal desde las recepciones a las emisiones.

## <a name="weighted-average-with-marking"></a>Media ponderada con marcado

La marcación es un proceso que permite vincular, o marcar, una transacción de emisión con una transacción de recepción. La marcación se puede efectuar con anterioridad o con posterioridad al registro de una transacción. Puede utilizar la marcación cuando desee asegurarse del coste exacto del inventario cuando se registra una transacción o cuando se efectúa el cierre de inventario.

Por ejemplo, supongamos que el Departamento de Atención al Cliente ha aceptado un pedido urgente de un cliente importante. Al tratarse de un pedido urgente, tendrá que pagar más por el artículo para poder responder a la solicitud del cliente. Debe estar seguro de que el coste del artículo de inventario correspondiente queda reflejado en el margen, o el coste de mercancías vendidas (COGS), de la factura de este pedido de ventas.

Cuando se registra el pedido de compra, se anota la recepción en el inventario con un coste de 120,00 USD. Por ejemplo, este documento de pedido de ventas se marca con el pedido de compra antes de registrar el albarán o la factura. Entonces, el coste de mercancías vendidas (COGS) será de 120,00 USD en lugar del coste promedio móvil actual para el artículo. Si el albarán o la factura del pedido de ventas se registra antes de que se realice la marcación, el coste de mercancías vendidas (COGS) se registrará con el precio de coste promedio móvil.

Antes de que se efectúe el cierre de inventario, puede mantenerse el marcado de las transacciones.

Una transacción de recepción se marca con una transacción de emisión. Entonces, no se tendrá en cuenta el método de valoración seleccionado para el grupo de modelos de artículo del artículo y el sistema liquidará estas transacciones entre sí.

Puede marcar una transacción de emisión con una transacción de recepción antes de registrar una transacción. Puede hacerlo desde una línea de pedido de ventas en la página **Detalles del pedido de ventas**. Las transacciones de recepción abiertas se ven en la página **Marcado**.

Puede marcar una transacción de emisión con una transacción de recepción después de registrar la transacción. Puede confrontar o marcar una transacción de emisión para una transacción de recepción abierta para un artículo en inventario desde un diario de ajuste de inventario registrado.

En el gráfico que aparece a continuación se muestran las transacciones siguientes:

- 1a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
- 1b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
- 2a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 20,00 dólares USD por unidad.
- 2b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 22,00 dólares USD por unidad.
- 3a. Recepción del inventario físico de una cantidad de 1 unidad con un precio de coste de 16,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).
- 3b. Emisión del inventario financiero de una cantidad de 1 unidad con un precio de coste de 16,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).
- 3c. El problema financiero de inventario para 3b está marcado como problema financiero de inventario para 2b.
- 4a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 25,00 dólares USD por unidad.
- 5a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
- 5b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
- 6a. Recepción del inventario físico de una cantidad de 1 unidad con un precio de coste de 23,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).
- 7\. Se efectúa el cierre de inventario. Según el principio de marcado que utiliza el método de media ponderada, las transacciones marcadas se liquidan entre sí. En este ejemplo, 3b se liquida contra 2b, y se contabiliza un ajuste para USD 6,00 en 3b para llevar el valor a USD 22,00. En este ejemplo, no se realizan liquidaciones adicionales porque el cierre crea liquidaciones solo para transacciones actualizadas financieramente.

En el diagrama siguiente se muestra esta serie de transacciones con los efectos que resultan de la selección del modelo de inventario de media ponderada con marcado.

![Media ponderada con marcado.](media/weighted-average-with-marking.png)

**Clave del diagrama**

- Las transacciones de inventario se representan por medio de flechas verticales.
- Las transacciones físicas están representadas por flechas grises claras más cortas.
- Las transacciones financieras están representadas por flechas negras más largas.
- Las recepciones de inventario se representan por medio de flechas verticales por encima del eje.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo del eje.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican el orden de los registros de transacciones de inventario en la línea de tiempo.
- Cada fecha en el diagrama está separada por una delgada línea vertical negra. La fecha se anota en la parte inferior del diagrama.
- Los cierres de inventario se representan por medio de una línea roja vertical discontinua.
- Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas de rayas que van en sentido diagonal desde las recepciones a las emisiones.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
