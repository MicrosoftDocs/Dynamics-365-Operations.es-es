---
title: "FIFO con valor físico y marcado"
description: "FIFO (primero en entrar, primero en salir) es un modelo de inventario en que las primeras recepciones adquiridas se emiten primero. Las emisiones actualizadas financieramente del inventario se liquidan contra las primeras recepciones actualizadas financieramente en el inventario, según la fecha financiera de la transacción de inventario."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations, Retail
ms.custom: 54682
ms.assetid: dc0e2855-83a0-41a7-a398-3c7852597d1a
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 2d3a6c412e497952c0c7f5b113990bbe693b0f22
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="fifo-with-physical-value-and-marking"></a>FIFO con valor físico y marcado

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

FIFO (primero en entrar, primero en salir) es un modelo de inventario en que las primeras recepciones adquiridas se emiten primero. Las emisiones actualizadas financieramente del inventario se liquidan contra las primeras recepciones actualizadas financieramente en el inventario, según la fecha financiera de la transacción de inventario. 

Cuando se usa el sistema FIFO no es necesario usar la regla FIFO. En su lugar, puede marcar las transacciones de inventario de modo que se liquide una recepción de artículo específica con una emisión específica. Se recomienda efectuar un cierre periódico del inventario si se usa el modelo de inventario FIFO. En los ejemplos siguientes muestran los efectos del uso de FIFO con tres configuraciones:

-   FIFO sin la opción **Incluir valor físico**
-   FIFO con la opción **Incluir valor físico**
-   FIFO con marcado

## <a name="fifo-without-the-include-physical-value-option"></a>FIFO sin la opción Incluir valor físico en coste
En este ejemplo, el grupo de modelos de artículo no está marcado para incluir el valor físico. En la ilustración siguiente se muestran estas transacciones:

-   1a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
-   1b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
-   2a. Recepción del inventario físico de una cantidad de 2 unidad a un coste de 10,00 dólares USD por unidad.
-   2b. Recepción del inventario financiero de una cantidad de 2 unidad a un coste de 10,00 dólares USD por unidad.
-   3a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 25,00 dólares USD por unidad.
-   4a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
-   4b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
-   5a. Recepción del inventario físico de una cantidad de 1 unidad con un precio de coste de 20,00 dólares USD por unidad (promedio móvil de transacciones actualizadas financieramente).
-   5b. Emisión del inventario financiero de una cantidad de 1 unidad con un precio de coste de 20,00 dólares USD por unidad (promedio móvil de transacciones actualizadas financieramente).
-   6. Se efectúa el cierre de inventario. Según el método FIFO, la primera emisión actualizada financieramente se liquidará contra la primera recepción actualizada financieramente. Se lleva a cabo un ajuste de 10,00 dólares USD en la transacción de emisión.

El nuevo precio de coste promedio móvil refleja la media de las transacciones actualizadas financieramente. Los ejemplos siguientes muestran los efectos del modelo de inventario FIFO sobre esta serie de transacciones cuando no se usa la opción **Incluir valor físico**. ![FIFO sin Incluir valor físico en coste](./media/fifowithoutincludephysicalvalue.gif) 

**Clave del diagrama**

- Las transacciones de inventario se representan por medio de flechas verticales.
- Las recepciones de inventario se representan por medio de flechas verticales por encima de la línea de tiempo.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo de la línea de tiempo.
- Por encima (o por debajo) de cada flecha vertical, se especifica el valor de la transacción de inventario con el formato Quantity@Unitprice.
- Los valores de transacciones de inventario entre paréntesis indican que la transacción de inventario se ha registrado físicamente en el inventario.
- Los valores de transacciones de inventario que no van entre paréntesis indican que la transacción de inventario se ha registrado financieramente en el inventario.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican el orden de los registros de transacciones de inventario en la línea de tiempo.
- Los cierres de inventario se representan por medio de una línea roja vertical discontinua y la etiqueta *Cierre de inventario*.
- Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas de rayas que van en sentido diagonal desde las recepciones a las emisiones.

## <a name="fifo-with-the-include-physical-value-option"></a>FIFO con la opción Incluir valor físico en coste
Si se ha seleccionado la casilla **Incluir valor físico** para un artículo en la página **Grupo de modelos de artículo**, el sistema utilizará tanto las transacciones de recepción del inventario físico como financiero para calcular el precio de coste promedio móvil. Cuando proceda, el sistema realizará también ajustes en la transacción de emisión actualizada físicamente. Si se ha anulado la selección de la casilla **Incluir valor físico**, el cierre de inventario con el modelo de inventario FIFO realizará únicamente las liquidaciones de las transacciones actualizadas financieramente. En la ilustración siguiente se muestran estas transacciones:

-   1a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
-   1b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
-   2a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 20,00 dólares USD por unidad.
-   2b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 20,00 dólares USD por unidad.
-   3a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 25,00 dólares USD por unidad.
-   4a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
-   4b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
-   5a. Emisión del inventario físico de una cantidad de 1 unidad con un precio de coste de 21,25 dólares USD por unidad (promedio móvil de transacciones actualizadas físicamente y financieramente).
-   5b. Emisión del inventario financiero de una cantidad de 1 unidad con un precio de coste de 21,25 dólares USD por unidad (promedio móvil de transacciones actualizadas físicamente y financieramente).
-   6a. Emisión del inventario físico de una cantidad de 1 unidad con un precio de coste de 21,25 dólares USD por unidad.
-   7. Se efectúa el cierre de inventario. Según el método FIFO, la primera transacción de emisión financiera se ajustará o liquidará contra la primera recepción actualizada (financiera o física).

La transacción 5b se liquidará contra la transacción de recepción 1b. Se producirá un ajuste de 11,25 USD a esta transacción de emisión. El nuevo precio de coste promedio móvil refleja la media de las transacciones actualizadas financieramente y físicamente, es decir, 27,50 dólares USD. La ilustración siguiente muestra los efectos del modelo de inventario FIFO sobre esta serie de transacciones cuando no se usa la opción **Incluir valor físico**. ![FIFO con Incluir valor físico en coste](./media/fifowithincludephysicalvalue.gif) 

**Clave del diagrama**

- Las transacciones de inventario se representan por medio de flechas verticales.
- Las recepciones de inventario se representan por medio de flechas verticales por encima de la línea de tiempo.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo de la línea de tiempo.
- Por encima (o por debajo) de cada flecha vertical, se especifica el valor de la transacción de inventario con el formato Quantity@Unitprice.
- Los valores de transacciones de inventario entre paréntesis indican que la transacción de inventario se ha registrado físicamente en el inventario.
- Los valores de transacciones de inventario que no van entre paréntesis indican que la transacción de inventario se ha registrado financieramente en el inventario.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican el orden de los registros de transacciones de inventario en la línea de tiempo.
- Los cierres de inventario se representan por medio de una línea roja vertical discontinua y la etiqueta *Cierre de inventario*.
- Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas de rayas que van en sentido diagonal desde las recepciones a las emisiones.

## <a name="fifo-with-marking"></a>FIFO con marcado
La marcación es un proceso que permite vincular, o marcar, una transacción de emisión con una transacción de recepción. La marcación se puede efectuar con anterioridad o con posterioridad al registro de una transacción. Puede utilizar la marcación cuando desee asegurarse del coste exacto del inventario cuando se registra una transacción o cuando se efectúa el cierre de inventario. Por ejemplo, supongamos que el Departamento de Atención al cliente ha aceptado un pedido urgente de un cliente importante. Al tratarse de un pedido urgente, deberá asumir un mayor coste del artículo para poder responder a la solicitud del cliente. Debe asegurarse de que el coste del artículo de inventario correspondiente queda reflejado en el margen, o coste de mercancías vendidas (COGS), de la factura de este pedido de ventas. Cuando se registra el pedido de compra, se anota la recepción en el inventario con un coste de 120,00 dólares USD. Si se marca el documento de pedido de ventas con el pedido de compra antes de registrar el albarán o la factura, el coste de mercancías vendidas (COGS) será de 120,00 dólares, y no el precio de coste promedio móvil actual del artículo. Si el albarán o la factura del pedido de ventas se registra antes de que se realice la marcación, el coste de mercancías vendidas (COGS) se registrará con el precio de coste promedio móvil. Antes de que se efectúe el cierre de inventario, puede mantenerse el marcado de las transacciones. Cuando una transacción de recepción coincide con una transacción de emisión, se descarta el método de valoración definido en el grupo de modelos de artículo y el sistema liquida estas transacciones entre sí. Puede marcar una transacción de emisión con una transacción de recepción antes de registrar una transacción. Puede hacerlo desde una línea de pedido de ventas en la página **Detalles del pedido de ventas**. Puede ver las transacciones de recepción abiertas en la página **Marcado**. También puede marcar una transacción de emisión con una transacción de recepción después de registrarla. Puede confrontar o marcar una transacción de emisión para una transacción de recepción abierta para un artículo en inventario desde un diario de ajuste de inventario registrado. En la ilustración siguiente se muestran estas transacciones:

-   1a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
-   1b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
-   2a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 20,00 dólares USD por unidad.
-   2b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 20,00 dólares USD por unidad.
-   3a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 25,00 dólares USD por unidad.
-   4a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
-   4b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
-   5a. Emisión del inventario físico de una cantidad de 1 unidad con un precio de coste de 21,25 dólares USD por unidad (promedio móvil de transacciones actualizadas físicamente y financieramente).
-   5b. La emisión del inventario financiero de una cantidad de 1 unidad se marca con la recepción de inventario 2b antes de registrar la transacción. Esta transacción se registra a un precio de coste de 20,00 USD por unidad.
-   6a. Emisión del inventario físico de una cantidad de 1 unidad con un precio de coste de 21,25 dólares USD por unidad.
-   7. Se efectúa el cierre de inventario. Debido a que la transacción FIFO que se ha actualizado financieramente incluye una marca con una recepción existente, estas transacciones se liquidan entre sí y no se realiza ningún ajuste.

El nuevo precio de coste promedio móvil refleja la media de las transacciones actualizadas financieramente y físicamente, es decir, 27,50 dólares USD. La ilustración siguiente muestra los efectos del modelo de inventario FIFO en esta serie de transacciones al emplear marcado entre emisiones y recepciones. ![FIFO con marcado](./media/fifowithmarking.gif) 

**Clave del diagrama**

- Las transacciones de inventario se representan por medio de flechas verticales.
- Las recepciones de inventario se representan por medio de flechas verticales por encima de la línea de tiempo.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo de la línea de tiempo.
- Por encima (o por debajo) de cada flecha vertical, se especifica el valor de la transacción de inventario con el formato Quantity@Unitprice.
- Los valores de transacciones de inventario entre paréntesis indican que la transacción de inventario se ha registrado físicamente en el inventario.
- Los valores de transacciones de inventario que no van entre paréntesis indican que la transacción de inventario se ha registrado financieramente en el inventario.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican el orden de los registros de transacciones de inventario en la línea de tiempo.
- Los cierres de inventario se representan por medio de una línea roja vertical discontinua y la etiqueta *Cierre de inventario*.
- Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas de rayas que van en sentido diagonal desde las recepciones a las emisiones.





