---
title: Configurar los impuestos para pedidos en línea
description: Este artículo proporciona una descripción general de la selección de grupos de impuestos para diferentes tipos de pedidos en línea en Dynamics 365 Commerce.
author: gvrmohanreddy
ms.date: 04/02/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: gmohanv
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.16
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.openlocfilehash: 5936d16039927812dabf99bd770afcc0e827f1ca
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9276726"
---
# <a name="configure-sales-tax-for-online-orders"></a>Configurar los impuestos para pedidos en línea

[!include [banner](includes/banner.md)]

Este artículo proporciona una descripción general de la selección de grupos de impuestos sobre las ventas para diferentes tipos de pedidos en línea utilizando configuraciones de impuestos basadas en el destino o en la cuenta del cliente. 

Es posible que desee que su canal de comercio electrónico admita opciones como la entrega o la recogida para pedidos en línea. La aplicabilidad de los impuestos se basa en la opción seleccionada por sus clientes en línea. 

## <a name="destination-based-taxes-for-online-orders"></a>Impuestos basados en el destino para pedidos en línea

En general, los impuestos para los pedidos en línea que se envían a las direcciones de los clientes quedan definidos según el destino. Cada grupo de impuestos sobre tiene una configuración del impuesto basada en el destino comercial donde su empresa puede definir detalles de destino, como país o región, estado, localidad y ciudad en una forma jerárquica.

### <a name="orders-delivered-to-customer-address"></a>Pedidos entregados a la dirección de un cliente

Cuando se realiza un pedido en línea, el motor de impuestos de Commerce utiliza la dirección de entrega de cada artículo de línea del pedido y busca grupos de impuestos que coincidan con los criterios de impuestos basados en el destino. Por ejemplo, para un pedido en línea con una dirección de entrega de artículos de línea para San Francisco, California, el motor de impuestos buscará el grupo de impuestos y el código de impuestos para California y luego calculará los impuestos para cada artículo de línea en consecuencia.

### <a name="order-pick-up-in-store"></a>Recogida de pedidos en tienda

Para las líneas de pedido con recogida en la tienda o recogida en un punto de entrega especificado, se aplicará el grupo fiscal de la tienda de recogida seleccionada. Para obtener detalles sobre cómo configurar impuestos de ventas para una tienda determinada, consulte [Establecer otras opciones de impuestos para tiendas](/dynamicsax-2012/appuser-itpro/set-other-tax-options-for-stores).

## <a name="customer-account-based-taxes-for-online-orders"></a>Impuestos basados en cuenta de cliente para pedidos en línea

Puede haber un escenario empresarial en el que desee configurar un grupo de impuestos sobre las ventas en una cuenta de cliente específica en Commerce Headquarters. Hay dos lugares en la sede donde puede configurar el impuesto sobre las ventas en una cuenta de cliente. Para acceder a ellos, primero deberá acceder a una página de detalles del cliente yendo a **Retail y Commerce \> Clientes \> Todos los clientes** y luego seleccionando un cliente.

Los dos lugares donde puede configurar el impuesto sobre las ventas para una cuenta de cliente son:

- **Grupo de impuestos sobre las ventas** en la ficha desplegable **Factura y entrega** de la página de detalles del cliente. 
- **Impuesto de venta** en la ficha desplegable **General** de la página **Administrar direcciones**. Para llegar desde la página de detalles del cliente, seleccione una dirección específica en la ficha desplegable **Direcciones** y luego seleccione **Avanzado**.

> [!TIP]
> Para los pedidos de clientes en línea, si solo desea aplicar los impuestos basados en el destino y evitar los impuestos basados en la cuenta del cliente, asegúrese de que el campo **Grupo de impuestos sobre las ventas** está vacío en la ficha desplegable **Factura y entrega** de la página de detalles del cliente. Para asegurarse de que los nuevos clientes que se registran mediante el canal en línea no hereden la configuración del grupo de impuestos sobre las ventas de la configuración predeterminada del grupo de clientes o clientes, asegúrese de que el campo **Grupo de impuestos sobre las ventas** también está vacío para la configuración predeterminada del cliente del canal en línea y la configuración del grupo de clientes (**Retail y Commerce \> Clientes \> Grupos de clientes**).

## <a name="determine-destination-based-tax-or-customer-account-based-tax-applicability"></a>Determinar la aplicabilidad de impuestos basados en el destino o impuestos basados en la cuenta del cliente 

La siguiente tabla explica si los impuestos basados en el destino o los impuestos basados en la cuenta del cliente se aplican a los pedidos en línea. 

| Tipo de cliente | Dirección de envío                   | Cliente > Factura y entrega> ¿Grupo de impuestos sobre las ventas? | ¿Dirección en la cuenta del cliente en la sede? | Dirección del cliente > Avanzado > General> ¿Grupo de impuestos sobre las ventas?                                              | Grupo de impuestos de ventas aplicado      |
|---------------|------------------------------------|-----------------------------------------------------|-----------------------------------|--------------------------------------------------------------------------------------------------------|------------------------------|
| Huésped         | Manhattan, Nueva York                      | No (en blanco)                                                | No (en blanco)                              | No (en blanco)                                                                                                   | NY (impuestos basados en el destino) |
| Sesión iniciada     | Austin, TX                          | No (en blanco)                                             | Sí                               | None<br/><br/>Nueva dirección agregada a través del canal en línea.                                                            | TX (impuestos basados en el destino) |
| Sesión iniciada     | San Francisco, CA (recoger en la tienda) | Sí (NY)                                            | No aplicable                              | No aplicable                                                                                                    | CA (impuestos basados en el destino) |
| Sesión iniciada     | Houston, TX                         | Sí (NY)                                            | Sí                               | Sí (NY)<br/><br/>Nueva dirección agregada a través del canal en línea y el grupo de impuestos sobre las ventas heredado de la cuenta del cliente. | NY (impuestos basados en la cuenta del cliente)  |
| Sesión iniciada     | Austin, TX                          | Sí (NY)                                            | Sí                               | Sí (NY)<br/><br/>Nueva dirección agregada a través del canal en línea y el grupo de impuestos sobre las ventas heredado de la cuenta del cliente. | NY (impuestos basados en la cuenta del cliente)  |
| Sesión iniciada     | Sarasota, FL                       | Sí (NY)                                            | Sí                               | Sí (WA)<br/><br/>Establecido manualmente en WA.                                                                          | WA (impuestos basados en la cuenta del cliente)  |
| Sesión iniciada     | Sarasota, FL                       | No (en blanco)                                                | Sí                               | Sí (WA)<br/><br/>Establecido manualmente en WA.                                                                          | WA (impuestos basados en la cuenta del cliente)  |

## <a name="additional-resources"></a>Recursos adicionales

[Configurar impuestos para tiendas en línea según el destino](/dynamicsax-2012/appuser-itpro/set-up-taxes-for-online-stores-based-on-destination)

[Información general de impuestos](../finance/general-ledger/indirect-taxes-overview.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Métodos de cálculo de impuestos en el campo Origen](../finance/general-ledger/sales-tax-calculation-methods-origin-field.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Asignación de impuestos y anulaciones](../supply-chain/procurement/tasks/sales-tax-assignment-overrides.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Importe completo y opciones de cálculo de Intervalo para los códigos de impuestos](../finance/general-ledger/whole-amount-interval-options-sales-tax-codes.md?toc=%2fdynamics365%2fcommerce%2ftoc.json) 

[Cálculo de exención de impuestos](tax-exempt-price-inclusive.md) 



[!INCLUDE[footer-include](../includes/footer-banner.md)]
