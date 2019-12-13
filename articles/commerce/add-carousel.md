---
title: Módulo de carrusel
description: En este tema se tratan los módulos de carrusel y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: c2c5adc8ab2e0330f7b07e5153fd8332ab0203e5
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785246"
---
# <a name="carousel-module"></a>Módulo de carrusel

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de carrusel y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Un módulo de carrusel se usa para colocar artículos promocionales en un carrusel que los clientes puedan explorar. Es un módulo especial de contenedor que hospeda otros módulos. Por ejemplo, un minorista puede usar un módulo de carrusel en una página principal para mostrar productos o promociones nuevas.

Puede agregar los módulos de elemento principal y características dentro de un módulo de carrusel. Las propiedades del módulo de carrusel definen a continuación cómo se representan esos módulos.

## <a name="examples-of-carousel-modules-in-e-commerce"></a>Ejemplos de módulos de carrusel en comercio electrónico

- Un carrusel que tiene dentro varios módulos promocionales se puede usar en una página principal.
- Un carrusel que tiene dentro varios módulos promocionales se puede usar en una página de detalles de producto.
- Un carrusel se puede utilizar en cualquier página de marketing para promocionar varias promociones o productos.

## <a name="carousel-module-properties"></a>Propiedades de módulo de carrusel

| Nombre de la propiedad             | Valor                                | Descripción |
|---------------------------|--------------------------------------|-------------|
| Reproducción automática                  | **Verdadero** o **Falso**                | Si el valor está establecido en **Verdadero**, la transición entre artículos dentro de carrusel se produce automáticamente. Si el valor se establece en **Falso**, no se produce ninguna transición a menos que el cliente use el teclado o el mouse para ir de un artículo al siguiente. |
| Intervalo de transición de diapositivas | Un valor en segundos                   | El intervalo para transiciones entre artículos. |
| Animación de transición      | **Diapositiva** o **Atenuación**                | El efecto de transición. |
| Ancho                     | **Ajustar contenedor** o **Rellenar pantalla** | Si el valor se establece en **Ajustar contenedor**, los elementos que se encuentran dentro del carrusel se limitan al ancho del carrusel. Si el valor se establece en **Rellenar pantalla**, los elementos no se limitan al ancho del carrusel pero pueden entrar en el modo de pantalla completa. Puede cambiar el valor para lograr el diseño deseado. |

## <a name="add-a-carousel-module-to-a-page"></a>Agregar un módulo de carrusel a una página

Para agregar un módulo de carrusel a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Cree una plantilla de página con el nombre **plantilla de carrusel**.
1. En el espacio **Principal** de la página predeterminada, agregue un módulo de carrusel.
1. Agregar un módulo de elemento principal al módulo de carrusel.
1. Agregar un módulo de características al módulo de carrusel.
1. Proteja la plantilla y publíquela. 
1. Use la plantilla de carrusel que acaba de crear para crear una página que se llame **página de carrusel**.
1. En el espacio **Principal** de la página nueva, agregue un módulo de carrusel.
1. Establezca la propiedad **Ancho** del módulo de carrusel **Rellenar pantalla**. 
1. Establezca la propiedad **Animación de transición** en **Diapositiva**.
1. Agregar un módulo de elemento principal al módulo de carrusel.
1. En el módulo de elemento principal, agregue una imagen y una encabezado y, a continuación, seleccione **Guardar**.
1. Agregar un módulo de características al módulo de carrusel.
1. En el módulo de características, agregue una imagen, un encabezado y un párrafo de texto.
1. Guarde la página y obtenga una vista previa de ella. La página debe mostrar un carrusel con dos módulos dentro (un módulo de elemento principal y un módulo de características). Puede cambiar las propiedades adicionales para que los módulos de carrusel, elemento principal y características logren el efecto deseado.
1. Proteja la página y publíquela.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo de alerta](add-alert.md)

[Módulo de bloque de enriquecimiento de contenido](add-content-rich-block.md)

[Módulo de sustitución de contenido](add-content-placement-modules.md)

[Módulo de característica](add-feature-module.md)

[Módulo de elemento principal](add-hero-module.md)

[Módulo de reproductor de vídeo](add-video-player.md)
