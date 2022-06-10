---
title: Módulo de suscripción
description: En este tema se tratan los módulos de suscripción y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.
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
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: efc9150ea5ddeb7051f82fb07c4d566ac8a48dfa
ms.sourcegitcommit: ccb39767bd3430c24f4653c26560bba2cd66553c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2022
ms.locfileid: "8780598"
---
# <a name="subscribe-module"></a>Módulo de suscripción

[!include [banner](includes/banner.md)]

En este tema se tratan los módulos de suscripción y se describe cómo agregarlos a las páginas de sitio en Microsoft Dynamics 365 Commerce.

Los módulos de suscripción se pueden utilizar en las páginas del sitio para capturar información del cliente para boletines o promociones.

La siguiente ilustración muestra un ejemplo de un módulo de suscripción en el pie de página de una página del sitio Adventure Works.

![Ejemplo de un módulo de suscripción en el pie de página de una página del sitio de Adventure Works](./media/Subscribe.PNG)

> [!IMPORTANT]
> - El módulo de suscripción está disponible en la biblioteca del módulo de Comercio a partir del lanzamiento de la versión 10.0.20 de Dynamics 365 Commerce.
> - El módulo de suscripción se muestra en el tema Adventure Works.
> - El módulo de suscripción requiere una extensión de acción de datos para trabajar con algunos proveedores de correo electrónico de marketing, de modo que se puedan enviar correos electrónicos promocionales o boletines después de que se capture la información del cliente.

## <a name="subscribe-module-properties"></a>Propiedades del módulo de suscripción

| Nombre de la propiedad | Valores | Descripción |
|---------------|--------|-------------|
| Cabecera       | Etiqueta de encabezado y texto de encabezado (**H1**, **H2**, **H3**, **H4**, **H5** o **H6**) | Un encabezado de texto para el módulo de suscripción, como **Suscribirse al boletín** o **Registrarse para obtener un 10 % de descuento**. |
| Párrafo     | Texto de párrafo | El módulo de suscripción admite texto de párrafo en formato de texto enriquecido, para proporcionar detalles adicionales para la llamada a la acción en el encabezado. |

## <a name="add-a-subscribe-module-to-a-new-page"></a>Agregar un módulo de suscripción a una página nueva

Para agregar un módulo de lista de suscripción a una página nueva y establecer las propiedades necesarias en el generador de sitios de Commerce, siga estos pasos.

1. Vaya a **Plantillas** y abra la plantilla de marketing para la página de inicio de su sitio (o cree una nueva plantilla de marketing).
1. En el espacio **Principal** de la página predeterminada, seleccione los puntos suspensivos (**...**) y, a continuación, seleccione **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Suscribir** y, a continuación, **Aceptar**.
1. Seleccione **Guardar** y seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.
1. Vaya a **Páginas** y abra la página de inicio del sitio (o cree una nueva página de inicio utilizando la plantilla de marketing).
1. En el espacio **Principal** de la página predeterminada, seleccione los puntos suspensivos (**...**) y, a continuación, **Agregar módulo**.
1. En el cuadro de diálogo **Seleccionar módulos**, seleccione el módulo **Suscribir** y, a continuación, **Aceptar**.
1. En el panel de propiedades del módulo de suscripción, agregue un encabezado, como **Suscribirse**.
1. Agregue texto de párrafo, como **Últimas tendencias, estilos y promociones. ¿Estás en la lista? ¡Suscríbete y obtén las últimas ofertas!**
1. Seleccione **Guardar** y luego seleccione **Vista previa** para previsualizar la página.
1. Seleccione **Finalizar edición** para proteger la plantilla y luego seleccione **Publicar** para publicarla.

## <a name="additional-resources"></a>Recursos adicionales

[Descripción general de la biblioteca de módulos](starter-kit-overview.md)

[Tema de Adventure Works](adventure-works-theme.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
