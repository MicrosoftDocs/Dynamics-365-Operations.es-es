---
title: Procesar recogidas de pedidos de clientes en PDV
description: Este tema explica la funcionalidad que está disponible en la aplicación de punto de venta (PDV) para procesar recogidas de pedidos de clientes.
author: Hhainesms
ms.date: 01/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.region: global
ms.author: hhaines
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: b5c17a65a54ae88118bc5ecaa25cdadb67861129
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5802776"
---
# <a name="process-customer-order-pickups-in-pos"></a>Procesar recogidas de pedidos de clientes en PDV

[!include [banner](includes/banner.md)]

Cuando se crea un [pedido de cliente](customer-orders-overview.md) para la recogida en la tienda, un usuario de la tienda puede usar la aplicación de punto de venta (PDV) para iniciar la recogida del inventario. PDV ejecutará la captura de pago final según sea necesario. También completará el inventario y el registro financiero de las cantidades recogidas.

Si es un usuario de la tienda, puede realizar la recogida mediante la operación **Recuperar pedido** o la operación **Cumplimiento de pedido** en PDV. Para hacer que la operación **Recoger** esté disponible, primero hay que seguir uno de estos pasos:

- Para usar la operación **Recuperar pedido**, busque y seleccione el pedido que se va a recoger.
- Para usar la operación **Cumplimiento de pedido**, busque y seleccione una o varias líneas de pedido.

Si el pedido seleccionado o las líneas de pedido no están configuradas para su recogida en esa tienda concreta, o si ya se ha recogido el pedido por completo, la operación **Recoger** no estará disponible.

![Operación de recogida](media/pickupoperation.png)

En Microsoft Dynamics 365 Commerce, versión 10.0.17 y posteriores, se puede activar la característica **Experiencia de usuario mejorada para el procesamiento de pedidos de recogida en el punto de venta** a través de Administración de características en la sede de Commerce. Si esta característica está desactivada, los usuarios no podrán seleccionar cantidades para recoger. De forma predeterminada, la cantidad total solicitada para la línea es la cantidad que se va a recoger. Esta experiencia puede ser problemática, ya que los usuarios pueden olvidarse de seleccionar algunos artículos para recoger cuando realizan la recogida a través del cumplimiento del pedido.

La característica **Experiencia de usuario mejorada para el procesamiento de pedidos de recogida en el punto de venta** ofrece a los usuarios más control sobre la selección de productos que se va a recoger y la cantidad de esos productos que se va a recoger. Los usuarios no tienen que seleccionar todas las líneas del pedido de ventas en la página de cumplimiento del pedido antes de seleccionar **Recoger**. Se mostrarán todos los artículos que se pueden recoger. Los usuarios pueden especificar varias líneas para recoger incluso si solo se selecciona una línea de producto.

Cuando la característica **Experiencia de usuario mejorada para el procesamiento de pedidos de recogida en el punto de venta** está activada y se selecciona la operación **Recoger**, aparece el cuadro de diálogo **Recoger**. En este cuadro puede seleccionar los artículos y las cantidades que se recogerán. De forma predeterminada, cualquier cantidad pedida que tenga inventario en estado de recogida o empaquetado se considera apta para recogida. De forma predeterminada, esa cantidad se establece como la cantidad de recogida. Puede cambiar la cantidad introducida siempre que esta cantidad no sea 0 (cero) y no exceda de la cantidad total abierta (es decir, no facturada) para la línea seleccionada.

![Cuadro de diálogo Recoger](media/pickupselect.png)

Después de seleccionar las cantidades que se van a recoger y de seleccionar **Recoger**, aparece la página de transacción. Si la característica [pagos de omnicanal](omni-channel-payments.md) está activada y hay registrados pagos con tarjeta de crédito preautorizados, debe aplicar el pago.

En la página de transacción, el sistema calcula los importes adeudados calculando el total adeudado por los artículos para recoger seleccionados y restando a continuación los depósitos aplicados previamente o los pagos autorizados con tarjeta de crédito. Debe procesar el pago para completar la transacción de recogida. Si el [diseño de pantalla](pos-screen-layouts.md) de la página de transacción está configurado de forma que incluya la operación **Concluir transacción** y no se adeuda ningún importe, puede completar la transacción sin seleccionar un método de pago. Si la operación **Concluir transacción** no está disponible, puede seleccionar vínculo **Importe de 0,00 $ adeudado** en el panel **Totales** para concluir la transacción sin tener que seleccionar un método de pago.

![Página de transacción para una transacción de recogida de pedido de cliente](media/pickupcart.png)

## <a name="changing-pickup-lines-or-quantities"></a>Cambio de líneas o cantidades de recogida

Si tiene que cambiar la cantidad de recogida después de haber seleccionado los artículos que se van a recoger, puede seleccionar **Establecer cantidad**. No puede establecer la cantidad de recogida en **0** (cero) ni incrementarla a un valor que exceda de la cantidad no facturada que queda para la línea pedida. Para quitar una línea de recogida del carro de transacción, seleccione **Anular transacción**. La transacción actual se detendrá y se reiniciará el flujo de la operación **Recogida**.

Si la característica **Experiencia de usuario mejorada para el procesamiento de pedidos de recogida en el punto de venta** está activada, las organizaciones pueden agregar al diseño de pantalla de la página de transacción un botón para la operación **Cambiar líneas de recogida**. Después de crear el carro de transacción de recogida en PDV y seleccionar artículos, puede seleccionar **Cambiar líneas de recogida** si desea cambiar los artículos de recogida pero no quiere anular toda la transacción. En el cuadro de diálogo **Cambiar líneas de recogida** que aparece, puede cambiar los artículos y las cantidades de recogida. El carro de transacción se actualiza para reflejar sus cambios.

![Cuadro de diálogo Cambiar elementos de recogida](media/pickupchange.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]