---
title: Módulo de galería de medios
description: En este artículo se tratan los módulos de galería multimedia y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: Release 10.0.13
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 5e2d0a4422341badee906c71bebdd491e18a38cc
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9273468"
---
# <a name="media-gallery-module"></a>Módulo de galería de medios

[!include [banner](includes/banner.md)]

En este artículo se tratan los módulos de galería multimedia y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

Los módulos de la galería multimedia muestran una o más imágenes en una vista de galería. Los módulos de galería multimedia admiten imágenes en miniatura que se pueden organizar horizontalmente fila (como fila debajo de la imagen) o verticalmente (como columna junto a la imagen). Los módulos de la galería multimedia también proporcionan funcionalidades que permiten que las imágenes se amplíen (aumenten) o se vean en modo de pantalla completa. Para representarse en un módulo de galería multimedia, una imagen debe estar disponible en la Biblioteca multimedia del generador de sitios de Commerce. Actualmente, los módulos de la galería multimedia solo admiten imágenes.

En el modo predeterminado, un módulo de galería multimedia utiliza el identificador del producto que está disponible en el contexto de la página de una página de detalles del producto (PDP) para representar las imágenes del producto correspondiente. En la Central de Commerce, se debe definir una ruta de archivo multimedia para todos los productos. Luego, las imágenes deben cargarse en la Biblioteca multimedia del creador de sitios de acuerdo con la ruta del archivo que se definió para los productos en la Central de Commerce. Estas imágenes incluyen imágenes de productos y cualquier variante de producto. Para obtener más información sobre cómo cargar imágenes a la Biblioteca multimedia del creador de sitios, consulte [Cargar imágenes](dam-upload-images.md).

Alternativamente, un módulo de galería multimedia puede hospedar un conjunto de imágenes completamente mantenidas en una página de galería de imágenes, donde no hay dependencias en el identificador del producto o el contexto de la página. En este caso, las imágenes deben cargarse en la Biblioteca multimedia del generador de sitios y especificarse en el generador de sitios.

Aquí hay algunos ejemplos de uso para módulos de galería multimedia:

- Representar imágenes de productos en un PDP
- Representar imágenes de productos en una página de marketing de productos
- Mostrar un conjunto de imágenes mantenidas en una página de marketing, como una página de galería

En el ejemplo de la siguiente ilustración, un cuadro de compra en un PDP hospeda imágenes de productos utilizando un módulo de galería multimedia.

![Ejemplo de un cuadro de compra en una página de detalles del producto que hospeda imágenes del producto utilizando un módulo de galería multimedia.](./media/ecommerce-pdp-buybox.PNG)

## <a name="media-gallery-properties"></a>Módulo de galería multimedia

| Nombre de la propiedad | Valores | Descripción |
|---------------|--------|-------------|
| Origen de imagen | **Contexto de la página** o **Id. de producto** | El valor predeterminado es **Contexto de la página**. Si **Contexto de la páginaI** está seleccionado, el módulo espera que la página proporcione la información del identificador del producto. Si **Id. de producto** está seleccionado, el identificador del producto para una imagen debe proporcionarse como el valor de la propiedad del **Id. de producto**. Esta funcionalidad está disponible en Commerce, versión 10.0.12. |
| Identificador de producto | Un identificador de producto | Esta propiedad solo es aplicable si el valor de la propiedad **Origen de la imagen** es **Id. de producto**. |
| Zoom de imagen | **En línea** o **Contenedor** | Esta propiedad permite al usuario hacer zoom en las imágenes en el módulo de galería multimedia. Una imagen se puede ampliar en línea o en un contenedor separado junto a la imagen. Esta funcionalidad está disponible en la versión 10.0.12. |
| Factor de zoom | Número decimal | Esta propiedad especifica el factor de escala para hacer zoom en las imágenes. Por ejemplo, si el valor se establece en **2,5**, las imágenes se amplían 2,5 veces. |
| Pantalla completa | **Verdadero** o **Falso** | Esta propiedad especifica si las imágenes se pueden ver en modo de pantalla completa. En el modo de pantalla completa, las imágenes también pueden ampliarse aún más si se activa la capacidad de zoom. Esta capacidad está disponible en Commerce, versión 10.0.13. |
| Calidad de imagen ampliada | Un número del 1 al 100 que representa un porcentaje y que se selecciona mediante un control de la barra de seguimiento | Esta propiedad define la calidad de la imagen para imágenes ampliadas. Se puede configurar al 100 por cien para garantizar que una imagen ampliada utilice siempre la resolución más alta posible. Esta propiedad no se aplica a los archivos PNG, porque utilizan un formato sin pérdidas. Esta capacidad está disponible a partir de la versión 10.0.19 de Commerce. |
| Imágenes | Imágenes que se seleccionan de la Biblioteca multimedia del creador de sitios | Además de representarse desde un producto, las imágenes se pueden mantener para un módulo de galería multimedia. Estas imágenes se agregarán a cualquier imagen de producto que esté disponible. Esta funcionalidad está disponible en Commerce, versión 10.0.12. |
| Orientación de miniaturas | **Vertical** u **Horizontal** | Esta propiedad especifica si las imágenes en miniatura deben mostrarse en una franja vertical o una franja horizontal. |
| Ocultar imágenes maestras del producto para la variante | **Verdadero** o **Falso** | Si esta propiedad se establece en **Verdadero**, cuando se selecciona una variante, las imágenes del producto maestro se ocultan, a menos que la variante no tenga imágenes. Esta propiedad no afecta a los productos que no tienen variantes. |
| Actualizar medios en selección de dimensión | **Verdadero** o **Falso** | Si esta propiedad se establece en **True**, las imágenes de la biblioteca multimedia se actualizarán cuando se seleccione cualquier dimensión (como color, estilo o tamaño) y si hay una imagen disponible. Esta propiedad ayuda a simplificar la experiencia de navegación, ya que no es necesario seleccionar todas las dimensiones de las variantes del producto para que se actualice la imagen correspondiente. Esta propiedad está disponible en la pestaña **Avanzado**. |

> [!IMPORTANT]
> La propiedad **Actualizar loss elmentos multimedia al seleccionar dimensiones** está disponible a partir de la versión 10.0.21 de Commerce. Requiere que esté instalada la versión 9.31 del paquete de la biblioteca de módulos de Commerce.

La siguiente ilustración muestra un ejemplo de un módulo de galería multimedia donde están disponibles las opciones de pantalla completa y zoom.

![Ejemplo de un módulo de galería multimedia donde están disponibles las opciones de pantalla completa y zoom.](./media/ecommerce-media-zoom.png)

La siguiente ilustración muestra un ejemplo de un módulo de galería multimedia que tiene imágenes mantenidas (es decir, las imágenes especificadas no dependen del identificador del producto o del contexto de la página).

![Ejemplo de un módulo de galería multimedia que tiene imágenes mantenidas.](./media/ecommerce-media-curated.PNG)

## <a name="commerce-scale-unit-interaction"></a>Interacción con Commerce Scale Unit

Cuando la fuente de la imagen se deriva del contexto de la página, el identificador del producto del PDP se utiliza para recuperar las imágenes. El módulo de la galería multimedia recupera la ruta del archivo de imagen para los productos mediante las interfaces de programación de aplicaciones (API) de Commerce Scale Unit. Luego, las imágenes se extraen de la Biblioteca multimedia para que puedan representarse en el módulo.

## <a name="add-a-media-gallery-module-to-a-page"></a>Agregar un módulo de galería multimedia a una página

Para agregar un módulo de galería multimedia a una página de marketing, siga estos pasos.

1. Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.
1. En el cuadro de diálogo **Nueva plantilla**, en **Nombre de la plantilla**, introduzca **Plantilla de marketing** y luego seleccione **Aceptar**.
1. En el espacio **Cuerpo**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Página predeterminada** y, a continuación, **Aceptar**.
1. En el espacio **Principal** de la página predeterminada, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.
1. Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.
1. En el cuadro de diálogo **Crear nueva página**, en **Nombre de página**, introduzca una **Página de galería de medios** y luego seleccione **Siguiente**.
1. En **Elegir plantilla**, seleccione la **Plantilla de marketing** que creó y, a continuación, seleccione **Siguiente**.
1. En **Elija un diseño**, seleccione un diseño de página (por ejemplo, **Diseño flexible**), y luego seleccione **Siguiente**.
1. En **Revisar y terminar**, revise la configuración de la página. Si necesita editar la información de la página, seleccione **Atrás**. Si la información de la página es correcta, seleccione **Crear página**. 
1. En el espacio **Principal** de la nueva página, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.
1. En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulo**, seleccione el módulo **Galería de medios** y, a continuación, **Aceptar**.
1. En el panel de propiedades para el módulo de galería multimedia, en **Fuente de imagen**,seleccione **Id. del producto**. Luego, en el campo **Id. de producto**, indique el identificador del producto.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página. Debería poder ver las imágenes del producto en una vista de galería.
1. Para usar solo imágenes seleccionadas, en el panel de propiedades, en **Origen de imagen**, seleccione **Id. del producto**. Después, en **Imágenes**, seleccione **Agregar una imagen** tantas veces como sea necesario para agregar imágenes desde la Biblioteca multimedia.
1. Establezca las propiedades adicionales que desee establecer, como **Zoom de imagen**, **Factor de zoom** y **Orientación de miniaturas**.
1. Cuando haya terminado, seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarlo.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulo de contenedor](add-container-module.md)

[Cargar imágenes](dam-upload-images.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
