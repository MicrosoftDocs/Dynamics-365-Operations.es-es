---
title: Modificar una página de sitio existente
description: En este tema se describe cómo modificar una página de sitio existente en Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6afd19a01520813e54871f4849aeb18f4424173c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/15/2021
ms.locfileid: "5223056"
---
# <a name="modify-an-existing-site-page"></a>Modificar una página de sitio existente


[!include [banner](includes/banner.md)]

En este tema se describe cómo modificar una página de sitio existente en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Si debe modificar una página, el primer paso es abrirla en el editor de páginas. Vaya al sitio que contiene su página y, a continuación, en la lista de páginas, encuentre la página que desea. Si no encuentra la página, puede usar la función de búsqueda enriquecida de la herramienta de creación. Escriba el nombre de página exacto o escriba las primeras letras y luego un asterisco (\*). Aparece una lista filtrada de páginas. Puede usar esta lista para encontrar la página que desea. Cuando encuentre la página correcta, seleccione el nombre de la página para abrirla en el editor de páginas.

> [!TIP]
> Si su página está visible en el inspector la página, puede seleccionar **Editar** y desproteger la página antes de abrirla en el editor de páginas. De esta manera, puede desproteger varias páginas al mismo tiempo.

Una vez que se abre la página en el editor de páginas, debe asegurarse de que se ha desprotegido para usted. La barra de comandos de la herramienta de creación es dinámica, contextual y sensible al estado. Por lo tanto, solo muestra las acciones que puede realizar actualmente en la página. Por ejemplo, si la página está desprotegida para usted, los botones **Guardar** y **Terminar edición** no aparecen en la barra de comandos. El estado de la página también se muestra en el lado derecho de la ventana.

Si la página no está ya desprotegida para usted, seleccione **Editar** en la barra de comandos. La barra de comandos cambia para reflejar el nuevo estado de la página. También recibe una notificación que indica que la página se desprotegió para usted.

El siguiente paso es realizar sus cambios reales. A menudo, usará el árbol de esquema de página de la izquierda para encontrar y seleccionar el módulo que desea cambiar y, a continuación, realizará cambios en el panel de propiedades de la derecha. 

No obstante, su cambio puede implicar a veces la adición o eliminación de modelos o fragmentos. Para agregar un fragmento o un módulo, use el árbol de esquema de página para encontrar la franja a la que desea agregar el módulo o el fragmento, y seleccione el botón de puntos suspensivos (**...**) para esa franja. Aparece un menú que incluye comandos para agregar un módulo o un fragmento. Para eliminar un módulo o un fragmento, encuéntrelo y selecciónelo en el árbol de esquema de la página, seleccione el botón de puntos suspensivos y el comando para eliminar el módulo o el fragmento.

> [!TIP]
> También puede ver y editar las propiedades para cualquier módulo que esté visible en la vista previa del generador de páginas visual seleccionándolo directamente.

Una vez que haya terminado de realizar los cambios y de obtener una vista previa del efecto, debe proteger la página seleccionando **Terminar edición** en la barra de comandos. 

Para publicar sus cambios inmediatamente, seleccione **Publicar** en la barra de comandos. Se publica la última versión protegida de la página que ha modificado y se vuelve disponible para los usuarios externos que ven el sitio. 

## <a name="example-change-the-video-on-the-home-page"></a>Ejemplo: Cambiar el vídeo de la página principal

El siguiente ejemplo muestra cómo modificar la página principal cambiando el vídeo que aparece en el módulo del reproductor de vídeo.

1. En **Sitios**, seleccione **Fabrikam** (o el nombre del sitio).
1. En el panel de navegación de la izquierda, seleccione **Páginas**.
1. Busque y seleccione la página principal para abrirla en el editor de páginas.
1. En la barra de comandos, seleccione **Editar**.
1. En el esquema de página, seleccione la franja **Principal**.
1. En la franja **Principal**, expanda todos los módulos de contenedor de fluido.
1. Encuentre y seleccione el módulo de reproductor de vídeo.
1. En el panel de propiedades de la derecha, seleccione la propiedad **vídeo**. Aparece el selector de activos.
1. En el selector de activos, seleccione un activo de vídeo disponible o elija **Cargar nuevo activo** para cargar un nuevo activo de vídeo.
1. Seleccione **Aceptar**.
1. Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.
1. En el campo **Comentarios**, especifique **Cambiar el vídeo** y, a continuación seleccione **Aceptar**.
1. Seleccione **Vista previa** para obtener una vista previa de la página actualizada. Cuando haya terminado, cierre la pestaña de vista previa para volver a la herramienta de creación.
1. Seleccione **Publicar**.

## <a name="additional-resources"></a>Recursos adicionales

[Agregar una página de sitio nueva](add-new-page.md)

[Seleccionar diseños de página](select-page-layouts.md)

[Administrar metadatos de SEO](manage-seo-metadata.md)

[Guardar, obtener una vista previa y publicar una página](save-preview-publish-page.md)

[Enriquecer una página de producto](enrich-product-page.md)

[Enriquecer una página de aterrizaje de categoría](enrich-category-page.md)

[Verificar accesibilidad de contenido de página](verify-accessibility.md)

[Crear páginas de comercio electrónico dinámicas basadas en parámetros de URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]