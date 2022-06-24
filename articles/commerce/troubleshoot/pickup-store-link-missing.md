---
title: La opción Recoger esto no aparece en el carrito o en las páginas de detalles del producto
description: Este artículo proporciona una guía de solución de problemas que puede ayudar cuando la opción de recogida en tienda no aparece en la página del carrito o en las páginas de detalles del producto.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 88367e13b4d079edb0816e301901828b65c437ae
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8900317"
---
# <a name="pick-this-up-option-doesnt-appear-on-cart-or-product-details-pages"></a>La opción "Recoger esto" no aparece en el carrito o en las páginas de detalles del producto

[!include [banner](../../includes/banner.md)]

Este artículo proporciona una guía de solución de problemas que puede ayudar cuando la opción de recogida en tienda no aparece en la página del carrito o en las páginas de detalles del producto.

## <a name="description"></a>Descripción

El botón **Recoger esto** no aparece en el carrito o en las páginas de detalles del producto.

La siguiente ilustración muestra un ejemplo de una página que incluye botón **Recoger esto**.

![Botón Recoger esto.](media/pickup-button-missing.jpg)

## <a name="resolution"></a>Resolución

### <a name="enable-the-bopis-extension-in-commerce-site-builder"></a>Habilitar la extensión BOPIS en el creador de sitios de Commerce

Para habilitar la extensión "comprar en línea, recoger en tienda" (BOPIS) en el creador de sitios de Commerce, siga estos pasos.

1. Seleccione su sitio.
1. Seleccione **Configuración del sitio** y después seleccione **Extensiones**.
1. Asegúrese de que la opción **Desactivar BOPIS** está desactivada.

### <a name="configure-modes-of-delivery-in-commerce-headquarters"></a>Configurar modos de entrega en la sede de Commerce

Para configurar los modos de entrega en la sede de Commerce, siga estos pasos.

1. Vaya a **Adquisiciones y abastecimiento \> Configuración \> Modos de entrega**.
1. Asegúrese de que se ha creado el modo de entrega **Recogida por parte del cliente** y se le han asignado productos y direcciones.
1. Vaya a **Retail y Commerce \> Configuración de sede \> Parámetros**.
1. En el panel de navegación izquierdo, seleccione **Pedidos de cliente**.
1. Asegúrese de que **Modo de recogida de entrega** está configurado correctamente.

### <a name="configure-customer-orders-payments"></a>Configurar pagos de pedidos de clientes

Para configurar pagos de pedidos de clientes en la sede de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de sede \> Parámetros**.
1. En el panel de navegación izquierdo, seleccione **Pedidos de cliente**.
1. En la ficha desplegable **Pagos**, asegúrese de que los campos **Condiciones de pago** y **Forma de pago** están configurados correctamente.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar BOPIS](../cpe-bopis.md)

[Habilitar varios modos de recogida de la entrega para pedidos de clientes](../multiple-pickup-modes.md)

[Pagos de pedido de Commerce en el omnicanal](../dev-itpro/commerce-payments.md)

[Módulo de selector de tienda](../store-selector.md)
