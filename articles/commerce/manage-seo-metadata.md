---
title: Administrar metadatos de SEO
description: Este artículo describe cómo administrar los metadatos de la optimización de motor de búsqueda (SEO) en Microsoft Dynamics 365 Commerce.
author: psimolin
ms.date: 04/21/2022
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
ms.openlocfilehash: 99c28c2bff7b683f3e92dea4ba24d8bead556443
ms.sourcegitcommit: 6616b969afd6beb11a79d8e740560bf00016ea7f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/17/2022
ms.locfileid: "9027318"
---
# <a name="manage-seo-metadata"></a>Administrar metadatos de SEO

[!include [banner](includes/banner.md)]

Este artículo describe cómo administrar los metadatos de la optimización de motor de búsqueda (SEO) en Microsoft Dynamics 365 Commerce.

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
1. En el editor de páginas, en la parte superior del control de contorno de la página a la izquierda, seleccione el (símbolo de engranaje) **Opción de modo de esquema** y, a continuación, seleccione **Vista de esquema avanzada**.
1. En la vista de esquema, expanda los controles de árbol para mostrar el contenido de la ranura **Encabezado HTML**.
1. En la ranura **Encabezado HTML**, seleccione el módulo SEO deseado (por ejemplo, **Resumen de la página**, **Resumen de la página del producto**, **Resumen de la página de categoría** o **Metaetiquetas**).
1. En el panel de propiedades de la derecha, edite los datos SEO deseados para el módulo SEO seleccionado (por ejemplo, **Título**, **Descripción** o **Compartir imagen**).
1. Seleccione **Guardar** y, a continuación, seleccione **Finalizar edición**.
1. En el campo **Comentarios**, escriba **Datos SEO actualizados** y, a continuación, seleccione **Aceptar**.
1. Seleccione **Vista previa** para obtener una vista previa de la página. Cuando haya terminado, cierre la pestaña de vista previa para volver a la herramienta de creación.
1. Seleccione **Publicar**.

> [!TIP]
> Los autores pueden utilizar el (símbolo de engranaje) **Opción de modo de esquema** en la parte superior del control de contorno izquierdo en el editor de páginas para cambiar entre **Vista de esquema básica** y **Vista de esquema avanzada**. **Vista de esquema básica** es la configuración predeterminada y filtra el esquema para que muestre solo los módulos en la ranura HTML **Cuerpo** para una página. **Vista de esquema avanzada** muestra todo el módulo de la página, incluidas las ranuras **Encabezado HTML**, **Comienzo del cuerpo** y **Fin del cuerpo**. Esta vista es útil cuando los autores deben editar la configuración específica del módulo de script o SEO para una página.

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
