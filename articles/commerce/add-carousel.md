---
title: Módulo de carrusel
description: En este tema se tratan los módulos de carrusel y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 0b4ce8fdb7b598e55db59ddf5a99a0ba46eb6f91
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4986013"
---
# <a name="carousel-module"></a>Módulo de carrusel

[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de carrusel y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Un módulo de carrusel sirve para colocar artículos promocionales (incluidas imágenes enriquecidas) en un banner de carrusel giratorio que los clientes pueden explorar. Por ejemplo, un minorista puede usar un módulo de carrusel en una página principal para mostrar productos o promociones nuevas.

Puede agregar los módulos de bloque de contenido dentro de un módulo de carrusel. Las propiedades del módulo de carrusel definen a continuación cómo se representan esos módulos.

## <a name="examples-of-carousel-modules-in-e-commerce"></a>Ejemplos de módulos de carrusel en comercio electrónico

- Un carrusel que tiene dentro varios módulos promocionales se puede usar en una página principal.
- Un carrusel que tiene dentro varios módulos promocionales se puede usar en una página de detalles de producto.
- Un carrusel se puede utilizar en cualquier página de marketing para promocionar varias promociones o productos.

La siguiente imagen muestra un ejemplo de un módulo de carrusel utilizado en una página principal. Este módulo de carrusel contiene múltiples elementos de bloque de contenido.

![Ejemplo de módulo de carrusel](./media/Hero.PNG)

## <a name="carousel-module-properties"></a>Propiedades de módulo de carrusel

| Nombre de la propiedad             | Valor                 | Descripción |
|---------------------------|-----------------------|-------------|
| Reproducción automática                  | **Verdadero** o **Falso** | Si el valor está establecido en **Verdadero**, la transición entre artículos dentro de carrusel se produce automáticamente. Si el valor se establece en **Falso**, no se produce ninguna transición a menos que el cliente use el teclado o el mouse para ir de un artículo al siguiente. |
| Intervalo de transición de diapositivas | Un valor en segundos    | El intervalo para transiciones entre artículos. |
| Tipo de transacción           | **Diapositiva** o **Atenuación** | El efecto de transición entre elementos. |
| Ocultar impulsor de carrusel     | **Verdadero** o **Falso** | Si el valor se establece en **Verdadero**, la aleta del carrusel y el indicador de secuencia están ocultos. |
| Permitir descartar carrusel    | **Verdadero** o **Falso** | Si el valor se establece en **Verdadero**, los usuarios pueden descartar el carrusel. |

## <a name="add-a-carousel-module-to-a-page"></a>Agregar un módulo de carrusel a una página

Para agregar un módulo de carrusel a una página nueva y establecer las propiedades necesarias, siga estos pasos.

1. Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.
1. En el cuadro de diálogo **Nueva plantilla**, debajo de **Nombre de la plantilla**, introduzca **Plantilla de carrusel** y luego seleccione **Aceptar**.
1. En el espacio **Cuerpo**, agregue un módulo de **Página predeterminada**.
1. Seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.  
1. Use la plantilla de carrusel que acaba de crear para crear una página que se llame **página de carrusel**.
1. En el espacio **Principal** de la página nueva, agregue un módulo de contenedor. 
1. En el panel de la derecha, establezca el valor de **Ancho** para **Rellenar pantalla**.
1. En **Esquema de la página**, agregue un módulo de carrusel al módulo de contenedor.
1. Agregue un módulo de bloque de contenido al módulo de carrusel. Establezca las propiedades del módulo de bloque de contenido proporcionando **Encabezado**, **Vínculo**, **Diseño** y otras propiedades.
1. Agregue y configure otro módulo de bloque de contenido.
1. Establezca propiedades adicionales para el módulo de carrusel según corresponda.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página. La página debe mostrar un carrusel con dos módulos dentro (un módulo de elemento principal y un módulo de características). Puede cambiar las propiedades adicionales para que los módulos de carrusel, elemento principal y características logren el efecto deseado.
1. Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de banner promocional](add-alert.md)

[Módulo de bloque de texto](add-content-rich-block.md)

[Módulo de bloque de contenido](add-hero-module.md)

[Módulo de reproductor de vídeo](add-video-player.md)
