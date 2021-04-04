---
title: La tienda minorista no aparece en la lista de tiendas desde donde recoger
description: Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando una tienda minorista no aparece en la lista de tiendas donde se pueden recoger los artículos.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 652f5f1a779a412c21c18814071ba0fb7dd2e155
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585526"
---
# <a name="retail-store-doesnt-appear-in-the-list-of-stores-to-pick-up-from"></a>La tienda minorista no aparece en la lista de tiendas desde donde recoger

[!include [banner](../../includes/banner.md)]

Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando una tienda minorista no aparece en la lista de tiendas donde se pueden recoger los artículos.

## <a name="description"></a>Descripción

Una tienda minorista no aparece en la lista de tiendas donde se pueden recoger artículos.

## <a name="resolution"></a>Resolución

### <a name="configure-the-longitude-and-latitude-for-the-store-address-in-commerce-headquarters"></a>Configure la longitud y latitud de la dirección de la tienda en la sede de Commerce

Para configurar la longitud y latitud de la dirección de la tienda en la sede de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Canales \> Tiendas \> Todas las tiendas**.
1. Busque la tienda que desea que aparezca entre las opciones de recogida en el sitio de comercio electrónico. Tome nota de su valor de **Número de unidad operativa**.
1. Vaya a **Administración de la organización \> Organizaciones \> Unidades operativas**.
1. Busque el número de unidad operativa que anotó anteriormente y luego seleccione la unidad operativa en los resultados de la búsqueda.
1. En la ficha desplegable **Direcciones**, seleccione **Más opciones** y luego seleccione **Avanzado**.
1. En la ficha desplegable **General**, asegúrese de que los campos **Longitud** y **Latitud** están configurados correctamente. Como parte de este paso, asegúrese de que los valores estén especificados correctamente como números positivos o negativos.

### <a name="configure-fulfillment-groups-in-commerce-headquarters"></a>Configurar grupos de cumplimentación en la sede de Commerce

Para configurar grupos de cumplimentación en la sede de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Canales \> Tiendas en línea**.
1. Seleccione la tienda en línea a configurar.
1. En el panel de acciones, seleccione **Configurar** y, a continuación, seleccione **Asignación de grupo de cumplimentación**.
1. En la página **Asignación de grupo de cumplimentación**, seleccione el grupo de cumplimentación para la tienda en línea.
1. En **Configuración**, asegúrese de que la tienda minorista esté configurada correctamente para el grupo de cumplimentación.

## <a name="additional-resources"></a>Recursos adicionales 

[Crear una unidad operativa](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit)

[Configurar un canal en línea](../channel-setup-online.md)
