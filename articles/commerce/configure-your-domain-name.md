---
title: Configurar su nombre de dominio
description: Este tema explica cómo configurar un nombre de dominio para un sitio de comercio electrónico de Microsoft Dynamics 365.
author: psimolin
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 7a988f533757cc3f8555fcf4fb724a22a5b014f8
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770467"
---
# <a name="configure-your-domain-name"></a>Configurar su nombre de dominio

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Este tema explica cómo configurar un nombre de dominio para un sitio de comercio electrónico de Microsoft Dynamics 365. 

## <a name="add-domains-during-e-commerce-initialization"></a>Agregar dominios durante la inicialización de comercio electrónico

Para asociar dominios con su entorno de comercio electrónico, inicialice el comercio electrónico como se describe en [Implementar un sitio nuevo de comercio electrónico](deploy-ecommerce-site.md). Durante la inicialización, se le pide proporcionar información que se usará para aprovisionar su entorno de comercio electrónico. En el campo **Nombres de hosts admitidos**, agregue todos los dominios que planea usar con este entorno. Se deben separar varios dominios con punto y coma. De esta manera, los dominios se configuran en todos los componentes requeridos de comercio electrónico y están listos para usarse al cambiar el tráfico desde su red de entrega de contenido (CDN) o servidor web y lo apunta a los front-ends de comercio electrónico.

## <a name="add-domains-after-e-commerce-initialization"></a>Agregar dominios después de la inicialización de comercio electrónico

Para asociar dominios nuevos con su entorno de comercio electrónico después de la inicialización de comercio electrónico, debe enviar una solicitud de servicio.

## <a name="additional-resources"></a>Recursos adicionales

[Visión general de la tienda en línea](online-store-overview.md)

[Crear un sitio de comercio electrónico](create-ecommerce-site.md)

[Implementar un sitio nuevo de comercio electrónico](deploy-ecommerce-site.md)

[Asociar un sitio en línea con un canal](associate-site-online-store.md)

[Agregar soporte para una red de entrega de contenido (CDN)](add-cdn-support.md)

[Habilitar la detección de tienda según la ubicación](enable-store-detection.md)

[Configurar páginas personalizadas para inicios de sesión de usuario](custom-pages-user-logins.md)
