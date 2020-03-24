---
title: Habilitar la detección de tienda según la ubicación
description: Este tema describe cómo activar la detección de tienda basada en ubicación para su sitio de Dynamics 365 Commerce.
author: brianshook
manager: annbe
ms.date: 03/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 66ffe56f9d969c9d62ed4ff49f0848fab7e58a56
ms.sourcegitcommit: 567132f4e4f7a1d76dccf762068209a42c788b52
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096878"
---
# <a name="enable-location-based-store-detection"></a>Habilitar la detección de tienda según la ubicación


[!include [banner](includes/banner.md)]

Este tema describe cómo activar la detección de tienda basada en ubicación para su sitio de Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

La detección de tienda basada en ubicación le permite proporcionar el contenido del sitio relevante a los clientes, en función de su ubicación. Cuando se activa la detección de tienda basada en tienda, el servicio de representación de Commerce utiliza información de país o región de la dirección IP del explorador web del cliente para dirigir al cliente a la mejor configuración de sitio geográfico que esté disponible.

## <a name="privacy-notice"></a>Aviso de privacidad

Si activa la función de detección de tienda basada en ubicación, la información del explorador del cliente se envía un servicio de ubicación de Microsoft. Esta información se usa a continuación para proporcionar contenido del cliente que sea relevante para su ubicación. Tanto la información que se envía desde el explorador del cliente como la información basada en la ubicación que se devuelve al cliente están sujetas a directivas de cumplimiento de cookies y privacidad.

## <a name="turn-on-location-based-store-detection"></a>Activar la detección de tienda según la ubicación

Para activar la detección de tienda según la ubicación en Commerce, siga estos pasos.

1. En la herramienta de creación, vaya al sitio.
1. En el panel de navegación de la izquierda, seleccione **Administración de sitios**.
1. Seleccione **Valores de configuración de sitio**.
1. Establezca la opción **Habilitar la detección de tienda según la ubicación** en **Activado**.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar su nombre de dominio](configure-your-domain-name.md)

[Implementar un sitio nuevo de comercio electrónico](deploy-ecommerce-site.md)

[Configurar un canal de la tienda en línea](online-stores.md)

[Crear un sitio de comercio electrónico](create-ecommerce-site.md)

[Asociar un sitio en línea con un canal](associate-site-online-store.md)

[Administrar archivos robots.txt](manage-robots-txt-files.md)

[Subir redireccionamientos de URL en grandes cantidades](upload-bulk-redirects.md)

[Configurar un inquilino B2C en Commerce](set-up-B2C-tenant.md)

[Configurar páginas personalizadas para inicios de sesión de usuario](custom-pages-user-logins.md)

[Configurar múltiples inquilinos B2C en un entorno de Commerce](configure-multi-B2C-tenants.md)

[Agregar soporte para una red de entrega de contenido (CDN)](add-cdn-support.md)
