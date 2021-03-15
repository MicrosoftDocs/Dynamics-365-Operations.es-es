---
title: Módulo de iframe
description: En este tema se trata el modulo de iframe y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.
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
ms.search.validFrom: 2020-02-10
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: b7b5935a81377e0cb6acfc497eece6148bf1eeee
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993378"
---
# <a name="iframe-module"></a>Módulo de iframe

[!include [banner](includes/banner.md)]

En este tema se trata el modulo de iframe y se describe la forma de agregarlo a las páginas de sitio en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Información general

Un módulo de iframe proporciona un iframe (marco en línea) que aloja contenido externo en un sitio. Por ejemplo, se puede usar para alojar un vídeo YouTube o un visor de archivos PDF en cualquier página del sitio. 

Un módulo de iframe requiere una URL de destino. Luego aloja el contenido de la página de destino dentro de un elemento **iframe** de HTML. Las URL externas deben estar en la lista de permitidos según las directivas de política de seguridad de contenido (CSP) del sitio. Para el contenido de iframe, las URL deben permitirse mediante el uso de la directiva **antepasado del marco**. Para más información, consulte [Administrar la Directiva de seguridad de contenido (CSP)](manage-csp.md).

> [!NOTE]
> El módulo iframe está disponible en la versión Dynamics 365 Commerce 10.0.13.

La siguiente imagen muestra ejemplos de módulos de iframe que muestran videos externos en las páginas del sitio.

![Ejemplo de módulos de iframe que muestran vídeos externos](./media/ecommerce-iframe.PNG)

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
1. En el cuadro de diálogo **Elegir una plantilla**, seleccione la plantilla **Plantilla de marketing**. En **Nombre de página**, introduzca **Página de marketing** y después seleccione **Aceptar**.
1. En el espacio **Principal** de la nueva página, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **Contenedor** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo, establezca el valor **Ancho** para **Llenar contenedor**.
1. En el espacio **Contenedor**, seleccione los puntos suspensivos (**...**) y después seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Agregar módulo**, seleccione el módulo **iframe** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo, establezca el valor **URL de destino** a una URL externa para un vídeo.
1. Establecer otras propiedades, como **Bóveda** y **Altura**, como lo requiera.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la página y luego seleccione **Publicar** para publicarla.
1. Vaya a la página de marketing en su sitio. Debería ver que el vídeo se representa en el módulo de iframe.
 
## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la biblioteca de módulos](starter-kit-overview.md)

[Administrar la directiva de seguridad de contenido (CSP)](manage-csp.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]