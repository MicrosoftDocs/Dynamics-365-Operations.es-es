---
title: Recuperar la operación de pedido en PDV
description: Este tema explica las capacidades de las funciones disponibles para mejorar las páginas de recuperación de pedidos en POS.
author: hhainesms
manager: annbe
ms.date: 10/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 42b11ff16757d633b868dfdf248341193a44378f
ms.sourcegitcommit: 9c05d48f6e03532aa711e1d89d0b2981e9d37200
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/03/2020
ms.locfileid: "4665307"
---
# <a name="recall-order-operation-in-pos"></a>Recuperar la operación de pedido en PDV

[!include [banner](includes/banner.md)]

La operación de **recuperación de pedidos** en el punto de venta comercial (POS) proporciona funciones de filtrado y búsqueda de pedidos actualizadas e información específica del pedido. Esta función está disponible en las versiones de Commerce 10.0.15 y posteriores.

Para habilitar esta funcionalidad, active la función **Operación mejorada de pedido de recuperación en PDV** en el espacio de trabajo **Gestión de funciones** en Commerce Headquarters. Después de habilitar la función, considere actualizar sus [diseños de pantalla](pos-screen-layouts.md) en el PDV para aprovechar algunas de las capacidades cambiadas.

La configuración del botón de operación **Recuperar pedido** permite a las organizaciones implementar la operación con una pantalla predefinida.

![Configuración de cuadrícula de botones](media/recallorderbuttongrid.png)

Las opciones de visualización son las siguientes.
- **Ninguna** - Esta opción despliega la operación sin visualización específica. Cuando un usuario abre la operación con esta configuración, se le pedirá que busque y encuentre pedidos o elija entre un filtro de pedidos predefinido.
- **Órdenes a cumplir** - Cuando un usuario inicia la operación, se ejecutará automáticamente una consulta para buscar y mostrar una lista de pedidos que debe atender la tienda. Estos pedidos están configurados para recogida en tienda o envío en tienda y las líneas de estos pedidos aún no se han recogido ni embalado.
- **Órdenes a recoger** - Cuando un usuario inicia la operación, se ejecutará automáticamente una consulta para buscar y mostrar una lista de pedidos que están configurados para la recogida en la tienda actual del usuario.
- **Órdenes a enviar** - Cuando un usuario inicia la operación, se ejecutará automáticamente una consulta para buscar y mostrar una lista de pedidos que están configurados para el envío desde la tienda actual del usuario.

Al iniciar la operación **Recuperar pedido** desde el PDV, si la pantalla está configurada para **Ninguno**, un usuario podrá buscar y recuperar los pedidos de una de las siguientes formas.
- Escanee códigos de barras de pedidos. Esto buscará coincidencias en los campos de número de orden, referencia de canal e ID de recibo.
- Seleccione **Buscar órdenes** o **Buscar y filtrar** en la barra de aplicaciones para usar el mecanismo de filtrado para localizar pedidos que cumplan con los criterios de filtrado.
- Elija entre un filtro predefinido del menú desplegable **Mostrar pedidos** (pedidos para cumplir, pedidos para recoger o pedidos para enviar).

![RecallOrderMainMenu](media/recallordermain.png)

Después de aplicar los criterios de búsqueda, la aplicación mostrará una lista de pedidos de ventas coincidentes.

![RecallOrderDetail](media/orderrecalldetail.png)

Un usuario puede seleccionar un pedido de la lista para ver detalles adicionales. El panel de información en el lado derecho de la pantalla muestra detalles sobre el pedido seleccionado, incluidos los detalles de la línea del pedido, los detalles de la entrega y los detalles de cumplimiento.

Desde la barra de aplicaciones, un usuario puede seleccionar una operación. Dependiendo del estado del pedido, es posible que algunas operaciones no estén habilitadas.

- **Regreso** - Ejecuta una devolución para una o más facturas relacionadas con el pedido del cliente seleccionado.

- **Cancelar** - Emitir una cancelación total de la orden de venta seleccionada.

- **Cumplir** - Transfiere al usuario a la página de cumplimiento del pedido, que se prefiltrará para el pedido seleccionado. Solo se mostrarán las líneas de pedido que estén abiertas para el cumplimiento por parte de la tienda del usuario para el pedido seleccionado.

- **Editar** - Permite a los usuarios realizar cambios en el pedido del cliente seleccionado.

- **Recoger** - Lanza el flujo de recogida, que permite al usuario elegir los productos a recoger y crea la transacción de venta de recogida.
