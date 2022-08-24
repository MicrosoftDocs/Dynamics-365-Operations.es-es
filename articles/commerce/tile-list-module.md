---
title: Módulo de lista de mosaicos
description: En este artículo se tratan los módulos de lista y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: 204465df80e490c8f3f4dc5aca04cb43cd853515
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9284640"
---
# <a name="tile-list-module"></a>Módulo de lista de mosaicos

[!include [banner](includes/banner.md)]

En este artículo se tratan los módulos de lista y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

Un módulo de lista de mosaicos es una colección de mosaicos en un carrusel. Se utiliza para comercializar categorías de productos o marcas de productos a través de imágenes y texto. Por ejemplo, un minorista puede agregar un módulo de lista de mosaicos a la página de inicio de un sitio de comercio electrónico para promocionar todas las categorías más vendidas.

El módulo de lista de iconos está controlado por datos del sistema de gestión de contenidos (CMS). No depende de otros módulos o datos de la sede de Commerce. El módulo de lista de iconos se puede agregar en cualquier página de sitio donde un minorista desee comercializar o promocionar algo (por ejemplo, productos, categorías o marcas).

La siguiente ilustración muestra un ejemplo de un módulo de lista de mosaicos y módulos de mosaicos en la página de inicio de Adventure Works.

![Ejemplo de módulo de lista de icono sy módulos de iconos en la página de inicio de Adventure Works](./media/Tile_list.PNG)

> [!IMPORTANT]
> El módulo de lista de iconos está disponible a partir de la versión 10.0.20 de Dynamics 365 Commerce.
> El módulo de lista de iconos se muestra en el tema Adventure Works.

## <a name="tile-list-modules-and-themes"></a>Módulos y temas de listas de mosaicos

El módulo de lista de iconos pueden admitir varios diseños y estilos, basados en un tema. Por ejemplo, en el tema Adventure Works, los mosaicos muestran un efecto de animación cuando los usuarios del sitio colocan el cursor sobre ellos. Cada tema puede contener propiedades adicionales para la lista de mosaicos y los módulos de mosaicos. Los desarrolladores de temas también pueden crear diseños adicionales para la lista de iconos y los módulos de iconos.

## <a name="tile-list-module-properties"></a>Propiedades del módulo de lista de iconos

| Nombre de la propiedad | Valores | Descripción |
|---------------|--------|-------------|
| Cabecera       | Texto de encabezado y etiqueta de encabezado | Un encabezado de texto para el módulo de lista de mosaicos. |

## <a name="tile-module-properties"></a>Propiedades del módulo de iconos

| Nombre de la propiedad | Valores | Descripción |
|---------------|--------|-------------|
| Imagen         | Archivo de imagen | Se puede usar una imagen para mostrar un producto o una categoría. La imagen se puede cargar en la biblioteca de medios en el creador de sitios de Commerce, o se puede usar una imagen existente. |
| Cabecera       | Etiqueta de encabezado y texto de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | De manera predeterminada, la etiqueta de encabezado **H2** se usa para el encabezado, pero la etiqueta de encabezado se puede cambiar para cumplir los requisitos de accesibilidad. |
| Párrafo     | Texto de párrafo | El módulo admite texto de párrafo en formato de texto enriquecido. Se admiten algunas capacidades básicas de texto enriquecido, hipervínculos y subrayado y cursiva. Algunas de estas capacidades se pueden anular por el tema de página que se aplica al módulo. |
| Vincular          | Texto de vínculo, dirección URL de vínculo, etiqueta de aplicaciones de Internet enriquecidas accesibles (ARIA) y **Abrir vínculo en una nueva pestaña** | Los módulos admiten uno o más vínculos de “llamada a la acción”. Si se agrega un vínculo, se requiere un texto de vínculo, una dirección URL y una etiqueta ARIA. Las etiquetas ARIA deben ser descriptivas para cumplir los requisitos de accesibilidad. Los vínculos se pueden configurar para abrirlos en una nueva pestaña. |
| Enlace de mosaico     | Texto de vínculo, dirección URL de vínculo, etiqueta ARIA y selector **Abrir vínculo en una nueva pestaña** | Esta propiedad se utiliza para definir un enlace de "llamada a la acción". Si se agrega un vínculo, se requiere un texto de vínculo, una dirección URL y una etiqueta ARIA. Las etiquetas ARIA deben ser descriptivas para cumplir los requisitos de accesibilidad. Los vínculos se pueden configurar para abrirlos en una nueva pestaña.|
| Icono          | Imagen | Además de una imagen de producto o categoría, se puede agregar un símbolo de icono. La imagen del símbolo del icono aparecerá sobre la imagen del producto o categoría. |

## <a name="add-a-tile-list-module-to-a-new-page"></a>Agregar un módulo de lista de iconos a una página nueva

Para agregar un módulo de lista de iconos a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Vaya a **Plantillas** y abra la plantilla de marketing para la página de inicio de su sitio (o cree una nueva plantilla de marketing).
1. En el espacio **Principal** de la página predeterminada, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Lista de mosaicos** y, a continuación, **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.
1. Vaya a **Páginas** y abra la página de inicio del sitio (o cree una nueva página de inicio utilizando la plantilla de marketing).
1. En el espacio **Principal** de la página predeterminada, seleccione los puntos suspensivos (**...**) y, a continuación, **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Lista de mosaicos** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo de lista de iconos, agregue un encabezado.
1. En la ranura **Lista de iconos**, seleccione el botón de puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Módulo de mosaicos** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo de mosaico, agregue una imagen, un encabezado y una imagen de símbolo de icono.
1. Agregue y configure módulos de mosaico adicionales según sea necesario.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.
1. Seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.

## <a name="additional-resources"></a>Recursos adicionales

[Descripción general de la biblioteca de módulos](starter-kit-overview.md)

[Tema de Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
