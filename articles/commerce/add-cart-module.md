---
title: Módulo de carro
description: En este tema se tratan los módulos de carro y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 1c910f08e5999ec586b5cb656d5769e9d4abd069
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/01/2019
ms.locfileid: "2696770"
---
# <a name="cart-module"></a>Módulo de carro

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de carro y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Un módulo de carro es el contenedor que se usa para hospedar todos los módulos que se necesitan para mostrar artículos que se encuentran en el carro. Por ejemplo, incluye todos los artículos que se han agregado al carro, al resumen de pedidos y a los códigos promocionales.

El módulo del carro representa datos a partir del id. del carro. El id, del carro es una cookie de explorador que está disponible a través del sitio.

## <a name="cart-module-properties-and-slots"></a>Franjas y propiedades del módulo del carro

Como contenedor, un módulo de carro controla algunas propiedades básicas, como el encabezado y el ancho. El encabezado normalmente es texto como **Cesta de la compra**, **Su carro** o **Artículos del carro**. El valor del ancho determina si los módulos dentro del contenedor deben ajustarse a ese contenedor o si pueden rellenar la pantalla.

La página del carro se divide en varias regiones: artículos de línea de carro, resumen de pedidos y finalización de compra, y la funcionalidad “buscar en tienda”. Cada región se asigna a una franja del módulo del carro y cada franja acepta un conjunto predefinido de módulos.

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Módulos que se pueden usar en un módulo de carro

- **Artículos de línea de carro**: Este módulo muestra un resumen de cada artículo que se ha agregado al carro. La información incluye el título del producto, las dimensiones seleccionadas, el precio, la cantidad y los descuentos. Este módulo también admite acciones como “quitar del carro“ y “agregar a la lista de deseos”. Para cada artículo de línea, hay una opción para enviar el artículo o recogerlo en la tienda. Esta opción se debe configurar por separado en el módulo de recogida en tienda.
- **Resumen del pedido**: Este módulo muestra un resumen del pedido. La información incluye el subtotal, el envío, los impuestos y los ahorros. Se puede configurar un encabezado para este módulo.
- **Código de promoción**: Este módulo le permite al cliente canjear códigos de promoción. Un código promocional se puede aplicar o quitar.
- **Finalizar compra**: Este módulo inicia la acción de finalización de compra y redirige al usuario a la página de finalización de compra. Se deben configurar tres vínculos para este módulo:

    - **Finalizar compra**: Este vínculo fuerza a los clientes a iniciar sesión si no lo han hecho todavía.
    - **Compra como invitado**: Este vínculo permite a clientes anónimos realizar pedidos. Se muestra si los clientes no han iniciado sesión.
    - **Volver a la compra**: Este vínculo permite a los clientes ir a la página principal o a cualquier otra página, para continuar haciendo compras.

- **Bloque de enriquecimiento de contenido**: Este módulo admite mensajería personalizada en el módulo del carro. Los mensajes se controlan mediante el sistema de gestión de contenidos (CMS). Se puede agregar cualquier mensaje, como “Para problemas con el pedido, póngase en contacto con 1-800-Fabrikam”.
- **Recogida en tienda**: Este módulo muestra una lista de las tiendas cercanas donde un artículo está disponible para su recogida. De forma predeterminada, este módulo muestra las tiendas que se encuentran en un radio de 50 millas de la ubicación del cliente. Sin embargo, el radio de búsqueda se puede personalizar en el módulo. Para cada tienda, se realiza una comprobación de inventario, si está activada la funcionalidad de comprobación de inventario, y se muestra un mensaje de en existencias o sin existencias.
- **Búsqueda de tiendas por Bing Maps** Este módulo se puede usar dentro del módulo de recogida en tienda. Permite la búsqueda de clientes para tiendas introduciendo una ubicación. La interfaz de programación de aplicaciones (API) de geocodificación de Bing Maps se utiliza para convertir la ubicación que el cliente ha introducido en una latitud y una longitud. Si no se usa este módulo, solo se muestran las tiendas que se encuentran cerca de la ubicación actual del cliente y el cliente no puede buscar una ubicación diferente.

## <a name="cart-module-settings"></a>Configuración de módulo de carro

Los módulos de carro tienen tres valores que se pueden configurar:

- **Cantidad máxima**: El número máximo de cada artículo que se puede agregar al carro. Por ejemplo, un minorista puede decidir si solo 10 de cada producto se pueden vender en una única transacción.
- **Comprobación de inventario**: Cuando el valor se establece en **Verdadero**, se agrega un artículo al carro solo después de que el módulo del cuadro de compra se asegure de que está en existencias. Esta comprobación de inventario se realiza tanto para situaciones donde se enviará el artículo como para situaciones en la que se recogerá en la tienda. Si el valor se establece en **Falso**, no se realiza ninguna comprobación de inventario antes de agregar un artículo al carro y se realiza el pedido.
- **Almacenaje de inventario**: El inventario se mantiene en tiempo real y, cuando muchos clientes realizan pedidos, puede ser difícil mantener un recuento de inventario preciso. Por lo tanto, se puede definir un almacenamiento para inventario. Cuando se realiza una comprobación de inventario, si el inventario es inferior a la cantidad de almacenaje, el producto se tratará como sin existencias. Por lo tanto, cuando las ventas se producen rápidamente entre varios canales, de manera que el recuento de inventario no está completamente sincronizado, hay un riesgo menor de que se venda un artículo del que no hay existencias.

## <a name="retail-server-interaction"></a>Interacción con Retail Server

El módulo del carro recupera la información de producto mediante las API de Retail Server. El id. del carro de la cookie del explorador se utiliza para recuperar toda la información de producto de Retail Server.

## <a name="add-a-cart-module-to-a-page"></a>Agregar un módulo de carro a una página

Para agregar un módulo de carro a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Cree un fragmento que se llame **fragmento de carro** y agréguele un módulo de carro.
1. En la franja **Artículos de línea de carro** del módulo del carro, agregue un módulo de artículos de línea de carro.
1. En la franja **Resumen del pedido**, agregue un módulo de resumen del pedido.
1. En la franja **Código de promoción**, agregue un módulo de código de promoción.
1. En la franja **Finalizar compra**, agregue un módulo de finalización de compra.
1. En la franja **Buscar en tienda**, agregue un módulo en recogida en tienda.
1. En el módulo de recogida en tienda, seleccione la franja **Búsqueda de tiendas** y agregue una búsqueda de tiendas por Bing Maps.
1. Proteja el fragmento y publíquelo.
1. Cree una plantilla que con el nombre **plantilla de carro** y agréguele el fragmento del carro que acaba de crear.
1. Guarde la plantilla, protéjala y publíquela.
1. Cree una página que use la nueva plantilla.
1. Guarde la página y obtenga una vista previa de ella.
1. Proteja la página y publíquela.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo Contenedor](add-container-module.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de confirmación de pedido](order-confirmation-module.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de pie de página](author-footer-module.md)
