---
title: Portal del cliente para introducción de Dynamics 365 Supply Chain Management
description: Este tema presenta el portal del Cliente y explica quién debe usarlo y cómo funciona.
author: dasani-madipalli
ms.date: 06/16/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: intro-internal
ms.search.region: Global
ms.author: damadipa
ms.search.validFrom: 2020-04-22
ms.dyn365.ops.version: Release 10.0.13
ms.openlocfilehash: 7618bb202dac3295c948d74c482900b0aeae8bd5
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/06/2021
ms.locfileid: "6353947"
---
# <a name="customer-portal-for-dynamics-365-supply-chain-management-overview"></a>Portal del cliente para introducción de Dynamics 365 Supply Chain Management

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

## <a name="what-is-the-customer-portal"></a>¿Qué es el portal del cliente?

Los sistemas modernos de la cadena de suministro dependen de la integración. Requieren que los departamentos de inventario, demanda de clientes y ventas se integren en lugar de residir en silos separados. El portal del cliente ayuda a las organizaciones que ejecutan Microsoft Dynamics 365 Supply Chain Management a mejorar esta integración y mantener informados a sus clientes de manera más efectiva.

El portal del cliente es una plantilla de [portales Power Apps](/powerapps/maker/portals/overview) que permite a las empresas crear un sitio web de empresa a empresa (B2B) orientado al exterior para escenarios relacionados con el procesamiento de pedidos de ventas. La plantilla usa [doble escritura](../../fin-ops-core/dev-itpro/data-entities/dual-write/dual-write-home-page.md), Supply Chain Management y portales Power Apps para permitir a los clientes empresariales externos ver y crear datos desde el entorno Dynamics 365 de la empresa.

La plantilla del portal del cliente tiene todas las capacidades de personalización que los portales presentan de ofertas de Power Apps. La plantilla se puede modificar fácilmente para representar la marca de la empresa, agregar una mayor funcionalidad y cambiar la experiencia del usuario. Toda la funcionalidad que ofrece la plantilla inmediatamente puede modificarse según se desee.

> [!IMPORTANT]
> Por sí misma, no está pensado que la plantilla sea completamente funcional. Simplemente sirve como un posibilitador para los clientes que desean crear un sitio web externo para que los clientes empresariales puedan interactuar con los datos de Supply Chain Management.

> [!NOTE]
> La documentación del portal del Cliente está dirigida a administradores, personalizadores e integradores de sistemas que configurarán el portal del Cliente para una instalación de Supply Chain Management. Utiliza los términos _cliente_ y _usuario_ para describir a las personas que son clientes de la organización que ejecuta Supply Chain Management y que utilizarán el portal final.

## <a name="video"></a>Vídeo

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4ylwW]

El vídeo de la [Descripción general de la plantilla del portal del cliente en Dynamics 365 Supply Chain Management](https://youtu.be/nPrqoLuHfV8) (que se muestra arriba) está incluido en la [lista de reproducción de Finance and Operations](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) disponible en YouTube.

## <a name="who-should-use-it"></a>¿Quién debería usarlo?

El portal del Cliente está diseñado para empresas que ejecutan Supply Chain Management y tienen estas características:

- Quieren crear un sitio web externo que comunique la información de procesamiento de pedidos (como el estado del pedido o la información de la cuenta) directamente desde su sistema de Supply Chain Management a sus clientes empresariales.
- Están haciendo la transición desde Dynamics AX 2012 a Supply Chain Management y anteriormente utilizaban el [AX Portal de autoservicio para clientes 2012](/dynamicsax-2012/appuser-itpro/about-the-customer-self-service-portal).

Los siguientes tipos de organizaciones **no** son buenos candidatos para implementar el portal del Cliente:

- Empresas que desean crear un sitio web para clientes no empresariales. Estas empresas deberían considerar crear un [sitio web de comercio electrónico Dynamics 365 Commerce](../../commerce/create-ecommerce-site.md).
- Empresas que ya están usando un sitio web de portales Power Apps para un propósito similar. Estas empresas no recibirán ningún beneficio adicional del portal del Cliente. El portal del Cliente se entrega como una plantilla que actúa como guía y punto de partida para los clientes que desean "interconectar" entre escritura doble, Supply Chain Management y portales Power Apps. Si ya ha configurado un sitio web que sirve para este propósito, es posible que no saque mucho provecho al usar la plantilla del portal del Cliente para reaprovisionar ese sitio web.

## <a name="how-does-it-work"></a>¿Cómo funciona?

El portal del cliente se proporciona como una plantilla de portales Power Apps. Depende de los portales Power Apps portales y doble escritura.

[Portales Power Apps](/powerapps/maker/portals/overview) es una característica que permite a los usuarios crear un sitio web externo en el que las personas externas a la organización pueden iniciar sesión. Se requiere poca o ninguna codificación para crear portales. El portal del cliente es una de las muchas [Plantillas de portal de Dynamics 365](/powerapps/maker/portals/portal-templates#environment-with-model-driven-apps-in-dynamics-365) que están disponibles en Microsoft.

La [doble escritura](/powerapps/maker/portals/overview) es un producto de infraestructura listo para usar que proporciona interacción casi en tiempo real entre aplicaciones de interacción con los clientes y aplicaciones de Finance and Operations. La doble escritura proporciona una integración bidireccional entre aplicaciones de Finance and Operations y Microsoft Dataverse. Por taanto, este flujo de datos automatizado proporciona una experiencia de usuario integrada en todas las aplicaciones. El portal del cliente depende de tablas que se sincronizan con doble escritura. Para que los datos de Supply Chain Management puedan aparecer en el portal del Cliente, se debe habilitar la escritura doble para todas las tablas apropiadas.

![Dependencias del portal del cliente.](media/customer-portal-elements.png "Dependencias del portal del cliente")

El portal del cliente actúa como punto de partida para las organizaciones que desean utilizar portales Power Apps para construir un sitio web externo que utilice datos de su instalación de Supply Chain Management. Ayuda a las organizaciones a conectar la doble escritura, Supply Chain Management y los portales Power Apps.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]