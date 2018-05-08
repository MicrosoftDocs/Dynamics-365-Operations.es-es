---
title: "LIFO con valor físico y marcado"
description: "El método de valoración contable LIFO (Último en entrar, primero en salir) es un modelo de inventario según el cual las últimas recepciones (o recepciones más recientes) se emiten primero. Las emisiones del inventario se liquidan contra las últimas recepciones del inventario según la fecha de transacción de inventario."
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
ms.custom: 55021
ms.assetid: 49c492b0-b018-44e0-928f-9671e54eee20
ms.search.region: Global
ms.search.industry: Retail
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: db6d04a64821b3b02679056f787092dc40ef4423
ms.contentlocale: es-es
ms.lasthandoff: 11/03/2017

---

# <a name="lifo-with-physical-value-and-marking"></a>LIFO con valor físico y marcado

[!include [banner](../includes/banner.md)]

[!include [retail name](../includes/retail-name.md)]

El método de valoración contable LIFO (Último en entrar, primero en salir) es un modelo de inventario según el cual las últimas recepciones (o recepciones más recientes) se emiten primero. Las emisiones del inventario se liquidan contra las últimas recepciones del inventario según la fecha de transacción de inventario. 

En el modelo de inventario Último en entrar, primero en salir (LIFO), las últimas recepciones (más recientes) se emiten antes. Las emisiones del inventario se liquidan en las últimas recepciones del inventario, según la fecha de transacción de inventario. Cuando se usa el sistema LIFO no es necesario usar la regla LIFO. En su lugar, puede marcar las transacciones de inventario de modo que se liquide una emisión de artículo específica con una recepción específica. Si usa el modelo de inventario LIFO, es recomendable un cierre de inventario periódico. 

En los ejemplos siguientes muestran los efectos del uso de LIFO con tres configuraciones:

-   LIFO sin la opción **Incluir valor físico**
-   LIFO con la opción **Incluir valor físico**
-   LIFO con marcado

## <a name="lifo-without-the-include-physical-value-option"></a>LIFO sin la opción Incluir valor físico
En este ejemplo, el grupo de modelos de artículo no está marcado para incluir el valor físico. En la ilustración siguiente se muestran estas transacciones:

-   1a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
-   1b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
-   2a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 20,00 dólares USD por unidad.
-   2b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 20,00 dólares USD por unidad.
-   3a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 25,00 dólares USD por unidad.
-   4a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
-   4b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
-   5a. Recepción del inventario físico de una cantidad de 1 unidad con un precio de coste de 20,00 dólares USD por unidad (promedio móvil de transacciones actualizadas financieramente).
-   5b. Emisión del inventario financiero de una cantidad de 1 unidad con un precio de coste de 20,00 dólares USD por unidad (promedio móvil de transacciones actualizadas financieramente).
-   6. Se efectúa el cierre de inventario. De acuerdo con el método LIFO, la última emisión actualizada financieramente se liquidará con la última recepción actualizada financieramente. Se lleva a cabo un ajuste de 10,00 dólares USD en la transacción de emisión.

El nuevo precio de coste promedio móvil reflejará la media de transacciones actualizadas financieramente de 15,00 dólares USD. El ejemplo siguiente muestra los efectos del modelo de inventario LIFO sobre esta serie de transacciones cuando no se usa la opción **Incluir valor físico**. ![LIFO sin Incluir valor físico en coste](./media/lifowithoutincludephysicalvalue.gif) 

**Clave del diagrama**

- Las transacciones de inventario se representan por medio de flechas verticales.
- Las recepciones de inventario se representan por medio de flechas verticales por encima de la línea de tiempo.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo de la línea de tiempo.
- Por encima (o por debajo) de cada flecha vertical, se especifica el valor de la transacción de inventario con el formato precio de Quantity@Unit.
- Los valores de transacciones de inventario entre paréntesis indican que la transacción de inventario se ha registrado físicamente en el inventario.
- Los valores de transacciones de inventario que no van entre paréntesis indican que la transacción de inventario se ha registrado financieramente en el inventario.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican el orden de los registros de transacciones de inventario en la línea de tiempo.
- Los cierres de inventario se representan por medio de una línea roja vertical discontinua y la etiqueta *Cierre de inventario*.
- Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas de rayas que van en sentido diagonal desde las recepciones a las emisiones.

## <a name="lifo-with-the-include-physical-value-option"></a>LIFO con la opción Incluir valor físico
Si se ha seleccionado la casilla **Incluir valor físico** para un artículo en la página **Grupos de modelos de artículo**, el sistema utilizará tanto las transacciones de recepción del inventario físico como financiero para calcular el precio de coste promedio móvil. Cuando proceda, el sistema realizará también ajustes en la transacción de emisión actualizada físicamente. Si se ha anulado la selección de la casilla **Incluir valor físico**, el cierre de inventario con el modelo de inventario LIFO realizará únicamente las liquidaciones de las transacciones actualizadas financieramente. 

En la ilustración siguiente se muestran estas transacciones:

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
-   7. Se efectúa el cierre de inventario. De acuerdo con el método LIFO, la última transacción de emisión se ajustará o se liquidará con la última recepción actualizada.

La transacción 6a se ajustará a la transacción de recepción 4b. El sistema no liquidará estas transacciones debido a que la recepción se actualiza físicamente pero no financieramente. En lugar de ello, se efectuará únicamente un ajuste de 8,75 dólares USA en la transacción de emisión física. La transacción 5b se ajustará a la transacción de recepción física 3a. El sistema no liquidará estas transacciones porque a que no se actualizan financieramente. En lugar de ello, se efectuará únicamente un ajuste de 3,75 dólares USD en esta transacción de emisión. El nuevo precio de coste promedio móvil refleja la media de las transacciones actualizadas financieramente y físicamente, es decir, 20,00 dólares USD. 

La ilustración siguiente muestra los efectos del modelo de inventario LIFO sobre esta serie de transacciones cuando no se usa la opción **Incluir valor físico**. ![LIFO con Incluir valor físico en coste](./media/lifowithincludephysicalvalue.gif) 

**Clave del diagrama**

- Las transacciones de inventario se representan por medio de flechas verticales.
- Las recepciones de inventario se representan por medio de flechas verticales por encima de la línea de tiempo.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo de la línea de tiempo.
- Por encima (o por debajo) de cada flecha vertical, se especifica el valor de la transacción de inventario con el formato precio de Quantity@Unit.
- Los valores de transacciones de inventario entre paréntesis indican que la transacción de inventario se ha registrado físicamente en el inventario.
- Los valores de transacciones de inventario que no van entre paréntesis indican que la transacción de inventario se ha registrado financieramente en el inventario.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican el orden de los registros de transacciones de inventario en la línea de tiempo.
- Los cierres de inventario se representan por medio de una línea roja vertical discontinua y la etiqueta *Cierre de inventario*.
- Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas de rayas que van en sentido diagonal desde las recepciones a las emisiones.

## <a name="lifo-with-marking"></a>LIFO con marcado
La marcación es un proceso que permite vincular, o marcar, una transacción de emisión con una transacción de recepción. La marcación se puede efectuar con anterioridad o con posterioridad al registro de una transacción. Puede utilizar la marcación cuando desee asegurarse del coste exacto del inventario cuando se registra una transacción o cuando se efectúa el cierre de inventario. Por ejemplo, supongamos que el Departamento de Atención al cliente ha aceptado un pedido urgente de un cliente importante. Al tratarse de un pedido urgente, deberá asumir un mayor coste del artículo para poder responder a la solicitud del cliente. 

Debe asegurarse de que el coste del artículo de inventario correspondiente queda reflejado en el margen, o coste de mercancías vendidas (COGS), de la factura de este pedido de ventas. Cuando se registra el pedido de compra, se anota la recepción en el inventario con un coste de 120,00 dólares USD. Si se marca el documento de pedido de ventas con el pedido de compra antes de registrar el albarán o la factura, el coste de mercancías vendidas (COGS) será de 120,00 dólares, y no el precio de coste promedio móvil actual del artículo. Si el albarán o la factura del pedido de ventas se registra antes de que se realice la marcación, el coste de mercancías vendidas (COGS) se registrará con el precio de coste promedio móvil. 

Antes de que se efectúe el cierre de inventario, puede mantenerse el marcado de las transacciones. 

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
-   7. Se efectúa el cierre de inventario. Debido a que la transacción FIFO que se ha actualizado financieramente incluye una marca con una recepción existente, estas transacciones se liquidan entre sí y no se realiza ningún ajuste.

El nuevo precio de coste promedio móvil refleja la media de las transacciones actualizadas financieramente y físicamente, es decir, 27,50 dólares USD. 

La ilustración siguiente muestra los efectos del modelo de inventario LIFO en esta serie de transacciones al emplear marcado entre emisiones y recepciones. ![LIFO con marcado](./media/lifowithmarking.gif) 

**Clave del diagrama**

- Las transacciones de inventario se representan por medio de flechas verticales.
- Las recepciones de inventario se representan por medio de flechas verticales por encima de la línea de tiempo.
- Las emisiones de inventario se representan por medio de flechas verticales por debajo de la línea de tiempo.
- Por encima (o por debajo) de cada flecha vertical, se especifica el valor de la transacción de inventario con el formato precio de Quantity@Unit.
- Los valores de transacciones de inventario entre paréntesis indican que la transacción de inventario se ha registrado físicamente en el inventario.
- Los valores de transacciones de inventario que no van entre paréntesis indican que la transacción de inventario se ha registrado financieramente en el inventario.
- Cada nueva transacción de recepción o emisión está indicada por una nueva etiqueta.
- Cada flecha vertical tiene una etiqueta con un identificador secuencial, por ejemplo, *1a*. Los identificadores indican el orden de los registros de transacciones de inventario en la línea de tiempo.
- Los cierres de inventario se representan por medio de una línea roja vertical discontinua y la etiqueta *Cierre de inventario*.
- Las liquidaciones que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas de rayas que van en sentido diagonal desde las recepciones a las emisiones.





