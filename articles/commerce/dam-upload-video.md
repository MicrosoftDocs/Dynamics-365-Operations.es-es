---
title: Subir vídeos
description: En este tema se describe cómo subir vídeos en el generador de sitios de Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 03/03/2020
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 98cb4f9049509dd700cf38a5d176447f86e9c824
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2020
ms.locfileid: "3097081"
---
# <a name="upload-videos"></a>Subir vídeos

[!include [banner](includes/banner.md)]

En este tema se describe cómo subir vídeos en el generador de sitios de Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

La Biblioteca de medios del generador de sitios de Commerce le permite subir vídeos. Siempre debe cargar la versión de la versión del vídeo con la mayor velocidad de bits y resolución, porque el vídeo se convertirá automáticamente para ser adecuado para diferentes ventanas y sus puntos de interrupción.

### <a name="video-information-specified-during-upload"></a>Información de vídeo especificada durante la carga

Al subir un vídeo, se puede especificar la siguiente información.

- **Título, descripción, palabras clave**: metadatos del vídeo.
- **Generar subtítulos automáticamente**: especifica si los subtítulos deben generarse automáticamente para el vídeo.
- **Subtítulos** : especifica los subtítulos que se utilizarán.
- **Audio normal**: especifica la pista de audio normal que se utilizará.
- **Miniatura**: especifica la miniatura del vídeo. Si no se especifica, se generará automáticamente.
- **Audio descriptivo**: especifica la pista de audio descriptivo que se utilizará.

## <a name="upload-a-video"></a>Subir un vídeo

Para subir un vídeo al generador de sitios, siga estos pasos.

1. En el panel de navegación izquierdo, seleccione **Biblioteca multimedia**.
1. En la barra de comandos, seleccione **Subir \> Subir elementos multimedia**.
1. En la ventana del Explorador de archivos, navegue y seleccione uno o más archivos de vídeo para cargar, y luego seleccione **Abrir**.
1. En el cuadro de diálogo **Subir elemento multimedia**, introduzca el título requerido y el texto alternativo.
1. Introduzca la descripción opcional y las palabras clave y seleccione una categoría si lo desea. 
1. Si quiere publicar las imágenes inmediatamente después de la carga, seleccione la casilla de verificación **Publicar elementos multimedia después de subir**
1. Seleccione **Aceptar**.

Si está cargando varios tipos de activos simultáneamente (por ejemplo, imágenes y videos), en el cuadro de diálogo **Subir elemento multimedia** solo podrá especificar palabras clave, si los archivos deben publicarse inmediatamente después de la carga y si los subtítulos deben generarse automáticamente para los archivos de vídeo. Todos los activos compartirán las mismas palabras clave.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la administración de activos digitales](dam-overview.md)

[Subir imágenes](dam-upload-images.md)

[Subir archivos](dam-upload-files.md)

[Recortar imágenes](dam-crop-images.md)

[Personalizar puntos focales de imagen](dam-custom-focal-point.md)
