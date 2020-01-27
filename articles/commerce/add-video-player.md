---
title: Módulo de reproductor de vídeo
description: En este tema se tratan los módulos de reproductor de vídeo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 12/02/2019
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
ms.openlocfilehash: 1c78583f39dbacdc7b38e89c33e67ae23731bf8a
ms.sourcegitcommit: 96bfc20eb748f4090a2b5e1ff9f54997d5a5d359
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/04/2019
ms.locfileid: "2885910"
---
# <a name="video-player-module"></a>Módulo de reproductor de vídeo

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de reproductor de vídeo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Los módulos de reproductor de vídeo se utilizan para admitir la reproducción de vídeo. Se ofrecen dos módulos de reproductor de vídeo en el kit de inicio de la tienda: el módulo del reproductor de vídeo ambiental y el módulo de reproductor de vídeo. Ambos participantes admiten el tipo de medios .mp4.

## <a name="ambient-video-player-module"></a>Módulo de reproductor de vídeo ambiental

El módulo del reproductor de vídeo ambiental admite vídeos informativos breves. Debe usarse para vídeos que duren menos de cinco segundos. Este reproductor admite capacidades de reproducción de vídeo limitadas, como reproducción y pausa.

### <a name="examples-of-ambient-video-player-modules-in-e-commerce"></a>Ejemplos de módulos de reproductor de vídeo ambiental en comercio electrónico

- Vídeos informativos breves que resaltan nuevos productos en la página principal
- Vídeos informativos breves que resaltan características de productos en una página de detalles de productos

### <a name="ambient-video-player-module-properties"></a>Propiedades del módulo de reproductor de vídeo ambiental

| Nombre de la propiedad     | Valor                 | Descripción |
|-------------------|-----------------------|-------------|
| Reproducción automática          | **Verdadero** o **Falso** | Si el valor está establecido en **Verdadero**, el vídeo se reproduce automáticamente. |
| Silenciar              | **Verdadero** o **Falso** | Si el valor está establecido en **Verdadero**, el audio está silenciado. Para este reproductor, el valor predeterminado es **Verdadero**. En el explorador de Google Chrome, los vídeos de reproducción automática están silenciados de manera predeterminada y el sonido solo se reproduce si el usuario reproduce el vídeo manualmente. |
| Bucle              | **Verdadero** o **Falso** | Si el valor está establecido en **Verdadero**, el vídeo se repite en un bucle. |
| Medios             |  Nombre y ruta del archivo de vídeo | El archivo de vídeo se reproduce por el reproductor de vídeo. |
| Controles de reproducción | **Verdadero** o **Falso** | Si el valor se establece en **Verdadero**, en el vídeo se muestra un botón de reproducción/pausa. Si el valor se establece en **Falso**, no se muestra el botón de reproducción/pausa, pero los usuarios seguirán pudiendo poner en pausa y reanudar el vídeo mediante el teclado. |

## <a name="video-player-module"></a>Módulo de reproductor de vídeo

El módulo del reproductor de vídeo se puede usar para mostrar vídeos en un sitio de comercio electrónico. Admite todas las capacidades de reproducción, como reproducción, pausa, modo de tamaño completo y subtítulos. El módulo de reproductor de vídeo también admite la personalización de subtítulos para cumplir los estándares de accesibilidad de Microsoft. Por ejemplo, puede personalizar el tamaño de fuente y el color de fondo.

El módulo del reproductor de vídeo también admite pistas de audio secundarias. Cuando se carga un vídeo, también se puede cargar una pista de audio secundaria. El módulo del reproductor de vídeo puede reproducir la pista de audio secundaria si un usuario la selecciona.

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
| Controles de reproducción     | **Verdadero** o **Falso**               | Si el valor se establece en **Verdadero**, en el vídeo se muestra un botón de reproducción/pausa. Si el valor se establece en **Falso**, no se muestra el botón de reproducción/pausa, pero los usuarios seguirán pudiendo poner en pausa y reanudar el vídeo mediante el teclado. |
| Reproducir pantalla completa       | **Verdadero** o **Falso**               | Si el valor está establecido en **Verdadero**, el vídeo se reproduce en modo de pantalla completa. |
| Controles              | **Verdadero** o **Falso**               | Si el valor está establecido en **Verdadero**, se muestran todos los controles. Estos controles incluyen los botones de reproducción y pausa, un indicador de progreso y subtítulos. |
| Ocultar marco de póster     | **Verdadero** o **Falso**               | Un vídeo puede tener un marco de póster. Si el valor de esta propiedad se establece en **Verdadero**, se oculta el marco de póster. |
| Nivel de máscara            | Un número del **0** al **100** | La máscara que se aplica al vídeo para estilo. |
| Estilo de icono de pantalla completa | **Cuadrado** o **Flecha**             | El estilo de icono de pantalla completa que se muestra en el reproductor de vídeo. |

## <a name="add-a-video-player-module-to-a-page"></a>Agregar un módulo de reproductor de vídeo a una página

Para agregar un módulo de reproductor de vídeo a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Cree una plantilla de página con el nombre **plantilla de reproductor de vídeo**.
1. En el espacio **Principal** de la página predeterminada, agregue un módulo de contenedor.
1. En el módulo de contenedor, agregue los módulos de reproductor de vídeo y reproductor de vídeo ambiental.
1. Proteja la plantilla y publíquela.
1. Use la plantilla de reproductor de vídeo que acaba de crear para crear una página que se llame **página de reproductor de vídeo**.
1. En el espacio **Principal** de la página nueva, agregue un módulo de reproductor de vídeo ambiental.
1. En la configuración para el módulo de reproductor de vídeo ambiental, vaya a **Medios** y cargue un archivo de vídeo. Puede cambiar **Reproducción automática**, **Bucle** y otras propiedades según sea necesario.
1. Guarde la página y obtenga una vista previa de ella.
1. En el espacio **Principal** de la página nueva, agregue un módulo de reproductor de vídeo.
1. En la configuración para el módulo de reproductor de vídeo, vaya a **Medios** y cargue un archivo de vídeo.
1. Guarde la página y obtenga una vista previa de ella. Debería ver ambos módulos de vídeo en la página. Puede cambiar la configuración adicional para personalizar el comportamiento de cada módulo.
1. Proteja la página y publíquela.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo de alerta](add-alert.md)

[Módulo de carrusel](add-carousel.md)

[Módulo de bloque de enriquecimiento de contenido](add-content-rich-block.md)

[Módulo de sustitución de contenido](add-content-placement-modules.md)

[Módulo de característica](add-feature-module.md)

[Módulo de elemento principal](add-hero-module.md)
