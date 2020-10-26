---
title: Consideraciones de optimización de motor de búsqueda (SEO) para su sitio
description: Este tema trata las consideraciones de la optimización de motor de búsqueda (SEO) para su sitio desde el desarrollo hasta la producción.
author: psimolin
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 6ffc772addb330abe7205007662a3f3e08a3e47f
ms.sourcegitcommit: f16db76c1c235dfa445b50614bcee9219782d6dc
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/05/2020
ms.locfileid: "3961595"
---
# <a name="search-engine-optimization-seo-considerations-for-your-site"></a>Consideraciones de optimización de motor de búsqueda (SEO) para su sitio


[!include [banner](includes/banner.md)]

Este tema trata las consideraciones de la optimización de motor de búsqueda (SEO) para su sitio desde el desarrollo hasta la producción.

## <a name="a-site-that-is-under-development"></a>Un sitio que se encuentra en desarrollo

Aunque un sitio esté en desarrollo, todas las páginas del sitio deben tener las etiquetas META **NOINDEX** y **NOFOLLOW**, de modo que los motores de búsqueda no indicen las páginas y las versiones de desarrollo de tienda de su sitio en su memoria caché. Para realizar esta configuración, debe agregar el módulo predeterminado de etiquetas META a la plantilla de página del sitio. Las propiedades de etiquetas META predeterminadas estarán entonces disponibles en la sección de propiedades SEO del editor de páginas. Puede usar estas propiedades para administrar las etiquetas META.

## <a name="soft-launch-of-a-site"></a>Lanzamiento suave de un sitio

Durante un “lanzamiento suave”, un sitio web se a pone a disposición de un mercado o público limitado antes de que se produzca el lanzamiento completo. Si realiza un lanzamiento suave de su sitio web, debe pensar en dejar las etiquetas META **NOINDEX** en su lugar. De esta manera, ayuda a garantizar que el lanzamiento suave permanece restringido al público limitado al que desea llegar.

## <a name="a-site-that-is-in-production"></a>Un sitio que está en producción

Cuando un sitio se encuentra en producción, debe asegurarse de que todas las páginas del sitio están etiquetadas correctamente. Microsoft Dynamics 365 Commerce usa la información especificada para que una página represente toda la información de SEO en esa página. Los siguientes módulos ofrecen esta funcionalidad: resumen de páginas de categoría, resumen de páginas de lista y resumen de páginas de producto.

Para optimizar la indexación del motor de búsqueda, el marco de representación usa la información de las propiedades SEO que se configuran en Dynamics 365 Commerce y la información específica del módulo. Para un sitio que está en la producción, debe asegurarse de que el archivo robots.txt permite la indexación de su sitio completo y que contiene vínculos al documento publicado del mapa del sitio. Debe activar la funcionalidad de generación del mapa de sitio en **Valores de configuración de sitio \> Mapas del sitio habilitados**.

### <a name="page-seo-settings-for-internal-preview-limited-audiences-and-all-audiences"></a>Configuración SEO de página para vista previa interna, públicos limitados y todas las audiencias

Dado que Dynamics 365 Commerce admite vistas previas autenticadas “Lo que se ve es lo que se verá" (WYSIWYG) en el generador de páginas visual, los autores pueden preparar su contenido de páginas sin tener que preocuparse de que la información estará visible para los visitantes del sitio. Si se debe publicar una página, pero su exposición debe estar limitada, debe tener la etiqueta META **NOINDEX**, de modo que no se vaya a indexar por motores de búsqueda. A continuación, cuando la página está lista para todos los públicos, todos los metadatos SEO básicos deben estar presentes, para maximizar la eficacia de la indexación del motor de búsqueda. Además, se debe eliminar la etiqueta META **NOLIMIT**.

## <a name="additional-resources"></a>Recursos adicionales

[Administrar usuarios y roles de comercio electrónico](manage-ecommerce-users-roles.md)

[Agregar secuencia de comandos a páginas del sitio para admitir telemetría](add-telemetry.md)

[Gestionar la directiva de seguridad de contenido (CSP)](manage-csp.md)
