---
title: Recuperar la operación de pedido en PDV
description: Este tema explica las capacidades de las funciones disponibles para mejorar las páginas de recuperación de pedidos en POS.
author: hhainesms
ms.date: 03/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 7a9507cd7f2a1612ab4063d6307b72d8522619ba
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6349433"
---
# <a name="recall-order-operation-in-pos"></a>Recuperar la operación de pedido en PDV

[!include [banner](includes/banner.md)]

La operación de **recuperación de pedidos** en el punto de venta comercial (POS) proporciona funciones de filtrado y búsqueda de pedidos actualizadas e información específica del pedido. Esta función está disponible en las versiones de Commerce 10.0.15 y posteriores.

Para habilitar esta funcionalidad, active la función **Operación mejorada de pedido de recuperación en PDV** en el espacio de trabajo **Gestión de funciones** en Commerce Headquarters. Después de habilitar la función, considere actualizar sus [diseños de pantalla](pos-screen-layouts.md) en el PDV para aprovechar algunas de las capacidades cambiadas.

La configuración del botón de operación **Recuperar pedido** permite a las organizaciones implementar la operación con una pantalla predefinida.

![Configuración de cuadrícula de botones.](media/recallorderbuttongrid.png)

Las opciones de visualización son las siguientes.
- **Ninguna** - Esta opción despliega la operación sin visualización específica. Cuando un usuario abre la operación con esta configuración, se le pedirá que busque y encuentre pedidos o elija entre un filtro de pedidos predefinido.
- **Órdenes a cumplir**: cuando un usuario inicia la operación, se ejecutará automáticamente una consulta para buscar y mostrar una lista de pedidos que debe atender la tienda del usuario actual. Estos pedidos están configurados para recogida en tienda o envío en tienda y las líneas de estos pedidos aún no se han recogido ni embalado.
- **Órdenes a recoger** - Cuando un usuario inicia la operación, se ejecutará automáticamente una consulta para buscar y mostrar una lista de pedidos que están configurados para la recogida en la tienda actual del usuario.
- **Órdenes a enviar** - Cuando un usuario inicia la operación, se ejecutará automáticamente una consulta para buscar y mostrar una lista de pedidos que están configurados para el envío desde la tienda actual del usuario.

Al iniciar la operación **Recuperar pedido** desde el PDV, si la pantalla está configurada para **Ninguno**, un usuario podrá buscar y recuperar los pedidos de una de las siguientes formas.
- Escanee códigos de barras de pedidos. Esto buscará coincidencias en los campos de número de orden, referencia de canal e ID de recibo.
- Seleccione **Buscar órdenes** o **Buscar y filtrar** en la barra de aplicaciones para usar el mecanismo de filtrado para localizar pedidos que cumplan con los criterios de filtrado.
- Elija entre un filtro predefinido del menú desplegable **Mostrar pedidos** (pedidos para cumplir, pedidos para recoger o pedidos para enviar).

![RecallOrderMainMenu.](media/recallordermain.png)

Después de aplicar los criterios de búsqueda, la aplicación mostrará una lista de pedidos de ventas coincidentes. Es importante tener en cuenta que al utilizar las opciones de búsqueda/filtro, los pedidos recuperados no tienen que ser pedidos vinculados a la tienda actual del usuario. Este proceso de búsqueda recuperará y mostrará cualquier pedido de cliente que coincida con los criterios de búsqueda, incluso si el pedido se creó o configuró para ser cumplido por otra tienda/canal o ubicación de almacén.

![RecallOrderDetail.](media/orderrecalldetail.png)

Un usuario puede seleccionar un pedido de la lista para ver detalles adicionales. El panel de información en el lado derecho de la pantalla muestra detalles sobre el pedido seleccionado, incluidos los detalles de la línea del pedido, los detalles de la entrega y los detalles de cumplimiento.

Desde la barra de aplicaciones, un usuario puede seleccionar una operación. Dependiendo del estado del pedido, es posible que algunas operaciones no estén habilitadas.

- **Devolución**: inicia el proceso de creación de una devolución para cualquiera de los productos facturados en el pedido del cliente seleccionado.

- **Cancelar** - Emitir una cancelación total de la orden de venta seleccionada. Esta opción no estará disponible para pedidos iniciados a través de un canal de centro de llamadas y no se puede utilizar para cancelar parcialmente un pedido.

- **Cumplir** - Transfiere al usuario a la página de cumplimiento del pedido, que se prefiltrará para el pedido seleccionado. Solo se mostrarán las líneas de pedido que estén abiertas para el cumplimiento por parte de la tienda del usuario para el pedido seleccionado.

- **Editar** - Permite a los usuarios realizar cambios en el pedido del cliente seleccionado. Los pedidos solo se pueden editar en [ciertos escenarios](customer-orders-overview.md#edit-an-existing-customer-order).

- **Recoger**: esta opción estará disponible si el pedido tiene una o más líneas designadas para recoger en la tienda actual del usuario. Esta operación lanza el flujo de recogida, que permite al usuario elegir los productos a recoger y crea la transacción de venta de recogida.

## <a name="add-notifications-to-the-recall-order-operation"></a>Agregar notificaciones a la operación de pedido de recuperación

En la versión 10.0.18 y posteriores, puede configurar notificaciones de PDV y alertas de mosaicos en vivo para la operación **Recuperación de pedidos** si lo desea. Para más información, consulte [Mostrar notificaciones de pedidos en el punto de venta (PDV)](notifications-pos.md).  

[!INCLUDE[footer-include](../includes/footer-banner.md)]
