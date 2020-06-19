---
title: Módulo Contenedor
description: En este tema se tratan los módulos de contenedor y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 06/01/2020
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
ms.openlocfilehash: c7d607047aab92144932b4b59db050a588d6483d
ms.sourcegitcommit: 2683aacb426bfb3b541637edf1f8ec2d6cb5a745
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/01/2020
ms.locfileid: "3417355"
---
# <a name="container-module"></a>Módulo Contenedor

[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de contenedor y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Un módulo de contenedor es un módulo que hospeda otros módulos dentro. El propósito principal de un módulo de contenedor es definir, mediante las propiedades que se establecen para él, el diseño de los módulos que contiene. Por ejemplo, esos módulos pueden aparecer de forma paralela en un diseño de dos, tres, cuatro o seis columnas. También se pueden limitar al ancho del contenedor o bien, pueden rellenar la pantalla. También se puede agregar una encabezado a cada módulo de contenedor.

Se admiten tres módulos de contenedor: contenedor, contenedor con 2 franjas y contenedor con 3 franjas. Los módulos de cualquier tipo se pueden colocar dentro de estos contenedores. 

> [!NOTE] 
> Recomendamos que siempre coloque módulos dentro de un módulo de contenedor, de forma que se puedan limitar al ancho del contenedor.

## <a name="examples-of-container-modules-in-e-commerce"></a>Ejemplos de módulos de contenedor en comercio electrónico

- Un autor del sitio desea un diseño de tres columnas, donde aparecen tres módulos de forma paralela. Por lo tanto, el autor del sitio utiliza un módulo de contenedor del contenedor con el tipo de 3 franjas.
- Un autor del sitio desea un diseño de seis columnas, donde aparecen seis módulos de forma paralela. Por lo tanto, el autor del sitio utiliza un contenedor del tipo contenedor con seis columnas dentro.
- Un autor del sitio desea colocar un módulo en una página pero no desea que rellene la pantalla. Por lo tanto, el autor del sitio agrega el módulo a un módulo de contenedor y establece la propiedad **Ancho** del contenedor en **Ajustar contenedor**.

La siguiente imagen muestra un ejemplo de un módulo contenedor que contiene un módulo carrusel en el creador de sitios de Commerce. En este ejemplo, la propiedadel **Anchura** del módulo contenedor se establece en **Rellenar pantalla**.

![Ejemplo de módulo contenedor](./media/ecommerce-container.PNG)

## <a name="container-module-properties"></a>Propiedades de módulo de contenedor

| Nombre de la propiedad     | Valores | Descripción |
|-------------------|--------|-------------|
| Título           | Etiqueta de encabezado y texto de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Se puede proporcionar un encabezado opcional para el contenedor. De forma predeterminada, la etiqueta de encabezado **H2** se usa para el encabezado. Sin embargo, la etiqueta se puede cambiar para satisfacer los requisitos de accesibilidad. |
| Ancho             | **Ajustar contenedor** o **Rellenar pantalla** | Si el valor se establece en **Ajustar contenedor** (el valor predeterminado), los elementos que se encuentran dentro del contenedor se limitan al ancho del contenedor. Si el valor se establece en **Rellenar pantalla**, los módulos no se limitan al ancho del contenedor, pero pueden rellenar la pantalla. |
| Número de columnas | **1**, **2**, **3**, **4**, **6** o **12** | Esta propiedad define el número de columnas del contenedor. Un contenedor puede tener hasta 12 columnas. |

## <a name="container-with-2-slots"></a>Contenedor con 2 ranuras

El contenedor con el tipo de 2 franjas está optimizado para un diseño de dos columnas. Este tipo de contenedor tiene dos franjas para permitir la vista paralela de los módulos que se encuentran dentro.

Se pueden usar propiedades adicionales para optimizar el diseño de los diferentes puertos de vista (dispositivos móviles, tabletas, equipos, etc.). Para cada puerto de vista, se puede definir el ancho de cada columna. La siguiente configuración de ancho de columna está disponible:

- **75%/25%**: el primer módulo tiene un ancho de columna del 75 por ciento y el segundo módulo tiene un ancho de columna del 25 por ciento. Una opción **25%/75%** también está disponible.
- **50%/50%**: ambos módulos tienen un ancho de columna igual.
- **67%/33%**: el primer módulo tiene un ancho de columna del 67 por ciento y el segundo módulo tiene un ancho de columna del 33 por ciento. Una opción **33%/67%** también está disponible.
- **100%**: ambos módulos tienen un ancho de columna completa. Por lo tanto, los módulos se apilan verticalmente en una columna única. Aunque este diseño de columna única vaya en contra de la intención del contenedor con el tipo de 2 franjas, es posible que sea preferible para algunos puertos de vista (por ejemplo, puertos de vista muy pequeñas como dispositivos móviles).

### <a name="container-with-2-slots-properties"></a>Contenedor con propiedades de 2 franjas

| Nombre de la propiedad                   | Valores | Descripción |
|---------------------------------|--------|-------------|
| Título                         | Texto de encabezado y etiqueta de encabezado | Se puede proporcionar un encabezado opcional para el contenedor. |
| Configuración de puerto de vista muy pequeña | **25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** o **100%** | Esta propiedad define el diseño para puertos de vista muy pequeños. |
| Configuración de puerto de vista pequeña   | **25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** o **100%** | Esta propiedad define el diseño para puertos de vista pequeños, como dispositivos móviles. |
| Configuración de puerto de vista mediana  | **25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** o **100%** | Esta propiedad define el diseño para puertos de vista medianos, como tabletas. |
| Configuración de puerto de vista grande   | **25%/75%**, **75%/25%**, **50%/50%**, **67%/33%**, **33%/67%** o **100%** | Esta propiedad define el diseño para puertos de vista grandes, como equipos. |

## <a name="container-with-3-slots"></a>Contenedor con 3 ranuras

El contenedor con el tipo de módulos de 3 franjas está optimizado para un diseño de tres columnas.

Se pueden usar propiedades adicionales para optimizar el diseño de los diferentes puertos de vista. Para cada puerto de vista, se puede definir el ancho de cada columna. La siguiente configuración de ancho de columna está disponible:

- **33%/33%/33%**: los tres módulos tienen un ancho de columna igual.
- **50%/25%/25%**: el primer módulo tiene un ancho de columna del 50 por ciento y cada uno de los dos módulos restantes tiene un ancho de columna del 25 por ciento. Las opciones **25%/50%/25%** y **25%/25%/50%** también están disponibles.
- **16%/16%/67%**: cada uno de los dos primeros módulos tiene un ancho de columna del 16 por ciento y el tercer módulo tiene un ancho de columna del 67 por ciento. Las opciones **16%/67%/16%** y **67%/16%/16%** también están disponibles.

### <a name="container-with-3-slots-properties"></a>Contenedor con propiedades de 3 franjas

| Nombre de la propiedad                   | Valores | Descripción |
|---------------------------------|--------|-------------|
| Título                         | Texto de encabezado y etiqueta de encabezado | Se puede agregar un encabezado opcional al contenedor. |
| Configuración de puerto de vista muy pequeña | **33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** o **67%/16%/16%** | Esta propiedad define el diseño para puertos de vista muy pequeños. |
| Configuración de puerto de vista pequeña   | **33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** o **67%/16%/16%** | Esta propiedad define el diseño para puertos de vista pequeños, como dispositivos móviles. |
| Configuración de puerto de vista mediana  | **33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** o **67%/16%/16%** | Esta propiedad define el diseño para puertos de vista medianos, como tabletas. |
| Configuración de puerto de vista grande   | **33%/33%/33%**, **50%/25%/25%**, **25%/50%/25%**, **25%/25%/50%**, **16%/16%/67%**, **16%/67%/16%** o **67%/16%/16%** | Esta propiedad define el diseño para puertos de vista grandes, como equipos. |

## <a name="add-a-container-module-to-a-page"></a>Agregar un módulo de contenedor a una página

Para agregar un módulo de reproductor de contenedor a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.
1. En el cuadro de diálogo **Nueva plantilla**, en **Nombre de la plantilla**, introduzca **Plantilla de contenedor** y luego seleccione **Aceptar**.
1. En el espacio **Cuerpo**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Página predeterminada** y, a continuación, **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla. 
1. Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.
1. En el cuadro de diálogo **Elegir una plantilla** seleccione la plantilla del reproductor de video que creó. En **Nombre de página**, introduzca **Página de contenedor** y después seleccione **Aceptar**.
1. En el espacio **Principal** de la nueva página, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.
1. En el panel de propiedades para el módulo del contenedor, establezca la propiedad **Número de columna** en **1** y la propiedad **Ancho** en **Rellenar contenedor**.
1. En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Bloque de contenido** y, a continuación, **Aceptar**.
1. En el panel de propiedades para el módulo de bloque de contenido, configure el encabezado, la imagen y el diseño.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página. Debería ver un módulo de características que se ajuste al ancho del módulo de contenedor.
1. En el panel de propiedades para el módulo de contenedor, cambie el valor de la propiedad **Número de columnas** a **3**.
1. Agregue dos módulos de bloque de contenido más al módulo contenedor y configúrelos.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página. Debe ver ahora tres módulos de bloque de contenido que aparecen de forma paralela.
1. Una vez que haya logrado el diseño que desea, seleccione **Finalizar edición** para comprobar en la página y luego seleccione **Publicar** para publicarlo.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general del kit de inicio](starter-kit-overview.md)

[Módulo de acordeón](add-accordion.md)

[Módulo de pestañas](add-tab.md)

[Módulo de carrusel](add-carousel.md)

[Módulo de bloque de texto](add-content-rich-block.md)

[Módulo de cuadro de compra](add-buy-box.md)

[Módulo de carro](add-cart-module.md)

[Módulo de finalización de compra](add-checkout-module.md)

[Módulo de encabezado](author-header-module.md)

[Módulo de pie de página](author-footer-module.md)
