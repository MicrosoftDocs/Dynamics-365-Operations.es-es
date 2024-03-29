---
title: Módulo de reproductor de vídeo
description: En este artículo se tratan los módulos de reproductor de vídeo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 919446981f7439d61b01deb57b206cd457eed919
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9269304"
---
# <a name="video-player-module"></a>Módulo de reproductor de vídeo

[!include [banner](includes/banner.md)]

En este artículo se tratan los módulos de reproductor de vídeo y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

El módulo de reproductor de vídeo se utiliza para permitir la reproducción de vídeo. Se puede agregar a cualquier página, siempre que el contenido de video se cargue y esté disponible en el sistema de administración de contenido (CMS). El módulo del reproductor de video admite medios de tipo .mp4.

## <a name="video-player-module"></a>Módulo de reproductor de vídeo

El módulo del reproductor de vídeo se puede usar para mostrar vídeos en un sitio de comercio electrónico. Admite todas las capacidades de reproducción, como reproducción, pausa, modo de tamaño completo, descripciones de audio y subtítulos. El módulo de reproductor de vídeo también admite la personalización de subtítulos para cumplir los estándares de accesibilidad de Microsoft. Por ejemplo, puede personalizar el tamaño de fuente y el color de fondo.

El módulo del reproductor de vídeo también admite pistas de audio secundarias. Cuando se carga un vídeo en el CMS, también se puede cargar una pista de audio secundaria. El módulo del reproductor de vídeo puede reproducir la pista de audio secundaria si un usuario la selecciona.

### <a name="examples-of-video-player-modules-in-e-commerce"></a>Ejemplos de módulos de reproductor de vídeo en comercio electrónico

- Vídeos educacionales sobre las páginas de detalles de productos o páginas de marketing
- Vídeos promocionales o vídeos sobre directivas en cualquier página de marketing
- Vídeos de marketing que resaltan características de productos en las páginas de detalles de productos o páginas de marketing

La siguiente imagen muestra un ejemplo de un módulo de reproductor de vídeo en una página principal.

![Ejemplo de un módulo de reproductor de vídeo.](./media/ecommerce-videoplayer.PNG)

### <a name="video-player-module-properties"></a>Propiedades de módulo de reproductor de vídeo

| Nombre de la propiedad         | Valor                               | Descripción |
|-----------------------|-------------------------------------|-------------|
| Cabecera               | Etiqueta de encabezado y texto de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | De manera predeterminada, la etiqueta de encabezado **H2** se usa para el encabezado, pero la etiqueta de encabezado se puede cambiar para cumplir los requisitos de accesibilidad. |
| Texto enriquecido             | Texto de párrafo | El módulo admite texto de párrafo en formato de texto enriquecido. Se admiten algunas capacidades básicas de texto enriquecido, hipervínculos y subrayado y cursiva. Algunas de estas capacidades se pueden anular por el tema de página que se aplica al módulo. |
| Vincular                  | Texto de vínculo, dirección URL de vínculo, etiqueta de aplicaciones de Internet enriquecidas accesibles (ARIA) y el selector de **Abrir vínculo en una nueva pestaña** | El módulo admite uno o más vínculos de “llamada a la acción”. Si se agrega un vínculo, se requiere un texto de vínculo, una dirección URL y una etiqueta ARIA. Las etiquetas ARIA deben ser descriptivas para cumplir los requisitos de accesibilidad. Los vínculos se pueden configurar para abrirlos en una nueva pestaña. |
| Trasfondo              | Encabezado, texto o enlaces | Se puede agregar contexto adicional para el módulo del reproductor de video, como el nombre de un autor o diseñador, o enlaces a blogs personales. |
| Reproducción automática             | **Verdadero** o **Falso**               | Si el valor está establecido en **Verdadero**, el vídeo se reproduce automáticamente. |
| Silenciar                  | **Verdadero** o **Falso**               | Si el valor está establecido en **Verdadero**, el audio está silenciado. Para este reproductor, el valor predeterminado es **Falso**. En el explorador de Chrome, los vídeos de reproducción automática están silenciados de manera predeterminada y el sonido solo se reproduce si el usuario reproduce el vídeo manualmente. |
| Bucle                  | **Verdadero** o **Falso**               | Si el valor está establecido en **Verdadero**, el vídeo se repite en un bucle. |
| Medios                 | Nombre y ruta del archivo de vídeo | El archivo de vídeo se reproduce en el reproductor de vídeo. |
| Reproducir pantalla completa       | **Verdadero** o **Falso**               | Si el valor está establecido en **Verdadero**, el vídeo se reproduce en modo de pantalla completa. |
| Desencadenador de reproducir/pausar    | **Verdadero** o **Falso**               | Si el valor se establece en **Verdadero**, en el vídeo se muestra un botón de reproducción/pausa. |
| Controles de reproductor de vídeo | **Verdadero** o **Falso**               | Si el valor está establecido en **Verdadero**, se muestran todos los controles del reproductor de vídeo. Estos controles incluyen los botones de reproducción y pausa, un indicador de progreso y opciones de subtítulos. |
| Ocultar imagen del publicador     | **Verdadero** o **Falso**               | Un vídeo puede tener un marco de póster. Si el valor de esta propiedad se establece en **Verdadero**, se oculta el marco de póster. |
| Nivel de máscara            | Un número del **0** al **100** | La máscara que se aplica al vídeo para estilo. |

> [!IMPORTANT]
> Las propiedades **Encabezado**, **Texto enriquecido**, **Enlace** y **Trasfondo** están disponibles a partir del lanzamiento de la versión 10.0.20 de Dynamics 365 Commerce.

## <a name="add-a-video-player-module-to-a-page"></a>Agregar un módulo de reproductor de vídeo a una página

> [!NOTE] 
> Antes de crear un módulo de reproductor de video tiene que cargar un video en la Biblioteca de medios.

Para agregar un módulo de reproductor de vídeo a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.
1. En el cuadro de diálogo **Nueva plantilla**, en **Nombre de plantilla**, introduzca **Plantilla de reproductor de vídeo** y luego seleccione **Aceptar**.
1. En el espacio **Cuerpo**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Página predeterminada** y, a continuación, **Aceptar**.
1. En el espacio **Principal** del módulo **Página predeterminada**, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.
1. En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Reproductor de vídeo** y, a continuación, **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla. 
1. Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.
1. En el cuadro de diálogo **Crear nueva página**, en **Nombre de página**, introduzca una **Página de reproductor de vídeo** y luego seleccione **Siguiente**.
1. En **Elegir plantilla**, seleccione la **Plantilla de reproductor de vídeo** que ha creado y, a continuación, seleccione **Siguiente**.
1. En **Elija un diseño**, seleccione un diseño de página (por ejemplo, **Diseño flexible**), y luego seleccione **Siguiente**.
1. En **Revisar y terminar**, revise la configuración de la página. Si necesita editar la información de la página, seleccione **Atrás**. Si la información de la página es correcta, seleccione **Crear página**.
1. En el espacio **Principal** de la nueva página, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.
1. En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Reproductor de vídeo** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo de reproductor de video, seleccione **Agregar un video**.
1. En el cuadro de diálogo **Selector de medios**, seleccione un video y, a continuación, seleccione **Cargar nuevo elemento multimedia**.
1. En el Explorador de archivos, seleccione un archivo de vídeo y luego seleccione **Abrir**.
1. En el cuadro de diálogo **Subir elemento multimedia** introduzca un título y otra información según sea necesario, y luego seleccione **Aceptar**.
1. En el cuadro de diálogo **Selector de medios** seleccione **Cerrar**.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página. Debería ver el módulo de vídeo en la página. Puede cambiar la configuración adicional para personalizar el comportamiento del módulo.
1. Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla. 

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de banner promocional](add-alert.md)

[Módulo de carrusel](add-carousel.md)

[Módulo de bloque de texto](add-content-rich-block.md)

[Módulo de bloque de contenido](add-hero-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
