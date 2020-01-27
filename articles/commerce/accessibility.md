---
title: Características y funcionalidades de accesibilidad
description: Este tema proporciona información sobre las capacidades y funciones de accesibilidad en Microsoft Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 01/08/2020
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
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3e667f89ffbc5496cc93f83fd3e7b29ba6ffa979
ms.sourcegitcommit: ef3a1d7527311d00b69a1072ae5eb021ce68034c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/09/2020
ms.locfileid: "2946077"
---
# <a name="accessibility-features-and-capabilities"></a>Características y funcionalidades de accesibilidad

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tema proporciona información sobre las capacidades y funciones de accesibilidad en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Las características y capacidades de accesibilidad proporcionan los medios funcionales para que todos los usuarios accedan y realicen acciones para que puedan lograr sus objetivos. Esta amplia gama de usuarios puede requerir herramientas de asistencia para la audición, la visión, la movilidad o la neurodiversidad.

Varias características en Dynamics 365 Commerce le permiten construir su sitio para que incluya la funcionalidad de asistencia. Cuando diseñe su sitio, debe considerar las áreas de funcionalidad de accesibilidad que se mencionan en el [Centro de accesibilidad de Microsoft ](https://www.microsoft.com/accessibility). 

Este tema describe algunas áreas adicionales de funcionalidad de accesibilidad que debe considerar al usar Dynamics 365 Commerce.

## <a name="image-alt-text"></a>Texto alternativo de imagen

Dynamics 365 Commerce tiene un sistema de gestión de activos digitales integrado para rastrear los activos de imagen y video que se utilizan en su sitio. Se pueden agregar leyendas, descripciones y texto alternativo en el panel de propiedades de una imagen cuando se selecciona o se carga.

## <a name="video-accessibility"></a>Accesibilidad de vídeo

El sistema de gestión de activos digitales de Dynamics 365 Commerce admite varias funciones de accesibilidad para contenido de vídeo. Se muestran algunos ejemplos en la tabla siguiente.

| Característica de vídeo               | Descripción |
|-----------------------------|-------------|
| Subtítulos (CC)      | Texto que se puede mostrar para el audio y los elementos descriptivos de audio de un vídeo, para ayudar a los usuarios con discapacidad auditiva |
| Subtítulos                   | Archivos de subtítulos que muestran el texto de pistas de contexto o diálogo en pantalla |
| Transcripciones de audio           | Una transcripción textual de palabras habladas que se genera a partir del audio de un recurso de video |
| Audio descriptivo           | Un canal de audio no primario que describe el contenido o el contexto que ocurre en la pantalla |
| Edad mínima de acceso            | Un atributo que puede almacenar la edad mínima que debe tener un espectador para ver un vídeo (solo metadatos) |

### <a name="configure-video-accessibility-elements"></a>Configurar elementos de accesibilidad de vídeo

En Dynamics 365 Commerce, en la sección **Activos** de su sitio, puede cargar recursos de vídeo que tengan archivos separados para subtítulos, audio normal y audio descriptivo. Los subtítulos también se pueden generar automáticamente cuando se carga un elemento de vídeo.

#### <a name="generate-or-upload-closed-caption-files-during-video-asset-upload"></a>Genere o cargue archivos de subtítulos cerrados durante la carga de activos de vídeo

Para tener un archivo de subtítulos generado automáticamente cuando sube un vídeo, siga este paso.

- En el cuadro de diálogo **Carga de activos**, seleccione **Generar subtítulos automáticamente**. Si está generando un archivo de subtítulos, el selector de archivos para los archivos de subtítulos no estará disponible en el cuadro de diálogo.

Para cargar manualmente un archivo de subtítulos cuando cargue un vídeo, siga este paso.

- En el cuadro de diálogo **Carga de activos**, elimine **Generar subtítulos automáticamente**.

Para cargar audio normal o archivos de audio descriptivos para el vídeo, use el selector de archivos en el cuadro de diálogo **Carga de activos**.

> [!NOTE]
> Los subtítulos, el audio normal y los recursos de audio descriptivos también se pueden agregar después de cargar un activo de video. Vaya a **Activos**, seleccione el elemento de vídeo y compruébelo. Luego, en el panel de propiedades del elemento de vídeo, cargue los activos adicionales.

#### <a name="edit-cc-and-audio-transcript-files"></a>Edite archivos de transcripción de audio y CC

Los archivos de transcripción CC y audio se pueden editar directamente en la herramienta de creación. La reproducción de vídeo está disponible durante la edición.

Para editar archivos de transcripción de audio y CC, siga estos pasos.

1. Vaya a **Activos**, seleccione el recurso de vídeo y luego seleccione **Editar CC / Transcripción**. Aparece el editor de contenido de subtítulos y transcripciones.
1. Seleccione **Desproteger**.
1. Edite el subtítulo o el texto de la transcripción.
1. Cuando haya terminado, seleccione **Guardar** y después **Registrar**.
1. Cuando esté listo para publicar, seleccione **Publicar**.

#### <a name="set-the-minimum-age-attribute"></a>Establecer el atributo Edad mínima

El atributo de metadatos **Edad mínima** puede asociarse con activos de vídeo.

Para configurar el atributo de **Edad mínima** para un recurso de vídeo, siga estos pasos.

1. Vaya a **Activos** y seleccione el recurso de vídeo.
1. Seleccione **Desproteger**.
1. En el panel de propiedades para el recurso de video, establezca el atributo **Edad mínima**.

> [!NOTE]
> El panel de propiedades solo se usa para establecer y almacenar el valor del atributo de metadatos. Se deben crear módulos personalizados para usar este atributo para la protección de reproducción.

## <a name="additional-resources"></a>Recursos adicionales

[Accesibilidad en formularios, productos y controles](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/user-interface/enable-accessibility)

[Centro de accesibilidad de Microsoft](https://www.microsoft.com/accessibility)

[Centro de accesibilidad de Dynamics 365](https://docs.microsoft.com/dynamics365/get-started/accessibility/index)

[Resumen de conformidad](compliance-overview.md)

[Cookie de conformidad](cookie-compliance.md)

[Agregar una página de directivas de privacidad](add-privacy-page.md)
