---
title: Módulo de bloque de enriquecimiento de contenido
description: En este tema se tratan los módulos de bloque de enriquecimiento de contenido y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 10/31/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 27dabb425b3c9a3015ffc54ff3c0e50b7ee11749
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785430"
---
# <a name="content-rich-block-module"></a>Módulo de bloque de enriquecimiento de contenido

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de bloque de enriquecimiento de contenido y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Un módulo de bloque de enriquecimiento de contenido es un contenedor especial en el que se pueden colocar uno o más elementos de módulo de bloque de enriquecimiento de contenido. Los módulos de bloque de enriquecimiento de contenido se utilizan para contenido textual en una página. Este contenido puede ser informativo o promocional.

Los módulos de bloque de enriquecimiento de contenido se controlan por datos desde el sistema de gestión de contenidos (CMS) y se pueden colocar en cualquier página. Son módulos independientes que no dependen del contexto de página o de cualquier otro módulo.

## <a name="examples-of-content-rich-block-modules-in-e-commerce"></a>Ejemplos de módulos de bloque de enriquecimiento de contenido en comercio electrónico

Los módulos de bloque de enriquecimiento de contenido se pueden utilizar de las siguientes maneras:

* Para mostrar características de producto en una página de detalles de productos.
* Para finalidad informativa en cualquier página. Por ejemplo, pueden explicar los beneficios de programas de fidelización, describir las directivas de envío y devolución, responder a preguntas más frecuentes o proporcionar contenido de “acerca de nosotros”.
* Para agregar mensajes personalizados en una página de detalles de productos. (por ejemplo, “Envío gratuito para pedidos superiores a 50 €").
* Para declinaciones de responsabilidad y detalles de contacto sobre páginas de detalles de productos, páginas de finalización de compra y otras páginas (por ejemplo, "Los envíos y las directivas están sujetos a las directivas de la tienda”).

## <a name="content-rich-block-module-properties"></a>Propiedades del módulo de bloque de enriquecimiento de contenido

| Nombre de la propiedad     | Valor                                 | Propiedad |
|-------------------|---------------------------------------|----------|
| Número de columnas | Un número del **1** al **4**     | Número de columnas de un bloque de enriquecimiento de contenido. Puede haber hasta cuatro columnas. |
| Ancho             | **Rellenar contenedor** o **Rellenar pantalla** | Si el valor se establece en **Rellenar contenedor**, los elementos que se encuentran dentro del contenedor se limitan al ancho del contenedor. Si el valor se establece en **Rellenar pantalla**, los elementos no se limitan al ancho del contenedor, pero pueden entrar en el modo de pantalla completa. Puede cambiar el valor para lograr el diseño deseado. |

## <a name="content-rich-block-item-module-properties"></a>Propiedades del módulo de elemento de bloque de enriquecimiento de contenido

| Nombre de la propiedad | Valor          | Descripción |
|---------------|----------------|-------------|
| Párrafo     | Texto de párrafo | El texto que acompaña a cada elemento de bloque de enriquecimiento de contenido. Se admiten algunas capacidades básicas de texto enriquecido, como negrita, subrayado y cursiva. |

## <a name="add-a-content-rich-block-module-to-a-page"></a>Agregar un módulo de bloque de enriquecimiento de contenido a una página

Para agregar un módulo de bloque de enriquecimiento de contenido a una nueva página y establecer las propiedades necesarias, siga estos pasos.

1. Cree una plantilla de página con el nombre **Plantilla de contenido**.
1. En el espacio **Principal** de la página predeterminada, agregue un módulo de bloque de enriquecimiento de contenido.
1. Proteja la plantilla y publíquela.
1. Use la plantilla de contenido que acaba de crear para crear una página que se llame **Página de contenido**.
1. En el espacio **Principal** de la nueva página, agregue un módulo de bloque de enriquecimiento de contenido.
1. En las propiedades del módulo de bloque de enriquecimiento de contenido, establezca el número de columnas en **2**.
1. En el módulo de bloque de enriquecimiento de contenido, seleccione **Agregar un módulo** y agregue un elemento de bloque de enriquecimiento de contenido (por ejemplo, **elemento1**).
1. En el nuevo elemento de bloque de enriquecimiento de contenido, agregue el texto del párrafo.
1. En el módulo de bloque de enriquecimiento de contenido, seleccione **Agregar un módulo** y agregue un elemento de bloque de enriquecimiento de contenido (por ejemplo, **elemento2**).
1. En el nuevo elemento de bloque de enriquecimiento de contenido, agregue el texto del párrafo.
1. Guarde la página y obtenga una vista previa de los cambios. Debería ver dos bloques de texto enriquecido en una vista de dos columnas.
1. Proteja la página y publíquela.

> [!NOTE]
> Si agrega un tercer elemento de bloque de enriquecimiento de contenido, se apilará debajo de los dos elementos que había agregado anteriormente. Al cambiar el número de columnas y elementos en el contenedor, podrá lograr diferentes diseños para el contenido textual.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo de alerta](add-alert.md)

[Módulo de carrusel](add-carousel.md)

[Módulo de colocación de contenido](add-content-placement-modules.md)

[Módulo de característica](add-feature-module.md)

[Módulo de elemento principal](add-hero-module.md)

[Módulo de reproductor de vídeo](add-video-player.md)

