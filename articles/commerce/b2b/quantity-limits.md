---
title: Establecer límites de cantidad de productos para sitios de comercio electrónico B2B
description: Este artículo describe cómo configurar límites de cantidad de productos para sitios de comercio electrónico de empresa a empresa (B2B).
author: josaw1
ms.date: 01/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.14
ms.search.industry: retail
ms.search.form: RetailOperations
ms.openlocfilehash: 76a7ad2c3095d1402ff214dbfee26b344b492681
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275688"
---
# <a name="set-product-quantity-limits-for-b2b-e-commerce-sites"></a>Establecer límites de cantidad de productos para sitios de comercio electrónico B2B

[!include [banner](../../includes/banner.md)]

Este artículo describe cómo configurar límites de cantidad de productos para sitios de comercio electrónico de empresa a empresa (B2B).

La mayoría de los productos tienen una unidad de medida que define su agrupación. La agrupación afecta a cómo se pueden vender los productos. Algunos productos pueden tener una agrupación adicional de cantidades. Esta agrupación determina si los productos se pueden vender como unidades individuales o múltiples, y si hay un límite mínimo o máximo de cantidad de pedido que se debe seguir.

La característica de limitación de la cantidad garantiza que las cantidades mínima, máxima, múltiple y estándar configuradas en Microsoft Dynamics 365 Commerce (en la configuración de pedidos predeterminada o en la configuración del sitio del generador de sitios de Commerce) se aplican a los pedidos de clientes que se realizan en un sitio de comercio electrónico. Actualmente, los límites de cantidad de productos no se admiten en los puntos de venta (PDV) y los centros de llamadas.

Muchos minoristas ofrecen la opción de pedidos de cliente (también llamados pedidos especiales) para satisfacer distintos requisitos de producto y de cumplimiento. Aquí hay algunas situaciones habituales:

- Un cliente quiere que los productos de variantes específicas se vendan en múltiplos de unos pocos.
- Un cliente desea elegir productos de una tienda o de una ubicación diferente de la tienda o de la ubicación donde el cliente compró los productos. Sin embargo, los estándares de empaquetado para las tiendas difieren de los estándares de empaquetado para la distribución de ventas en línea.
- Un cliente desea comprar un producto de edición limitada que tiene un límite máximo de cantidad de artículos que se pueden comprar.

## <a name="turn-on-the-default-order-settings-feature-in-commerce-headquarters"></a>Activar la característica de configuración de pedidos predeterminada en la sede central de Commerce

Para poder establecer límites de cantidad de productos, la característica de configuración de pedidos predeterminada debe estar activada en la sede central de Commerce.

Para activar la característica de configuración de pedidos predeterminada, siga estos pasos.

1. Vaya a **Administración del sistema \> Espacios de trabajo \> Administración de características**.
1. Busque y seleccione la característica **Admitir la configuración de pedido del sitio y predeterminada en el pedido del cliente**.
1. En la parte inferior del panel derecho, seleccione **Habilitar ahora**. 

## <a name="define-quantity-settings"></a>Definir la configuración de cantidad 

Puede definir la configuración de cantidad en la página **Configuración predeterminada de pedido**.

Para definir la configuración de cantidad, siga estos pasos: 

1. Vaya a Producto **Retail y Commerce \> Productos y categorías \> Productos liberados por categoría**.
1. Seleccione un producto liberado.
1. En el panel de acciones, en la pestaña **Administrar inventario**, en el grupo **Configuración de pedido**, seleccione **Configuración de pedido predeterminada**. 
1. En la página **Configuración de pedido predeterminada**, en la ficha desplegable **Pedido de ventas**, en la sección **Cantidad de ventas**, establezca las cantidades de ventas del producto:

    - **Múltiplos**: la cantidad en cuyos múltiplos se puede comprar el producto.
    - **Cantidad mínima de pedido**: el número mínimo de productos que se deben comprar.
    - **Cantidad máxima de pedido**: el número máximo de productos que se pueden comprar.
    - **Cantidad de pedido estándar**: la cantidad predeterminada que se introduce automáticamente al seleccionar el producto.

## <a name="turn-on-the-b2b-order-quantity-limits-feature-in-commerce-site-builder"></a>Activar la característica de límites de cantidad de pedidos B2B en el generador de sitios de Commerce

Para activar la característica de límites de cantidad de pedidos B2B en el generador de sitios de Commerce, siga estos pasos.

1. Vaya a **Configuración del sitio \> Extensiones**.
1. En **Habilitar límites de cantidad de pedidos**, seleccione **Habilitado para clientes de B2B** en el menú desplegable. 

> [!NOTE] 
> La configuración actualizada del generador de sitios solo se aplicará después de que se haya actualizado el archivo app.settings.json. Para obtener más información, consulte [Actualizaciones del SDK y la biblioteca de módulos](../e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="additional-resources"></a>Recursos adicionales

[Configurar un sitio de comercio electrónico B2B](set-up-b2b-site.md)

[Administrar socios comerciales B2B utilizando jerarquías de clientes](partners-customer-hierarchies.md)

[Gestionar usuarios de partner comerciales en sitios de comercio electrónico B2B](manage-b2b-users.md)

[Configurar el método de pago de la cuenta del cliente para sitios de comercio electrónico B2B](payment-method.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
