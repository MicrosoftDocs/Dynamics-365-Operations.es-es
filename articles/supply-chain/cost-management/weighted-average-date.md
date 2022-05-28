---
title: Fecha de media ponderada con valor físico y marcado incluido
description: La fecha de media ponderada es un modelo de inventario basado en el principio de media ponderada, según el cual las emisiones de inventario se valoran según el valor medio de los artículos que se reciben en inventario para cada día diferente en el período de cierre de inventario.
author: JennySong-SH
ms.date: 03/04/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 28991
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1497cb08f4cc5a455c832b9bf125c309cd90aa3d
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/03/2022
ms.locfileid: "8672133"
---
# <a name="weighted-average-date-with-include-physical-value-and-marking"></a>Fecha de media ponderada con valor físico y marcado incluido

[!include [banner](../includes/banner.md)]

La *fecha de promedio ponderado* es un modelo de inventario basado en un promedio que se calcula multiplicando cada componente (transacción de artículos) por un factor (precio de costo) que refleja su importancia (cantidad) en cada día del periodo. En otras palabras, es un modelo de inventario que asigna el costo de las transacciones de emisión en función del valor medio de todo el inventario recibido cada día, más cualquier inventario disponible del día anterior.

Cuando ejecuta un cierre de inventario utilizando el modelo de inventario de fecha de promedio ponderado, hay dos métodos de crear una liquidación. Normalmente, todas las recepciones se liquidan contra una emisión virtual, que mantiene la cantidad recibida total y el valor. Esta emisión virtual tiene una recepción virtual correspondiente a partir de la cual se liquidan las emisiones. De este modo, todas las emisiones obtienen el mismo coste medio cada día. La emisión virtual y el recibo virtual pueden considerarse una transferencia virtual. Esta transferencia virtual se conoce como *transferencia de cierre de inventario promedio ponderado*. Por lo tanto, este método de liquidación se denomina *liquidación resumida media ponderada*. Si solo existe una recepción, todas las emisiones se pueden liquidar a partir de ella y no se creará la transferencia virtual. Este método de liquidación se conoce como *liquidación directa*. Cualquier inventario que esté disponible después de realizar el cierre del inventario se valora al promedio ponderado del último día anterior y se incluye en el cálculo de fecha de promedio ponderado en el período siguiente.

Puede reemplazar el principio de fecha de media ponderada marcando las transacciones de inventario de modo que se liquide una recepción de artículo específica con una emisión específica. Se requiere un cierre de inventario periódico cuando utiliza el modelo de inventario de fecha media ponderada para crear liquidaciones y ajustar el valor de las emisiones de acuerdo con el principio de fecha de media ponderada. Hasta que ejecute el cierre de inventario, las transacciones de emisión se valoran en el promedio móvil cuando ocurrieron las actualizaciones físicas y financieras. A menos que esté utilizando el marcado, el promedio móvil se calcula cuando se realiza la actualización física o financiera.

El método de gestión de costes de inventario de fecha de media ponderada se calcula mediante la fórmula siguiente cada día:

*Costo* = \[(*Q*<sub>*b*</sub> × *P*<sub>*b*</sub>) + &#x2211;<sub>*n*</sub>(*Q*<sub>*n*</sub> × *P*<sub>*n*</sub>)\] ÷ (*Q*<sub>*b*</sub> + &#x2211;<sub>*n*</sub>*Q*<sub>*n*</sub>)

- *Q* = cantidad de la transacción
- *P* = precio de la transacción

En otras palabras, el costo promedio ponderado es igual a la cantidad inicial por el precio inicial, más la suma de cada cantidad recibida por su precio recibido, todo dividido por la cantidad inicial más la suma de las cantidades recibidas.

Durante el cierre de inventario, el cálculo se realiza a diario hasta el período de cierre.

> [!NOTE]
> Para obtener más información sobre liquidaciones, consulte [Cierre de inventario](inventory-close.md).

En los ejemplos siguientes se muestra el efecto del uso del método de fecha de media ponderada con cinco configuraciones:

- Liquidación directa de la fecha de media ponderada cuando no se usa la opción **Incluir valor físico en coste**
- Liquidación resumida de la fecha de media ponderada cuando no se usa la opción **Incluir valor físico en coste**
- Liquidación directa de la fecha de media ponderada cuando se usa la opción **Incluir valor físico en coste**
- Liquidación resumida de la fecha de media ponderada cuando se usa la opción **Incluir valor físico en coste**
- Fecha de media ponderada cuando se usa el marcado

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-isnt-used"></a>Liquidación directa de la fecha de media ponderada cuando no se usa la opción Incluir valor físico en coste

El principio de liquidación directa crea liquidaciones directamente entre recibos y salidas, sin crear transacciones de inventario adicionales. El sistema utiliza este principio de liquidación directa en las siguientes situaciones:

- Se ha registrado una o más recepciones en el período.
- Solo se han registrado emisiones en el período y el inventario incluye artículos disponibles de un cierre anterior.

En este ejemplo, la casilla de verificación **Incluir valor físico** está desactivada en la página **Grupo de modelo de artículo** para el producto emitido. En el diagrama siguiente se muestran estas transacciones:

**Día 1:**

- 1a. Recepción del inventario físico de una cantidad de 10 unidad a un coste de 10,00 dólares USD por unidad.
- 1b. Recepción del inventario financiero de una cantidad de 10 unidad a un coste de 10,00 dólares USD por unidad.
- 2a. Recepción del inventario físico de una cantidad de 10 unidad a un coste de 20,00 dólares USD por unidad.
- 3a. Recepción del inventario físico de una cantidad de 1 unidad con un precio de coste de 10,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).
- 3b. Emisión del inventario financiero de una cantidad de 1 unidad con un precio de coste de 10,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).

**Día 2:**

- 4a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 25,00 dólares USD por unidad.
- 5a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
- 5b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
- 6a. Emisión del inventario financiero de una cantidad de 1 unidad con un precio de 20,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).

**Día 3:**

- 7\. Se efectúa el cierre de inventario. Basado en el método de fecha de promedio ponderado, el sistema utiliza el método de liquidación directa para el 30 de diciembre (30/12) porque solo se actualiza financieramente un recibo el 30/12. En este ejemplo, se crea un asentamiento entre las transacciones 1b y 3b. Se realiza un ajuste de USD 10,00 para llevar el valor de la transacción 3b hasta 20,00. No se realiza ningún ajuste o liquidación al 31 de diciembre (31/12) porque no hay emisiones actualizadas financieramente al 31/12.

En el diagrama siguiente se muestra esta serie de transacciones y los efectos que resultan de usar el modelo de inventario de media ponderada y el principio de liquidación directa sin la opción **Incluir valor físico** en coste.

![Liquidación directa de la fecha de media ponderada sin la opción Incluir valor físico en coste.](media/weighted-average-date-direct-settlement-without-include-physical-value.png)

**Clave del diagrama:**

- Las transacciones de inventario se representan por medio de flechas verticales.
- Las transacciones físicas están representadas por flechas grises claras más cortas.
- Las transacciones financieras están representadas por flechas negras más largas.
- Las recepciones de inventario se representan por medio de flechas verticales por encima del eje.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo del eje.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican el orden de los registros de transacciones de inventario en la línea de tiempo.
- Las fechas están separadas por finas líneas negras verticales. Las fechas se anotan en la parte inferior del diagrama.
- Los cierres de inventario se representan por medio de líneas rojas verticales discontinuas.
- Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas de rayas que van en sentido diagonal desde las recepciones a las emisiones.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-isnt-used"></a>Liquidación resumida de la fecha de media ponderada cuando no se usa la opción Incluir valor físico en coste

Cuando hay varios recibos en un período, la fecha de media ponderada utiliza el principio de liquidación de que todas las recepciones dentro de un día único se resumen en una transacción denominada *cierre de inventario de media ponderada*. Todas las recepciones del día se liquidarán con la emisión de la transacción de inventario recién creada. Todas las emisiones del día se liquidarán contra la recepción de la nueva transacción de inventario. Si hay un valor restante de inventario disponible tras el cierre del inventario, el valor del inventario disponible se incluye en el recibo de la transacción de las transacciones de cierre de inventario de media ponderada.

En el diagrama siguiente se muestran estas transacciones:

**Día 1:**

- 1a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
- 1b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
- 2a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 20,00 dólares USD por unidad.
- 2b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 22,00 dólares USD por unidad.
- 3a. Recepción del inventario físico de una cantidad de 1 unidad con un precio de coste de 16,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).
- 3b. Emisión del inventario financiero de una cantidad de 1 unidad con un precio de coste de 16,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).

**Día 2:**

- 4a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 25,00 dólares USD por unidad.
- 5a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
- 5b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
- 6a. Recepción del inventario físico de una cantidad de 1 unidad con un precio de coste de 23,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).

**Día 3:**

- 7\. Se efectúa el cierre de inventario.
- 7a. Se crea una emisión financiera Transacción de cierre de inventario de media ponderada para realizar la suma de las liquidaciones de todas las recepciones financieras de inventario.

    - La transacción 1b se liquida por una cantidad de 1 con una cantidad liquidada de USD 10,00.
    - La transacción 2b se liquida por una cantidad de 1 con una cantidad liquidada de USD 22,00.
    - La transacción 7a se liquida por una cantidad de 2 con una cantidad liquidada de USD 32,00. Esta transacción compensa la suma de las dos transacciones de recibo que se actualizan financieramente en el período.

- 7b. Se crea una recepción del inventario financiero para la transacción de cierre de inventario de media ponderada como contrapartida de las operaciones financieras cerradas.

    - La transacción 3b se liquida por una cantidad de 1 con una cantidad liquidada de USD 16,00. Esta transacción no se ajusta porque es el promedio ponderado de las transacciones registradas financieramente el 1 de diciembre (12/1).
    - La transacción 7b se crea para una cantidad de 2 con un monto financiero de USD 32,00 y un monto liquidado de USD 16,00 para compensar la transacción 3b. Esta transacción compensa la suma de la transacción de recibo que se actualiza financieramente en el período. La transacción permanece abierta porque todavía hay uno disponible.

En el diagrama siguiente se muestra esta serie de transacciones con los efectos que resultan de elegir el modelo de inventario de media ponderada y el principio de liquidación resumida pero sin usar la opción **Incluir valor físico en coste**.

![Liquidación resumida de la fecha de media ponderada sin la opción Incluir valor físico en coste.](media/weighted-average-date-summarized-settlement-without-include-physical-value.png)

**Clave del diagrama:**

- Las transacciones de inventario se representan por medio de flechas verticales.
- Las transacciones físicas están representadas por flechas grises claras más cortas.
- Las transacciones financieras están representadas por flechas negras más largas.
- Las recepciones de inventario se representan por medio de flechas verticales por encima del eje.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo del eje.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican el orden de los registros de transacciones de inventario en la línea de tiempo.
- Las fechas están separadas por finas líneas negras verticales. Las fechas se anotan en la parte inferior del diagrama.
- Los cierres de inventario se representan por medio de líneas rojas verticales discontinuas.
- Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas de rayas que van en sentido diagonal desde las recepciones a las emisiones.

## <a name="weighted-average-date-direct-settlement-when-the-include-physical-value-option-is-used"></a>Liquidación directa de la fecha de media ponderada cuando se usa la opción Incluir valor físico en coste

En la versión actual del producto, la opción **Incluir valor físico en coste** funciona de manera diferente con el modelo de inventario de fecha de media ponderada que funcionaba en las versiones anteriores. Cuando selecciona la casilla **Incluir valor físico en coste** para un artículo en la página **Grupo de modelos de artículo**, el sistema utiliza las recepciones actualizadas físicamente al calcular el precio de coste estimado o el promedio móvil. Las emisiones se registrarán con el precio de coste estimado durante el período. Durante el cierre de inventario, solo se tendrán en cuenta para el cálculo de la media ponderada las transacciones de recepción actualizadas financieramente.

En el diagrama siguiente se muestran estas transacciones:

**Día 1:**

- 1a. Recepción del inventario físico de una cantidad de 10 unidad a un coste de 10,00 dólares USD por unidad.
- 1b. Recepción del inventario financiero de una cantidad de 10 unidad a un coste de 10,00 dólares USD por unidad.
- 2a. Recepción del inventario físico de una cantidad de 10 unidad a un coste de 20,00 dólares USD por unidad.
- 3a. Emisión del inventario físico de una cantidad de 1 unidad con un precio de coste de 15,00 dólares USD por unidad (promedio móvil de transacciones registradas física y financieramente).
- 3b. Emisión del inventario financiero de una cantidad de 1 unidad con un precio de coste de 15,00 dólares USD por unidad (promedio móvil de transacciones registradas física y financieramente).

**Día 2:**

- 4a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 25,00 dólares USD por unidad.
- 5a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
- 5b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
- 6a. Emisión del inventario físico de una cantidad de 1 unidad con un precio de 21,25 dólares USD por unidad (promedio móvil de transacciones registradas física y financieramente).

**Día 3:**

- 7\. Se efectúa el cierre de inventario. Basado en el método de fecha de promedio ponderado, el sistema utiliza el método de liquidación directa para el 30 de diciembre (30/12) porque solo se actualiza financieramente un recibo el 30/12. En este ejemplo, se crea un asentamiento entre las transacciones 1b y 3b. No se hace ningún ajuste a la emisión el 30/12. Además, no se realiza ningún ajuste o liquidación al 31 de diciembre (31/12) porque no hay emisiones actualizadas financieramente al 31/12.

En el diagrama siguiente se muestra esta serie de transacciones y los efectos que resultan de usar el modelo de inventario de media ponderada y el principio de liquidación directa con la opción **Incluir valor físico** en coste.

![Liquidación directa de media ponderada con la opción Incluir valor físico en coste.](media/weighted-average-date-direct-settlement-with-include-physical-value.png)

**Clave del diagrama:**

- Las transacciones de inventario se representan por medio de flechas verticales.
- Las transacciones físicas están representadas por flechas grises claras más cortas.
- Las transacciones financieras están representadas por flechas negras más largas.
- Las recepciones de inventario se representan por medio de flechas verticales por encima del eje.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo del eje.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican el orden de los registros de transacciones de inventario en la línea de tiempo.
- Las fechas están separadas por finas líneas negras verticales. Las fechas se anotan en la parte inferior del diagrama.
- Los cierres de inventario se representan por medio de líneas rojas verticales discontinuas.
- Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas de rayas que van en sentido diagonal desde las recepciones a las emisiones.

## <a name="weighted-average-date-summarized-settlement-when-the-include-physical-value-option-is-used"></a>Liquidación resumida de la fecha de media ponderada cuando se usa la opción Incluir valor físico en coste

En la versión actual del producto, la opción **Incluir valor físico en coste** funciona de manera diferente con el modelo de inventario de media ponderada que funcionaba en las versiones anteriores. Cuando selecciona la casilla **Incluir valor físico en coste** para un artículo en la página **Grupo de modelos de artículo**, el sistema utiliza las recepciones actualizadas físicamente al calcular el precio de coste estimado o el promedio móvil. Las emisiones se registrarán con el precio de coste estimado durante el período. Durante el cierre de inventario, solo se tendrán en cuenta para el cálculo de la media ponderada las transacciones de recepción actualizadas financieramente. Es recomendable que realice un cierre de inventario mensual cuando se usa el modelo de inventario de media ponderada. En este ejemplo de liquidación resumida de fecha de media ponderada, el modelo de inventario está marcado para incluir el valor físico en coste.

En el diagrama siguiente se muestran estas transacciones:

**Día 1:**

- 1a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
- 1b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
- 2a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 20,00 dólares USD por unidad.
- 2b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 22,00 dólares USD por unidad.
- 3a. Emisión del inventario físico de una cantidad de 1 unidad con un precio de coste de 16,00 dólares USD por unidad (promedio móvil de transacciones registradas física y financieramente).
- 3b. Emisión del inventario financiero de una cantidad de 1 unidad con un precio de coste de 16,00 dólares USD por unidad (promedio móvil de transacciones registradas física y financieramente).

**Día 2:**

- 4a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 25,00 dólares USD por unidad.
- 5a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
- 5b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
- 6a. Emisión del inventario físico de una cantidad de 1 unidad con un precio de coste de 23,67 dólares USD por unidad (promedio móvil de transacciones registradas física y financieramente).

**Día 3:**

- 7\. Se efectúa el cierre de inventario.
- 7a. Se crea una emisión financiera Transacción de cierre de inventario de media ponderada para realizar la suma de las liquidaciones de todas las recepciones financieras de inventario.

    - La transacción 1b se liquida por una cantidad de 1 con una cantidad liquidada de USD 10,00.
    - La transacción 2b se liquida por una cantidad de 1 con una cantidad liquidada de USD 22,00.
    - La transacción 7a se liquida por una cantidad de 2 con una cantidad liquidada de USD 32,00. Esta transacción compensa la suma de las dos transacciones de recibo que se actualizan financieramente en el período.

- 7b. Se crea una recepción del inventario financiero para la transacción de cierre de inventario de media ponderada como contrapartida de las operaciones financieras cerradas.

    - La transacción 3b se liquida por una cantidad de 1 con una cantidad liquidada de USD 16,00. Esta transacción no se ajusta porque es el promedio ponderado de las transacciones registradas financieramente el 1 de diciembre (12/1).
    - La transacción 7b se crea para una cantidad de 2 con un monto financiero de USD 32,00 y un monto liquidado de USD 16,00 para compensar la transacción 3b. Esta transacción compensa la suma de la transacción de recibo que se actualiza financieramente en el período. La transacción permanece abierta porque todavía hay uno disponible.

En el diagrama siguiente se muestra esta serie de transacciones y los efectos que resultan de usar el modelo de inventario de media ponderada y el principio de liquidación resumida sin la opción **Incluir valor físico** en coste.

![Liquidación resumida de media ponderada con Incluir valor físico en coste.](media/weighted-average-date-summarized-settlement-with-include-physical-value.png)

**Clave del diagrama:**

- Las transacciones de inventario se representan por medio de flechas verticales.
- Las transacciones físicas están representadas por flechas grises claras más cortas.
- Las transacciones financieras están representadas por flechas negras más largas.
- Las recepciones de inventario se representan por medio de flechas verticales por encima del eje.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo del eje.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican el orden de los registros de transacciones de inventario en la línea de tiempo.
- Las fechas están separadas por finas líneas negras verticales. Las fechas se anotan en la parte inferior del diagrama.
- Los cierres de inventario se representan por medio de líneas rojas verticales discontinuas.
- Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas de rayas que van en sentido diagonal desde las recepciones a las emisiones.

## <a name="weighted-average-date-when-marking-is-used"></a>Fecha de media ponderada cuando se usa el marcado

La marcación es un proceso que permite vincular, o marcar, una transacción de emisión con una transacción de recepción. La marcación se puede efectuar con anterioridad o con posterioridad al registro de una transacción. Puede utilizar la marcación cuando desee asegurarse del coste exacto del inventario cuando se registra una transacción o cuando se efectúa el cierre de inventario.

Por ejemplo, supongamos que el Departamento de Atención al Cliente ha aceptado un pedido urgente de un cliente importante. Al tratarse de un pedido urgente, tendrá que pagar más por el artículo para poder responder a la solicitud del cliente. Debe asegurarse de que el coste del artículo de inventario correspondiente queda reflejado en el margen, o coste de mercancías vendidas (COGS), de la factura de este pedido de ventas.

Cuando se registra el pedido de compra, se anota la recepción en el inventario con un coste de 120,00 USD. Si se marca el documento de pedido de ventas con el pedido de compra antes de registrar el albarán o la factura, el coste de mercancías vendidas (COGS) será de 120,00 dólares, en lugar del precio de coste promedio móvil actual del artículo. Si el albarán o la factura del pedido de ventas se registra después de que se realice la marcación, el coste de mercancías vendidas (COGS) se registrará con el precio de coste promedio móvil.

Antes de que se efectúe el cierre de inventario, puede mantenerse el marcado de las transacciones.

Si una transacción de recepción se marca con una transacción de emisión, se descarta el método de valoración seleccionado en el grupo de modelos de artículo y el sistema liquidará estas transacciones entre sí.

Puede marcar una transacción de emisión con una transacción de recepción antes de registrar una transacción. Puede hacer este marcado desde una línea de pedido de ventas en la página **Detalles del pedido de ventas**. Las transacciones de recepción abiertas se ven en la página **Marcado**.

También puede marcar una transacción de emisión con una transacción de recepción después de registrarla. Puede confrontar o marcar una transacción de emisión para una transacción de recepción abierta para un artículo en inventario desde un diario de ajuste de inventario registrado.

En el diagrama siguiente se muestran estas transacciones:

**Día 1:**

- 1a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
- 1b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
- 2a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 20,00 dólares USD por unidad.
- 2b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 22,00 dólares USD por unidad.
- 3a. Recepción del inventario físico de una cantidad de 1 unidad con un precio de coste de 16,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).
- 3b. Emisión del inventario financiero de una cantidad de 1 unidad con un precio de coste de 16,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).
- 3c. El problema financiero de inventario para la transacción 3b está marcado como problema financiero de inventario para la transacción 2b.

**Día 2:**

- 4a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 25,00 dólares USD por unidad.
- 5a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
- 5b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
- 6a. Recepción del inventario físico de una cantidad de 1 unidad con un precio de coste de 23,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).

**Día 3:**

- 7\. Se efectúa el cierre de inventario. Según el principio de marcado que utiliza el método de media ponderada, las transacciones marcadas se liquidan entre sí. En este ejemplo, la transacción 3b se liquida contra la transacción 2b, y se contabiliza un ajuste para USD 6,00 en la transacción 3b para llevar el valor a USD 22,00. En este ejemplo, no se realizan liquidaciones adicionales porque el cierre crea liquidaciones solo para transacciones actualizadas financieramente.

El diagrama siguiente muestra esta serie de transacciones y los efectos que resultan de usar el inventario de media ponderada y el marcado.

![Media ponderada con marcado.](media/weighted-average-date-with-marking.png)

**Clave del diagrama:**

- Las transacciones de inventario se representan por medio de flechas verticales.
- Las transacciones físicas están representadas por flechas grises claras más cortas.
- Las transacciones financieras están representadas por flechas negras más largas.
- Las recepciones de inventario se representan por medio de flechas verticales por encima del eje.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo del eje.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican el orden de los registros de transacciones de inventario en la línea de tiempo.
- Las fechas están separadas por finas líneas negras verticales. Las fechas se anotan en la parte inferior del diagrama.
- Los cierres de inventario se representan por medio de líneas rojas verticales discontinuas.
- Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas de rayas que van en sentido diagonal desde las recepciones a las emisiones.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
