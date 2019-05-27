---
title: Fecha LIFO con valor físico y marcado
description: El método de valoración contable de fecha LIFO (Último en entrar, primero en salir) es un modelo de inventario. Las emisiones del inventario se liquidan contra las últimas recepciones del inventario según la fecha de transacción de inventario. Mediante la fecha LIFO, si no existe ninguna recepción antes de la emisión, ésta se liquida frente a cualquier recepción que ocurra después de la fecha de la emisión. Varias emisiones en una misma fecha se pueden liquidar en el orden de última emisión, última recepción.
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 51592
ms.assetid: d9f13274-3268-444f-85c8-b686fd39286d
ms.search.region: Global
ms.search.industry: Retail
ms.author: shylaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3913801eb35faec858ef4b8e1e5056b755054218
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "1554745"
---
# <a name="lifo-date-with-physical-value-and-marking"></a>Fecha LIFO con valor físico y marcado

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

El método de valoración contable de fecha LIFO (Último en entrar, primero en salir) es un modelo de inventario. Las emisiones del inventario se liquidan contra las últimas recepciones del inventario según la fecha de transacción de inventario. Mediante la fecha LIFO, si no existe ninguna recepción antes de la emisión, ésta se liquida frente a cualquier recepción que ocurra después de la fecha de la emisión. Varias emisiones en una misma fecha se pueden liquidar en el orden de última emisión, última recepción. 

Cuando se usa el modelo de inventario de fecha LIFO (Último en entrar, primero en salir), si no existe ninguna recepción antes de la emisión, esta se liquida con cualquier recepción que ocurra después de la fecha de la emisión. Varias emisiones en una misma fecha se pueden liquidar en el orden de última emisión, última recepción. Al usar la fecha LIFO, no es necesario usar la regla de fecha LIFO. En su lugar, puede marcar las transacciones de inventario de modo que se liquide una recepción de artículo específica con una emisión específica. 

Se recomienda efectuar un cierre periódico del inventario si se usa el modelo de inventario de fecha LIFO. 

En los ejemplos siguientes muestran los efectos del uso de la fecha LIFO en tres configuraciones:

-   Fecha LIFO sin la opción **Incluir valor físico**
-   Fecha LIFO con la opción**Incluir valor físico**
-   Fecha LIFO con marcado

## <a name="lifo-date-without-the-include-physical-value-option"></a>Fecha LIFO sin la opción Incluir valor físico
En este ejemplo, el grupo de modelos de artículo no está marcado para incluir el valor físico. En la ilustración siguiente se muestran estas transacciones:

-   1a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
-   1b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
-   2a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 20,00 dólares USD por unidad.
-   2b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 20,00 dólares USD por unidad.
-   3a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 25,00 dólares USD por unidad.
-   4a. Recepción del inventario físico de una cantidad de 1 unidad con un precio de coste de 15,00 dólares USD por unidad (promedio móvil de transacciones actualizadas financieramente).
-   4b. Emisión del inventario financiero de una cantidad de 1 unidad con un precio de coste de 15,00 dólares USD por unidad (promedio móvil de transacciones actualizadas financieramente).
-   5a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
-   5b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
-   6. Se efectúa el cierre de inventario. De acuerdo con el método de fecha LIFO, la última emisión actualizada financieramente se liquidará con la última recepción actualizada financieramente por fecha. Se lleva a cabo un ajuste de 5,00 dólares USD en la transacción de emisión. Estas transacciones se liquidarán entre sí.

El nuevo precio de coste promedio móvil reflejará la media de transacciones actualizadas financieramente de 15,00 dólares USD. 

La ilustración siguiente muestra los efectos del modelo de inventario de fecha LIFO cuando no se usa la opción **Incluir valor físico**. ![Fecha LIFO con Incluir valor físico en coste](./media/lifodatewithoutincludephysicalvalue.gif) 

**Clave del diagrama**

- Las transacciones de inventario se representan por medio de flechas verticales.
- Las recepciones de inventario se representan por medio de flechas verticales por encima de la línea de tiempo.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo de la línea de tiempo.
- Por encima (o por debajo) de cada flecha vertical, se especifica el valor de la transacción de inventario con el formato Cantidad@Preciounitario.
- Los valores de transacciones de inventario entre paréntesis indican que la transacción de inventario se ha registrado físicamente en el inventario.
- Los valores de transacciones de inventario que no van entre paréntesis indican que la transacción de inventario se ha registrado financieramente en el inventario.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican el orden de los registros de transacciones de inventario en la línea de tiempo.
- Los cierres de inventario se representan por medio de una línea roja vertical discontinua y la etiqueta *Cierre de inventario*.
- Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas de rayas que van en sentido diagonal desde las recepciones a las emisiones.

## <a name="lifo-date-with-the-include-physical-value-option"></a>Fecha LIFO con la opción Incluir valor físico
Puede activar la casilla **Incluir valor físico** para un artículo en la página **Grupos de modelos de artículo**. En este caso, el sistema usará transacciones de recepción tanto físicas como financieras para calcular el precio de coste promedio móvil. Cuando proceda, el sistema realizará también ajustes en la transacción de emisión actualizada físicamente. Si se ha desactivado la casilla **Incluir valor físico**, el cierre de inventario que usa el modelo de inventario de fecha LIFO realizará únicamente las liquidaciones de las transacciones actualizadas financieramente. 

En este ejemplo, el grupo de modelos de artículo está marcado para incluir el valor físico. 

En la ilustración siguiente se muestran estas transacciones:

-   1a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
-   1b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
-   2a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 20,00 dólares USD por unidad.
-   2b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 20,00 dólares USD por unidad.
-   3a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 25,00 dólares USD por unidad.
-   4a. Emisión del inventario físico de una cantidad de 1 unidad con un precio de coste de 18,33 dólares USD por unidad (promedio móvil de transacciones actualizadas financieramente).
-   4b. Emisión del inventario financiero de una cantidad de 1 unidad con un precio de coste de 18,33 dólares USD por unidad (promedio móvil de transacciones actualizadas financieramente).
-   5a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
-   5b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
-   6. Se efectúa el cierre de inventario. De acuerdo con el método de fecha LIFO, la última emisión actualizada se ajustará o se liquidará con la última recepción actualizada por fecha. Estas transacciones no se liquidarán entre sí ya que la transacción de recepción financiera se ajustará a una transacción actualizada del inventario físico. En lugar de ello, se efectuará únicamente un ajuste de 6,67 dólares en la transacción de emisión.

El nuevo precio de coste promedio móvil refleja la media de las transacciones actualizadas financieramente a 20,00 dólares USD. 

La ilustración siguiente muestra los efectos del modelo de inventario LIFO cuando se usa la opción **Incluir valor físico**. ![Fecha LIFO con Incluir valor físico en coste](./media/lifodatewithincludephysicalvalue.gif) 

**Clave del diagrama**

- Las transacciones de inventario se representan por medio de flechas verticales.
- Las recepciones de inventario se representan por medio de flechas verticales por encima de la línea de tiempo.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo de la línea de tiempo.
- Por encima (o por debajo) de cada flecha vertical, se especifica el valor de la transacción de inventario con el formato Cantidad@Preciounitario.
- Los valores de transacciones de inventario entre paréntesis indican que la transacción de inventario se ha registrado físicamente en el inventario.
- Los valores de transacciones de inventario que no van entre paréntesis indican que la transacción de inventario se ha registrado financieramente en el inventario.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican el orden de los registros de transacciones de inventario en la línea de tiempo.
- Los cierres de inventario se representan por medio de una línea roja vertical discontinua y la etiqueta *Cierre de inventario*.
- Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas de rayas que van en sentido diagonal desde las recepciones a las emisiones.

## <a name="lifo-date-with-marking"></a>Fecha LIFO con marcado
La marcación es un proceso que permite vincular, o marcar, una transacción de emisión con una transacción de recepción. La marcación se puede efectuar con anterioridad o con posterioridad al registro de una transacción. Puede utilizar la marcación cuando desee asegurarse del coste exacto del inventario cuando se registra una transacción o cuando se efectúa el cierre de inventario. 

Por ejemplo, supongamos que el Departamento de Atención al cliente ha aceptado un pedido urgente de un cliente importante. Al tratarse de un pedido urgente, deberá asumir un mayor coste del artículo para poder responder a la solicitud del cliente. Debe asegurarse de que el coste del artículo de inventario correspondiente queda reflejado en el margen, o coste de mercancías vendidas (COGS), de la factura de este pedido de ventas. 

Cuando se registra el pedido de compra, se anota la recepción en el inventario con un coste de 120,00 dólares USD. Si se marca el documento de pedido de ventas con el pedido de compra antes de registrar el albarán o la factura, el coste de mercancías vendidas (COGS) será de 120,00 dólares, y no el precio de coste promedio móvil actual del artículo. Si el albarán o la factura del pedido de ventas se registra antes de que se realice la marcación, el coste de mercancías vendidas (COGS) se registrará con el precio de coste promedio móvil. 

Antes de que se efectúe el cierre de inventario, puede mantenerse el marcado de las transacciones. 

Por ejemplo, una transacción de recepción se marca para una transacción de emisión. En tal caso, se descarta el método de valoración definido en el grupo de modelos del artículo y el sistema liquidará estas transacciones entre sí. 

Puede marcar una transacción de emisión con una transacción de recepción antes de registrar una transacción. Puede hacerlo desde una línea de pedido de ventas en la página **Detalles del pedido de ventas**. Puede ver las transacciones de recepción abiertas en la página **Marcado**. 

También puede marcar una transacción de emisión con una transacción de recepción después de registrarla. Puede confrontar o marcar una transacción de emisión para una transacción de recepción abierta para un artículo en inventario desde un diario de ajuste de inventario registrado. 

En la ilustración siguiente se muestran estas transacciones:

-   1a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
-   1b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
-   2a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 20,00 dólares USD por unidad.
-   2b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 20,00 dólares USD por unidad.
-   3a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 25,00 dólares USD por unidad.
-   4a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
-   4b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
-   5a. Emisión del inventario físico de una cantidad de 1 unidad con un precio de coste de 21,25 dólares USD por unidad (promedio móvil de transacciones actualizadas físicamente y financieramente).
-   5b. La emisión del inventario financiero de una cantidad de 1 unidad se marca con la recepción de inventario 2b antes de registrar la transacción. Esta transacción se registra con un precio de coste de 20,00 dólares USD por unidad.
-   6a. Emisión del inventario físico de una cantidad de 1 unidad con un precio de coste de 21,25 dólares USD por unidad.
-   7. Se efectúa el cierre de inventario. Debido a que la transacción FIFO (Primero en entrar, primero en salir) que se ha actualizado financieramente incluye una marca con una recepción existente, estas transacciones se liquidan entre sí y no se realiza ningún ajuste.

El nuevo precio de coste promedio móvil refleja la media de las transacciones actualizadas financieramente y físicamente a 27,50 dólares USD. 

La siguiente ilustración muestra el efecto que se deriva de seleccionar el modelo de inventario LIFO cuando se usa el marcado entre las emisiones y recepciones. ![Fecha LIFO con marcado](./media/lifodatewithmarking.gif) 

**Clave del diagrama**

- Las transacciones de inventario se representan por medio de flechas verticales.
- Las recepciones de inventario se representan por medio de flechas verticales por encima de la línea de tiempo.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo de la línea de tiempo.
- Por encima (o por debajo) de cada flecha vertical, se especifica el valor de la transacción de inventario con el formato Cantidad@Preciounitario.
- Los valores de transacciones de inventario entre paréntesis indican que la transacción de inventario se ha registrado físicamente en el inventario.
- Los valores de transacciones de inventario que no van entre paréntesis indican que la transacción de inventario se ha registrado financieramente en el inventario.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican el orden de los registros de transacciones de inventario en la línea de tiempo.
- Los cierres de inventario se representan por medio de una línea roja vertical discontinua y la etiqueta *Cierre de inventario*.
- Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas de rayas que van en sentido diagonal desde las recepciones a las emisiones.




