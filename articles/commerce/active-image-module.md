---
title: Módulo de imagen activa
description: En este tema se tratan los módulos imagen activa y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 07/08/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 36b7d6dea87c7f309c07608794d443a0ae19be211847d2cddcad95f2d933a8db
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716917"
---
# <a name="active-image-module"></a>Módulo de imagen activa

[!include [banner](includes/banner.md)]

En este tema se tratan los módulos imagen activa y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

Se puede utilizar un módulo de imagen activo para incrustar etiquetas de productos en una imagen. Los usuarios del sitio de comercio electrónico pueden pasar el cursor sobre las etiquetas para obtener una vista previa de los productos que se muestran en la imagen. Las vistas previas se muestran en ventanas emergentes. Al seleccionar una ventana emergente de vista previa, los usuarios pueden ir directamente a la página de detalles del producto (PDP) del producto correspondiente.

Las etiquetas se definen mediante el uso de coordenadas X e Y en la imagen. Cada punto etiquetado debe configurarse con el ID de producto del producto que se muestra en la imagen.

La siguiente ilustración muestra un ejemplo de una ventana emergente de vista previa en una imagen principal en la página de inicio de Adventure Works.

![Ejemplo de una ventana emergente de vista previa en un módulo de imagen activo](./media/Active_image.PNG)

> [!IMPORTANT]
> - El módulo de imagen activa está disponible a partir de la versión 10.0.20 de Dynamics 365 Commerce.
> - El módulo de imagen activa se muestra en el tema Adventure Works.

## <a name="active-image-module-properties"></a>Propiedades del módulo de imagen activa

| Nombre de la propiedad      | Valores | Descripción |
|--------------------|--------|-------------|
| Imagen              | Archivo de imagen | Se puede usar una imagen para mostrar uno o más productos. La imagen se puede cargar en la biblioteca de medios en el creador de sitios de Commerce, o se puede usar una imagen existente. |
| Anchura              | Número de píxeles | Esta propiedad define el ancho de la imagen. Las coordenadas activas se calculan en función del ancho de la imagen.|
| Coordenadas activas | Coordenadas X e Y, y un número de identificación del producto | Cada matriz de imágenes activa consta de coordenadas X e Y, y un número de identificación de producto.|
| Cabecera            | Etiqueta de encabezado y texto de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | De manera predeterminada, la etiqueta de encabezado **H2** se usa para el encabezado, pero la etiqueta de encabezado se puede cambiar para cumplir los requisitos de accesibilidad. |
| Párrafo          | Texto de párrafo | El módulo admite texto de párrafo en formato de texto enriquecido. Se admiten algunas capacidades básicas de texto enriquecido, hipervínculos y subrayado y cursiva. Algunas de estas capacidades se pueden anular por el tema de página que se aplica al módulo. |
| Vincular               | Texto de vínculo, dirección URL de vínculo, etiqueta de aplicaciones de Internet enriquecidas accesibles (ARIA) y el selector de **Abrir vínculo en una nueva pestaña** | El módulo admite uno o más vínculos de “llamada a la acción”. Si se agrega un vínculo, se requiere un texto de vínculo, una dirección URL y una etiqueta ARIA. Las etiquetas ARIA deben ser descriptivas para cumplir los requisitos de accesibilidad. Los vínculos se pueden configurar para abrirlos en una nueva pestaña. |
| Trasfondo           | Encabezado, texto y enlaces | Se puede agregar contexto adicional para la imagen, como el nombre de un autor o diseñador, o enlaces a blogs personales.|
| Tema de texto         | **Claro** u **Oscuro** | Esta propiedad permite al usuario establecer el texto en claro u oscuro, según la imagen de fondo. Está disponible como una extensión de tema en el tema Adventure Works. |

## <a name="add-an-active-image-module-to-a-new-page"></a>Agregar un módulo de imagen activo a una nueva página

Para agregar un módulo de imagen activa a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Vaya a **Plantillas** y abra la plantilla de marketing para la página de inicio de su sitio (o cree una nueva plantilla de marketing).
1. En el espacio **Principal** de la página predeterminada, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Imagen activa** y, a continuación, **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.
1. Vaya a **Páginas** y abra la página de inicio del sitio (o cree una nueva página de inicio utilizando la plantilla de marketing).
1. En el espacio **Principal** de la página predeterminada, seleccione los puntos suspensivos (**...**) y, a continuación, **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Imagen activa** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo de imagen activo, agregue una imagen y establezca el ancho del lienzo al tamaño de la imagen.
1. Establezca las coordenadas X e Y y agregue el número de identificación del producto correspondiente.
1. Agregue y configure módulos de imagen activa adicionales según sea necesario.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.
1. Seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.

## <a name="additional-resources"></a>Recursos adicionales

[Descripción general de la biblioteca de módulos](starter-kit-overview.md)

[Tema de Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
