---
title: Configurar los impuestos para pedidos en línea
description: Este tema proporciona una descripción general de la selección de grupos de impuestos para diferentes tipos de pedidos en línea en Dynamics 365 Commerce.
author: gvrmohanreddy
manager: AnnBe
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: gmohanv
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.16
ms.openlocfilehash: 56621bb9658b71551c7312aa47812903914bc888
ms.sourcegitcommit: da17648c296b22d517eadb2f71c7803672e5648d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/19/2021
ms.locfileid: "5031798"
---
# <a name="configure-sales-tax-for-online-orders"></a>Configurar los impuestos para pedidos en línea

[!include [banner](includes/banner.md)]

Este tema proporciona una descripción general de la selección de grupos de impuestos para diferentes tipos de pedidos en línea. 

Es posible que su canal de comercio electrónico desee admitir opciones como la entrega o la recogida para pedidos en línea. La aplicabilidad de los impuestos se basa en la opción seleccionada por sus usuarios en línea. Cuando un cliente del sitio elige comprar un artículo en línea y lo envía a una dirección, el impuesto se determina según la configuración del grupo de impuestos de la dirección de envío del cliente. Cuando un cliente opta por recoger un artículo comprado en una tienda, el impuesto se determina según la configuración del grupo de impuestos de la tienda de recogida. 

## <a name="orders-shipped-to-a-customer-address"></a>Pedidos enviados a la dirección de un cliente 

En general, los impuestos para los pedidos en línea que se envían a las direcciones de los clientes quedan definidos según el destino. Cada grupo de impuestos sobre tiene una configuración del impuesto basada en el destino comercial donde su empresa puede definir detalles de destino como provincia, región, estado, localidad y ciudad en una forma jerárquica. Cuando se realiza un pedido en línea, el motor de impuestos de Commerce utiliza la dirección de entrega de cada artículo de línea del pedido y busca grupos de impuestos que coincidan con los criterios de impuestos basados en el destino. Por ejemplo, para un pedido en línea con una dirección de entrega de artículos de línea para San Francisco, California, el motor de impuestos buscará el grupo de impuestos y el código de impuestos para California y luego calculará los impuestos para cada artículo de línea en consecuencia.  

## <a name="customer-based-tax-groups"></a>Grupos de impuestos basados en el cliente

En la sede central de Commerce, hay dos lugares donde se configuran los grupos de impuestos de clientes:

- **Perfil del cliente**
- **Dirección de envío del cliente**

### <a name="if-a-customers-profile-has-a-tax-group-configured"></a>Si el perfil de un cliente tiene un grupo fiscal configurado

El registro del perfil de un cliente en la sede central puede tener configurado un grupo de impuestos; sin embargo, para los pedidos en línea, el motor de impuestos no utilizará el grupo de impuestos configurado en el perfil de un cliente. 

### <a name="if-a-customers-shipping-address-has-a-tax-group-configured"></a>Si la dirección de envío de un cliente tiene un grupo fiscal configurado

Si el registro de la dirección de envío de un cliente tiene un grupo de impuestos configurado y un pedido en línea (o artículo de línea) se envía a la dirección de envío del cliente, el motor de impuestos utilizará el grupo de impuestos configurado en el registro de la dirección del cliente para los cálculos de impuestos.

#### <a name="configure-a-tax-group-for-a-customers-shipping-address-record"></a>Configurar un grupo fiscal para el registro de la dirección de envío de un cliente

Para configurar un grupo de impuestos para el registro de la dirección de envío de un cliente en la sede central de Commerce, siga estos pasos.

1. Vaya a **Todos los clientes** y luego seleccione el cliente deseado. 
1. En la ficha desplegable **Direcciones**, seleccione la dirección deseada y luego seleccione **Más opciones \> Avanzado**. 
1. En la pestaña **General** en la página **Administrar direcciones**, configure el valor del impuesto según sea necesario.

> [!NOTE]
> El grupo de impuestos se define utilizando la dirección de entrega de la línea de pedido y los impuestos basados en el destino se configuran en el propio grupo fiscal. Para más información, vea [Configurar impuestos para tiendas en línea según el destino](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination).

## <a name="order-pickup-in-store"></a>Recogida de pedidos en tienda

Para las líneas de pedido con recogida en la tienda o recogida en un punto de entrega especificado, se aplicará el grupo fiscal de la tienda de recogida seleccionada. Para obtener detalles sobre cómo configurar el grupo fiscal para una tienda determinada, consulte [Establecer otras opciones de impuestos para tiendas](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).

> [!NOTE]
> Cuando se recoge una línea de pedido en una tienda, el motor de impuestos ignorará la configuración de impuestos de la dirección de un cliente (si está configurada) y se aplicará la configuración de impuestos de la tienda de recogida. 

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de impuestos](https://docs.microsoft.com/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json) 

[Métodos de cálculo de impuestos en el campo Origen](https://docs.microsoft.com/dynamics365/finance/general-ledger/sales-tax-calculation-methods-origin-field?toc=/dynamics365/commerce/toc.json) 

[Asignación de impuestos y anulaciones](https://docs.microsoft.com/dynamics365/supply-chain/procurement/tasks/sales-tax-assignment-overrides?toc=/dynamics365/commerce/toc.json) 

[Importe completo y opciones de cálculo de Intervalo para los códigos de impuestos](https://docs.microsoft.com/dynamics365/finance/general-ledger/whole-amount-interval-options-sales-tax-codes?toc=/dynamics365/commerce/toc.json) 

[Cálculo de exención de impuestos](tax-exempt-price-inclusive.md) 



[!INCLUDE[footer-include](../includes/footer-banner.md)]