---
title: Ocultar información de desglose de impuestos en resúmenes de pedidos
description: Este artículo describe cómo ocultar la información de desglose de impuestos en los resúmenes de pedidos en las páginas del carrito, pago, confirmación del pedido y detalles del pedido en Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 05/17/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2022-03-28
ms.openlocfilehash: 669534a6611860ac73439460afedce341310cc7d
ms.sourcegitcommit: 6616b969afd6beb11a79d8e740560bf00016ea7f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2022
ms.locfileid: "9027344"
---
# <a name="hide-tax-breakup-information-in-order-summaries"></a>Ocultar información de desglose de impuestos en resúmenes de pedidos

[!include [banner](includes/banner.md)]

Este artículo describe cómo ocultar la información de desglose de impuestos en los resúmenes de pedidos en las páginas del carrito, pago, confirmación del pedido y detalles del pedido en Microsoft Dynamics 365 Commerce.

Por defecto, Dynamics 365 Commerce muestra la información sobre el desglose de los impuestos en los resúmenes de los pedidos en las páginas del carrito, la caja, la confirmación del pedido y los detalles del pedido. A partir del lanzamiento de la versión 10.0.27 de Commerce, el generador de sitios de Commerce incluye una opción que le permite ocultar la información de desglose de impuestos en los resúmenes de pedidos.

La siguiente ilustración muestra un ejemplo de dos resúmenes de pedidos. El primero muestra la información de desglose de impuestos y el segundo la oculta.

![Ejemplos de carritos donde se muestra y oculta información de desglose de impuestos.](media/prices-include-sales-tax-e-Commerce.png)

> [!NOTE]
> - La opción para ocultar la información de desglose de impuestos en los resúmenes de pedidos está disponible solo cuando la opción **Los precios incluyen el impuesto a las ventas** para el canal de comercio electrónico se establece en **Sí** en la sede de Commerce, en **Retail y Commerce \> Canales \> Historias \> Todas las tiendas**. 
> - Por defecto, la opción **Mostrar desglose de impuestos en el resumen del pedido** está habilitada en el generador de sitios.

## <a name="hide-tax-breakup-information-in-order-summaries"></a>Ocultar información de desglose de impuestos en resúmenes de pedidos

Para ocultar información de desglose de impuestos en resúmenes de pedidos, siga estos pasos.

1. En el generador de sitios de Commerce, vaya al sitio que desea actualizar.
1. Ir **Configuraciones del sitio \> Extensiones**.
1. Desactivar la casilla **Mostrar desglose de impuestos en el resumen del pedido**.

Para mostrar información de desglose de impuestos en resúmenes de pedidos, seleccione la casilla **Mostrar desglose de impuestos en el resumen del pedido**.  

La siguiente ilustración muestra la casilla **Mostrar desglose de impuestos en el resumen del pedido** resaltada y seleccionada en el generador de sitios.

![Mostrar desglose de impuestos en el resumen del pedido está habilitada en el generador de sitios.](media/prices-include-sales-tax-e-Commerce-site-settings.png)

> [!NOTE]
> Si tiene módulos de resumen de pedidos personalizados y no desea heredar la funcionalidad "Ocultar la información de desglose de impuestos en los resúmenes de pedidos" en Commerce, versión 10.0.27 o posterior, consulte [El subtotal del resumen del pedido no incluye los impuestos sobre los cargos cuando se utilizan módulos personalizados de resumen del pedido](troubleshoot/summary-taxes-custom-modules-10.0.27.md#resolution).

## <a name="additional-resources"></a>Recursos adicionales

[Información general de impuestos](/finance/general-ledger/indirect-taxes-overview)

[Configurar los impuestos para pedidos en línea](sales-tax-config.md)

[Solución de problemas: los impuestos sobre los pedidos en línea se calculan incorrectamente](troubleshoot/tax-miscalculated-online-order.md)
