---
title: Módulo de funciones interactivas
description: En este tema se tratan los módulos de características interactivas y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b1d00b9173fd1d5faee71e0fec6c9d1546989e41
ms.sourcegitcommit: e42c7dd495829b0853cebdf827b86a7cf655cf86
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/17/2021
ms.locfileid: "6638863"
---
# <a name="interactive-feature-module"></a>Módulo de funciones interactivas

[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de características interactivas y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

Los módulos de funciones interactivas son módulos en forma de mosaico que se pueden usar para comercializar múltiples categorías de productos o marcas de productos mediante una combinación de imágenes y texto. Por ejemplo, un minorista puede agregar un módulo de caracterísicas interactivas a la página de inicio de un sitio de comercio electrónico para promocionar las categorías más vendidas. El módulo de funciones interactivas se parece al módulo de lista de mosaicos, pero tiene un diseño diferente y una funcionalidad de interacción diferente.

Cada módulo de características interactivas es una colección de módulos de elementos de características interactivas. Cada módulo de elementos de características está controlado por datos del sistema de gestión de contenidos (CMS). No depende de otros módulos o datos de la sede de Commerce. El módulo de características interactivas se puede agregar en cualquier página de sitio donde un minorista desee comercializar o promocionar algo (por ejemplo, productos, categorías o marcas).

> [!IMPORTANT]
> - El módulo de características interactivas está disponible a partir de la versión 10.0.20 de Dynamics 365 Commerce.
> - El módulo de caracterísicas interactivas se muestra en el tema Adventure Works.

La siguiente ilustración muestra un ejemplo de un módulo de características interactivas en la página de inicio de Adventure Works.

![Ejemplo de un módulo de funciones interactivas en la página de inicio de Adventure Works](./media/Feature.PNG)

## <a name="interactive-feature-module-and-themes"></a>Módulo de temas y funciones interactivas

El módulo de características interactivas pueden admitir varios diseños y estilos, basados en un tema. Por ejemplo, en el tema Adventure Works, el módulo de funciones interactivas tiene un diseño de dos columnas que muestra efectos de animación cuando un usuario del sitio se desplaza sobre cada elemento. El módulo de funciones interactivas está optimizado para un número par de imágenes que se organizan en un diseño de dos columnas.

## <a name="interactive-feature-module-properties"></a>Propiedades del módulo de funciones interactivas

| Nombre de la propiedad | Valores | Descripción |
|---------------|--------|-------------|
| Cabecera       | Etiqueta de encabezado y texto de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Un encabezado de texto para el módulo de características interactivas. |

## <a name="interactive-feature-item-module-properties"></a>Propiedades del módulo de elementos de funciones interactivas

| Nombre de la propiedad | Valores | Descripción |
|---------------|--------|-------------|
| Imagen         | Archivo de imagen | Una imagen que representa un producto o una categoría. La imagen se puede cargar en la biblioteca de medios en el creador de sitios de Commerce, o se puede usar una imagen existente. |
| Cabecera       | Etiqueta de encabezado y texto de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | De manera predeterminada, la etiqueta de encabezado **H2** se usa para el encabezado, pero la etiqueta de encabezado se puede cambiar para cumplir los requisitos de accesibilidad. |
| Párrafo     | Texto de párrafo | El módulo admite texto de párrafo en formato de texto enriquecido. Se admiten algunas capacidades básicas de texto enriquecido, hipervínculos y subrayado y cursiva. Algunas de estas capacidades se pueden anular por el tema de página que se aplica al módulo. |
| Vincular          | Texto de vínculo, dirección URL de vínculo, etiqueta de aplicaciones de Internet enriquecidas accesibles (ARIA) y el selector de **Abrir vínculo en una nueva pestaña** | El módulo admite uno o más vínculos de “llamada a la acción”. Si se agrega un vínculo, se requiere un texto de vínculo, una dirección URL y una etiqueta ARIA. Las etiquetas ARIA deben ser descriptivas para cumplir los requisitos de accesibilidad. Los vínculos se pueden configurar para abrirlos en una nueva pestaña. |

## <a name="add-an-interactive-feature-module-to-a-new-page"></a>Agregar un módulo de características interactivas a una página nueva

Para agregar un módulo de características interactivas a una página nueva y establecer las propiedades necesarias en el generador de sitios de Commerce, siga estos pasos.

1. Vaya a **Plantillas** y abra la plantilla de marketing para la página de inicio de su sitio (o cree una nueva plantilla de marketing).
1. En el espacio **Principal** de la página predeterminada, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Características interactivas** y, a continuación, **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.
1. Vaya a **Páginas** y abra la página de inicio del sitio (o cree una nueva página de inicio utilizando la plantilla de marketing).
1. En el espacio **Principal** de la página predeterminada, seleccione los puntos suspensivos (**...**) y, a continuación, **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, en **Seleccionar módulos**, seleccione el módulo **Características interactivas** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo de características interactivas, agregue un encabezado.
1. En la ranura **Característica interactiva**, seleccione el botón de puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Elemento de características interactivas** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo de elementos de características interactivas, agregue una imagen, texto de encabezado, texto de párrafo y una URL.
1. Agregue y configure módulos de elemento de características interactivas según sea necesario.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.
1. Seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.

## <a name="additional-resources"></a>Recursos adicionales

[Descripción general de la biblioteca de módulos](starter-kit-overview.md)

[Tema de Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
