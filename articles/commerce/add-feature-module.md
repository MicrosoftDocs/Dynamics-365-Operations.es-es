---
title: Módulo de característica
description: En este tema se tratan los módulos de características y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
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
ms.openlocfilehash: 76b59681d0bda11446f6db8b2685d1a0656f8f55
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785315"
---
# <a name="feature-module"></a>Módulo de característica 

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de características y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Un módulo de características se usa para promociones o productos de mercado a través de una combinación de imágenes y texto. Por ejemplo, un minorista puede agregar un módulo de características a una página de detalles de productos para resaltar las características del producto.

Un módulo de características está controlado por datos del sistema de gestión de contenidos (CMS). Es un módulo independiente que no dependen de otros módulos de la página. Un módulo de características se puede colocar en cualquier página de sitio donde un minorista desee comercializar o promocionar algo (por ejemplo, productos, ventas o características).

## <a name="examples-of-feature-modules-in-e-commerce"></a>Ejemplos de módulos de características en comercio electrónico

Un módulo de características se puede usar en las siguientes páginas:

- Una página de detalles de productos, para mostrar características de producto.
- La página principal, para promocionar productos
- Una página de categoría, para resaltar una categoría de productos

## <a name="feature-module-properties"></a>Propiedades de módulo de características

| Nombre de la propiedad     | Valores | Descripción |
|-------------------|--------|-------------|
| Imagen             | Archivo de imagen | Se puede usar una imagen para comercializar el producto o la promoción. Se puede cargar una imagen en la galería de imágenes, o se puede usar una imagen existente. |
| Título           | Etiqueta de encabezado y texto de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Cada módulo de características puede tener un encabezado. De forma predeterminada, la etiqueta de encabezado **H2** se usa para el encabezado. Sin embargo, la etiqueta se puede cambiar para satisfacer los requisitos de accesibilidad. |
| Párrafo         | Texto de párrafo | Los módulos de características admiten texto de párrafo en formato de texto enriquecido. Se admiten algunas capacidades básicas de texto enriquecido, como negrita, subrayado y cursiva, además de hipervínculos. Algunas de estas capacidades se pueden anular por el tema de página que se aplica al módulo. |
| Vincular              | Texto de vínculo, dirección URL de vínculo, etiqueta de aplicaciones de Internet enriquecidas accesibles (ARIA) y **Abrir vínculo en una nueva pestaña** | Los módulos de características admiten uno o más vínculos de “llamada a la acción”. Si se agrega un vínculo, se requiere un texto de vínculo, una dirección URL y una etiqueta ARIA. Las etiquetas ARIA deben ser descriptivas para cumplir los requisitos de accesibilidad. Los vínculos se pueden configurar para abrirlos en una nueva pestaña. |
| Posición de imagen   | **Derecha**, **Izquierda**, **Arriba** o **Inferior** | Esta propiedad define la posición de la imagen en relación con el texto. Por ejemplo, si se selecciona **Derecha**, la imagen aparece a la derecha del texto. |
| Tamaño de columna de imagen | Un valor del **1** al **12** | Esta propiedad define el tamaño de la imagen en relación con el texto. El tamaño se expresa como un número de columnas en la página. Hay 12 columnas en una página. De forma predeterminada, la imagen y el texto tienen igual tamaño (seis columnas cada uno). Sin embargo, el tamaño se puede ajustar según sea necesario. |

## <a name="add-a-feature-module-to-a-new-page"></a>Agregar un módulo de características a una página nueva 

Para agregar un módulo de características a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Vaya a **Plantillas** y cree una plantilla de página con el nombre **plantilla de características**.
1. En el espacio **Principal** de la página predeterminada, agregue un módulo de características.
1. Proteja la plantilla y publíquela.
1. Use la plantilla de características que acaba de crear para crear una página con el nombre **página de características**.
1. En el espacio **Principal** de la página predeterminada, seleccione los puntos suspensivos (**...**) y, a continuación, **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, en **Seleccionar módulos**, seleccione un módulo de características y, a continuación, **Aceptar**.
1. En el árbol de esquema de la izquierda, seleccione el módulo de características.
1. En el panel de propiedades de la derecha, seleccione **Agregar una imagen**. A continuación, seleccione una imagen existente o cargue una imagen nueva.
1. Seleccione **Encabezado**.
1. En el cuadro de diálogo **Encabezado**, agregue el texto del encabezado, seleccione el nivel de encabezado y luego **Aceptar**.
1. En **Texto enriquecido**, agregue el texto según sea necesario.
1. Seleccione **Agregue vínculo de acción**.
1. En el cuadro de diálogo **Vínculo de acción**, agregue el texto del vínculo, una dirección URL del vínculo y una etiqueta ARIA para el vínculo y, a continuación seleccione **Aceptar**.
1. Guarde la página y obtenga una vista previa de los cambios.
1. Proteja la página y publíquela.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo de alerta](add-alert.md)

[Módulo de carrusel](add-carousel.md)

[Módulo de bloque de enriquecimiento de contenido](add-content-rich-block.md)

[Módulo de sustitución de contenido](add-content-placement-modules.md)

[Módulo de elemento principal](add-hero-module.md)

[Módulo de reproductor de vídeo](add-video-player.md)
