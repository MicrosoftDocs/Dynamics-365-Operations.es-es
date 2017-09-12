---
title: Reservar cantidades de inventario
description: En este tema se describen las diferentes opciones de reserva de inventario disponibles.
author: perlynne
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventModelGroup
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 207264
ms.assetid: 47537e4f-cdf6-4813-96fd-c945b2dfe9d4
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 942a1e9ddcf6e0952da66b239e1884cb83369175
ms.contentlocale: es-es
ms.lasthandoff: 05/25/2017

---

# <a name="reserve-inventory-quantities"></a>Reservar cantidades de inventario

[!include[banner](../includes/banner.md)]


En este tema se describen las diferentes opciones de reserva de inventario disponibles.

Puede reservar automáticamente cantidades de inventarios para un pedido de ventas concreto. Esto significa que el inventario reservado no se puede sacar del almacén para otros pedidos excepto que se cancele la reserva de inventario o parte de la reserva de inventario.

Existen varios motivos para reservar el inventario:
-   Pedido primero, entregado primero, que significa que los clientes obtienen artículos disponibles en el mismo orden en el que cursan sus pedidos.
-   Escasez de artículos debido a un tiempo de entrega largo o desconocido del proveedor. Es posible que desee comprobar que algunos clientes o pedidos consiguen la entrega de los primeros artículos disponibles.
-   Algunos clientes y algunos tipos de pedidos tienen primera prioridad para la entrega.
-   Artículos con números de serie o lote. Puede marcar algunos artículos que se hayan entregado o que se entregarán a pedidos concretos.
-   Artículos pedidos especialmente que se reservan para algunos pedidos.
-   Pedidos de producción. Por ejemplo, puede marcar artículos producidos y ajustados para pedidos concretos.

El inventario se puede reservar automáticamente al crear una línea de pedido, o bien se puede reservar manualmente con los pedidos individuales. También es posible realizar la reserva del inventario en diferentes etapas de un proceso de producción. Solo se pueden reservar los productos en existencias. Los servicios no se pueden reservar porque no hay ningún inventario disponible. Se pueden reservar el inventario físico y disponible aunque aún sin recibir. Si se reserva una cantidad mayor que la que contiene el inventario disponible, se muestra un mensaje que dice que no puede reservar una cantidad tan grande. Entonces puede elegir reservar la cantidad de todas formas o cambiar la cantidad solicitada. La cantidad se puede reservar o cambiar. Si se reservan más artículos de los que están disponibles, la escasez queda cubierta la próxima vez que los artículos estén disponibles para la entrega.

## <a name="inventory-reservation-policies"></a>Directivas de reserva de inventario
Las directivas de reserva de inventario se establecen en la página de **Grupos de modelos de artículos**, en **Parámetros de gestión de inventarios y almacenes** y en **Parámetros de producción**.
### <a name="policies-on-the-item-model-groups-page"></a>Directivas en la página de los grupos de modelos de artículos

La sección de **Directivas de inventario** contiene las siguientes directivas de reserva.
|                         |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
|-------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Directiva de las reservas**  | **Descripción**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    |
| Fecha FIFO controlada    | Si activa la opción **FIFO controlado mediante la fecha**, la reserva de inventario se controla mediante una fecha de ordenación según el principio FIFO. Los lotes se reservan en función de la fecha de recepción de artículos más antigua, según el principio de que el primero en entrar es el primero en salir (FIFO).                                                                                                                                                                                                                                                                       |
| Fechas de envío en orden inverso | Esta opción solo está disponible si se ha seleccionado la opción **FIFO controlado mediante la fecha**. Si activa la casilla **Fecha de envío inverso**, la reserva de inventario se realiza hacia atrás desde la fecha de envío deseada según el principio de que el último en entrar es el primero en salir (LIFO). Si no hay recepciones disponibles antes de la fecha de envío, se utiliza una reserva FIFO.                                                                                                                                                                                                           |
| Reserva de venta de artículos  | Determina si la reserva de artículos se realiza de forma manual o automática. Si es una reserva automática, se reserva el inventario cuando se crean líneas de pedido. Es posible hacer reservas a nivel del número de artículo nivel para listas de materiales (opción **Automático**) o para los elementos individuales de una lista de materiales (opción **Expansión**). El valor predeterminado para la **Reserva de las ventas de artículos** puede heredarse de los **Parámetros de cuentas deudoras**. En dicha página, el valor se establece en el campo de Reserva en la **sección** **Valores predeterminados** de ventas en la pestaña **General**. |
| Selección del mismo lote    | La reserva del mismo lote le permite reservar inventario de una línea del pedido de ventas de un único lote del inventario. Si desea usar esta opción, también debe establecer la opción de **Consolidar requisito** a **Sí**. Hay ajustes adicionales necesarios para el grupo de dimensiones de seguimiento y el grupo de dimensiones de almacenamiento. Para obtener más información, consulte [Reserva del mismo lote para un pedido de ventas](../sales-marketing/reserve-same-batch-sales-order.md).                                                          |
| Consolidar requisito | Esta opción es similar a la opción de **Selección del mismo lote**, y consolida el inventario que se reserva para las líneas de pedido de ventas en un solo requisito.                                                                                                                                                                                                                                                                                                                                                                                      |
| Controlado por fecha FEFO    | Esta opción permite reservar los lotes cercanos a su fecha de vencimiento o fecha de consumo preferente. También debe configurar el campo de **Criterios de selección** para seleccionar la **Fecha de vencimiento** o la **Fecha de consumo preferente**.                                                                                                                                                                                                                                                                                                                              |

#### <a name="example-for-fifo-date-controlled-and-backward-from-ship-date"></a>Ejemplo de FIFO controlado mediante la fecha y Fecha de envío en orden inverso

En este ejemplo, el inventario disponible para el número de artículo A existe para tres números de lote distintos.
| código de artículo | Número de lote | Cantidad | Fecha             |
|-------------|--------------|----------|------------------|
| A           | 1000         | 5        | 2 de febrero de 2016 |
| A           | 1001         | 3        | 1 de enero de 2016  |
| A           | 1002         | 7        | 3 de marzo de 2016    |

Un pedido de ventas que se debe reservar de forma automática en entregada el 4 de abril de 2016 reserva el siguiente lote:
-   Si se desactivan las casillas **FIFO controlado mediante la fecha** y **Fecha de envío inverso**, se reserva el lote 1000 por ser el lote con el número más bajo.
-   Si se activa la casilla **FIFO controlado mediante la fecha** y se desactiva la casilla **Fecha de envío inverso**, se reserva el lote 1001, ya que es el lote con la primera fecha de recibo (FIFO).
-   Si las casillas **FIFO controlado mediante la fecha** y **Fecha de envío inverso** están activadas, se reserva el lote 1002, ya que tiene la fecha de recepción de lote más cercana a la fecha de envío del pedido de ventas.

### <a name="policies-on-the-inventory-and-warehouse-management-parameter-page"></a>Página de directivas de los parámetros de gestión de inventario y almacenes

Existen dos opciones relacionadas con las reservas de la página de **Parámetros de gestión de inventario y almacenes**:
-   La opción de **Reserva de artículos** de la ficha **General** le permite reservar los recibos de los artículos que únicamente se solicitan en emisiones de artículos de las Cuentas deudoras, Gestión de proyectos y contabilidad, y Control de producción. Si no selecciona esta opción, solo podrá reservar artículos que se hayan recibido físicamente. Si un artículo particular se ha configurado para aceptar un inventario negativo, este campo no es relevante.
-   La opción **Reservar artículos automáticamente** de la ficha **Transporte** determina la configuración predeterminada si los artículos se reservan automáticamente para los pedidos de transferencia. La configuración predeterminada se puede anular en pedidos de transferencia individuales.

### <a name="inventory-reservation-policies-on-the-production-parameters-page"></a>Directivas de la reserva de inventario en la página de los Parámetros de producción

El valor del campo **Reserva** de la pestaña **General** en la página de **Parámetros de producción** determina el punto predeterminado en el proceso de producción en el que se debe reservar el inventario. Por ejemplo, el inventario puede reservarse cuando se programa el trabajo o cuando el trabajo se ha iniciado.

