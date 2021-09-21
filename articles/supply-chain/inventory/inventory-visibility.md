---
title: Información general sobre el complemento de visibilidad de inventario
description: Este tema explica qué es la visibilidad de inventario y describe sus características.
author: sherry-zheng
ms.date: 10/26/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-10-26
ms.dyn365.ops.version: Release 10.0.15
ms.openlocfilehash: 644eb0d682c35bd604c188aa02e4a6c69b3ff209
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7474997"
---
# <a name="inventory-visibility-add-in-overview"></a>Información general sobre el complemento de visibilidad de inventario

[!include [banner](../includes/banner.md)]

El complemento de visibilidad de inventario (también conocido como *Visibilidad de inventario*) es un microservicio independiente y altamente escalable que permite el seguimiento del inventario disponible en tiempo real. Por lo tanto, proporciona una visión global del inventario.

Los sistemas externos acceden al servicio a través de las API RESTful. De esa manera, pueden consultar información disponible sobre conjuntos de dimensiones dados o realizar cambios en su inventario en diferentes orígenes de datos personalizados.

Como un microservicio que se basa en Microsoft Dataverse, Visibilidad de inventario proporciona extensibilidad. Puedes usar Power Apps para crear aplicaciones. También puede aplicar Power BI para proporcionar una funcionalidad personalizada que cumpla con los requisitos de su negocio.

Puede integrar Visibilidad de inventario con varios sistemas de terceros estableciendo opciones de configuración para dimensiones de inventario estandarizadas y configurando tipos de transacciones. Visibilidad de inventario también admite la extensibilidad personalizada a través de cantidades calculadas configurables.

## <a name="inventory-visibility-integration-with-dynamics-365-supply-chain-management"></a>Integración de Visibilidad de inventario con Dynamics 365 Supply Chain Management

La solución integrada extrae datos de inventario de Dynamics 365 Supply Chain Management y realiza un seguimiento continuo de los cambios de inventario. Para más información, vea [Instalar y configurar la visibilidad de inventario](inventory-visibility-setup.md) y [Configurar la visibilidad del inventario](inventory-visibility-configuration.md).

## <a name="get-a-global-view-of-inventory"></a>Obtener una vista global del inventario

La solución integrada le permite definir sus propios orígenes de datos y centralizar los datos de inventario. Para obtener más información, consulte [Configurar la visibilidad de inventario](inventory-visibility-configuration.md).

Hay dos enfoques para ver su inventario:

- Envíe una consulta a través de la API de alto rendimiento. Esta API puede devolver datos de inventario casi en tiempo real directamente desde una instancia almacenada en caché. Puede encontrar contratos y muestras en las [API públicas de Visibilidad de inventario](inventory-visibility-api.md).
- Vea la lista sin procesar disponible. Esta lista se sincroniza periódicamente desde una instancia en caché y es visible en Dataverse. Para obtener más información, consulte [Aplicación Visibilidad de inventario](inventory-visibility-power-platform.md).

## <a name="soft-reservations"></a>Reservas flexibles

[!INCLUDE [preview-banner-section](../../includes/preview-banner-section.md)]

La reserva flexible se aplica cuando una empresa debe reservar una cantidad específica de productos para respaldar, por ejemplo, el cumplimiento de pedidos de ventas que eviten la sobreventa. Cuando se crea y confirma un pedido de ventas en Supply Chain Management u otros sistemas de gestión de pedidos, se envía una solicitud a Visibilidad de inventario para reservar la cantidad. Visibilidad de inventario le permite reservar productos que tienen detalles de dimensión y tipos de transacciones de inventario específicos. (Para obtener más información, consulte [Aplicación Visibilidad de inventario](inventory-visibility-power-platform.md).) Una vez que la cantidad se ha reservado correctamente, se devuelve un Id. de reserva. Puede utilizar este Id. de reserva para vincular el pedido original en Supply Chain Management u otros sistemas de gestión de pedidos.

La funcionalidad está diseñada para que una reserva en Visibilidad de inventario no cambie la cantidad total. En cambio, solo marca la cantidad reservada. (Por esta razón, se llama *reserva flexible*.) La cantidad reservada de forma flexible se puede compensar cuando los productos se consumen en Supply Chain Management o en un sistema de terceros llamando a la API nuevamente para hacer una deducción de cantidad y actualizar la cantidad total en Visibilidad de inventario. Para obtener más información, consulte [Reservas de Visibilidad de inventario](inventory-visibility-reservations.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
