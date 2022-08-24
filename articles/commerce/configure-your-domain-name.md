---
title: Configurar su nombre de dominio
description: Este artículo explica cómo configurar un nombre de dominio para un sitio de comercio electrónico de Microsoft Dynamics 365.
author: josaw1
ms.date: 07/02/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: global
ms.author: josaw
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.custom: ''
ms.assetid: ''
ms.search.industry: Retail
ms.search.form: ''
ms.openlocfilehash: 298ce84008e60cc82a494320b6a41f35338508c3
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9278634"
---
# <a name="configure-your-domain-name"></a>Configurar su nombre de dominio


[!include [banner](includes/banner.md)]

Este artículo explica cómo configurar un nombre de dominio para un sitio de comercio electrónico de Microsoft Dynamics 365. 

## <a name="add-domains-during-e-commerce-initialization"></a>Agregar dominios durante la inicialización de comercio electrónico

Para asociar dominios con su entorno de comercio electrónico de Dynamics 365 Commerce, inicialice el comercio electrónico como se describe en [Implementar un sitio nuevo de comercio electrónico](deploy-ecommerce-site.md). Durante la inicialización, se le pide proporcionar información que se usará para aprovisionar su entorno de comercio electrónico. En el campo **Nombres de hosts admitidos**, agregue todos los dominios que planea usar con este entorno. Se deben separar varios dominios con punto y coma. De esta manera, los dominios se configuran en todos los componentes requeridos de comercio electrónico y están listos para usarse al cambiar el tráfico desde su red de entrega de contenido (CDN) o servidor web y lo apunta a los front-ends de comercio electrónico.

## <a name="add-domains-after-e-commerce-initialization"></a>Agregar dominios después de la inicialización de comercio electrónico

Para asociar dominios nuevos con su entorno de comercio electrónico después de la inicialización de comercio electrónico, debe enviar una solicitud de servicio.

## <a name="additional-resources"></a>Recursos adicionales

[Implementar un inquilino nuevo de comercio electrónico](deploy-ecommerce-site.md)

[Crear un sitio de comercio electrónico](create-ecommerce-site.md)

[Asociar un sitio de Dynamics 365 Commerce con un canal en línea](associate-site-online-store.md)

[Administrar archivos robots.txt](manage-robots-txt-files.md)

[Subir redireccionamientos de URL en grandes cantidades](upload-bulk-redirects.md)

[Configurar un inquilino B2C en Commerce](set-up-B2C-tenant.md)

[Configurar páginas personalizadas para inicios de sesión de usuario](custom-pages-user-logins.md)

[Configurar múltiples inquilinos B2C en un entorno de Commerce](configure-multi-B2C-tenants.md)

[Agregar soporte para una red de entrega de contenido (CDN)](add-cdn-support.md)

[Habilitar la detección de tienda según la ubicación](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
