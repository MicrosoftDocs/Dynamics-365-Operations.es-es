---
title: Información general del tema de Adventure Works
description: Este tema ofrece una descripción general del tema de Adventure Works y describe cómo aplicarlo a las páginas del sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 12/03/2021
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 34ea24e2d81a69d720973455492f9e05ed34dd81
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2022
ms.locfileid: "7983703"
---
# <a name="adventure-works-theme-overview"></a>Información general del tema de Adventure Works

[!include [banner](includes/banner.md)]

Este tema ofrece una descripción general del tema de Adventure Works y describe cómo aplicarlo a las páginas del sitio en Microsoft Dynamics 365 Commerce.

Dynamics 365 Commerce tiene un tema para el comercio electrónico que se llama Adventure Works. El tema Adventure Works muestra productos deportivos y recreativos, y está optimizado para una experiencia narrativa rica y mejorada. Proporciona una apariencia moderna, nuevos diseños y efectos de animación para crear una experiencia de compra en línea envolvente y atractiva para los clientes de comercio electrónico.

## <a name="trial-environments-in-commerce"></a>Entornos de prueba en Commerce

Para ver cómo se ve el tema Adventure Works cuando se implementa para sitios de empresa a consumidor (B2C) y de empresa a empresa (B2B), visite los siguientes sitios de prueba:

- [Sitio B2C de Adventure Works](https://www.adventure-works.com/)
- [Sitio B2B de Adventure Works](https://www.adventure-works.com/business)

## <a name="theme-capabilities"></a>Funcionalidades de tema

El tema Adventure Works proporciona las siguientes nuevas funcionalidades:

- El módulo de reproductor de video ahora admite la funcionalidad de encabezados, párrafos y enlaces para contar historias adicionales.
- Hay mejores transiciones de contenido a través de la animación.
- La acción de "agregar al carrito" invoca el mini carrito en lugar de proporcionar una notificación.
- El módulo de vista rápida es un panel que se desliza en las ventanas gráficas de escritorio y móviles.
- Hay nuevos diseños para las páginas del sitio. 
- El contenido de marketing se puede configurar para el carrito y el mini carrito cuando están vacíos.
- El mini carrito puede mostrar mensajes promocionales, como "Envío gratuito en pedidos superiores a 50 $".
- Las tarjetas de descripción se representan en las páginas de búsqueda y categoría.

El tema Adventure Works ahora incluye los siguientes módulos de narración de historias en la biblioteca de módulos de Commerce:

- [Módulo de lista de iconos](tile-list-module.md)
- [Módulo de funciones interactivas](interactive-feature-module.md)
- [Módulo de imagen activa](active-image-module.md)
- [Módulo de suscripción](subscribe-module.md)
- [Módulo de lista de imágenes](image-list-module.md)

El tema Adventure Works es totalmente receptivo y proporciona una experiencia optimizada para las ventanas gráficas de escritorio, dispositivos móviles y tabletas.

> [!IMPORTANT]
> El tema de Adventure Works y los nuevos módulos están disponibles a partir del lanzamiento de la versión 10.0.20 de Dynamics 365 Commerce.

La siguiente ilustración muestra un ejemplo de una página de inicio que usa el tema Adventure Works.

![Ejemplo de una página de inicio que usa el tema Adventure Works](./media/aw_b2c.PNG)

La siguiente ilustración muestra un ejemplo de una página de lista que usa el tema Adventure Works.

![Ejemplo de una página de lista que usa el tema Adventure Works](./media/Aw_list.PNG)

La siguiente ilustración muestra un ejemplo de una página de detalles de producto (PDP) que usa el tema Adventure Works.

![Ejemplo de una página de detalles de producto (PDP) que usa el tema Adventure Works](./media/aw_pdp.PNG)

## <a name="use-the-adventure-works-theme-for-b2b-sites"></a>Utilice el tema Adventure Works para sitios B2B

El tema de Adventure Works también es un tema de referencia para los sitios de empresa a empresa (B2B). Todos los módulos y flujos de trabajo B2B se muestran en el tema Adventure Works. Para obtener información sobre cómo configurar un sitio B2B, consulte [Configuración de sitios B2B](./b2b/set-up-b2b-site.md).

La siguiente ilustración muestra un ejemplo de una página de inicio B2B que usa el tema Adventure Works.

![Ejemplo de una página de inicio B2B que usa el tema Adventure Works](./media/aw_b2b.PNG)

## <a name="theme-extensions"></a>Extensiones de tema

El tema de Adventure Works incluye varias extensiones de tema, como las extensiones **Ver extensiones** y **Definición de módulo**. El tema Adventure Works se puede utilizar como tema de referencia para crear extensiones similares. Por ejemplo, la página de lista en el tema Adventure Works se implementa como una extensión de vista que tiene un refinador horizontal. (Por el contrario, se utiliza un refinador de panel izquierdo en el tema Fabrikam).

Asimismo, otros módulos incluyen extensiones de definición de módulo. Por ejemplo, el [módulo de icono de carrito](cart-icon-module.md) incluye dos ranuras adicionales **Carro vacio** y **Contenido promocional** que se implementan mediante extensiones de definición de módulo. Además, una nueva propiedad **Logotipo móvil** se ha agregado al módulo de encabezado para admitir un logotipo en las ventanas gráficas móviles. Esta propiedad se implementa como una extensión de la definición del módulo de encabezado.

Para obtener más información sobre las extensiones de tema, consulte [Extensiones de tema](e-commerce-extensibility/theme-module-extensions.md).

## <a name="install-the-adventure-works-theme"></a>Instalar el tema de Adventure Works

Para obtener información sobre cómo instalar el tema Adventure Works, consulte [Instalar el tema de Adventure Works](install-adventure-works.md).

## <a name="additional-resources"></a>Recursos adicionales

[Descripción general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de lista de iconos](tile-list-module.md)

[Módulo de funciones interactivas](interactive-feature-module.md)

[Módulo de imagen activa](active-image-module.md)

[Módulo de suscripción](subscribe-module.md)

[Módulo de lista de imágenes](image-list-module.md)

[Extensiones de tema](e-commerce-extensibility/theme-module-extensions.md)

[Módulo de icono de carro](cart-icon-module.md)

[Configurar un sitio de comercio electrónico B2B](./b2b/set-up-b2b-site.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
