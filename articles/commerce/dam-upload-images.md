---
title: Subir imágenes
description: En este tema se describe cómo cargar imágenes en el generador de sitios de Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 69b812c58739357dfdb3f9e65e34e5d54d890284
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4963019"
---
# <a name="upload-images"></a>Subir imágenes

[!include [banner](includes/banner.md)]

En este tema se describe cómo cargar imágenes en el generador de sitios de Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

La Biblioteca de medios del creador de sitios de Commerce le permite cargar imágenes, ya sea individualmente o en masa, utilizando carpetas. Siempre debe cargar la versión de la imagen con la mayor resolución y calidad, ya que el componente de cambio de tamaño de la imagen optimizará automáticamente la imagen para diferentes ventanas y sus puntos de interrupción.

### <a name="image-information-specified-during-upload"></a>Información de imagen especificada durante la carga

Al cargar una imagen, se puede especificar la siguiente información.

- **Título, texto alternativo, descripción, palabras clave**: metadatos de la imagen o imágenes. El título y el texto alternativo son valores obligatorios.
- **Seleccionar categoría**:
    - **Ninguno**: se utiliza para una imagen o imágenes de narración de comercio electrónico.
    - **Producto, Categoría, Cliente, Empleado, Catálogo**: usado para imagen o imágenes omnicanal de Dynamics 365 Commerce.
- **Publicar activos después de subir**: cuando esta casilla de verificación está seleccionada, la imagen o las imágenes se publican inmediatamente después de la carga.

> [!NOTE]
> Los activos de imagen con una categoría asignada también se etiquetan automáticamente con la categoría como una palabra clave para ayudar a buscar activos de una categoría específica.

### <a name="naming-conventions-for-omni-channel-images"></a>Convenciones de nomenclatura para imágenes omnicanal 

Si ha configurado la Biblioteca multimedia como el backend de imagen omnicanal, puede usar categorías de imágenes para indicar a qué categoría pertenece la imagen cargada. También hay una convención de nomenclatura que debe seguirse para garantizar que las imágenes sean recuperadas correctamente por otros canales, como el punto de venta (PDV).

La convención de nomenclatura predeterminada varía según la categoría:
- Las imágenes de catálogo deben llamarse "**/Catalogs/\{LanguageId\}/\{CatalogName\}.jpg**"
- Las imágenes de categoría deben llamarse "**/Categories/\{CategoryName\}.png**"
- Las imágenes de los clientes deben llamarse "**/Customers/\{CustomerNumber\}.jpg**"
- Las imágenes de los empleados deben llamarse "**/Workers/\{WorkerNumber\}.jpg**"
- Las imágenes del producto deben llamarse "**/Products/\{ProductNumber\}_000_001.png**"
    - 001 es la secuencia de la imagen y puede ser 001, 002, 003, 004 o 005
- Las imágenes de variante del producto deben llamarse "**/Products/\{ProductNumber\}\_\{Size\}\_\{Color\}\_\{Style\}\_000_001.png**"

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
