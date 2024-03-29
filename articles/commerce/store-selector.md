---
title: Módulo de selector de tienda
description: En este artículo se trata el modulo selector de tiendao y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
manager: annbe
ms.openlocfilehash: aa3aed837072cb6c3d4f7f92bec2f4b700408cf7
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9268350"
---
# <a name="store-selector-module"></a>Módulo de selector de tienda

[!include [banner](includes/banner.md)]

En este artículo se trata el modulo selector de tiendao y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.

Los clientes pueden usar el módulo selector de tiendas para recoger un producto en una tienda seleccionada después de una compra en línea. En la versión 10.0.13 de Commerce, el módulo selector de tienda también incluye capacidades adicionales que pueden mostrar una página **Encontrar una tienda** que muestra tiendas cercanas.

El módulo selector de tiendas permite a los usuarios especificar una ubicación (ciudad, estado, dirección, etc.) para buscar tiendas dentro de un radio de búsqueda. Cuando se abre el módulo por primera vez, utiliza la ubicación del navegador del cliente para encontrar tiendas (si se proporciona el consentimiento).

## <a name="store-selector-module-usage"></a>Uso del módulo de selector de tienda

- Se puede usar un módulo selector de tiendas en una página de detalles del producto (PDP) para seleccionar una tienda como punto de recogida.
- Se puede usar un módulo selector de tiendas en una página de carrito para seleccionar una tienda como punto de recogida.
- Se puede usar un módulo selector de tiendas en una página independiente que muestra todas las tiendas disponibles.

## <a name="fulfillment-group-setup-in-commerce-headquarters"></a>Configuración de grupos de cumplimentación en la sede de Commerce

Para que el selector de tiendas muestre las tiendas disponibles, el grupo de cumplimiento debe estar configurado en la sede de Commerce. Para obtener más información, consulte [Configurar grupos de cumplimentación](customer-orders-overview.md#set-up-fulfillment-groups).

Además, para cada tienda del grupo de cumplimiento, la latitud y la longitud de la ubicación de la tienda deben definirse en la sede.

Para introducir la longitud y latitud de una ubicación de la tienda en la sede de Commerce, siga estos pasos.

1. Vaya a **Gestión del inventario \> Configuración \> Desglose del inventario**
1. Seleccione la ubicación de almacén en el panel izquierdo.
1. En la ficha desplegable **Direcciones**, seleccione **Avanzado**.

    ![Ejemplo de detalles de la tienda en la sede.](./media/Store-address.png)

1. En el panel Acciones, seleccione **Editar**.
1. En la ficha desplegable **General**, introduzca valores para **Latitud** y **Longitud**.

    ![Ejemplo de configuración de latitud y longitud para una tienda en la sede.](./media/Store-latitude-longitude.png)

1. En el panel Acciones, seleccione **Guardar**. 

### <a name="hide-a-store-from-the-store-selector-module"></a>Ocultar una tienda del módulo selector de tiendas

Es posible que algunas tiendas de un grupo de cumplimiento no sean ubicaciones de recogida válidas. Para asegurarse de que solo las ubicaciones de recogida válidas aparezcan como opciones en el módulo de selección de tiendas, siga estos pasos en la sede de Commerce.

1. Vaya a **Retail y Commerce \> Configuración de Commerce \> Grupos de cumplimiento \> Todas las tiendas**.
1. En el panel Acciones, seleccione **Editar**.
1. Bajo **Configuración**, para cada tienda que no sea una ubicación de recogida válida, borre la casilla **Es la ubicación de recogida**.
1. En el panel Acciones, seleccione **Guardar**.
1. Ejecute el trabajo de programación de distribución 1070 **Configuración del canal**.

## <a name="bing-maps-integration"></a>Integración con Bing Maps

El módulo selector de tiendas está integrado con las [Interfaces de programación de aplicaciones (API) REST de Bing Maps](/bingmaps/rest-services/) para utilizar las características de geocodificación y Autosuggest de Bing. Se requiere una clave de la API de Bing Maps, y debe agregarse a la página de parámetros compartidos en la Central de Commerce. La API de geocodificación se utiliza para convertir una ubicación en valores de latitud y longitud. La integración con la API de Autosuggest se utiliza para mostrar sugerencias de búsqueda cuando los usuarios ingresan ubicaciones en el campo de búsqueda.

Para la API REST de Autosuggest, debe asegurarse de que las siguientes URL estén permitidas según la directiva de seguridad de contenido (CSP) de su sitio. Esta configuración se realiza en el creador de sitios de Commerce, agregando las direcciones URL permitidas a varias directivas CSP para el sitio (por ejemplo, **img-src**). Para más información, consulte [Directiva de seguridad de contenido](manage-csp.md). 

- Para la directiva **connect-src**, agregue **&#42;.bing.com**.
- Para la directiva **img-src**, agregue **&#42;.virtualearth.net**.
- Para la directiva **script-src**, **agregue &#42;.bing.com, &#42;.virtualearth.net**.
- Para la directiva **script style-src**, agregue **&#42;.bing.com**.

## <a name="pickup-in-store-mode"></a>Modo Recoger en tienda

El módulo selector de tienda admite un modo **Recoger en tienda** que muestra una lista de tiendas donde un producto está disponible para su recogida. También muestra el horario de la tienda y el inventario de productos para cada tienda en la lista. El módulo selector de tienda requiere el contexto de un producto para representar la disponibilidad del producto y permitir que el usuario agregue el producto al carrito, si el modo de entrega del producto está configurado en **recoger** en la tienda seleccionada. Para obtener más información, consulte [Configuración de inventario](inventory-settings.md). 

El módulo selector de tiendas se puede agregar a un módulo de caja de compra en la página de detalles del producto para mostrar las tiendas donde hay un producto disponible para su recogida. También se puede agregar a un módulo de carrito. En este caso, el módulo selector de tienda muestra las opciones de recogida para cada artículo de línea en el carrito. El módulo selector de tienda también se puede agregar a otras páginas o módulos a través de extensiones y personalizaciones.

Para que funcione este escenario, los productos deben configurarse para poder utilizr el modo de entrega de **recogida**. De lo contrario, el módulo no se mostrará en las páginas de productos. Para obtener más información sobre cómo configurar el modo de entrega, consulte [Configurar modos de entrega](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery).

La siguiente imagen muestra un ejemplo de un módulo selector de tienda utilizado en un PDP.

![Ejemplo de un módulo selector de tienda utilizado en un PDP.](./media/BOPIS.PNG)

> [!NOTE]
> En la versión 10.0.16 y posteriores, se puede habilitar una nueva características que permite a una organización definir múltiples modos de recogida de opciones de entrega para los clientes.  Si esta función está habilitada, el selector de tiendas y otros módulos de comercio electrónico se mejorarán para permitir que el comprador elija entre múltiples opciones de entrega de recogida si están configuradas.  Para obtener más información sobre esta característica, consulte [esta documentación](./multiple-pickup-modes.md). 

## <a name="find-stores-mode"></a>Modo Buscar tiendas

El módulo selector de tienda también admite un modo **Buscar tiendas**. Este modo se puede usar para crear una página de ubicaciones de tiendas que muestra las tiendas disponibles y su información. En este modo, el módulo selector de tiendas funciona sin contexto del producto y puede usarse como un módulo independiente en cualquier página del sitio. Además, si las configuraciones relevantes están activadas para el módulo, los usuarios pueden seleccionar una tienda como su tienda preferida. Cuando se selecciona una tienda como la tienda preferida de un usuario, el identificador de la tienda se mantiene en las cookies del navegador. Por lo tanto, el usuario debe aceptar un mensaje de consentimiento de cookies.

La siguiente ilustración muestra un ejemplo de un módulo selector de tiendas que se utiliza junto con un módulo de mapa en una página de ubicaciones de tiendas.

![Ejemplo de un módulo selector de tienda y un módulo de mapa en una página de ubicaciones de tiendas.](./media/ecommerce-Storelocator.PNG)

## <a name="render-a-map"></a>Representar un mapa

El módulo selector de tiendas se puede usar junto con el módulo de mapa para mostrar las ubicaciones de la tienda en un mapa. Para obtener más información sobre este módulo del mapa, consulte [Módulo del mapa](map-module.md).

## <a name="store-selector-module-properties"></a>Propiedades del módulo selector de tienda

| Nombre de la propiedad | Valor | Descripción |
|---------------|-------|-------------|
| Cabecera | Texto | El encabezado del módulo. |
| Modo | **Buscar tiendas** o **Recoger en tienda** | El modo **Buscar tiendas** muestra las tiendas disponibles. El modo **Recoger en tienda** permite a los usuarios seleccionar una tienda como punto de recogida. |
| Estilo | **Diálogo** o **En línea** | El módulo se puede representar en línea o en un cuadro de diálogo. |
| Establecer como tienda preferida | **Verdadero** o **Falso** | Cuando esta propiedad se establece en **True**, los usuarios pueden establecer una tienda preferida. Esta característica requiere que los usuarios acepten un mensaje de consentimiento de cookies. |
| Mostrar todas las tiendas | **Verdadero** o **Falso** | Cuando esta propiedad se establece en **True**, los usuarios pueden evitar la propiedad **Buscar radio** y ver todas las tiendas. |
| Opciones de Autosuggest: resultados máximos | Número | Esta propiedad define el número máximo de resultados de sugerencias automáticas que se pueden mostrar a través de la API de Bing Autosuggest. |
| Radio de búsqueda | Número | Esta propiedad define el radio de búsqueda de tiendas, en millas. Si no se especifica ningún valor, se utiliza el radio de búsqueda predeterminado: 50 millas. |
| Términos del servicio | Dirección URL |  Esta propiedad especifica la URL de los términos del servicio que se requiere para usar el servicio Bing Maps. |

## <a name="site-settings"></a>Valores de configuración de sitio

El módulo selector de tiendas respeta la configuración de [Agregar el producto al carrito](add-cart-settings.md). Una vez que se agrega un artículo al carrito desde el módulo selector de tiendas, los usuarios del sitio verán los flujos de trabajo configurados correspondientes.

## <a name="add-a-store-selector-module-to-a-page"></a>Agregar un módulo de selector de tienda a una página

Para el modo **Recoger en tienda**, el módulo solo se puede usar en PDP y páginas de carrito. Debe establecer el modo en **Recoger en tienda** en el panel de propiedades del módulo.

- Para obtener información sobre cómo agregar un módulo selector de tienda a un módulo de caja de compra, vea [Módulo de caja de compra](add-buy-box.md). 
- Para obtener información sobre cómo agregar un módulo selector de tienda a un módulo de carrito, vea [Módulo de carrito](add-cart-module.md)

Para configurar el módulo selector de tiendas para mostrar las tiendas disponibles para una página de ubicaciones de tiendas, como en la ilustración que aparece anteriormente en este artículo, siga estos pasos.

1. Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.
1. En el cuadro de diálogo **Nueva plantilla**, en **Nombre de la plantilla**, introduzca **Plantilla de marketing** y luego seleccione **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.
1. Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.
1. En el cuadro de diálogo **Crear nueva página**, en **Nombre de página**, introduzca **Ubicaciones de tienda** y luego seleccione **Siguiente**.
1. En **Elegir plantilla**, seleccione la **Plantilla de marketing** que creó y, a continuación, seleccione **Siguiente**.
1. En **Elija un diseño**, seleccione un diseño de página (por ejemplo, **Diseño flexible**), y luego seleccione **Siguiente**.
1. En **Revisar y terminar**, revise la configuración de la página. Si necesita editar la información de la página, seleccione **Atrás**. Si la información de la página es correcta, seleccione **Crear página**. 
1. En el espacio **Principal** de la nueva página, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.
1. En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Contenedor con dos columnas** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo, establezca el valor **Ancho** para **Llenar contenedor**.
1. Establezca el valor de **Configuración de columna de puerto de vista muy pequeño** en **100 %**.
1. Establezca el valor de **Configuración de columna de puerto de vista pequeño** en **100 %**.
1. Establezca el valor de **Configuración de columna de puerto de vista mediano** en **33 % 67 %**.
1. Establezca el valor de **Configuración de columna de puerto de vista grande** en **33 % 67 %**.
1. En el espacio **Contenedor con dos columnas**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Selector de tienda** y elija **Aceptar**.
1. En el panel de propiedades del módulo, establezca el valor **Modo** en **Buscar tiendas**.
1. Establezca el valor **Buscar radio** en millas.
1. Establezca otras propiedades, como **Establecer como tienda preferida**, **Mostrar todas las tiendas** y **Habilitar sugerencia automática**, como lo requiera.
1. En el espacio **Contenedor con dos columnas**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Asignar** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo, configure las propiedades adicionales según necesite.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.
 
## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulo de carro](add-cart-module.md)

[Visita rápida de PDP](quick-tour-pdp.md)

[Paseo rápido por el carro y la finalización de la compra](quick-tour-cart-checkout.md)

[Configurar modos de entrega](/dynamicsax-2012/appuser-itpro/set-up-modes-of-delivery)

[Administrar Mapas de Bing para su organización](dev-itpro/manage-bing-maps.md)

[API de REST de Bing Maps](/bingmaps/rest-services/)

[Módulo de Maps](map-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
