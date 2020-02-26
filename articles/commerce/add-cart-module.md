---
title: Módulo de carro
description: En este tema se tratan los módulos de carro y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.openlocfilehash: f6dd8fb56f7342eb9c877eda503a92f4a31e5863
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025445"
---
# <a name="cart-module"></a>Módulo de carro


[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de carro y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Se utiliza un módulo de carro para mostrar los artículos que se han agregado al carro antes de que el cliente finalice la compra. Por ejemplo, incluye todos los artículos que se han agregado al carro y un resumen del pedido. También permite al cliente aplicar o quitar códigos promocionales.

El módulo de carro permite finalizar la compra como usuario que ha iniciado sesión o como usuario invitado. También admite un vínculo **Volver a la compra**. Puede configurar la ruta para este vínculo en **Valores de configuración de sitio \> Extensiones \> Rutas**.

El módulo del carro representa datos a partir del id. del carro. El id, del carro es una cookie de explorador que está disponible a través del sitio.

## <a name="cart-module-properties-and-slots"></a>Franjas y propiedades del módulo del carro

El módulo de carro tiene una propiedad **Encabezado** que se puede establecer en valores como **Cesta de la compra** y **Artículos del carro**. 

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Módulos que se pueden usar en un módulo de carro

- **Bloque de texto**: este módulo admite mensajería personalizada en el módulo de carro. Los mensajes se controlan mediante el sistema de gestión de contenidos (CMS). Se puede agregar cualquier mensaje, como “Si hubiera algún problema con el pedido, póngase en contacto con 1-800-Fabrikam”.
- **Selector de tienda**: este módulo muestra una lista de las tiendas cercanas en las que un artículo está disponible para su recogida. Permite a los usuarios especificar una ubicación para encontrar tiendas cercanas. El módulo selector de tienda se integra con la interfaz de programación de aplicaciones (API) de geocodificación de Bing Maps para convertir la ubicación que el cliente ha introducido en una latitud y una longitud. Se requiere una clave de la API de Bing Maps, y debe agregarse a la página de parámetros compartidos de Retail en Dynamics 365 Retail. Este módulo admite dos propiedades, **Radio de búsqueda** y **Vínculo a los términos de servicio**. La propiedad **Radio de búsqueda** define el radio de búsqueda de las tiendas, en millas. Si no se especifica ningún valor, se utiliza el radio de búsqueda predeterminado: 50 millas. Si se utiliza Bings Maps o cualquier servicio externo, se puede usar la propiedad **Vínculo a los términos de servicio** para proporcionar un enlace a los términos del servicio. Se requiere un vínculo a los términos de servicio para el servicio Bing Maps. 

## <a name="cart-module-settings"></a>Configuración de módulo de carro

Los módulos de carro tienen las siguientes opciones de configuración que se pueden establecer en **Valores de configuración de sitio \> Extensiones**:

- **Cantidad máxima**: esta propiedad se usa para especificar el número máximo de cada artículo que se puede agregar al carro. Por ejemplo, un minorista puede decidir si solo 10 de cada producto se pueden vender en una única transacción.
- **Comprobación de inventario**: Cuando el valor se establece en **Verdadero**, se agrega un artículo al carro solo después de que el módulo del cuadro de compra se asegure de que está en existencias. Esta comprobación de inventario se realiza tanto para situaciones donde se enviará el artículo como para situaciones en la que se recogerá en la tienda. Si el valor se establece en **Falso**, no se realiza ninguna comprobación de inventario antes de agregar un artículo al carro y se realiza el pedido.
- **Almacenaje de inventario**: esta propiedad se usa para especificar un número de almacenaje para el inventario. El inventario se mantiene en tiempo real y, cuando muchos clientes realizan pedidos, puede ser difícil mantener un recuento de inventario preciso. Cuando se realiza una comprobación de inventario, si el inventario es inferior a la cantidad de almacenaje, el producto se tratará como sin existencias. Por lo tanto, cuando las ventas se producen rápidamente entre varios canales, y el recuento de inventario no está completamente sincronizado, hay un riesgo menor de que se venda un artículo del que no hay existencias.
- **Volver a la compra**: esta propiedad se utiliza para especificar la ruta para el vínculo **Volver a la compra**. Esta ruta se puede configurar a nivel de sitio. Esta configuración permite a los minoristas llevar al cliente a la página de inicio o a cualquier otra página del sitio.

## <a name="commerce-scale-unit-interaction"></a>Interacción con Commerce Scale Unit

El módulo del carro recupera la información de producto mediante las API de Commerce Scale Unit. El id. del carro de la cookie del explorador se utiliza para recuperar toda la información de producto de Commerce Scale Unit.

## <a name="add-a-cart-module-to-a-page"></a>Agregar un módulo de carro a una página

Para agregar un módulo de carro a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Cree un fragmento que se llame **Fragmento de carro** y agréguele un módulo de carro.
1. Agregue un encabezado al módulo de carro.
1. Agregue un módulo selector de tienda al módulo del carro.
1. Guarde el fragmento, termine de editarlo y publíquelo.
1. Cree una plantilla con el nombre **Plantilla de carro** y agréguele el fragmento del carro que acaba de crear.
1. Guarde la plantilla, termine de editarla y publíquela.
1. Cree una página que use la nueva plantilla.
1. Guarde la página y obtenga una vista previa de ella.
1. Termine de editar la página y publíquela.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo Contenedor](add-container-module.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de confirmación de pedido](order-confirmation-module.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de pie de página](author-footer-module.md)
