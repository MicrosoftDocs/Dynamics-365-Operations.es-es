---
title: Módulo de reproductor de vídeo
description: En este tema se tratan los módulos de reproductor de vídeo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 01/23/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: e94658eed12b12d6666e63d2c06b86646c81a120
ms.sourcegitcommit: 829329220475ed8cff5a5db92a59dd90c22b04fa
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/05/2020
ms.locfileid: "3025680"
---
# <a name="video-player-module"></a>Módulo de reproductor de vídeo


[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de reproductor de vídeo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

El módulo de reproductor de vídeo se utiliza para permitir la reproducción de vídeo. Se puede agregar a cualquier página, siempre que el contenido de video se cargue y esté disponible en el sistema de administración de contenido (CMS). El módulo del reproductor de video admite medios de tipo .mp4.

## <a name="video-player-module"></a>Módulo de reproductor de vídeo

El módulo del reproductor de vídeo se puede usar para mostrar vídeos en un sitio de comercio electrónico. Admite todas las capacidades de reproducción, como reproducción, pausa, modo de tamaño completo, descripciones de audio y subtítulos. El módulo de reproductor de vídeo también admite la personalización de subtítulos para cumplir los estándares de accesibilidad de Microsoft. Por ejemplo, puede personalizar el tamaño de fuente y el color de fondo.

El módulo del reproductor de vídeo también admite pistas de audio secundarias. Cuando se carga un vídeo en el CMS, también se puede cargar una pista de audio secundaria. El módulo del reproductor de vídeo puede reproducir la pista de audio secundaria si un usuario la selecciona.

### <a name="examples-of-video-player-modules-in-e-commerce"></a>Ejemplos de módulos de reproductor de vídeo en comercio electrónico

- Vídeos educacionales sobre las páginas de detalles de productos o páginas de marketing
- Vídeos promocionales o vídeos sobre directivas en cualquier página de marketing
- Vídeos de marketing que resaltan características de productos en las páginas de detalles de productos o páginas de marketing

### <a name="video-player-module-properties"></a>Propiedades de módulo de reproductor de vídeo

| Nombre de la propiedad         | Valor                               | Descripción |
|-----------------------|-------------------------------------|-------------|
| Reproducción automática             | **Verdadero** o **Falso**               | Si el valor está establecido en **Verdadero**, el vídeo se reproduce automáticamente. |
| Silenciar                  | **Verdadero** o **Falso**               | Si el valor está establecido en **Verdadero**, el audio está silenciado. Para este reproductor, el valor predeterminado es **Falso**. En el explorador de Chrome, los vídeos de reproducción automática están silenciados de manera predeterminada y el sonido solo se reproduce si el usuario reproduce el vídeo manualmente. |
| Bucle                  | **Verdadero** o **Falso**               | Si el valor está establecido en **Verdadero**, el vídeo se repite en un bucle. |
| Medios                 | Nombre y ruta del archivo de vídeo | El archivo de vídeo se reproduce en el reproductor de vídeo. |
| Reproducir pantalla completa       | **Verdadero** o **Falso**               | Si el valor está establecido en **Verdadero**, el vídeo se reproduce en modo de pantalla completa. |
| Desencadenador de reproducir/pausar    | **Verdadero** o **Falso**               | Si el valor se establece en **Verdadero**, en el vídeo se muestra un botón de reproducción/pausa. |
| Controles de reproductor de vídeo | **Verdadero** o **Falso**               | Si el valor está establecido en **Verdadero**, se muestran todos los controles del reproductor de vídeo. Estos controles incluyen los botones de reproducción y pausa, un indicador de progreso y opciones de subtítulos. |
| Ocultar imagen del publicador     | **Verdadero** o **Falso**               | Un vídeo puede tener un marco de póster. Si el valor de esta propiedad se establece en **Verdadero**, se oculta el marco de póster. |
| Nivel de máscara            | Un número del **0** al **100** | La máscara que se aplica al vídeo para estilo. |

## <a name="add-a-video-player-module-to-a-page"></a>Agregar un módulo de reproductor de vídeo a una página

> [!NOTE] 
> Antes de crear un módulo de reproductor de video tiene que cargar un video en la Biblioteca de medios.

Para agregar un módulo de reproductor de vídeo a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Cree una plantilla de página con el nombre **plantilla de reproductor de vídeo**.
1. En el espacio **Principal** de la página predeterminada, agregue un módulo de contenedor.
1. En el módulo de contenedor, agregue los módulos de reproductor de vídeo y reproductor de vídeo ambiental.
1. Termine de editar la plantilla y publíquela.
1. Use la plantilla de reproductor de vídeo que acaba de crear para crear una página llamada **página de reproductor de vídeo**.
1. En el espacio **Principal** de la página nueva, agregue un módulo de reproductor de vídeo.
1. En el panel de propiedades para el módulo del reproductor de video, seleccione **Agregar un video**.
1. En el cuadro de diálogo **Selector de medios**, seleccione un video y, a continuación, seleccione **Cargar nuevo elemento multimedia**.
1. Guarde la página y obtenga una vista previa de ella. Debería ver el módulo de vídeo en la página. Puede cambiar la configuración adicional para personalizar el comportamiento del módulo.
1. Termine de editar la página y publíquela.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo de banner promocional](add-alert.md)

[Módulo de carrusel](add-carousel.md)

[Módulo de bloque de texto](add-content-rich-block.md)

[Módulo de bloque de contenido](add-hero-module.md)
