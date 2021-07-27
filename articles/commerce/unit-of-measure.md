---
title: Aplicar la configuración de unidades de medida
description: Este tema cubre las configuraciones de unidades de medida y describe cómo aplicarlas en Microsoft Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 04/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 076d4a68362dbf11c5fcf223a836f075d07e27a3
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6350337"
---
# <a name="apply-unit-of-measure-settings"></a>Aplicar la configuración de unidades de medida

[!include [banner](includes/banner.md)]

Este tema cubre las configuraciones de unidades de medida y describe cómo aplicarlas en Microsoft Microsoft Dynamics 365 Commerce.

Un producto se puede vender en diferentes unidades, como "cada uno", "par" y "docena". En la sede de Commerce, la unidad de medida de venta por unidad puede definirse para un producto y mostrarse en un sitio de comercio electrónico. Por ejemplo, si un minorista vende un producto tanto individualmente como en docenas, las unidades de medida disponibles se pueden mostrar junto con otra información del producto.

En el ejemplo de la siguiente ilustración, una unidad de medida de venta por **ea** (cada uno) se ha configurado para un producto en la sede de Commerce.

![Ejemplo de un producto configurado con una unidad de medida en la sede de Commerce.](./media/Productunit-headquarters.PNG)

> [!NOTE]
> El soporte para aplicar y mostrar la unidad de medida está disponible a partir de la versión 10.0.19 de Commerce.

## <a name="unit-of-measure-settings"></a>Configuración de unidades de medida

La configuración de visualización de unidades de medida se define en el creador de sitios de Commerce, en **Configuración del sitio \> Extensiones \> Mostrar unidad de medida para los productos**. Hay tres configuraciones compatibles:

- **No mostrar**: cuando se selecciona esta configuración, el sitio de comercio electrónico no mostrará la unidad de medida del producto. Este comportamiento es el predeterminado.
- **Mostrar en la experiencia de compra de productos**: cuando se selecciona esta configuración, la unidad de medida se muestra en las páginas de detalles del producto, el carrito, la finalización de compra, el historial de pedidos y detalles de pedidos.
- **Mostrar en la experiencia de navegación y compra de productos**: cuando se selecciona esta configuración, la unidad de medida se muestra en las páginas de experiencia de compra de productos y también durante la experiencia de navegación de productos. Como parte de este comportamiento, las unidades de medida se muestran en los resultados de búsqueda y en los módulos de recopilación de productos.

> [!IMPORTANT]
> La configuración de visualización de unidades de medida está disponible a partir de la versión 10.0.19 de Commerce. Si está actualizando desde una versión anterior de Commerce, debe actualizar manualmente el archivo appsettings.json. Para obtener instrucciones, consulte [Actualizaciones del SDK y la biblioteca de módulos](e-commerce-extensibility/sdk-updates.md#update-the-appsettingsjson-file).

## <a name="modules-that-use-unit-of-measure-settings"></a>Módulos que usan configuraciones de unidades de medida

Los módulos que utilizan la configuración de unidades de medida incluyen el cuadro de compra, la lista de deseos, el carrito, el icono del carrito, el contenedor de resultados de búsqueda, la colección de productos, la finalización de compra y los módulos de detalles del pedido.

En el ejemplo de la siguiente ilustración, una página de detalles del producto (PDP) muestra la unidad de medida (**ea**) para un producto.

![Ejemplo de un PDP que muestra la unidad de medida.](./media/Productunit-PDP.png)

En el ejemplo de la siguiente ilustración, un módulo de colección de productos muestra la unidad de medida (**ea**) para un producto.

![Ejemplo de un módulo de colección de productos que muestra la unidad de medida.](./media/Productunit-productcollection.png)

## <a name="additional-resources"></a>Recursos adicionales

[Descripción general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de carro](add-cart-module.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulos y páginas de gestión de cuentas](account-management.md)

[Actualizaciones de SDK y bibliotecas de módulos](e-commerce-extensibility/sdk-updates.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
