---
title: Agregar una página de sitio nueva
description: En este tema se describe cómo agregar una página de sitio nueva en Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/14/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 4b031431499eba0e109ac04dc46ec187250eba694284864bf78bb1f90265d788
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/05/2021
ms.locfileid: "6725395"
---
# <a name="add-a-new-site-page"></a>Agregar una página de sitio nueva

[!include [banner](includes/banner.md)]

En este tema se describe cómo agregar una página de sitio nueva en Microsoft Dynamics 365 Commerce.

Una vez que ha creado las plantillas y los fragmentos para su sitio, el paso siguiente es empezar a crear las páginas que los usen. Para empezar, debe seleccionar una plantilla o un diseño, un nombre de página y una dirección URL de página.

## <a name="template-or-layout"></a>Plantilla o diseño

Puede usar una plantilla o un diseño para su nueva página. Para obtener más información, consulte [Visión general de plantillas y diseños](templates-layouts-overview.md).

## <a name="page-name"></a>Nombre de página

El nombre de la página debe ser único para la página. Debe ser descriptivo, de modo que pueda encontrarlo fácilmente y otras entidades sepan para qué está pensada la página. Elija el nombre de la página cuidadosamente porque no se podrá cambiar posteriormente.

## <a name="page-url"></a>URL de página

Puede tener la opción de especificar una dirección URL para la nueva página. Al crear una página, puede especificar una cadena que se usará para formar una dirección URL completa. Esta cadena se conoce como dirección URL relativa o slug de URL. Una URL completa se genera entonces en función del slug de URL y se le asigna la nueva página. Puede cambiar el slug de URL más tarde, antes de publicar la página. Para obtener más información, consulte [Crear una URL de página](create-page-URL.md).

> [!NOTE]
> Dynamics 365 Commerce desacopla direcciones URL y contenido. Es decir, se puede crear una página que no está asociada a una dirección URL, y se puede crear una dirección URL que no está asociada a una página. Por lo tanto, el intercambiar de contenido se puede hacer para una dirección URL y no requiere tiempo de inactividad, y las redirecciones son más fáciles de gestionar.

## <a name="add-a-new-page"></a>Agregar una página nueva

Para agregar una página de sitio nueva al sitio, siga estos pasos.

1. En **Sitios**, seleccione **Fabrikam** (o el nombre del sitio).
1. Seleccione **Página nueva**.
1. En el cuadro de diálogo **Página nueva**, seleccione una plantilla y **Aceptar**.
1. En el campo **Nombre de página**, especifique un nombre de página (por ejemplo, **Mi página nueva**).
1. En el campo **URL**, especifique una cadena (slug de URL) para completar la dirección URL (por ejemplo, **mynewpage**).
1. Seleccione **Aceptar**. Aparece el editor de páginas. Observe que un encabezado y un pie de página se agregan automáticamente a la página, en función de la plantilla que ha seleccionado.
1. En la página Esquema, seleccione el espacio **Principal**, los puntos suspensivos (**...**) y, a continuación, **Agregar módulo**.
1. Seleccione **Contenedor** y, a continuación, seleccione **Aceptar**.
1. Seleccione **Contenedor de fluido**, el botón de puntos suspensivos y **Agregar módulo**.
1. Seleccione **Bloque de enriquecimiento de contenido** y, a continuación, **Aceptar**.
1. Seleccione **Bloque de enriquecimiento de contenido**, el botón de puntos suspensivos y **Agregar módulo**.
1. Seleccione **Elemento de bloque de enriquecimiento de contenido** y, a continuación, **Aceptar**.
1. En el panel de las propiedades de la derecha, seleccione **Párrafo** y, a continuación, en el campo, escriba **Mi texto de prueba**.
1. Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.
1. En el campo **Comentarios**, especifique **Nueva página agregada** y, a continuación seleccione **Aceptar**.
1. Seleccione **Vista previa** para obtener una vista previa de la página. Cuando haya terminado, cierre la pestaña de vista previa para volver a la herramienta de creación.
1. Seleccione **Publicar**.
1. En la ruta de navegación, seleccione **Fabrikam** (o el nombre del sitio).
1. En el panel de navegación de la izquierda, seleccione **Direcciones URL**.
1. Busque y seleccione su dirección URL (**minuevapágina**) en la lista.
1. Seleccione **Publicar**.

## <a name="additional-resources"></a>Recursos adicionales

[Modificar una página de sitio existente](modify-existing-page.md)

[Seleccionar diseños de página](select-page-layouts.md)

[Administrar metadatos de SEO](manage-seo-metadata.md)

[Guardar, obtener una vista previa y publicar una página](save-preview-publish-page.md)

[Enriquecer una página de producto](enrich-product-page.md)

[Enriquecer una página de aterrizaje de categoría](enrich-category-page.md)

[Verificar accesibilidad de contenido de página](verify-accessibility.md)

[Crear páginas de comercio electrónico dinámicas basadas en parámetros de URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
