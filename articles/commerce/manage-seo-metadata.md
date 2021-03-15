---
title: Administrar metadatos de SEO
description: Este tema describe cómo administrar los metadatos de la optimización de motor de búsqueda (SEO) en Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: c7cf9e76ffb30ee5c8bba318b2644e67c757bff0
ms.sourcegitcommit: 872600103d2a444d78963867e5e0cdc62e68c3ec
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2021
ms.locfileid: "5097424"
---
# <a name="manage-seo-metadata"></a>Administrar metadatos de SEO


[!include [banner](includes/banner.md)]

Este tema describe cómo administrar los metadatos de la optimización de motor de búsqueda (SEO) en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Los metadatos SEO para un sitio se pueden administrar mediante mapas de sitio y metadatos de página.
    
## <a name="site-maps"></a>Mapas del sitio

Un mapa del sitio es una lista legible, en formato XML, de las páginas de su sitio web. Se ha pensado para ser consumido por motores de búsqueda, de modo que puedan proporcionar mejores resultados de la búsqueda desde el sitio. Los mapas del sitio se pueden ingerir manualmente por motores de búsqueda o publicarse en un archivo robots.txt.

Dynamics 365 Commerce admite la creación automática de mapas del sitio. Los mapas del sitio se actualizan automáticamente cuando las páginas se publican y se cancela su publicación.

### <a name="turn-on-site-map-generation"></a>Activar la generación de mapa del sitio

1. Inicie sesión en la herramienta de creación.
1. En **Sitios**, seleccione **Fabrikam** (o el nombre del sitio).
1. En el panel de navegación de la izquierda, seleccione **Administración de sitios**.
1. Asegúrese de que la opción **Mapas del sitio habilitados** está activada.

## <a name="page-metadata"></a>Metadatos de página

Dynamics 365 Commerce le permite administrar metadatos SEO para páginas individuales. Puede ver y modificar esta información en la sección **Propiedades de SEO** de un contenedor de página. Se admiten las siguientes propiedades de metadatos SEO:

- Cargo
- Descripción
- Palabras clave SEO
- Etiquetas de aria
- noindex
- nofollow
- noarchive
- nocache
- noOpenDirectoryProject
- nosnippet
- noImageIndex
- unavailableAfter

### <a name="modify-page-metadata"></a>Modificar metadatos de página

Para modificar metadatos de página, siga estos pasos.

1. En **Sitios**, seleccione **Fabrikam** (o el nombre del sitio).
1. En el panel de navegación de la izquierda, seleccione **Páginas**.
1. Seleccione la página principal para abrirla en el editor de páginas.
1. En la barra de comandos, seleccione **Editar**.
1. En el panel de propiedades de la derecha, expanda **Etiquetas META predeterminadas**.
1. Para agregar una nueva etiqueta META, seleccione **Agregar** y después introduzca la etiqueta en el campo. Para quitar un etiqueta META existente, seleccione el símbolo de papelera que se encuentra a su derecha.
1. Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.
1. En el campo **Comentarios**, especifique **Etiquetas META actualizadas** y, a continuación seleccione **Aceptar**.
1. Seleccione **Vista previa** para obtener una vista previa de la página. Cuando haya terminado, cierre la pestaña de vista previa para volver a la herramienta de creación.
1. Seleccione **Publicar**.

## <a name="additional-resources"></a>Recursos adicionales

[Modificar una página de sitio existente](modify-existing-page.md)

[Agregar una página de sitio nueva](add-new-page.md)

[Seleccionar diseños de página](select-page-layouts.md)

[Guardar, obtener una vista previa y publicar una página](save-preview-publish-page.md)

[Enriquecer una página de producto](enrich-product-page.md)

[Enriquecer una página de aterrizaje de categoría](enrich-category-page.md)

[Verificar accesibilidad de contenido de página](verify-accessibility.md)

[Crear páginas de comercio electrónico dinámicas basadas en parámetros de URL](create-dynamic-pages.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]