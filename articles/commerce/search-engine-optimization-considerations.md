---
title: Consideraciones de optimización de motor de búsqueda (SEO) para su sitio
description: Este tema trata las consideraciones de la optimización de motor de búsqueda (SEO) para su sitio desde el desarrollo hasta la producción.
author: psimolin
ms.date: 05/25/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.openlocfilehash: 2f90581766dba3d3a671df52ec08339a1a0fd7dc
ms.sourcegitcommit: 9dd2d32fc303023a509d58ec7b5935f89d1e9c6d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/26/2022
ms.locfileid: "8806414"
---
# <a name="search-engine-optimization-seo-considerations-for-your-site"></a>Consideraciones de optimización del motor de búsqueda (SEO) para su sitio


[!include [banner](includes/banner.md)]

Este tema trata las consideraciones de la optimización de motor de búsqueda (SEO) para su sitio desde el desarrollo hasta la producción.

## <a name="a-site-that-is-under-development"></a>Un sitio que se encuentra en desarrollo

Para garantizar que los motores de búsqueda no indexen un sitio en desarrollo, todas las páginas del sitio deben tener las meta etiquetas **noindex** y **nofollow** etiquetas meta. Una buena práctica es crear un fragmento basado en el [Módulo MetaTags](metatags-module.md) que contiene la siguiente entrada de etiqueta meta y asegúrese de que el fragmento se agregue a la sección HTML \<head\> de todas las plantillas utilizadas en su sitio.

```html
<meta name="robots" content="noindex,nofollow" /> 
```

## <a name="soft-launch-of-a-site"></a>Lanzamiento suave de un sitio

Durante un “lanzamiento suave”, un sitio web se a pone a disposición de un mercado o público limitado antes de que se produzca el lanzamiento completo. Si realiza un lanzamiento suave de su sitio web, debe pensar en dejar las etiquetas meta **noindex** en su lugar. De esta manera, ayuda a garantizar que el lanzamiento suave permanece restringido al público limitado al que desea llegar.

## <a name="a-site-that-is-in-production"></a>Un sitio que está en producción

Cuando un sitio se encuentra en producción, debe asegurarse de que todas las páginas del sitio están etiquetadas correctamente. Microsoft Dynamics 365 Commerce usa la información especificada para que una página represente toda la información de SEO en esa página. Los siguientes módulos ofrecen esta funcionalidad: resumen de páginas de categoría, resumen de páginas de lista y resumen de páginas de producto.

Para optimizar la indexación del motor de búsqueda, el marco de representación usa la información de las propiedades SEO que se configuran en Dynamics 365 Commerce y la información específica del módulo. Para un sitio que está en la producción, debe asegurarse de que el archivo robots.txt permite la indexación de su sitio completo y que contiene vínculos al documento publicado del mapa del sitio. Debe activar la funcionalidad de generación del mapa de sitio en **Valores de configuración de sitio \> Mapas del sitio habilitados**.

### <a name="page-seo-settings-for-internal-preview-limited-audiences-and-all-audiences"></a>Configuración SEO de página para vista previa interna, públicos limitados y todas las audiencias

Dado que Dynamics 365 Commerce admite vistas previas autenticadas “Lo que se ve es lo que se verá" (WYSIWYG) en el generador de páginas visual, los autores pueden preparar su contenido de páginas sin tener que preocuparse de que la información estará visible para los visitantes del sitio. Si se debe publicar una página, pero su exposición debe estar limitada, debe tener la etiqueta meta **noindex**, de modo que no se vaya a indexar por motores de búsqueda. A continuación, cuando la página está lista para todos los públicos, todos los metadatos SEO básicos deben estar presentes, para maximizar la eficacia de la indexación del motor de búsqueda. Además, se debe eliminar la etiqueta meta **nolimit**.

## <a name="additional-resources"></a>Recursos adicionales

[Administrar usuarios y roles de comercio electrónico](manage-ecommerce-users-roles.md)

[Agregar secuencia de comandos a páginas del sitio para admitir telemetría](add-telemetry.md)

[Gestionar la directiva de seguridad de contenido (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
