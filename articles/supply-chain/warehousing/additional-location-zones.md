---
title: Zonas de ubicación adicionales
description: Este tema proporciona una descripción general de las nuevas zonas de ubicación que se han agregado a Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: 662725edf5bf8d95be038f7c989b73d8d05fa0df
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996435"
---
# <a name="additional-location-zones"></a>Zonas de ubicación adicionales

[!include [banner](../includes/banner.md)]

Tres nuevos campos de zona están disponibles en Microsoft Dynamics 365 Supply Chain Management. Los gerentes de almacén pueden usarlos para definir organizaciones o diseños de almacén adicionales. Los nuevos campos de zona se pueden configurar manualmente o mediante el uso del asistente de **Configuración de ubicación**. Se pueden usar en cualquier consulta o filtrado que use la tabla Ubicaciones.

No se requiere configuración adicional para usar los campos de zona.

## <a name="turn-on-the-additional-location-zone-feature"></a>Activar la característica de zona de ubicación adicional

Antes de poder usar la característica *Zona de ubicación adicional*, esta debe estar activada en su sistema. Los administradores pueden usar la configuración de [gestión de funciones](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar el estado de la función y activarla si es necesario. En el espacio de trabajo **Administración de funciones**, la función aparece de la siguiente forma:

- **Módulo:** *Gestión de almacén*
- **Nombre de la característica:** *Zona de ubicación adicional*

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
