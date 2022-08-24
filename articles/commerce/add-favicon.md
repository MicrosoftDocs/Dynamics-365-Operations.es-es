---
title: Agregar un icono favorito
description: En este artículo se explica cómo agregar un icono de favoritos al sitio.
author: bicyclingfool
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 41d6d8f823c7364f9206fd0f7588e35b6f0a018a
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9270447"
---
# <a name="add-a-favicon"></a>Agregar un icono favorito

[!include [banner](includes/banner.md)]

En este artículo se explica cómo agregar un icono de favoritos al sitio.

Un icono de favoritos es un pequeño archivo gráfico que se muestra en una pestaña del explorador web, en la barra de direcciones, en el historial de exploración, y en marcadores o favoritos, entre otros lugares. Recomendamos que agregue un icono de favoritos al sitio, ya que representa y refuerza su marca, y ayuda a diferenciar el sitio de otros que los clientes visitan.

Aunque puede agregar varios iconos favoritos de diversos tamaños y tipos de archivos al sitio, este artículo muestra cómo agregar un icono favorito único. Sin embargo, se utilizan el mismo proceso y ubicación para agregar más iconos favoritos.

## <a name="upload-a-favicon-to-your-sites-asset-collection"></a>Cargue un icono favorito en la colección de activos del sitio

Para cargar un icono favorito en la colección de activos del sitio, siga estos pasos.

1. En el panel de navegación izquierdo, seleccione **Biblioteca multimedia**.
1. En la barra de comandos, seleccione **Subir \> Subir elementos multimedia**.
1. En la ventana del Explorador de archivos, busque el archivo de imagen de icono favorito que desea cargar, selecciónelo y luego seleccione **Abrir**.
1. En el cuadro de diálogo **Subir elemento multimedia**, introduzca el título requerido y el texto alternativo.
1. Si quiere publicar la imagen inmediatamente después de la carga, seleccione la casilla de verificación **Publicar elementos multimedia después de subir**.

    > [!NOTE]
    > Si no selecciona la casilla **Publicar elementos multimedia tras la carga**, debe volver a la página **Elementos multimedia** y publicar manualmente el icono favorito posteriormente.

1. Seleccione **Aceptar**.
1. En el panel de propiedades de la derecha, copie la dirección URL pública del icono favorito. Usará esta URL más tarde.

## <a name="create-the-html-for-your-favicon"></a>Crear el HTML para el icono favorito

Para crear el HTML para el icono favorito, use el siguiente código HTML. Para el atributo **href**, reemplace **"URL\_pública\_para\_su\_icono favorito"** por la dirección URL pública que ha copiado antes.

`<link rel="shortcut icon" href="Public_URL_for_your_favicon">`

## <a name="create-a-fragment-that-contains-a-metatag-for-your-favicon"></a>Crear un fragmento que contenga una metaetiqueta para el favicon

Para crear un fragmento que contenga una metaetiqueta para el icono favorito, siga estos pasos.

1. Vaya a **Fragmentos** y después **Nuevo**.
1. En el cuadro de diálogo **Nuevo fragmento**, seleccione **Metaetiquetas** como módulo en el que se basa el fragmento.
1. Especifique un nombre para el fragmento y después seleccione **Aceptar**.
1. En el árbol de jerarquía de fragmentos, seleccione el elemento secundario **Metaetiquetas predeterminadas**.
1. En el panel derecho, en **Metaetiquetas**, seleccione **Añadir** y luego introduzca la cadena HTML que creó anteriormente para el icono favorito. 
1. Seleccione **Finalizar edición** y luego seleccione **Publicar** para publicar el fragmento.

## <a name="add-the-metatag-fragment-to-the-html-head-section-of-your-pages"></a>Agregar el fragmento de metaetiqueta a la sección de encabezado HTML de las páginas

Para agregar el fragmento de metaetiqueta a la sección **encabezado** de las páginas, siga estos pasos.

1. Vaya a **Plantillas**, abra la plantilla para las páginas en las que desea agregar el icono favorito y luego seleccione **Editar**.
1. En el árbol de jerarquía de plantilla, seleccione el botón de puntos suspensivos (**...**) a la derecha del contenedor **Cabeza HTML** y luego seleccione **Añadir fragmento**.
1. En el cuadro de diálogo **Seleccionar fragmento**, seleccione el fragmento de metaetiqueta creado anteriormente y, a continuación, seleccione **Aceptar**.
1. Seleccione **Finalizar edición** y luego seleccione **Publicar** para publicar la plantilla.

> [!NOTE]
> Si su sitio utiliza más de una plantilla, debe agregar el fragmento de metaetiquetas a todas ellas.

Cuando obtenga una vista previa de las páginas que se basan en la plantilla a la que agregó el fragmento de metaetiquetas, ahora debería ver el icono favorito en la pestaña del navegador.

## <a name="additional-resources"></a>Recursos adicionales

[Agregar un logotipo](add-logo.md)

[Seleccionar un tema de sitio](select-site-theme.md)

[Trabajar con archivos de invalidaciones CSS](css-override-files.md)

[Agregar un aviso de derechos de autor](add-copyright-notice.md)

[Agregar idiomas al sitio](add-languages-to-site.md)

[Agregar secuencia de comandos a páginas del sitio para admitir telemetría](add-telemetry.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
