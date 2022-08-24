---
title: Tarjetas regalo digitales de comercio electrónico
description: Este artículo describe cómo funcionan las tarjetas regalo digitales en la implementación de comercio electrónico de Microsoft Dynamics 365 Commerce. También proporciona una descripción general de los pasos de configuración importantes.
author: anupamar-ms
ms.date: 05/27/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.15
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: b31ef231ea56f1c3d2fc199bb0a19bd0c991dc8b
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270007"
---
# <a name="e-commerce-digital-gift-cards"></a>Tarjetas regalo digitales de comercio electrónico

[!include [banner](includes/banner.md)]

Este artículo describe cómo funcionan las tarjetas regalo digitales en la implementación de comercio electrónico de Microsoft Dynamics 365 Commerce. También proporciona una descripción general de los pasos de configuración importantes.

En Dynamics 365 Commerce, la compra de tarjetas regalo digitales sigue el mismo proceso que la compra de otros productos del sistema. No es necesario configurar módulos adicionales. Si se agregan varias tarjetas regalo al carrito, los artículos de la tarjeta regalo no se agregan en una sola línea de ventas. Este comportamiento es necesario porque cada línea de ventas se factura mediante un número de tarjeta regalo independiente.

La compra de tarjetas regalo digitales se admite en la versión de Dynamics 365 Commerce 10.0.16 y en las posteriores.

La siguiente ilustración muestra un ejemplo de la página de detalles del producto (PDP) para una tarjeta regalo digital en el sitio de comercio electrónico de Fabrikam.

![Ejemplo de una tarjeta regalo digital PDP en el sitio de comercio electrónico de Fabrikam.](./media/GiftcardPDP.PNG)

## <a name="turn-on-the-digital-gift-card-feature-in-commerce-headquarters"></a>Active la función de tarjeta regalo digital en la sede de Commerce

Para que funcione el flujo de compra de las tarjetas regalo digitales en Dynamics 365 Commerce, la característica **Compra de tarjetas regalo en la función de comercio electrónico** debe estar activada en la sede central de Commerce. Puede encontrar la característica en el área de trabajo **Administración de características** de la sede de Commerce, como muestra la ilustración siguiente.

![Espacio de trabajo de administración de características en la sede central de Commerce.](./media/Featureflag.PNG)

## <a name="configure-a-digital-gift-card-in-commerce-headquarters"></a>Configurar una tarjeta regalo digital en la sede central de Commerce

Los productos de tarjetas regalo digitales deben configurarse en la sede central de Commerce. El proceso es similar al proceso para otros productos. Sin embargo, los siguientes pasos importantes son específicos para la configuración de las tarjetas regalo para su compra. Para obtener más información sobre cómo crear y configurar productos, consulte [Crear un nuevo producto en Commerce](create-new-product-commerce.md).

- Al configurar productos de tarjetas regalo digitales en el cuadro de diálogo **Nuevo producto**, configure el campo **Tipo de producto** en **Servicio**. (Para abrir el cuadro de diálogo, vaya a **Venta minorista y comercio \> Productos y categorías \> Productos por categoría** y seleccione **Nuevo**). No se comprueba el inventario disponible para los productos del tipo **Servicio** antes de realizar un pedido. Para obtener más información, consulte [Crear un nuevo producto](create-new-product-commerce.md#create-a-new-product).
- En la página **Parámetros comerciales**, en la página **Destino**, el campo **Producto de tarjeta regalo** debe establecerse en **Tarjeta regalo digital**, como se muestra en la siguiente ilustración. Si el producto es una tarjeta regalo externa, consulte [Soporte para tarjetas regalo externas](./dev-itpro/gift-card.md) para más información.

    ![Campo de producto de tarjeta regalo en la sede de Commerce.](./media/PostGiftcard.png)

- Si una tarjeta regalo debe admitir varios importes predefinidos (por ejemplo, 25 $, 50 $ y 100 $), la dimensión **Tamaño** debe utilizarse para configurar esos importes predefinidos. Cada importe predefinido será una variante del producto. Para obtener más información, consulte [Dimensiones del producto](../supply-chain/pim/product-dimensions.md?toc=%2fdynamics365%2fretail%2ftoc.json).
- Si los clientes deben poder especificar un importe personalizado para una tarjeta regalo, además de las cantidades prdefinidas, primero configure una variante que permita un importe personalizado. El atributo **Tamaño** admite variantes de importe personalizado. A continuación, abra el producto desde la página **Productos lanzados en la categoría** y luego, en la ficha desplegable **Commerce**, establezca el campo **Teclear precio** en **Debe teclear un nuevo precio**, como se muestra en la siguiente ilustración de ejemplo. Esta configuración garantiza que los clientes puedan introducir un precio cuando exploran el producto en un PDP.

    ![Teclear en el campo de precio en la sede central de Commerce.](./media/KeyInPrice.png)
    
    La siguiente ilustración de ejemplo muestra una lista de variantes de productos de tarjetas de regalo digitales en Commerce headquarters, incluidas dos variantes de precios personalizados.
    ![Variantes de productos de tarjetas de regalo digitales con ejemplo de variante de precio personalizado](./media/DigitalGiftCards_ProductVariantsWithCustom.png)

- El modo de entrega de una tarjeta regalo digital debe establecerse en **Electrónico**. En la página **Modos de entrega** (**Venta minorista y comercio \> Configuración de cana l\> Modos de entrega**), selecciona el modo **Electrónico** de entrega en el panel de la lista, y luego agregue el producto de tarjeta regalo digital a la cuadrícula en la ficha desplegable **Productos**, como se muestra en la siguiente ilustración. Para obtener más información, consulte [Configurar los modos de entrega](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

    ![Productos de tarjetas regalo digitales en la página Modo de entrega en la sede de Commerce.](./media/ElectronicMode.PNG)
    
- Asegúrese de que se haya creado un perfil de funcionalidad en línea y asociado con su tienda en línea en la sede de Commerce. En el perfil de funcionalidad, configure la opción **Productos agregados** en **Sí**. Esta configuración garantiza que se agreguen todos los elementos, excepto las tarjetas regalo. Para más información, consulte [Crear un perfil de funcionalidad en línea](online-functionality-profile.md).
- Para asegurarse de que los clientes reciban un correo electrónico después de facturar una tarjeta regalo, cree un nuevo tipo de notificación por correo electrónico en la página **Perfiles de notificación por correo electrónico** y establezca el campo **Tipo de notificación por correo electrónico** en **Emitir tarjeta regalo**. Para más información, vea [Configurar un perfil de notificaciones por correo electrónico](email-notification-profiles.md).

## <a name="add-product-images-to-the-commerce-site-builder-media-library"></a>Agregar imágenes de productos a la biblioteca multimedia del creador de sitios de Commerce

Debe agregar imágenes de productos para productos de tarjetas regalo digitales a la biblioteca de medios del creador de sitios de Commerce. Asegúrese de que los nombres de los archivos de imagen de la tarjeta regalo sigan las convenciones de nomenclatura de su sitio para las imágenes de productos. Para obtener más información, consulte [Cargar imágenes](dam-upload-images.md).

## <a name="configure-a-custom-amount-for-a-digital-gift-card-in-commerce-site-builder"></a>Configurar una cantidad personalizada para una tarjeta regalo digital en el creador de sitios de Commerce

Si una tarjeta regalo digital está configurada para permitir un importe personalizado, este comportamiento también debe habilitarse en el [módulo de caja de regalo](add-buy-box.md) que se utiliza en los PDP de su sitio. El módulo de caja de regalo admite la configuración del módulo para permitir cantidades personalizadas. También puede definir los importes mínimo y máximo permitidos para importes personalizados.

Para configurar una cantidad personalizada para una tarjeta regalo digital en el creador de sitios de Commerce, siga estos pasos.

1. Vaya al módulo de caja de regalo que se utiliza en los PDP de su sitio. Este módulo de caja de regalo puede implementarse en un fragmento, en una plantilla o en una página.
1. Seleccione **Editar**.
1. En el panel de propiedades de la derecha, seleccione la casilla **Permitir precio personalizado**.
1. Opcional: para definir importes mínimos y máximos para importes personalizados, introduzca los importes en **Precio mínimo** y **Precio máximo**.
1. Seleccione **Terminar la edición** y, a continuación, seleccione **Publicar**.

## <a name="additional-resources"></a>Recursos adicionales

[Módulo de cuadro de compra](add-buy-box.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de carro](add-cart-module.md)

[Crear un nuevo producto en Commerce](create-new-product-commerce.md)

[Configurar modos de entrega](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Dimensiones de producto](../supply-chain/pim/product-dimensions.md?toc=%2fdynamics365%2fretail%2ftoc.json)

[Configurar perfil de notificación por correo electrónico](email-notification-profiles.md)

[Crear un perfil de funcionalidad en línea](online-functionality-profile.md)

[Compatibilidad para tarjetas regalo externas](./dev-itpro/gift-card.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
