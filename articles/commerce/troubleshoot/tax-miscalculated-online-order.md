---
title: Los impuestos sobre los pedidos en línea se calculan incorrectamente
description: Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando los impuestos sobre los pedidos en línea se calculan incorrectamente o cuando el grupo de impuestos en la línea de ventas no está configurado correctamente.
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
ms.openlocfilehash: f7cef533d76bdddfbad2e8c5f84f81ef62bccc38
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021112"
---
# <a name="taxes-on-online-orders-are-incorrectly-calculated"></a>Los impuestos sobre los pedidos en línea se calculan incorrectamente

[!include [banner](../../includes/banner.md)]

Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando los impuestos sobre los pedidos en línea se calculan incorrectamente o cuando el grupo de impuestos en la línea de ventas no está configurado correctamente.

## <a name="description"></a>Descripción

Cuando se realiza un pedido de comercio electrónico, los impuestos se calculan incorrectamente o el grupo de impuestos en la línea de ventas está configurado incorrectamente.

## <a name="resolution"></a>Resolución

### <a name="configure-the-sales-tax-for-a-retail-store-in-commerce-headquarters"></a>Configurar el impuesto para una tienda minorista en la sede de Commerce

Para configurar el impuesto para una tienda minorista en la sede de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Canales \> Todas las tiendas**.
1. Seleccione la tienda para la que desea configurar el impuesto.
1. En la ficha desplegable **General**, en la sección **Impuesto**, configure la información del impuesto para la tienda.

> [!NOTE]
> Para la recolección de productos en una tienda, el grupo de impuestos proviene de la tienda seleccionada para la recogida. Para obtener más información, consulte [Definir otras opciones tributarias para tiendas](/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).

### <a name="configure-the-sales-tax-for-a-customers-address-in-commerce-headquarters"></a>Configurar el impuesto para una dirección de cliente en la sede de Commerce

Para configurar el impuesto para una dirección de cliente en la sede de Commerce, siga estos pasos.

1. Vaya a **Clientes \> Clientes \> Todos los clientes**.
1. Seleccione el cliente para el que se va a configurar el impuesto.
1. En la ficha desplegable **Direcciones**, seleccione la dirección para la que desea configurar los impuestos, seleccione **Más opciones** y luego seleccione **Avanzado**.
1. En la ficha desplegable **General**, seleccione el **Grupo de impuestos**.
1. En el campo **Impuesto**, seleccione el valor adecuado.

> [!NOTE]
> Para envíos que implican impuestos en la dirección del cliente, la dirección de entrega de la línea determina el grupo de impuestos para la línea. Si el cliente realiza un envío a una dirección existente que tiene un grupo de impuestos que ya está configurado, se utilizará el grupo de impuestos existente. De forma predeterminada, las direcciones no tienen un grupo de impuestos al crearse.

### <a name="configure-general-sales-tax-groups-in-commerce-headquarters"></a>Configurar grupos generales de impuestos en la sede de Commerce

Para configurar grupos de impuestos generales en la sede de Commerce, siga estos pasos.

1. Vaya a **Impuestos \> Impuestos indirectos \> Impuestos \> Grupos de impuestos**.
1. En la zona de navegación de la izquierda, seleccione el grupo de impuestos a configurar.
1. En la ficha desplegable **Impuesto basado en el destino minorista**, configure los impuestos para el grupo de impuestos.

> [!NOTE]
> Para los envíos que no implican impuestos en la dirección del cliente, la dirección de entrega de la línea y los impuestos basados en el destino que están configurados para el grupo de impuestos determinan el grupo de impuestos. Para más información, vea [Configurar impuestos para tiendas en línea según el destino](/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).

## <a name="additional-resources"></a>Recursos adicionales

[Configurar los impuestos para pedidos en línea](../sales-tax-config.md)