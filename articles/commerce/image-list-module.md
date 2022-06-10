---
title: Módulo de lista de imágenes
description: En este tema se tratan los módulos de lista de imágenes y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
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
ms.openlocfilehash: 67da83410d819d01396d0b7d421076ee3b0f17ec
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780852"
---
# <a name="image-list-module"></a>Módulo de lista de imágenes

[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de lista de imágenes y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

El módulo de lista de imágenes se puede utilizar para agregar fácilmente una colección (matriz) de imágenes a las páginas del sitio. Cada imagen de la matriz se puede configurar con texto de párrafo y URL de enlace. El módulo de lista de imágenes es más adecuado para mostrar logotipos de marcas o una lista que incluye logotipos.

> [!IMPORTANT]
> - El módulo de lista de imágenes está disponible en la biblioteca del módulo de Comercio a partir del lanzamiento de la versión 10.0.20 de Dynamics 365 Commerce.
> - El módulo de lista de imágenes se muestra en el tema Adventure Works.

La siguiente ilustración muestra un ejemplo en el que un módulo de lista de imágenes muestra una lista de texto que incluye logotipos en una página de sitio de empresa a consumidor (B2C) de Adventure Works.

![Ejemplo de un módulo de lista de imágenes que muestra una lista de texto que incluye logotipos](./media/Image_list.PNG)

La siguiente ilustración muestra un ejemplo en el que un módulo de lista de imágenes muestra una lista de texto que incluye logotipos de marca en una página de sitio de empresa a empresa (B2B) de Adventure Works.

![Ejemplo de un módulo de lista de imágenes que muestra logotipos de marcas](./media/Image_list_B2B.PNG)

## <a name="image-list-module-properties"></a>Propiedades del módulo de lista de imágenes

| Nombre de la propiedad | Valores | Descripción |
|---------------|--------|-------------|
| Cabecera       | Etiqueta de encabezado y texto de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Un encabezado de texto para el módulo de lista de imágenes. |
| Lista de imágenes    | Imágenes, texto y URL | Cada elemento de la matriz es una imagen que va acompañada de un texto de párrafo y una URL. |

## <a name="add-an-image-list-module-to-a-new-page"></a>Agregar un módulo de lista de imágenes a una nueva página

Para agregar un módulo de lista de imágenes a una página nueva y establecer las propiedades necesarias en el generador de sitios de Commerce, siga estos pasos.

1. Vaya a **Plantillas** y abra la plantilla de marketing para la página de inicio de su sitio (o cree una nueva plantilla de marketing).
1. En el espacio **Principal** de la página predeterminada, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Lista de imágenes** y, a continuación, **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.
1. Vaya a **Páginas** y abra la página de inicio del sitio (o cree una nueva página de inicio utilizando la plantilla de marketing).
1. En el espacio **Principal** de la página predeterminada, seleccione los puntos suspensivos (**...**) y, a continuación, **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Lista de imágenes** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo de lista de imágenes, agregue un encabezado (por ejemplo, **Nuestras marcas**).
1. Agregue un elemento de lista de imágenes y especifique una imagen, un texto de párrafo y una URL de redireccionamiento.
1. Agregue y configure módulos de elemento de lista de imágenes adicionales según sea necesario.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.
1. Seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.

## <a name="additional-resources"></a>Recursos adicionales

[Descripción general de la biblioteca de módulos](starter-kit-overview.md)

[Tema de Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
