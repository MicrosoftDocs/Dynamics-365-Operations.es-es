---
title: Visión general del proceso de salida
description: En este tema se proporciona información general del proceso de salida en la gestión del inventario.
author: perlynne
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSOrder, WMSShipment, MCRPickingWorkbench, WMSPickingRegistration, CustomFilterGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 274363
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.dyn365.ops.version: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.openlocfilehash: db1a6887e7742700dd3451c9a877b948b5ab691b
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207287"
---
# <a name="outbound-process-overview"></a>Visión general del proceso de salida

[!include [banner](../includes/banner.md)]

En este tema se proporciona información general del proceso de salida en la gestión del inventario.

## <a name="output-orders"></a>Pedidos de salida

Los pedidos de salida se usan para vincular las líneas de pedido de ventas y transferirlas mediante los procesos de selección de salida que usan listas de selección.

Cuando se crean las listas de selección a partir de los pedidos de ventas o de transferencia, se crean automáticamente los pedidos de salida o de envío. Una lista de selección tiene una relación unívoca con un envío. El envío de pedidos de transferencia o el albarán del pedido de ventas se puede procesar desde el mismo envío. 

El siguiente diagrama muestra una vista general del proceso de pedidos de salida. 

[![Vista general del proceso de pedidos de salida](./media/outbound-order.png)](./media/outbound-order.png)

Puede configurar las reglas de salida para determinar cómo desea que el programa gestione el proceso de salida. Puede usar estas reglas para controlar el proceso de envío. En particular, puede usar las reglas para controlar en qué fase del proceso se puede realizar un envío. La siguiente configuración indica cómo se gestionan los procesos de salida.

## <a name="picking-route-status-for-sales-and-transfer-orders"></a>Estado de la ruta de selección para ventas y pedidos de transferencia 

Vaya a **Clientes** \> **Configuración** \> **Parámetros de clientes** y, a continuación, en la pestaña **Actualizaciones**, seleccione un valor en el campo **Estado de la ruta de selección**.

[![Campo del estado de la ruta de selección para pedidos de ventas](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)

Si el campo **Estado de la ruta de selección** se establece en **Completado**, el proceso de selección aparece automáticamente como parte del proceso para crear listas de selección. Si el campo está establecido en **Activado**, las líneas de la lista de selección se deben actualizar manualmente.

La misma configuración se aplica a pedidos de transferencia. Vaya a **Gestión del inventario** \> **Configuración** \> **Parámetros de gestión de inventarios y almacenes** y, a continuación, en la pestaña **Transporte**, seleccione un valor en el campo **Estado de la ruta de selección**.

[![Campo del estado de la ruta de selección para pedidos de transferencia](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)

## <a name="end-output-inventory-orders"></a>Completar los pedidos de inventario de salida

Vaya a **Gestión del inventario** \> **Configuración** \> **Parámetros de gestión de inventarios y almacenes** y, a continuación, en la pestaña **General** , establezca la opción **Completar pedido de inventario de salida**.

[![Opción para completar el pedido de inventario de salida](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)

Cuando el trabajador de almacén reduce las cantidades de la lista de selección, las cantidades correspondientes del pedido de inventario se quitarán del envío. Cuando la lista de selección se actualiza en un momento dado, las cantidades restantes vuelven al pedido si la opción **Completar pedido de inventario de salida** se establece en **Sí**. Si la opción **Completar pedido de inventario de salida** se establece en **No**, las cantidades restantes se conservan como cantidad de pedido de salida abierta y se deben agregar a una nueva lista de selección como parte de la funcionalidad **Abrir pedidos de salida**. 

[![Comando para abrir los pedidos de salida en el menú Funciones](./media/open-output-order.png)](./media/open-output-order.png)

[![Menú Funciones en la página para abrir los pedidos de salida](./media/open-output-order-function.png)](./media/open-output-order-function.png)

## <a name="reduce-quantity"></a>Reducir cantidad

El tercer parámetro que puede usar como parte del proceso de creación de listas de selección, es el parámetro **Reducir cantidad**. La configuración de este parámetro funciona igual que la configuración **Reserva** que activa un proceso de reserva como parte del proceso de liberación al almacén.

[![Parámetro Reducir cantidad](./media/reduce-quantity.png)](./media/reduce-quantity.png)

## <a name="example-of-an-outbound-process-for-a-sales-order"></a>Ejemplo de un proceso de salida de un pedido de ventas

En este ejemplo, hay un pedido de ventas para dos artículos. Durante la creación de la lista de selección, debe seleccionar el parámetro **Reducir cantidad**. Por lo tanto, liberará y creará líneas de selección solo para aquel inventario disponible. Se debe informar de la selección mediante un proceso de registro de listas de selección**Estado de la ruta de selección** = (**Activado**).

El inventario que no se haya reservado se reservará durante la creación de la lista de selección. El inventario que no está disponible se puede quitar del pedido de ventas o se puede liberar al almacén para realizar más adelante un proceso de salida, cuando el inventario esté disponible para realizar una selección.

[![Actualizar la lista de selección](./media/update-picking-list.png)](./media/update-picking-list.png)

Tan pronto como todas las líneas de selección hayan sido utilizadas en la página **Registro de la lista de selección**, se completa el envío asociado. El proceso de los albaranes del pedido de ventas se podrá inicializar en función del inventario seleccionado.

[![Actualizar envíos salientes](./media/outbound-shipments.png)](./media/outbound-shipments.png)
