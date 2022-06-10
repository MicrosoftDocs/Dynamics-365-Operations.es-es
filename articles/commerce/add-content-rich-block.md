---
title: Módulo de bloque de texto
description: En este tema se tratan los módulos de bloque de texto y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 18a4226d3b8dce1b46e6612521d70a3627b517d1
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780498"
---
# <a name="text-block-module"></a>Módulo de bloque de texto

[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de bloque de texto y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

Un módulo de bloque de texto es un módulo que se utiliza para agregar contenido textual. Este contenido puede ser informativo o promocional.

Los módulos de bloque de texto se controlan con datos desde el sistema de gestión de contenidos (CMS) y se pueden colocar en cualquier página. Son módulos independientes que no dependen del contexto de página o de cualquier otro módulo.

## <a name="examples-of-text-block-modules-in-e-commerce"></a>Ejemplos de módulos de bloque de texto en comercio electrónico

Los módulos de bloque de texto se pueden utilizar de las siguientes maneras:

* Para mostrar características de producto en una página de detalles de productos.
* Para finalidad informativa en cualquier página. Por ejemplo, pueden explicar los beneficios de programas de fidelización, describir las directivas de envío y devolución, responder a preguntas más frecuentes o proporcionar contenido de “acerca de nosotros”.
* Para agregar mensajes personalizados en una página de detalles de productos. (por ejemplo, “Envío gratuito para pedidos superiores a 50 €").
* Para declinaciones de responsabilidad y detalles de contacto sobre páginas de detalles de productos, páginas de finalización de compra y otras páginas (por ejemplo, "Los envíos y las directivas están sujetos a las directivas de la tienda”).

La siguiente imagen muestra un ejemplo de un módulo de bloque de texto utilizado en una página principal.

![Ejemplo de un módulo de bloque de texto.](./media/ecommerce-textblock.PNG)

## <a name="text-block-module-properties"></a>Propiedades de módulo de bloque de texto

| Nombre de la propiedad     | Valor                                            | Descripción |
|-------------------|--------------------------------------------------|-------------|
| Texto enriquecido         | Texto enriquecido                                        | Texto de párrafo. Se admiten algunas capacidades básicas de texto enriquecido, como negrita, subrayado y cursiva. |
| Nombre de clase personalizada | Un nombre de clase de hojas de estilo en cascada (CSS)        | El nombre de una clase CSS personalizada que un desarrollador proporciona para aplicar formato a este módulo. El nombre de la clase debe definirse en el paquete de temas. |
| Tamaño de fuente         | **Pequeño**, **Mediano**, **Grande** o **Extragrande** | El tamaño de fuente del contenido. |

## <a name="add-a-text-block-module-to-a-page"></a>Agregar un módulo de bloque de texto a una página

Para agregar un módulo de bloque de texto a una nueva página y establecer las propiedades necesarias, siga estos pasos.

1. Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.
1. En el cuadro de diálogo **Nueva plantilla**, en **Nombre de plantilla**, introduzca **Plantilla de contenido**.
1. En el espacio **Cuerpo**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Página predeterminada** y, a continuación, **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.
1. Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.
1. En el cuadro de diálogo **Crear nueva página**, en **Nombre de página**, introduzca una **Página de contenido** y luego seleccione **Siguiente**.
1. En **Elegir plantilla**, seleccione **Plantilla de contenido** y luego seleccione **Siguiente**.
1. En **Elija un diseño**, seleccione un diseño de página (por ejemplo, **Diseño flexible**), y luego seleccione **Siguiente**.
1. En **Revisar y terminar**, revise la configuración de la página. Si necesita editar la información de la página, seleccione **Atrás**. Si la información de la página es correcta, seleccione **Crear página**. 
1. En el espacio **Principal** de la nueva página, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.
1. En el panel de propiedades para el módulo de contenedor, establezca la propiedad **Ancho** en **Rellenar contenedor**.
1. En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Bloque de texto** y, a continuación, **Aceptar**. 
1. En el panel de propiedades del módulo de bloque de texto, agregue texto al campo **Texto enriquecido**.
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.
1. Seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la biblioteca de módulos](starter-kit-overview.md)

[Módulo de banner promocional](add-alert.md)

[Módulo de carrusel](add-carousel.md)

[Módulo de bloque de contenido](add-hero-module.md)

[Módulo de reproductor de vídeo](add-video-player.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
