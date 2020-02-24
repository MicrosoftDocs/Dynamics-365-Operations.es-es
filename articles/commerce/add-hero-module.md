---
title: Módulo de bloque de contenido
description: En este tema se tratan los módulos de bloque de contenido y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
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
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: f91de93ce5ed4813f9f2adbe7678229189b5af2f
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025767"
---
# <a name="content-block-module"></a>Módulo de bloque de contenido


[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de bloque de contenido y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Un módulo de bloque de contenido se usa para promociones o productos de mercado a través de una combinación de imágenes y texto. Por ejemplo, un minorista puede agregar un módulo de bloque de contenido a la página principal de un sitio de comercio electrónico para promocionar un nuevo producto y atraer la atención de los clientes.

Un módulo de bloque de contenido está controlado por datos del sistema de gestión de contenidos (CMS). Es un módulo independiente que no dependen de otros módulos de la página. Un módulo de bloque de contenido se puede colocar en cualquier página de sitio donde un minorista desee comercializar o promocionar algo (por ejemplo, productos, ventas o características).

## <a name="examples-of-content-block-module-in-e-commerce"></a>Ejemplos de módulos de bloque de contenido en comercio electrónico

- Un módulo de bloque de contenido se puede usar en la página principal de un sitio de comercio electrónico para resaltar promociones y nuevos productos.
- Un módulo de bloque de contenido se puede usar en una página de detalles de productos para mostrar la información del producto.
- Varios módulos de bloque de contenido se pueden colocar en un módulo de carrusel para resaltar varios productos o promociones.

## <a name="content-block-modules-and-themes"></a>Módulos y temas de bloque de contenido

Los módulos de bloque de contenido pueden admitir varios diseños y estilos basados en un tema. Por ejemplo, el tema Fabrikam admite tres variaciones de diseño de un módulo de bloque de contenido: héroe, característica y mosaico. El diseño del héroe muestra una imagen en el fondo con superposición de texto. El diseño de la característica muestra una imagen y un texto uno al lado del otro. El diseño de mosaico permite múltiples bloques de contenido en un formato de mosaico.

Además, el tema puede exponer diferentes propiedades para cada diseño. Un desarrollador de temas puede construir más diseños con más estilos utilizando el módulo de bloque de contenido.

La siguiente imagen muestra un ejemplo de módulo de bloque de contenido con un diseño de héroe.

![Ejemplo de un módulo de elemento principal](./media/Hero.PNG)

La siguiente imagen muestra un ejemplo de módulo de bloque de contenido con un diseño de característica.

![Ejemplos de módulos de características](./media/Feature.PNG)

## <a name="content-block-module-properties"></a>Propiedades del módulo de bloque de contenido

| Nombre de la propiedad  | Valores | Descripción |
|----------------|--------|-------------|
| Imagen          | Archivo de imagen | Se puede usar una imagen para mostrar un producto o una promoción. Se puede cargar una imagen en la galería de imágenes, o se puede usar una imagen existente. |
| Título        | Etiqueta de encabezado y texto de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Cada módulo de elemento principal puede tener un encabezado. De forma predeterminada, la etiqueta de encabezado **H2** se usa para el encabezado. Sin embargo, la etiqueta se puede cambiar para satisfacer los requisitos de accesibilidad. |
| Párrafo      | Texto de párrafo | Los módulos de elemento principal admiten texto de párrafo en formato de texto enriquecido. Se admiten algunas capacidades básicas de texto enriquecido, como negrita, subrayado y cursiva, además de hipervínculos. Algunas de estas capacidades se pueden anular por el tema de página que se aplica al módulo. |
| Vincular           | Texto de vínculo, dirección URL de vínculo, etiqueta de aplicaciones de Internet enriquecidas accesibles (ARIA) y **Abrir vínculo en una nueva pestaña** | Los módulos de elemento principal admiten uno o más vínculos de “llamada a la acción”. Si se agrega un vínculo, se requiere un texto de vínculo, una dirección URL y una etiqueta ARIA. Las etiquetas ARIA deben ser descriptivas para cumplir los requisitos de accesibilidad. Los vínculos se pueden configurar para abrirlos en una nueva pestaña. |

## <a name="content-block-module-properties-exposed-by-the-fabrikam-theme"></a>Propiedades del módulo de bloque de contenido expuestas por el tema Fabrikam 

| Nombre de la propiedad  | Valores | Descripción |
|----------------|--------|-------------|
| Posición del texto | **Izquierda**, **Derecha**, **Centro** | Esta propiedad define la posición del texto en la imagen. Solo se aplica al diseño del héroe. |
| Tema de texto     | **Claro** u **Oscuro** | Un esquema de colores se puede definir para el texto, en función de la imagen de fondo. Por ejemplo, si la imagen tiene un fondo oscuro, se puede aplicar un tema claro para que el texto sea más visible y cumplir las relaciones de contraste de color para fines de accesibilidad. Solo se aplica al diseño del héroe.|
| Posición de imagen       | **Izquierda**, **Derecha** | Esta propiedad especifica si la imagen debe estar a la izquierda o a la derecha del texto. Solo se aplica al diseño de la característica.  |

## <a name="add-a-content-block-module-to-a-new-page"></a>Agregar un módulo de bloque de contenido a una nueva página

Para agregar un módulo de elemento principal a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Vaya a **Plantillas** y cree una plantilla de página con el nombre **plantilla de bloque de contenido**.
1. En el espacio **Principal** de la página predeterminada, agregue un módulo de elemento principal.
1. Proteja la plantilla y publíquela.
1. Use la plantilla de héroe que acaba de crear para crear una página que se llame **página de bloque de contenido**.
1. En el espacio **Principal** de la página predeterminada, seleccione los puntos suspensivos (**...**) y, a continuación, **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, en **Seleccionar módulos**, seleccione el módulo de elemento principal y, a continuación, **Aceptar**.
1. En el árbol de esquema de la izquierda, seleccione el módulo de bloque de contenido.
1. En el panel de propiedades de la derecha, seleccione **Agregar una imagen**. A continuación, seleccione una imagen existente o cargue una imagen nueva.
1. Seleccione **Encabezado**.
1. En el cuadro de diálogo **Encabezado**, agregue el texto del encabezado, seleccione el nivel de encabezado y luego **Aceptar**.
1. En **Texto enriquecido**, agregue el texto según sea necesario.
1. Seleccione **Agregar vínculo**.
1. En el cuadro de diálogo **Vínculo**, agregue el texto del vínculo, una dirección URL de vínculo y una etiqueta ARIA para el vínculo. A continuación. seleccione **Aceptar**.
1. Selecciona el diseño **Héroe**.
1. Guarde la página y obtenga una vista previa de los cambios.
1. Proteja la página y publíquela.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo de banner promocional](add-alert.md)

[Módulo de carrusel](add-carousel.md)

[Módulo de bloque de texto](add-content-rich-block.md)

[Módulo de reproductor de vídeo](add-video-player.md)
