---
title: Módulo de banner promocional
description: En este tema se tratan los módulos de banner promocional y se describe la forma de agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 04/14/2020
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
ms.openlocfilehash: 12cabbf0b8d9f337f15a8cd6cb1f2a85100b75f7
ms.sourcegitcommit: 7a1d01122790b904e2d96a7ea9f1d003392358a6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/17/2020
ms.locfileid: "3269783"
---
# <a name="promo-banner-module"></a>Módulo de banner promocional


[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de banner promocional y se describe la forma de agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Los módulos de banner promocional se usan para mostrar mensajes informativos en línea en una página. Se pueden utilizar para mostrar las promociones en todo el sitio que aparecen en todas las páginas de un sitio de comercio electrónico. 

Los módulos de banner promocional admiten un mensaje de texto y un vínculo. Si se agregan varios mensajes a un módulo de banner promocional, se convierte en un banner de carrusel giratorio que permite a los clientes ver todos los mensajes. 

Los módulos de banner promocional se controlan con datos desde el sistema de gestión de contenidos (CMS) y se pueden colocar en cualquier página.

## <a name="usage-examples-of-promo-banners-in-e-commerce"></a>Ejemplos de uso de banners promocionales en comercio electrónico

Los banners promocionales se pueden usar en el encabezado del sitio para mostrar promociones o mensajes en todo el sitio, como en los siguientes ejemplos.

“La venta anual finaliza en 10 días”

“Ahorre a lo grande con la oferta de la vuelta al cole. Compre ahora."

## <a name="promo-banner-module-properties"></a>Propiedades del módulo de banner promocional

| Nombre de la propiedad             | Valor                              | Descripción |
|---------------------------|------------------------------------|-------------|
| Mensajes de banner           | Texto y vínculos                     | Una gran variedad de texto y vínculos. |
| Reproducción automática                  | **Verdadero** o **Falso**              | Un valor que indica si los mensajes se muestran cíclicamente de manera automática, si se han configurado varios mensajes. |
| Intervalo de transición de diapositivas | Un número de milisegundos (ms)      | El intervalo que se usa para recorrer los mensajes. |
| Permitir descartar             | **Verdadero** o **Falso**              | Si el valor se establece en **Verdadero**, los clientes pueden descartar la alerta. |
| Mostrar aleta de carrusel     | **Verdadero** o **Falso**              | Un valor que indica si se deben mostrar las aletas del carrusel para que los clientes puedan desplazarse manualmente por varios elementos del banner. |
| Alineación de texto            | **Derecha**, **Izquierda** o **Centro** | La alineación del texto en el módulo de banner promocional. |
| Vincular                      | Una dirección URL                              | La dirección URL para un vínculo opcional. |

## <a name="add-a-promo-banner-module-to-a-page"></a>Agregar un módulo de banner promocional a una página 

Para agregar un módulo banner promocional a una página y establecer las propiedades necesarias, siga estos pasos.

1. Seleccione **Nuevo** para crear una plantilla de página.
1. En el cuadro de diálogo **Nueva plantilla**, debajo de **Nombre de la plantilla**, ingrese **Plantilla de banner promocional** y luego seleccione **Aceptar**.
1. En **Esquema de la página**, agregue un módulo de **Página predeterminada** a la franja **Cuerpo**. 
1. Seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla. 
1. Use la plantilla que acaba de crear para crear una página que se llame **Página de banner promocional**. 
1. En el espacio **Principal** de la página nueva, agregue un módulo de contenedor. 
1. En el panel de la derecha, establezca el valor de **Ancho** en **Rellenar contenedor**.
1. En **Esquema de la página**, agregue un módulo de banner promocional al módulo de contenedor.
1. En la configuración del módulo de banner, agregue uno o más mensajes de banner. Cada mensaje puede tener texto junto con un vínculo. Puede editar las otras propiedades para personalizar más el módulo.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página. En la parte superior de la página, debe ver una alerta que muestra el texto que ha agregado.
1. Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla. 

> [!NOTE]
> Un banner promocional se usa generalmente en la franja de encabezado de página o en una franja de subtítulo.


## <a name="additional-resources"></a>Recursos adicionales

[Visión general de kit de inicio](starter-kit-overview.md)

[Módulo de carrusel](add-carousel.md)

[Módulo de bloque de texto](add-content-rich-block.md)

[Módulo de bloque de contenido](add-hero-module.md)

[Módulo de reproductor de vídeo](add-video-player.md)
