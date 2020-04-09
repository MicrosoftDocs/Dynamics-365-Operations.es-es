---
title: Módulo selector de tienda
description: En este tema se trata el modulo selector de tienda y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 03/19/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8efc2345ded52bfaee2d400815795906f326f4fd
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/21/2020
ms.locfileid: "3157349"
---
# <a name="store-selector-module"></a>Módulo selector de tienda

[!include [banner](includes/banner.md)]

En este tema se trata el modulo selector de tienda y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Se utiliza un módulo selector de tienda para el escenario de cliente "comprar en línea, recoger en la tienda" (BOPIS). Muestra una lista de tiendas donde un producto está disponible para recoger, así como el horario de la tienda y el inventario de productos para cada tienda.

El módulo selector de tiendas requiere el contexto de un producto y una ubicación de búsqueda para encontrar tiendas. En ausencia de una ubicación de búsqueda, el valor predeterminado es la ubicación del navegador del cliente, siempre que el cliente dé su consentimiento. El módulo tiene un cuadro de entrada que permite al cliente ingresar una ubicación (código postal, o ciudad y estado) para encontrar tiendas cercanas.

El módulo selector de tienda se integra con la interfaz de programación de aplicaciones (API) de geocodificación de Bing Maps para convertir la ubicación que el cliente ha introducido en una latitud y una longitud. Se requiere una clave de la API de Bing Maps, y debe agregarse a la página de parámetros compartidos de Commerce en Dynamics 365 Commerce.

El módulo selector de tiendas se puede agregar a un módulo de caja de compra en la página de detalles del producto (PDP) para mostrar las tiendas donde hay un producto disponible para su recogida. También se puede agregar a un módulo de carrito. Cuando se agrega a un módulo de carrito, el módulo selector de tienda muestra opciones de recolección para cada artículo de línea de carrito. Además, con la codificación personalizada, este módulo se puede agregar a otras páginas o módulos a través de extensiones y personalizaciones.

Para que funcione el escenario BOPIS, los productos deben configurarse con el modo de entrega "recogida del cliente". De lo contrario, el módulo no se mostrará en las páginas respectivas. Para obtener detalles sobre cómo configurar el modo de entrega, consulte [Configurar modos de entrega](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

La siguiente imagen muestra un ejemplo de un módulo selector de tienda utilizado en un PDP.

![Ejemplo de un módulo selector de tienda](./media/BOPIS.PNG)

## <a name="store-selector-module-usage-in-e-commerce"></a>Uso del módulo selector de tienda en comercio electrónico

- Un módulo selector de tiendas se puede usar en la página de detalles del producto (PDP) para mostrar las tiendas cercanas donde hay un producto disponible para su recogida.
- Un módulo selector de tiendas se puede usar en la página de carrito para mostrar las tiendas cercanas donde hay un producto en el carrito disponible para su recogida.

## <a name="store-selector-module-properties"></a>Propiedades del módulo selector de tienda

| Nombre de la propiedad             | Valor                 | Descripción |
|---------------------------|-----------------------|-------------|
| Radio de búsqueda | Número | Define el radio de búsqueda de tiendas, en millas. Si no se especifica ningún valor, se utiliza el radio de búsqueda predeterminado: 50 millas.|
|Términos de servicio | Dirección URL    |  La URL de los términos de servicio que se requiere para el servicio Bing Maps. |

## <a name="add-a-store-selector-module-to-a-page"></a>Agregar un módulo de selector de tienda a una página

Un módulo selector de tienda necesita el contexto de un producto, por lo que solo se puede usar dentro de los módulos de compra y carrito. Los módulos de selector de tienda no funcionan fuera de estos módulos.

- Para obtener información sobre cómo agregar un módulo selector de tienda a un módulo de caja de compra, vea [Módulo de caja de compra](add-buy-box.md). 
- Para obtener información sobre cómo agregar un módulo selector de tienda a un módulo de carrito, vea [Módulo de carrito](add-cart-module.md)

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulo de carro](add-cart-module.md)

[Visita rápida de PDP](quick-tour-pdp.md)

[Paseo rápido por el carro y la finalización de la compra](quick-tour-cart-checkout.md)

[Configurar modos de entrega](https://docs.microsoft.com/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)
