---
title: Habilitar la detección de tienda según la ubicación
description: Este artículo describe cómo activar la detección de tienda basada en ubicación para su sitio de Dynamics 365 Commerce.
author: brianshook
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 38c93e30a606d818d909a4ec014009c18c25e8c5
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9274350"
---
# <a name="enable-location-based-store-detection"></a>Habilitar la detección de tienda según la ubicación

[!include [banner](includes/banner.md)]

Este artículo describe cómo activar la detección de tienda basada en ubicación para su sitio de Dynamics 365 Commerce.

La detección de tienda basada en ubicación le permite proporcionar el contenido del sitio relevante a los clientes, en función de su ubicación. Cuando se activa la detección de tienda basada en tienda, el servicio de representación de Commerce utiliza información de país o región de la dirección IP del explorador web del cliente para dirigir al cliente a la mejor configuración de sitio geográfico que esté disponible.

## <a name="privacy-notice"></a>Aviso de privacidad

Si activa la función de detección de tienda basada en ubicación, la información del explorador del cliente se envía un servicio de ubicación de Microsoft. Esta información se usa a continuación para proporcionar contenido del cliente que sea relevante para la ubicación del mismo. Tanto la información que se envía desde el explorador del cliente como la información basada en la ubicación que se devuelve al cliente están sujetas a directivas de cumplimiento de cookies y privacidad.

## <a name="turn-on-location-based-store-detection"></a>Activar la detección de tienda según la ubicación

Para activar la detección de tienda según la ubicación en Commerce, siga estos pasos.

1. En la herramienta de creación, vaya al sitio.
1. En el panel de navegación de la izquierda, seleccione **Administración de sitios**.
1. Seleccione **Valores de configuración de sitio**.
1. Establezca la opción **Habilitar la detección de tienda según la ubicación** en **Activado**.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar su nombre de dominio](configure-your-domain-name.md)

[Implementar un inquilino nuevo de comercio electrónico](deploy-ecommerce-site.md)

[Crear un sitio de comercio electrónico](create-ecommerce-site.md)

[Asociar un sitio de Dynamics 365 Commerce con un canal en línea](associate-site-online-store.md)

[Administrar archivos robots.txt](manage-robots-txt-files.md)

[Subir redireccionamientos de URL en grandes cantidades](upload-bulk-redirects.md)

[Configurar un inquilino B2C en Commerce](set-up-B2C-tenant.md)

[Configurar páginas personalizadas para inicios de sesión de usuario](custom-pages-user-logins.md)

[Configurar múltiples inquilinos B2C en un entorno de Commerce](configure-multi-B2C-tenants.md)

[Agregar soporte para una red de entrega de contenido (CDN)](add-cdn-support.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
