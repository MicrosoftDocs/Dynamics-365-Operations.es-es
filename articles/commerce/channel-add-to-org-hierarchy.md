---
title: Agregar un canal a una jerarquía organizativa
description: En este tema se describe cómo agregar un canal a una jerarquía organizativa en Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 297bd34f9bde23d5cc7de266b8e8f49b1a752662
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993711"
---
# <a name="add-a-channel-to-an-organizational-hierarchy"></a>Agregar un canal a una jerarquía organizativa


[!include [banner](includes/banner.md)]

En este tema se describe cómo agregar un canal a una jerarquía organizativa en Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Visión general

Los canales deben estar asociados con una o más jerarquías organizativas. Antes de crear canales, debe confirmar que se han configurado sus jerarquías organizativas.  

Consulte [Jerarquías organizativas](channels-org-hierarchies.md) para ver más detalles sobre cómo crear jerarquías organizativas.

## <a name="select-a-hierarchy"></a>Seleccionar una jerarquía

Para seleccionar una jerarquía, siga estos pasos.

1. En el panel de navegación, vaya a **Módulos \> Retail y Commerce \> Configuración de canal \> Jerarquía organizativa**.
1. En la lista, seleccione la jerarquía organizativa a la que va a agregar el canal.
1. En el panel de acciones, seleccione **Ver** para ver los detalles de la jerarquía.

La siguiente imagen muestra detalles de la jerarquía organizativa para la jerarquía seleccionada.

![Detalles de la jerarquía organizativa para la jerarquía seleccionada.](media/channel-add-to-org-hierarchy-1.png)

## <a name="add-a-channel-to-a-hierachy-node"></a>Agregar un canal a un nodo de jerarquía

Para agregar un canal a un nodo de jerarquía, siga estos pasos.

1. En el panel de acciones, seleccione **Editar**.
1. Seleccione el nodo de jerarquía al que desea agregar el canal y, a continuación, desde la lista desplegable **Insertar**, seleccione **Canal comercial**. 
1. Seleccione el canal para agregar y, a continuación, seleccione el botón **Aceptar**.
1. En el panel de acciones, seleccione **Guardar**.
1. En el panel de acciones, seleccione **Publicar** y proporcione una **Fecha de vigencia** del pasado para que esta acción entre en vigor de inmediato.

La siguiente imagen muestra cómo seleccionar un canal para agregarlo a un nodo de jerarquía.

![Seleccionar un canal para agregarlo a un nodo de jerarquía](media/channel-add-to-org-hierarchy-2.png)

La siguiente imagen muestra una jerarquía con varios canales agregados.

![Una jerarquía con varios canales agregados](media/channel-add-to-org-hierarchy-3.png)

## <a name="additional-resources"></a>Recursos adicionales

[Resumen de canales](channels-overview.md)

[Requisitos previos de configuración de canales](channels-prerequisites.md)

[Visión general de las organizaciones y las jerarquías organizativas](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[Planificación de su jerarquía organizativa](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[Jerarquías organizativas](channels-org-hierarchies.md)

[Configurar un canal comercial](channel-setup-retail.md)
    
[Configurar un canal en línea](channel-setup-online.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]