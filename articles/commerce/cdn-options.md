---
title: Opciones de implementación de la red de entrega de contenido
description: Este tema revisa las diferentes opciones para la implementación de la red de entrega de contenido (CDN) que se pueden usar con ambientes de Microsoft Dynamics 365 Commerce. Estas opciones incluyen instancias nativas proporcionadas por Commerce de Azure Front Door e instancias propiedad del cliente de Azure Front Door.
author: BrianShook
ms.date: 03/11/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2020-11-01
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9e98cf81f13b9181059bc96b95ac277a088311ea
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800720"
---
# <a name="content-delivery-network-implementation-options"></a>Opciones de implementación de la red de entrega de contenido

[!include [banner](includes/banner.md)]

Este tema revisa las diferentes opciones para la implementación de la red de entrega de contenido (CDN) que se pueden usar con ambientes de Microsoft Dynamics 365 Commerce. Estas opciones incluyen instancias nativas proporcionadas por Commerce de Azure Front Door e instancias propiedad del cliente de Azure Front Door.

Los clientes de Commerce tienen varias opciones cuando están considerando qué servicio de red CDN usar con su entorno de Commerce. Commerce se lanza con soporte básico de Azure Front Door que cubre los requisitos básicos de hospedaje y dominio personalizado. Para las empresas que desean más control y capacidades de seguridad más específicas, como un firewall de aplicaciones web (WAF), la mejor opción podría ser usar una instancia de Azure Front Door propiedad del cliente o un servicio CDN externo.

Las siguientes tres opciones de implementación de CDN se pueden utilizar con entornos de Commerce:

- Una instancia de Azure Front Door proporcionada por Commerce
- Una instancia de Azure Front Door propiedad del cliente (para un mayor control y características de seguridad adicionales)
- Un servicio CDN externo

Las tres opciones de implementación de CDN ofrecen solo contenido HTML dinámico de dominios personalizados. Commerce maneja automáticamente todo el JavaScript, las hojas de estilo en cascada (CSS), imágenes, vídeos y otro contenido estático a través de las CDN administradas por Microsoft. La opción que elija determina las capacidades operativas, las capacidades de control y las capacidades de seguridad adicionales que están disponibles.

La ilustración siguiente muestra una visión general de la arquitectura de Commerce.

![Visión general de la arquitectura de Commerce](media/Commerce_CDN-Option_ComparisonModels.png)

Para obtener más información sobre cómo configurar una instancia de Azure Front Door para su sitio de Commerce, consulte [Agregar soporte CDN](add-cdn-support.md).

## <a name="use-the-commerce-provided-azure-front-door-instance"></a>Usar la instancia de Azure Front Door proporcionada por Commerce

En la siguiente tabla se enumeran los pros y los contras de usar la instancia de Azure Front Door proporcionada por Commerce para administrar los puntos de conexión de contenido.

| Pros | Contras |
|------|------|
| <ul><li>La instancia está incluida en el coste de Commerce.</li><li>Debido a que la instancia es administrada por el equipo de Comercio, se requiere menos mantenimiento y hay pasos de configuración compartidos.</li><li>La infraestructura alojada en Azure es escalable, segura y confiable.</li><li>El certificado Capa de sockets seguros (SSL) requiere una configuración única y se renueva automáticamente.</li><li>El equipo de Commerce supervisa la instancia para detectar errores y anomalías.</li></ul> | <ul><li>No se admite WAF.</li><li>No hay personalizaciones específicas ni ajustes de configuración.</li><li>La instancia depende del equipo de Commerce para actualizaciones o cambios.</li><li>Se requiere una instancia independiente de Azure Front Door para los dominios apex y se requiere trabajo adicional para integrar los dominios apex con Azure DNS.</li><li>No se proporciona al cliente telemetría sobre las respuestas por segundo (RPS) o la tasa de error.</li></ul> |

La siguiente ilustración muestra la arquitectura de la instancia de Azure Front Door proporcionada por Commerce.

![Instancia de Azure Front Door proporcionada por Commerce](media/Commerce_CDN-Option_CommerceFrontDoor.png)

## <a name="use-a-customer-owned-azure-front-door-instance"></a>Usar una instancia de Azure Front Door propiedad del cliente

En la siguiente tabla se enumeran los pros y los contras de usar la instancia de Azure Front Door propiedad del cliente para administrar los puntos de conexión de contenido.

| Pros | Contras |
|------|------|
| <ul><li>La configuración es segura y fácil de administrar.</li><li>La infraestructura alojada en Azure es escalable, segura y confiable.</li><li>La instancia permite la integración WAF y controles de reglas granulares para una seguridad de mayor grado que se ajusta específicamente a su sitio.</li><li>La instancia permite un control más preciso de los certificados SSL (tanto propiedad del cliente como administrados por Azure Front Door) y la vinculación de dominios.</li><li>La instancia ofrece una solución de dominio apex si está emparejada directamente con Azure DNS.</li><li>Se proporcionan telemetría y alertas.</li><li>El certificado SSL requiere una configuración única y se renueva automáticamente.</li></ul> | <ul><li>La instancia es autogestionada.</li><li>Se requiere un aumento de los conocimientos iniciales.</li></ul> |

La siguiente ilustración muestra una infraestructura de Commerce que incluye una instancia de Azure Front Door propiedad del cliente.

![Infraestructura de Commerce que incluye una instancia de Azure Front Door propiedad del cliente](media/Commerce_CDN-Option_CustomerOwnedAzureFrontDoor.png)

## <a name="use-an-external-cdn-service"></a>Usar un servicio CDN externo

La siguiente tabla enumera los pros y los contras de usar un servicio CDN externo para administrar puntos finales de contenido.

| Pros | Contras |
|------|------|
| <ul><li>Esta opción es útil cuando el dominio existente ya está alojado en una CDN externa.</li><li>Las CDN de la competencia (por ejemplo, Akamai) pueden tener más capacidades WAF.</li></ul> | <ul><li>Se requiere un contrato por separado y un coste adicional.</li><li>SSL puede generar costos adicionales.</li><li>Debido a que el servicio está separado de la estructura de la nube de Azure, se debe administrar una infraestructura adicional.</li><li>Es posible que el servicio requiera inversiones más prolongadas en la configuración de puntos de conexión y seguridad.</li><li>El servicio es autogestionado.</li><li>El servicio es autogestionado.</li></ul> |

La siguiente ilustración muestra una infraestructura de Commerce que incluye un servicio CDN externo.

![Infraestructura comercial que incluye un servicio CDN externo](media/Commerce_CDN-Option_ExternalFrontDoor.png)

## <a name="additional-resources"></a>Recursos adicionales

[Agregar soporte para una red de entrega de contenido (CDN)](add-cdn-support.md)
