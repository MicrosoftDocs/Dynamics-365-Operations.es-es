---
title: Módulo de carro
description: En este artículo se tratan los módulos de carro y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: f3bf61d03d6e318494a13af6721028ac573d7424
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9277068"
---
# <a name="cart-module"></a>Módulo de carro

[!include [banner](includes/banner.md)]

En este artículo se tratan los módulos de carro y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

Un módulo de carro muestra los artículos que se han agregado al carro antes de que el cliente finalice la compra. El módulo también muestra un resumen del pedido y permite al cliente aplicar o quitar códigos promocionales.

El módulo de carro permite finalizar la compra como usuario que ha iniciado sesión o como usuario invitado. También admite un vínculo **Volver a la compra**. Puede configurar la ruta para este vínculo en **Valores de configuración de sitio \> Extensiones \> Rutas**.

El módulo de carrito procesa los datos en función de la ID del carrito, que es una cookie del navegador disponible en todo el sitio. 

La siguiente imagen muestra un ejemplo de una página de carro en el sitio Fabrikam.

![Ejemplo de un módulo de carrito en el sitio de Fabrikam.](./media/cart2.PNG)

La siguiente imagen muestra un ejemplo de una página de carro en el sitio Fabrikam. En este ejemplo, hay una cuota de manipulación para un artículo de línea.

![Ejemplo de un módulo de carrito con una tarifa de manipulación para un artículo de línea.](./media/ecommerce-handling-fee.png)

## <a name="cart-module-properties-and-slots"></a>Franjas y propiedades del módulo del carro

| Propiedad | Valores | Descripción |
|----------------|--------|-------------|
| Cabecera | Texto de encabezado y etiqueta de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | El encabezado del carro, como "Bolsa de compra" o "Artículos en el carro". |
| Mostrar errores de existencias agotadas | **Verdadero** o **Falso** | Si esta propiedad se establece en **Verdadero**, la página del carro mostrará errores relacionados con las existencias. Le recomendamos que establezca esta propiedad en **Verdadero** si se aplican controles de inventario en el sitio. |
| Mostrar gastos de envío para artículos de línea | **Verdadero** o **Falso** | Si esta propiedad se establece en **Verdadero**, las líneas de pedido del carro mostrarán los gastos de envío, si esta información está disponible. Esta característica no es compatible con el tema Fabrikam porque los usuarios seleccionan el envío solo en el flujo de finalización de compra. Sin embargo, esta característica se puede activar en otros flujos de trabajo, si corresponde. |
| Mostrar promociones disponibles| **Verdadero** o **Falso** | Si esta propiedad se establece en **Verdadero**, el carrito muestra las promociones disponibles, según los artículos del carrito. Esta capacidad solo está disponible en la versión 10.0.16 de Dynamics 365 Commerce. |

## <a name="modules-that-can-be-used-in-a-cart-module"></a>Módulos que se pueden usar en un módulo de carro

- **Bloque de texto**: este módulo admite mensajería personalizada en el módulo de carro. Los mensajes se controlan mediante el sistema de gestión de contenidos (CMS). Se puede agregar cualquier mensaje, como “Si hubiera algún problema con el pedido, póngase en contacto con 1-800-Fabrikam”.
- **Selector de tienda**: este módulo muestra una lista de las tiendas cercanas en las que un artículo está disponible para su recogida. Permite a los usuarios especificar una ubicación para encontrar tiendas cercanas. Para obtener más información sobre este módulo, consulte [Módulo selector de tienda](store-selector.md).

## <a name="module-properties"></a>Propiedades del módulo

Las siguientes opciones de cmódulo de carro pueden configurarse en **Configuración de sitio \> Extensiones**:

- **Cantidad máxima**: esta propiedad se usa para especificar el número máximo de cada artículo que se puede agregar al carro. Por ejemplo, un minorista puede decidir si solo 10 de cada producto se pueden vender en una única transacción.
- **Inventario**: para obtener información sobre cómo aplicar la configuración de inventario, consulte [Aplicar configuración de inventario](inventory-settings.md).
- **Volver a la compra**: esta propiedad se utiliza para especificar la ruta para el vínculo **Volver a la compra**. La ruta se puede configurar en el nivel de sitio, lo que permite a los minoristas llevar al cliente de vuelta a la página de inicio o cualquier otra página del sitio.

> [!IMPORTANT]
> En la versión Dynamics 365 Commerce 10.0.14 y posteriores, los artículos del carro se agregan en función de la configuración definida en el perfil de funcionalidad en línea para la tienda en línea en la sede de Commerce. Para obtener más información sobre cómo crear un perfil de funcionalidad en línea y establecer las propiedades necesarias para la agregación, consulte [Crear un perfil de funcionalidad en línea](online-functionality-profile.md).

## <a name="commerce-scale-unit-interaction"></a>Interacción con Commerce Scale Unit

El módulo del carro recupera la información de producto mediante las API de Commerce Scale Unit. El id. del carro de la cookie del explorador se utiliza para recuperar toda la información de producto de Commerce Scale Unit.

## <a name="add-a-cart-module-to-a-page"></a>Agregar un módulo de carro a una página

Para agregar un módulo de carro a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Vaya a **Fragmentos** y seleccione **Nuevo** para crear un nuevo fragmento.
1. En el cuadro de diálogo **Seleccionar fragmento**, seleccione el módulo **Carrito**.
1. En **Nombre del fragmento**, introduzca el nombre **Fragmento de carro** y luego seleccione **Aceptar**.
1. Seleccione el espacio **Carro**.
1. En el panel de propiedades de la derecha, seleccione el símbolo del lápiz, introduzca el texto del encabezado en el campo y luego seleccione el símbolo de marca de verificación.
1. En el espacio **Carrito**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Selector de tienda** y elija **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger el fragmento y luego seleccione **Publicar** para publicarlo.
1. Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.
1. En el cuadro de diálogo **Nueva plantilla**, en **Nombre de plantilla**, introduzca un nombre para la plantilla.
1. En el árbol de esquema, seleccione el espacio **Cuerpo**, luego los puntos suspensivos (**...**) y, a continuación, **Agregar fragmento**.
1. En el cuadro de diálogo **Seleccionar fragmento**, seleccione el fragmento **Fragmento de carro** y, a continuación, seleccione **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.
1. Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.
1. En el cuadro de diálogo **Elegir una plantilla**, seleccione la plantilla creada anteriormente, introduzca un nombre de página y, a continuación, seleccione **Aceptar**.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.
1. Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

## <a name="additional-resources"></a>Recursos adicionales

[Módulo de icono de carro](cart-icon-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de pago](payment-module.md)

[Módulo de dirección de envío](ship-address-module.md)

[Módulo de opciones de entrega](delivery-options-module.md)

[Módulo de información de recogida](pickup-info-module.md)

[Módulo de detalles del pedido](order-confirmation-module.md)

[Módulo de tarjeta de regalo](add-giftcard.md)

[Calcular la disponibilidad de inventario para canales comerciales](calculated-inventory-retail-channels.md)

[Crear un perfil de funcionalidad en línea](online-functionality-profile.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
