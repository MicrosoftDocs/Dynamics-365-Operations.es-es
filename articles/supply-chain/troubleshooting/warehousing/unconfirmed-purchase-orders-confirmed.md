---
title: La tarea Actualizar recibos de productos confirma pedidos no confirmados
description: Después de ejecutar Actualizar recibos de productos, el sistema confirma los pedidos no confirmados que tienen el estado de Registrado. Obtenga más información sobre la función que soluciona este problema.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 171a978efc6b55b92f429381e72036cb1b3296c6
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477489"
---
# <a name="unconfirmed-purchase-orders-are-confirmed-after-running-update-product-receipts"></a>Los pedidos de compra no confirmados se confirman después de ejecutar Actualizar recepciones de producto

## <a name="symptoms"></a>Síntomas

Después de ejecutar la tarea periódica *Actualizar recibos de productos*, el sistema confirma automáticamente las órdenes de compra no confirmadas que tienen un estado de transacción de inventario de *Registrado*.

## <a name="resolution"></a>Resolución

Una nueva función de manipulación de carga entrante, *Sobre recepción de cantidades de carga*, soluciona este problema. Para activar esta característica, vaya al espacio de trabajo [Administración de características](/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview) y active las siguientes características en el mismo ordenen que se enumeran:

1. Asociar transacciones de inventario de pedido de compra a carga
2. Recepción en exceso de cantidades de carga

Para más información, vea [Contabilice las cantidades de producto registradas contra las órdenes de compra](/dynamics365/supply-chain/warehousing/inbound-load-handling).
