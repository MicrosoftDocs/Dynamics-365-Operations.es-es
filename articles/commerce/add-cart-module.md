---
title: Módulo de carro
description: En este tema se tratan los módulos de carro y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 05/28/2020
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
ms.openlocfilehash: f21268ed4cffed1d5c789f722796cdf05e965819
ms.sourcegitcommit: 4a981ee4be6d7e6c0e55541535d386bce2565cba
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/27/2020
ms.locfileid: "3621045"
---
# <a name="cart-module"></a>Módulo de carro

[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de carro y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Un módulo de carro muestra los artículos que se han agregado al carro antes de que el cliente finalice la compra. El módulo también muestra un resumen del pedido y permite al cliente aplicar o quitar códigos promocionales.

El módulo de carro permite finalizar la compra como usuario que ha iniciado sesión o como usuario invitado. También admite un vínculo **Volver a la compra**. Puede configurar la ruta para este vínculo en **Valores de configuración de sitio \> Extensiones \> Rutas**.

El módulo de carrito procesa los datos en función de la ID del carrito, que es una cookie del navegador disponible en todo el sitio. 

La siguiente imagen muestra un ejemplo de una página de carro en el sitio Fabrikam.

![Ejemplo de un módulo de carro](./media/cart2.PNG)

## <a name="cart-module-properties-and-slots"></a>Franjas y propiedades del módulo del carro

El módulo de carro tiene una propiedad **Encabezado** que se puede establecer en valores como **Cesta de la compra** y **Artículos del carro**. 

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Módulos que se pueden usar en un módulo de carro

- **Bloque de texto**: este módulo admite mensajería personalizada en el módulo de carro. Los mensajes se controlan mediante el sistema de gestión de contenidos (CMS). Se puede agregar cualquier mensaje, como “Si hubiera algún problema con el pedido, póngase en contacto con 1-800-Fabrikam”.
- **Selector de tienda**: este módulo muestra una lista de las tiendas cercanas en las que un artículo está disponible para su recogida. Permite a los usuarios especificar una ubicación para encontrar tiendas cercanas. Para obtener más información sobre este módulo, consulte [Módulo selector de tienda](store-selector.md).

## <a name="module-properties"></a>Propiedades del módulo

Las siguientes opciones de cmódulo de carro pueden configurarse en **Configuración de sitio \> Extensiones**:

- **Cantidad máxima**: esta propiedad se usa para especificar el número máximo de cada artículo que se puede agregar al carro. Por ejemplo, un minorista puede decidir si solo 10 de cada producto se pueden vender en una única transacción.
- **Inventario**: para obtener información sobre cómo aplicar la configuración de inventario, consulte [Aplicar configuración de inventario](inventory-settings.md).
- **Volver a la compra**: esta propiedad se utiliza para especificar la ruta para el vínculo **Volver a la compra**. La ruta se puede configurar a nivel de sitio, lo que permite a los minoristas llevar al cliente de vuelta a la página de inicio o cualquier otra página del sitio.

## <a name="commerce-scale-unit-interaction"></a>Interacción con Commerce Scale Unit

El módulo del carro recupera la información de producto mediante las API de Commerce Scale Unit. El id. del carro de la cookie del explorador se utiliza para recuperar toda la información de producto de Commerce Scale Unit.

## <a name="add-a-cart-module-to-a-page"></a>Agregar un módulo de carro a una página

Para agregar un módulo de carro a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Vaya a **Fragmentos de página** y seleccione **Nuevo** para crear un nuevo fragmento.
1. En el cuadro de diálogo, **Nuevo fragmento de página**, seleccione el módulo **Carro**.
1. En **Nombre del fragmento de página**, introduzca el nombre **Fragmento de carro** y luego seleccione **Aceptar**.
1. Seleccione el espacio **Carro**.
1. En el panel de propiedades de la derecha, seleccione el símbolo del lápiz, introduzca el texto del encabezado en el campo y luego seleccione el símbolo de marca de verificación.
1. En el espacio **Carro**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Selector de tienda** y elija **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger el fragmento y luego seleccione **Publicar** para publicarlo.
1. Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.
1. En el cuadro de diálogo **Nueva plantilla**, en **Nombre de plantilla**, introduzca un nombre para la plantilla.
1. En el árbol de esquema, seleccione el espacio **Cuerpo**, luego los puntos suspensivos (**...**) y, a continuación, **Agregar fragmento**.
1. En el cuadro de diálogo **Seleccionar fragmento de página**, seleccione el fragmento **Fragmento de carro** y, a continuación, seleccione **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.
1. Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.
1. En el cuadro de diálogo **Elegir una plantilla**, seleccione la plantilla creada anteriormente, introduzca un nombre de página y, a continuación, seleccione **Aceptar**.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.
1. Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general del kit de inicio](starter-kit-overview.md)

[Módulo Contenedor](add-container-module.md)

[Módulo de selector de tienda](store-selector.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulo de icono de carrito](cart-icon-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de confirmación de pedido](order-confirmation-module.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de pie de página](author-footer-module.md)

[Calcular la disponibilidad de inventario para canales comerciales](calculated-inventory-retail-channels.md)
