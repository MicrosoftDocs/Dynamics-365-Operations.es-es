---
title: Módulo de iframe
description: En este tema se trata el modulo de iframe y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: eeb9d76367be6b2d2153578f6358594b807382ac
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780243"
---
# <a name="iframe-module"></a>Módulo de iFrame

[!include [banner](includes/banner.md)]

En este tema se trata el modulo de iframe y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.

Un módulo de iframe proporciona un iframe (marco en línea) que aloja contenido externo en un sitio. Por ejemplo, se puede usar para alojar un vídeo YouTube o un visor de archivos PDF en cualquier página del sitio. 

Un módulo de iframe requiere una URL de destino. Luego aloja el contenido de la página de destino dentro de un elemento **iframe** de HTML. Las URL externas deben estar en la lista de permitidos según las directivas de política de seguridad de contenido (CSP) del sitio. Para el contenido de iframe, las URL deben permitirse mediante el uso de la directiva **antepasado del marco**. Para más información, consulte [Administrar la Directiva de seguridad de contenido (CSP)](manage-csp.md).

> [!NOTE]
> El módulo iframe está disponible en la versión Dynamics 365 Commerce 10.0.13.

La siguiente imagen muestra ejemplos de módulos de iframe que muestran videos externos en las páginas del sitio.

![Ejemplo de módulos de iframe que muestran vídeos externos.](./media/ecommerce-iframe.PNG)

## <a name="iframe-module-properties"></a>Propiedades de módulo de iframe

| Nombre de la propiedad             | Valor                 | Descripción |
|---------------------------|-----------------------|-------------|
| Cabecera | Texto | El encabezado del módulo. |
| Dirección URL de destino | Dirección URL | La URL que está alojada en el módulo. |
| Alto | Número o porcentaje | La altura del módulo, en píxeles o como porcentaje. Por ejemplo, el valor **100** se tratará como una cantidad de píxeles y el valor **100 %** se tratará como un porcentaje. |
| Etiqueta Aria | Texto | Se puede definir una etiqueta de aplicaciones de Internet accesibles enriquecidas (ARIA) para fines de accesibilidad. |

## <a name="add-an-iframe-module-to-a-page"></a>Agregar un módulo de iframe a una página

Para agregar un módulo de iframe a una página para mostrar un vídeo externo, siga estos pasos.

1. Vaya a **Plantillas** y luego seleccione **Nuevo** para crear una nueva plantilla.
1. En el cuadro de diálogo **Nueva plantilla**, en **Nombre de la plantilla**, introduzca **Plantilla de marketing** y luego seleccione **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.
1. Vaya a **Páginas** y seleccione **Nuevo** para crear una nueva página.
1. En el cuadro de diálogo **Crear nueva página**, en **Nombre de página**, introduzca **Página de marketing** y luego seleccione **Siguiente**.
1. En **Elegir plantilla**, seleccione la **Plantilla de marketing** que creó y, a continuación, seleccione **Siguiente**.
1. En **Elija un diseño**, seleccione un diseño de página (por ejemplo, **Diseño flexible**), y luego seleccione **Siguiente**.
1. En **Revisar y terminar**, revise la configuración de la página. Si necesita editar la información de la página, seleccione **Atrás**. Si la información de la página es correcta, seleccione **Crear página**. 
1. En el espacio **Principal** de la nueva página, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo, establezca el valor **Ancho** para **Llenar contenedor**.
1. En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **iframe** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo, establezca el valor **URL de destino** a una URL externa para un vídeo.
1. Establecer otras propiedades, como **Bóveda** y **Altura**, como lo requiera.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.
1. Vaya a la página de marketing en su sitio. Debería ver que el vídeo se representa en el módulo de iframe.

> [!NOTE]
> Debido a que el módulo de iframe hospeda contenido externo, los autores del sitio deben asegurarse de que el contenido hospedado en un módulo de iframe no infrinja las directivas de restricción de contenido en el mercado respectivo. Si hay una infracción de contenido en una página que utiliza el módulo de iframe, el autor del sitio puede eliminar el módulo de iframe abriendo la página en el creador del sitio y seleccionando **Quitar módulo** en la ranura del módulo de iframe y luego guardar y volver a publicar la página.

## <a name="additional-resources"></a>Recursos adicionales

[Descripción general de la biblioteca de módulos](starter-kit-overview.md)

[Administrar la directiva de seguridad de contenido (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
