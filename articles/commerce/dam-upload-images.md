---
title: Cargar imágenes
description: En este artículo se describe cómo subir imágenes en el generador de sitios de Microsoft Dynamics 365 Commerce.
author: josaw1
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.custom: ''
ms.assetid: ''
ms.search.industry: ''
ms.openlocfilehash: d937e8c0e00ce28b0e4a4c2feab3ac1c8f075916
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9283389"
---
# <a name="upload-images"></a>Cargar imágenes

[!include [banner](includes/banner.md)]

En este artículo se describe cómo subir imágenes en el generador de sitios de Microsoft Dynamics 365 Commerce.

La Biblioteca de medios del creador de sitios de Commerce le permite cargar imágenes, ya sea individualmente o en masa, utilizando carpetas. Siempre debe cargar la versión de la imagen con la mayor resolución y calidad, ya que el componente de cambio de tamaño de la imagen optimizará automáticamente la imagen para diferentes ventanas y sus puntos de interrupción.

### <a name="image-information-specified-during-upload"></a>Información de imagen especificada durante la carga

Al cargar una imagen, se puede especificar la siguiente información.

- **Título, texto alternativo, descripción, palabras clave**: metadatos de la imagen o imágenes. El título y el texto alternativo son valores obligatorios.
- **Seleccionar categoría**:
    - **Ninguno**: se utiliza para una imagen o imágenes de narración de comercio electrónico.
    - **Producto, Categoría, Cliente, Empleado, Catálogo**: usado para imagen o imágenes omnicanal de Dynamics 365 Commerce.
- **Publicar activos después de subir**: cuando esta casilla de verificación está seleccionada, la imagen o las imágenes se publican inmediatamente después de la carga.

> [!NOTE]
> - Los activos de imagen con una categoría asignada también se etiquetan automáticamente con la categoría como una palabra clave para ayudar a buscar activos de una categoría específica.
> - Las páginas de detalles del producto generan dinámicamente el **Texto alternativo** usando el nombre del producto, así que cambiar el **Texto alternativo** por una imagen de producto no tendrá ningún impacto en la imagen renderizada.

### <a name="naming-conventions-for-omni-channel-images"></a>Convenciones de nomenclatura para imágenes omnicanal 

Si ha configurado la Biblioteca multimedia como el backend de imagen omnicanal, puede usar categorías de imágenes para indicar a qué categoría pertenece la imagen cargada. También hay una convención de nomenclatura que debe seguirse para garantizar que las imágenes sean recuperadas correctamente por otros canales, como el punto de venta (PDV).

La convención de nomenclatura predeterminada varía según la categoría:
- Las imágenes de catálogo deben llamarse "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"
- Las imágenes de categoría deben llamarse "**/Categories/\{CategoryName\}.png**"
- Las imágenes de los clientes deben llamarse "**/Customers/\{CustomerNumber\}.jpg**"
- Las imágenes de los empleados deben llamarse "**/Workers/\{WorkerNumber\}.jpg**"
- Las imágenes del producto deben llamarse "**/Products/\{ProductNumber\}\_000_001.png**"
    - 001 es la secuencia de la imagen y puede ser 001, 002, 003, 004 o 005
- Las imágenes de variante del producto deben llamarse "**/Products/\{ProductNumber\} \^ \{Style\} \^ \{Size\} \^ \{Color\} \^\_000_001.png**"
    - Por ejemplo: 93039 \^ &nbsp;\^ 2 \^ Black \^\_000_001.png
- Las imágenes de variante del producto con dimensión de configuración deben llamarse "**/Products/\{ProductNumber\} \^ \{Configuration\}\_Color 000_001.png**"
    - Por ejemplo: 93039 \^ LB8017_000_001.png

> [!NOTE]
> Para las imágenes de variante del producto, si el valor de la dimensión está vacío, debe haber dos espacios en blanco entre los signos de intercalación en el nombre del archivo.

Los ejemplos anteriores utilizan la configuración predeterminada. El carácter y las dimensiones del separador son configurables y el nombre exacto requerido puede variar entre implementaciones. Un método para identificar la convención de nomenclatura exacta requerida es usar la consola de desarrollador del explorador para inspeccionar las solicitudes de imágenes de variantes del producto mientras se cambian las dimensiones del producto en la página de detalles del producto (PDP) del escaparate.

## <a name="upload-an-image"></a>Subir una imagen

Para subir una imagen al generador de sitios, siga estos pasos.

1. En el panel de navegación izquierdo, seleccione **Biblioteca multimedia**.
1. En la barra de comandos, seleccione **Subir \> Subir elementos multimedia**.
1. En la ventana del Explorador de archivos, navegue y seleccione uno o más archivos de imagen para cargar, y luego seleccione **Abrir**.
1. En el cuadro de diálogo **Subir elemento multimedia**, introduzca el título requerido y el texto alternativo.
1. Introduzca la descripción opcional y las palabras clave y seleccione una categoría si lo desea. 
1. Si quiere publicar las imágenes inmediatamente después de la carga, seleccione la casilla de verificación **Publicar elementos multimedia después de subir**.
1. Seleccione **Aceptar**.

## <a name="upload-a-folder-of-images"></a>Subir una carpeta de imágenes

Para subir en masa una carpeta de imágenes en el generador de sitios, siga estos pasos.

1. En el panel de navegación izquierdo, seleccione **Biblioteca multimedia**.
1. En la barra de comandos, seleccione **Subir \> Subir carpeta**.
1. En la ventana del Explorador de archivos, navegue y una carpeta para cargar, y luego seleccione **Abrir**.
1. En el cuadro de diálogo **Subir elementos multimedia**, introduzca palabras clave opcionales y seleccione una categoría si lo desea. 
1. Si quiere publicar las imágenes en la carpeta inmediatamente después de la carga, seleccione la casilla de verificación **Publicar elementos multimedia después de subir**.
1. Seleccione **Aceptar**.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la administración de activos digitales](dam-overview.md)

[Cargar vídeo](dam-upload-video.md)

[Subir archivos](dam-upload-files.md)

[Recortar imágenes](dam-crop-images.md)

[Personalizar puntos focales de imagen](dam-custom-focal-point.md)

[Cargar y servir archivos estáticos](upload-serve-static-files.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
