---
title: Información general de las páginas de detalles de producto
description: Este artículo proporciona una visión general de las páginas de detalles de producto (PDP) en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 01/23/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 7b7630a15f98da4a1454f7c9b0d3501d4f035649
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/03/2022
ms.locfileid: "8884294"
---
# <a name="product-details-pages-overview"></a>Información general de las páginas de detalles de producto

[!include [banner](includes/banner.md)]

Este artículo proporciona una visión general de las páginas de detalles de producto (PDP) en Microsoft Dynamics 365 Commerce.

Una PDP proporciona información detallada sobre un producto y permite a los clientes seleccionar opciones de productos como un tamaño, un estilo y un color. Una PDP debe mostrar toda la información de producto que un cliente necesita para tomar una decisión de compra.

En la ilustración siguiente se muestra un ejemplo de una PDP.

![Ejemplo de una página de detalles de productos.](./media/pdp.PNG)

## <a name="header-and-footer-modules"></a>Módulos de encabezado y pie de página

La parte superior de una PDP tiene un encabezado que muestra todas las categorías de producto y otras páginas que el minorista desea que los clientes exploren. La parte inferior de la página tiene un pie de página que contiene vínculos rápidos a diversos artículos que pueden interesar a clientes.

## <a name="buy-box-module"></a>Módulo de cuadro de compra

El módulo más importante en un PDP es el módulo de cuadro de compra, que aparece como el primer elemento en la sección principal de la página. Un módulo de cuadro de compra muestra información importante del producto, como el nombre del producto, la descripción del producto, el precio del producto, las imágenes del producto y las clasificaciones del producto.

El módulo de cuadro de compra permite al cliente seleccionar opciones de productos (por ejemplo, un tamaño, un estilo y un color) y agregar el producto al carro. También permite al cliente comprar el producto en línea y recogerlo en una tienda. El módulo de compra en línea y recogida en tienda usa la integración con las interfaces de programación de aplicaciones (API) de Bing Maps para encontrar tiendas cercanas o tiendas en otra ubicación que el cliente especifique.

Un módulo de cuadro de compra requiere un id. de producto. Este id. se deriva del contexto de la página. Si se agrega un módulo de cuadro de compra a una página en la que el contexto de la página no incluye un id. de producto, no representará la información correctamente.

## <a name="product-specifications-module"></a>Módulo de especificaciones del producto

El módulo de especificaciones del producto se puede utilizar para mostrar detalles adicionales sobre el producto. Estos detalles se toman de atributos del producto en Commerce. El módulo de especificaciones del producto muestra todos los atributos donde la propiedad **visible** se establece en **verdadero**. Requiere un id. de producto para recuperar los atributos del producto.

## <a name="recommendations-module"></a>Módulo de recomendaciones

El módulo de recomendaciones es un módulo importante en una PDP. Mientras los clientes exploran productos, se le deben presentar más opciones de productos, de manera que puedan encontrar el producto correcto y realizar una compra. Las recomendaciones ayudan a los clientes a detectar con facilidad contenido relacionado y a continuar comprando.

Hay diferentes tipos de listas de recomendaciones disponibles:

- El lista **A la gente también le gustó** se basa en el aprendizaje automático. Usa el historial de transacciones de otros clientes para proporcionar recomendaciones. Esta lista se genera con el servicio de recomendaciones y se parece a las listas “Los clientes que compraron el producto, compraron…”. Se requiere un id. de producto para generar esta lista.
- Se puede generar una lista **Relacionado** para un producto en Commerce. Por ejemplo, para un bolso de viaje de cuero marrón, se pueden configurar para la lista relacionada más bolsos que sean de cuero o estén diseñados para viaje. En Commerce se pueden configurar otros tipos de listas relacionadas, como **Accesorios** y **Más como esto**. Se requiere un id. de producto para generar esta lista. Por lo tanto, si se ha agregado a una página principal, donde el contexto de la página no incluye un id. de producto, la lista estará vacía.
- En las PDF se pueden usar listas de recomendaciones generadas de manera algorítmica, como **Tendencias**, **Más vendidos** y **Nuevos**. Aunque es posible que estas listas no estén directamente relacionadas con el producto en la PDP, son otra manera de ayudar a los clientes a encontrar productos que puedan interesarles. Estos tipos de listas no requieren un id. de producto. Son listas genéricas que se generan en función de patrones de compra en todo el sitio.
- Las listas editoriales son listas mantenidas manualmente. Por ejemplo, un minorista puede decidir mantener manualmente listas de productos que desea mostrar.

## <a name="ratings-and-reviews-modules"></a>Módulos de clasificaciones y opiniones

Se pueden usar tres módulos para mostrar y agregar opiniones:

- **Revisiones**: este módulo muestra clasificaciones y revisiones que han proporcionado otros clientes. Los clientes pueden ordenar y filtrar las reseñas. Este módulo también permite que los clientes puedan indicar que les gusta o no las reseñas e informar de problemas.
- **Escribir opinión**: este módulo permite a los clientes escribir sus propias opiniones de un producto.
- **Histograma de clasificaciones**: este módulo incluye un histograma que muestra la tendencia de las clasificaciones de un producto.

Para obtener más información, consulte [Visión general de clasificaciones y revisiones](ratings-reviews-overview.md).

## <a name="marketing-modules"></a>Módulos de marketing

Si el contenido de marketing es exclusivo de un producto específico, cualquier módulo de marketing puede agregarse a la PDP. Puede agregar módulos de marketing a una PDP “enriqueciendo” la página. Para más detalles, consulte [Enriquecer una página de producto](enrich-product-page.md).

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la página principal](quick-tour-home-page.md)

[Visión general de las páginas del carro y de la finalización de la compra](quick-tour-cart-checkout.md)

[Visión general de las páginas de la gestión de cuentas](quick-tour-account-management.md)

[Enriquecer una página de detalles de producto](enrich-product-page.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
