---
title: Los registros de clientes no aparecen en la sede de Commerce
description: Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando los registros de los clientes no aparecen inmediatamente en la sede de Commerce.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: b8d065dd104df616ba8f10f7813e74c900fdcf77
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018491"
---
# <a name="customer-records-dont-appear-in-commerce-headquarters"></a>Los registros de clientes no aparecen en la sede de Commerce

[!include [banner](../../includes/banner.md)]

Este tema proporciona una guía para la resolución de problemas que puede ayudar cuando los registros de los clientes no aparecen inmediatamente en la sede de Commerce.

## <a name="description"></a>Descripción

Cuando crea un nuevo registro de cliente mediante el flujo de registro en el escaparate de comercio electrónico, el registro de cliente correspondiente no aparece inmediatamente en la sede de Commerce.

## <a name="resolution"></a>Resolución

### <a name="disable-customer-creation-in-async-mode"></a>Deshabilitar la creación de clientes en modo asíncrono

> [!IMPORTANT]
> Si deshabilita la creación de clientes asincrónica, el rendimiento del sistema podría verse afectado, porque la creación de cada registro producirá una solicitud en tiempo real a la sede de Commerce. Además, si la sede de Commerce está inactiva (por ejemplo, durante los flujos de servicio), cualquier flujo de creación de nuevos clientes producirá errores.

Para deshabilitar la creación de clientes en modo asíncrono en la sede de Commerce, siga estos pasos.

1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de tienda en línea \> Perfiles de funcionalidad**.
1. Si aún no está utilizando un perfil de funcionalidad para su canal en línea, cree uno.
1. Asegúrese de que la opción **Crear cliente en modo asíncrono** está configurada en **No**.
1. Vaya a **Retail y Commerce \> Canales \> Tiendas en línea**.
1. Seleccione la tienda en línea para la que deshabilitar la creación de clientes asincrónica.
1. En la pestaña **General**, asegúrese de que el campo **Perfil de funcionalidad** está configurado para el perfil de funcionalidad que está utilizando para su canal en línea.

## <a name="additional-resources"></a>Recursos adicionales

[Configurar un inquilino B2C en Commerce](../set-up-b2c-tenant.md)
