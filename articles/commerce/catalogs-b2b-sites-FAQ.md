---
title: P+F de catálogos de Commerce para sitios B2B
description: En este artículo se proporcionan respuestas a las preguntas frecuentes sobre los catálogos Microsoft Dynamics 365 Commerce.
author: ashishmsft
ms.date: 05/18/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: asharchw
ms.search.validFrom: 2022-02-28
ms.openlocfilehash: af69c3d27142a961049470dd1292ffbc3d8387a9
ms.sourcegitcommit: 6616b969afd6beb11a79d8e740560bf00016ea7f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2022
ms.locfileid: "9027377"
---
# <a name="commerce-catalogs-for-b2b-faq"></a>P+F de catálogos de Commerce para sitios B2B

[!include [banner](includes/banner.md)]

En este artículo se proporcionan respuestas a las preguntas frecuentes sobre los Microsoft Dynamics 365 Commerce [catálogos negocio a negocio (B2B)](catalogs-b2b-sites.md).

## <a name="why-cant-i-configure-a-catalog-specific-navigation-hierarchy-or-see-an-option-to-associate-a-customer-hierarchy"></a>¿Por qué no puedo configurar una jerarquía de navegación específica del catálogo o ver una opción para asociar una jerarquía de clientes?

Asegúrese de que la característica **Habilite el uso de múltiples catálogos en canales minoristas** está habilitada en el espacio de trabajo **Gestión de características** en la sede de Commerce. Además, asegúrese de que su entorno utilice la versión 10.0.27 o posterior de Commerce.

## <a name="can-i-view-the-catalog-specific-hierarchy-and-enrich-category-pages-in-commerce-site-builder"></a>¿Puedo ver la jerarquía específica del catálogo y enriquecer las páginas de categorías en el creador de sitios de Commerce?

Sí, los usuarios del creador de sitios de Commerce que tienen acceso a la página **Productos** en el creador de sitios puede seleccionar un catálogo y ver la jerarquía específica del catálogo. Desde la página **Productos**, los usuarios también pueden enriquecer una página de categoría para una categoría específica en el catálogo. Para obtener más información, consulte [Enriquecer una página de aterrizaje de categoría](enrich-category-page.md). Si desea tener un enriquecimiento que sea específico para un catálogo, le recomendamos que tenga una jerarquía de navegación distinta y única para ese catálogo.

## <a name="can-a-b2b-shopper-purchase-from-multiple-catalogs-in-a-single-checkout"></a>¿Puede un comprador B2B comprar de varios catálogos en un solo pago?

Sí, se permiten las compras de varios catálogos en una misma caja. Los compradores B2B pueden usar el indicador de catálogo en la vista del carrito para determinar qué artículos se agregaron de qué catálogos.

## <a name="if-a-b2b-shopper-purchases-the-same-item-from-different-catalogs-what-is-the-expected-behavior"></a>Si un comprador B2B compra el mismo artículo de diferentes catálogos, ¿cuál es el comportamiento esperado?

Aunque un usuario determinado puede tener acceso a varios catálogos en un momento dado, la expectativa es que los productos de esos catálogos se excluyan mutuamente. En otras palabras, lo ideal es que un mismo producto no forme parte de más de un catálogo para un mismo usuario.

Sin embargo, si surge una situación en la que el mismo producto pertenece a varios catálogos, el sistema mantendrá varias líneas de carrito para ese producto. Habrá una línea separada para cada catálogo. El mismo producto de dos catálogos diferentes no se fusionará al finalizar la compra.

## <a name="when-a-b2b-shopper-is-shopping-is-there-any-validation-for-catalog-availability"></a>Cuando un comprador B2B está comprando, ¿hay alguna validación para la disponibilidad del catálogo?

Sí. Un comprador B2B podrá proceder al pago solo si todos los artículos en el carrito son de catálogos válidos. Si algún artículo del carrito pertenece a catálogos vencidos o retirados, se eliminará y se notificará al usuario.

## <a name="during-the-shopping-experience-are-search-and-product-discovery-including-related-and-recommended-product-collections-catalog-specific"></a>Durante la experiencia de compra, ¿la búsqueda y el descubrimiento de productos (incluidas las colecciones de productos recomendados y relacionados) son específicos del catálogo?

Sí. Tan pronto como un usuario selecciona un catálogo específico, todo el viaje de compras se convierte en un catálogo específico. Este viaje incluye experiencias de descubrimiento de productos, como sugerencias de búsqueda, resultados de búsqueda, resultados de categorías, refinadores, precios, atributos y productos recomendados (como productos nuevos, más vendidos, de moda, comprados juntos con frecuencia y productos relacionados).

## <a name="can-a-b2b-shopper-purchase-from-the-default-assortment-catalogid0"></a>¿Puede un comprador B2B comprar del surtido predeterminado (catalogID=0)?

No, un comprador B2B no puede comprar del surtido predeterminado. Ese surtido está destinado únicamente a la navegación anónima. Si a un comprador B2B le faltan asignaciones de catálogo (actualizaciones pendientes de su administración), no podrá ver ningún catálogo entre los que pueda elegir y no se verá ninguna jerarquía de categorías.

## <a name="can-marketing-content-be-curated-for-a-product-that-is-specific-to-a-catalog"></a>¿Se puede seleccionar contenido de marketing para un producto específico de un catálogo?

Actualmente, el enriquecimiento de productos solo se admite en los niveles de sitio y canal. En otras palabras, si se enriquece un producto, se comparte en varios catálogos y la página de detalles del producto (PDP) correspondiente para ese producto se representará de la misma manera en todos los catálogos de un sitio determinado.

## <a name="is-catalog-support-available-for-both-b2b-and-business-to-consumer-b2c-online-channels"></a>¿El soporte de catálogo está disponible para los canales en línea B2B y de empresa a consumidor (B2C)?

Actualmente, los catálogos de Commerce están pensados para funcionar solo con canales B2B.

## <a name="can-we-set-up-catalog-specific-upsellcross-sell-items"></a>¿Podemos configurar artículos de venta adicional/cruzada específicos del catálogo?

Actualmente, solo se admite la funcionalidad de productos relacionados. Sin embargo, las configuraciones de artículos de venta adicional y venta cruzada están disponibles para los centros de llamadas.

Las siguientes funciones también son compatibles solo con los centros de llamadas:

- Códigos fuente de catálogo
- Utilización del identificador de origen para realizar un seguimiento de los costes y las tasas de respuesta
- Secuencias de comandos de pedidos y artículos específicos del catálogo
- Análisis de página de catálogo
- Solicitudes de catálogo
- Multivencimientos.
- Productos gratuitos basados en códigos fuente

## <a name="can-we-use-catalog-source-codes-for-b2b-orders-through-the-e-commerce-portal"></a>¿Podemos usar los códigos fuente del catálogo para pedidos B2B a través del portal de comercio electrónico?

No Los códigos fuente del catálogo solo son compatibles con los canales del centro de llamadas.

## <a name="additional-resources"></a>Recursos adicionales

[Crear catálogos de Commerce para sitios B2B](catalogs-b2b-sites.md)

[Impacto de extensibilidad de los catálogos de Commerce para personalizaciones B2B](catalogs-b2b-sites-dev.md)
