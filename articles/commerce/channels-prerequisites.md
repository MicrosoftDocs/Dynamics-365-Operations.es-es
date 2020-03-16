---
title: Requisitos previos de configuración de canales
description: Este tema presenta una visión general de los requisitos previos de configuración de canales en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 02/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 8a0927f6ee9b2d5bed1327bb223ceca85ecc16a0
ms.sourcegitcommit: 161e85eb0a6b772b60ba8b2578a3de149ce5bfd7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/22/2020
ms.locfileid: "3081324"
---
# <a name="channel-setup-prerequisites"></a>Requisitos previos de configuración de canales


[!include [banner](includes/banner.md)]

Este tema presenta una visión general de los requisitos previos de configuración de canales en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Para poder crear un canal de Dynamics 365 Commerce es necesario completar antes varias tareas de requisitos previos. Las siguientes listas de tareas de requisitos previos están organizadas por tipo de canal.

> [!NOTE]
> Todavía se está escribiendo parte de la documentación. Los vínculos se actualizarán a medida que se publique nuevo contenido.

## <a name="initialization"></a>Inicialización

- [Inicializar datos semilla](enable-configure-retail-functionality.md)

## <a name="global-prerequisities-required-for-all-channel-types"></a>Requisitos previos globales necesarios para todos los tipos de canales

- [Definir y configurar su estructura de entidad jurídica](channels-legal-entities.md) 
- [Configurar su jerarquía organizativa](channels-org-hierarchies.md)
- [Configurar un almacén](channels-setup-warehouse.md)
- [Configurar impuestos](https://docs.microsoft.com/dynamics365/finance/general-ledger/indirect-taxes-overview?toc=/dynamics365/commerce/toc.json)
- [Configurar un perfil de notificación por correo electrónico](email-notification-profiles.md)
- [Configurar secuencias numéricas](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/number-sequence-overview?toc=/dynamics365/commerce/toc.json)
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
