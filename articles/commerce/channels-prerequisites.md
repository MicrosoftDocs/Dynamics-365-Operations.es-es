---
title: Requisitos previos de configuración del canal
description: Este artículo presenta una visión general de los requisitos previos de configuración de canales en Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 02/21/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 98ca2dc4691534853467c1680890199d08bc4e79
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 08/12/2022
ms.locfileid: "9282305"
---
# <a name="channel-setup-prerequisites"></a>Requisitos previos de configuración del canal

[!include [banner](includes/banner.md)]

Este artículo presenta una visión general de los requisitos previos de configuración de canales en Microsoft Dynamics 365 Commerce.

Para poder crear un canal de Dynamics 365 Commerce es necesario completar antes varias tareas de requisitos previos. Las siguientes listas de tareas de requisitos previos están organizadas por tipo de canal.

> [!NOTE]
> Todavía se está escribiendo parte de la documentación. Los vínculos se actualizarán a medida que se publique nuevo contenido.

## <a name="initialization"></a>Inicialización

- [Inicializar datos semilla](enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a>Requisitos previos globales necesarios para todos los tipos de canales

- [Definir y configurar su estructura de entidad jurídica](channels-legal-entities.md) 
- [Configurar su jerarquía organizativa](channels-org-hierarchies.md)
- [Configurar un almacén](channels-setup-warehouse.md)
- [Configurar impuestos](../finance/general-ledger/indirect-taxes-overview.md?toc=/dynamics365/commerce/toc.json)
- [Configurar un perfil de notificación por correo electrónico](email-notification-profiles.md)
- [Configurar secuencias numéricas](../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md?toc=/dynamics365/commerce/toc.json)
- [Configurar un cliente y una libreta de direcciones predeterminados](default-customer.md)
<!--
- [Configure commerce parameters](commerce-parameters.md)
-->

## <a name="retail-channel-prerequisites"></a>Requisitos previos de canal comercial

- [Códigos de información y grupos de códigos de información](info-codes-retail.md)
- [Configurar un perfil de funcionalidad comercial](retail-functionality-profile.md)
- [Configurar una libreta de direcciones de empleado](new-address-book.md)
- [Configurar un diseño de pantalla](pos-screen-layouts.md)
- [Configurar una estación de hardware](retail-hardware-station-configuration-installation.md)

## <a name="call-center-channel-prerequisites"></a>Requisitos previos de canales de centro de llamadas

- Parámetros del centro de llamadas.
- [Métodos de pedido de centro de llamadas y devolución de pagos](work-with-payments.md)
- [Modos de entrega y cobros de los modos de centro de llamadas](configure-call-center-delivery.md)

## <a name="online-channel-prerequisites"></a>Requisitos previos del canal en línea

- [Crear un perfil de funcionalidad en línea](online-functionality-profile.md)

## <a name="additional-resources"></a>Recursos adicionales

[Resumen de canales](channels-overview.md)

[Visión general de las organizaciones y las jerarquías organizativas](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Configurar jerarquías organizativas](channels-org-hierarchies.md)

[Crear entidades jurídicas](channels-legal-entities.md)

[Configurar un canal comercial](channel-setup-retail.md)
    
[Configurar un canal en línea](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
