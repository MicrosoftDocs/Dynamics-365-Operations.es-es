---
title: Módulo de colocación de contenido
description: En este tema se tratan los módulos de colocación de contenido y de elementos de colocación de contenido, y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 1b64e930628c969334ff6e643ba23b77445e6e4c
ms.sourcegitcommit: 3a4e137ef3a96ba0a58c5352f4a3b57467ace9ae
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2019
ms.locfileid: "2785309"
---
# <a name="content-placement-module"></a>Módulo de colocación de contenido

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de colocación de contenido y de elementos de colocación de contenido, y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Un módulo de colocación de contenido es un contenedor especial en el que otros módulos se pueden colocar dentro en un diseño específico. Los módulos de colocación de contenido admiten los siguientes tipos de módulos como módulos secundarios: elemento de colocación de contenido, elemento de bienvenida de cuenta, elemento de pedido de cuenta, elemento de lista de deseos de cuenta y elemento de perfil de cuenta.

Los módulos de colocación de contenido obtienen datos de los módulos secundarios que admiten. Por lo tanto, los módulos de colocación de contenido se pueden usar de diversas maneras, en función de los módulos que se agregan.

Los módulos de elementos de colocación de contenido usan tanto imágenes como texto para mostrar promociones, directivas y características de producto. Por ejemplo, un módulo de elementos de colocación de contenido se puede usar en una página principal para mostrar directivas de la tienda o información de envío. Los módulos de elementos de colocación de contenido se controlan por datos desde el sistema de gestión de contenidos (CMS) y se pueden colocar en cualquier página. Sin embargo, solo se pueden usar dentro de un módulo de colocación de contenido.

## <a name="examples-of-content-placement-modules-in-e-commerce"></a>Ejemplos de módulos de colocación de contenido en comercio electrónico

* Los módulos de colocación de contenido que contienen módulos de elementos de colocación de contenido se pueden usar en una página principal o en páginas de marketing para mostrar características de productos, promociones, directivas de tienda, información de envío y otra información a través tanto de ambas imágenes como de texto.
* Los módulos de colocación de contenido que contienen módulos de elementos de colocación de contenido se pueden usar en páginas de detalles de productos para mostrar características de productos.
* Los módulos de colocación de contenido que contienen módulos de elementos de pedido de cuenta o elementos de bienvenida de cuenta se pueden usar en páginas de administración de cuentas.

## <a name="content-placement-module-properties"></a>Propiedades de módulo de colocación de contenido

| Nombre de la propiedad | Valor | Descripción |
|---------------|-------|-------------|
| Ancho         | **Ajustar contenedor** o **Rellenar pantalla** | Si el valor se establece en **Ajustar contenedor**, los elementos que se encuentran dentro del módulo de colocación de contenido se limitan al ancho del módulo de colocación de contenido. Si el valor se establece en **Rellenar pantalla**, los elementos no se limitan al ancho del módulo de colocación de contenido, sino que puede entrar en el modo de pantalla completa. |

## <a name="content-placement-item-module-properties"></a>Propiedades de módulo de elementos de colocación de contenido

| Nombre de la propiedad | Valor | Descripción |
|---------------|-------|-------------|
| Título       | Etiquetas de encabezado y texto de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Cada módulo de elementos de colocación de contenido puede tener un encabezado. La propiedad **Encabezado** admite etiquetas de encabezado. De manera predeterminada, se usa la etiqueta de encabezado **H2**, pero la etiqueta de encabezado se puede cambiar para cumplir los requisitos de accesibilidad. |
| Párrafo     | Texto de párrafo | Los módulos de elementos de colocación de contenido admiten texto de párrafo en formato de texto enriquecido. Se admiten algunas capacidades básicas de texto enriquecido, como negrita, subrayado y cursiva, además de hipervínculos. Algunas de estas capacidades se pueden anular por el tema de página que se aplica al módulo. |
| Imagen         | Archivo de imagen | Una imagen se puede asociar al texto. |
| Vincular          | Dirección URL de vínculo y texto de vínculo | Un vínculo se puede agregar al texto para redirigir a los usuarios a una página específica. |
| Tamaño de icono     | Un número del **1** al **12** | Para cada elemento de colocación de contenido, esta propiedad define el número de espacios que el elemento debe rellenar en el módulo de colocación de contenido. El tamaño máximo del módulo de colocación de contenido es 12 espacios. Si el tamaño de icono total para los primeros *n* elementos del módulo de colocación de contenido supera las 12 espacios, los artículos se ajustan a la fila siguiente. |

## <a name="add-a-content-placement-module-that-contains-a-content-placement-item-module-to-a-page"></a>Agregar un módulo de colocación de contenido que contenga un módulo de colocación de contenido a una página

Para agregar un módulo de colocación de contenido que contenga un módulo de elementos de colocación de contenido a una página nueva y establecer las propiedades requeridas, siga estos pasos.

1. Cree una plantilla con el nombre **plantilla de colocación de contenido**.
1. En el espacio **Principal** de la página predeterminada, agregue un módulo de colocación de contenido.
1. En el módulo de colocación de contenido, agregue un módulo de elementos de colocación de contenido.
1. Proteja la plantilla y publíquela.
1. Use la plantilla de colocación de contenido que acaba de crear para crear una página que se llame **Página de colocación de contenido**.
1. En el espacio **Principal** de la página nueva, agregue un módulo de colocación de contenido.
1. En el módulo de colocación de contenido, agregue un módulo de elementos de colocación de contenido.
1. En el panel de propiedad del módulo de elementos de colocación de contenido, seleccione una imagen, agregue un encabezado, agregue un párrafo, agregue un vínculo, establezca la dirección URL del vínculo y establezca el tamaño del icono en **6**.
1. Repita los pasos 7 y 8 para agregar otro módulo de elementos de colocación de contenido que tenga el mismo tamaño de icono.
1. Guarde la página y obtenga una vista previa de ella. Solo debería ver dos elementos de colocación de contenido que aparezcan uno junto al otro. Puede ajustar la propiedad **Tamaño de icono** de cada módulo de elementos de colocación de contenido y agregar más módulos para lograr el diseño que desee.
1. Proteja la página y publíquela.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo de alerta](add-alert.md)

[Módulo de carrusel](add-carousel.md)

[Módulo de bloque de enriquecimiento de contenido](add-content-rich-block.md)

[Módulo de característica](add-feature-module.md)

[Módulo de elemento principal](add-hero-module.md)

[Módulo de reproductor de vídeo](add-video-player.md)
