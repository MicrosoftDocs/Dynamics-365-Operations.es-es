---
title: Módulo de cuadro de compra
description: En este tema se tratan los módulos de cuadro de compra y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/13/2020
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
ms.openlocfilehash: 35b7027e0f0b680dd82ebfcea754fef1617c0163
ms.sourcegitcommit: ac966ea3a6c557fb5f9634b187b0e788d3e82d4d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/14/2020
ms.locfileid: "3261407"
---
# <a name="buy-box-module"></a>Módulo de cuadro de compra


[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de cuadro de compra y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

El término *cuadro de compra* hace referencia normalmente a una página de detalles de productos que se encuentra “por encima del pliegue” y que hospeda toda la información más importante necesaria para crear una compra del producto. (Un área que está “por encima del pliegue” es visible cuando la página se carga por primera vez, de modo que los usuarios no tengan que desplazarse hacia abajo para verla).

Un módulo de cuadro de compra es el contenedor especial que se usa para hospedar todos los módulos que se muestran en el área del cuadro de compra de una página de detalles de producto.

La dirección URL de una página de detalles de producto incluye el id. de producto. Toda la información que se necesita para representar un módulo de cuadro de compra se deriva de este id. de producto. Si no se proporciona un id. de producto, el módulo de cuadro de compra no se representará correctamente en una página. Por lo tanto, un módulo de cuadro de compra solo se puede usar en páginas que tienen contexto de producto. Para usarlo en una página que no tiene contexto de producto (por ejemplo, una página de inicio o una página de marketing), debe realizar personalizaciones adicionales.

## <a name="buy-box-module-properties-and-slots"></a>Franjas y propiedades del módulo de cuadro de compra 

En una página de detalles de productos, un cuadro de compra se divide en dos regiones: una región multimedia a la izquierda y una región de contenido a la derecha. De manera predeterminada, la proporción del ancho de columna de la región multimedia con respecto al ancho de columna de la región de contenido es 2:1. En los dispositivos móviles, se apilan las dos regiones, de modo que una región aparece debajo de la otra. Los temas se pueden usar para personalizar los anchos de columna y la clasificación de pilas.

Un módulo de caja de compra representa el título, la descripción, el precio y las calificaciones de un producto. También permite a los clientes seleccionar variantes de productos que tienen atributos de producto distintos, como tamaño, estilo y color. Cuando hay una variante de producto seleccionada, se actualizan otras propiedades del cuadro de compra (por ejemplo, la descripción del producto y las imágenes) para reflejar la información de la variante. 

Se proporciona un selector de cantidad, para que los clientes puedan especificar la cantidad de artículos a comprar. La cantidad máxima que se puede comprar se puede establecer en la configuración del sitio.

Desde el cuadro de compra, los clientes también pueden realizar acciones como agregar un producto al carro, agregar un producto a su lista de deseos y seleccionar una ubicación de recogida. Estas acciones se pueden realizar en un producto o una variante de producto. Para agregar un producto a una lista de deseos, el cliente debe iniciar sesión.

Los temas se pueden usar para eliminar o cambiar el orden de las propiedades del producto de la caja de compra y los controles de acción. 

## <a name="module-properties"></a>Propiedades del módulo

- **Etiqueta de encabezado**: esta propiedad define la etiqueta de encabezado para el título del producto. Si el cuadro de compra está en la parte superior de la página, esta propiedad debe establecerse en **h1** para cumplir los estándares de accesibilidad. 

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a>Módulos que se pueden usar en un módulo de cuadro de compra

- **Galería de medios** Este módulo se usa para mostrar imágenes de un producto en una página de detalles de productos. Puede admitir de una a varias Imágenes. También admite imágenes en miniatura. Las imágenes en miniatura se pueden organizar horizontalmente fila (como fila debajo de la imagen) o verticalmente (como columna junto a la imagen). El módulo de galería de medios se puede agregar a la franja **Medios** del módulo del cuadro de compra. Actualmente solo admite imágenes y vídeos. 
- **Selector de tienda**: este módulo muestra una lista de las tiendas cercanas en las que un artículo está disponible para su recogida. Permite a los usuarios especificar una ubicación para encontrar tiendas cercanas. Para obtener más información sobre este módulo, vea [Módulo selector de tienda](store-selector.md).

## <a name="buy-box-module-settings"></a>Configuración del módulo de cuadro de compra

Los módulos de cuadro de compra tienen tres opciones de configuración opciones que se pueden establecer en **Valores de configuración de sitio \> Extensiones**:

- **Cantidad máxima**: esta propiedad se usa para especificar el número máximo de cada artículo que se puede agregar al carro. Por ejemplo, un minorista puede decidir si solo 10 de cada producto se pueden vender en una única transacción.
- **Comprobación de inventario**: Cuando el valor se establece en **Verdadero**, se agrega un artículo al carro solo después de que el módulo del cuadro de compra se asegure de que está en existencias. Esta comprobación de inventario se realiza para situaciones donde se enviará el artículo y para situaciones en la que se recogerá en la tienda. Si el valor se establece en **Falso**, no se realiza ninguna comprobación de inventario antes de agregar un artículo al carro y se realiza el pedido. Para obtener información sobre cómo configurar las opciones de inventario en la oficina administrativa, vea [Calcular la disponibilidad de inventario para canales minoristas](calculated-inventory-retail-channels.md).

- **Almacenaje de inventario**: esta propiedad se usa para especificar un número de almacenaje para el inventario. El inventario se mantiene en tiempo real y, cuando muchos clientes realizan pedidos, puede ser difícil mantener un recuento de inventario preciso. Cuando se realiza una comprobación de inventario, si el inventario es inferior a la cantidad de almacenaje, el producto se tratará como sin existencias. Por lo tanto, cuando las ventas se producen rápidamente entre varios canales, y el recuento de inventario no está completamente sincronizado, hay un riesgo menor de que se venda un artículo del que no hay existencias.

## <a name="commerce-scale-unit-interaction"></a>Interacción con Commerce Scale Unit

El módulo de cuadro de compra recupera la información de producto mediante las API de Commerce Scale Unit. El id. del producto de la página de detalles de productos se utiliza para recuperar toda la información.

## <a name="add-a-buy-box-module-to-a-page"></a>Agregar un módulo de cuadro de compra a una página

Para agregar un módulo de cuadro de compra a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Cree un fragmento que se llame **fragmento de cuadro de compra** y agréguele un módulo de cuadro de compra.
1. En la franja **Medios** del módulo del cuadro de compra, agregue un módulo de galería de medios.
1. En la franja **Selector de tienda** del módulo de caja de compra, agregue un módulo de selector de tienda.
1. Proteja la página y publíquela.
1. Cree una plantilla para una página de detalles de productos y asígnele el nombre **Plantilla de PDP**.
1. Agregue una página predeterminada.
1. En el espacio **Principal** de la página predeterminada, agregue un fragmento de cuadro de compra.
1. Guarde la plantilla, termine de editarla y publíquela.
1. Use la plantilla que acaba de crear para crear una página que se llame **Página de PDP**.
1. En el espacio **Principal** de la página nueva, agregue un fragmento de cuadro de compra.
1. Guarde la página y obtenga una vista previa de ella. Agregue el parámetro de cadena de consulta **?productid=&lt;id. de producto&gt;** a la dirección URL de la página de vista previa. De esa manera, el contexto del producto se usa para cargar y representar la página de vista previa.
1. Guarde la página, termine de editarla y publíquela. Un cuadro de la compra debe aparecer en la página de detalles de productos.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo de selector de tienda](store-selector.md)

[Módulo Contenedor](add-container-module.md)

[Módulo de carro](add-cart-module.md)

[Módulo de icono de carrito](cart-icon-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de confirmación de pedido](order-confirmation-module.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de pie de página](author-footer-module.md)

[Calcular la disponibilidad de inventario para canales comerciales](calculated-inventory-retail-channels.md)
