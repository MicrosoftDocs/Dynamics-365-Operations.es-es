---
title: Módulo de cuadro de compra
description: En este tema se tratan los módulos de cuadro de compra y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 08/31/2020
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
ms.openlocfilehash: 6556ee8acf1e24a9f6ceddb622960cb3ac891852
ms.sourcegitcommit: 420b9e538f706178f8e1f2786e02f4f400bf2336
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/02/2020
ms.locfileid: "3761306"
---
# <a name="buy-box-module"></a>Módulo de cuadro de compra

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

En este tema se tratan los módulos de cuadro de compra y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

El término *cuadro de compra* hace referencia normalmente a una página de detalles de productos que se encuentra “por encima del pliegue” y que hospeda toda la información más importante necesaria para crear una compra del producto. (Un área que está “por encima del pliegue” es visible cuando la página se carga por primera vez, de modo que los usuarios no tengan que desplazarse hacia abajo para verla).

Un módulo de cuadro de compra es el contenedor especial que se usa para hospedar todos los módulos que se muestran en el área del cuadro de compra de una página de detalles de producto.

La dirección URL de una página de detalles de producto incluye el id. de producto. Toda la información que se necesita para representar un módulo de cuadro de compra se deriva de este id. de producto. Si no se proporciona un id. de producto, el módulo de cuadro de compra no se representará correctamente en una página. Por lo tanto, un módulo de cuadro de compra solo se puede usar en páginas que tienen contexto de producto. Para usarlo en una página que no tiene contexto de producto (por ejemplo, una página de inicio o una página de marketing), debe realizar personalizaciones adicionales.

La siguiente imagen muestra un ejemplo de un módulo de cuadro de compra en una página de detalles del producto.

![Ejemplo de un módulo de cuadro de compra](./media/ecommerce-pdp-buybox.PNG)

## <a name="buy-box-module-properties-and-slots"></a>Franjas y propiedades del módulo de cuadro de compra 

En una página de detalles de productos, un cuadro de compra se divide en dos regiones: una región multimedia a la izquierda y una región de contenido a la derecha. De manera predeterminada, la proporción del ancho de columna de la región multimedia con respecto al ancho de columna de la región de contenido es 2:1. En los dispositivos móviles, se apilan las dos regiones, de modo que una región aparece debajo de la otra. Los temas se pueden usar para personalizar los anchos de columna y la clasificación de pilas.

Un módulo de caja de compra representa el título, la descripción, el precio y las calificaciones de un producto. También permite a los clientes seleccionar variantes de productos que tienen atributos de producto distintos, como tamaño, estilo y color. Cuando hay una variante de producto seleccionada, se actualizan otras propiedades del cuadro de compra (por ejemplo, la descripción del producto y las imágenes) para reflejar la información de la variante. 

Se proporciona un selector de cantidad, para que los clientes puedan especificar la cantidad de artículos a comprar. La cantidad máxima que se puede comprar se puede establecer en la configuración del sitio.

Desde el cuadro de compra, los clientes también pueden realizar acciones como agregar un producto al carro, agregar un producto a su lista de deseos y seleccionar una ubicación de recogida. Estas acciones se pueden realizar en un producto o una variante de producto. Para agregar un producto a una lista de deseos, el cliente debe iniciar sesión.

Los temas se pueden usar para eliminar o cambiar el orden de las propiedades del producto de la caja de compra y los controles de acción. 

## <a name="module-properties"></a>Propiedades del módulo

- **Etiqueta de encabezado**: esta propiedad define la etiqueta de encabezado para el título del producto. Si el cuadro de compra está en la parte superior de la página, esta propiedad debe establecerse en **h1** para cumplir los estándares de accesibilidad. 

- **Habilitar recomendaciones de "comprar looks similares"**: esta propiedad permite que el cuadro de compra muestre enlaces a productos que se parecen al artículo que se ve actualmente. Esta función está disponible en Commerce, versión 10.0.13 y posterior.

## <a name="modules-that-can-be-used-in-a-buy-box-module"></a>Módulos que se pueden usar en un módulo de cuadro de compra

- **Galería de medios** Este módulo se usa para mostrar imágenes de un producto en una página de detalles de productos. Para obtener más información sobre este módulo, consulte [Módulo de galería de medios](media-gallery-module.md).
- **Selector de tienda**: este módulo muestra una lista de las tiendas cercanas en las que un artículo está disponible para su recogida. Permite a los usuarios especificar una ubicación para encontrar tiendas cercanas. Para obtener más información sobre este módulo, consulte [Módulo selector de tienda](store-selector.md).
- **Compartir en redes sociales**: este módulo se puede agregar al cuadro de compra para permitir a los usuarios compartir información del producto en las redes sociales. Para más información, consulte [Módulo Compartir en rees sociales](social-share-module.md).

## <a name="buy-box-module-settings"></a>Configuración del módulo de cuadro de compra

Las siguientes opciones de cuadro de compra pueden configurarse en **Configuración de sitio \> Extensiones**:

- **Límite de cantidad de línea de carro**: esta propiedad se usa para especificar el número máximo de cada artículo que se puede agregar al carro. Por ejemplo, un minorista puede decidir si solo 10 de cada producto se pueden vender en una única transacción.
- **Inventario**: para obtener información sobre cómo aplicar la configuración de inventario, consulte [Aplicar configuración de inventario](inventory-settings.md).
- **Añadir al carro**: esta propiedad se utiliza para especificar el comportamiento después de agregar un artículo al carro. Los valores posibles son **Navegar al carro**, **No navegar al carro** y **Mostrar notificaciones**. Cuando el valor se establece en **Navegar al carro**, se envía a los usuarios a la página del carro después de agregar un artículo. Cuando el valor se establece en **No navegar al carro**, se envía a los usuarios a la página del carro después de agregar un artículo. Cuando el valor se establece en **Mostrar notificaciones**, los usuarios reciben una notificación de confirmación y pueden continuar navegando en la página de detalles del producto. 

    La siguiente imagen muestra un ejemplo de una notificación de confirmación de "agregado al carro" en el sitio de Fabrikam.

    ![Ejemplo de un módulo de notificación](./media/ecommerce-addtocart-notifications.PNG)

## <a name="commerce-scale-unit-interaction"></a>Interacción con Commerce Scale Unit

El módulo de cuadro de compra recupera la información de producto mediante las interfaces de programación de aplicaciones (API) de Commerce Scale Unit. El id. del producto de la página de detalles de productos se utiliza para recuperar toda la información.

## <a name="add-a-buy-box-module-to-a-page"></a>Agregar un módulo de cuadro de compra a una página

Para agregar un módulo de cuadro de compra a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Vaya a **Fragmentos** y seleccione **Nuevo** para crear un nuevo fragmento.
1. En el cuadro de diálogo **Nuevo fragmento**, seleccione el módulo **Cuadro de compra**.
1. En **Nombre del fragmento**, especifique el nombre **Fragmento de cuadro de compra** y luego seleccione **Aceptar**.
1. En el espacio **Galería de medios** del módulo de cuadro de compra, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Galería de medios** y, a continuación, **Aceptar**.
1. En el espacio **Selector de tienda** del módulo de cuadro de compra, seleccione los puntos suspensivos (**...**) y luego seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Selector de tienda** y elija **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger el fragmento y luego seleccione **Publicar** para publicarlo.
1. Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.
1. En el cuadro de diálogo **Nueva plantilla**, en **Nombre de plantilla**, introduzca **Plantilla PDP** y luego seleccione **Aceptar**.
1. En el espacio **Cuerpo**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Página predeterminada** y, a continuación, **Aceptar**.
1. En el espacio **Principal** de la página predeterminada, seleccione los puntos suspensivos (**...**) y, a continuación, **Agregar fragmento**.
1. En el cuadro de diálogo **Seleccionar fragmento**, seleccione el fragmento **Fragmento de cuadro de compra** creado anteriormente y, a continuación, seleccione **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.
1. Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.
1. En el cuadro de diálogo **Elegir una plantilla**, seleccione la plantilla **Modelo PDP**. En **Nombre de página**, introduzca **Página PDP** y después seleccione **Aceptar**.
1. En el espacio **Principal** de la nueva página, seleccione los puntos suspensivos (**...**) y, a continuación, **Agregar fragmento**.
1. En el cuadro de diálogo **Seleccionar fragmento**, seleccione el fragmento **Fragmento de cuadro de compra** creado anteriormente y, a continuación, seleccione **Aceptar**.
1. Guarde la página y obtenga una vista previa de ella. Agregue el parámetro de cadena de consulta **?productid=&lt;id. de producto&gt;** a la dirección URL de la página de vista previa. De esa manera, el contexto del producto se usa para cargar y representar la página de vista previa.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla. Un cuadro de la compra debe aparecer en la página de detalles de productos.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general del kit de inicio](starter-kit-overview.md)

[Módulo de selector de tienda](store-selector.md)

[Módulo de galería de medios](media-gallery-module.md)

[Módulo de contenedor](add-container-module.md)

[Módulo de carro](add-cart-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de confirmación de pedido](order-confirmation-module.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de pie de página](author-footer-module.md)

[Módulo Compartir en redes sociales](social-share-module.md)

[Calcular la disponibilidad de inventario para canales comerciales](calculated-inventory-retail-channels.md)
