---
title: LIFO con valor físico y marcado
description: El método de valoración contable LIFO (Último en entrar, primero en salir) es un modelo de inventario según el cual las últimas recepciones (o recepciones más recientes) se emiten primero. Las emisiones del inventario se liquidan contra las últimas recepciones del inventario según la fecha de transacción de inventario.
author: JennySong-SH
ms.date: 02/02/2022
ms.topic: article
ms.search.form: InventJournalLossProfit, InventMarking, InventModelGroup, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 55021
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c1acc103291c5d648ac7e179a598348cd9cc2a93
ms.sourcegitcommit: 6b209919de39c15e0ebe4abc9cbcd30618f2af0b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/11/2022
ms.locfileid: "9135581"
---
# <a name="lifo-with-physical-value-and-marking"></a>LIFO con valor físico y marcado

[!include [banner](../includes/banner.md)]

Último en entrar, primero en salir (LIFO) es un método de valoración y gestión de inventario en el que el inventario que se produjo o adquirió en último lugar se vende, utiliza o elimina primero. Durante el proceso de cierre de inventario en Microsoft Dynamics 365 Supply Chain Management, el sistema creará liquidaciones donde el último recibo se coteja con la primera emisión, y así sucesivamente. El principio de liquidación y casamiento se basa en la fecha financiera de las transacciones de inventario. Se puede realizar una evaluación preliminar de las liquidaciones y ajustes ejecutando el proceso de recálculo de inventario.

Puede reemplazar el principio LIFO marcando las transacciones de inventario de modo que se liquide una recepción de artículo específica con una emisión específica. Se requiere un cierre de inventario periódico cuando utiliza el modelo de inventario LIFO para crear liquidaciones y ajustar el valor de las emisiones de acuerdo con el principio LIFO. Hasta que ejecute el proceso de cierre de inventario, las transacciones de emisión se valoran en el promedio móvil cuando ocurrieron las actualizaciones físicas y financieras. A menos que esté utilizando el marcado, el promedio móvil se calcula cuando se realiza la actualización física o financiera.

En los ejemplos siguientes muestran los efectos del uso de LIFO con tres configuraciones:

- LIFO sin la opción **Incluir valor físico**
- LIFO con la opción **Incluir valor físico**
- LIFO con marcado

## <a name="lifo-without-the-include-physical-value-option"></a>LIFO sin la opción Incluir valor físico

En este ejemplo, la casilla de verificación **Incluir valor físico** está desactivada en el grupo de modelo de artículo para el producto emitido. En la ilustración siguiente se muestran estas transacciones:

- 1a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
- 1b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 10,00 dólares USD por unidad.
- 2a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 20,00 dólares USD por unidad.
- 2b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 22,00 dólares USD por unidad.
- 3a. Recepción del inventario físico de una cantidad de 1 unidad con un precio de coste de 16,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).
- 3b. Emisión del inventario financiero de una cantidad de 1 unidad con un precio de coste de 16,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente).
- 4a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 25,00 dólares USD por unidad.
- 5a. Recepción del inventario físico de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
- 5b. Recepción del inventario financiero de una cantidad de 1 unidad a un coste de 30,00 dólares USD por unidad.
- 6a. Recepción del inventario físico de una cantidad de 1 unidad con un precio de coste de 23,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente)
- 7\. Se efectúa el cierre de inventario. Según el método LIFO, la primera emisión actualizada financieramente se liquidará contra la última recepción actualizada financieramente, etc. En este ejemplo, se crea un asentamiento entre 5b y 3b. Se realizará un ajuste de USD 14.00 a 3b, y el costo final resultante será USD 30.00.

El ejemplo siguiente muestra los efectos del modelo de inventario FIFO sobre esta serie de transacciones cuando no se usa la opción **Incluir valor físico**.

![LIFO sin la opción Incluir valor físico en coste.](./media/lifo-without-including-physical-value.png)

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

## <a name="lifo-with-the-include-physical-value-option"></a>LIFO con la opción Incluir valor físico

Si se ha seleccionado la casilla **Incluir valor físico** para un artículo en la página **Grupos de modelos de artículo**, el sistema utilizará tanto las transacciones de recepción del inventario físico como financiero para calcular el precio de coste promedio móvil. Cuando proceda, el sistema también ajusta la transacción de emisión actualizada físicamente. Si se ha desactivado la casilla **Incluir valor físico**, el cierre de inventario que usa el modelo de inventario LIFO realizará únicamente las liquidaciones de las transacciones actualizadas financieramente.

En la ilustración siguiente se muestran estas transacciones:

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
- 7\. Se efectúa el cierre de inventario. Según el método LIFO, la primera emisión actualizada financieramente se liquidará contra la última recepción actualizada financieramente, etc. En este ejemplo, se crea un asentamiento entre 3b y 5b. Se realizará un ajuste de USD 14.00 a 3b, y el costo final resultante será USD 30.00. Además, la transacción 6a se ajustará al coste de la transacción de recepción 4a. El sistema no liquidará estas transacciones debido a que la recepción se actualiza físicamente pero no financieramente. En su lugar, solo se publicará un ajuste de USD 1,33 en la transacción de emisión física y el costo ajustado resultante será USD 25,00.

La ilustración siguiente muestra los efectos del modelo de inventario LIFO sobre esta serie de transacciones cuando no se usa la opción **Incluir valor físico**.

![LIFO con la opción Incluir valor físico en coste.](./media/lifo-with-included-physical-value.png)

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

## <a name="lifo-with-marking"></a>LIFO con marcado

La marcación es un proceso que permite vincular, o marcar, una transacción de emisión con una transacción de recepción. La marcación se puede efectuar con anterioridad o con posterioridad al registro de una transacción. Puede utilizar la marcación cuando desee asegurarse del coste exacto del inventario cuando se registra una transacción o cuando se efectúa el cierre de inventario. Por ejemplo, supongamos que el Departamento de Atención al cliente ha aceptado un pedido urgente de un cliente importante. Al tratarse de un pedido urgente, deberá asumir un mayor coste del artículo para poder responder a la solicitud del cliente.

Debe asegurarse de que el coste del artículo de inventario correspondiente queda reflejado en el margen, o coste de mercancías vendidas (COGS), de la factura del pedido de ventas. Cuando se registra el pedido de compra, se anota la recepción en el inventario con un coste de 120,00 USD. Si se marca el documento de pedido de ventas con el pedido de compra antes de registrar el albarán o la factura, el coste de mercancías vendidas (COGS) será de 120,00 dólares, y no el precio de coste promedio móvil actual del artículo. Si el albarán o la factura del pedido de ventas se registra antes de que se realice la marcación, el coste de mercancías vendidas (COGS) se registrará con el precio de coste promedio móvil.

Antes de que se efectúe el cierre de inventario, puede mantenerse el marcado de las transacciones.

Puede marcar una transacción de emisión con una transacción de recepción antes de registrar una transacción. Puede realizar esta marca desde una línea de orden de venta en la página **Detalles de la orden de venta** seleccionando **Inventario \> Calificación** en la ficha desplegable **Líneas de orden de venta**. Puede ver las transacciones de recepción abiertas en la página **Marcado**.

También puede marcar una transacción de emisión con una transacción de recepción después de registrarla. Puede confrontar o marcar una transacción de emisión para una transacción de recepción abierta para un artículo en inventario desde un diario de ajuste de inventario registrado.

En la ilustración siguiente se muestran estas transacciones:

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
- 6a. Recepción del inventario físico de una cantidad de 1 unidad con un precio de coste de 23,00 dólares USD por unidad (promedio móvil de transacciones registradas financieramente)
- 7\. Se efectúa el cierre de inventario. Según el principio de marcado que utiliza el método LIFO, las transacciones marcadas se liquidan entre sí. En este ejemplo, 3b se liquida contra 2b, y se contabiliza un ajuste para USD 6,00 en 3b para llevar el valor a USD 22,00. En este ejemplo, no se realizan liquidaciones adicionales porque el cierre crea liquidaciones solo para transacciones actualizadas financieramente.

El nuevo precio de coste promedio móvil refleja la media de las transacciones actualizadas financieramente y físicamente, es decir, 17,50 dólares USD.

La ilustración siguiente muestra los efectos del modelo de inventario LIFO en esta serie de transacciones al emplear marcado entre emisiones y recepciones.

![LIFO con marcado.](./media/lifo-with-marking.png)

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
- Las liquidaciones y los marcados que se llevan a cabo mediante el cierre de inventario se representan por medio de flechas rojas de rayas que van en sentido diagonal desde las recepciones a las emisiones.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
