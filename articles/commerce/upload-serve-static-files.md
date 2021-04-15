---
title: Cargar y servir archivos estáticos
description: Este tema describe cómo cargar un archivo estático en el generador de sitios de Microsoft Dynamics 365 Commerce y cómo crear una URL personalizada y un nombre de archivo que se pueda usar para solicitar ese archivo.
author: StuHarg
ms.date: 11/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: stuharg
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: d5f092042b3dda65b041ab2f25f7319dd8e158d1
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5801394"
---
# <a name="upload-and-serve-static-files"></a>Cargar y servir archivos estáticos

[!include [banner](includes/banner.md)]

Este tema describe cómo cargar un archivo estático en el generador de sitios de Microsoft Dynamics 365 Commerce y cómo crear una URL personalizada y un nombre de archivo que se pueda usar para solicitar ese archivo.

Algunos conectores de terceros requieren que un archivo esté hospedado y servido desde el sitio de comercio electrónico. Estos conectores esperan que el archivo sea devuelto por solicitudes a una ruta de acceso URL de devolución de llamada y un nombre de archivo específicos. Por lo tanto, este tema explica cómo cargar y entregar un archivo estático que tiene una URL y un nombre de archivo definibles por el usuario en un sitio de comercio electrónico de Dynamics 365 Commerce.

## <a name="create-a-site-url-that-returns-a-static-file"></a>Crear una URL de sitio que devuelva un archivo estático

Para crear una URL de sitio que devuelva un archivo estático en el generador de sitios de Commerce, siga estos pasos.

1. Vaya a la biblioteca de medios de su sitio y cargue el archivo que deben servir las solicitudes a la URL que definirá. Si ya cargó el archivo, puede omitir este paso.
1. Vaya a las **URL** para su sitio.
1. Seleccione **Nuevo \> Nueva URL**.
1. En el cuadro de diálogo **Nueva URL**, seleccione **Activo de la biblioteca de medios**.
1. En el campo **Ruta de acceso URL**, especifique la ruta de acceso URL. Incluya el nombre del archivo en la ruta de acceso.
1. Seleccione **Siguiente**. La biblioteca de medios se abre y muestra todos los activos de medios del tipo de **documento** que se han subido.
1. Seleccione el archivo que se debe servir para las solicitudes a la URL que definió en el paso 5.
1. Seleccione **Guardar**.

En este punto, la dirección URL que ha creado se encuentra en un estado de borrador. El archivo al que apunta la URL no se devolverá hasta que publique la URL. Antes de publicar la URL, puede validar que devuelva los datos correctos.

## <a name="validate-and-publish-a-url"></a>Validar y publicar una URL

Para validar una URL antes de publicarla, siga estos pasos.

1. Vaya a las **URL** para su sitio y seleccione la URL de la que quiere obtener la vista previa.
2. En el panel de propiedades de la derecha, debajo del botón **Editar**, seleccione el enlace URL correcto. Se abre una nueva ventana del explorador y debería recibir un error 404.
3. Anexe la cadena de consulta **?preview=inprogress** a la URL (por ejemplo, `https://yoursite.com/callback.html?preview=inprogress`) y vuelva a cargar la página. El archivo que cargó en la biblioteca de medios debe devolverse en la respuesta.

Una vez que haya validado la URL, puede publicarla.

1. Vaya a las **URL** para su sitio y seleccione la URL.
2. Seleccione **Publicar** en la barra de comandos.

## <a name="update-the-file-that-a-url-points-to"></a>Actualizar el archivo al que apunta una URL

Una vez publicada una URL, puede actualizarla para que apunte a un archivo diferente. Alternativamente, puede actualizar la URL para que apunte a un tipo de recurso diferente, como se describe en la siguiente sección. Por ejemplo, puede apuntar la URL a una página interna o una redirección.

Para actualizar el archivo al que apunta una URL, siga estos pasos.

1. Vaya a las **URL** para su sitio y seleccione la URL que quiere actualizar.
1. En el panel de propiedades de la derecha, seleccione **Editar**.
1. En **Asignación de URL**, seleccione el cuadro **Paso 2** y luego seleccione un nuevo documento de la biblioteca de medios.
1. Seleccionar **Aplicar**.

## <a name="update-the-asset-type-that-a-url-points-to"></a>Actualizar el tipo de activo al que apunta una URL

También puede actualizar una URL para que apunte a un tipo diferente de activo (recurso), como una página interna o una redirección.

Para actualizar el tipo de activo al que apunta una URL, siga estos pasos.

1. Vaya a las **URL** para su sitio y seleccione la URL que quiere actualizar.
1. En el panel de propiedades de la derecha, seleccione **Editar**.
1. En **Asignación de URL**, en **Paso 1**, seleccione un tipo de activo diferente.
1. Selecciona el cuadro **Paso 2** y, a continuación, seleccione el nuevo activo.
1. Seleccionar **Aplicar**.

## <a name="change-the-url-path"></a>Cambiar la ruta de acceso de la URL

Después de crear una URL, su ruta de acceso no se puede cambiar. Si tiene que cambiar la ruta de acceso de la URL que sirve a un archivo o cualquier otro tipo de recurso, debe crear una nueva URL, asignarla al archivo existente u otro recurso y luego anular la publicación y eliminar la URL anterior.

Para cambiar la ruta de acceso de la URL siga estos pasos.

1. Para crear una nueva URL y asignarla al archivo existente u otro recurso, siga las instrucciones en la sección [Crear una URL de sitio que devuelva un archivo estático](#create-a-site-url-that-returns-a-static-file) anteriormente en este tema.
1. Seleccione la nueva URL y seleccione **Publicar** en la barra de comandos. Se publica la nueva URL.
1. Para anular la publicación de la URL anterior, selecciónela y luego seleccione **Anular publicación** en la barra de comandos. Ahora puede eliminar la URL anterior si lo desea.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la administración de activos digitales](dam-overview.md)

[Cargar imágenes](dam-upload-images.md)

[Subir vídeos](dam-upload-video.md)

[Cargar archivos que no sean imágenes y vídeos](dam-upload-files.md)

[Recortar imágenes](dam-crop-images.md)

[Personalizar puntos focales de imagen](dam-custom-focal-point.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]