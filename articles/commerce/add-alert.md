---
title: Módulo de alerta
description: En este tema se tratan los módulos de alerta y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 82138dd7f0934f732215f67a3726638eb87075d4
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785361"
---
# <a name="alert-module"></a>Módulo de alerta

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de alerta y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Un módulo de alerta se usa para mostrar mensajes informativos en línea en una página. Los módulos alertas admiten un mensaje de texto y un vínculo. Se pueden utilizar para mostrar las promociones en todo el sitio que aparecen en todas las páginas de un sitio de comercio electrónico. 

Los módulos de alerta se controlan por datos desde el sistema de gestión de contenidos (CMS) y se pueden colocar en cualquier página.

## <a name="examples-of-alert-modules-in-e-commerce"></a>Ejemplos de módulos de alerta en comercio electrónico

Los módulos de alerta se pueden usar en el encabezado del sitio para indicar promociones o mensajes en todo el sitio. A continuación se incluyen algunos ejemplos:

“La venta anual finaliza en 10 días”

“Ahorre a lo grande con la oferta de la vuelta al cole. Compre ahora."

## <a name="alert-module-properties"></a>Propiedades del módulo de alerta

| Nombre de la propiedad  | Valor                              | Descripción |
|----------------|------------------------------------|-------------|
| Texto           | Texto                               | El mensaje de texto que aparece en el módulo de alerta. |
| Alineación de texto | **Derecha**, **Izquierda** o **Centro** | Valor que define la manera en que el texto se alinea en el módulo de alerta. |
| Descartar alerta  | **Verdadero** o **Falso**              | Si el valor se establece en **Verdadero**, el cliente puede descartar la alerta. |
| Vincular           | URL                                | La dirección URL para un vínculo opcional. |

## <a name="add-an-alert-module-to-a-page"></a>Agregar un módulo de alerta a una página 

Para agregar un módulo de alerta a una página y establecer las propiedades necesarias, siga estos pasos.

1. Cree una plantilla de página con el nombre **plantilla de alerta**.
1. En el espacio **Principal** de la página predeterminada, agregue un módulo de alerta.
1. Proteja la plantilla y publíquela. 
1. Use la plantilla de alerta que acaba de crear para crear una página que se llame **página de alerta**. 
1. En el espacio **Principal** de la página nueva, agregue un módulo de alerta.
1. En la configuración para el módulo de alerta, escriba el texto de la alerta. Puede editar las otras propiedades si desea personalizar más el módulo de alerta.
1. Guarde la página y obtenga una vista previa de ella. En la parte superior de la página, debe ver una alerta que tenga el texto que ha agregado.
1. Proteja la página y publíquela. 

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo de carrusel](add-carousel.md)

[Módulo de bloque de enriquecimiento de contenido](add-content-rich-block.md)

[Módulo de sustitución de contenido](add-content-placement-modules.md)

[Módulo de característica](add-feature-module.md)

[Módulo de elemento principal](add-hero-module.md)

[Módulo de reproductor de vídeo](add-video-player.md)
