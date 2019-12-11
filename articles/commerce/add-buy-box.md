---
title: Módulo de cuadro de compra
description: En este tema se tratan los módulos de cuadro de compra y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 11/11/2019
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
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e86b1881e6829ccc33f36ada453af20c1815a2fa
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2019
ms.locfileid: "2811150"
---
# <a name="buy-box-module"></a>Módulo de cuadro de compra

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de cuadro de compra y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

El término *cuadro de compra* hace referencia normalmente a una página de detalles de productos que se encuentra “por encima del pliegue” y que hospeda toda la información más importante necesaria para crear una compra del producto. (Un área que está “por encima del pliegue” es visible cuando la página se carga por primera vez, de modo que los usuarios no tengan que desplazarse hacia abajo para verla).

Un módulo de cuadro de compra es el contenedor especial que se usa para hospedar todos los módulos que se muestran en el área del cuadro de compra de una página de detalles de producto.

La dirección URL de una página de detalles de producto incluye el id. de producto. Toda la información que se necesita para representar un módulo de cuadro de compra se deriva de este id. de producto. Si no se proporciona un id. de producto, el módulo de cuadro de compra no se representará correctamente en una página. Por lo tanto, un módulo de cuadro de compra no se puede usar en cualquier página que no tenga contexto de productos (por ejemplo, una página principal o una página de marketing).

## <a name="buy-box-module-properties-and-slots"></a>Franjas y propiedades del módulo de cuadro de compra 

Como contenedor, un módulo de cuadro de compra controla algunas propiedades básicas, como el ancho. El valor del ancho determina si los módulos dentro del contenedor deben ajustarse a ese contenedor o si pueden rellenar la pantalla.

En una página de detalles de productos, un cuadro de compra se divide en dos regiones: una región multimedia a la izquierda y una región de contenido a la derecha. Estas dos regiones se representan por franjas en el módulo de cuadro de compra. Cada franja está preconfigurada para aceptar solo módulos específicos que se admiten por la franja. Por ejemplo, una franja **Medios** solo admite el módulo de galería multimedia.

De forma predeterminada, la relación de anchos de columna para la región multimedia y la región de contenido es 2:1. Sin embargo, los anchos de columna se pueden anular por el tema. Además, en los dispositivos móviles, se apilan las dos regiones, de modo que una región aparece debajo de la otra.

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a>Módulos que se pueden usar en un módulo de cuadro de compra

- **Galería de medios** Este módulo se usa para mostrar imágenes de un producto en una página de detalles de productos. Puede admitir de una a varias Imágenes. También admite imágenes en miniatura. Las imágenes en miniatura se pueden organizar horizontalmente fila (como fila debajo de la imagen) o verticalmente (como columna junto a la imagen). El módulo de galería de medios se puede agregar a la franja **Medios** del módulo del cuadro de compra. Solo admite actualmente imágenes y vídeos.
- **Título del producto**: Este módulo muestra el título del producto en una página de detalles de productos. De manera predeterminada, se usa la etiqueta de encabezado **H1**, pero la etiqueta de encabezado se puede cambiar según sea necesario.
- **Clasificación de producto**: Este módulo muestra calificaciones de estrellas, en función de las clasificaciones de clientes para un producto. El módulo del cuadro de compra recupera las clasificaciones de productos para cada producto desde el servicio de clasificaciones.
- **Precio de producto**: Este módulo muestra el precio del producto. El precio incluye precios y descuentos tachados.
- **Descripción de producto**: Este módulo muestra la descripción del producto.
- **Configuración de producto**: Este módulo muestra el tamaño, el estilo y las dimensiones del producto. Los selectores de dimensión se pueden apilar verticalmente o pueden aparecer uno junto al otro. Cuando hay una variante de producto seleccionada, se actualizan otras propiedades del cuadro de compra (por ejemplo, la descripción del producto y las imágenes) para reflejar la información de la variante.
- **Cantidad de producto**: Este módulo se usa para configurar la cantidad del producto. Un valor limita la cantidad de un producto o una variante que se puede agregar al carro.
- **Agregar al carro**: Este módulo se usa para realizar la acción “agregar al carro”. Solo se puede agregar un producto o una variante al carro. Es decir, no se puede agregar un producto maestro al carro. El módulo tiene una propiedad **Navegar hasta el carro** que el autor del sitio puede establecer. Cuando esta propiedad se establece en **Verdadero**, se lleva al usuario a la página del carro cada vez que se desencadena la acción “agregar al carro”. Cuando se establece en **Falso**, el cliente puede continuar examinando en la página de detalles de productos después de que los artículos se agreguen al carro.
- **Agregar a la lista de deseos**: Este módulo se usa para agregar un artículo a la lista de deseos del cliente. Solo se puede agregar un producto o una variante a una lista de deseos. Además, el cliente debe haber iniciado sesión en el sitio. El módulo incluye lógica de tratamiento de errores para asegurarse de que se cumplen estas condiciones.
- **Buscar en tienda**: Este módulo desencadena el flujo “comprar en línea, recoger en tienda”.
- **Recogida en tienda**: Este módulo muestra una lista de las tiendas cercanas donde un artículo está disponible para su recogida. De forma predeterminada, este módulo muestra las tiendas que se encuentran en un radio de 50 millas de la ubicación del cliente. Sin embargo, el radio de búsqueda se puede personalizar en el módulo. Para cada tienda, se realiza una comprobación de inventario, si está activada la funcionalidad de comprobación de inventario, y se muestra un mensaje de en existencias o sin existencias.
- **Búsqueda de tiendas por Bing Maps** Este módulo se puede usar dentro del módulo de recogida en tienda. Permite la búsqueda de clientes para tiendas introduciendo una ubicación. La interfaz de programación de aplicaciones (API) de geocodificación de Bing Maps se utiliza para convertir la ubicación especificada en una latitud y una longitud. Si se usa este módulo, solo se muestran las tiendas que se encuentran cerca de la ubicación actual del cliente y el cliente no puede buscar una ubicación diferente.
- **Bloque de enriquecimiento de contenido**: Este módulo puede mostrar un mensaje que el autor del sitio o el minorista desea promocionar en el cuadro de compra, como “Para problemas con el pedido, póngase en contacto con 1-800-FABRIKAM “o “Envío gratuito en pedidos superiores a 100 €”. Los mensajes se controlan mediante el sistema de gestión de contenidos (CMS).

## <a name="buy-box-module-settings"></a>Configuración del módulo de cuadro de compra

Los módulos de cuadro de compra tienen tres valores que se pueden configurar:

- **Cantidad máxima**: El número máximo de cada artículo que se puede agregar al carro. Por ejemplo, un minorista puede decidir si solo 10 de cada producto se pueden vender en una única transacción.
- **Comprobación de inventario**: Cuando el valor se establece en **Verdadero**, se agrega un artículo al carro solo después de que el módulo del cuadro de compra se asegure de que está en existencias. Esta comprobación de inventario se realiza tanto para situaciones donde se enviará el artículo como para situaciones en la que se recogerá en la tienda. Si el valor se establece en **Falso**, no se realiza ninguna comprobación de inventario antes de agregar un artículo al carro y se realiza el pedido.
- **Almacenaje de inventario**: El inventario se mantiene en tiempo real y, cuando muchos clientes realizan pedidos, puede ser difícil mantener un recuento de inventario preciso. Por lo tanto, se puede definir un almacenamiento para inventario. Cuando se realiza una comprobación de inventario, si el inventario es inferior a la cantidad de almacenaje, el producto se tratará como sin existencias. Por lo tanto, cuando las ventas se producen rápidamente entre varios canales, de manera que el recuento de inventario no está completamente sincronizado, hay un riesgo menor de que se venda un artículo del que no hay existencias.

## <a name="retail-server-interaction"></a>Interacción con Retail Server

El módulo de cuadro de compra recupera la información de producto mediante las API de Retail Server. El id. del producto de la página de detalles de productos se utiliza para recuperar toda la información.

## <a name="add-a-buy-box-module-to-a-page"></a>Agregar un módulo de cuadro de compra a una página

Para agregar un módulo de cuadro de compra a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Cree un fragmento que se llame **fragmento de cuadro de compra** y agréguele un módulo de cuadro de compra.
1. En la franja **Medios** del módulo del cuadro de compra, agregue un módulo de galería de medios.
1. En el espacio **Contenido** del módulo de cuadro de compra, agregue los siguientes módulos: título del producto, calificación del producto, precio del producto, descripción del producto, configuración del producto, agregar al carro, agregar a la lista de deseos y buscar en tienda. Puede reorganizar los módulos del espacio **Contenido** para lograr el diseño deseado.
1. Seleccione el módulo de buscar en tienda. En el espacio dentro de este módulo, agregue un módulo de recogida en tienda.
1. En el espacio dentro del módulo de recogida en tienda, agregue una búsqueda de tiendas por Bing Maps.
1. Proteja la página y publíquela.
1. Cree una plantilla para una página de detalles de productos y asígnele el nombre **Plantilla de PDP**.
1. Agregue una página predeterminada.
1. En el espacio **Principal** de la página predeterminada, agregue un fragmento de cuadro de compra.
1. Guarde la plantilla, protéjala y publíquela.
1. Use la plantilla que acaba de crear para crear una página que se llame **Página de PDP**.
1. En el espacio **Principal** de la página nueva, agregue un fragmento de cuadro de compra.
1. Guarde la página y obtenga una vista previa de ella. Agregue el parámetro de cadena de consulta **?productid=&lt;id. de producto&gt;** a la dirección URL de la página de vista previa. De esa manera, el contexto del producto se usa para cargar y representar la página de vista previa.
1. Proteja la página y publíquela. Un cuadro de la compra debe aparecer en la página de detalles de productos.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo Contenedor](add-container-module.md)

[Módulo de carro](add-cart-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de confirmación de pedido](order-confirmation-module.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de pie de página](author-footer-module.md)
