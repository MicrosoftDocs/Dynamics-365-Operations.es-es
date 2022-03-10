---
title: Zonas de ubicación adicionales
description: Este tema proporciona una descripción general de las nuevas zonas de ubicación que se han agregado a Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSLocationBuild, WHSZone
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: dd9e97cabe5e3d3bdc261a7280930b73eb8e1419
ms.sourcegitcommit: fcb8a3419e3597fe855cae9eb21333698518c2c7
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/09/2022
ms.locfileid: "8103847"
---
# <a name="additional-location-zones"></a>Zonas de ubicación adicionales

[!include [banner](../includes/banner.md)]

Tres nuevos campos de zona están disponibles en Microsoft Dynamics 365 Supply Chain Management. Los gerentes de almacén pueden usarlos para definir organizaciones o diseños de almacén adicionales. Los nuevos campos de zona se pueden configurar manualmente o mediante el uso del asistente de **Configuración de ubicación**. Se pueden usar en cualquier consulta o filtrado que use la tabla Ubicaciones.

No se requiere configuración adicional para usar los campos de zona.

## <a name="turn-the-additional-location-zone-feature-on-or-off"></a>Activar o desactivar la característica de zona de ubicación adicional

A partir de la versión 10.0.25 de Supply Chain Management, esta función está activada de forma predeterminada. Los administradores pueden activar o desactivar esta funcionalidad buscando la característica *Zona de ubicación adicional* en el espacio de trabajo [Administración de características](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

## <a name="use-location-zones"></a>Usar zonas de ubicación

1. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Asistente de configuración de ubicación**.
2. Establezca los valores siguientes:

    - En el campo **Almacén**, seleccione _62_.
    - En el campo **Id. de zona**, escriba _FLOOR_.
    - En el campo **Zona adicional 1**, escriba _PICKZONE1_.
    - En el campo **Zona adicional 2**, escriba _WEBSHOP1_.
    - En el campo **Id. de perfil de ubicación**, seleccione _FLOOR_.

3. Seleccione la línea **Floor**.
4. En el campo **Desde número**, escriba _1_. En el campo **Hasta número**, escriba _3_.
5. Seleccione la línea **Aisle**.
6. En el campo **Desde número**, escriba _1_. En el campo **Hasta número**, escriba _5_.
7. Seleccione **Crear**.
8. Recibe mensajes que indican que se han agregado nuevas ubicaciones. Seleccione el botón **Mostrar mensajes** para ver los mensajes.
9. Vaya a **Gestión de almacenes \> Configurar \> Almacén \> Ubicaciones**. Las nuevas ubicaciones aparecen en la lista y todos los campos de zona están disponibles (es decir, el campo de zona existente y los nuevos campos de zona adicionales).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]