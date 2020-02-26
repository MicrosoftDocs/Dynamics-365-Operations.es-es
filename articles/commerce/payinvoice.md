---
title: Configurar situaciones de pago de facturas
description: En este tema se describe cómo configurar Dynamics 365 Commerce para diversos escenarios relacionados con el pago de facturas.
author: josaw1
manager: AnnBe
ms.date: 11/14/2018
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 9fe8fde32549568812a724311781d3515ef7036c
ms.sourcegitcommit: 81a647904dd305c4be2e4b683689f128548a872d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/01/2020
ms.locfileid: "3004421"
---
# <a name="set-up-pay-invoice-scenarios"></a>Configurar situaciones de pago de facturas

[!include [banner](includes/banner.md)]

La funcionalidad de pago de facturas de Dynamics 365 Commerce se ha ampliado para permitir:

- El pago de varias facturas de pedidos de ventas en una sola transacción de PDV.
- El pago de diversos tipos de factura de cliente, incluidas las facturas de servicios, las facturas basadas en proyectos y las notas de abono.

Para habilitar estas situaciones, debe configurarse el perfil de funcionalidad para las tiendas como se indica a continuación.

1. Vaya a **Retail y Commerce \> Configuración de canal \> Configuración de PDV \> Perfiles de PDV \> Perfiles de funcionalidad** y seleccione un perfil que esté vinculado a las tiendas para las que desea realizar cambios.
2. En la pestaña **Funciones**, configure los siguientes parámetros si es necesario.

    - **Factura de pedido de ventas**: seleccione **Sí** para permitir a los usuarios pagar una o más facturas de pedido de ventas en una sola transacción de PDV.
    - **Factura de servicios**: seleccione **Sí** para permitir a los usuarios pagar una o más facturas de servicios en una sola transacción de PDV.
    - **Factura de proyecto**: seleccione **Sí** para permitir a los usuarios pagar una o más facturas de proyecto en una sola transacción de PDV.
    - **Nota de abono de pedidos de ventas**: seleccione **Sí** para permitir a los usuarios liquidar varias notas de abono de pedido de ventas para facturas abiertas o procesar un reembolso al cliente para una nota de abono abierta.

> [!NOTE]
> Aún no se admite el pago o liquidación de importes parciales.
